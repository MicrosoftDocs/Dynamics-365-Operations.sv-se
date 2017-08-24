--- 
title: "Upprätta avgifter för kundbetalning"
description: "Skapa betalningsavgifter för kundbetalningar."
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 220b33fe81a63aad83bc045ca4a7c74971e7c7bd
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-payment-fees"></a>Upprätta avgifter för kundbetalning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Skapa betalningsavgifter för kundbetalningar.

I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Kundreskontra > Betalningsinställning > Betalningsavgift.
2. Klicka på Ny.
3. Ange ID i fältet Avgifts-ID.
    * Avgifts-ID visas i betalningsjournaler, vilket gör det beskrivande så att du förstår vilken avgiften som åläggs.  
4. Ange namn i fältet Namn.
5. Ange en beskrivning av avgiften i fältet Beskrivning.
6. Välj om tillägget ska debiteras kunden eller ett huvudbokskonto.
    * Välj Kund om kunden ska debiteras avgiften. Om avgiften ska åläggas din organisation som en utgift, välj redovisning. Markera kunden för denna uppgift.  
7. Välj typ av journal som kan använda denna betalningsavgift.
    * Om dessa tillägg används för kundbetalningar, kommer journaltypen troligen vara kundbetalning.  
8. Klicka på Spara.
9. Klicka på Betalningsavgiftsinställning.
    * Betalningsavgiftinställningar används för att definiera villkoren för betalningsavgiften, när ska bedömas.  Du kan till exempel definiera som avgiften beräknas, om företaget är USMF OPER, och betalningsmetoden är check.  
10. Välj Register, Grupp eller Alla när du vill definiera vilka bankkonton ska bedömas den avgiften.
    * Om du väljer Alla, kan alla bankkonton åläggas avgiften.  Om du väljer Register, kan bara det bankkonto som du valt åläggas avgiften. Om du väljer Grupp, kan bara bankkontona i den markerade bankgruppen åläggas avgiften.  
11. Välj antingen en bankgrupp eller ett bankkonto.
    * Om du väljer Register, visar sökningen bankkonton. Om du väljer Grupp, visar sökningen bankgrupper.  
12. Klicka på länken på den valda raden i listan.
13. Välj en betalningsmetod som ska användas för åläggandet av den aktuella betalningsavgiften.
    * Du kan till exempel ålägga en avgift till kunden om de skickar betalningar som en check, snarare än som en elektronisk betalning.  
14. Hitta och markera önskad post i listan.
15. Ange en betalningsvaluta, om det behövs.
    * Betalningvalutan används som villkor för om avgift ska åläggas.  Anta att din bank läsa in en ytterligare avgift för betalningar som tas emot i USD, eftersom de normalt bara arbetar med EUR-valuta.  
16. Välj om tillägget ska vara procent, ett belopp eller ett intervall.
17. Ange antingen procentandelen eller beloppet av avgiften.
    * Om procentsatsen/beloppsfält är procentvärde anges värdet som en procentsats. Om procentsatsen/beloppsfält är belopp, anges värdet som en procentsats. Om procentsatsen/beloppsfält är intervall, ska du använda intervallfliken för att definiera nivåerna.  
18. Välj valuta för tillägget i avgiftvalutafältet.
    * Detta är den valuta som avgiften ska skapas i.  
19. Klicka på Spara.


