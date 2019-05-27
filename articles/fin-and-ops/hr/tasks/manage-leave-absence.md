---
title: Hantera ledighet och frånvaro
description: I den här proceduren går vi igenom genereringen av medarbetarnas tjänstledighetsposter.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmEmploymentLeave
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ce57495be4ae601d6ac06bb4780a2e1192dfcc5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509767"
---
# <a name="manage-leave-of-absence"></a><span data-ttu-id="3d33a-103">Hantera ledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="3d33a-103">Manage leave of absence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3d33a-104">I den här proceduren går vi igenom genereringen av medarbetarnas tjänstledighetsposter.</span><span class="sxs-lookup"><span data-stu-id="3d33a-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="3d33a-105">Du kan spåra tjänstledighetstid av skäl som sjukvård, utbildning eller föräldraaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="3d33a-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="3d33a-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="3d33a-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="3d33a-107">Gå till Personal > Arbetare > Medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3d33a-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="3d33a-108">Välj en medarbetare i listan.</span><span class="sxs-lookup"><span data-stu-id="3d33a-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="3d33a-109">Visa detaljerad information om den valda medarbetaren genom att välja medarbetarens namn.</span><span class="sxs-lookup"><span data-stu-id="3d33a-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="3d33a-110">Klicka på fliken Anställning.</span><span class="sxs-lookup"><span data-stu-id="3d33a-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="3d33a-111">Klicka på Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="3d33a-111">Click Leave.</span></span>
6. <span data-ttu-id="3d33a-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3d33a-112">Click New.</span></span>
7. <span data-ttu-id="3d33a-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="3d33a-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="3d33a-114">Du kan koppla en tjänstledighetstyp till en ersättningskod i tjänstledighetstypformuläret.</span><span class="sxs-lookup"><span data-stu-id="3d33a-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="3d33a-115">Om en tjänstledighetstyp associeras med en ersättningskod, visas en förtjänstrad med den tillhörande ersättningskoden under tjänstledighetsperioden som du anger.</span><span class="sxs-lookup"><span data-stu-id="3d33a-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="3d33a-116">Välj en tjänstledighetstyp i listan.</span><span class="sxs-lookup"><span data-stu-id="3d33a-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="3d33a-117">Exempel: Adoption</span><span class="sxs-lookup"><span data-stu-id="3d33a-117">For example: Adoption</span></span>  
9. <span data-ttu-id="3d33a-118">Ange datum då tjänstledigheten ska börja.</span><span class="sxs-lookup"><span data-stu-id="3d33a-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="3d33a-119">Exempel: "2015-10-26"</span><span class="sxs-lookup"><span data-stu-id="3d33a-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="3d33a-120">Exempel: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="3d33a-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="3d33a-121">Ange datum då tjänstledigheten ska börja.</span><span class="sxs-lookup"><span data-stu-id="3d33a-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="3d33a-122">Exempel: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="3d33a-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="3d33a-123">Ange en beskrivning i noteringsfältet.</span><span class="sxs-lookup"><span data-stu-id="3d33a-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="3d33a-124">Exempel: Tjänstledighet för adoption</span><span class="sxs-lookup"><span data-stu-id="3d33a-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="3d33a-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="3d33a-125">Click Save.</span></span>

