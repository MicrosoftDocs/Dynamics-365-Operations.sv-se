---
title: "Linjär avskrivning av tjänstelivstid"
description: "Det här avsnittet ger en översikt över metoden för linjär tjänstelivstid för avskrivning."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: b48cf3970379f8dd2ea529cd8a434c0bdc196a1e
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="straight-line-service-life-depreciation"></a><span data-ttu-id="def28-103">Linjär avskrivning av tjänstelivstid</span><span class="sxs-lookup"><span data-stu-id="def28-103">Straight line service life depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="def28-104">Det här avsnittet ger en översikt över metoden för linjär tjänstelivstid för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="def28-104">This article gives an overview of the Straight line service life method of depreciation.</span></span>

<span data-ttu-id="def28-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer Linjär återstående tjänstelivstid i fältet Metod på sidan Avskrivningsprofiler baseras avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen på tillgångens totala tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="def28-105">When you set up a fixed asset depreciation profile and select Straight line service life in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated based on the total service life of the asset.</span></span> <span data-ttu-id="def28-106">Det är vanligtvis samma avskrivningsbelopp i varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="def28-106">This generally is the same depreciation amount in each depreciation period.</span></span> 

<span data-ttu-id="def28-107">Avskrivningsbelopp som beräknas mellan återstående linjär tjänstelivstid och linjär tjänstelivstid skiljer sig endast då en justering har bokförts för tillgången.</span><span class="sxs-lookup"><span data-stu-id="def28-107">The difference in the depreciation amount that is calculated between straight line service life remaining and straight line service life is when there is an adjustment posted to the asset.</span></span> 

<span data-ttu-id="def28-108">Om du vill ställa in linjär avskrivning kvarstående tjänstelivstid måste du också markera alternativ i fältet Avskrivningsår och fältet Periodfrekvens på sidan Avskrivningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="def28-108">To set up straight line service life depreciation, you must also select options in the Depreciation year and Period frequency fields in the Depreciation profiles page.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="def28-109">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="def28-109">Select a depreciation year</span></span>
<span data-ttu-id="def28-110">Du kan välja Kalender eller Räkenskapsår i fältet Avskrivningår på sidan Avskrivningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="def28-110">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="def28-111">Valet avgör vilka alternativ som är tillgängliga i fältet Periodfrekvens.</span><span class="sxs-lookup"><span data-stu-id="def28-111">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="def28-112">Standardalternativet är Kalender.</span><span class="sxs-lookup"><span data-stu-id="def28-112">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="def28-113">Kalender</span><span class="sxs-lookup"><span data-stu-id="def28-113">Calendar</span></span>

<span data-ttu-id="def28-114">När du väljer Kalender blir kalenderåret 1 januari till 31 december, även om du har gjort andra inställningar för räkenskapskalender.</span><span class="sxs-lookup"><span data-stu-id="def28-114">If you select Calendar, a year of January 1 to December 31 is assumed, even if you have defined the fiscal calendar differently.</span></span> 

<span data-ttu-id="def28-115">Med alternativet Kalender uppdaterar du avskrivningsbasen som vanligtvis är bokfört nettovärde minus skrotvärde, den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="def28-115">The Calendar option updates the depreciation base, which is typically the net book value minus the salvage value, on January 1 of each year.</span></span> <span data-ttu-id="def28-116">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="def28-116">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="def28-117">Om du väljer Kalender är följande alternativ tillgängliga i fältet Periodfrekvens, som definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret:</span><span class="sxs-lookup"><span data-stu-id="def28-117">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>
-   <span data-ttu-id="def28-118">Årlig bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="def28-118">Yearly posts an amount on December 31.</span></span>
-   <span data-ttu-id="def28-119">Månadsvis bokför ett månatligt belopp i slutet av varje månad.</span><span class="sxs-lookup"><span data-stu-id="def28-119">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="def28-120">Kvartalvis bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="def28-120">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="def28-121">Halvårsvis bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="def28-121">Half-Yearly posts a half-yearly amount at the end of each calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="def28-122">Dagligen bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="def28-122">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="def28-123">Om du till exempel väljer Årligen, bokförs årets avskrivning alltså bara en gång, den 31 december varje år.</span><span class="sxs-lookup"><span data-stu-id="def28-123">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="def28-124">Om du väljer Månadsvis, bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="def28-124">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="def28-125">Skatt</span><span class="sxs-lookup"><span data-stu-id="def28-125">Fiscal</span></span>

