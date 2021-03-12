---
title: Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder
description: Det här ämnet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner.
author: ShylaThompson
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dcb51c730da3f2ad155675f06f5c1cd9e8476d2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988674"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="ff026-103">Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder</span><span class="sxs-lookup"><span data-stu-id="ff026-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff026-104">Det här ämnet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ff026-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="ff026-105">Bidragsunderlag på snabbfliken Beräkning på sidan Momskoder avgör vilket belopp som används för att plocka rätt momssatser från momssatserna på sidan Momskodvärden.</span><span class="sxs-lookup"><span data-stu-id="ff026-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="ff026-106">Beloppstypen i fältet Bidragsunderlag i kombination med metoden i fältet Beräkningsmetod bestämmer logiken för att hitta rätt momssats för en transaktion.</span><span class="sxs-lookup"><span data-stu-id="ff026-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="ff026-107">Olika kombinationer av värden i de här fälten kan ge mycket olika momsberäkningar, vilket demonstreras i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="ff026-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="ff026-108">I exemplen används samma momsintervallvärden – värden som har ställts in för varje momskod på sidan Momskodvärden.</span><span class="sxs-lookup"><span data-stu-id="ff026-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="ff026-109">Klicka på Momskod &gt; Värden på sidan Momskoder för att öppna denna sida.</span><span class="sxs-lookup"><span data-stu-id="ff026-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="ff026-110">Om Bidragsunderlag för en eller flera av dina momskoder baseras på radbelopp eller enheter måste värdet i fältet Beräkningsmetod på sidan Allmänna huvudboksparametrar ha inställningen Rad.</span><span class="sxs-lookup"><span data-stu-id="ff026-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="ff026-111"> Nettobelopp per rad</span><span class="sxs-lookup"><span data-stu-id="ff026-111">Net amount per line</span></span>
<span data-ttu-id="ff026-112">Välj det här alternativet för att bestämma momssatser baserat på nettobeloppet för fakturaraderna, exklusive andra skatter.</span><span class="sxs-lookup"><span data-stu-id="ff026-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="ff026-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-113">Example</span></span>

<span data-ttu-id="ff026-114">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-115">Beloppsintervall</span><span class="sxs-lookup"><span data-stu-id="ff026-115">Amount interval</span></span>    | <span data-ttu-id="ff026-116">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="ff026-117">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-117">0 - 50</span></span>             | <span data-ttu-id="ff026-118">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-118">30%</span></span>      |
| <span data-ttu-id="ff026-119">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-119">50 - 100</span></span>           | <span data-ttu-id="ff026-120">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-120">20%</span></span>      |
| <span data-ttu-id="ff026-121">100 – 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-122">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="ff026-123">Den övre gränsen på noll (0) i det sista intervallet innebär att alla belopp över 100 inkluderas i intervallet.</span><span class="sxs-lookup"><span data-stu-id="ff026-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="ff026-124">Bidragsunderlaget: **Nettobelopp per rad**</span><span class="sxs-lookup"><span data-stu-id="ff026-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="ff026-125">Beräkningsmetod: **Intervall**</span><span class="sxs-lookup"><span data-stu-id="ff026-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="ff026-126">Du köper 8 lampor som kostar 25,00 styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="ff026-127">Nettobeloppet för fakturaraden är 200,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="ff026-128">Momsen beräknas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ff026-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="ff026-129">Total moms = 50 × 30 % + 50 × 20 % + 100 × 10 % = 15 + 10 + 10 = 35,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="ff026-130">Totalt fakturabelopp = 200,00 + 35,00 = 235,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="ff026-131">**Variant**</span><span class="sxs-lookup"><span data-stu-id="ff026-131">**Variation**</span></span> 

<span data-ttu-id="ff026-132">Om fakturan har två rader med fyra artiklar på varje rad är nettobeloppet på respektive rad 100,00, och momsen beräknas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ff026-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="ff026-133">Moms för rad 1 = 50 × 30 % + 50 × 20 % = 15 + 10 = 25,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="ff026-134">Moms för rad 2 = 50 × 30 % + 50 × 20 % = 15 + 10 = 25,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="ff026-135">Total moms = 25,00 +25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="ff026-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="ff026-136">Totalt fakturabelopp = 200,00 + 50,00 = 250,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="ff026-137"> Nettobelopp per enhet</span><span class="sxs-lookup"><span data-stu-id="ff026-137">Net amount per unit</span></span>
<span data-ttu-id="ff026-138">Välj det här alternativet för att bestämma momssatser baserat på värdet för varje enhet, exklusive andra skatter.</span><span class="sxs-lookup"><span data-stu-id="ff026-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="ff026-139">När en enhet som baseras på Bidragsunderlag väljs måste även en enhet anges för momskoden.</span><span class="sxs-lookup"><span data-stu-id="ff026-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="ff026-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-140">Example</span></span>

