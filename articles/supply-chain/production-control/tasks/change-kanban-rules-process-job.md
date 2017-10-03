--- 
title: "Ändra kanban-regel för ett processjobb"
description: "Den här proceduren fokuserar på att ändra den använda kanban-regeln för en viss kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
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
ms.openlocfilehash: e8355a94322e6489fe64f22a049a34b7ecfe65b9
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a>Ändra kanban-regel för ett processjobb

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att ändra den använda kanban-regeln för en viss kanban. Det här är användbart för att utjämna beläggningsresurser eller i händelse av ett fel. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för planeraren som arbetar på ett lean manufacturing företag och är ansvarig för värdeströmmen.


## <a name="copy-kanban-rule"></a>Kopiera kanban-regel
1. Gå till Kanban-regler.
2. Hitta och markera önskad post i listan.
    * Välj händelsen Kanban-regel 000022 för L0001.  
3. Klicka på Duplicera kanban-regel.
4. Klicka på OK.

## <a name="change-kanban-rule"></a>Ändra kanban-regel
1. Stäng sidan.
2. Gå till Kanban-jobbplanering.
3. Markera vald rad i listan.
    * Markera raden med Kanban 000177.  
4. Klicka på Använd alternativ kanban-regel.
5. Klicka på Nästa.
6. I fältet Kanban-regel, ange eller välj ett värde.
    * Välj kanban-regeln som har skapats tidigare. Detta är kanban-regeln med det högsta numret.  
7. Klicka på Avsluta.
    * Nu använder kanban-jobbet en annan kanban-regel. Det kan vara bra för att utjämna beläggningen av arbetsgrupper.  


