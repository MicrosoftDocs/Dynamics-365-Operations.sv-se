--- 
title: Flytta tidsplanerade kanban-jobb
description: "Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5f101a097643fa027a667b9d6577fbe5d24ecd27
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Flytta tidsplanerade kanban-jobb

[!include[task guide banner](../../includes/task-guide-banner.md)]

Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren som arbetar med kanbans.


## <a name="select-scheduled-kanban-jobs"></a>Välj tidsplanerade kanban-jobb
1. Gå till Produktionsstyring > Kanban > Tidsplanering av kanban-jobb.
2. !MtCMR!Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp. áçêìõý!
3. På för række för Markér hålavalgte lyssnar.
    * Välj arbetsgrupp 1250.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Jobblistan filtreras så att endast de tidsplanerade kanban-jobben visas.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Flytta kanban-jobb till en annan period.
1. Find og vælg den ønskede post på listen.
    * Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 20 december 2012 i fältet Planerad period. Flytta sedan jobbet till föregående period.  
2. Klik på Previous period.
3. Klik på End.
    * Jobbet flyttas till slutet av jobblistan som det sista jobbet i föregående period.  
4. Find og vælg den ønskede post på listen.
    * Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 18 december 2012 i fältet Planerad period. Flytta sedan jobbet till nästa period.  
5. Klik på Next period.
6. Klik på Start.
    * Jobbet flyttas till början av jobblistan som det sista första jobbet i föregående period.  

## <a name="task-move-a-job-within-a-period"></a>Uppgift: Flytta ett jobb inom en period
1. Find og vælg den ønskede post på listen.
    * Markera ett jobb som har statusen Planerat jobb, till exempel det andra jobbet som har tidsplanerats den 19 december 2012 i fältet Planerad period. Flytta sedan jobbet inom den planerade perioden.  
2. Klik på Forward.
    * Observera att jobbet flyttas en rad ned på listan.  
3. Klik på Backward.
    * Observera att jobbet flyttas en rad upp på listan.  


