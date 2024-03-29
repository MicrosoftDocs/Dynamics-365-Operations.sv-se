---
title: Överför material med kanban-jobb
description: Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11771bbedc9fe4bdfaaa074c449cd329ce1a1d8f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568001"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Överför material med kanban-jobb

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]