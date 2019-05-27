---
title: Skapa en materialplan för samprodukter
description: Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556010"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="219f7-103">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="219f7-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="219f7-104">Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.</span><span class="sxs-lookup"><span data-stu-id="219f7-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="219f7-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USP2.</span><span class="sxs-lookup"><span data-stu-id="219f7-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="219f7-106">Skapa behov för en samprodukt</span><span class="sxs-lookup"><span data-stu-id="219f7-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="219f7-107">Gå till standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="219f7-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="219f7-108">Klicka på Bearbetning och förfrågan om försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="219f7-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="219f7-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="219f7-109">Click New.</span></span>
4. <span data-ttu-id="219f7-110">Klicka på Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="219f7-110">Click Sales order.</span></span>
5. <span data-ttu-id="219f7-111">Ange ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="219f7-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="219f7-112">Exempel: US-001</span><span class="sxs-lookup"><span data-stu-id="219f7-112">Example: US-001</span></span>  
6. <span data-ttu-id="219f7-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-113">Click OK.</span></span>
7. <span data-ttu-id="219f7-114">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="219f7-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="219f7-115">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="219f7-115">Example: P6003</span></span>  
8. <span data-ttu-id="219f7-116">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="219f7-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="219f7-117">Exempel: 50 000</span><span class="sxs-lookup"><span data-stu-id="219f7-117">Example: 50000</span></span>  
9. <span data-ttu-id="219f7-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="219f7-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="219f7-119">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="219f7-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="219f7-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219f7-120">Close the page.</span></span>
2. <span data-ttu-id="219f7-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219f7-121">Close the page.</span></span>
3. <span data-ttu-id="219f7-122">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="219f7-122">Click Master planning.</span></span>
4. <span data-ttu-id="219f7-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="219f7-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="219f7-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="219f7-125">Exempel: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="219f7-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="219f7-126">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="219f7-126">Click Run.</span></span>
7. <span data-ttu-id="219f7-127">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="219f7-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="219f7-128">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="219f7-128">Click Filter.</span></span>
9. <span data-ttu-id="219f7-129">Välj raden för fält = artikelnummer i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="219f7-130">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="219f7-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="219f7-131">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="219f7-131">Example: P6003</span></span>  
11. <span data-ttu-id="219f7-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-132">Click OK.</span></span>
12. <span data-ttu-id="219f7-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-133">Click OK.</span></span>
13. <span data-ttu-id="219f7-134">Klicka på Planerade order.</span><span class="sxs-lookup"><span data-stu-id="219f7-134">Click Planned orders.</span></span>
14. <span data-ttu-id="219f7-135">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="219f7-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="219f7-136">Filtrera till exempel i fältet Artikelnummer med värdet "P6000".</span><span class="sxs-lookup"><span data-stu-id="219f7-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="219f7-137">Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.</span><span class="sxs-lookup"><span data-stu-id="219f7-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="219f7-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="219f7-139">Välj någon av de rader som returneras av filtret.</span><span class="sxs-lookup"><span data-stu-id="219f7-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="219f7-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="219f7-141">Expandera eller komprimera avsnittet Pegging.</span><span class="sxs-lookup"><span data-stu-id="219f7-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="219f7-142">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="219f7-143">Den planerade ordern peggas till försäljningsordern för samprodukten.</span><span class="sxs-lookup"><span data-stu-id="219f7-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="219f7-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219f7-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="219f7-145">Skapa behov för en samprodukt</span><span class="sxs-lookup"><span data-stu-id="219f7-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="219f7-146">Gå till standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="219f7-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="219f7-147">Klicka på Bearbetning och förfrågan om försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="219f7-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="219f7-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="219f7-148">Click New.</span></span>
4. <span data-ttu-id="219f7-149">Klicka på Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="219f7-149">Click Sales order.</span></span>
5. <span data-ttu-id="219f7-150">Ange ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="219f7-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="219f7-151">Exempel: US-001</span><span class="sxs-lookup"><span data-stu-id="219f7-151">Example: US-001</span></span>  
6. <span data-ttu-id="219f7-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-152">Click OK.</span></span>
7. <span data-ttu-id="219f7-153">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="219f7-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="219f7-154">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="219f7-154">Example: P6003</span></span>  
8. <span data-ttu-id="219f7-155">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="219f7-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="219f7-156">Exempel: 50 000</span><span class="sxs-lookup"><span data-stu-id="219f7-156">Example: 50000</span></span>  
9. <span data-ttu-id="219f7-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="219f7-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="219f7-158">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="219f7-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="219f7-159">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="219f7-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="219f7-160">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="219f7-161">Exempel: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="219f7-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="219f7-162">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="219f7-162">Click Run.</span></span>
4. <span data-ttu-id="219f7-163">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="219f7-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="219f7-164">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="219f7-164">Click Filter.</span></span>
6. <span data-ttu-id="219f7-165">Välj raden för fält = artikelnummer i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="219f7-166">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="219f7-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="219f7-167">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="219f7-167">Example: P6003</span></span>  
8. <span data-ttu-id="219f7-168">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-168">Click OK.</span></span>
9. <span data-ttu-id="219f7-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="219f7-169">Click OK.</span></span>
10. <span data-ttu-id="219f7-170">Klicka på Planerade order.</span><span class="sxs-lookup"><span data-stu-id="219f7-170">Click Planned orders.</span></span>
11. <span data-ttu-id="219f7-171">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="219f7-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="219f7-172">Filtrera till exempel i fältet Artikelnummer med värdet "P6000".</span><span class="sxs-lookup"><span data-stu-id="219f7-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="219f7-173">Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.</span><span class="sxs-lookup"><span data-stu-id="219f7-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="219f7-174">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="219f7-175">Välj någon av de rader som returneras av filtret.</span><span class="sxs-lookup"><span data-stu-id="219f7-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="219f7-176">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="219f7-177">Expandera eller komprimera avsnittet Pegging.</span><span class="sxs-lookup"><span data-stu-id="219f7-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="219f7-178">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="219f7-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="219f7-179">Den planerade ordern peggas till försäljningsordern för samprodukten.</span><span class="sxs-lookup"><span data-stu-id="219f7-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="219f7-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219f7-180">Close the page.</span></span>
17. <span data-ttu-id="219f7-181">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="219f7-181">Click Master planning.</span></span>
18. <span data-ttu-id="219f7-182">Gå till Huvudplanering > Inställningar > Huvudplaneringsparametrar.</span><span class="sxs-lookup"><span data-stu-id="219f7-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="219f7-183">Välj Nej i fältet Inaktivera alla planeringsprocesser.</span><span class="sxs-lookup"><span data-stu-id="219f7-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="219f7-184">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219f7-184">Close the page.</span></span>

