---
title: Skapa en produktnummernomenklatur för konfigurerade produktvarianter
description: I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f75d7e493255b9c09c10b121f388854861cb0fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437665"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="4b33c-103">Skapa en produktnummernomenklatur för konfigurerade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="4b33c-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4b33c-104">I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall.</span><span class="sxs-lookup"><span data-stu-id="4b33c-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="4b33c-105">I den här proceduren visas även hur du kan skapa en konfigurationsnomenklatur för en modellkomponent för en produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4b33c-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="4b33c-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="4b33c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4b33c-107">Den nya produktnummernomenklaturen tilldelas produktmallen D0004.</span><span class="sxs-lookup"><span data-stu-id="4b33c-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="4b33c-108">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="4b33c-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="4b33c-109">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="4b33c-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="4b33c-110">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="4b33c-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="4b33c-111">Klicka på Product nomenclature.</span><span class="sxs-lookup"><span data-stu-id="4b33c-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="4b33c-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4b33c-112">Click New.</span></span>
4. <span data-ttu-id="4b33c-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4b33c-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4b33c-114">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4b33c-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="4b33c-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-115">Click Add.</span></span>
7. <span data-ttu-id="4b33c-116">Klicka på Product master number.</span><span class="sxs-lookup"><span data-stu-id="4b33c-116">Click Product master number.</span></span>
8. <span data-ttu-id="4b33c-117">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-117">Click Add.</span></span>
9. <span data-ttu-id="4b33c-118">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="4b33c-118">Click Text constant.</span></span>
10. <span data-ttu-id="4b33c-119">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="4b33c-120">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="4b33c-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="4b33c-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-121">Click Add.</span></span>
13. <span data-ttu-id="4b33c-122">Klicka på Configuration.</span><span class="sxs-lookup"><span data-stu-id="4b33c-122">Click Configuration.</span></span>
14. <span data-ttu-id="4b33c-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="4b33c-124">Tilldela produktnummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="4b33c-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="4b33c-125">Klicka på Product masters.</span><span class="sxs-lookup"><span data-stu-id="4b33c-125">Click Product masters.</span></span>
2. <span data-ttu-id="4b33c-126">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="4b33c-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4b33c-127">Filtrera till exempel fältet Product number med värdet "D".</span><span class="sxs-lookup"><span data-stu-id="4b33c-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="4b33c-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4b33c-129">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="4b33c-129">Click Edit.</span></span>
5. <span data-ttu-id="4b33c-130">Välj Yes i fältet Use nomenclature.</span><span class="sxs-lookup"><span data-stu-id="4b33c-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="4b33c-131">I nomenklatursfältet Product variant number anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="4b33c-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="4b33c-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-132">Close the page.</span></span>
8. <span data-ttu-id="4b33c-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="4b33c-134">Skapa en nomenklatur för en komponent i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="4b33c-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="4b33c-135">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4b33c-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="4b33c-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4b33c-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4b33c-138">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="4b33c-138">Click Edit.</span></span>
5. <span data-ttu-id="4b33c-139">Välj Yes i fältet Use configuration nomenclature.</span><span class="sxs-lookup"><span data-stu-id="4b33c-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="4b33c-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-140">Click Add.</span></span>
7. <span data-ttu-id="4b33c-141">Klicka på Attribute value.</span><span class="sxs-lookup"><span data-stu-id="4b33c-141">Click Attribute value.</span></span>
8. <span data-ttu-id="4b33c-142">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="4b33c-143">Ange eller välj ett värde i fältet Attribute.</span><span class="sxs-lookup"><span data-stu-id="4b33c-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="4b33c-144">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-144">Click Add.</span></span>
11. <span data-ttu-id="4b33c-145">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="4b33c-145">Click Text constant.</span></span>
12. <span data-ttu-id="4b33c-146">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="4b33c-147">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="4b33c-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="4b33c-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-148">Click Add.</span></span>
15. <span data-ttu-id="4b33c-149">Klicka på Attribute value.</span><span class="sxs-lookup"><span data-stu-id="4b33c-149">Click Attribute value.</span></span>
16. <span data-ttu-id="4b33c-150">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="4b33c-151">Ange eller välj ett värde i fältet Attribute.</span><span class="sxs-lookup"><span data-stu-id="4b33c-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="4b33c-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-152">Click Add.</span></span>
19. <span data-ttu-id="4b33c-153">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="4b33c-153">Click Text constant.</span></span>
20. <span data-ttu-id="4b33c-154">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="4b33c-155">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="4b33c-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="4b33c-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-156">Click Add.</span></span>
23. <span data-ttu-id="4b33c-157">Klicka på Attribute value.</span><span class="sxs-lookup"><span data-stu-id="4b33c-157">Click Attribute value.</span></span>
24. <span data-ttu-id="4b33c-158">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="4b33c-159">Ange eller välj ett värde i fältet Attribute.</span><span class="sxs-lookup"><span data-stu-id="4b33c-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="4b33c-160">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-160">Click Add.</span></span>
27. <span data-ttu-id="4b33c-161">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="4b33c-161">Click Text constant.</span></span>
28. <span data-ttu-id="4b33c-162">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="4b33c-163">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="4b33c-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="4b33c-164">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-164">Click Add.</span></span>
31. <span data-ttu-id="4b33c-165">Klicka på Attribute value.</span><span class="sxs-lookup"><span data-stu-id="4b33c-165">Click Attribute value.</span></span>
32. <span data-ttu-id="4b33c-166">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="4b33c-167">Ange eller välj ett värde i fältet Attribute.</span><span class="sxs-lookup"><span data-stu-id="4b33c-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="4b33c-168">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-168">Click Add.</span></span>
35. <span data-ttu-id="4b33c-169">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="4b33c-169">Click Text constant.</span></span>
36. <span data-ttu-id="4b33c-170">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="4b33c-171">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="4b33c-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="4b33c-172">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4b33c-172">Click Add.</span></span>
39. <span data-ttu-id="4b33c-173">Klicka på Number sequence value.</span><span class="sxs-lookup"><span data-stu-id="4b33c-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="4b33c-174">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="4b33c-175">I fältet Number sequence anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="4b33c-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="4b33c-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-176">Close the page.</span></span>
43. <span data-ttu-id="4b33c-177">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-177">Close the page.</span></span>
44. <span data-ttu-id="4b33c-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4b33c-178">Close the page.</span></span>

