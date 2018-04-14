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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f491558c38a48a47e1477c0140d8d1b5f9c8016
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="update-kanban-status"></a><span data-ttu-id="f88ab-103">Uppdatera kanban-status</span><span class="sxs-lookup"><span data-stu-id="f88ab-103">Update kanban status</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f88ab-104">När en kanban tömms av misstag eller en inlevererad kanban behöver tömmas, måste du uppdatera kanban-status.</span><span class="sxs-lookup"><span data-stu-id="f88ab-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="f88ab-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="f88ab-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f88ab-106">Den här proceduren är avsedd för arbetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="f88ab-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="f88ab-107">Hitta kanbanet.</span><span class="sxs-lookup"><span data-stu-id="f88ab-107">Find the kanban.</span></span>
1. <span data-ttu-id="f88ab-108">Gå till Produktionskontroll > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="f88ab-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="f88ab-109">Öppna kolumnfiltret Status för materialhanteringsenhet.</span><span class="sxs-lookup"><span data-stu-id="f88ab-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="f88ab-110">Klicka på Rensa.</span><span class="sxs-lookup"><span data-stu-id="f88ab-110">Click Clear.</span></span>
    * <span data-ttu-id="f88ab-111">Detta återställer filtren.</span><span class="sxs-lookup"><span data-stu-id="f88ab-111">This resets the filters.</span></span>  
4. <span data-ttu-id="f88ab-112">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="f88ab-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f88ab-113">Filtrera till exempel i fältet Kortnummer med värdet "000149".</span><span class="sxs-lookup"><span data-stu-id="f88ab-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="f88ab-114">Ändra status Tömd till status Inlevererad</span><span class="sxs-lookup"><span data-stu-id="f88ab-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="f88ab-115">Klicka på Omvänd tom materialhanteringsenhet.</span><span class="sxs-lookup"><span data-stu-id="f88ab-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="f88ab-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f88ab-116">Click OK.</span></span>
    * <span data-ttu-id="f88ab-117">Observera att status för materialhanteringsenhet är Inlevererad.</span><span class="sxs-lookup"><span data-stu-id="f88ab-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="f88ab-118">Ändra status Inlevererad till status Tömd</span><span class="sxs-lookup"><span data-stu-id="f88ab-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="f88ab-119">Klicka på Töm kanban.</span><span class="sxs-lookup"><span data-stu-id="f88ab-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="f88ab-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f88ab-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f88ab-121">Observera att status för materialhanteringsenhet är Tömd.</span><span class="sxs-lookup"><span data-stu-id="f88ab-121">Notice that the Handling unit status is Emptied.</span></span>  


