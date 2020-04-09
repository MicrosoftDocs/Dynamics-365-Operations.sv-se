---
title: Ändra kanban-regel för ett processjobb
description: Den här proceduren fokuserar på att ändra den använda kanban-regeln för en viss kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 485afff3747a87a6e36f0249b146a39361d81b23
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147145"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Ändra kanban-regel för ett processjobb

[!include [banner](../../includes/banner.md)]

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

