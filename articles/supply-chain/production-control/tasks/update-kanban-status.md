---
title: Uppdatera kanban-status
description: När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb8559c0843d7e6e538b5b29dc394a50d05462ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437835"
---
# <a name="update-kanban-status"></a>Uppdatera kanban-status

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]