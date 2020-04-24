---
title: Flytta tidsplanerade kanban-jobb
description: Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb95bab2173cb45300560f59c394cd2d558fe69f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206989"
---
# <a name="move-scheduled-kanban-jobs"></a>Flytta tidsplanerade kanban-jobb

[!include [banner](../../includes/banner.md)]

Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren som arbetar med kanbans.

## <a name="select-scheduled-kanban-jobs"></a>Välj tidsplanerade kanban-jobb. 

1. Gå till **Produktionskontroll > Kanban > Kanban-jobbplanering**. 

2. I fältet **Arbetsgrupp**, klicka på den nedrullningsbara knappen för att öppna uppslaget. 

3. Markera vald rad i listan. 
   - Välj arbetsgrupp 1250. 
4. Klicka på **Välj**. 

5. I fältet **Visa jobbstatus**, välj **Tidsplanerad**. Jobblistan filtreras så att endast de tidsplanerade kanban-jobben visas. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Flytta kanban-jobb till en annan period. 

1. Hitta och markera önskad post i listan. Markera ett jobb som har statusen **Planerat jobb** till exempel ett jobb som har tidsplanerats den 20 december 2012 i fältet **Planerad period**. Flytta sedan jobbet till föregående period. 

2. Klicka på **Föregående period**. 

3. Klicka på **Slut** för att flytta jobbet till slutet av jobblistan som det sista jobbet i föregående period. 

4. Hitta och markera önskad post i listan. Markera ett jobb som har statusen **Planerat jobb** till exempel ett jobb som har tidsplanerats den 18 december 2012 i fältet **Planerad period**. Flytta sedan jobbet till nästa period. 

5. Klicka på **Nästa period**. 

6. Klicka på **Start** för att flytta jobbet till start av jobblistan som det första jobbet i föregående period. 

## <a name="move-a-job-within-a-period"></a>Flytta ett jobb inom en period. 

1. Hitta och markera önskad post i listan. Markera ett jobb som har statusen Planerat jobb, till exempel det andra jobbet som har tidsplanerats den 19 december 2012 i fältet **Planerad period**. Flytta sedan jobbet inom den planerade perioden. 

2. Klicka på **Framåt.** Observera att jobbet flyttas en rad ned på listan. 

3. Klicka på **Bakåt**. Observera att jobbet flyttas en rad upp på listan.
