---
title: "Ställa in räntesatser för en räntekod"
description: "Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7ae0bfdc157a7e2e5b9f871dae487a6f85e889b9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="d68fb-103">Ställa in räntesatser för en räntekod</span><span class="sxs-lookup"><span data-stu-id="d68fb-103">Set up interest rates for an interest code</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d68fb-104">Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton.</span><span class="sxs-lookup"><span data-stu-id="d68fb-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="d68fb-105">Du kan ställa in en enskild räntekod och använda den till flera bokföringsprofiler för kunder och faktureringskoder eller för specifika fakturarader.</span><span class="sxs-lookup"><span data-stu-id="d68fb-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="d68fb-106">När räntekoddetaljerna ändras kommer alla funktioner som använder koden att införa ändringarna automatiskt i nya transaktioner.</span><span class="sxs-lookup"><span data-stu-id="d68fb-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="d68fb-107">För varje räntekod kan du ställa in två typer av satser:</span><span class="sxs-lookup"><span data-stu-id="d68fb-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="d68fb-108">Satser för ränteintäkter − dessa representerar intäkt som erhållits genom att debitera ränta på fakturor, eller räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="d68fb-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="d68fb-109">Satser för räntebetalningar − dessa representerar en kostnad som betalas för ränta på kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="d68fb-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="d68fb-110">Båda av följande satstyper kan finnas samtidigt och med samma räntekod.</span><span class="sxs-lookup"><span data-stu-id="d68fb-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="d68fb-111">Räntesatser kan baseras på tre beräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="d68fb-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="d68fb-112">Ränta i procent.</span><span class="sxs-lookup"><span data-stu-id="d68fb-112">Interest by percentage.</span></span>
-   <span data-ttu-id="d68fb-113">Ränta i belopp.</span><span class="sxs-lookup"><span data-stu-id="d68fb-113">Interest by amount.</span></span>
-   <span data-ttu-id="d68fb-114">Ränta per intervall, vilket resulterar i en enskild procentandel eller belopp.</span><span class="sxs-lookup"><span data-stu-id="d68fb-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="d68fb-115">När en räntekod används för beräkning av räntan skapas en separat räntefaktura för varje räntesats som gäller under den tid som betalningen har överskridit transaktionens förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="d68fb-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="d68fb-116">Du använder fliken **Resultaten** på sidan **Räntekod** för att ställa in räntesatser för ränta som du till exempel tjänar genom att debitera ränta.</span><span class="sxs-lookup"><span data-stu-id="d68fb-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="d68fb-117">Använd fliken **Betalningar** om du vill ställa in räntesatser för ränta som du betalar.</span><span class="sxs-lookup"><span data-stu-id="d68fb-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="d68fb-118">Räntesatser baserat på procentsats</span><span class="sxs-lookup"><span data-stu-id="d68fb-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="d68fb-119">Du kan ställa in räntesatser för att beräkna en viss procent.</span><span class="sxs-lookup"><span data-stu-id="d68fb-119">You can set up interest rates that calculate a specified percentage.</span></span>

