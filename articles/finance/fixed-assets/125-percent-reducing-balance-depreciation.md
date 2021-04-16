---
title: 125 procent degressiv avskrivning
description: Den här avsnittet ger en översikt över 125-procentsmetoden för degressiv avskrivning.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d05ec02d47a563c0d7ae7cb0fafdbad45bd140
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827204"
---
# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="3d36d-103">125 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="3d36d-103">125 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d36d-104">Den här avsnittet ger en översikt över 125-procentsmetoden för degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="3d36d-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="3d36d-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **125 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="3d36d-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="3d36d-106">Denna procentsats beräknas baserat på tillgångens tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="3d36d-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="3d36d-107">Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 25 procent (125 % ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="3d36d-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="3d36d-108">Om du vill ställa in 125 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="3d36d-109">De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="3d36d-110">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="3d36d-110">Select a depreciation year</span></span>
<span data-ttu-id="3d36d-111">Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="3d36d-112">Standardvärdet är **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="3d36d-113">Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="3d36d-114">Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="3d36d-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="3d36d-115">Kalender</span><span class="sxs-lookup"><span data-stu-id="3d36d-115">Calendar</span></span>

<span data-ttu-id="3d36d-116">Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="3d36d-117">Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="3d36d-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="3d36d-118">Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet.</span><span class="sxs-lookup"><span data-stu-id="3d36d-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="3d36d-119">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="3d36d-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="3d36d-120">Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="3d36d-121">**Årlig** bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="3d36d-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="3d36d-122">**Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.</span><span class="sxs-lookup"><span data-stu-id="3d36d-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="3d36d-123">**Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="3d36d-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="3d36d-124">**Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="3d36d-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="3d36d-125">**Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="3d36d-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="3d36d-126">Skatt</span><span class="sxs-lookup"><span data-stu-id="3d36d-126">Fiscal</span></span>

<span data-ttu-id="3d36d-127">Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 125 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="3d36d-128">Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="3d36d-129">För räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="3d36d-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="3d36d-130">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="3d36d-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="3d36d-131">Avskrivningen justeras automatiskt för varje period och längden på nästa räkenskapsår bestäms av perioderna som ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="3d36d-132">Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:</span><span class="sxs-lookup"><span data-stu-id="3d36d-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="3d36d-133">**Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="3d36d-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="3d36d-134">**Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="3d36d-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="3d36d-135">Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="3d36d-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="3d36d-136">Exempel på en degressiv avskrivning på 125 %</span><span class="sxs-lookup"><span data-stu-id="3d36d-136">Example of 125% reducing balance depreciation</span></span>

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| <span data-ttu-id="3d36d-137">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="3d36d-137">Acquisition cost</span></span>               | <span data-ttu-id="3d36d-138">11 000</span><span class="sxs-lookup"><span data-stu-id="3d36d-138">11,000</span></span> |
| <span data-ttu-id="3d36d-139">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="3d36d-139">Salvage value</span></span>                  | <span data-ttu-id="3d36d-140">1 000</span><span class="sxs-lookup"><span data-stu-id="3d36d-140">1,000</span></span>  |
| <span data-ttu-id="3d36d-141">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="3d36d-141">Depreciation base</span></span>              | <span data-ttu-id="3d36d-142">10 000</span><span class="sxs-lookup"><span data-stu-id="3d36d-142">10,000</span></span> |
| <span data-ttu-id="3d36d-143">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="3d36d-143">Service life years</span></span>             | <span data-ttu-id="3d36d-144">5</span><span class="sxs-lookup"><span data-stu-id="3d36d-144">5</span></span>      |
| <span data-ttu-id="3d36d-145">Årlig avskrivningsprocent</span><span class="sxs-lookup"><span data-stu-id="3d36d-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="3d36d-146">25 %</span><span class="sxs-lookup"><span data-stu-id="3d36d-146">25%</span></span>    |

<span data-ttu-id="3d36d-147">Den degressiva avskrivningsmetoden på 125 % delar 125 procent med tjänstelivstiden i år.</span><span class="sxs-lookup"><span data-stu-id="3d36d-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="3d36d-148">Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="3d36d-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="3d36d-149">Period</span><span class="sxs-lookup"><span data-stu-id="3d36d-149">Period</span></span> | <span data-ttu-id="3d36d-150">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="3d36d-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="3d36d-151">Bokfört värde</span><span class="sxs-lookup"><span data-stu-id="3d36d-151">Book value</span></span>                    | <span data-ttu-id="3d36d-152">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="3d36d-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="3d36d-153">År 1</span><span class="sxs-lookup"><span data-stu-id="3d36d-153">Year 1</span></span> | <span data-ttu-id="3d36d-154">(11 000 – 1 000) × 25 % = 2 500</span><span class="sxs-lookup"><span data-stu-id="3d36d-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="3d36d-155">(11 000 – 2 500) = 8 500</span><span class="sxs-lookup"><span data-stu-id="3d36d-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="3d36d-156">(11 000 – 1 000 – 2 500) = 7 500</span><span class="sxs-lookup"><span data-stu-id="3d36d-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="3d36d-157">År 2</span><span class="sxs-lookup"><span data-stu-id="3d36d-157">Year 2</span></span> | <span data-ttu-id="3d36d-158">7 500 × 25 % = 1 875</span><span class="sxs-lookup"><span data-stu-id="3d36d-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="3d36d-159">(8 500 – 1 875) = 6 625</span><span class="sxs-lookup"><span data-stu-id="3d36d-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="3d36d-160">(7 500 – 1 875) = 5 625</span><span class="sxs-lookup"><span data-stu-id="3d36d-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="3d36d-161">År 3</span><span class="sxs-lookup"><span data-stu-id="3d36d-161">Year 3</span></span> | <span data-ttu-id="3d36d-162">5 625 × 25 % = 1 406,25</span><span class="sxs-lookup"><span data-stu-id="3d36d-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="3d36d-163">(6 625 – 1 406,25) = 5 218,75</span><span class="sxs-lookup"><span data-stu-id="3d36d-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="3d36d-164">(5 625 – 1 406,25) = 4 218,75</span><span class="sxs-lookup"><span data-stu-id="3d36d-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="3d36d-165">Om beloppet som beräknas med den degressiva avskrivningsmetoden 125 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="3d36d-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]