---
title: Reduceringsnycklar
description: "Den här artikeln ger exempel som visar hur du ställer in en reduceringsnyckel. Den innehåller information om de olika reduceringsnyckelinställningarna och resultaten av varje nyckel. Du kan använda en reduceringsnyckel om du vill ange hur du ska minska prognosbehoven."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506ca3aac7ad271ca7472f3b74627e94d97a74ee
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="reduction-keys"></a><span data-ttu-id="dcede-105">Reduceringsnycklar</span><span class="sxs-lookup"><span data-stu-id="dcede-105">Reduction keys</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dcede-106">Den här artikeln ger exempel som visar hur du ställer in en reduceringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="dcede-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="dcede-107">Den innehåller information om de olika reduceringsnyckelinställningarna och resultaten av varje nyckel.</span><span class="sxs-lookup"><span data-stu-id="dcede-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="dcede-108">Du kan använda en reduceringsnyckel om du vill ange hur du ska minska prognosbehoven.</span><span class="sxs-lookup"><span data-stu-id="dcede-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="dcede-109">Exempel 1: Procent - reduceringsnyckel för prognosreduceringsprincip</span><span class="sxs-lookup"><span data-stu-id="dcede-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="dcede-110">Detta exempel visar hur en reduceringsnyckel reducerar behoven av efterfrågeprognos enligt procentsatserna och de perioder som definieras av reduceringsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="dcede-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1.  <span data-ttu-id="dcede-111">Ange följande rader på sidan **Reduceringsnycklar**.</span><span class="sxs-lookup"><span data-stu-id="dcede-111">On the **Reduction keys** page, set up the following lines.</span></span>
    | <span data-ttu-id="dcede-112">Växel</span><span class="sxs-lookup"><span data-stu-id="dcede-112">Change</span></span> | <span data-ttu-id="dcede-113">Enhet</span><span class="sxs-lookup"><span data-stu-id="dcede-113">Unit</span></span>  | <span data-ttu-id="dcede-114">Procent</span><span class="sxs-lookup"><span data-stu-id="dcede-114">Percent</span></span> |
    |--------|-------|---------|
    | <span data-ttu-id="dcede-115">1</span><span class="sxs-lookup"><span data-stu-id="dcede-115">1</span></span>      | <span data-ttu-id="dcede-116">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-116">Month</span></span> | <span data-ttu-id="dcede-117">100</span><span class="sxs-lookup"><span data-stu-id="dcede-117">100</span></span>     |
    | <span data-ttu-id="dcede-118">2</span><span class="sxs-lookup"><span data-stu-id="dcede-118">2</span></span>      | <span data-ttu-id="dcede-119">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-119">Month</span></span> | <span data-ttu-id="dcede-120">75</span><span class="sxs-lookup"><span data-stu-id="dcede-120">75</span></span>      |
    | <span data-ttu-id="dcede-121">3</span><span class="sxs-lookup"><span data-stu-id="dcede-121">3</span></span>      | <span data-ttu-id="dcede-122">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-122">Month</span></span> | <span data-ttu-id="dcede-123">50</span><span class="sxs-lookup"><span data-stu-id="dcede-123">50</span></span>      |
    | <span data-ttu-id="dcede-124">4</span><span class="sxs-lookup"><span data-stu-id="dcede-124">4</span></span>      | <span data-ttu-id="dcede-125">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-125">Month</span></span> | <span data-ttu-id="dcede-126">25</span><span class="sxs-lookup"><span data-stu-id="dcede-126">25</span></span>      |

