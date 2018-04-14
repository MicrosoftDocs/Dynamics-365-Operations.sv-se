--- 
title: Definiera resurskunskaper
description: "Resurskapaciteter beskriver vad verksamhetsresurser kan göra."
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6cd8b8e409348b4df1144ad58700882879012766
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="d1b03-103">Definiera resurskunskaper</span><span class="sxs-lookup"><span data-stu-id="d1b03-103">Define resource capabilities</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1b03-104">Resurskapaciteter beskriver vad verksamhetsresurser kan göra.</span><span class="sxs-lookup"><span data-stu-id="d1b03-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="d1b03-105">Vid tidsplanering matchas kraven för varje jobb och operation mot kapaciteter hos de tillgängliga resurserna.</span><span class="sxs-lookup"><span data-stu-id="d1b03-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="d1b03-106">Den här uppgiftsguiden hjälper dig att skapa en resurskapacitet och tilldela den till en resurs.</span><span class="sxs-lookup"><span data-stu-id="d1b03-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="d1b03-107">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="d1b03-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="d1b03-108">Skapa en ny resurskapacitet</span><span class="sxs-lookup"><span data-stu-id="d1b03-108">Create a resource capability</span></span>
1. <span data-ttu-id="d1b03-109">Gå till Resurskunskaper.</span><span class="sxs-lookup"><span data-stu-id="d1b03-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="d1b03-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d1b03-110">Click New.</span></span>
3. <span data-ttu-id="d1b03-111">Ange ID för resurskapaciteten i fältet Kapacitet.</span><span class="sxs-lookup"><span data-stu-id="d1b03-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="d1b03-112">Använd kapacitets-ID för en viss operation för att ange att resurser som måste ha denna kapacitet för att utföra operationen.</span><span class="sxs-lookup"><span data-stu-id="d1b03-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="d1b03-113">I fältet Beskrivning anger du en kort beskrivning av kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="d1b03-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="d1b03-114">Tilldela kapaciteten till en resurs</span><span class="sxs-lookup"><span data-stu-id="d1b03-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="d1b03-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d1b03-115">Click Add.</span></span>
2. <span data-ttu-id="d1b03-116">Ange ID för resursen i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="d1b03-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="d1b03-117">En resurskapacitet kan tilldelas till en eller flera resurser.</span><span class="sxs-lookup"><span data-stu-id="d1b03-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="d1b03-118">I fältet Utgång anger du datum.</span><span class="sxs-lookup"><span data-stu-id="d1b03-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="d1b03-119">Du kan använda det här fältet om du vill ange att en resurs har kapacitet i bara en begränsad tid.</span><span class="sxs-lookup"><span data-stu-id="d1b03-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="d1b03-120">Välj ett tal i fältet Prioritet.</span><span class="sxs-lookup"><span data-stu-id="d1b03-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="d1b03-121">När du planerar jobb och operationer kan du ange om du vill välja resurser efter prioritet.</span><span class="sxs-lookup"><span data-stu-id="d1b03-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="d1b03-122">Om du väljer att göra detta och fler än en resurs kan utföra jobbet eller operationen per det begärt datumet, väljs resursen som har lägst prioritet med avseende på den begärda kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="d1b03-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="d1b03-123">Välj ett tal i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="d1b03-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="d1b03-124">När du anger att ett jobb eller en operation kräver en viss kapacitet, kan du också ange den lägsta nivån som krävs.</span><span class="sxs-lookup"><span data-stu-id="d1b03-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="d1b03-125">Använd kapacitetsnivån för att skilja mellan resurser som kan utföra samma jobb, men med olika hastighet, styrka, storlek osv.</span><span class="sxs-lookup"><span data-stu-id="d1b03-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  