<span data-ttu-id="ff026-141">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-142">Belopp</span><span class="sxs-lookup"><span data-stu-id="ff026-142">Amount</span></span>             | <span data-ttu-id="ff026-143">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="ff026-144">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-144">0 - 50</span></span>             | <span data-ttu-id="ff026-145">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-145">30%</span></span>      |
| <span data-ttu-id="ff026-146">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-146">50 - 100</span></span>           | <span data-ttu-id="ff026-147">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-147">20%</span></span>      |
| <span data-ttu-id="ff026-148">100 – 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-149">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-149">10%</span></span>      |

<span data-ttu-id="ff026-150">Bidragsunderlag: **Nettobelopp per enhet**</span><span class="sxs-lookup"><span data-stu-id="ff026-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="ff026-151">Beräkningsmetod: **Hela beloppet**</span><span class="sxs-lookup"><span data-stu-id="ff026-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="ff026-152">Du köper 8 lampor som kostar 25,00 styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="ff026-153">Nettobeloppet för fakturaraden är 200,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="ff026-154">Momsen beräknas på följande sätt: Moms per enhet = 25,00 × 30 % = 7,50 Total moms = 7,50 × 8 enheter = 60,00 Totalt fakturabelopp = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="ff026-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="ff026-155"> Nettobelopp av fakturasaldo</span><span class="sxs-lookup"><span data-stu-id="ff026-155">Net amount of invoice balance</span></span>

<span data-ttu-id="ff026-156">Välj det här alternativet för att bestämma momssatser baserat på fakturans totala värde, exklusive andra skatter.</span><span class="sxs-lookup"><span data-stu-id="ff026-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="ff026-157">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-157">Example</span></span>

<span data-ttu-id="ff026-158">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-159">Belopp</span><span class="sxs-lookup"><span data-stu-id="ff026-159">Amount</span></span>            | <span data-ttu-id="ff026-160">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="ff026-161">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-161">0 - 50</span></span>            | <span data-ttu-id="ff026-162">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-162">30%</span></span>      |
| <span data-ttu-id="ff026-163">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-163">50 - 100</span></span>          | <span data-ttu-id="ff026-164">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-164">20%</span></span>      |
| <span data-ttu-id="ff026-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-166">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-166">10%</span></span>      |

<span data-ttu-id="ff026-167">Bidragsunderlag **Nettobelopp av fakturasaldo**</span><span class="sxs-lookup"><span data-stu-id="ff026-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="ff026-168">Beräkningsmetod: **Intervall** En försäljningsfaktura har 2 rader med 4 lampor på respektive rad för 25,00 per styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="ff026-169">Nettobeloppet för fakturasaldo är 4 × 25,00 + 4 × 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="ff026-170">Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 100 × 0,10 = 15 + 10 + 10 = 35,00 Totalt fakturabelopp = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="ff026-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="ff026-171"> Bruttobelopp per rad</span><span class="sxs-lookup"><span data-stu-id="ff026-171">Gross amount per line</span></span>

<span data-ttu-id="ff026-172">Välj det här alternativet för att bestämma momssatser baserat på radens värde, inklusive alla andra skatter för raden.</span><span class="sxs-lookup"><span data-stu-id="ff026-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="ff026-173">I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ff026-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="ff026-174">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-174">Example</span></span>

<span data-ttu-id="ff026-175">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-176">Belopp</span><span class="sxs-lookup"><span data-stu-id="ff026-176">Amount</span></span>             | <span data-ttu-id="ff026-177">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="ff026-178">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-178">0 - 50</span></span>             | <span data-ttu-id="ff026-179">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-179">30%</span></span>      |
| <span data-ttu-id="ff026-180">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-180">50 - 100</span></span>           | <span data-ttu-id="ff026-181">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-181">20%</span></span>      |
| <span data-ttu-id="ff026-182">100 – 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-183">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-183">10%</span></span>      |

<span data-ttu-id="ff026-184">Bidragsunderlag: **Bruttobelopp per rad** Beräkningsmetod: **Intervall** Det finns också en annan momskod som beräknas för en särskild avgift på 5,00 för varje lampa.</span><span class="sxs-lookup"><span data-stu-id="ff026-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="ff026-185">Avgiften läggs till nettobeloppet innan momsen beräknas.</span><span class="sxs-lookup"><span data-stu-id="ff026-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="ff026-186">Du köper 8 lampor som kostar 25,00 styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="ff026-187">Nettobeloppet för fakturaraden är 200,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="ff026-188">Bruttobeloppet för fakturaraden är 8 × 25,00 + 8 × 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="ff026-189">Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 20 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="ff026-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="ff026-190">**Variant**</span><span class="sxs-lookup"><span data-stu-id="ff026-190">**Variation**</span></span> 