2.  <span data-ttu-id="dcede-127">Länka reduceringsnyckeln till artikelns täckningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="dcede-127">Link the reduction key to the item's coverage group.</span></span>
3.  <span data-ttu-id="dcede-128">På sidan **Huvudplaner** i fältet **Reduceringsprincip** väljer du **Procent - reduceringsnyckel**.</span><span class="sxs-lookup"><span data-stu-id="dcede-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4.  <span data-ttu-id="dcede-129">Skapa en efterfrågeprognos på 1 000 enheter per månad.</span><span class="sxs-lookup"><span data-stu-id="dcede-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="dcede-130">Om du kör prognosplanering den 1 januari förbrukas kraven på efterfrågeprognos enligt de procentsatser som du ställer in på sidan **Reduceringsnycklar**.</span><span class="sxs-lookup"><span data-stu-id="dcede-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="dcede-131">Följande behovskvantiteter överförs till huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="dcede-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="dcede-132">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-132">Month</span></span>                | <span data-ttu-id="dcede-133">Obligatoriskt antal enheter</span><span class="sxs-lookup"><span data-stu-id="dcede-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="dcede-134">Januari</span><span class="sxs-lookup"><span data-stu-id="dcede-134">January</span></span>              | <span data-ttu-id="dcede-135">0</span><span class="sxs-lookup"><span data-stu-id="dcede-135">0</span></span>                         |
| <span data-ttu-id="dcede-136">Februari</span><span class="sxs-lookup"><span data-stu-id="dcede-136">February</span></span>             | <span data-ttu-id="dcede-137">250</span><span class="sxs-lookup"><span data-stu-id="dcede-137">250</span></span>                       |
| <span data-ttu-id="dcede-138">Mars</span><span class="sxs-lookup"><span data-stu-id="dcede-138">March</span></span>                | <span data-ttu-id="dcede-139">500</span><span class="sxs-lookup"><span data-stu-id="dcede-139">500</span></span>                       |
| <span data-ttu-id="dcede-140">april</span><span class="sxs-lookup"><span data-stu-id="dcede-140">April</span></span>                | <span data-ttu-id="dcede-141">750</span><span class="sxs-lookup"><span data-stu-id="dcede-141">750</span></span>                       |
| <span data-ttu-id="dcede-142">Maj - december</span><span class="sxs-lookup"><span data-stu-id="dcede-142">May through December</span></span> | <span data-ttu-id="dcede-143">1 000</span><span class="sxs-lookup"><span data-stu-id="dcede-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="dcede-144">Exempel 2: Transaktioner - reduceringsnyckel för prognosreduceringsprincip</span><span class="sxs-lookup"><span data-stu-id="dcede-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="dcede-145">Detta exempel visar hur aktuella order som inträffar under de perioder som definieras av reduceringsnyckeln reducerar behoven av efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="dcede-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="dcede-146">På sidan **Huvudplaner** i fältet **Reduceringsprincip** väljer du **Transaktioner - reduceringsnyckel**.</span><span class="sxs-lookup"><span data-stu-id="dcede-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="dcede-147">Följande försäljningsorder finns den 1 januari.</span><span class="sxs-lookup"><span data-stu-id="dcede-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="dcede-148">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-148">Month</span></span>    | <span data-ttu-id="dcede-149">Beställt antal enheter</span><span class="sxs-lookup"><span data-stu-id="dcede-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="dcede-150">Januari</span><span class="sxs-lookup"><span data-stu-id="dcede-150">January</span></span>  | <span data-ttu-id="dcede-151">956</span><span class="sxs-lookup"><span data-stu-id="dcede-151">956</span></span>                      |
| <span data-ttu-id="dcede-152">Februari</span><span class="sxs-lookup"><span data-stu-id="dcede-152">February</span></span> | <span data-ttu-id="dcede-153">1 176</span><span class="sxs-lookup"><span data-stu-id="dcede-153">1,176</span></span>                    |
| <span data-ttu-id="dcede-154">Mars</span><span class="sxs-lookup"><span data-stu-id="dcede-154">March</span></span>    | <span data-ttu-id="dcede-155">451</span><span class="sxs-lookup"><span data-stu-id="dcede-155">451</span></span>                      |
| <span data-ttu-id="dcede-156">april</span><span class="sxs-lookup"><span data-stu-id="dcede-156">April</span></span>    | <span data-ttu-id="dcede-157">119</span><span class="sxs-lookup"><span data-stu-id="dcede-157">119</span></span>                      |

