--- 
title: Skapa operationstidsmallar
description: "Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d9290dd363e5e617ec714f9b3ee8b71a21a61166
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="create-working-time-templates"></a><span data-ttu-id="38e77-103">Skapa operationstidsmallar</span><span class="sxs-lookup"><span data-stu-id="38e77-103">Create working time templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38e77-104">Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="38e77-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="38e77-105">I den här proceduren visas om hur du definierar en arbetstidsmall med hjälp av arbetstidsplaneringsegenskaper för att kategorisera arbetstidintervall.</span><span class="sxs-lookup"><span data-stu-id="38e77-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="38e77-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="38e77-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="38e77-107">Gå till Alla arbetsytor > Livscykelhantering för resurs.</span><span class="sxs-lookup"><span data-stu-id="38e77-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="38e77-108">Klicka på Arbetstidsmallar.</span><span class="sxs-lookup"><span data-stu-id="38e77-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="38e77-109">Skapa arbetstidsmall</span><span class="sxs-lookup"><span data-stu-id="38e77-109">Create working time template</span></span>
1. <span data-ttu-id="38e77-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e77-110">Click New.</span></span>
2. <span data-ttu-id="38e77-111">Skriv ett värde i fältet Arbetstidsmall.</span><span class="sxs-lookup"><span data-stu-id="38e77-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="38e77-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="38e77-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="38e77-113">Expandera alternativet Måndag.</span><span class="sxs-lookup"><span data-stu-id="38e77-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="38e77-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="38e77-114">Click Add.</span></span>
6. <span data-ttu-id="38e77-115">Ange en tid i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="38e77-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="38e77-116">Ange tiden då arbetet börjar på morgonen.</span><span class="sxs-lookup"><span data-stu-id="38e77-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="38e77-117">Ange en tid i fältet Till.</span><span class="sxs-lookup"><span data-stu-id="38e77-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="38e77-118">Ange tiden när medarbetare tar lunch.</span><span class="sxs-lookup"><span data-stu-id="38e77-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="38e77-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="38e77-119">Click Add.</span></span>
9. <span data-ttu-id="38e77-120">Ange en tid i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="38e77-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="38e77-121">Ange tiden då arbetet återupptas efter efter lunch.</span><span class="sxs-lookup"><span data-stu-id="38e77-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="38e77-122">Ange en tid i fältet Till.</span><span class="sxs-lookup"><span data-stu-id="38e77-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="38e77-123">Ange när arbetsdagen slutar.</span><span class="sxs-lookup"><span data-stu-id="38e77-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="38e77-124">Replikera arbetstider till alla veckodagar</span><span class="sxs-lookup"><span data-stu-id="38e77-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="38e77-125">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="38e77-125">Click Copy day.</span></span>
    * <span data-ttu-id="38e77-126">Kopiera arbetstidsdefinitioner från måndag till tisdag.</span><span class="sxs-lookup"><span data-stu-id="38e77-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="38e77-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e77-127">Click OK.</span></span>
3. <span data-ttu-id="38e77-128">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="38e77-128">Click Copy day.</span></span>
    * <span data-ttu-id="38e77-129">Kopiera arbetstidsdefinitioner från måndag till onsdag.</span><span class="sxs-lookup"><span data-stu-id="38e77-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="38e77-130">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="38e77-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="38e77-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e77-131">Click OK.</span></span>
6. <span data-ttu-id="38e77-132">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="38e77-132">Click Copy day.</span></span>
    * <span data-ttu-id="38e77-133">Kopiera arbetstidsdefinitioner från måndag till torsdag.</span><span class="sxs-lookup"><span data-stu-id="38e77-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="38e77-134">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="38e77-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="38e77-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e77-135">Click OK.</span></span>
9. <span data-ttu-id="38e77-136">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="38e77-136">Click Copy day.</span></span>
    * <span data-ttu-id="38e77-137">Kopiera arbetstidsdefinitioner från måndag till fredag.</span><span class="sxs-lookup"><span data-stu-id="38e77-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="38e77-138">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="38e77-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="38e77-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e77-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="38e77-140">Definiera tidsluckor för särskilda operationer</span><span class="sxs-lookup"><span data-stu-id="38e77-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="38e77-141">Expandera alternativet Fredag.</span><span class="sxs-lookup"><span data-stu-id="38e77-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="38e77-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="38e77-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="38e77-143">Ange eller välj ett värde i fältet Egenskap.</span><span class="sxs-lookup"><span data-stu-id="38e77-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="38e77-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="38e77-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="38e77-145">Ange eller välj ett värde i fältet Egenskap.</span><span class="sxs-lookup"><span data-stu-id="38e77-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="38e77-146">Markera helgdagar som stängda för upphämtning</span><span class="sxs-lookup"><span data-stu-id="38e77-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="38e77-147">Expandera alternativt Lördag.</span><span class="sxs-lookup"><span data-stu-id="38e77-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="38e77-148">Välj Ja i fältet Stängd för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="38e77-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="38e77-149">Expandera alternativet Söndag.</span><span class="sxs-lookup"><span data-stu-id="38e77-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="38e77-150">Välj Ja i fältet Stängd för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="38e77-150">Select Yes in the Closed for pickup field.</span></span>


