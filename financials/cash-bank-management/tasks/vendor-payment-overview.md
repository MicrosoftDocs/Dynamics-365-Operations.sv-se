--- 
title: "Översikt över leverantörsbetalning"
description: "Den här uppgiftsguiden går igenom vilka olika metoder som används för att skapa leverantörsbetalningar, till exempel hur du använder ett betalningsförslag eller manuellt anger en enstaka betalning."
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 44b7c02e7c238dcea83c5900620731a7befbbb42
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="vendor-payment-overview"></a>Översikt över leverantörsbetalning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden går igenom vilka olika metoder som används för att skapa leverantörsbetalningar, till exempel hur du använder ett betalningsförslag eller manuellt anger en enstaka betalning. I den här proceduren används demonstrationsföretaget USMF.

1. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Välj den betalningsjournal där du kan spara leverantörsbetalningarna. 
4. Välj journalen eller ange den manuellt.
5. Klicka på Rader.
6. Klicka på Betalningsförslag.
7. Klicka på Skapa betalningsförslag.
    * Betalningsförslaget är en fråga som används för att välja fakturor för betalning. Du kan redigera listan över vilka fakturor som ska betalas innan du skapar eller genererar leverantörsbetalningarna.  
8. Välj fakturor för betalning efter förfallodatum, kassarabatt eller både och. 
9. Ange datumet för att jämföra med förfallodatumet eller kassarabatten. 
10. Du kan även: Ange ett betalningsdatum som används för alla betalningar.
    * Det datum som anges här ska vara betalningsdatum för alla betalningar som skapas, oavsett förfallodatum- eller kassarabattdatum.  
11. Valfritt: Ange ett tidigaste betalningsdatum som kan användas som betalningsdatum.
    * Tidigaste betalningsdatumet är det tidigaste datum som användes när du skapade betalningar. Om en faktura till exempel har ett tidigaste betalningsdatum, kommer betalningsdatumet att vara betalningsdatumet i stället för det tidigaste betalningsdatumet för att fakturan ska betalas vid det senaste möjliga datumet.  
12. Ange ytterligare frågebegränsningar under Poster som ska ingå.
    * Filtret används ofta för att begränsa de fakturor som har valts för betalning per leverantörsgrupp eller betalningsmetod. Du kan till exempel lägga till ett filter att endast betala fakturor med check i den här lönekörningen.  
13. Ange ytterligare standardvärden för frågebegränsning eller betalning. 
    * De ytterligare parametrarna kan användas för att definiera betalningsvalutan eller aktivera centraliserade betalningar för den här lönekörningen.  
14. Klicka på OK.
    * När du har klickat på OK kommer resultaten av frågan att visas. Om du inte vill granska listan med markerade fakturor som ska betalas kan du gå tillbaka till du snabbfliken Parametrar och ändra inställningen Skapa betalningar utan att förhandsgranska fakturor = Ja.  
15. Välj Visa betalningsöversikt om du vill visa de betalningar som ska skapas för leverantören på den valda fakturan.
16. Välj Dölj betalningsöversikt om du vill dölja betalningarna. 
17. Klicka på Skapa betalningar.
    * Innan du väljer Skapa betalningar kan du högerklicka på rutnätet och exportera listan med fakturor till Excel. Med knappen Skapa betalningar skapas leverantörsbetalningarna i betalningsjournalen.  
18. Skanna dina betalningar och kontrollera att betalningsmetoden har definierats för alla betalningar. 
    * Om du vill generera betalningarna, till exempel skriva ut en check eller skapa en elektronisk betalning måste betalningsmetoden definieras. Betalningsmetoden avgör också vilket bankkonto som betalningen ska göras från som standard.  
19. Klicka på Ny för att skapa en enstaka betalning.
    * En enstaka betalning kan läggas till i en betalningsjournal när som helst före bokföring. Detta görs genom att klicka på knappen Ny och att lägga till betalningsinformationen manuellt snarare än att använda betalningsförslaget.  
20. Välj den leverantör som betalningen ska ske till.
21. Om det finns en faktura som ska betalas, väljer du Kvitta transaktioner för att välja fakturan för betalning.
    * Om det är en förskottsbetalning är detta steg valfritt. Du kan skapa betalningen utan att välja någon faktura.  
22. Markera alla fakturor som ska betalas.
    * Om du använder Kvitta transaktioner för att välja fakturor för betalning beräknas betalningsbeloppet automatiskt baserat på vilka fakturor du markerar för betalning och vilket belopp du anger i Belopp att kvitta.  
23. Klicka på OK.
24. Markera raden om du vill ta bort en betalning.
25. Klicka på Ta bort.
    * Om du tar bort en betalning tas endast betalningen bort. Alla fakturor som markeras för betalning är fortfarande tillgängliga för att betalas av en annan betalning.  
26. Klicka på Ja.
27. Välj Generera betalning för att skriva ut checkar eller skapa den elektroniska betalningsfilen.
28. Välj den betalningsmetod som du vill generera.
    * Betalningsjournalen kan innehålla betalningar för båda checkar och elektroniska betalningar, men du kan bara generera en betalningstyp i taget.  
29. Välj bankkontot från vilket du vill generera betalningarna.
30. Klicka på OK.
    * Betalningar genereras endast för betalningar som matchar betalningsmetoden och det bankkonto som du har valt.  
31. Om du genererar checkar väljer du Dokument för att säkerställa korrekt utskriftsmål för checkarna.
32. Klicka på OK.
33. Klicka på OK för att generera betalningarna.
34. Klicka på Bokför om alla betalningar har godkänts och genererats. 


