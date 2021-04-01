---
title: Skapa operationstidsmallar
description: Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9829e91500abf8cba3f7cbfe2f89863cb2b1f4c4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257373"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="22031-103">Skapa operationstidsmallar</span><span class="sxs-lookup"><span data-stu-id="22031-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="22031-104">Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="22031-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="22031-105">I den här proceduren visas om hur du definierar en arbetstidsmall med hjälp av arbetstidsplaneringsegenskaper för att kategorisera arbetstidintervall.</span><span class="sxs-lookup"><span data-stu-id="22031-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="22031-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="22031-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="22031-107">Gå till Alla arbetsytor > Livscykelhantering för resurs.</span><span class="sxs-lookup"><span data-stu-id="22031-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="22031-108">Klicka på Arbetstidsmallar.</span><span class="sxs-lookup"><span data-stu-id="22031-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="22031-109">Skapa arbetstidsmall</span><span class="sxs-lookup"><span data-stu-id="22031-109">Create working time template</span></span>
1. <span data-ttu-id="22031-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="22031-110">Click New.</span></span>
2. <span data-ttu-id="22031-111">Skriv ett värde i fältet Arbetstidsmall.</span><span class="sxs-lookup"><span data-stu-id="22031-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="22031-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="22031-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="22031-113">Expandera alternativet Måndag.</span><span class="sxs-lookup"><span data-stu-id="22031-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="22031-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="22031-114">Click Add.</span></span>
6. <span data-ttu-id="22031-115">Ange en tid i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="22031-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="22031-116">Ange tiden då arbetet börjar på morgonen.</span><span class="sxs-lookup"><span data-stu-id="22031-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="22031-117">Ange en tid i fältet Till.</span><span class="sxs-lookup"><span data-stu-id="22031-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="22031-118">Ange tiden när medarbetare tar lunch.</span><span class="sxs-lookup"><span data-stu-id="22031-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="22031-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="22031-119">Click Add.</span></span>
9. <span data-ttu-id="22031-120">Ange en tid i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="22031-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="22031-121">Ange tiden då arbetet återupptas efter efter lunch.</span><span class="sxs-lookup"><span data-stu-id="22031-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="22031-122">Ange en tid i fältet Till.</span><span class="sxs-lookup"><span data-stu-id="22031-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="22031-123">Ange när arbetsdagen slutar.</span><span class="sxs-lookup"><span data-stu-id="22031-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="22031-124">Replikera arbetstider till alla veckodagar</span><span class="sxs-lookup"><span data-stu-id="22031-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="22031-125">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="22031-125">Click Copy day.</span></span>
    * <span data-ttu-id="22031-126">Kopiera arbetstidsdefinitioner från måndag till tisdag.</span><span class="sxs-lookup"><span data-stu-id="22031-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="22031-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22031-127">Click OK.</span></span>
3. <span data-ttu-id="22031-128">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="22031-128">Click Copy day.</span></span>
    * <span data-ttu-id="22031-129">Kopiera arbetstidsdefinitioner från måndag till onsdag.</span><span class="sxs-lookup"><span data-stu-id="22031-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="22031-130">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="22031-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="22031-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22031-131">Click OK.</span></span>
6. <span data-ttu-id="22031-132">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="22031-132">Click Copy day.</span></span>
    * <span data-ttu-id="22031-133">Kopiera arbetstidsdefinitioner från måndag till torsdag.</span><span class="sxs-lookup"><span data-stu-id="22031-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="22031-134">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="22031-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="22031-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22031-135">Click OK.</span></span>
9. <span data-ttu-id="22031-136">Klicka på Kopiera dag.</span><span class="sxs-lookup"><span data-stu-id="22031-136">Click Copy day.</span></span>
    * <span data-ttu-id="22031-137">Kopiera arbetstidsdefinitioner från måndag till fredag.</span><span class="sxs-lookup"><span data-stu-id="22031-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="22031-138">Markera ett alternativ i fältet Till veckodag.</span><span class="sxs-lookup"><span data-stu-id="22031-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="22031-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22031-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="22031-140">Definiera tidsluckor för särskilda operationer</span><span class="sxs-lookup"><span data-stu-id="22031-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="22031-141">Expandera alternativet Fredag.</span><span class="sxs-lookup"><span data-stu-id="22031-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="22031-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="22031-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="22031-143">Ange eller välj ett värde i fältet Egenskap.</span><span class="sxs-lookup"><span data-stu-id="22031-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="22031-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="22031-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="22031-145">Ange eller välj ett värde i fältet Egenskap.</span><span class="sxs-lookup"><span data-stu-id="22031-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="22031-146">Markera helgdagar som stängda för upphämtning</span><span class="sxs-lookup"><span data-stu-id="22031-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="22031-147">Expandera alternativt Lördag.</span><span class="sxs-lookup"><span data-stu-id="22031-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="22031-148">Välj Ja i fältet Stängd för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="22031-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="22031-149">Expandera alternativet Söndag.</span><span class="sxs-lookup"><span data-stu-id="22031-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="22031-150">Välj Ja i fältet Stängd för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="22031-150">Select Yes in the Closed for pickup field.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]