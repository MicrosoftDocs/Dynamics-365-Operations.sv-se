--- 
title: Hantera arbetstagarnas logi
description: "Den här proceduren går igenom stegen för att ställa in logityper för arbetsmiljön, till exempel ergonomiska stolar eller periodiska raster."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="13029-103">Hantera arbetstagarnas logi</span><span class="sxs-lookup"><span data-stu-id="13029-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="13029-104">Den här proceduren går igenom stegen för att ställa in logityper för arbetsmiljön, till exempel ergonomiska stolar eller periodiska raster.</span><span class="sxs-lookup"><span data-stu-id="13029-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="13029-105">Här visas även hur du tilldelar dessa logityper till en arbetare och antingen godkänner eller avslår logitypen.</span><span class="sxs-lookup"><span data-stu-id="13029-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="13029-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="13029-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="13029-107">Ställ in logi</span><span class="sxs-lookup"><span data-stu-id="13029-107">Setup accommodations</span></span>
1. <span data-ttu-id="13029-108">Gå till Personal > Inställningar > Boendetyper.</span><span class="sxs-lookup"><span data-stu-id="13029-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="13029-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="13029-109">Click New.</span></span>
3. <span data-ttu-id="13029-110">Ange ett namn för boendet i fältet Logityp.</span><span class="sxs-lookup"><span data-stu-id="13029-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="13029-111">Exempel: Tangentbord.</span><span class="sxs-lookup"><span data-stu-id="13029-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="13029-112">Ange en beskrivning av logitypen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="13029-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="13029-113">Exempel: Ergonomiskt tangentbord.</span><span class="sxs-lookup"><span data-stu-id="13029-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="13029-114">Ange eventuell information som hjälper till att klargöra login i fältet Anmärkning.</span><span class="sxs-lookup"><span data-stu-id="13029-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="13029-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="13029-115">Click Save.</span></span>
7. <span data-ttu-id="13029-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="13029-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="13029-117">Tilldela logi</span><span class="sxs-lookup"><span data-stu-id="13029-117">Assign accommodations</span></span>
1. <span data-ttu-id="13029-118">Gå till Personal > Arbetare > Medarbetare.</span><span class="sxs-lookup"><span data-stu-id="13029-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="13029-119">Välj en medarbetare från listan.</span><span class="sxs-lookup"><span data-stu-id="13029-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="13029-120">Klicka på medarbetarens namn för att visa information om den medarbetare som begär login.</span><span class="sxs-lookup"><span data-stu-id="13029-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="13029-121">Expandera snabbfliken Personlig information.</span><span class="sxs-lookup"><span data-stu-id="13029-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="13029-122">Klicka på Logi.</span><span class="sxs-lookup"><span data-stu-id="13029-122">Click Accommodations.</span></span>
6. <span data-ttu-id="13029-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="13029-123">Click New.</span></span>
7. <span data-ttu-id="13029-124">Välj lämplig logi i fältet Logityp.</span><span class="sxs-lookup"><span data-stu-id="13029-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="13029-125">Exempel: Tangentbord</span><span class="sxs-lookup"><span data-stu-id="13029-125">Example: Keyboard</span></span>
8. <span data-ttu-id="13029-126">Välj den arbetsuppgift som kräver login i fältet Arbetsuppgift.</span><span class="sxs-lookup"><span data-stu-id="13029-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="13029-127">Ställ in lämplig status i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="13029-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="13029-128">Exempel: Rimligt</span><span class="sxs-lookup"><span data-stu-id="13029-128">Example: Reasonable</span></span>
    * <span data-ttu-id="13029-129">Följande statusalternativ finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="13029-129">The following statuses are available.</span></span> <span data-ttu-id="13029-130">Begärt anger att login har skapats men ännu inte har granskats.</span><span class="sxs-lookup"><span data-stu-id="13029-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="13029-131">Rimligt anger att login är rimlig och används och kommer att godkännas.</span><span class="sxs-lookup"><span data-stu-id="13029-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="13029-132">Oskälig anger att login kommer att innebära en orimlig börda för arbetsgivaren och har avslagits.</span><span class="sxs-lookup"><span data-stu-id="13029-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="13029-133">I det här exemplet godkändes begäran direkt eftersom logibegäran var minimal.</span><span class="sxs-lookup"><span data-stu-id="13029-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="13029-134">Välj den person som godkände logibegäran i fältet Godkänt.</span><span class="sxs-lookup"><span data-stu-id="13029-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="13029-135">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="13029-135">Click Select.</span></span>
12. <span data-ttu-id="13029-136">Ange datum och tid när logibegäran godkändes i fältet Godkännandedatum.</span><span class="sxs-lookup"><span data-stu-id="13029-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="13029-137">Expandera avsnittet Anmärkning.</span><span class="sxs-lookup"><span data-stu-id="13029-137">Expand the Note section.</span></span>
14. <span data-ttu-id="13029-138">Ange de informations- eller resurskostnader som gör det lättare att klargöra påverkan av login i fältet Ekonomisk.</span><span class="sxs-lookup"><span data-stu-id="13029-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="13029-139">Om login har nekats kan svarsfältet användas för att ange varför begäran avslogs.</span><span class="sxs-lookup"><span data-stu-id="13029-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="13029-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="13029-140">Click Save.</span></span>