<span data-ttu-id="def28-126">Om du väljer Räkenskapsår i fältet Avskrivningsår används linjär avskrivning av tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="def28-126">If you select Fiscal in the Depreciation year field, the straight line service life depreciation is used.</span></span> <span data-ttu-id="def28-127">Den beräknas utifrån räkenskapsåret, som definieras av den räkenskapskalender som anges för boken, eller utifrån räkenskapskalendern som valts på sidan Redovisning.</span><span class="sxs-lookup"><span data-stu-id="def28-127">It is calculated based on the fiscal year, which is defined by the fiscal calendar that is specified for the book, or by the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="def28-128">Räkenskapskalendrar ställs in på sidan Räkenskapskalendrar.</span><span class="sxs-lookup"><span data-stu-id="def28-128">Fiscal calendars are set up in the Fiscal calendars page.</span></span>

<span data-ttu-id="def28-129">Exempelvis för räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="def28-129">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="def28-130">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="def28-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="def28-131">Avskrivningen justeras automatiskt för varje räkenskapsperiod.</span><span class="sxs-lookup"><span data-stu-id="def28-131">The depreciation automatically is adjusted for each fiscal period.</span></span> <span data-ttu-id="def28-132">Längden på nästa räkenskapsår baseras på de räkenskapsperioder som du ställer in när du skapar ett nytt räkenskapsår i formuläret Räkenskapskalendrar.</span><span class="sxs-lookup"><span data-stu-id="def28-132">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars form.</span></span> 

<span data-ttu-id="def28-133">Om du väljer Räkenskapsår har du följande alternativ i fältet Räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="def28-133">If you select Fiscal, the following options are available in the Period frequency field:</span></span>
-   <span data-ttu-id="def28-134">Årligen bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="def28-134">Yearly posts the total amount of the depreciation that is calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="def28-135">Räkenskapsperiod beräknar det totala avskrivningsbeloppet för räkenskapsåret, som periodiseras till de räkenskapsperioder som har definierats i formuläret Räkenskapsperiod för räkenskapskalendern.</span><span class="sxs-lookup"><span data-stu-id="def28-135">Fiscal period calculates the total amount of the depreciation for the fiscal year, which is accrued into the periods that are defined in the Fiscal calendars form for the fiscal calendar.</span></span>

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a><span data-ttu-id="def28-136">Exempel: Linjär avskrivning av en oförändrad anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="def28-136">Example: Straight line depreciation of an unchanged fixed asset</span></span>
<span data-ttu-id="def28-137">Anta att anläggningstillgången har följande egenskaper.</span><span class="sxs-lookup"><span data-stu-id="def28-137">Suppose that a fixed asset has the following characteristics.</span></span>

|                     |        |
|---------------------|--------|
| <span data-ttu-id="def28-138">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="def28-138">Acquisition cost</span></span>    | <span data-ttu-id="def28-139">11 000</span><span class="sxs-lookup"><span data-stu-id="def28-139">11,000</span></span> |
| <span data-ttu-id="def28-140">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="def28-140">Salvage value</span></span>       | <span data-ttu-id="def28-141">1 000</span><span class="sxs-lookup"><span data-stu-id="def28-141">1,000</span></span>  |
| <span data-ttu-id="def28-142">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="def28-142">Depreciation base</span></span>   | <span data-ttu-id="def28-143">10 000</span><span class="sxs-lookup"><span data-stu-id="def28-143">10,000</span></span> |
| <span data-ttu-id="def28-144">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="def28-144">Service life years</span></span>  | <span data-ttu-id="def28-145">5</span><span class="sxs-lookup"><span data-stu-id="def28-145">5</span></span>      |
| <span data-ttu-id="def28-146">Årlig avskrivning</span><span class="sxs-lookup"><span data-stu-id="def28-146">Yearly depreciation</span></span> | <span data-ttu-id="def28-147">2 000</span><span class="sxs-lookup"><span data-stu-id="def28-147">2,000</span></span>  |

