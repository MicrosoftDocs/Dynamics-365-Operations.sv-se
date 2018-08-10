--- 
title: "Förbered ett kanban-processjobb när material är inte tillgängliga för arbetsgruppen"
description: "I den här proceduren ligger fokus på att förbereda ett kanban-processjobb när en del av materialet inte är tillgängligt för arbetsgruppen och det därför är nödvändigt att plocka material från lagerstället."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a47af6910a9686e74ab6d1069dd02079e60cb8a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Förbered ett kanban-processjobb när material är inte tillgängliga för arbetsgruppen

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren ligger fokus på att förbereda ett kanban-processjobb när en del av materialet inte är tillgängligt för arbetsgruppen och det därför är nödvändigt att plocka material från lagerstället. Proceduren "Förbered ett kanban-processjobb när material är tillgängliga" är en förutsättning när du skapar den här proceduren. Den här proceduren är avsedd för maskinoperatören. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Produktionskontroll > Kanban > Kanban-tavla för processjobb.
2. Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.
3. Klicka på länken på den valda raden i listan.
    * Välj arbetsgrupp 1250.  
4. Hitta och markera önskad post i listan.
    * Välj Kanban 000356.  
5. Hitta och markera önskad post i listan.
    * I listan avmarkerar du rad 4. eller rad 4 om du inte har slutfört uppgiften "Förbered ett kanban-processjobb när material är tillgängliga".  
6. Växla expansionen av avsnittet Plocklista.
    * Ikonen Ingen post i tillförselstatusen visar att det saknas 48 st. av artikeln P0002 för arbetsgruppen.  

## <a name="transfer-materials-to-work-cell"></a>Överför material till arbetsgrupp
1. Växla expansionen av avsnittet Överför jobb.
2. Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P0002.
3. Hitta och markera önskad post i listan.
4. Klicka på Start.
    * Överföring pågår.  
5. Klicka på Slutför.
    * Artikeln P0002 är nu tillgänglig i plocklistan för kanban-jobb. Det innebär att vi kan förbereda kanban med alla nödvändiga material.  
6. Klicka på Förbered.
    * Lägg märke till att en ikon i jobbstatusen indikerar att jobbet nu är klart.  


