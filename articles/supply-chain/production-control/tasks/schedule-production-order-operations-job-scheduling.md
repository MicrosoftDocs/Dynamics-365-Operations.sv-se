---
title: Tidsplanera en produktionsorder med operationer och jobbplanering
description: Det här avsnittet fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.
author: ChristianRytt
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3023d6a6fe09c84b47839a2c4b78c37907754ded
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914894"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Tidsplanera en produktionsorder med operationer och jobbplanering

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det här avsnittet fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering. Inga jobb skapas med grovplanering medan jobb skapas med finplanering. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.


## <a name="create-a-production-order"></a>Skapa en produktionsorder
1. I Navigeringsfönster, gå till **Moduler > Produktionskontroll > Produktionsorder > Alla produktionsorder**.
2. Välj **Ny produktionsorder**.
3. I fältet **artikelnummer** anger du eller väljer ett värde. Välj artikelnummer **D0001**.  
4. Markera **Skapa**.

## <a name="schedule-operations-for-the-production-order"></a>Tidsplanera åtgärder för produktionsordern.
1. Markera den nyss skapade raden.      
2. I åtgärdsfönstret, välj **Tidsplan**.
3. Välj **Tidsplanera operationer**.
4. Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.
5. Ange ett datum i fältet **Planeringsdatum**. Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
6. Välj **OK**.
7. Markera vald rad i listan. Observera att statusen ändras till **Tidsplanerad**. 
8. Välj **Alla jobb**. Observera att inga jobb skapas med grovplanering.  
9. Stäng sidan.

## <a name="schedule-jobs-for-the-production-order"></a>Tidsplanera jobben för produktionsordern
1. I åtgärdsfönstret, välj **Tidsplan**.
2. Välj **Tidsplanera jobb**.
3. Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.
4. Ange ett datum i fältet **Planeringsdatum**. Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
5. Välj **OK**.
6. Välj **Produktionsorder** i åtgärdsfönstret.
7. Välj **Alla jobb**. Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.  