<span data-ttu-id="def28-148">Samma avskrivningsbelopp varje år.</span><span class="sxs-lookup"><span data-stu-id="def28-148">You get the same depreciation amount each year.</span></span> <span data-ttu-id="def28-149">(Anskaffningskostnad - skrotvärde)/tjänstelivstidsår</span><span class="sxs-lookup"><span data-stu-id="def28-149">(Acquisition cost - Salvage value) / Service life years</span></span>

| <span data-ttu-id="def28-150">Period</span><span class="sxs-lookup"><span data-stu-id="def28-150">Period</span></span> | <span data-ttu-id="def28-151">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="def28-151">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="def28-152">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="def28-152">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="def28-153">År 1</span><span class="sxs-lookup"><span data-stu-id="def28-153">Year 1</span></span> | <span data-ttu-id="def28-154">(11 000 - 1 000) / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-154">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="def28-155">9 000</span><span class="sxs-lookup"><span data-stu-id="def28-155">9,000</span></span>                                 |
| <span data-ttu-id="def28-156">År 2</span><span class="sxs-lookup"><span data-stu-id="def28-156">Year 2</span></span> | <span data-ttu-id="def28-157">(11 000 - 1 000) / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-157">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="def28-158">7 000</span><span class="sxs-lookup"><span data-stu-id="def28-158">7,000</span></span>                                 |
| <span data-ttu-id="def28-159">År 3</span><span class="sxs-lookup"><span data-stu-id="def28-159">Year 3</span></span> | <span data-ttu-id="def28-160">(11 000 - 1 000) / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-160">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="def28-161">5 000</span><span class="sxs-lookup"><span data-stu-id="def28-161">5,000</span></span>                                 |
| <span data-ttu-id="def28-162">År 4</span><span class="sxs-lookup"><span data-stu-id="def28-162">Year 4</span></span> | <span data-ttu-id="def28-163">(11 000 - 1 000) / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-163">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="def28-164">3 000</span><span class="sxs-lookup"><span data-stu-id="def28-164">3,000</span></span>                                 |
| <span data-ttu-id="def28-165">År 5</span><span class="sxs-lookup"><span data-stu-id="def28-165">Year 5</span></span> | <span data-ttu-id="def28-166">(11 000 - 1 000) / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-166">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="def28-167">1 000</span><span class="sxs-lookup"><span data-stu-id="def28-167">1,000</span></span>                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a><span data-ttu-id="def28-168">Exempel: Linjär avskrivning av en förändrad anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="def28-168">Example: Straight line depreciation of a modified fixed asset</span></span>

<span data-ttu-id="def28-169">Antag att du lägger till en anskaffningsjustering på 4 000 under år 2 till samma anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="def28-169">Suppose that you add an acquisition adjustment of 4,000 in year 2 to the same fixed asset.</span></span> 

<span data-ttu-id="def28-170">Anskaffningsjusteringens tjänstelivstid är samma som anläggningstillgångens och påbörjas vid anskaffning.</span><span class="sxs-lookup"><span data-stu-id="def28-170">The service life of the acquisition adjustment is the same as that of the fixed asset and starts at the time of its acquisition.</span></span> <span data-ttu-id="def28-171">Vid slutet av år 5 återstår ett bokfört nettovärde som motsvarar anskaffningsjusteringens bokförda nettovärde.</span><span class="sxs-lookup"><span data-stu-id="def28-171">A net book value remains at the end of year 5, corresponding to the net book value of the acquisition adjustment.</span></span> <span data-ttu-id="def28-172">Följande tabell visar hur avskrivning per period beräknas.</span><span class="sxs-lookup"><span data-stu-id="def28-172">The depreciation by period is calculated as shown in the following table.</span></span>

