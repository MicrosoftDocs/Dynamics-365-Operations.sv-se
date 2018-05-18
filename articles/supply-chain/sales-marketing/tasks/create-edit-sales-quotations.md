--- 
title: "Skapa och redigera försäljningsofferter"
description: "I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
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
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: 7ffa4fe8d87db5b3f8293ec9dbc042496d09d6e3
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---
# <a name="create-and-edit-sales-quotations"></a>Skapa och redigera försäljningsofferter

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert. Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.


## <a name="create-a-sales-quotation"></a>Skapa en försäljningsoffert.
1. Gå till försäljning och marknadsföring > offerter > Alla offerter.
2. Klicka på Ny.
3. Välj Potentiell kund i fältet Kontotyp.
4. Ange eller välj ett värde i fältet Potentiell kund.
5. Expandera avsnittet Allmänt.
    * Eftersom du valde att skapa en offert från området Försäljning och marknadsföring ställs typen automatiskt in på Försäljningsoffert. Om du vill skapa en offert för ett projekt måste du öppna det från modulen Projekthantering och redovisning.   
6. Klicka på OK.
    * Fälten och åtgärder på offertraderna liknar de på försäljningsorderraderna.   På samma sätt som med försäljningsorder kan offerter skapas för en specifik artikel eller, när artikelnumret är okänt eller inte finns när offerten skapas, också kan offerter skapas för en försäljningskategori.  
7. Ange eller välj ett värde i fältet Artikel.
8. Ange ett värde i fältet Artikel.
9. Stäng sidan.
10. Ange ett tal i fältet Kvantitet.
    * Om det finns giltiga handelsavtal för den markerade artikeln på raden, kommer tillhörande pris och rabatter automatiskt kopieras till offertraden. Kontrollera att enhetsprisfältet innehåller ett värde och du kan även ange rabattvärden, om du vill.  
11. Klicka på Spara.
12. Klicka på Försäljningsoffert i åtgärdsfönstret.
13. Klicka på Summor.
14. Klicka på OK.
15. Klicka på Försäljningsoffertrad.
16. Klicka på Priser.
    * I Kör pris simulering kan du experimentera med att justera det förväntade inkomster eller lönsamheten för din offert utifrån önskat pris per enhet, rabattbelopp, rabatt i procent, totalt belopp, marginal, eller bidrag.   När du är nöjd med mål att tillämpa förslaget till offertraden och dess pris-relaterade fält uppdateras.  
    * Du kan skapa så många prissimuleringar som du vill ha. När du klickar på Nytt, kopieras prisvillkoren från den aktuella offertraden till sidan. Du kan sedan ändra värdena i någon av de prisrelaterade fälten till målfältet. En ändring i ett av fälten leder till omräkning av alla övriga fält. För att systemet ska kunna beräkna försäljningsmarginalen och täckningsgraden, måste produktens enhetskostnad vara känd. Använd fliken Simulerade priser för en detaljerad vy över de ursprungliga priserna, föreslagna ändringarna och deras inverkan på offertsummorna.   Som en allmän regel räknar systemet om och anger ett nytt värde i fältet Enhetspris när en simulering som anger ett nytt belopp används på offertraden. Om simuleringen baseras på en ny marginal eller ny täckningsgrad, uppdateras bara nettobeloppsfältet, medan enhetspriset är tomt. I båda fallen raderas eventuella rabatter som användes på offertraden före simuleringen.  
17. Stäng sidan.
18. Klicka på Offert i åtgärdsfönstret.
19. Klicka på Skicka offert.
20. Välj Ja i fältet Skriv ut offert.
21. Klicka på OK.
    * Rapporten kan ta någon minut att skapa. Stäng inte sidan förrän den har skapats.  
22. Stäng sidan.

## <a name="update-a-sales-quotation"></a>Uppdatera en försäljningsoffert.
1. Klicka på Uppföljning i åtgärdsfönstret.
2. Klicka på Konvertera till kund.
3. Ange ett värde i fältet Kundkonto.
4. Klicka på Kontrollera.
    * Se till att det visas ett meddelande om att kontonumret du har angett är ledigt.  
5. Klicka på OK.
    * Systemet har nu skapat ett nytt kundkonto för den potentiella kunden i offerten.  
6. Stäng sidan.
7. Klicka på Uppföljning i åtgärdsfönstret.
8. Klicka på Bekräfta.
9. Ange eller välj ett värde i fältet Orsak.
10. Klicka på OK.
11. Klicka på Allmänt i åtgärdsfönstret.
12. Klicka på Försäljningsorder.
13. Stäng sidan.


