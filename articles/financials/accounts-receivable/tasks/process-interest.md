---
title: Beräkna ränta
description: I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5652a38684061914f895d7f8b82999c9840fd63
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "359162"
---
# <a name="process-interest"></a>Beräkna ränta

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor. I den här uppgiften används demonstrationsföretaget USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Ställ in ränta i bokföringsprofilen
1. Gå till Kredit och inkasso > Inställningar > Kundbokföringsprofiler.
2. Klicka på Redigera.
    * Välj en räntekod i listrutan. Om du inte vill skapa beräkna ränta för transaktioner med denna bokföringsprofil, lämna fältet tomt.  
    * Registerbegränsningsfliken gör det möjligt att ändra hur ränta bearbetas. Om detta fält har satts till Ja, beräknas ränta för denna bokföringsprofil.  

## <a name="calculate-interest"></a>Beräkna ränta
1. Gå till Kredit och inkasso > Ränta > Skapa räntefakturor.
    * Du måste välja transaktionstyperna för att beräkna ränta. Alla öppna transaktioner för dessa typer inkluderas i beräkningen.  
    * Om du väljer ränta, ska du beräkna ränta på ränta. Du kanske du vill kontrollera lagar som styr beräkningen av ränta på ränta som inkluderar för dessa transaktioner.  
    * Ränta beräknas utifrån detta datum i ”till”. Om du inte bort specifikt ”från-datum”, annulleras alla bokförda räntefakturor och ränta beräknas på nytt från transaktionsdatum.  
2. Ange datum för räntefakturan.
    * Det finns tre bokföringsprofilalternativ: Konto – använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.   Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.   Transaktion – Använd bokföringsprofilen från den transaktioner där ränta beräknas för varje räntefaktura. Transaktioner som inte har en tilldelad bokföringsprofil kommer använda bokföringsprofilen som angetts i området Redovisning och moms i formuläret Parametrar för kundreskontra.  
    * Välj en bokföringsprofil om du har ändrat Använd bokföringsprofil från till Välj.  
3. Utöka eller komprimera avsnittet Poster som ska ingå.
4. Klicka på Filter.
5. Ange Kund-ID i fältet Kriterier. Till exempel US-001.
6. Klicka på OK.
7. Klicka på OK.

## <a name="print-interest-notes"></a>Skriv ut räntefakturor
1. Gå till Kredit och inkasso > Ränta > Granska och beräkna räntefakturor.
2. Välj Skapad i fältet Status.
3. Välj Ej utskrivet i fältet Utskriven.
4. Klicka på Skriv ut.
5. Utöka eller komprimera avsnittet Poster som ska ingå.
6. Klicka på OK.
7. Stäng sidan.

## <a name="post-the-interest-note"></a>Bokför räntefakturan
1. Välj en räntefakktura som är klar att bokföra (status skapas).
2. Klicka på Bokför.
3. Ange bokföringsdatumet för räntefakturan.
    * Välj Ja för att skapa en redovisningstransaktion för varje räntefaktura.     Om du inte mväljer Ja ackumuleras räntan på alla räntefakturor till kunden och bokförs i redovisningen i en enda transaktion.  
4. Utöka eller komprimera avsnittet Poster som ska ingå.
5. Klicka på OK.
6. Välj Bokförd i fältet Status.

