--- 
title: "Stänga räkenskapsåret"
description: "Denna procedur vägleder dig genom stegen i årsbokslutsprocessen som överför saldon till ett nytt räkenskapsår."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
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
ms.openlocfilehash: 83ea19e11596374c3e3ceb051db0b483f4b58583
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="close-the-fiscal-year"></a>Stänga räkenskapsåret

[!include[task guide banner](../../includes/task-guide-banner.md)]

Denna procedur vägleder dig genom stegen i årsbokslutsprocessen som överför saldon till ett nytt räkenskapsår.


## <a name="validate-year-end-close-parameters"></a>Validera årsbokslutsparametrar
1. Gå till Redovisning > Redovisningsinställning > Redovisningsparametrar.
2. Expandera avsnittet Fiscal year close.
3. Välj Yes eller No för alternativet Delete close-of-year transactions during transfer.
    * Om räkenskapsåret redan har stängts och årsbokslutet körs igen, är den här inställningen viktig. Om verifikationen är inställd på "Yes", kommer verifikationen för föregående årsbokslut att raderas och en ny verifikation skapas för alla konton som startar saldon. Om inställningen är "No" kommer föregående verifikation att bli kvar, och en ny kupong kommer endast att skapas för justeringar av poster som bokfördes efter det sista årsbokslutet.  
4. Välj Yes eller No för Create closing transactions during transfer.
    * Om inställningen är "Yes", skapas två transaktioner. En verifikation skapas i det räkenskapsår som stäng i syfte att sänka saldona för PL-huvudbokskontona till noll, och en andra verifikation skapas i nästkommande räkenskapsår för de nya saldona. Om inställt på "No" kommer en enda verifikation att skapas i nästa räkenskapsår för de nya saldona.  
5. Välj Yes eller No för statusen "Permanently closed" för Set fiscal year.
    * Om inställt på "Yes", kommer räkenskapsårsstatusen att ställas in som "Permanently closed".  Eftersom ett permanent stängt år inte kan öppnas på nytt, är det bäst att ange detta alternativ som "No".  
6. Välj Yes eller No för huruvida ett verifikationsnummer måste fyllas i under årsbokslutet.
    * Om inställt på "Yes" måste ett verifikationsnummer anges manuellt under processen för årsbokslutet. En nummerserie används inte för att generera detta verifikationsnummer. Det bästa är att ange detta som "Yes".  
7. Stäng sidan.
8. Gå till Redovisning > Periodstängning > Årsbokslut.
9. Klicka på New för att skapa en årsbokslutsmall.
    * En mall kan skapas för en grupp juridiska personer för vilka du vill köra årsbokslutet. Denna mall kan återanvändas året efter år.  
10. Ange ett mallnamn för årsbokslut i fältet Group name.
11. Välj det räkenskapsår som mallen ska skapas för.
    * Endast juridiska personer som använder samma räkenskapsår kan grupperas tillsammans mallen för årsbokslut. Detta eftersom årsbokslutet görs genom att välja ett räkenskapsår, inte ett datum.  
12. Använd genvägen för att spara en post.
13. Klicka på Add to för att välja de juridiska personerna för den här mallen.
    * Juridiska personer kan läggas till, antingen genom att välja de juridiska personerna eller genom att välja en organisationshierarki.  Endast juridiska personer med en organisationshierarki med samma markerade räkenskapskalender läggs till.  
14. Välj antingen de juridiska personerna eller organisationshierarkin.
15. Klicka på OK.
16. Välj om de ekonomiska dimensionerna ska överföras till nästa räkenskapsår.
    * Det bästa är att ange detta akternativ som "Yes" för balansräkningskonton.  Detta kommer att bibehålla de ekonomiska dimensionerna i bokförda transaktioner när nya saldon ska skapas för balansräkningskontona.  För vinst - och förlustkonton kan du välja att underhålla stäng ekonomiska dimensioner (Close all) när saldona flyttas till balanserade vinstmedel, eller också kan du välja att byta ut de ekonomiska dimensionerna med ett annat dimensionsvärde (Close single). Om du väljer Close single kan du definiera ett specifikt dimensionsvärde för varje dimension, eller till och med välja att lämna den tom.  
17. Klicka på Spara.
18. Starta årsbokslutet genom att välja Kör årsbokslut i åtgärdsfönstret.
    * Årsbokslutet körs för den valda mallen.  
19. Välj alla eller en underuppsättning juridiska personer från den mall för vilken du vill köra årsbokslutet.
    * När årsbokslutet först körs, kan de flesta organisationer välja att köra årsbokslutet för samtliga juridiska personer i mallen i syfte att skapa ingående saldon. Om postjusteringar utförs efter det, kan du välja att köra årsbokslutet för enbart de juridiska personerna som har justeringar.  
20. Klicka på OK.
21. Markera det räkenskapsår du vill köra årsbokslutet för.
22. Ange ett värde i fältet Voucher.
    * Det bästa är att inkludera räkenskapsåret i verifikationsnummer, detta för att göra det enklare att hitta verifikationen för årsbokslutet som skapas.  
23. Årsbokslutets standardvärden som ska köras i batch.
    * Det bästa är att låta långvariga processer köras i batch-läge. Detta är vanligtvis en av dessa processer, vilket är orsaken till att standardinställningen är att använda batch-läge.  
24. Klicka på OK.


