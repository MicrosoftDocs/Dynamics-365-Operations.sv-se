--- 
title: "Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet"
description: "Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe."
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 46ba6322f2cea7828033c214502accdf73f073be
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="0639c-103">Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="0639c-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0639c-104">Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe.</span><span class="sxs-lookup"><span data-stu-id="0639c-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="0639c-105">Kostnadsrevisorn säkerställer att kostnaderna fördelas till kostnadsställena utifrån det valda allokeringsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="0639c-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="0639c-106">En princip och motsvarande regler tilldelas en kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="0639c-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="0639c-107">I den här uppgiftsguiden används ett exempel för att lära dig skapa en kostnadsfördelningspolicy och motsvarande regler.</span><span class="sxs-lookup"><span data-stu-id="0639c-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="0639c-108">Skapa en policy</span><span class="sxs-lookup"><span data-stu-id="0639c-108">Create a policy</span></span>
1. <span data-ttu-id="0639c-109">Gå till Kostnadsredovisning > Policyer > Kostnadsfördelningspolicyer.</span><span class="sxs-lookup"><span data-stu-id="0639c-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="0639c-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0639c-110">Click New.</span></span>
3. <span data-ttu-id="0639c-111">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="0639c-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="0639c-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="0639c-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0639c-113">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="0639c-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-114">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="0639c-114">Select Organization.</span></span>  
6. <span data-ttu-id="0639c-115">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="0639c-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-116">Välj CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="0639c-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="0639c-117">Ange eller välj ett värde i fältet Statistikdimension.</span><span class="sxs-lookup"><span data-stu-id="0639c-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-118">Välj Statistiska element.</span><span class="sxs-lookup"><span data-stu-id="0639c-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="0639c-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0639c-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="0639c-120">Skapa regler för policyn</span><span class="sxs-lookup"><span data-stu-id="0639c-120">Create rules for the policy</span></span>
1. <span data-ttu-id="0639c-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0639c-121">Click New.</span></span>
2. <span data-ttu-id="0639c-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0639c-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="0639c-123">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="0639c-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-124">Expandera hela hierarkin för att välja 094.</span><span class="sxs-lookup"><span data-stu-id="0639c-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="0639c-125">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="0639c-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-126">Välj Övriga driftkostnader och sedan 605110 Cleaning.</span><span class="sxs-lookup"><span data-stu-id="0639c-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="0639c-127">Välj ett alternativ i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="0639c-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="0639c-128">Välj Fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="0639c-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="0639c-129">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="0639c-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="0639c-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0639c-130">Click New.</span></span>
8. <span data-ttu-id="0639c-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0639c-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0639c-132">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="0639c-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-133">Expandera hela hierarkin för att välja 094.</span><span class="sxs-lookup"><span data-stu-id="0639c-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="0639c-134">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="0639c-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0639c-135">Välj Övriga driftkostnader och sedan 605150 Rent.</span><span class="sxs-lookup"><span data-stu-id="0639c-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="0639c-136">Välj ett alternativ i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="0639c-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="0639c-137">Välj Fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="0639c-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="0639c-138">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="0639c-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="0639c-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0639c-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="0639c-140">Tilldela regler till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="0639c-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="0639c-141">Klicka på Policytilldelningar för kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="0639c-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="0639c-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0639c-142">Click New.</span></span>
3. <span data-ttu-id="0639c-143">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0639c-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0639c-144">Ange ett datum i fältet Gäller från redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="0639c-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="0639c-145">Välj den 1 september som giltigt räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="0639c-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="0639c-146">Ange eller välj ett värde i fältet Kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="0639c-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="0639c-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0639c-147">Click Save.</span></span>


