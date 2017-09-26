--- 
title: Uppdatera kanban-status
description: "När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: caf7dead2da14e1ff76e205e7477b1eb11a2ca52
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="update-kanban-status"></a>Uppdatera kanban-status

[!include[task guide banner](../../includes/task-guide-banner.md)]

När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för arbetsansvarig.


## <a name="find-the-kanban"></a>Hitta kanbanet.
1. Gå till Produktionskontroll > Kanban > Kanbans.
2. Öppna kolumnfiltret Status för materialhanteringsenhet.
3. Klicka på Rensa.
    * Detta återställer filtren.  
4. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Kortnummer med värdet "000149".

## <a name="change-emptied-status-to-received-status"></a>Ändra status Tömd till status Inlevererad
1. Klicka på Omvänd tom materialhanteringsenhet.
2. Klicka på OK.
    * Observera att status för materialhanteringsenhet är Inlevererad.  

## <a name="change-received-status-to-emptied-status"></a>Ändra status Inlevererad till status Tömd
1. Klicka på Töm kanban.
2. Markera vald rad i listan.
    * Observera att status för materialhanteringsenhet är Tömd.  


