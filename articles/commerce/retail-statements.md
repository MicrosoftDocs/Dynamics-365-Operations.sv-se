---
title: Butiksutdrag
description: Denna artikel beskriver hur rapporter skapas och bokförs.
author: ashishmsft
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 0717c1198171f411e3c52233200ecfcc213dc13f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878467"
---
# <a name="retail-statements"></a>Butiksutdrag

[!include [banner](includes/banner.md)]

I Dynamics 365 Commerce är bokföringsprocessen för utdraget att ta hänsyn till de transaktioner som sker i molnbaserad kassa (POS) eller Modern POS (MOPS). Bokföringsprocessen för utdrag använder distributionsschemat för att hämra en uppsättning kassatransaktioner till klientens huvudkontor (HQ). De parametrar som definieras på sidorna **Handelsparametrar** och **Butiker** används för att välja vilka transaktioner som hämtas till enskilda rapporter.

Utdragsbokföringsprocessen illustreras i följande diagram. I denna process överförs transaktioner som är registrerade i POS till klienten, genom att Commerce schemaläggare används. När klienten har tagit emot transaktionerna kan du skapa, beräkna och bokföra transaktionsutdraget för butiken.

[![Bokföringsprocess för utdrag.](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Skapa och bokföra utdrag

Du kan skapa ett utdrag manuellt, eller genom att använda de Batch processer, ställer du in så att den körs periodvis under dagen. I båda fallen används följande steg för att skapa och bokföra utdrag.

### <a name="create-the-statement"></a>Skapa utdraget

Det här steget identifierar den butik som utdraget skapas manuellt för. Om du konfigurerar en batchprocess, kan du automatiskt skapa utdrag för alla butiker som baseras på en tidsplan som du definierar.

### <a name="calculate-the-statement"></a>Beräkna utdraget

I det här steget väljs transaktionsraderna utifrån villkor som definieras för varje butik i på sidorna **Handelsparametrar** och **Butiker**. På dessa sidor definierar du villkoren och anger hur transaktionerna beräknas. Om du vill visa en lista över de transaktioner som är inkluderade i utdraget, innan du beräknar utdraget, använder du **Transaktioner**.

En utdragsberäkning använder kassaavstämningar från kassor som beräknat belopp. Alternativt kan du ange det räknade beloppet manuellt. Utdraget visar skillnaden mellan försäljningsbeloppet för transaktionerna och det verkliga beräknade beloppet i alla betalsätt. Utdraget bokförs endast om avvikelsen är mindre än den maximalt tillåtna för butiken.

> [!NOTE]
> Beräkningsprocessen för utdraget använder den globala nummerserien.

När du beräknar ett utdrag inkluderar beräkningen följande uppgifter:

- Markera transaktioner som inte är inkluderade i en tidigare utdragsberäkning för det valda datumintervallet.
- Beräkna totalbelopp som avstämts i valda transaktioner. Resultaten visas på utdragsrader, beroende på utdragsmetoden:

    - Om utdragsmetoden är **Totalt** skapas en rad för varje betalningsmetod i de valda transaktionerna.
    - Om utdragsmetoden är **Personal** skapas en rad för varje betalningsmetod i de transaktioner som har gjorts av den valda personalmedlemmen.
    - Om utdragsmetoden är **Kassaterminal** skapas en rad för varje betalningsmetod i de transaktioner som har gjorts på den valda POS.
    - Om utdragsmetoden är **Skift** skapas en rad för varje betalningsmetod i de transaktioner som har gjorts under ett skift.

Om kryssrutan **Dela upp efter utdragsmetod** är markerad på sidan **butiker** skapas ett separat uttryck baserat på värdet som valts på fliken **utdragsmetod**.

Om din butiks öppettider förlängdes till efter midnatt, kan du konfigurera utdragsbokföring som baseras på slutet av arbetsdagen i stället för slutet av kalenderdagen.

På sidan **Butiker** på snabbfliken **Utdrag/stängning** i fältet **Slut på vardagen** anger du den tidpunkt då den senaste transaktionen måste registreras för att inkluderas i arbetsdagens utdrag. Markera kryssrutan **Bokför som vardag** för att bokföra transaktionerna på samma vardag. När utdraget bokförs kan transaktionerna som registreras inom samma arbetsdag inkluderas på samma försäljningsorder, även om de infaller före och efter midnatt.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Exempel: Bokföra ett utdrag för en arbetsdag som sträcker sig över två kalenderdagar

En butik har öppet mellan kl 08:00 och 03:00 och kryssrutan **Bokför som vardag** är markerad i butikens konfigurationen. Den 31 maj registrerar butiken transaktioner mellan kl 08:00 och midnatt. Butiken registrerar även transaktioner mellan kl 00:01 och 03:00 den 1 juni.

När butiken bokför sitt utdrag för slutet av arbetsdagen, skapas en försäljningsorder som omfattar alla transaktioner som har registrerats under öppettider mellan kl 08:00 och 03:00 även om transaktionerna inträffade de två dagarna 31 maj och 1 juni.

Om kryssrutan **Bokför som vardag** är avmarkerad för samma butik, genereras separata försäljningsorder när butiken bokför sitt utdrag vid slutet av arbetsdagen. En försäljningsorder innehåller transaktionerna som har registrerats för öppettider mellan kl 08:00 och midnatt den 31 maj, och den andra försäljningsordern inkluderar transaktioner som har registrerats affärstiderna mellan kl 00:01 och 03:00 den 1 juni.

> [!NOTE]
> Innan du kan skapa utdrag måste du stänga skiften i utdragsperioden.

### <a name="post-the-statement"></a>Bokför utdraget

När du bokför ett utdrag, skapas fakturor för försäljningsorder och försäljning i utdraget.

- Hemköpsförsäljning (cash and carry) aggregeras till en försäljningsorder och faktureras för standardkunden som har tilldelats till butiken.
- Försäljning, för vilken en kund lades till i transaktionen i POS genererar separata försäljningsorder och fakturor, en för varje unik kund.

Betalningsjournaler skapas automatiskt för betalningarna i utdraget och lagret uppdateras för kassabutiken.


[!INCLUDE[footer-include](../includes/footer-banner.md)]