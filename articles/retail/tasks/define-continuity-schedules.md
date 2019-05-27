---
title: " Definiera kontinuitetstidsplaner"
description: I detta avsnitt beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd70780927bb9aaa19c196705d6e8fa1c247ea66
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559242"
---
# <a name="define-continuity-schedules"></a> Definiera kontinuitetstidsplaner

[!include[task guide banner](../includes/task-guide-banner.md)]

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

