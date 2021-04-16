---
title: Ställa in räntesatser för en räntekod
description: Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton.
author: ShivamPandey-msft
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62868c30d3ff60e51d99c71b743ab0bbb3c87451
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835206"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="02b8e-103">Ställa in räntesatser för en räntekod</span><span class="sxs-lookup"><span data-stu-id="02b8e-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02b8e-104">Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton.</span><span class="sxs-lookup"><span data-stu-id="02b8e-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="02b8e-105">Du kan ställa in en enskild räntekod och använda den till flera bokföringsprofiler för kunder och faktureringskoder eller för specifika fakturarader.</span><span class="sxs-lookup"><span data-stu-id="02b8e-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="02b8e-106">När räntekoddetaljerna ändras kommer alla funktioner som använder koden att införa ändringarna automatiskt i nya transaktioner.</span><span class="sxs-lookup"><span data-stu-id="02b8e-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="02b8e-107">För varje räntekod kan du ställa in två typer av satser:</span><span class="sxs-lookup"><span data-stu-id="02b8e-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="02b8e-108">Satser för ränteintäkter − dessa representerar intäkt som erhållits genom att debitera ränta på fakturor, eller räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="02b8e-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="02b8e-109">Satser för räntebetalningar − dessa representerar en kostnad som betalas för ränta på kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="02b8e-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="02b8e-110">Båda av följande satstyper kan finnas samtidigt och med samma räntekod.</span><span class="sxs-lookup"><span data-stu-id="02b8e-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="02b8e-111">Räntesatser kan baseras på tre beräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="02b8e-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="02b8e-112">Ränta i procent.</span><span class="sxs-lookup"><span data-stu-id="02b8e-112">Interest by percentage.</span></span>
-   <span data-ttu-id="02b8e-113">Ränta i belopp.</span><span class="sxs-lookup"><span data-stu-id="02b8e-113">Interest by amount.</span></span>
-   <span data-ttu-id="02b8e-114">Ränta per intervall, vilket resulterar i en enskild procentandel eller belopp.</span><span class="sxs-lookup"><span data-stu-id="02b8e-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="02b8e-115">När en räntekod används för beräkning av räntan skapas en separat räntefaktura för varje räntesats som gäller under den tid som betalningen har överskridit transaktionens förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="02b8e-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="02b8e-116">Du använder fliken **Resultaten** på sidan **Räntekod** för att ställa in räntesatser för ränta som du till exempel tjänar genom att debitera ränta.</span><span class="sxs-lookup"><span data-stu-id="02b8e-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="02b8e-117">Använd fliken **Betalningar** om du vill ställa in räntesatser för ränta som du betalar.</span><span class="sxs-lookup"><span data-stu-id="02b8e-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="02b8e-118">Räntesatser baserat på procentsats</span><span class="sxs-lookup"><span data-stu-id="02b8e-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="02b8e-119">Du kan ställa in räntesatser för att beräkna en viss procent.</span><span class="sxs-lookup"><span data-stu-id="02b8e-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="02b8e-120">Räntebeloppet gäller för alla valutor.</span><span class="sxs-lookup"><span data-stu-id="02b8e-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="02b8e-121">Valfria räntebeloppsgränser kan anges.</span><span class="sxs-lookup"><span data-stu-id="02b8e-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="02b8e-122">**Procent** väljs i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="02b8e-123">Om du till exempel vill ställa in en räntekod som värderas med 5 procent ränta för varje tvåmånadersperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 2 i fältet **Beräkna ränta var** och välja **Månad**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="02b8e-124">Den nya algoritmen för räntefakturaberäkning läggs till med funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="02b8e-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="02b8e-125">Om du vill använda den här algoritmen funktionen **(GBL) Låt beräkna ränta per dag i procent per år dividerat med 365**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="02b8e-126">Mer information om hur du aktiverar funktionen finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="02b8e-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="02b8e-127">Formeln för beräkning av räntefakturabeloppet är:</span><span class="sxs-lookup"><span data-stu-id="02b8e-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="02b8e-128">Räntefakturabelopp = Belopp för skuld \*Årsräntan % / 365 \* Antal dagar för sent</span><span class="sxs-lookup"><span data-stu-id="02b8e-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="02b8e-129">Den här funktionen finns i version 10.0.18 eller senare.</span><span class="sxs-lookup"><span data-stu-id="02b8e-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="02b8e-130">Räntesatser baserade på belopp</span><span class="sxs-lookup"><span data-stu-id="02b8e-130">Interest rates based on amounts</span></span>
<span data-ttu-id="02b8e-131">Du kan ställa in räntesatser för att beräkna ett angivet belopp per valuta.</span><span class="sxs-lookup"><span data-stu-id="02b8e-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="02b8e-132">Ett räntebelopp anges för varje valuta i räntekoden.</span><span class="sxs-lookup"><span data-stu-id="02b8e-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="02b8e-133">Valfria räntebeloppsgränser kan anges.</span><span class="sxs-lookup"><span data-stu-id="02b8e-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="02b8e-134">**Belopp** väljs i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="02b8e-135">Om du till exempel vill ställa in en räntekod som värderas med 25,00 ränta för varje 20-dagarsperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 20 i fältet **Beräkna ränta var** och välj **Dag**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="02b8e-136">Räntesatser baserade på perioder</span><span class="sxs-lookup"><span data-stu-id="02b8e-136">Interest rates based on ranges</span></span>
<span data-ttu-id="02b8e-137">Du kan ställa in räntesatser som varierar beroende på det förfallna beloppet, antalet dagar som beloppet är försenat eller antalet månader som beloppet är försenat.</span><span class="sxs-lookup"><span data-stu-id="02b8e-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="02b8e-138">Du kan använda fliken **Resultaten per valuta** för att ange särskilda ränteinställningar för varje valuta.</span><span class="sxs-lookup"><span data-stu-id="02b8e-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="02b8e-139">Det är också där du definierar intervallet.</span><span class="sxs-lookup"><span data-stu-id="02b8e-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="02b8e-140">Använd knappen **Intervall** om du vill lägga till rader som motsvarar intervall som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="02b8e-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="02b8e-141">Värdet **Från** representerar starttiden för intervallet och talet **Räntevärde** representerar antingen ett procenttal eller ett belopp, beroende på valet i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.</span><span class="sxs-lookup"><span data-stu-id="02b8e-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="02b8e-142">Exempel 1: Ränta efter period = Belopp</span><span class="sxs-lookup"><span data-stu-id="02b8e-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="02b8e-143">Du kan ställa in en räntekod som beräknar ränta en gång var tredje månad som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="02b8e-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="02b8e-144">Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa beloppsintervall.</span><span class="sxs-lookup"><span data-stu-id="02b8e-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="02b8e-145">Räntevärdet ska vara 1 procent för fakturabelopp upp till 1.000,00, 2 procent för belopp från 1.001,00 till 5.000,00 och 3 procent för större än 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="02b8e-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="02b8e-146">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="02b8e-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="02b8e-147">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="02b8e-147">**Field name**</span></span>                  | <span data-ttu-id="02b8e-148">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="02b8e-149">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="02b8e-149">**Interest code**</span></span>               | <span data-ttu-id="02b8e-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="02b8e-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="02b8e-151">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="02b8e-151">**Calculate interest every**</span></span>    | <span data-ttu-id="02b8e-152">3/månad</span><span class="sxs-lookup"><span data-stu-id="02b8e-152">3/Month</span></span>         |
| <span data-ttu-id="02b8e-153">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="02b8e-153">**Interest by range**</span></span>           | <span data-ttu-id="02b8e-154">Belopp</span><span class="sxs-lookup"><span data-stu-id="02b8e-154">Amount</span></span>          |
| <span data-ttu-id="02b8e-155">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="02b8e-155">**Calculate interest based on**</span></span> | <span data-ttu-id="02b8e-156">Procent</span><span class="sxs-lookup"><span data-stu-id="02b8e-156">Percentage</span></span>      |