| <span data-ttu-id="def28-173">Period</span><span class="sxs-lookup"><span data-stu-id="def28-173">Period</span></span> | <span data-ttu-id="def28-174">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="def28-174">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="def28-175">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="def28-175">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="def28-176">År 1</span><span class="sxs-lookup"><span data-stu-id="def28-176">Year 1</span></span> | <span data-ttu-id="def28-177">10 000 / 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="def28-177">10,000 / 5 = 2,000</span></span>                        | <span data-ttu-id="def28-178">11 000 - 2 000 = 9 000</span><span class="sxs-lookup"><span data-stu-id="def28-178">11,000 - 2,000 = 9,000</span></span>                |
| <span data-ttu-id="def28-179">År 2</span><span class="sxs-lookup"><span data-stu-id="def28-179">Year 2</span></span> | <span data-ttu-id="def28-180">4 000 (anskaffningsjustering)</span><span class="sxs-lookup"><span data-stu-id="def28-180">4,000 (acquisition adjustment)</span></span>            | <span data-ttu-id="def28-181">9 000 + 4 000 =13 000</span><span class="sxs-lookup"><span data-stu-id="def28-181">9,000 + 4,000 =13,000</span></span>                 |
| <span data-ttu-id="def28-182">År 2</span><span class="sxs-lookup"><span data-stu-id="def28-182">Year 2</span></span> | <span data-ttu-id="def28-183">14 000 / 5 = 2 800</span><span class="sxs-lookup"><span data-stu-id="def28-183">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="def28-184">13 000 - 2 800 = 10 200</span><span class="sxs-lookup"><span data-stu-id="def28-184">13,000 - 2,800 = 10,200</span></span>               |
| <span data-ttu-id="def28-185">År 3</span><span class="sxs-lookup"><span data-stu-id="def28-185">Year 3</span></span> | <span data-ttu-id="def28-186">14 000 / 5 = 2 800</span><span class="sxs-lookup"><span data-stu-id="def28-186">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="def28-187">10 200 - 2 800 = 7 400</span><span class="sxs-lookup"><span data-stu-id="def28-187">10,200 - 2,800 = 7,400</span></span>                |
| <span data-ttu-id="def28-188">År 4</span><span class="sxs-lookup"><span data-stu-id="def28-188">Year 4</span></span> | <span data-ttu-id="def28-189">14 000 / 5 = 2 800</span><span class="sxs-lookup"><span data-stu-id="def28-189">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="def28-190">7 400 - 2 800 = 4 600</span><span class="sxs-lookup"><span data-stu-id="def28-190">7,400 - 2,800 = 4,600</span></span>                 |
| <span data-ttu-id="def28-191">År 5</span><span class="sxs-lookup"><span data-stu-id="def28-191">Year 5</span></span> | <span data-ttu-id="def28-192">14 000 / 5 = 2 800</span><span class="sxs-lookup"><span data-stu-id="def28-192">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="def28-193">4 600 - 2 800 = 1 800</span><span class="sxs-lookup"><span data-stu-id="def28-193">4,600 - 2,800 = 1,800</span></span>                 |
| <span data-ttu-id="def28-194">År 6</span><span class="sxs-lookup"><span data-stu-id="def28-194">Year 6</span></span> | <span data-ttu-id="def28-195">Resterande 800\*</span><span class="sxs-lookup"><span data-stu-id="def28-195">Remaining 800\*</span></span>                           | <span data-ttu-id="def28-196">1 800 – 800 = 1 000</span><span class="sxs-lookup"><span data-stu-id="def28-196">1,800 – 800 = 1,000</span></span>                   |

<span data-ttu-id="def28-197">\*Eftersom det resterande beloppet är mindre än avskrivningsbeloppet hämtas endast det resterande beloppet minus skrotvärdet.</span><span class="sxs-lookup"><span data-stu-id="def28-197">\*Because the remaining amount is less than the depreciation amount, only the remaining amount minus the salvage value is taken.</span></span>






