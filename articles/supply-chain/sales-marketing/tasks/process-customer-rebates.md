--- 
title: Generera och bearbeta kundrabatter
description: "Den här proceduren visar hur du vill bearbeta kunden rabatter från krav generation till passerar dem såsom periodiseringar av kundfordringar."
author: omulvad
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 348793abc6d219f38bcdc2629b77343d93927005
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="generate-and-process-customer-rebates"></a>Generera och bearbeta kundrabatter

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du vill bearbeta kunden rabatter från krav generation till passerar dem såsom periodiseringar av kundfordringar. Den promenader dig genom ett konkret exempel för att förklara hur olika villkor för rabatten rader påverkar det slutliga belopp som skall krediteras kunden. Du behöver använda USMF demo företaget och utföra följande uppgifter innan du startar guiden: (1) Gå till kundfordringar parametrar sidan och expandera fliken priser och sedan priset på fliken Detaljer och kontrollera att aktivera prisuppgifter alternativet är inställt på Ja. (2) Gå till rabatt avtal sidan och välj kund rabatt avtal: USMF-000001. Om fältet Status för arbetsflödesgodkännande inte har angetts som Godkänt, måste du klicka på Validering i åtgärdsfönstret för att godkänna det.


## <a name="review-a-customer-rebate-agreement"></a>Granska ett kundrabattavtal
1. Gå till försäljning och marknadsföring > kund rabatter > Rabatt avtal.
    * Nästa steg Titta på villkoren i avtalet USMF-000001. Detta gör det enklare att förstå hur kundkreditvärdena beräknas längre fram i proceduren.  
    * Avtalet gäller för en enskild kund, i den här exemplet kund US-009.  
    * Rabatter ska ges till kunden när han/hon köper en viss produkt. I det här fallet har produkten artikelnummer T0020.   
    * Kundens försäljningsresultat, som används för att beräkna rabattbelopp, ska ackumuleras på en veckobasis.  
    * Inställningen för "Pris hämtat från" är Brutto, vilket innebär att radens försäljningsbelopp, som används som bas för att beräkna kravet inte reduceras av radrabatten.  
    * I fältet Radbrytningstyp för rabatt visas metoden för att beräkna rabatter. I det här fallet anges försäljningsmålet, som används för att beräkna rabatterna, till Kvantitet.   
    * Avtalets rader anger rabattbeloppstyp, det faktiska rabattvärdet och trösklarna. I det här exemplet kvalificerar sig kunden för en rabatt på 200 kronor per såld enhet, om veckoinköpen av produkten ligger inom 1 till 50 enheter och en rabatt på 400 kronor per såld enhet, om de köper över 50 enheter.  
2. Stäng sidan.

## <a name="generate-rebate-claims"></a>Generera rabattanspråk
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
    * Om du vill efterlikna det sätt som rabattanspråk genereras på, är nästa uppgift är att skapa en försäljningsorder, där produkten och kvantiteten kvalificerar kunden i fråga för en rabatt.  
3. I fältet Kundkonto, ange eller välj ett värde.
4. Klicka på OK.
5. Ange eller välj ett värde i fältet Artikelnummer.
6. Ställ in kvantiteten på 40.
7. Klicka på Försäljningsorderrad.
8. Klicka på Prisinformation.
    * Om du inte ser det här alternativet beror det på att du inte har ställt in alternativet Aktivera prisinformation till Ja innan du startade guiden.  
9. Expandera avsnittet Rabatter.
    * På fliken Rabatt visas alla rabattavtal som gäller för den aktuella orderraden och det beräknade rabattbeloppet. Observera att det visas beloppen endast indikationer på vad framtida rabatten yrkanden kan vara. De faktiska rabattbeloppen kan vara olika beroende på: den totala försäljningsvolymen som har erhållits av kunden under ett periodiskt rabattavtal, om kunden har returnerat alla kvantiteter eller delkvantiteter och om den tillämpliga försäljningsordern har fakturerats.  
10. Stäng sidan.
11. Klicka på Lägg till rad.
12. Ange eller välj ett värde i fältet Artikelnummer.
13. Ställ in kvantiteten på 60.
14. Klicka på Spara.
15. Klicka på Faktura i åtgärdsfönstret.
16. Klicka på Faktura.
17. Expandera avsnittet Parametrar.
18. Välj Alla i fältet Kvantitet.
19. Klicka på OK.
20. Klicka på OK.

## <a name="process-rebate-claims"></a>Bearbeta rabattkrav
1. Gå till försäljning och marknadsföring > kund rabatter > rabatter.
    * Rabattsidan fungerar som en workbench där du kan granska, godkänna och bearbeta rabattanspråk. Du kommer nu att behandla de ansökningar som skapats som ett resultat av fakturering till en försäljningsorder för kunden oss-009, som är föremål för avtal om rabatt USMF-000001.   
    * Den första raden representerar ett rabattanspråk på 8 000 SEK, baserat på försäljning av 40 enheter av produkt T0020, som beräknas till 200 kronor per enhet. Det matchar villkoren för den första kvantitetsbrytningen i rabattavtalet.  
    * Det andra anspråket är för 24 000 SEK, baserat på försäljning av 60 enheter av produkt T0020, som beräknas till 400 SEK per enhet, i enlighet med det andra kvantitetsbrytningen i avtalet.  
    * Båda anspråken har statusen "Ska beräknas". Det innebär att de är associerade med ett avtal som spårar kundens försäljningsresultat på periodisk basis och att de måste beräknas om för kontot för den totala försäljningsvolymen inom respektive period.   
2. Klicka på Ackumulera.
3. Ange eller välj ett värde i fältet Kund.
4. Välj dagens datum i fältet Startdatum.
5. Klicka på OK.
    * Som ett resultat av att funktionen Ackumulera har körts har det beräknade anspråksbeloppet nu justerats till konto på grund av att kundens totala försäljningsvolym i den relevanta perioden är högre än när den första rabatten genererades. Mer specifikt, eftersom den totala inköpta kvantiteten har nått 100 enheter, kunden nu kvalificerar sig för 40 USD per enhet (enligt överenskommelse andra kvantiteten rast) eller 400 USD av den totala rabatten. Skillnaden är registrerat som ett nytt krav "justering" för ytterligare 800 USD. Statusen för de rabattanspråk som är inkluderade i den ackumulerade uppdateringen anges nu till Beräknad.   
6. Markera alla rader i listan.
7. Klicka på Godkänn.
8. Klicka på Process.
9. Ange eller välj ett värde i fältet Kund.
10. Klicka på OK.
    * I ett meddelande visas att rabatten har bearbetats och att statusen för anspråken har ändrats till Markera. Detta innebär att som ett resultat av en rabatt periodiseringsjournal som konteras: a) kraven har nu överförts till den temporära kund balans som avdrag; b) Rabatten accrual konto har krediterats utgör den framtida ansvar gentemot kunden, och c) Rabatten bekostnad konto har debiterats, erkännande av kostnader i samband med försäljning.   


