---
title: Tidsplanera en produktionsorder med operationer och jobbplanering
description: Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.sourcegitcommit: 2ebea3cbddfa0a5ef0e0fd13d3693da6152bc288
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2019
ms.locfileid: "352469"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Tidsplanera en produktionsorder med operationer och jobbplanering

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering. Inga jobb skapas med grovplanering medan jobb skapas med finplanering. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.


## <a name="create-a-production-order"></a>Skapa en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
2. Klicka på Ny produktionsorder.
3. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj artikelnummer D0001.  
4. Klicka på Skapa.

## <a name="schedule-operations-for-the-production-order"></a>Tidsplanera åtgärder för produktionsordern.
1. Markera vald rad i listan.
    * Välj den tillverkningsorder som du just har skapat. Den bör vara överst i listan.      
2. Klicka på Tidsplanera i åtgärdsfönstret.
3. Klicka på Tidsplanera operationer.
4. Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.
5. Ange ett datum i fältet Planeringsdatum.
    * Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
6. Klicka på OK.
7. Markera vald rad i listan.
    * Observera att statusen ändras till Tidsplanerad.  
8. Klicka på länken på den valda raden i listan.
9. Klicka på Alla jobb.
    * Observera att inga jobb skapas med grovplanering.  
10. Stäng sidan.

## <a name="schedule-jobs-for-the-production-order"></a>Tidsplanera jobben för produktionsordern
1. Klicka på Tidsplanera i åtgärdsfönstret.
2. Klicka på Tidsplanera jobb.
3. Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.
4. Ange ett datum i fältet Planeringsdatum.
    * Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
5. Klicka på OK.
6. Klicka på Produktionsorder i åtgärdsfönstret.
7. Klicka på Alla jobb.
    * Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.  

