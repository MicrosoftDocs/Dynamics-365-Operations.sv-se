---
title: "Alternativ för hela belopp och intervallberäkning för momskoder"
description: "Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bab0f6ca21f4216b70cccf24f5781e0dbf48b7f8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="a0941-103">Alternativ för hela belopp och intervallberäkning för momskoder</span><span class="sxs-lookup"><span data-stu-id="a0941-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]



<span data-ttu-id="a0941-104">Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp.</span><span class="sxs-lookup"><span data-stu-id="a0941-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="a0941-105">Du kan ställa in en momskod som ska beräknas baserat på ett helt belopp eller ett intervallbelopp.</span><span class="sxs-lookup"><span data-stu-id="a0941-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="a0941-106">På sidan Momskoder använder du fältet Beräkningsmetod på snabbfliken Beräkning för att välja hur du beräknar en momskod.</span><span class="sxs-lookup"><span data-stu-id="a0941-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
-   <span data-ttu-id="a0941-107">Hela belopp – Momssatsen tillämpas för hela det momspliktiga beloppet.</span><span class="sxs-lookup"><span data-stu-id="a0941-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
-   <span data-ttu-id="a0941-108">Intervall – Det momspliktiga beloppet delas upp i delar, och varje del ligger inom ett intervall som har en specifik momssats.</span><span class="sxs-lookup"><span data-stu-id="a0941-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="a0941-109">Den del av beloppet som ligger inom ett angivet intervall beläggs med moms i enlighet med momssatsen för intervallet.</span><span class="sxs-lookup"><span data-stu-id="a0941-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="a0941-110">Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="a0941-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
> [!NOTE]                                                                                                                              
> <span data-ttu-id="a0941-111">Alternativet Intervall är bara tillgängliga när du väljer i fältet Rad i fältet Beräkningsmetod i området Moms på sidan Redovisningparameter.</span><span class="sxs-lookup"><span data-stu-id="a0941-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="a0941-112">Intervall ställs in på sidan Momskodvärden, genom att ange gränsbelopp för minimum och maximum per momssats.</span><span class="sxs-lookup"><span data-stu-id="a0941-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="a0941-113">För att moms ska beräknas på alla momspliktiga belopp, oavsett vilken beräkningsmetod som har valts, måste intervallen vara utformade i enlighet med följande regler:</span><span class="sxs-lookup"><span data-stu-id="a0941-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="a0941-114">Det första intervallet måste ha en minimigräns på noll.</span><span class="sxs-lookup"><span data-stu-id="a0941-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="a0941-115">Det sista intervallet måste ha en maximal gräns på noll, vilket anger oändlighet.</span><span class="sxs-lookup"><span data-stu-id="a0941-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="a0941-116">Den maximala gränsen i ett intervall måste vara minimumgränsen i nästa intervall.</span><span class="sxs-lookup"><span data-stu-id="a0941-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="a0941-117">Om ett belopp är den maximala gränsen för föregående intervall och den minimala gränsen i nästa intervall används momssatsen från det första intervallet för beloppet.</span><span class="sxs-lookup"><span data-stu-id="a0941-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="a0941-118">Om ett belopp ligger utanför de intervall som har definierats av övre och nedre gränser används momssatsen noll.</span><span class="sxs-lookup"><span data-stu-id="a0941-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="a0941-119">Exempel: Beräkningsmetoden för hela beloppet</span><span class="sxs-lookup"><span data-stu-id="a0941-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="a0941-120">På sidan för momskodvärden ställs momssatser in med följande intervall:</span><span class="sxs-lookup"><span data-stu-id="a0941-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>
|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="a0941-121">**Minimigräns**</span><span class="sxs-lookup"><span data-stu-id="a0941-121">**Minimum limit**</span></span> | <span data-ttu-id="a0941-122">**Maximigräns**</span><span class="sxs-lookup"><span data-stu-id="a0941-122">**Maximum limit**</span></span> | <span data-ttu-id="a0941-123">**Momssats**</span><span class="sxs-lookup"><span data-stu-id="a0941-123">**Tax rate**</span></span> |
| <span data-ttu-id="a0941-124">0,00</span><span class="sxs-lookup"><span data-stu-id="a0941-124">0.00</span></span>              | <span data-ttu-id="a0941-125">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-125">50.00</span></span>             | <span data-ttu-id="a0941-126">30 %</span><span class="sxs-lookup"><span data-stu-id="a0941-126">30%</span></span>          |
| <span data-ttu-id="a0941-127">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-127">50.00</span></span>             | <span data-ttu-id="a0941-128">100,00</span><span class="sxs-lookup"><span data-stu-id="a0941-128">100.00</span></span>            | <span data-ttu-id="a0941-129">20 %</span><span class="sxs-lookup"><span data-stu-id="a0941-129">20%</span></span>          |
| <span data-ttu-id="a0941-130">100,00</span><span class="sxs-lookup"><span data-stu-id="a0941-130">100.00</span></span>            | <span data-ttu-id="a0941-131">0,00</span><span class="sxs-lookup"><span data-stu-id="a0941-131">0.00</span></span>              | <span data-ttu-id="a0941-132">10 %</span><span class="sxs-lookup"><span data-stu-id="a0941-132">10%</span></span>          |

