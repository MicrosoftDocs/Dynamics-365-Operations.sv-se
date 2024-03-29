---
title: Fel fältvärde i TaxTrans
description: I denna artikel finns information om felsökning av felaktiga fältvärden i TaxTrans.
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6e7329ffdc04207116c92cb42e02750b176713fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899826"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Fel fältvärde i TaxTrans

[!include [banner](../includes/banner.md)]

Om ett fältvärde i **TaxTrans** är fel använder du informationen i detta ämne för att lösa problemet.

## <a name="overview-of-values"></a>Översikt över värden
I följande lista visas hur **TaxTrans**, **TaxUncommitted** och **TmpTaxWorkTrans** påminner om datauppsättningar men fungerar på olika sätt.

  - **TaxTrans** är det slutligt bokförda skattetransaktionsresultatet som finns kvar i databasen.
  - **TaxUncommitted** är det mellanliggande beräknade skatteresultatet som finns kvar i databasen (om tillämpligt) och som kommer att användas senare vid bokföring.
  - **TmpTaxWorkTrans** är det tillfälligt beräknade skatteresultatet i registret i minnet (Registertyp = InMemory).

Om du hittar rotorsaken till en felaktig **TaxTrans**-kolumn har du även funnit rotorsaken till en felaktig **TaxUncommitted**- eller **TmpTaxWorkTrans**-kolumn. Detta beror på att de tre kolumnerna kopieras från varandra.

I samband med skatteberäkning genereras vanligtvis **TmpTaxWorkTrans**, varefter **TaxUncommitted** genereras (om tillämpbart). Under skattebokföringen genereras **TaxTrans**.


## <a name="add-breakpoints"></a>Lägga till brytpunkter
Utför följande steg för att lägga till brytpunkter: 

1. Lägg till tillägg och brytpunkter i *insert()* och *update()* i tilläggen enligt nedan.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Du kan också lägga till brytpunkter direkt när **TaxUncommitted** inte ingår.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Återskapa och felsöka

När brytpunkter har ställts in visas varje databeständighetsändring under felsökningen. Om du vill hitta rotorsaken till en felaktig kolumn med **TaxTrans**, **TaxUncommitted** eller **TmpTaxWorkTrans**, kan du granska och observera följande artiklar:

- Den sista brytpunkten där kolumnen är korrekt.
- Den första brytpunkten där kolumnen är felaktig.
- Det som händer mellan dessa två poäng.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns
Om du har utfört stegen i de föregående avsnitten men inte har lyckats lösa problemet, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning kontaktar du Microsoft Support för hjälp.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

