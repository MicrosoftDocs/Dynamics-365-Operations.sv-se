--- 
title: "Hantera ledighet och frånvaro"
description: "I den här proceduren går vi igenom genereringen av medarbetarnas tjänstledighetsposter."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: fc16d2aefcb52493e72e78def5b86b9da9673914
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="manage-leaves-of-absence"></a><span data-ttu-id="64d99-103">Hantera ledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="64d99-103">Manage leaves of absence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64d99-104">I den här proceduren går vi igenom genereringen av medarbetarnas tjänstledighetsposter.</span><span class="sxs-lookup"><span data-stu-id="64d99-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="64d99-105">Du kan spåra tjänstledighetstid av skäl som sjukvård, utbildning eller föräldraaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="64d99-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="64d99-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="64d99-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="64d99-107">Gå till Personal > Arbetare > Medarbetare.</span><span class="sxs-lookup"><span data-stu-id="64d99-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="64d99-108">Välj en medarbetare i listan.</span><span class="sxs-lookup"><span data-stu-id="64d99-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="64d99-109">Visa detaljerad information om den valda medarbetaren genom att välja medarbetarens namn.</span><span class="sxs-lookup"><span data-stu-id="64d99-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="64d99-110">Klicka på fliken Anställning.</span><span class="sxs-lookup"><span data-stu-id="64d99-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="64d99-111">Klicka på Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="64d99-111">Click Leave.</span></span>
6. <span data-ttu-id="64d99-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="64d99-112">Click New.</span></span>
7. <span data-ttu-id="64d99-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="64d99-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="64d99-114">Du kan koppla en tjänstledighetstyp till en ersättningskod i tjänstledighetstypformuläret.</span><span class="sxs-lookup"><span data-stu-id="64d99-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="64d99-115">Om en tjänstledighetstyp associeras med en ersättningskod, visas en förtjänstrad med den tillhörande ersättningskoden under tjänstledighetsperioden som du anger.</span><span class="sxs-lookup"><span data-stu-id="64d99-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="64d99-116">Välj en tjänstledighetstyp i listan.</span><span class="sxs-lookup"><span data-stu-id="64d99-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="64d99-117">Exempel: Adoption</span><span class="sxs-lookup"><span data-stu-id="64d99-117">For example: Adoption</span></span>  
9. <span data-ttu-id="64d99-118">Ange datum då tjänstledigheten ska börja.</span><span class="sxs-lookup"><span data-stu-id="64d99-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="64d99-119">Exempel: "2015-10-26"</span><span class="sxs-lookup"><span data-stu-id="64d99-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="64d99-120">Exempel: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="64d99-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="64d99-121">Ange datum då tjänstledigheten ska börja.</span><span class="sxs-lookup"><span data-stu-id="64d99-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="64d99-122">Exempel: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="64d99-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="64d99-123">Ange en beskrivning i noteringsfältet.</span><span class="sxs-lookup"><span data-stu-id="64d99-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="64d99-124">Exempel: Tjänstledighet för adoption</span><span class="sxs-lookup"><span data-stu-id="64d99-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="64d99-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="64d99-125">Click Save.</span></span>