-   <span data-ttu-id="d68fb-120">Räntebeloppet gäller för alla valutor.</span><span class="sxs-lookup"><span data-stu-id="d68fb-120">Interest amount applies to all currencies.</span></span>
-   <span data-ttu-id="d68fb-121">Valfria räntebeloppsgränser kan anges.</span><span class="sxs-lookup"><span data-stu-id="d68fb-121">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="d68fb-122">**Procent** väljs** **i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="d68fb-122">**Percentage** is selected** **in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="d68fb-123">Om du till exempel vill ställa in en räntekod som värderas med 5 procent ränta för varje tvåmånadersperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 2 i fältet **Beräkna ränta var** och välja **Månad**.</span><span class="sxs-lookup"><span data-stu-id="d68fb-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="d68fb-124">Räntesatser baserade på belopp</span><span class="sxs-lookup"><span data-stu-id="d68fb-124">Interest rates based on amounts</span></span>
<span data-ttu-id="d68fb-125">Du kan ställa in räntesatser för att beräkna ett angivet belopp per valuta.</span><span class="sxs-lookup"><span data-stu-id="d68fb-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
-   <span data-ttu-id="d68fb-126">Ett räntebelopp anges för varje valuta i räntekoden.</span><span class="sxs-lookup"><span data-stu-id="d68fb-126">An interest amount is specified for each currency in the interest code.</span></span>
-   <span data-ttu-id="d68fb-127">Valfria räntebeloppsgränser kan anges.</span><span class="sxs-lookup"><span data-stu-id="d68fb-127">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="d68fb-128">**Belopp **väljs i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="d68fb-128">**Amount **is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="d68fb-129">Om du till exempel vill ställa in en räntekod som värderas med 25,00 ränta för varje 20-dagarsperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 20 i fältet **Beräkna ränta var** och välj **Dag**.</span><span class="sxs-lookup"><span data-stu-id="d68fb-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="d68fb-130">Räntesatser baserade på perioder</span><span class="sxs-lookup"><span data-stu-id="d68fb-130">Interest rates based on ranges</span></span>
<span data-ttu-id="d68fb-131">Du kan ställa in räntesatser som varierar beroende på det förfallna beloppet, antalet dagar som beloppet är försenat eller antalet månader som beloppet är försenat.</span><span class="sxs-lookup"><span data-stu-id="d68fb-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="d68fb-132">Du kan använda fliken **Resultaten per valuta** för att ange särskilda ränteinställningar för varje valuta.</span><span class="sxs-lookup"><span data-stu-id="d68fb-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="d68fb-133">Det är också där du definierar intervallet.</span><span class="sxs-lookup"><span data-stu-id="d68fb-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="d68fb-134">Använd knappen **Intervall** om du vill lägga till rader som motsvarar intervall som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="d68fb-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="d68fb-135">Värdet **Från** representerar starttiden för intervallet och talet **Räntevärde** representerar antingen ett procenttal eller ett belopp, beroende på valet i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="d68fb-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="d68fb-136">Exempel 1: Ränta efter period = Belopp</span><span class="sxs-lookup"><span data-stu-id="d68fb-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="d68fb-137">Du kan ställa in en räntekod som beräknar ränta en gång var tredje månad som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d68fb-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="d68fb-138">Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="d68fb-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="d68fb-139">Räntevärdet ska vara 1 procent för fakturabelopp upp till 1.000,00, 2 procent för belopp från 1.001,00 till 5.000,00 och 3 procent för större än 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="d68fb-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="d68fb-140">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="d68fb-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="d68fb-141">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="d68fb-141">**Field name**</span></span>                  | <span data-ttu-id="d68fb-142">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="d68fb-143">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="d68fb-143">**Interest code**</span></span>               | <span data-ttu-id="d68fb-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="d68fb-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="d68fb-145">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="d68fb-145">**Calculate interest every**</span></span>    | <span data-ttu-id="d68fb-146">3/månad</span><span class="sxs-lookup"><span data-stu-id="d68fb-146">3/Month</span></span>         |
| <span data-ttu-id="d68fb-147">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="d68fb-147">**Interest by range**</span></span>           | <span data-ttu-id="d68fb-148">Belopp</span><span class="sxs-lookup"><span data-stu-id="d68fb-148">Amount</span></span>          |
| <span data-ttu-id="d68fb-149">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="d68fb-149">**Calculate interest based on**</span></span> | <span data-ttu-id="d68fb-150">Procent</span><span class="sxs-lookup"><span data-stu-id="d68fb-150">Percentage</span></span>      |

<span data-ttu-id="d68fb-151">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="d68fb-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="d68fb-152">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-152">**From value**</span></span> | <span data-ttu-id="d68fb-153">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="d68fb-154">0</span><span class="sxs-lookup"><span data-stu-id="d68fb-154">0</span></span>              | <span data-ttu-id="d68fb-155">1</span><span class="sxs-lookup"><span data-stu-id="d68fb-155">1</span></span>                  |
| <span data-ttu-id="d68fb-156">1,001</span><span class="sxs-lookup"><span data-stu-id="d68fb-156">1,001</span></span>          | <span data-ttu-id="d68fb-157">2</span><span class="sxs-lookup"><span data-stu-id="d68fb-157">2</span></span>                  |
| <span data-ttu-id="d68fb-158">5,001</span><span class="sxs-lookup"><span data-stu-id="d68fb-158">5,001</span></span>          | <span data-ttu-id="d68fb-159">3</span><span class="sxs-lookup"><span data-stu-id="d68fb-159">3</span></span>                  |

 
## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="d68fb-160">Exempel 2: Ränta efter period = Dagar</span><span class="sxs-lookup"><span data-stu-id="d68fb-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="d68fb-161">Du kan ställa in en räntekod som beräknar ränta en gång för varje 15 dagar som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d68fb-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="d68fb-162">Du ska basera beräkningen på ett räntevärde för ett belopp, efter stegvisa dagsintervall.</span><span class="sxs-lookup"><span data-stu-id="d68fb-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="d68fb-163">Räntavärdet blir 10,00 per 15 dagar under de första 60 dagar, 15,00 dagar per 15 dagar under 61 till 90 och 20,00 per 15 dagar från dag 91 och ska.</span><span class="sxs-lookup"><span data-stu-id="d68fb-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="d68fb-164">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="d68fb-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="d68fb-165">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="d68fb-165">**Field name**</span></span>                  | <span data-ttu-id="d68fb-166">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="d68fb-167">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="d68fb-167">**Interest code**</span></span>               | <span data-ttu-id="d68fb-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="d68fb-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="d68fb-169">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="d68fb-169">**Calculate interest every**</span></span>    | <span data-ttu-id="d68fb-170">15/dag</span><span class="sxs-lookup"><span data-stu-id="d68fb-170">15/Day</span></span>          |
| <span data-ttu-id="d68fb-171">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="d68fb-171">**Interest by range**</span></span>           | <span data-ttu-id="d68fb-172">Dagar</span><span class="sxs-lookup"><span data-stu-id="d68fb-172">Days</span></span>            |
| <span data-ttu-id="d68fb-173">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="d68fb-173">**Calculate interest based on**</span></span> | <span data-ttu-id="d68fb-174">Belopp</span><span class="sxs-lookup"><span data-stu-id="d68fb-174">Amount</span></span>          |

