--- 
title: Tidsplanera kanban-jobb
description: "Den här proceduren fokuserar på att tidsplanera kanban-processjobb för en specifik arbetsgrupp."
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
ms.openlocfilehash: 88399f70a3c286d536637e166e8428eae50a561d
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="schedule-kanban-jobs"></a>Tidsplanera kanban-jobb

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att tidsplanera kanban-processjobb för en specifik arbetsgrupp. Proceduren "Förbered ett kanban-processjobb när material inte är tillgängliga" är en förutsättning när du skapar den här proceduren. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Denna uppgift är avsedd för produktionslagerarbetsledaren och produktionsplaneraren som arbetar med kanbans.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Välj kanban-jobb för en arbetsgrupp
1. Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.
2. Expandera faktarutan Periodkapacitet
    * Expandera Kanban-faktaboxen.  
3. Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.
4. Markera vald rad i listan.
    * Välj arbetsgrupp 1250. Då filtreras vyn så att endast jobben för arbetsgrupp 1250 visas.  
5. Klicka på länken på den valda raden i listan.
6. Klicka på Välj.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Tidsplanera ett kanban-jobb i den första tillgängliga perioden
1. Markera vald rad i listan.
    * Välj den första raden i listan som statusen Inte planerad. Den prickiga ikonen i fältet Jobbstatus anger inte planerad.  
2. Klicka på Tidsplanera.
    * Kanban-jobbet tidsplaneras i den första tillgängliga perioden.  
    * Observera att kanban-jobb flyttas till slutet av listan, eftersom de har lagts till den period som startar från idag.  
    * Om den period som startar från dagens datum är fullbokad, kommer jobbet flyttas till den första tillgängliga perioden.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Tidsplanera två kanban-jobb för en specifik dag
1. Väl rad 1 i listan.
    * Du bör se att den första raden har statusen Inte planerad i fältet Jobbstatus.  
2. Väl rad 2 i listan.
    * Du bör se att den andra raden har statusen Inte planerad i fältet Jobbstatus. Nu har de två första jobben valts.  
3. Klicka på Tidsplan från den om du vill öppna dialogrutan.
4. Markera eller avmarkera rutan Åsidosätt reaktion på standardkapacitetsbrist.
    * Med det här alternativet kan du åsidosätta reaktionen på standardkapacitetsbristen.  
5. Välj "Lägg till i den begärda perioden" i fältet Reaktion på kapacitetsbrist.
    * Med det här alternativet läggs jobbet till i den begärda perioden oavsett om arbetsgruppen kanske är överbelagd.  
6. Klicka på Tidsplanera.
    * Observera att båda jobben anges till den önskade perioden.  
    * I avsnittet Periodkapacitet kan du visa beläggningen för varje period. I fältet Förbrukning visas den tidsplanerade förbrukningen i denna period. Om den tidsplanerade förbrukningen är högre än den tillgängliga kapaciteten i denna period, kommer den överbelagda förbrukningen att markeras.  

