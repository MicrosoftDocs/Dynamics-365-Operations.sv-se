--- 
title: Bearbeta kravbrev
description: "I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, SysQueryForm, CustCollectionLetterNote
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a>Bearbeta kravbrev

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev. I den här uppgiften används demonstrationsföretaget USMF.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Ställ in en kravbrevsserie för bokföringsprofilen
1. Gå till Kredit och inkasso > Inställningar > Kundbokföringsprofiler.
2. Klicka på Redigera.
    * Välj en kravbrevssekvens i listrutan. Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.  
    * Registerbegränsningsfliken gör det möjligt att ändra hur kravbrev bearbetas. Om detta fält har satts till Ja, kravbrev skapas för denna bokföringsprofil.  
3. Stäng sidan.

## <a name="create-collection-letters"></a>Skapa kravbrev
1. Gå till Kredit och inkasso > Kravbrev > Skapa kravbrev.
    * Du måste välja transaktionstyperna för kravbrev. Alla öppna transaktioner för dessa typer inkluderas i beräkningen.  
2. Välj ett alternativ i fältet Collection letter.
3. Ange datumet för det aktuella kravbrevet.
    * Det finns två bokföringsprofilalternativ: Konto – använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.   Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.  
    * Välj en bokföringsprofil om du har ändrat Använd bokföringsprofil från till Välj.  
4. Expandera avsnittet Poster som ska ingå.
5. Klicka på Filter.
6. I fältet Kriterier, ange ett kund ID i kriteriefältet. Till exempel US-001.
7. Klicka på OK.
8. Klicka på OK.

## <a name="print-collection-letters"></a>Skriv ut kravbrev
1. Gå till Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev.
2. Välj Skapad i fältet Status.
3. Välj Ej utskrivet i fältet Utskriven.
4. Klicka på Skriv ut.
5. Klicka på kravbrevsnotering.
6. Expandera avsnittet Poster som ska ingå.
7. Ange slutdatumet för bokföringar
8. Klicka på OK för att skriva ut kravbrevet.

## <a name="post-the-collection-letter"></a>Bokför kravbrevet
1. Klicka på Bokför.
2. Ange bokföringsdatumet för kravbrevet.
3. Expandera avsnittet Poster som ska ingå.
4. Klicka på OK.
5. Välj Bokförd i fältet Status.
6. Välj ett alternativ i fältet Utskriven.


