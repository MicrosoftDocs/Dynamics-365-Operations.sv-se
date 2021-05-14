---
title: Skapa operationstidsmallar
description: Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920939"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="97f17-103">Skapa operationstidsmallar</span><span class="sxs-lookup"><span data-stu-id="97f17-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97f17-104">Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="97f17-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="97f17-105">I den här proceduren visas om hur du definierar en arbetstidsmall med hjälp av arbetstidsplaneringsegenskaper för att kategorisera arbetstidintervall.</span><span class="sxs-lookup"><span data-stu-id="97f17-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="97f17-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="97f17-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="97f17-107">Gå till **Arbetsytor > Livscykelhantering för resurser**.</span><span class="sxs-lookup"><span data-stu-id="97f17-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="97f17-108">Välj **Arbetstidmallar**.</span><span class="sxs-lookup"><span data-stu-id="97f17-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="97f17-109">Skapa arbetstidsmall</span><span class="sxs-lookup"><span data-stu-id="97f17-109">Create working time template</span></span>

1. <span data-ttu-id="97f17-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="97f17-110">Select **New**.</span></span>
1. <span data-ttu-id="97f17-111">I fältet **Arbetstidmall** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="97f17-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="97f17-112">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="97f17-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="97f17-113">Expandera avsnittet **Måndag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="97f17-114">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="97f17-114">Select **Add**.</span></span>
1. <span data-ttu-id="97f17-115">Ange en tidpunkt i fältet **Från**.</span><span class="sxs-lookup"><span data-stu-id="97f17-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="97f17-116">Ange tiden då arbetet börjar på morgonen.</span><span class="sxs-lookup"><span data-stu-id="97f17-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="97f17-117">Ange en tidpunkt i fältet **Till**.</span><span class="sxs-lookup"><span data-stu-id="97f17-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="97f17-118">Ange tiden när medarbetare tar lunch.</span><span class="sxs-lookup"><span data-stu-id="97f17-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="97f17-119">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="97f17-119">Select **Add**.</span></span>
1. <span data-ttu-id="97f17-120">Ange en tidpunkt i fältet **Från**.</span><span class="sxs-lookup"><span data-stu-id="97f17-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="97f17-121">Ange tiden då arbetet återupptas efter efter lunch.</span><span class="sxs-lookup"><span data-stu-id="97f17-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="97f17-122">Ange en tidpunkt i fältet **Till**.</span><span class="sxs-lookup"><span data-stu-id="97f17-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="97f17-123">Ange när arbetsdagen slutar.</span><span class="sxs-lookup"><span data-stu-id="97f17-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="97f17-124">Replikera arbetstider till alla veckodagar</span><span class="sxs-lookup"><span data-stu-id="97f17-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="97f17-125">Välj **Kopiera dag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="97f17-126">Kopiera arbetstidsdefinitioner från måndag till tisdag.</span><span class="sxs-lookup"><span data-stu-id="97f17-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="97f17-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f17-127">Select **OK**.</span></span>
1. <span data-ttu-id="97f17-128">Välj **Kopiera dag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="97f17-129">Kopiera arbetstidsdefinitioner från måndag till onsdag.</span><span class="sxs-lookup"><span data-stu-id="97f17-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="97f17-130">Välj ett alternativ i fältet **Till veckodag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="97f17-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f17-131">Select **OK**.</span></span>
1. <span data-ttu-id="97f17-132">Välj **Kopiera dag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="97f17-133">Kopiera arbetstidsdefinitioner från måndag till torsdag.</span><span class="sxs-lookup"><span data-stu-id="97f17-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="97f17-134">Välj ett alternativ i fältet **Till veckodag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="97f17-135">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f17-135">Select **OK**.</span></span>
1. <span data-ttu-id="97f17-136">Välj **Kopiera dag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="97f17-137">Kopiera arbetstidsdefinitioner från måndag till fredag.</span><span class="sxs-lookup"><span data-stu-id="97f17-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="97f17-138">Välj ett alternativ i fältet **Till veckodag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="97f17-139">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f17-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="97f17-140">Definiera tidsluckor för särskilda operationer</span><span class="sxs-lookup"><span data-stu-id="97f17-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="97f17-141">Expandera avsnittet **Fredag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="97f17-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="97f17-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="97f17-143">Ange eller välj ett värde i fältet **Egenskap**.</span><span class="sxs-lookup"><span data-stu-id="97f17-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="97f17-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="97f17-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="97f17-145">Ange eller välj ett värde i fältet **Egenskap**.</span><span class="sxs-lookup"><span data-stu-id="97f17-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="97f17-146">Markera helgdagar som stängda för upphämtning</span><span class="sxs-lookup"><span data-stu-id="97f17-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="97f17-147">Expandera avsnittet **Lördag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="97f17-148">Välj *Ja* i fältet **Stängd för avhämtning**.</span><span class="sxs-lookup"><span data-stu-id="97f17-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="97f17-149">Expandera avsnittet **Söndag**.</span><span class="sxs-lookup"><span data-stu-id="97f17-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="97f17-150">Välj *Ja* i fältet **Stängd för avhämtning**.</span><span class="sxs-lookup"><span data-stu-id="97f17-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]