<span data-ttu-id="dcede-158">Med samma försäljningsprognos på 1 000 enheter per månad överförs följande behovskvantiteter till huvudplanen:</span><span class="sxs-lookup"><span data-stu-id="dcede-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="dcede-159">Månad</span><span class="sxs-lookup"><span data-stu-id="dcede-159">Month</span></span>                | <span data-ttu-id="dcede-160">Obligatoriskt antal enheter</span><span class="sxs-lookup"><span data-stu-id="dcede-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="dcede-161">Januari</span><span class="sxs-lookup"><span data-stu-id="dcede-161">January</span></span>              | <span data-ttu-id="dcede-162">44</span><span class="sxs-lookup"><span data-stu-id="dcede-162">44</span></span>                        |
| <span data-ttu-id="dcede-163">Februari</span><span class="sxs-lookup"><span data-stu-id="dcede-163">February</span></span>             | <span data-ttu-id="dcede-164">0</span><span class="sxs-lookup"><span data-stu-id="dcede-164">0</span></span>                         |
| <span data-ttu-id="dcede-165">Mars</span><span class="sxs-lookup"><span data-stu-id="dcede-165">March</span></span>                | <span data-ttu-id="dcede-166">549</span><span class="sxs-lookup"><span data-stu-id="dcede-166">549</span></span>                       |
| <span data-ttu-id="dcede-167">april</span><span class="sxs-lookup"><span data-stu-id="dcede-167">April</span></span>                | <span data-ttu-id="dcede-168">881</span><span class="sxs-lookup"><span data-stu-id="dcede-168">881</span></span>                       |
| <span data-ttu-id="dcede-169">Maj - december</span><span class="sxs-lookup"><span data-stu-id="dcede-169">May through December</span></span> | <span data-ttu-id="dcede-170">1 000</span><span class="sxs-lookup"><span data-stu-id="dcede-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="dcede-171">Exempel 3: Transaktioner - dynamisk period för prognosreduceringsprincip</span><span class="sxs-lookup"><span data-stu-id="dcede-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="dcede-172">I de flesta fall ställs systemen in så att transaktioner minskar efterfrågeprognosen inom specifika detaljprognosperioder: veckor, månader och så vidare.</span><span class="sxs-lookup"><span data-stu-id="dcede-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="dcede-173">Dessa perioder definieras i reduceringsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="dcede-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="dcede-174">Men tiden mellan två efterfrågeprognosrader kan också *antyda* en period.</span><span class="sxs-lookup"><span data-stu-id="dcede-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1.  <span data-ttu-id="dcede-175">Skapa en efterfrågeprognos för följande datum och kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="dcede-175">Create a demand forecast for the following dates and quantities.</span></span>
    | <span data-ttu-id="dcede-176">Datum</span><span class="sxs-lookup"><span data-stu-id="dcede-176">Date</span></span>       | <span data-ttu-id="dcede-177">Efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="dcede-177">Demand forecast</span></span> |
    |------------|-----------------|
    | <span data-ttu-id="dcede-178">1 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-178">January 1</span></span>  | <span data-ttu-id="dcede-179">1 000</span><span class="sxs-lookup"><span data-stu-id="dcede-179">1,000</span></span>           |
    | <span data-ttu-id="dcede-180">5 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-180">January 5</span></span>  | <span data-ttu-id="dcede-181">500</span><span class="sxs-lookup"><span data-stu-id="dcede-181">500</span></span>             |
    | <span data-ttu-id="dcede-182">12 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-182">January 12</span></span> | <span data-ttu-id="dcede-183">1 000</span><span class="sxs-lookup"><span data-stu-id="dcede-183">1,000</span></span>           |

    <span data-ttu-id="dcede-184">I denna prognos finns det inte en tydlig period mellan prognosdata: mellan de första och andra data finns det endast en tidsperiod på 4 dagar, och mellan de andra och tredje data finns det endast en tidsperiod på 1 dag.</span><span class="sxs-lookup"><span data-stu-id="dcede-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="dcede-185">Dessa olika tidsperioder är de dynamiska perioderna.</span><span class="sxs-lookup"><span data-stu-id="dcede-185">These various spans are the dynamic periods.</span></span>
2.  <span data-ttu-id="dcede-186">Skapa försäljningsorderrader enligt följande.</span><span class="sxs-lookup"><span data-stu-id="dcede-186">Create sales order lines as follows.</span></span>
    | <span data-ttu-id="dcede-187">Datum</span><span class="sxs-lookup"><span data-stu-id="dcede-187">Date</span></span>                             | <span data-ttu-id="dcede-188">Försäljningsorderns kvantitet</span><span class="sxs-lookup"><span data-stu-id="dcede-188">Sales order quantity</span></span> |
    |----------------------------------|----------------------|
    | <span data-ttu-id="dcede-189">15 december föregående år</span><span class="sxs-lookup"><span data-stu-id="dcede-189">December 15 in the previous year</span></span> | <span data-ttu-id="dcede-190">500</span><span class="sxs-lookup"><span data-stu-id="dcede-190">500</span></span>                  |
    | <span data-ttu-id="dcede-191">3 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-191">January 3</span></span>                        | <span data-ttu-id="dcede-192">100</span><span class="sxs-lookup"><span data-stu-id="dcede-192">100</span></span>                  |
    | <span data-ttu-id="dcede-193">10 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-193">January 10</span></span>                       | <span data-ttu-id="dcede-194">200</span><span class="sxs-lookup"><span data-stu-id="dcede-194">200</span></span>                  |

