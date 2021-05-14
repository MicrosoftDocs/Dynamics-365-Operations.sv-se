---
title: Skapa en materialplan för samprodukter
description: Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920739"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="966cb-103">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="966cb-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="966cb-104">Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.</span><span class="sxs-lookup"><span data-stu-id="966cb-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="966cb-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USP2.</span><span class="sxs-lookup"><span data-stu-id="966cb-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="966cb-106">Skapa behov för en samprodukt</span><span class="sxs-lookup"><span data-stu-id="966cb-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="966cb-107">Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.</span><span class="sxs-lookup"><span data-stu-id="966cb-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="966cb-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="966cb-108">Select **New**.</span></span>
1. <span data-ttu-id="966cb-109">Välj **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="966cb-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="966cb-110">I fältet **kundkonto** och ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="966cb-111">Exempel: US-001</span><span class="sxs-lookup"><span data-stu-id="966cb-111">Example: US-001</span></span>  
1. <span data-ttu-id="966cb-112">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-112">Select **OK**.</span></span>
1. <span data-ttu-id="966cb-113">I fältet **Artikelnummer**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="966cb-114">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="966cb-114">Example: P6003</span></span>  
1. <span data-ttu-id="966cb-115">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="966cb-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="966cb-116">Exempel: 50 000</span><span class="sxs-lookup"><span data-stu-id="966cb-116">Example: 50000</span></span>  
1. <span data-ttu-id="966cb-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="966cb-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="966cb-118">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="966cb-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="966cb-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="966cb-119">Close the page.</span></span>
1. <span data-ttu-id="966cb-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="966cb-120">Close the page.</span></span>
1. <span data-ttu-id="966cb-121">Välj **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="966cb-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="966cb-122">Öppna sökningen genom att välja listrutan i fältet **Planera**.</span><span class="sxs-lookup"><span data-stu-id="966cb-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="966cb-123">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="966cb-124">Exempel: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="966cb-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="966cb-125">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="966cb-125">Select **Run**.</span></span>
1. <span data-ttu-id="966cb-126">Utöka eller komprimera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="966cb-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="966cb-127">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="966cb-127">Select **Filter**.</span></span>
1. <span data-ttu-id="966cb-128">Välj raden för **Fält** = *Artikelnummer* i listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="966cb-129">I fältet **Kriterier** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="966cb-130">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="966cb-130">Example: P6003</span></span>  
1. <span data-ttu-id="966cb-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-131">Select **OK**.</span></span>
1. <span data-ttu-id="966cb-132">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-132">Select **OK**.</span></span>
1. <span data-ttu-id="966cb-133">Välj **Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="966cb-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="966cb-134">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="966cb-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="966cb-135">Filtrera till exempel fältet **Artikelnummer** med värdet "P6000".</span><span class="sxs-lookup"><span data-stu-id="966cb-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="966cb-136">Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.</span><span class="sxs-lookup"><span data-stu-id="966cb-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="966cb-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="966cb-138">Välj någon av de rader som returneras av filtret.</span><span class="sxs-lookup"><span data-stu-id="966cb-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="966cb-139">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="966cb-140">Expandera avsnittet **Pegging**.</span><span class="sxs-lookup"><span data-stu-id="966cb-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="966cb-141">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="966cb-142">Den planerade ordern peggas till försäljningsordern för samprodukten.</span><span class="sxs-lookup"><span data-stu-id="966cb-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="966cb-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="966cb-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="966cb-144">Skapa ett andra behov för en samprodukt</span><span class="sxs-lookup"><span data-stu-id="966cb-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="966cb-145">Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.</span><span class="sxs-lookup"><span data-stu-id="966cb-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="966cb-146">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="966cb-146">Select **New**.</span></span>
1. <span data-ttu-id="966cb-147">Välj **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="966cb-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="966cb-148">I fältet **kundkonto** och ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="966cb-149">Exempel: US-001</span><span class="sxs-lookup"><span data-stu-id="966cb-149">Example: US-001</span></span>  
1. <span data-ttu-id="966cb-150">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-150">Select **OK**.</span></span>
1. <span data-ttu-id="966cb-151">I fältet **Artikelnummer**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="966cb-152">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="966cb-152">Example: P6003</span></span>  
1. <span data-ttu-id="966cb-153">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="966cb-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="966cb-154">Exempel: 50 000</span><span class="sxs-lookup"><span data-stu-id="966cb-154">Example: 50000</span></span>  
1. <span data-ttu-id="966cb-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="966cb-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="966cb-156">Skapa en andra materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="966cb-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="966cb-157">Öppna sökningen genom att välja listrutan i fältet **Planera**.</span><span class="sxs-lookup"><span data-stu-id="966cb-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="966cb-158">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="966cb-159">Exempel: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="966cb-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="966cb-160">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="966cb-160">Select **Run**.</span></span>
4. <span data-ttu-id="966cb-161">Utöka eller komprimera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="966cb-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="966cb-162">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="966cb-162">Select **Filter**.</span></span>
6. <span data-ttu-id="966cb-163">Välj raden för **Fält** = *Artikelnummer* i listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="966cb-164">I fältet *Kriterier* skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="966cb-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="966cb-165">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="966cb-165">Example: P6003</span></span>  
8. <span data-ttu-id="966cb-166">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-166">Select **OK**.</span></span>
9. <span data-ttu-id="966cb-167">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="966cb-167">Select **OK**.</span></span>
10. <span data-ttu-id="966cb-168">Välj **Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="966cb-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="966cb-169">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="966cb-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="966cb-170">Filtrera till exempel fältet **Artikelnummer** med värdet "P6000".</span><span class="sxs-lookup"><span data-stu-id="966cb-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="966cb-171">Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.</span><span class="sxs-lookup"><span data-stu-id="966cb-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="966cb-172">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="966cb-173">Välj någon av de rader som returneras av filtret.</span><span class="sxs-lookup"><span data-stu-id="966cb-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="966cb-174">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="966cb-175">Expandera eller komprimera avsnittet **Pegging**.</span><span class="sxs-lookup"><span data-stu-id="966cb-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="966cb-176">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="966cb-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="966cb-177">Den planerade ordern peggas till försäljningsordern för samprodukten.</span><span class="sxs-lookup"><span data-stu-id="966cb-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="966cb-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="966cb-178">Close the page.</span></span>
17. <span data-ttu-id="966cb-179">Välj **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="966cb-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="966cb-180">Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="966cb-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="966cb-181">Välj *Nej* i fältet **Inaktivera samtliga planeringsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="966cb-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="966cb-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="966cb-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]