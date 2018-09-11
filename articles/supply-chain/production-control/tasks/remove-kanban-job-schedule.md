--- 
title: "Ta bort ett kanban-jobb från tidsplanen"
description: "Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9a0f246bfe42dde0befdf5c4f01d2ad1e1200b12
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Ta bort ett kanban-jobb från tidsplanen

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren.


## <a name="find-a-planned-kanban-job"></a>Sök efter ett planerat kanban-jobb
1. Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.
2. Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.
3. Klicka på länken på den valda raden i listan.
    * Välj arbetsgrupp 1250.  
4. Klicka på Välj.
5. Välj "Tidsplanerad" i fältet Visa jobbstatus.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Ta bort det planerade kanban-jobbet från tidsplanen
1. Hitta och markera önskad post i listan.
    * Välj ett jobb som har statusen Planerad, till exempel ett jobb från 19 december, 2012.  
2. Klicka på Plan i åtgärdsfönstret.
3. Klicka på Återställ jobbstatus.
4. Klicka på OK.
    * Då återställs den aktuella jobbstatusen från "Planerad" till "Inte planerad" och tas bort från processtavlan.   


