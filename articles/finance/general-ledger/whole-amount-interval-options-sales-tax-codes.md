---
title: Alternativ för hela belopp och intervallberäkning för momskoder
description: Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48569da2d504e4c380ca89bfec4450ad1b9888e5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842378"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="4d677-103">Alternativ för hela belopp och intervallberäkning för momskoder</span><span class="sxs-lookup"><span data-stu-id="4d677-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d677-104">Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp.</span><span class="sxs-lookup"><span data-stu-id="4d677-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="4d677-105">Du kan ställa in en momskod som ska beräknas baserat på ett helt belopp eller ett intervallbelopp.</span><span class="sxs-lookup"><span data-stu-id="4d677-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="4d677-106">På sidan Momskoder använder du fältet Beräkningsmetod på snabbfliken Beräkning för att välja hur du beräknar en momskod.</span><span class="sxs-lookup"><span data-stu-id="4d677-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="4d677-107">Hela belopp – Momssatsen tillämpas för hela det momspliktiga beloppet.</span><span class="sxs-lookup"><span data-stu-id="4d677-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="4d677-108">Intervall – Det momspliktiga beloppet delas upp i delar, och varje del ligger inom ett intervall som har en specifik momssats.</span><span class="sxs-lookup"><span data-stu-id="4d677-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="4d677-109">Den del av beloppet som ligger inom ett angivet intervall beläggs med moms i enlighet med momssatsen för intervallet.</span><span class="sxs-lookup"><span data-stu-id="4d677-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="4d677-110">Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="4d677-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="4d677-111">Alternativet Intervall är bara tillgängliga när du väljer i fältet Rad i fältet Beräkningsmetod i området Moms på sidan Redovisningparameter.</span><span class="sxs-lookup"><span data-stu-id="4d677-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="4d677-112">Intervall ställs in på sidan Momskodvärden, genom att ange gränsbelopp för minimum och maximum per momssats.</span><span class="sxs-lookup"><span data-stu-id="4d677-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="4d677-113">För att moms ska beräknas på alla momspliktiga belopp, oavsett vilken beräkningsmetod som har valts, måste intervallen vara utformade i enlighet med följande regler:</span><span class="sxs-lookup"><span data-stu-id="4d677-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="4d677-114">Det första intervallet måste ha en minimigräns på noll.</span><span class="sxs-lookup"><span data-stu-id="4d677-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="4d677-115">Det sista intervallet måste ha en maximal gräns på noll, vilket anger oändlighet.</span><span class="sxs-lookup"><span data-stu-id="4d677-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="4d677-116">Den maximala gränsen i ett intervall måste vara minimumgränsen i nästa intervall.</span><span class="sxs-lookup"><span data-stu-id="4d677-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="4d677-117">Om ett belopp är den maximala gränsen för föregående intervall och den minimala gränsen i nästa intervall används momssatsen från det första intervallet för beloppet.</span><span class="sxs-lookup"><span data-stu-id="4d677-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="4d677-118">Om ett belopp ligger utanför de intervall som har definierats av övre och nedre gränser används momssatsen noll.</span><span class="sxs-lookup"><span data-stu-id="4d677-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="4d677-119">Exempel: Beräkningsmetoden för hela beloppet</span><span class="sxs-lookup"><span data-stu-id="4d677-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="4d677-120">På sidan för momskodvärden ställs momssatser in med följande intervall:</span><span class="sxs-lookup"><span data-stu-id="4d677-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="4d677-121">Minimigräns</span><span class="sxs-lookup"><span data-stu-id="4d677-121">Minimum limit</span></span>     | <span data-ttu-id="4d677-122">Maximigräns</span><span class="sxs-lookup"><span data-stu-id="4d677-122">Maximum limit</span></span>     | <span data-ttu-id="4d677-123">Momssats</span><span class="sxs-lookup"><span data-stu-id="4d677-123">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="4d677-124">0,00</span><span class="sxs-lookup"><span data-stu-id="4d677-124">0.00</span></span>              | <span data-ttu-id="4d677-125">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-125">50.00</span></span>             | <span data-ttu-id="4d677-126">30 %</span><span class="sxs-lookup"><span data-stu-id="4d677-126">30%</span></span>          |
| <span data-ttu-id="4d677-127">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-127">50.00</span></span>             | <span data-ttu-id="4d677-128">100,00</span><span class="sxs-lookup"><span data-stu-id="4d677-128">100.00</span></span>            | <span data-ttu-id="4d677-129">20 %</span><span class="sxs-lookup"><span data-stu-id="4d677-129">20%</span></span>          |
| <span data-ttu-id="4d677-130">100,00</span><span class="sxs-lookup"><span data-stu-id="4d677-130">100.00</span></span>            | <span data-ttu-id="4d677-131">0,00</span><span class="sxs-lookup"><span data-stu-id="4d677-131">0.00</span></span>              | <span data-ttu-id="4d677-132">10 %</span><span class="sxs-lookup"><span data-stu-id="4d677-132">10%</span></span>          |

