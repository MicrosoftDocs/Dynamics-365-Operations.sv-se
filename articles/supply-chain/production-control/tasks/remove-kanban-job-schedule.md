---
title: Ta bort ett kanban-jobb från tidsplanen
description: Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0236faa9b534678ed232ac3572c8172c62e5241f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437363"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Ta bort ett kanban-jobb från tidsplanen

[!include [banner](../../includes/banner.md)]

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

