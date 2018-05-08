--- 
title: " Definiera kontinuitetstidsplaner"
description: "I detta avsnitt beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order)."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5ac333989dd987fd3cb1d2b2769fbcdb93bdb4bd
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="define-continuity-schedules"></a> Definiera kontinuitetstidsplaner

[!include [task guide banner](../includes/task-guide-banner.md)]

I detta avsnitt beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order). Detta ämne använder företaget USRT för demonstrationsdatan.


## <a name="create-continuity-program"></a>Skapa ett kontinuitetsprogram
1. Gå till Retail and commerce > Continuity > Continuity programs.
2. Klicka på Ny.
3. Ange ID för kontinuitetstidsplan i fältet Schedule ID.
4. I fältet Order start väljer du "First event".
    * Om en kund lägger en ny order för kontinuitetsprogrammet finns det två alternativ för vilken produkten levereras: 1. Första händelse: den första produkten i kontinuitetsprogrammet ska levereras.  2. Aktuell händelse: den aktuella produkten skickas. Till exempel: tre månader efter programmets början får kunden den tredje i programmet.  
5. Välj ”Yes” om du vill efterfråga orderstartdatumet.
6. Klicka på Lägg till rad.
7. I fältet Item number anger du artikelnumret för den första produkten ("0013").
8. Ange "CP".
9. Ange det datum då den första produkten finns tillgänglig för order.
10. Klicka på Lägg till rad.
11. Skriv 0014 i fältet Artikelnummer.
12. I fältet för datumintervallskod rensar du värdet så att fältet står tomt.
    * Rensa datumintervallet för denna procedur. Du anger datumet som inkrementellt från startdatum för den första artikeln.  
13. Här kan du ange det intervallet då produkterna skickas. Ange "30".
    * För att ett månatligt program ska du ange 30 dagar för intervallet.  
14. Klicka på Lägg till rad.
15. Skriv 0015 i fältet Artikelnummer.
16. Ange "End".
17. Klicka på Spara.

## <a name="assign-to-continuity-item"></a>Tilldela till en kontinuitetsartikel
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Välj artikel "0016".
    * För den här proceduren väljer du artikel nummer 0016. Normalt har du skapat en frisläppt produkt som har ytterligare tillämpad kontinuitetsaffärslogik när den läggs på en försäljningsorder hos kundtjänsten.  
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Expandera eller komprimera sälja avsnitt.
6. Här kan du ange det kontinuitetsprogram som denna artikel representerar. Ange det tidsplans-ID som du skapade tidigare.
    * När artikeln säljs hos en kundtjänst tillämpas affärslogik från det valda kontinuitetsprogrammet.  
7. Klicka på Spara.


