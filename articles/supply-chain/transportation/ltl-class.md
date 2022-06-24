---
title: Mindre än lastbilsklasser (LTL)
description: I denna artikel beskrivs vad mindre än "lastbilsklasser" (LTL; "truckload") är och hur du konfigurerar dem i Microsoft Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9ab05e1bc5d0ae2c8b5d98dda32660d2436676e9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857211"
---
# <a name="less-than-truckload-ltl-classes"></a>Mindre än lastbilsklasser (LTL)

[!include [banner](../includes/banner.md)]

En klass som är mindre än truckload (LTL) är en fraktleveransklass som används för att klassificera artiklar som kan levereras. I allmänhet har varje typ av produkt eller vara en kod för nationell motorfraktklassificering (NMFC) som motsvarar ett specifikt fraktklassnummer för LTL-försändelser. LTL-fraktklasser representerar artikelkategorier, medan NMFC-koder rör specifika varor i var och en av de 18 fraktklasserna.

Denna funktion låter dig använda ditt system för att utföra följande uppgifter:

- Definiera LTL-fraktklasserna som används i företaget.
- Tilldela varje LTL-klass till en NMFC-kod på sidan **NMFC-koder**. Mer information finns i [National Motor Freight Classification (NMFC)-koder](nmfc-codes.md).
- Tilldela en NMFC-kod (och därmed dess tillhörande LTL-kod) till respektive produkt på sidan **Produkter**.
- Bedöma korrekt LTL-klass för respektive produkt som en NMFC-kod har tilldelats till.
- Fastställ förpackningskraven för varje LTL-klass genom att kontrollera de internationella LTL-standarderna. På detta sätt ser du till att dina produkter är väl skyddade och levereras säkert.
- Få korrekta leveransuppskattningar, baserat på LTL-fraktklassen för respektive produkt.

I denna artikel beskrivs hur du skapar LTL-klasser i Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Skapa en LTL-klass

Gör så här om du vill skapa en LTL-klass:

1. Gör något av följande:

    - Gå till **Lagerstyrning \> Inställningar \> Lager \> LTL-klasser**.
    - Gå till **Transporthantering \> Inställningar \> Transportstandarder \> LTL-klasser**.

2. I åtgärdsfönstret väljer du **Ny** för att skapa en LTL-klass. Ange sedan följande fält:

    - **LTL-klass** – Ange företagets interna LTL-klassidentifierare (ID) för varutypen. De flesta företag använder den internationella standarden. I sådana fall matchar värdet i det här fältet värdet för fältet **Klass**. Om ditt företag använder sin egen standard anger du dock en kod som överensstämmer med den standarden.
    - **Namn** – Ange ett beskrivande namn som gör det möjligt för dig och andra användare att välja rätt LTL-klass för varje NMFC-kod.
    - **Klass** – Ange ID för internationell standard-LTL-klass för artikeltypen. Koden du anger här måste överensstämma med den officiella standarden.

## <a name="example-set-up-ltl-classes"></a>Exempel: Konfigurera LTL-klasser

Följande exempel visar hur du konfigurerar två olika LTL-klasser som du kan använda med olika produkttyper.

1. Gå till **Lagerstyrning \> Inställningar \> Lager \> LTL-klasser**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden på denna nya rad:

    - **LTL-klass:** *92.5*
    - **Namn:** *Datorer, monitorer, kylskåp*
    - **Klass:** *92.5*

1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden på denna nya rad:

    - **LTL-klass:** *125*
    - **Namn:** *Mindre hushållsmaskiner*
    - **Klass:** *125*

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

- [National Motor Freight Classification (NMFC)-koder](nmfc-codes.md)
- [Skapa en fraktsedel](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
