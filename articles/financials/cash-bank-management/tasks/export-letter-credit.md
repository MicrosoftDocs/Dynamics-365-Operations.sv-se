--- 
title: Exportera en remburs
description: "I den här proceduren förklaras processen för exportremburs."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0fa4b57825bcf81778d91ee01484511bb40f6bd7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="export-a-letter-of-credit"></a>Exportera en remburs

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren förklaras processen för exportremburs.

En remburs är ett avtal som har utfärdats av en bank, i vilket banken går med på att säkerställa betalningen på uppdrag av köparen om villkoren i avtalet mellan köparen och säljaren uppfylls.



Kör procedurerna Ställ in bankkreditlimiter och bokföringsprofiler, och Remburs_Skapa ett kreditlimitavtal före den här proceduren. USMF-demonstrationsföretaget måste väljas för att utföra den här proceduren.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Skapa en försäljningsorder för exportremburs
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Utöka eller komprimera avsnittet Allmänt.
7. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
    * Välj platsen där artikeln som ska utlevereras lagras.  
8. Klicka på länken på den valda raden i listan.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
    * Välj det lagerställe där artikeln som ska utlevereras lagras.  
10. Klicka på länken på den valda raden i listan.
    * Obs! Fältet Bankdokumenttyp bör väljas med värdet Remburs.  
11. Välj Remburs i fältet Bankdokumenttyp.
12. Utöka eller komprimera avsnittet Leverans.
    * Välj Leveransdatumkontroll = Ingen.  
13. I fältet Begärt inleveransdatum, ange ett datum.
14. Klicka på OK.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
    * Välj den begärda artikeln som ska utlevereras/säljas.  
16. Hitta och markera önskad post i listan.
17. Klicka på länken på den valda raden i listan.
18. Ange ett tal i fältet Enhetspris.
19. Expandera eller dölj avsnittet Raddetaljer.
20. Klicka på fliken Leverans.
21. I fältet Begärt transportdatum, ange ett datum.
22. I fältet Bekräftat transportdatum, ange ett datum.
23. Klicka på Hantera i åtgärdsfönstret.
24. Klicka på Remburs.
25. Skriv ett värde i fältet Bankdokumentnummer.
26. I fältet Utgångsdatum anger du datum och tid.
27. Expandera eller dölj avsnittet Bankdetaljer.
28. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utfärdande bank.
29. Klicka på länken på den valda raden i listan.
30. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Aviserande bank.
31. Hitta och markera önskad post i listan.
32. Klicka på länken på den valda raden i listan.
33. Klicka på Hämta försäljningsorderförsändelser.
34. Klicka på Utfärda bankdokument.
35. Stäng sidan.

## <a name="post-packing-slip"></a>Bokför följesedel
1. Klicka på Plocka och packa i åtgärdsfönstret.
2. Klicka på Bokför följesedel.
3. Utöka eller komprimera avsnittet Parametrar.
4. Välj "Alla" i fältet Kvantitet.
5. Utöka eller komprimera avsnittet Inställningar.
6. I fältet Följesedel, ange ett datum.
7. Välj försändelsenumret.
8. Klicka på länken på den valda raden i listan.
9. Klicka på OK.
10. Klicka på OK.

## <a name="post-sales-invoice"></a>Bokför försäljningsfaktura
1. Klicka på Faktura i åtgärdsfönstret.
2. Klicka på Faktura.
3. Utöka eller komprimera avsnittet Översikt.
4. Välj försändelsenumret.
5. Klicka på länken på den valda raden i listan.
6. Utöka eller komprimera avsnittet Inställningar.
7. Ange ett datum i fältet Fakturadatum.
8. Klicka på OK.
9. Klicka på OK.

## <a name="shipment-document-submitted-status"></a>Status för skickade försändelsedokument
1. Klicka på Hantera i åtgärdsfönstret.
2. Klicka på Remburs.
3. Utöka eller komprimera avsnittet Rader.
    * Obs! Fältet Dokument som skickas måste vara inställt på Ja.  

## <a name="verify-export-letter-of-credit"></a>Verifiera exportremburs
1. Gå till Kassa- och bankhantering > Remburser > Exportremburs och importinkasso.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Kontrollera att exportrembursen har försändelsestatusen Fakturerad.  

## <a name="customer-payment"></a>Kundbetalning
1. Gå till Kundreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
5. Klicka på länken på den valda raden i listan.
6. Klicka på Rader.
7. Ange ett datum i fältet Datum.
8. Ange önskade värden i fältet Konto.
9. Klicka på Kvittning.
10. Markera kryssrutan i rubriken för Summor.
    * Obs! Ställ in fältet Visa till Remburs.  
11. Hitta och markera önskad post i listan.
12. Markera eller avmarkera kryssrutan Markera.
13. Klicka på OK.
14. Klicka på fliken Betalning.
    * Kontrollera informationen om bankdokumentnumret och försändelsenumret  
15. Klicka på Bokför.

## <a name="verify-export-letter-of-credit-after-payment"></a>Verifiera exportremburs efter betalning
1. Gå till Kassa- och bankhantering > Remburser > Exportremburs och importinkasso.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Kontrollera att Försändelsens status = Betalning mottagen och att Saldobelopp = 0,00.  


