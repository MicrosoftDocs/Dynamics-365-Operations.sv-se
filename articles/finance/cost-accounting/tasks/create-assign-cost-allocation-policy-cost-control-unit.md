---
title: Skapa och tilldela en kostnadsallokeringspolicy till en kostnadsstyrenhet
description: Använd den här proceduren när du vill skapa och tilldela en kostnadsallokeringspolicy och motsvarande regler för en kostnadsstyrenhet.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80ec8fed2094025ef31114a229c35bee1cd1033b
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759338"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="c2438-103">Skapa och tilldela en kostnadsallokeringspolicy till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="c2438-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2438-104">Använd den här proceduren när du vill skapa och tilldela en kostnadsallokeringspolicy och motsvarande regler för en kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="c2438-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="c2438-105">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="c2438-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="c2438-106">Skapa en policy</span><span class="sxs-lookup"><span data-stu-id="c2438-106">Create a policy</span></span>
1. <span data-ttu-id="c2438-107">Gå till Kostnadsredovisning > Policyer > Kostnadsfördelningspolicyer.</span><span class="sxs-lookup"><span data-stu-id="c2438-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="c2438-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2438-108">Click New.</span></span>
3. <span data-ttu-id="c2438-109">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="c2438-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="c2438-110">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c2438-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="c2438-111">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="c2438-111">Select Organization.</span></span>  
5. <span data-ttu-id="c2438-112">Ange eller välj ett värde i fältet Statistikdimension.</span><span class="sxs-lookup"><span data-stu-id="c2438-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="c2438-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c2438-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="c2438-114">Skapa allokeringsregler</span><span class="sxs-lookup"><span data-stu-id="c2438-114">Create allocation rules</span></span>
1. <span data-ttu-id="c2438-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2438-115">Click New.</span></span>
2. <span data-ttu-id="c2438-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c2438-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="c2438-117">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c2438-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="c2438-118">Välj Summa i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="c2438-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="c2438-119">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c2438-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="c2438-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2438-120">Click New.</span></span>
7. <span data-ttu-id="c2438-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c2438-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c2438-122">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c2438-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="c2438-123">Välj Summa i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="c2438-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="c2438-124">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c2438-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="c2438-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2438-125">Click New.</span></span>
12. <span data-ttu-id="c2438-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c2438-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="c2438-127">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c2438-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="c2438-128">Välj Summa i fältet Kostnadsbeteende.</span><span class="sxs-lookup"><span data-stu-id="c2438-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="c2438-129">Ange eller välj ett värde i fältet Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c2438-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="c2438-130">Fortsätt tills du har skapat alla regler.</span><span class="sxs-lookup"><span data-stu-id="c2438-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="c2438-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c2438-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="c2438-132">Tilldela policyn till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="c2438-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="c2438-133">Klicka på Policytilldelningar för kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="c2438-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="c2438-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c2438-134">Click New.</span></span>
3. <span data-ttu-id="c2438-135">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c2438-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c2438-136">Ange ett datum i fältet Gäller från redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="c2438-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="c2438-137">Reglerna gäller utifrån datum.</span><span class="sxs-lookup"><span data-stu-id="c2438-137">The rules are date-effective.</span></span> <span data-ttu-id="c2438-138">En användare eller systemet kan se till att reglerna upphör att gälla om det finns en nyare version.</span><span class="sxs-lookup"><span data-stu-id="c2438-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="c2438-139">Ange eller välj ett värde i fältet Kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="c2438-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="c2438-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c2438-140">Click Save.</span></span>