<span data-ttu-id="02b8e-157">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="02b8e-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="02b8e-158">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-158">**From value**</span></span> | <span data-ttu-id="02b8e-159">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="02b8e-160">0</span><span class="sxs-lookup"><span data-stu-id="02b8e-160">0</span></span>              | <span data-ttu-id="02b8e-161">1</span><span class="sxs-lookup"><span data-stu-id="02b8e-161">1</span></span>                  |
| <span data-ttu-id="02b8e-162">1,001</span><span class="sxs-lookup"><span data-stu-id="02b8e-162">1,001</span></span>          | <span data-ttu-id="02b8e-163">2</span><span class="sxs-lookup"><span data-stu-id="02b8e-163">2</span></span>                  |
| <span data-ttu-id="02b8e-164">5,001</span><span class="sxs-lookup"><span data-stu-id="02b8e-164">5,001</span></span>          | <span data-ttu-id="02b8e-165">3</span><span class="sxs-lookup"><span data-stu-id="02b8e-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="02b8e-166">Exempel 2: Ränta efter period = Dagar</span><span class="sxs-lookup"><span data-stu-id="02b8e-166">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="02b8e-167">Du kan ställa in en räntekod som beräknar ränta en gång för varje 15 dagar som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="02b8e-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="02b8e-168">Du ska basera beräkningen på ett räntevärde för ett belopp, efter stegvisa dagsintervall.</span><span class="sxs-lookup"><span data-stu-id="02b8e-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="02b8e-169">Räntavärdet blir 10,00 per 15 dagar under de första 60 dagar, 15,00 dagar per 15 dagar under 61 till 90 och 20,00 per 15 dagar från dag 91 och ska.</span><span class="sxs-lookup"><span data-stu-id="02b8e-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="02b8e-170">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="02b8e-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="02b8e-171">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="02b8e-171">**Field name**</span></span>                  | <span data-ttu-id="02b8e-172">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="02b8e-173">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="02b8e-173">**Interest code**</span></span>               | <span data-ttu-id="02b8e-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="02b8e-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="02b8e-175">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="02b8e-175">**Calculate interest every**</span></span>    | <span data-ttu-id="02b8e-176">15/dag</span><span class="sxs-lookup"><span data-stu-id="02b8e-176">15/Day</span></span>          |
| <span data-ttu-id="02b8e-177">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="02b8e-177">**Interest by range**</span></span>           | <span data-ttu-id="02b8e-178">Dagar</span><span class="sxs-lookup"><span data-stu-id="02b8e-178">Days</span></span>            |
| <span data-ttu-id="02b8e-179">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="02b8e-179">**Calculate interest based on**</span></span> | <span data-ttu-id="02b8e-180">Belopp</span><span class="sxs-lookup"><span data-stu-id="02b8e-180">Amount</span></span>          |

