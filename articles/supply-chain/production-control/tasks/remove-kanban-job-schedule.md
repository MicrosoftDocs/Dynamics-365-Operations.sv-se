---
title: Ta bort ett kanban-jobb från tidsplanen
description: Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3e9a512e7f391e08a35fd0eea449af12d81e644
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828596"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]