<span data-ttu-id="4d677-133">Momsen beräknas till hela momspliktiga beloppet.</span><span class="sxs-lookup"><span data-stu-id="4d677-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="4d677-134">Momspliktigt belopp (pris)</span><span class="sxs-lookup"><span data-stu-id="4d677-134">Taxable amount (price)</span></span> | <span data-ttu-id="4d677-135">Beräkning</span><span class="sxs-lookup"><span data-stu-id="4d677-135">Calculation</span></span>    | <span data-ttu-id="4d677-136">Moms</span><span class="sxs-lookup"><span data-stu-id="4d677-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="4d677-137">35,00</span><span class="sxs-lookup"><span data-stu-id="4d677-137">35.00</span></span>                  | <span data-ttu-id="4d677-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="4d677-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="4d677-139">10,50</span><span class="sxs-lookup"><span data-stu-id="4d677-139">10.50</span></span>     |
| <span data-ttu-id="4d677-140">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-140">50.00</span></span>                  | <span data-ttu-id="4d677-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="4d677-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="4d677-142">15,00</span><span class="sxs-lookup"><span data-stu-id="4d677-142">15.00</span></span>     |
| <span data-ttu-id="4d677-143">85,00</span><span class="sxs-lookup"><span data-stu-id="4d677-143">85.00</span></span>                  | <span data-ttu-id="4d677-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="4d677-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="4d677-145">17,00</span><span class="sxs-lookup"><span data-stu-id="4d677-145">17.00</span></span>     |
| <span data-ttu-id="4d677-146">305,00</span><span class="sxs-lookup"><span data-stu-id="4d677-146">305.00</span></span>                 | <span data-ttu-id="4d677-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="4d677-147">305.00 \* 0.10</span></span> | <span data-ttu-id="4d677-148">30,50</span><span class="sxs-lookup"><span data-stu-id="4d677-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="4d677-149"> Exempel: Beräkningsmetoden Intervall</span><span class="sxs-lookup"><span data-stu-id="4d677-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="4d677-150">PÅ sidan Värden ställs momssatserna in med följande intervall:</span><span class="sxs-lookup"><span data-stu-id="4d677-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="4d677-151">Minimigräns</span><span class="sxs-lookup"><span data-stu-id="4d677-151">Minimum limit</span></span>     | <span data-ttu-id="4d677-152">Maximigräns</span><span class="sxs-lookup"><span data-stu-id="4d677-152">Maximum limit</span></span>     | <span data-ttu-id="4d677-153">Momssats</span><span class="sxs-lookup"><span data-stu-id="4d677-153">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="4d677-154">0,00</span><span class="sxs-lookup"><span data-stu-id="4d677-154">0.00</span></span>              | <span data-ttu-id="4d677-155">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-155">50.00</span></span>             | <span data-ttu-id="4d677-156">30 %</span><span class="sxs-lookup"><span data-stu-id="4d677-156">30%</span></span>          |
| <span data-ttu-id="4d677-157">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-157">50.00</span></span>             | <span data-ttu-id="4d677-158">100,00</span><span class="sxs-lookup"><span data-stu-id="4d677-158">100.00</span></span>            | <span data-ttu-id="4d677-159">20 %</span><span class="sxs-lookup"><span data-stu-id="4d677-159">20%</span></span>          |
| <span data-ttu-id="4d677-160">100,00</span><span class="sxs-lookup"><span data-stu-id="4d677-160">100.00</span></span>            | <span data-ttu-id="4d677-161">0,00</span><span class="sxs-lookup"><span data-stu-id="4d677-161">0.00</span></span>              | <span data-ttu-id="4d677-162">10 %</span><span class="sxs-lookup"><span data-stu-id="4d677-162">10%</span></span>          |

<span data-ttu-id="4d677-163">Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="4d677-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="4d677-164">Momspliktigt belopp (pris)</span><span class="sxs-lookup"><span data-stu-id="4d677-164">Taxable amount (price)</span></span> | <span data-ttu-id="4d677-165">Beräkning</span><span class="sxs-lookup"><span data-stu-id="4d677-165">Calculation</span></span>                                                               | <span data-ttu-id="4d677-166">Moms</span><span class="sxs-lookup"><span data-stu-id="4d677-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="4d677-167">35,00</span><span class="sxs-lookup"><span data-stu-id="4d677-167">35.00</span></span>                  | <span data-ttu-id="4d677-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="4d677-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="4d677-169">10,50</span><span class="sxs-lookup"><span data-stu-id="4d677-169">10.50</span></span>     |
| <span data-ttu-id="4d677-170">50,00</span><span class="sxs-lookup"><span data-stu-id="4d677-170">50.00</span></span>                  | <span data-ttu-id="4d677-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="4d677-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="4d677-172">15,00</span><span class="sxs-lookup"><span data-stu-id="4d677-172">15.00</span></span>     |
| <span data-ttu-id="4d677-173">85,00</span><span class="sxs-lookup"><span data-stu-id="4d677-173">85.00</span></span>                  | <span data-ttu-id="4d677-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="4d677-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="4d677-175">22,00</span><span class="sxs-lookup"><span data-stu-id="4d677-175">22.00</span></span>     |
| <span data-ttu-id="4d677-176">305,00</span><span class="sxs-lookup"><span data-stu-id="4d677-176">305.00</span></span>                 | <span data-ttu-id="4d677-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="4d677-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="4d677-178">45.50</span><span class="sxs-lookup"><span data-stu-id="4d677-178">45.50</span></span>     |



<span data-ttu-id="4d677-179">Mer information finns i [Momssatser baserat på fälten Marginalbas och Beräkningsmetod](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="4d677-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]