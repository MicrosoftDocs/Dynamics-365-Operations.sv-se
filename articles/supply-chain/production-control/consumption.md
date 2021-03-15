---
title: Beräkna materialförbrukning
description: Den här artikeln innehåller information om olika alternativ som är relaterade till beräkningen av materialförbrukning.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acccc677c855fc675d52814d7f6f0a5141bbc8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001683"
---
# <a name="calculate-material-consumption"></a>Beräkna materialförbrukning

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om olika alternativ som är relaterade till beräkningen av materialförbrukning. 

Följande alternativ, som är relaterade till beräkningen av materialförbrukning, är tillgängliga på flikarna **Inställningar** och **Stegförbrukning** på snabbfliken **Radinformation** på sidan **Strukturlista**.

## <a name="variable-and-constant-consumption"></a>Variabel och konstant förbrukning
I fältet **Förbrukningen är** kan du välja om förbrukningen ska beräknas som en konstant kvantitet eller en variabel kvantitet. Välj **Konstant** om en fast kvantitet eller volym krävs för tillverkningen, oavsett den kvantitet som tillverkas. Välj **Variabel** som är standardinställningen om det obligatoriska beloppet för material i de färdiga varorna är proportionellt mot antalet färdiga varor som tillverkas.

## <a name="calculating-consumption-from-a-formula"></a>Beräkna förbrukning från en formel
I fältet **Formel** kan du ställa in olika formler för beräkning av materialförbrukning. Om du använder standardvärde **Standard**, beräknas förbrukningen inte från en formel. Följande formler fungerar tillsammans med fälten **Höjd**,  **Bredd** **Djup** **Densitet**, och **Konstant**:

-   Höjd \* Konstant
-   Höjd \* Bredd \* Konstant
-   Höjd \* Bredd \* Djup \* Konstant
-   (Höjd \* Bredd \* Djup / Densitet) \* Konstant

## <a name="rounding-up-and-multiples"></a>Avrundning och multipler.
Tillsammans låter fälten **Avrundning** och **Multipler** avrunda värdet för materialförbrukning. Du kan till exempel avrunda värdet enligt hanteringsenheten där råmaterial plockas för produktion. Följande alternativ är tillgängliga i fältet **Avrundning**: **Kvantitet** **Mått**, och **Förbrukning**.

### <a name="quantity"></a>Kvantitet

Om du väljer **Kvantitet** som avrundningsmekanism måste kvantiteten vara en multipel av den angivna kvantiteten. När till exempel hela tal krävs anger du 1 i fältet **1** i fältet **Multipler**. Nummer avrundas sedan upp till en kvantitet som är delbar med 1.

### <a name="measurement"></a>Mått

Vanligtvis väljer du **Mått** som avrundningsmekanism när råmaterial levereras i bestämda dimensioner. Till exempel krävs en del av metallröret på 2 meter för färdig vara och metallröret lagras i längder på 4,5 meter. I detta fall kan avrundningsmekanismen **Mått** användas för att beräkna hur många metallrör som krävs för att skapa ett visst antal enheter av den färdiga varan. I det här exemplet anges fältet **Formel** som **höjd \* Konstant**. Fältet **Höjd** anges som **2** för att ange längden på röret som krävs för den färdiga varan. Fältet **Multipel** är inställt på **4,5** för att ange att röret plockas i längder på 4,5 meter. Beräkningen är:

1.  Antal multiplar som krävs för 10 delar av den färdiga varan: 10 ÷ 2 = 5 enheter
2.  Total förbrukning: 4,5 × 5 = 22,5 meter av metallrör

Det antas att 0,5 rör kasseras för var femte del av röret som förbrukas.

### <a name="consumption"></a>Förbrukning

Vanligtvis väljer du **Förbrukning** som avrundningsmekanism när råmaterial måste plockas i hela kvantiteter för en specifik hanteringsenhet av produkten. Till exempel används 2 liter färg för att tillverka en enhet av en färdig vara och målarfärgen plockas i 25 kvartars burkar. I detta fall kan avundningsmekanismen **Förbrukning** användas för att avrunda förbrukning till heltal i 25 kvartars burkar. Här följer beloppet för beräkningen av färg som krävs, om 180 enheter av den färdiga varan måste produceras:

1.  Målning som krävs, exklusive kassation: 180 × 2 = 360 liter
2.  Antal burkar: 360 ÷ 25 = 14,4, som avrundas uppåt till 15
3.  Målning som krävs, inklusive kassation: 15 × 25 = 375 liter

## <a name="step-consumption"></a>Stegförbrukning
Stegförbrukning används för att beräkna konstant förbrukning i kvantitetintervall. Om du väljer **Stegförbrukning** i fältet **Formel** på fliken **Inställningar** kan du lägga till information om stegen i fliken **Stegförbrukning**. Den fasta förbrukade kvantiteten kan anges i intervaller för den framställda kvantiteten. Till exempel stegförbrukning har angetts i tabellen nedan.

| Från serie | Kvantitet |
|-------------|----------|
| 0,00        | 10,0000  |
| 100,00      | 20,0000  |
| 200,00      | 40,0000  |

Kvantiteten för strukturlista (BOM) är 1, och produktionskvantiteten är 110. Formeln för förbrukningen är From series (kvantitet) = förbrukning. Eftersom produktionskvantiteten är 110, är den i "Från 100-serien". Därför är kvantiteten 20.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]