<span data-ttu-id="02b8e-181">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="02b8e-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="02b8e-182">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-182">**From value**</span></span> | <span data-ttu-id="02b8e-183">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="02b8e-184">0</span><span class="sxs-lookup"><span data-stu-id="02b8e-184">0</span></span>              | <span data-ttu-id="02b8e-185">10</span><span class="sxs-lookup"><span data-stu-id="02b8e-185">10</span></span>                 |
| <span data-ttu-id="02b8e-186">61</span><span class="sxs-lookup"><span data-stu-id="02b8e-186">61</span></span>             | <span data-ttu-id="02b8e-187">15</span><span class="sxs-lookup"><span data-stu-id="02b8e-187">15</span></span>                 |
| <span data-ttu-id="02b8e-188">91</span><span class="sxs-lookup"><span data-stu-id="02b8e-188">91</span></span>             | <span data-ttu-id="02b8e-189">20</span><span class="sxs-lookup"><span data-stu-id="02b8e-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="02b8e-190">Exempel 3: Ränta efter period = Månader</span><span class="sxs-lookup"><span data-stu-id="02b8e-190">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="02b8e-191">Du kan ställa in en räntekod som beräknar ränta en gång för varje månad som överskrider fakturans förfallodatum för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="02b8e-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="02b8e-192">Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa månadsintervall.</span><span class="sxs-lookup"><span data-stu-id="02b8e-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="02b8e-193">Räntevärdet ska vara 1,5 procent per månad för de första tre förfallna månaderna, 2,0 procent per månad för nästa tre månader och 2,5 procent per månad för varje månad efter det första halvåret.</span><span class="sxs-lookup"><span data-stu-id="02b8e-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="02b8e-194">Du ställer in räntekodfältvärdena på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="02b8e-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="02b8e-195">**Fältnamn**</span><span class="sxs-lookup"><span data-stu-id="02b8e-195">**Field name**</span></span>                  | <span data-ttu-id="02b8e-196">**Fältvärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="02b8e-197">**Räntekod**</span><span class="sxs-lookup"><span data-stu-id="02b8e-197">**Interest code**</span></span>               | <span data-ttu-id="02b8e-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="02b8e-198">1M%ByMth</span></span>        |
| <span data-ttu-id="02b8e-199">**Beräkna ränta var**</span><span class="sxs-lookup"><span data-stu-id="02b8e-199">**Calculate interest every**</span></span>    | <span data-ttu-id="02b8e-200">1/månad</span><span class="sxs-lookup"><span data-stu-id="02b8e-200">1/Month</span></span>         |
| <span data-ttu-id="02b8e-201">**Ränta per intervall**</span><span class="sxs-lookup"><span data-stu-id="02b8e-201">**Interest by range**</span></span>           | <span data-ttu-id="02b8e-202">Månader</span><span class="sxs-lookup"><span data-stu-id="02b8e-202">Months</span></span>          |
| <span data-ttu-id="02b8e-203">**Beräkna ränta baserat på**</span><span class="sxs-lookup"><span data-stu-id="02b8e-203">**Calculate interest based on**</span></span> | <span data-ttu-id="02b8e-204">Procent</span><span class="sxs-lookup"><span data-stu-id="02b8e-204">Percentage</span></span>      |

