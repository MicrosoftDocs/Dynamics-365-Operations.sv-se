---
title: Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet
description: Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 946d188652e8f5b45d5c31a5aa0640d5362ef554
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208689"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="b5c36-103">Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="b5c36-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5c36-104">Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe.</span><span class="sxs-lookup"><span data-stu-id="b5c36-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="b5c36-105">Kostnadsrevisorn säkerställer att kostnaderna fördelas till kostnadsställena utifrån det valda allokeringsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="b5c36-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="b5c36-106">En princip och motsvarande regler tilldelas en kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="b5c36-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="b5c36-107">I den här uppgiftsguiden används ett exempel för att lära dig skapa en kostnadsfördelningspolicy och motsvarande regler.</span><span class="sxs-lookup"><span data-stu-id="b5c36-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="b5c36-108">Skapa en policy</span><span class="sxs-lookup"><span data-stu-id="b5c36-108">Create a policy</span></span>
1. <span data-ttu-id="b5c36-109">Gå till Kostnadsredovisning > Policyer > Kostnadsfördelningspolicyer.</span><span class="sxs-lookup"><span data-stu-id="b5c36-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="b5c36-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5c36-110">Click New.</span></span>
3. <span data-ttu-id="b5c36-111">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="b5c36-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="b5c36-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b5c36-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b5c36-113">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="b5c36-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-114">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="b5c36-114">Select Organization.</span></span>  
6. <span data-ttu-id="b5c36-115">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="b5c36-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-116">Välj CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="b5c36-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="b5c36-117">Ange eller välj ett värde i fältet Statistikdimension.</span><span class="sxs-lookup"><span data-stu-id="b5c36-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-118">Välj Statistiska element.</span><span class="sxs-lookup"><span data-stu-id="b5c36-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="b5c36-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5c36-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="b5c36-120">Skapa regler för policyn</span><span class="sxs-lookup"><span data-stu-id="b5c36-120">Create rules for the policy</span></span>
1. <span data-ttu-id="b5c36-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5c36-121">Click New.</span></span>
2. <span data-ttu-id="b5c36-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b5c36-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="b5c36-123">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="b5c36-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-124">Expandera hela hierarkin för att välja 094.</span><span class="sxs-lookup"><span data-stu-id="b5c36-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="b5c36-125">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="b5c36-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-126">Välj Övriga driftkostnader och sedan 605110 Cleaning.</span><span class="sxs-lookup"><span data-stu-id="b5c36-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="b5c36-127">Välj ett alternativ i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="b5c36-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="b5c36-128">Välj Fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="b5c36-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="b5c36-129">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="b5c36-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="b5c36-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5c36-130">Click New.</span></span>
8. <span data-ttu-id="b5c36-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b5c36-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="b5c36-132">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="b5c36-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-133">Expandera hela hierarkin för att välja 094.</span><span class="sxs-lookup"><span data-stu-id="b5c36-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="b5c36-134">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="b5c36-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="b5c36-135">Välj Övriga driftkostnader och sedan 605150 Rent.</span><span class="sxs-lookup"><span data-stu-id="b5c36-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="b5c36-136">Välj ett alternativ i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="b5c36-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="b5c36-137">Välj Fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="b5c36-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="b5c36-138">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="b5c36-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="b5c36-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5c36-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="b5c36-140">Tilldela regler till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="b5c36-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="b5c36-141">Klicka på Policytilldelningar för kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="b5c36-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="b5c36-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5c36-142">Click New.</span></span>
3. <span data-ttu-id="b5c36-143">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b5c36-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b5c36-144">Ange ett datum i fältet Gäller från redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="b5c36-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="b5c36-145">Välj den 1 september som giltigt räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="b5c36-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="b5c36-146">Ange eller välj ett värde i fältet Kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="b5c36-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="b5c36-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5c36-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]