---
title: Uppdatera kanban-status
description: När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831828"
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