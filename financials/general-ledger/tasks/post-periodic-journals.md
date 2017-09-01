--- 
title: "Bokför periodiska journaler"
description: "Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas."
author: aprilolson
manager: AnnBe
ms.date: 02/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b1b1b857428ca1ee36496f82c79a17eb157c8dd8
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="post-periodic-journals"></a>Bokför periodiska journaler

[!include[task guide banner](../../includes/task-guide-banner.md)]

Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas. När du skapar och bokför en periodisk journal anger du periodintervallet för upprepningen, till exempel dagar eller månader. I den här uppgiftsguiden skapas en periodisk journal med månadsvis upprepningar.



1. Gå till Redovisning > Periodiska uppgifter > Periodiska journaler.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
4. Klicka på länken på den valda raden i listan.
5. Ange ett värde i fältet Beskrivning.
    * Beskrivningen är namnet på den periodiska journalen när den hämtas senare, så se till att ge den ett relevant namn.  
6. Klicka på Rader.
    * En periodisk journal vanligtvis kommer att innehålla flera journalrader. Men i den här uppgiftguiden ska vi bara lägga till en rad.  
7. Ange ett datum i fältet Datum.
    * Fältet Datum innehåller bokföringsdatumet för nästa överföring till den dagliga journalen. För journaler som ska hämtas varje månad rekommenderas du att använda datumet i månaden när de bokförs, vanligen det första eller sista datumet i perioden. Det går att lämna datumfältet tomt och ange ett datum när journalen hämtas, med det tomma datumfältet.    Fältet uppdateras automatiskt till nästa återkommande datum då transaktioner hämtas.  
8. Ange önskade värden i fältet Konto.
9. Ange ett värde i fältet Beskrivning.
10. Stäng sidan.
11. Ange ett tal i fältet Debet.
12. Ange önskade värden i fältet Motkonto.
13. Välj "Månader" i fältet Enhet.
14. Ange "1" i fältet Antal enheter.
15. Ange ett datum i fältet för senaste datum.
    * Om du anger det senaste datumet i den föregående perioden förhindras den återkommande journalen att skapas av misstag i fel startperiod. Senaste datum kommer att uppdateras senare, varje gång den periodiska journalen hämtas.  
16. Klicka på Spara.
17. Gå till standardinstrumentpanelen.
18. Gå till Redovisning > Journalposter > Allmänna journaler.
19. Klicka på Ny.
20. Ange eller välj ett värde i fältet Namn.
21. Hitta och markera önskad post i listan.
22. Klicka på länken på den valda raden i listan.
23. Ange ett värde i fältet Beskrivning.
24. Klicka på Rader.
25. Klicka på Periodjournal.
26. Klicka på Hämta journal.
27. Ange ett datum i fältet Till datum.
    * Till-datumet fungerar som brytdatum för de periodiska verifikationsraderna. Baserat på återkommandeinställningen kan senaste datum och till-datum på samma rad inkluderas mer än en gång i den resulterande journalen. Till-datum uppdateras automatiskt på grundval av sessiondatumet för den senaste gången den periodiska raden överfördes till en journal.  
28. Ange eller välj ett värde i fältet Periodisk journal.
29. Klicka på länken på den valda raden i listan.
30. Klicka på OK.
    * Periodjournalen kan nu granskas, godkännas eller bokföras beroende på inställningar och krav.  