<span data-ttu-id="a0941-133">Momsen beräknas till hela momspliktiga beloppet.</span><span class="sxs-lookup"><span data-stu-id="a0941-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="a0941-134">Momspliktigt belopp (pris)</span><span class="sxs-lookup"><span data-stu-id="a0941-134">Taxable amount (price)</span></span> | <span data-ttu-id="a0941-135">Beräkning</span><span class="sxs-lookup"><span data-stu-id="a0941-135">Calculation</span></span>    | <span data-ttu-id="a0941-136">Moms</span><span class="sxs-lookup"><span data-stu-id="a0941-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="a0941-137">35,00</span><span class="sxs-lookup"><span data-stu-id="a0941-137">35.00</span></span>                  | <span data-ttu-id="a0941-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="a0941-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="a0941-139">10,50</span><span class="sxs-lookup"><span data-stu-id="a0941-139">10.50</span></span>     |
| <span data-ttu-id="a0941-140">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-140">50.00</span></span>                  | <span data-ttu-id="a0941-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="a0941-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="a0941-142">15,00</span><span class="sxs-lookup"><span data-stu-id="a0941-142">15.00</span></span>     |
| <span data-ttu-id="a0941-143">85,00</span><span class="sxs-lookup"><span data-stu-id="a0941-143">85.00</span></span>                  | <span data-ttu-id="a0941-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="a0941-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="a0941-145">17,00</span><span class="sxs-lookup"><span data-stu-id="a0941-145">17.00</span></span>     |
| <span data-ttu-id="a0941-146">305,00</span><span class="sxs-lookup"><span data-stu-id="a0941-146">305.00</span></span>                 | <span data-ttu-id="a0941-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="a0941-147">305.00 \* 0.10</span></span> | <span data-ttu-id="a0941-148">30,50</span><span class="sxs-lookup"><span data-stu-id="a0941-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="a0941-149"> Exempel: Beräkningsmetoden Intervall</span><span class="sxs-lookup"><span data-stu-id="a0941-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="a0941-150">PÅ sidan Värden ställs momssatserna in med följande intervall:</span><span class="sxs-lookup"><span data-stu-id="a0941-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="a0941-151">**Minimigräns**</span><span class="sxs-lookup"><span data-stu-id="a0941-151">**Minimum limit**</span></span> | <span data-ttu-id="a0941-152">**Maximigräns**</span><span class="sxs-lookup"><span data-stu-id="a0941-152">**Maximum limit**</span></span> | <span data-ttu-id="a0941-153">**Momssats**</span><span class="sxs-lookup"><span data-stu-id="a0941-153">**Tax rate**</span></span> |
| <span data-ttu-id="a0941-154">0,00</span><span class="sxs-lookup"><span data-stu-id="a0941-154">0.00</span></span>              | <span data-ttu-id="a0941-155">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-155">50.00</span></span>             | <span data-ttu-id="a0941-156">30 %</span><span class="sxs-lookup"><span data-stu-id="a0941-156">30%</span></span>          |
| <span data-ttu-id="a0941-157">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-157">50.00</span></span>             | <span data-ttu-id="a0941-158">100,00</span><span class="sxs-lookup"><span data-stu-id="a0941-158">100.00</span></span>            | <span data-ttu-id="a0941-159">20 %</span><span class="sxs-lookup"><span data-stu-id="a0941-159">20%</span></span>          |
| <span data-ttu-id="a0941-160">100,00</span><span class="sxs-lookup"><span data-stu-id="a0941-160">100.00</span></span>            | <span data-ttu-id="a0941-161">0,00</span><span class="sxs-lookup"><span data-stu-id="a0941-161">0.00</span></span>              | <span data-ttu-id="a0941-162">10 %</span><span class="sxs-lookup"><span data-stu-id="a0941-162">10%</span></span>          |

<span data-ttu-id="a0941-163">Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="a0941-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="a0941-164">Momspliktigt belopp (pris)</span><span class="sxs-lookup"><span data-stu-id="a0941-164">Taxable amount (price)</span></span> | <span data-ttu-id="a0941-165">Beräkning</span><span class="sxs-lookup"><span data-stu-id="a0941-165">Calculation</span></span>                                                               | <span data-ttu-id="a0941-166">Moms</span><span class="sxs-lookup"><span data-stu-id="a0941-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="a0941-167">35,00</span><span class="sxs-lookup"><span data-stu-id="a0941-167">35.00</span></span>                  | <span data-ttu-id="a0941-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="a0941-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="a0941-169">10,50</span><span class="sxs-lookup"><span data-stu-id="a0941-169">10.50</span></span>     |
| <span data-ttu-id="a0941-170">50,00</span><span class="sxs-lookup"><span data-stu-id="a0941-170">50.00</span></span>                  | <span data-ttu-id="a0941-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="a0941-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="a0941-172">15,00</span><span class="sxs-lookup"><span data-stu-id="a0941-172">15.00</span></span>     |
| <span data-ttu-id="a0941-173">85,00</span><span class="sxs-lookup"><span data-stu-id="a0941-173">85.00</span></span>                  | <span data-ttu-id="a0941-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="a0941-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="a0941-175">22,00</span><span class="sxs-lookup"><span data-stu-id="a0941-175">22.00</span></span>     |
| <span data-ttu-id="a0941-176">305,00</span><span class="sxs-lookup"><span data-stu-id="a0941-176">305.00</span></span>                 | <span data-ttu-id="a0941-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="a0941-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="a0941-178">45,50</span><span class="sxs-lookup"><span data-stu-id="a0941-178">45.50</span></span>     |

 

<span data-ttu-id="a0941-179">Mer information finns i [Bestämning av momssatser baserat på fälten Marginal base och Calculation method](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="a0941-179">For more information, see [Determining sale tax rates based on the Marginal base and Calculation method fields](marginal-base-field.md).</span></span>






