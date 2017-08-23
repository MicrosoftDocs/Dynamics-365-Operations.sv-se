--- 
title: "Beräkna ränta"
description: "I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
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
ms.openlocfilehash: 8a53c4deb146d336fdd8ca88a081e6a5af71465a
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="process-interest"></a>Beräkna ränta

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


