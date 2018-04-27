--- 
title: "Ställ in efterdaterade checkar"
description: "I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar."
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
ms.openlocfilehash: d83713f9d54b396a10894995024ac1c8dd47a6f1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-postdated-checks"></a>Ställ in efterdaterade checkar

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar. Du kan även ange clearingkonton för Betalda checkar, Mottagna checkar och källskatt. Efterdaterade checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Du kan ange om checken ska återspeglas i dina redovisningsböcker före dess förfallodag.



Rollen för den här proceduren är Kassaförvaltare. I den här proceduren används demonstrationsföretaget USMF.


## <a name="set-up-postdated-checks"></a>Ställ in efterdaterade checkar
1. Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.
2. Klicka på fliken Efterdaterade checkar.
3. Markera eller avmarkera kryssrutan Aktivera efterdaterade checkar.
4. Markera eller avmarkera kryssrutan Bokför journalposter för efterdaterade checkar.
5. I fältet Clearingkonto för utfärdade checkar, ange de önskade värdena.
6. I fältet Clearingkonto för mottagna checkar, ange de önskade värdena.
7. I fältet Allmän journal för clearingposter, skriv ett värde.
8. I fältet Överför efterdaterade checkar till den här leverantörsbetalningsjournalen, skriv ett värde.
9. I fältet Clearingkonto för källskattebelopp, ange de önskade värdena.
10. Klicka på Spara.
11. Stäng sidan.
12. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.
13. Klicka på Ny.
14. Skriv ett värde i fältet Betalningsmetod.
15. Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.
16. Välj "Bank" i fältet Kontotyp.
    * Motkontot för betalningsmetoden kommer att vara en bank.  
17. I fältet Betalningskonto, ange önskade värden.
    * Välj det bankkonto som används för att dra av fakturabeloppet.  
18. Stäng sidan.
19. Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder
20. Klicka på Ny.
21. Skriv ett värde i fältet Betalningsmetod.
22. Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.
23. Välj "Bank" i fältet Kontotyp.
    * Motkontot för betalningsmetoden kommer att vara en bank.  
24. I fältet Betalningskonto, ange önskade värden.
    * Välj det bankkonto som används för att dra av fakturabeloppet.  
25. Stäng sidan.


