---
title: 175 procent degressiv avskrivning
description: Det här ämnet ger en översikt över 175-procentsmetoden för degressiv avskrivning.
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a63293dbf24c27733f8013947aeab5792fa0db9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570209"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="db0ae-103">175 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="db0ae-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db0ae-104">Det här ämnet ger en översikt över 175-procentsmetoden för degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="db0ae-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="db0ae-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **175 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="db0ae-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="db0ae-106">Om du vill ställa in 175% degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="db0ae-107">De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="db0ae-108">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="db0ae-108">Select a depreciation year</span></span>
<span data-ttu-id="db0ae-109">Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="db0ae-110">Standardvärdet är **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="db0ae-111">Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="db0ae-112">Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="db0ae-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="db0ae-113">Kalender</span><span class="sxs-lookup"><span data-stu-id="db0ae-113">Calendar</span></span>

<span data-ttu-id="db0ae-114">Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="db0ae-115">Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="db0ae-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="db0ae-116">Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet.</span><span class="sxs-lookup"><span data-stu-id="db0ae-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="db0ae-117">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="db0ae-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="db0ae-118">Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="db0ae-119">**Årlig** bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="db0ae-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="db0ae-120">**Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.</span><span class="sxs-lookup"><span data-stu-id="db0ae-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="db0ae-121">**Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="db0ae-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="db0ae-122">**Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="db0ae-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="db0ae-123">**Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="db0ae-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="db0ae-124">Skatt</span><span class="sxs-lookup"><span data-stu-id="db0ae-124">Fiscal</span></span>

<span data-ttu-id="db0ae-125">Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 175 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="db0ae-126">Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="db0ae-127">Mer information finns i [Räkenskapskalendrar, räkenskapsår och perioder](../budgeting/fiscal-calendars-fiscal-years-periods.md)</span><span class="sxs-lookup"><span data-stu-id="db0ae-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="db0ae-128">För räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="db0ae-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="db0ae-129">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="db0ae-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="db0ae-130">Avskrivningen justeras automatiskt för varje period och längden på nästa räkenskapsår bestäms av perioderna som ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="db0ae-131">Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:</span><span class="sxs-lookup"><span data-stu-id="db0ae-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="db0ae-132">**Årlig** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="db0ae-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="db0ae-133">**Räkenskapsperiod** beräknar det totala avskrivningsbeloppet för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="db0ae-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="db0ae-134">Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="db0ae-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="db0ae-135">Exempel på en degressiv avskrivning på 175 %</span><span class="sxs-lookup"><span data-stu-id="db0ae-135">Example of 175% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="db0ae-136">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="db0ae-136">Acquisition cost</span></span>               | <span data-ttu-id="db0ae-137">11 000</span><span class="sxs-lookup"><span data-stu-id="db0ae-137">11,000</span></span> |
| <span data-ttu-id="db0ae-138">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="db0ae-138">Salvage value</span></span>                  | <span data-ttu-id="db0ae-139">1 000</span><span class="sxs-lookup"><span data-stu-id="db0ae-139">1,000</span></span>  |
| <span data-ttu-id="db0ae-140">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="db0ae-140">Depreciation base</span></span>              | <span data-ttu-id="db0ae-141">10 000</span><span class="sxs-lookup"><span data-stu-id="db0ae-141">10,000</span></span> |
| <span data-ttu-id="db0ae-142">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="db0ae-142">Service life years</span></span>             | <span data-ttu-id="db0ae-143">5</span><span class="sxs-lookup"><span data-stu-id="db0ae-143">5</span></span>      |
| <span data-ttu-id="db0ae-144">Årlig avskrivningsprocent</span><span class="sxs-lookup"><span data-stu-id="db0ae-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="db0ae-145">35 %</span><span class="sxs-lookup"><span data-stu-id="db0ae-145">35%</span></span>    |

<span data-ttu-id="db0ae-146">Den degressiva avskrivningsmetoden på 175 % delar 175 procent med tjänstelivstiden i år.</span><span class="sxs-lookup"><span data-stu-id="db0ae-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="db0ae-147">Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="db0ae-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="db0ae-148">Period</span><span class="sxs-lookup"><span data-stu-id="db0ae-148">Period</span></span> | <span data-ttu-id="db0ae-149">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="db0ae-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="db0ae-150">Bokfört värde</span><span class="sxs-lookup"><span data-stu-id="db0ae-150">Book value</span></span>                  | <span data-ttu-id="db0ae-151">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="db0ae-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="db0ae-152">År 1</span><span class="sxs-lookup"><span data-stu-id="db0ae-152">Year 1</span></span> | <span data-ttu-id="db0ae-153">(11 000 - 1 000) × 35 % = 3 500</span><span class="sxs-lookup"><span data-stu-id="db0ae-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="db0ae-154">11 000 - 3 500 = 7 500</span><span class="sxs-lookup"><span data-stu-id="db0ae-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="db0ae-155">11 000 - 1 000 – 3 500 = 6 500</span><span class="sxs-lookup"><span data-stu-id="db0ae-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="db0ae-156">År 2</span><span class="sxs-lookup"><span data-stu-id="db0ae-156">Year 2</span></span> | <span data-ttu-id="db0ae-157">6 500 × 35 % = 2 275</span><span class="sxs-lookup"><span data-stu-id="db0ae-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="db0ae-158">7 500 - 2 275 = 5 225</span><span class="sxs-lookup"><span data-stu-id="db0ae-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="db0ae-159">6 500 - 2 275 = 4 225</span><span class="sxs-lookup"><span data-stu-id="db0ae-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="db0ae-160">År 3</span><span class="sxs-lookup"><span data-stu-id="db0ae-160">Year 3</span></span> | <span data-ttu-id="db0ae-161">4 225 × 35 % = 1 478,75</span><span class="sxs-lookup"><span data-stu-id="db0ae-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="db0ae-162">5 225 - 1 478,75 = 3 746,25</span><span class="sxs-lookup"><span data-stu-id="db0ae-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="db0ae-163">4,225 - 1 478,75 = 2 746,25</span><span class="sxs-lookup"><span data-stu-id="db0ae-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="db0ae-164">Om beloppet som beräknas med den degressiva avskrivningsmetoden 175 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="db0ae-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