<span data-ttu-id="ff026-191">Om fakturan skapas med två fakturarader med fyra artiklar på respektive rad, är nettobeloppet per fakturarad 100,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="ff026-192">Bruttobeloppet (inklusive avgiften på 4 × 5,00) per fakturarad blir då 120,00 och momsen skapas på följande sätt: Moms för fakturarad 1 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Moms för fakturarad 2 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Total moms = 27,00 + 27,00 = 54,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 54,00 + 40,00 = 294,00</span><span class="sxs-lookup"><span data-stu-id="ff026-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="ff026-193"> Bruttobelopp per enhet</span><span class="sxs-lookup"><span data-stu-id="ff026-193">Gross amount per unit</span></span>

<span data-ttu-id="ff026-194">Välj det här alternativet för att bestämma momssatser baserat på värdet för enheten inklusive andra skatter.</span><span class="sxs-lookup"><span data-stu-id="ff026-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="ff026-195">I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ff026-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="ff026-196">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-196">Example</span></span>

<span data-ttu-id="ff026-197">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-198">Belopp</span><span class="sxs-lookup"><span data-stu-id="ff026-198">Amount</span></span>             | <span data-ttu-id="ff026-199">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="ff026-200">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-200">0 - 50</span></span>             | <span data-ttu-id="ff026-201">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-201">30%</span></span>      |
| <span data-ttu-id="ff026-202">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-202">50 - 100</span></span>           | <span data-ttu-id="ff026-203">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-203">20%</span></span>      |
| <span data-ttu-id="ff026-204">100 – 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-205">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-205">10%</span></span>      |

<span data-ttu-id="ff026-206">Bidragsunderlag: **Bruttobelopp per enhet** Det finns en särskild avgift på 5,00 för varje lampa.</span><span class="sxs-lookup"><span data-stu-id="ff026-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="ff026-207">Avgiften läggs till nettobeloppet innan momsen beräknas.</span><span class="sxs-lookup"><span data-stu-id="ff026-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="ff026-208">Du köper 8 lampor som kostar 25,00 styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="ff026-209">Bruttobeloppet per enhet är 30,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="ff026-210">Momsen beräknas på följande sätt: Moms per enhet = 30 × 30% = 9,00 Total moms = 9,00 × 8 = 72,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="ff026-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="ff026-211"> Fakturatotal inkl. andra momsbelopp</span><span class="sxs-lookup"><span data-stu-id="ff026-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="ff026-212">Välj det här alternativet för att bestämma momssatser baserat på fakturans totala värde, inklusive andra skatter.</span><span class="sxs-lookup"><span data-stu-id="ff026-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="ff026-213">I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ff026-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="ff026-214">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff026-214">Example</span></span>

<span data-ttu-id="ff026-215">Momssatserna ställs in med följande intervall.</span><span class="sxs-lookup"><span data-stu-id="ff026-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="ff026-216">Belopp</span><span class="sxs-lookup"><span data-stu-id="ff026-216">Amount</span></span>             | <span data-ttu-id="ff026-217">Skattesats</span><span class="sxs-lookup"><span data-stu-id="ff026-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="ff026-218">0 – 50</span><span class="sxs-lookup"><span data-stu-id="ff026-218">0 - 50</span></span>             | <span data-ttu-id="ff026-219">30 %</span><span class="sxs-lookup"><span data-stu-id="ff026-219">30%</span></span>      |
| <span data-ttu-id="ff026-220">50 – 100</span><span class="sxs-lookup"><span data-stu-id="ff026-220">50 - 100</span></span>           | <span data-ttu-id="ff026-221">20 %</span><span class="sxs-lookup"><span data-stu-id="ff026-221">20%</span></span>      |
| <span data-ttu-id="ff026-222">100 – 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="ff026-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="ff026-223">10 %</span><span class="sxs-lookup"><span data-stu-id="ff026-223">10%</span></span>      |

<span data-ttu-id="ff026-224">Bidragsunderlag: **Fakturasumma inklusive andra momsbelopp** Beräkningsmetod: **Intervall** </span><span class="sxs-lookup"><span data-stu-id="ff026-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="ff026-225">Det finns en särskild avgift på 5, 00 för varje lampa.</span><span class="sxs-lookup"><span data-stu-id="ff026-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="ff026-226">Avgiften läggs till nettobeloppet innan momsen beräknas.</span><span class="sxs-lookup"><span data-stu-id="ff026-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="ff026-227">Du köper 8 lampor som kostar 25,00 styck.</span><span class="sxs-lookup"><span data-stu-id="ff026-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="ff026-228">Nettobeloppet för fakturan är 200,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="ff026-229">Bruttobeloppet för fakturan är 200,00 + (8 × 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="ff026-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="ff026-230">Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 10 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="ff026-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="ff026-231">Mer information finns i [Alternativ för hela belopp och intervallberäkning för momskoder](whole-amount-interval-options-sales-tax-codes.md) samt i [Beräkning av momskoder i fältet Ursprung](sales-tax-calculation-methods-origin-field.md).</span><span class="sxs-lookup"><span data-stu-id="ff026-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>



