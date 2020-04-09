---
title: Uppdatera kanban-status
description: När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48dd5c3a878efb7413f461e76fde086030015b60
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146685"
---
# <a name="update-kanban-status"></a><span data-ttu-id="23532-103">Uppdatera kanban-status</span><span class="sxs-lookup"><span data-stu-id="23532-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23532-104">När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status.</span><span class="sxs-lookup"><span data-stu-id="23532-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="23532-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="23532-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="23532-106">Den här proceduren är avsedd för arbetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="23532-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="23532-107">Hitta kanbanet.</span><span class="sxs-lookup"><span data-stu-id="23532-107">Find the kanban.</span></span>
1. <span data-ttu-id="23532-108">Gå till Produktionskontroll > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="23532-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="23532-109">Öppna kolumnfiltret Status för materialhanteringsenhet.</span><span class="sxs-lookup"><span data-stu-id="23532-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="23532-110">Klicka på Rensa.</span><span class="sxs-lookup"><span data-stu-id="23532-110">Click Clear.</span></span>
    * <span data-ttu-id="23532-111">Detta återställer filtren.</span><span class="sxs-lookup"><span data-stu-id="23532-111">This resets the filters.</span></span>  
4. <span data-ttu-id="23532-112">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="23532-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="23532-113">Filtrera till exempel i fältet Kortnummer med värdet "000149".</span><span class="sxs-lookup"><span data-stu-id="23532-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="23532-114">Ändra status Tömd till status Inlevererad</span><span class="sxs-lookup"><span data-stu-id="23532-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="23532-115">Klicka på Omvänd tom materialhanteringsenhet.</span><span class="sxs-lookup"><span data-stu-id="23532-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="23532-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="23532-116">Click OK.</span></span>
    * <span data-ttu-id="23532-117">Observera att status för materialhanteringsenhet är Inlevererad.</span><span class="sxs-lookup"><span data-stu-id="23532-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="23532-118">Ändra status Inlevererad till status Tömd</span><span class="sxs-lookup"><span data-stu-id="23532-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="23532-119">Klicka på Töm kanban.</span><span class="sxs-lookup"><span data-stu-id="23532-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="23532-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="23532-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="23532-121">Observera att status för materialhanteringsenhet är Tömd.</span><span class="sxs-lookup"><span data-stu-id="23532-121">Notice that the Handling unit status is Emptied.</span></span>  

