---
title: Skapa kontostrukturer
description: Den här uppgiften leder dig genom stegen för att skapa en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b75ee76a1fb874652415a2174441f629955d763a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448086"
---
# <a name="create-account-structures"></a><span data-ttu-id="e8c28-103">Skapa kontostrukturer</span><span class="sxs-lookup"><span data-stu-id="e8c28-103">Create account structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8c28-104">Den här uppgiften leder dig genom stegen för att skapa en kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="e8c28-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="e8c28-105">Demoföretaget USMF används i stegen.</span><span class="sxs-lookup"><span data-stu-id="e8c28-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="e8c28-106">Gå till **Navigeringsfönster > Moduler > Redovisning > Kontoplaner > Strukturer > Konfigurera kontostrukturer**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="e8c28-107">Klicka på **Ny** i **åtgärdsfönstret** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e8c28-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="e8c28-108">Ange ett namn som beskriver syftet med kontostrukturen i fältet **Kontostruktur**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="e8c28-109">Ange en beskrivning för att ange syftet med kontostrukturen i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="e8c28-110">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-110">Click **Create**.</span></span>
6. <span data-ttu-id="e8c28-111">Klicka på **Lägg till segment** i **Segment och tillåtna värden**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="e8c28-112">I listan Dimensioner väljer du den dimension du vill lägga till i kontostrukturen.</span><span class="sxs-lookup"><span data-stu-id="e8c28-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="e8c28-113">Klicka på **Lägg till segment** i slutet av listan.</span><span class="sxs-lookup"><span data-stu-id="e8c28-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="e8c28-114">Upprepa steg 6 till 9 efter behov.</span><span class="sxs-lookup"><span data-stu-id="e8c28-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="e8c28-115">I avsnittet **Information om tillåtna värden** väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="e8c28-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="e8c28-116">Klicka till exempel i fältet **Huvudkonto**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="e8c28-117">Välj ett alternativ i fältet **Operator**, till exempel ligger mellan eller inkluderar.</span><span class="sxs-lookup"><span data-stu-id="e8c28-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="e8c28-118">Ange ett värde i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="e8c28-119">Exempelvis 600000.</span><span class="sxs-lookup"><span data-stu-id="e8c28-119">For example, 600000.</span></span>  
13. <span data-ttu-id="e8c28-120">Skriv ett värde i fältet **via**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-120">In the **through** field, type a value.</span></span> <span data-ttu-id="e8c28-121">Exempelvis 699999.</span><span class="sxs-lookup"><span data-stu-id="e8c28-121">For example, 699999.</span></span>  
14. <span data-ttu-id="e8c28-122">Klicka på **Använd** i avsnittet **Information om tillåtna värden**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="e8c28-123">Upprepa steg 10 till 15 efter behov.</span><span class="sxs-lookup"><span data-stu-id="e8c28-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="e8c28-124">Klicka på **Lägg till nya kriterier** i avsnittet **Information om tillåtna värden**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="e8c28-125">Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.</span><span class="sxs-lookup"><span data-stu-id="e8c28-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="e8c28-126">Ange ett värde i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="e8c28-127">Exempelvis 033.</span><span class="sxs-lookup"><span data-stu-id="e8c28-127">For example, 033.</span></span>  
19. <span data-ttu-id="e8c28-128">Skriv ett värde i fältet **via**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-128">In the **through** field, type a value.</span></span> <span data-ttu-id="e8c28-129">Exempelvis 034.</span><span class="sxs-lookup"><span data-stu-id="e8c28-129">For example, 034.</span></span>  
20. <span data-ttu-id="e8c28-130">Klicka på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-130">Click **Apply**.</span></span>
21. <span data-ttu-id="e8c28-131">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="e8c28-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="e8c28-132">Till exempel Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="e8c28-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="e8c28-133">Skriv ett värde i fältet **CostCenter**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="e8c28-134">Till exempel 007..021.</span><span class="sxs-lookup"><span data-stu-id="e8c28-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="e8c28-135">Klicka på **Lägg till** i **Segment och tillåtna värden**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="e8c28-136">Ange ett värde i fältet **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="e8c28-137">Till exempel 600000..699999</span><span class="sxs-lookup"><span data-stu-id="e8c28-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="e8c28-138">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="e8c28-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="e8c28-139">Till exempel Avdelning.</span><span class="sxs-lookup"><span data-stu-id="e8c28-139">For example, Department.</span></span>  
26. <span data-ttu-id="e8c28-140">Ange ett värde i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="e8c28-140">In the Department field, type a value.</span></span> <span data-ttu-id="e8c28-141">Exempelvis 032.</span><span class="sxs-lookup"><span data-stu-id="e8c28-141">For example, 032.</span></span>  
27. <span data-ttu-id="e8c28-142">Skriv ett värde i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="e8c28-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="e8c28-143">Exempelvis 086.</span><span class="sxs-lookup"><span data-stu-id="e8c28-143">For example, 086.</span></span>  
28. <span data-ttu-id="e8c28-144">Klicka på **Validera** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="e8c28-145">Klicka på **Aktivera** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="e8c28-146">Klicka på **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="e8c28-146">Click **Activate**.</span></span>