<span data-ttu-id="d68fb-175">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="d68fb-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="d68fb-176">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-176">**From value**</span></span> | <span data-ttu-id="d68fb-177">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="d68fb-178">0</span><span class="sxs-lookup"><span data-stu-id="d68fb-178">0</span></span>              | <span data-ttu-id="d68fb-179">10</span><span class="sxs-lookup"><span data-stu-id="d68fb-179">10</span></span>                 |
| <span data-ttu-id="d68fb-180">61</span><span class="sxs-lookup"><span data-stu-id="d68fb-180">61</span></span>             | <span data-ttu-id="d68fb-181">15</span><span class="sxs-lookup"><span data-stu-id="d68fb-181">15</span></span>                 |
| <span data-ttu-id="d68fb-182">91</span><span class="sxs-lookup"><span data-stu-id="d68fb-182">91</span></span>             | <span data-ttu-id="d68fb-183">20</span><span class="sxs-lookup"><span data-stu-id="d68fb-183">20</span></span>                 |

 
## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="d68fb-184">Exempel 3: Ränta efter period = Månader</span><span class="sxs-lookup"><span data-stu-id="d68fb-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="d68fb-185">Du kan ställa in en räntekod som beräknar ränta en gång för varje månad som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d68fb-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="d68fb-186">Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa månadsintervall.</span><span class="sxs-lookup"><span data-stu-id="d68fb-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="d68fb-187">Räntevärdet ska vara 1,5 procent per månad för de första tre förfallna månaderna, 2,0 procent per månad för nästa tre månader och 2,5 procent per månad för varje månad efter det första halvåret.</span><span class="sxs-lookup"><span data-stu-id="d68fb-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="d68fb-188">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="d68fb-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="d68fb-189">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="d68fb-189">**Field name**</span></span>                  | <span data-ttu-id="d68fb-190">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="d68fb-191">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="d68fb-191">**Interest code**</span></span>               | <span data-ttu-id="d68fb-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="d68fb-192">1M%ByMth</span></span>        |
| <span data-ttu-id="d68fb-193">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="d68fb-193">**Calculate interest every**</span></span>    | <span data-ttu-id="d68fb-194">1/månad</span><span class="sxs-lookup"><span data-stu-id="d68fb-194">1/Month</span></span>         |
| <span data-ttu-id="d68fb-195">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="d68fb-195">**Interest by range**</span></span>           | <span data-ttu-id="d68fb-196">Månader</span><span class="sxs-lookup"><span data-stu-id="d68fb-196">Months</span></span>          |
| <span data-ttu-id="d68fb-197">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="d68fb-197">**Calculate interest based on**</span></span> | <span data-ttu-id="d68fb-198">Procent</span><span class="sxs-lookup"><span data-stu-id="d68fb-198">Percentage</span></span>      |

<span data-ttu-id="d68fb-199">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="d68fb-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="d68fb-200">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-200">**From value**</span></span> | <span data-ttu-id="d68fb-201">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="d68fb-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="d68fb-202">0</span><span class="sxs-lookup"><span data-stu-id="d68fb-202">0</span></span>              | <span data-ttu-id="d68fb-203">1.5</span><span class="sxs-lookup"><span data-stu-id="d68fb-203">1.5</span></span>                |
| <span data-ttu-id="d68fb-204">4</span><span class="sxs-lookup"><span data-stu-id="d68fb-204">4</span></span>              | <span data-ttu-id="d68fb-205">2</span><span class="sxs-lookup"><span data-stu-id="d68fb-205">2</span></span>                  |
| <span data-ttu-id="d68fb-206">7</span><span class="sxs-lookup"><span data-stu-id="d68fb-206">7</span></span>              | <span data-ttu-id="d68fb-207">2,5</span><span class="sxs-lookup"><span data-stu-id="d68fb-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="d68fb-208">Nya versioner</span><span class="sxs-lookup"><span data-stu-id="d68fb-208">New versions</span></span>
<span data-ttu-id="d68fb-209">Räntekoder har giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="d68fb-209">Interest codes are date effective.</span></span> <span data-ttu-id="d68fb-210">Om du vill ändra räntesatsen kan du skapa en **ny version** som gäller för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="d68fb-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="d68fb-211">Om du vill visa andra versioner kan du använda menyvalet **Från och med (datum)** för att välja slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="d68fb-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="d68fb-212">Du kan också markera **Visa alla poster** för att visa alla räntekoder på sidan.</span><span class="sxs-lookup"><span data-stu-id="d68fb-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




