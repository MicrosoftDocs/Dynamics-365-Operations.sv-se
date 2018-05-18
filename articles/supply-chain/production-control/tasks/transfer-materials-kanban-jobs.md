--- 
title: "Överför material med kanban-jobb (enbart februari 2016)"
description: "Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material."
author: ChristianRytt
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c79480d844627a7eed8129515924f1f70ad04f95
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-materials-with-kanban-jobs-february-2016-only"></a>Överför material med kanban-jobb (enbart februari 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för lagerarbetaren.


## <a name="display-transfer-jobs"></a>Visa överföringsjobb
1. Gå till tillverkningskontroll > Kanban > Kanban board för överföringsjobb.
2. Expandera eller komprimera avsnittet Filter.
    * I avsnittet Filter kan du ange vilka jobb som du vill visa genom att filtrera efter produktionsflöde, aktivitetsnamn, från lagerställe och plats och till lagerställe och plats.  
3. Skriv "11" i fältet Från lagerställe.
4. Skriv "12" i fältet Till plats.

## <a name="start-a-transfer-job"></a>Starta ett överföringsjobb
1. Avmarkera den valda raden i listan - om det finns någon sådan.
2. Väl rad 4 i listan.
    * Välj det första jobbet med statusen Inte planerad. Kontrollera att det här är den enda valda jobbet.  
3. Klicka på Start.
    * Observera att en ikon indikerar att jobbet startas.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Välj ett andra överföringsjobb och ändra kvantiteten
1. Hitta och markera önskad post i listan.
    * Du kan välja flera jobb, men nu väljer du rad 5.  
2. Hitta och markera önskad post i listan.
    * Kontrollera att jobbet i det föregående steget är det enda som har valts. Avmarkera alla andra jobb.  
3. Observera värdet i fältet Jobbkvantitet så att du kan referera till det senare
4. Ange jobbkvantiteten till "30".
    * Meddelandet OBS! Du kan inte överföra 30. Enligt inställningarna för kanban-regel kan du bara överföra den ursprungliga kvantiteten.  
5. Använd värdet som noterades tidigare i fältet Jobbkvantitet
    * Ange jobbkvantiteten till det föregående värdet.  

## <a name="start-the-second-transfer-job"></a>Starta andra överföringsjobbet
1. Klicka på Start.
    * Då startas överföringen av jobbet på rad 5.  

## <a name="complete-both-transfer-jobs"></a>Slutför båda överföringsjobben
1. Väl rad 4 i listan.
    * Nu är två överföringsjobb markerade på rad 4 och rad 5.  
2. Klicka på Slutför.
    * Detta slutför överföringen av båda jobben.  


