--- 
title: " Använd ett kontinuitetsprogram"
description: "Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: e94d9ded5cefc731e28af6898004419a00e0c189
ms.contentlocale: sv-se
ms.lasthandoff: 11/14/2017

---
# <a name="use-a-continuity-program"></a> Använd ett kontinuitetsprogram

[!include[task guide banner](../includes/task-guide-banner.md)]

Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar. För att slutföra denna procedur måste användaren konfigureras som en kundtjänstanvändare. I proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > Kunder > Kundtjänst.
2. I det fältet för söktext, ange "Karen" och tryck sedan på Tabb-tangenten.
    * Den avancerade sökningsdialogen bör dyka upp. Om den inte gör det, klicka då på Search till höger om fältet.  
3. Markera vald rad i listan.
    * Det bör bara finnas en rad som anger Karen Berg. Markera raden genom att klicka på kryssmarkeringskolumnen längst till höger på rutnätet.  
4. Klicka på Välj.
5. Klicka på Ny försäljningsorder.
    * Det är god bra idé att notera försäljningsorderns nummer. Du kommer att behöva det senare under denna procedur.  
6. I fältet för artikelnummer, ange "88000" och tryck sedan på Tabb-tangenten.
    * Detta är en kontinuitetsartikel i USRT-demonstrationsdatan.  
7. Klicka på Slutför.
8. I fältet för betalsätt anger du "Visa".
9. Klicka på Add credit card.
    * Ange den obligatoriska kreditkortsinformationen på denna sida.  
10. Klicka på OK.
11. Expandera avsnittet Betalning.
    * Om du vill skicka in en kundcenterorder måste betalningar anges för ordern.  
12. Klicka på OK.
13. Klicka på Skicka.
    * Du har nu skapat en ny kontinuitetsorder. Sedan ska du köra två batchprocesser som används för att processa kontinuitetsordrarna.  
14. Stäng sidan.
15. Gå till Retail and commerce > Continuity > Process continuity payments.
16. Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.
17. Klicka på OK.
18. Gå till Retail and commerce > Continuity > Create continuity child orders.
    * Denna process skapar nya försäljningsordrar som baseras på inställningarna för dina kontinuitetsprogram.  
19. Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.
    * Artikel "88000" är en kontinuitetsartikel i USRT-demonstrationsdatan.  
20. I fältet Sales order anger eller väljer du ett värde.
    * Ange försäljningsordernummer som du noterade tidigare i proceduren. Detta håller bearbetningstiden till ett minimum för denna procedur. Fältet för försäljningsorder valfritt ‒ du kan processa alla ordrar för valfritt program.  
21. Klicka på OK.