<span data-ttu-id="02b8e-205">Du ställer in information om intervall så här.</span><span class="sxs-lookup"><span data-stu-id="02b8e-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="02b8e-206">**Från-värde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-206">**From value**</span></span> | <span data-ttu-id="02b8e-207">**Räntevärde**</span><span class="sxs-lookup"><span data-stu-id="02b8e-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="02b8e-208">0</span><span class="sxs-lookup"><span data-stu-id="02b8e-208">0</span></span>              | <span data-ttu-id="02b8e-209">1.5</span><span class="sxs-lookup"><span data-stu-id="02b8e-209">1.5</span></span>                |
| <span data-ttu-id="02b8e-210">4</span><span class="sxs-lookup"><span data-stu-id="02b8e-210">4</span></span>              | <span data-ttu-id="02b8e-211">2</span><span class="sxs-lookup"><span data-stu-id="02b8e-211">2</span></span>                  |
| <span data-ttu-id="02b8e-212">7</span><span class="sxs-lookup"><span data-stu-id="02b8e-212">7</span></span>              | <span data-ttu-id="02b8e-213">2,5</span><span class="sxs-lookup"><span data-stu-id="02b8e-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="02b8e-214">Nya versioner</span><span class="sxs-lookup"><span data-stu-id="02b8e-214">New versions</span></span>
<span data-ttu-id="02b8e-215">Räntekoder har giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="02b8e-215">Interest codes are date effective.</span></span> <span data-ttu-id="02b8e-216">Om du vill ändra räntesatsen kan du skapa en **ny version** som gäller för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="02b8e-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="02b8e-217">Om du vill visa andra versioner kan du använda menyvalet **Från och med (datum)** för att välja slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="02b8e-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="02b8e-218">Du kan också markera **Visa alla poster** för att visa alla räntekoder på sidan.</span><span class="sxs-lookup"><span data-stu-id="02b8e-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
