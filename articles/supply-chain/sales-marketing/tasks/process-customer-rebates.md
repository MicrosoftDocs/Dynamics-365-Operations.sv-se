---
title: Generera och bearbeta kundrabatter
description: Den här proceduren visar hur du vill bearbeta kunden rabatter från krav generation till passerar dem såsom periodiseringar av kundfordringar.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8ebc281036842bdc8965e062990438e1fb466ff
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986874"
---
# <a name="generate-and-process-customer-rebates"></a>Generera och bearbeta kundrabatter

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du vill bearbeta kunden rabatter från krav generation till passerar dem såsom periodiseringar av kundfordringar. Den promenader dig genom ett konkret exempel för att förklara hur olika villkor för rabatten rader påverkar det slutliga belopp som skall krediteras kunden. Du behöver använda USMF demo företaget och utföra följande uppgifter innan du startar guiden: (1) Gå till kundfordringar parametrar sidan och expandera fliken priser och sedan priset på fliken Detaljer och kontrollera att aktivera prisuppgifter alternativet är inställt på Ja. (2) Gå till rabatt avtal sidan och välj kund rabatt avtal: USMF-000001. Om fältet Status för arbetsflödesgodkännande inte har angetts som Godkänt, måste du klicka på Validering i åtgärdsfönstret för att godkänna det.


## <a name="review-a-customer-rebate-agreement"></a>Granska ett kundrabattavtal
1. Gå till **Navigeringsfönstret > Moduler > Försäljning och marknadsföring > Kundrabatter > Rabattavtal**.
    - Nästa steg Titta på villkoren i avtalet USMF-000001. Detta gör det enklare att förstå hur kundkreditvärdena beräknas längre fram i proceduren.  
    - Avtalet gäller för en enskild kund, i den här exemplet kund US-009.  
    - Rabatter ska ges till kunden när han/hon köper en viss produkt. I det här fallet har produkten artikelnummer T0020.   
    - Kundens försäljningsresultat, som används för att beräkna rabattbelopp, ska ackumuleras på en veckobasis.  
    - Inställningen för "Pris hämtat från" är Brutto, vilket innebär att radens försäljningsbelopp, som används som bas för att beräkna kravet inte reduceras av radrabatten.  
    - I fältet Radbrytningstyp för rabatt visas metoden för att beräkna rabatter. I det här fallet anges försäljningsmålet, som används för att beräkna rabatterna, till Kvantitet.   
    - Avtalets rader anger rabattbeloppstyp, det faktiska rabattvärdet och trösklarna. I det här exemplet kvalificerar sig kunden för en rabatt på 200 kronor per såld enhet, om veckoinköpen av produkten ligger inom 1 till 50 enheter och en rabatt på 400 kronor per såld enhet, om de köper över 50 enheter.  
2. Stäng sidan.

## <a name="generate-rebate-claims"></a>Generera rabattanspråk
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Klicka på **Ny**. Om du vill efterlikna det sätt som rabattanspråk genereras på, är nästa uppgift är att skapa en försäljningsorder, där produkten och kvantiteten kvalificerar kunden i fråga för en rabatt.    
3. Ange eller välj ett värde i fältet **Kundkonto**.
4. Klicka på **OK**.
5. I fältet **artikelnummer** anger du eller väljer ett värde.
6. Ställ in **kvantiteten** på 40.
7. Under avsnittet **Försäljningsorderrader**, klicka på **Försäljningsorderrader**.
8. Klicka på **prisuppgifter**. Om du inte ser det här alternativet beror det på att du inte har ställt in alternativet **Aktivera prisinformation** till Ja innan du startade guiden.     
9. Expandera avsnittet **Rabatter**. Fliken **Rabatter** listar alla rabattavtal som är tillämpliga för den aktuella orderraden och visar den beräknade rabatten. Observera att det visas beloppen endast indikationer på vad framtida rabatten yrkanden kan vara. De faktiska rabattbeloppen kan vara olika beroende på: den totala försäljningsvolymen som har erhållits av kunden under ett periodiskt rabattavtal, om kunden har returnerat alla kvantiteter eller delkvantiteter och om den tillämpliga försäljningsordern har fakturerats.
10. Stäng sidan.
11. Klicka på **Lägg till rad**.
12. I fältet **artikelnummer** anger du eller väljer ett värde.
13. Ställ in **kvantiteten** på 60.
14. Klicka på **Spara**.
15. Klicka på **Faktura** i **åtgärdsfönstret**.
16. Klicka på **faktura**.
17. Expandera avsnittet **Parametrar**.
18. I fältet **Kvantitet**, välj 'Alla'.
19. Klicka på **OK**.
20. Klicka på **OK**.

## <a name="process-rebate-claims"></a>Bearbeta rabattkrav
1. Gå till **Navigeringsfönstret > Moduler > Försäljning och marknadsföring > Kundrabatter > Rabatter**.
    - Rabattsidan fungerar som en workbench där du kan granska, godkänna och bearbeta rabattanspråk. Du kommer nu att behandla de ansökningar som skapats som ett resultat av fakturering till en försäljningsorder för kunden oss-009, som är föremål för avtal om rabatt USMF-000001.   
    - Den första raden representerar ett rabattanspråk på 8 000 SEK, baserat på försäljning av 40 enheter av produkt T0020, som beräknas till 200 kronor per enhet. Det matchar villkoren för den första kvantitetsbrytningen i rabattavtalet.  
    - Det andra anspråket är för 24 000 SEK, baserat på försäljning av 60 enheter av produkt T0020, som beräknas till 400 SEK per enhet, i enlighet med det andra kvantitetsbrytningen i avtalet.  
    - Båda anspråken har statusen "Ska beräknas". Det innebär att de är associerade med ett avtal som spårar kundens försäljningsresultat på periodisk basis och att de måste beräknas om för kontot för den totala försäljningsvolymen inom respektive period.   
2. Klicka på **Slå samman**.
3. Ange eller välj ett värde i fältet **Kund**.
4. I fältet **startdatum** väljer du dagens datum.
5. Klicka på **OK**. Som ett resultat av att funktionen **Ackumulera** har körts har det beräknade anspråksbeloppet nu justerats till konto på grund av att kundens totala försäljningsvolym i den relevanta perioden är högre än när den första rabatten genererades. Mer specifikt, eftersom den totala inköpta kvantiteten har nått 100 enheter, kunden nu kvalificerar sig för 40 USD per enhet (enligt överenskommelse andra kvantiteten rast) eller 400 USD av den totala rabatten. Skillnaden är registrerat som ett nytt krav "justering" för ytterligare 800 USD. Statusen för de rabattanspråk som är inkluderade i den ackumulerade uppdateringen anges nu till Beräknad. 
6. Markera alla rader i listan.
7. Klicka på **Godkänn**.
8. Klicka på **Bearbeta**.
9. Ange eller välj ett värde i fältet **Kund**.
10. Klicka på **OK**. I ett meddelande visas att rabatten har bearbetats och att statusen för anspråken har ändrats till Markera. Det innebär att en periodiseringsjournal för rabatt bokförs:
    - Anspråk har nu överförts till tillfälliga kundsaldot som avdrag.
    - Rabattperiodiseringskontot har krediterats för att representera framtida ansvar mot kunden.
    - Utgiftskontot för rabatt debiterades för att känna igen den kostnad som uppstod i samband med försäljning.   

