---
title: Skapa och redigera försäljningsofferter
description: I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert.
author: omulvad
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2e9db489383d9c6ef05bc25d190d380b3150d311
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995014"
---
# <a name="create-and-edit-sales-quotations"></a>Skapa och redigera försäljningsofferter

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert. Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.


## <a name="create-a-sales-quotation"></a>Skapa en försäljningsoffert.
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsofferter > Alla offerter**.
2. Klicka på **Ny**.
3. I fältet **Kontotyp** väljer du "potentiell kund".
4. I fältet **potentiell kund** anger eller väljer du ett värde.
5. Expandera den **allmänna** delen. Eftersom du valde att skapa en offert från området Försäljning och marknadsföring ställs typen automatiskt in på Försäljningsoffert. Om du vill skapa en offert för ett projekt måste du öppna det från modulen **Projekthantering och redovisning**.
6. Klicka på **OK**. Fälten och åtgärder på offertraderna liknar de på försäljningsorderraderna.   På samma sätt som med försäljningsorder kan offerter skapas för en specifik artikel eller, när artikelnumret är okänt eller inte finns när offerten skapas, också kan offerter skapas för en försäljningskategori.     
7. I fältet **Objekt** eller välj ett värde.
8. Ange ett värde i fältet **Plats**.
9. Ange ett nummer i fältet **Kvantitet**. Om det finns giltiga handelsavtal för den markerade artikeln på raden, kommer tillhörande pris och rabatter automatiskt kopieras till offertraden. Kontrollera att enhetsprisfältet innehåller ett värde och du kan även ange rabattvärden, om du vill. 
10. Klicka på **Spara**.
11. I **åtgärdsrutan**, klicka på **försäljningsoffert**.
12. Klicka på **summor**.
13. Klicka på **OK**.
14. Välj försäljningsoffertraden
15. I **åtgärdsrutan**, klicka på **offerten**.
16. Klicka på **prissimulering**
    - I **Kör prissimulering** kan du experimentera med att justera förväntade inkomster eller lönsamheten för din offert utifrån önskat pris per enhet, rabattbelopp, rabatt i procent, totalt belopp, marginal, eller täckningsgrad. När du är nöjd med mål att tillämpa förslaget till offertraden och dess pris-relaterade fält uppdateras.  
    - Du kan skapa så många prissimuleringar som du vill ha. När du klickar på **Nytt**, kopieras prisvillkoren från den aktuella offertraden till sidan. Du kan sedan ändra värdena i någon av de prisrelaterade fälten till målfältet. En ändring i ett av fälten leder till omräkning av alla övriga fält. För att systemet ska kunna beräkna försäljningsmarginalen och täckningsgraden, måste produktens enhetskostnad vara känd. Använd fliken Simulerade priser för en detaljerad vy över de ursprungliga priserna, föreslagna ändringarna och deras inverkan på offertsummorna. Som en allmän regel räknar systemet om och anger ett nytt värde i fältet Enhetspris när en simulering som anger ett nytt belopp används på offertraden. Om simuleringen baseras på en ny marginal eller ny täckningsgrad, uppdateras bara nettobeloppsfältet, medan enhetspriset är tomt. I båda fallen raderas eventuella rabatter som användes på offertraden före simuleringen.
17. I **åtgärdsrutan**, klicka på **offerten**.
18. Klicka på **Skicka offertförfrågan**.
19. Välj Ja i listrutan **Skriv ut offert**.
20. Klicka på **OK**. Rapporten kan ta någon minut att skapa. Stäng inte sidan förrän den har skapats.

## <a name="update-a-sales-quotation"></a>Uppdatera en försäljningsoffert.
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsofferter > Alla offerter**.
2. I **åtgärdsrutan**, klicka på **uppföljning**.
3. Klicka på **Konvertera till kunden**.
4. I fältet **kundkonto** och ange ett värde.
5. Klicka på **Kontrollera**. Se till att det visas ett meddelande om att kontonumret du har angett är ledigt.  
6. Klicka på **OK**. Systemet har nu skapat ett nytt kundkonto för den potentiella kunden i offerten.  
7. Stäng sidan.
8. I **åtgärdsrutan**, klicka på **uppföljning**.
9. Klicka på **Bekräfta**.
10. Ange eller välj ett värde i fältet **Orsak**.
11. Klicka på **OK**.
12. I **åtgärdsrutan** klickar du på **Allmänt**.
13. Klicka på **Försäljningsorder**.
14. Stäng sidan.