<span data-ttu-id="dcede-195">Prognosen reduceras enligt följande:</span><span class="sxs-lookup"><span data-stu-id="dcede-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="dcede-196">Den första försäljningsordern sker inte inom någon period, så den kommer inte att reducera prognosen.</span><span class="sxs-lookup"><span data-stu-id="dcede-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="dcede-197">Den andra försäljningsordern sker mellan 1 januari och 5 januari, så den ska reducera prognosen för 1 januari med 100.</span><span class="sxs-lookup"><span data-stu-id="dcede-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="dcede-198">Den tredje försäljningsordern sker mellan 5 januari och 12 januari, så den ska reducera prognosen för 5 januari med 200.</span><span class="sxs-lookup"><span data-stu-id="dcede-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="dcede-199">Följande planerade order skapas för att uppfylla prognosen.</span><span class="sxs-lookup"><span data-stu-id="dcede-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="dcede-200">Efterfrågeprognosdatum</span><span class="sxs-lookup"><span data-stu-id="dcede-200">Demand forecast date</span></span> | <span data-ttu-id="dcede-201">Reducerad kvantitet</span><span class="sxs-lookup"><span data-stu-id="dcede-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="dcede-202">1 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-202">January 1</span></span>            | <span data-ttu-id="dcede-203">900</span><span class="sxs-lookup"><span data-stu-id="dcede-203">900</span></span>              |
| <span data-ttu-id="dcede-204">5 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-204">January 5</span></span>            | <span data-ttu-id="dcede-205">300</span><span class="sxs-lookup"><span data-stu-id="dcede-205">300</span></span>              |
| <span data-ttu-id="dcede-206">12 januari</span><span class="sxs-lookup"><span data-stu-id="dcede-206">January 12</span></span>           | <span data-ttu-id="dcede-207">1 000</span><span class="sxs-lookup"><span data-stu-id="dcede-207">1,000</span></span>            |

<span data-ttu-id="dcede-208">Här följer en sammanfattning av **Transaktioner - dynamisk period** för reducering:</span><span class="sxs-lookup"><span data-stu-id="dcede-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="dcede-209">Prognosbehoven reduceras med de verkliga ordertransaktionerna som inträffar under den dynamiska perioden.</span><span class="sxs-lookup"><span data-stu-id="dcede-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="dcede-210">Den dynamiska perioden omfattar de aktuella prognosdatumen och slutar i början av nästa prognos.</span><span class="sxs-lookup"><span data-stu-id="dcede-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="dcede-211">Den här metoden använder inte eller kräver en reduceringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="dcede-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="dcede-212">När det här alternativet används, sker följande beteende:</span><span class="sxs-lookup"><span data-stu-id="dcede-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="dcede-213">Om prognosen reduceras fullständigt, blir prognosbehoven för den aktuella prognosen 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="dcede-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="dcede-214">Om det inte finns någon framtida prognos, kommer prognosbehov från sista prognosen att reduceras.</span><span class="sxs-lookup"><span data-stu-id="dcede-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="dcede-215">Tidsgränser ingår i prognosförminskningsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="dcede-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="dcede-216">Positiva dagar ingår i beräkningen av prognosreducering.</span><span class="sxs-lookup"><span data-stu-id="dcede-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="dcede-217">Om verkliga ordertransaktioner överskrider prognosbehoven, förs resten av transaktionerna inte framåt till nästa prognosperiod.</span><span class="sxs-lookup"><span data-stu-id="dcede-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="see-also"></a><span data-ttu-id="dcede-218">Se även</span><span class="sxs-lookup"><span data-stu-id="dcede-218">See also</span></span>
--------

[<span data-ttu-id="dcede-219">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="dcede-219">Master plans</span></span>](master-plans.md)




