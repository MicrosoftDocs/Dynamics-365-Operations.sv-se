---
title: 200 procent degressiv avskrivning
description: Den här artikeln ger en översikt över 200-procentsmetoden för degressiv avskrivning.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91876ae28d088a52b12ac58db06cb0cd84b129ad
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193526"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="bf73f-103">200 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="bf73f-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf73f-104">Den här artikeln ger en översikt över 200-procentsmetoden för degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="bf73f-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="bf73f-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **200 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="bf73f-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="bf73f-106">Denna procentsats beräknas baserat på tillgångens tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="bf73f-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="bf73f-107">Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 40 procent (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="bf73f-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="bf73f-108">Denna metod kallas också för dubbel degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="bf73f-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="bf73f-109">Om du vill ställa in 200 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="bf73f-110">De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="bf73f-111">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="bf73f-111">Select a depreciation year</span></span>
<span data-ttu-id="bf73f-112">Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="bf73f-113">Standardvärdet är **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="bf73f-114">Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="bf73f-115">Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="bf73f-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="bf73f-116">Kalender</span><span class="sxs-lookup"><span data-stu-id="bf73f-116">Calendar</span></span>

<span data-ttu-id="bf73f-117">Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="bf73f-118">Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="bf73f-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="bf73f-119">Generellt är avskrivningen bokfört nettovärde minus kassationsvärdet.</span><span class="sxs-lookup"><span data-stu-id="bf73f-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="bf73f-120">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="bf73f-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="bf73f-121">Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="bf73f-122">**Årlig** bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="bf73f-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="bf73f-123">**Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.</span><span class="sxs-lookup"><span data-stu-id="bf73f-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="bf73f-124">**Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="bf73f-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="bf73f-125">**Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="bf73f-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="bf73f-126">**Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="bf73f-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="bf73f-127">Skatt</span><span class="sxs-lookup"><span data-stu-id="bf73f-127">Fiscal</span></span>

<span data-ttu-id="bf73f-128">Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 200 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="bf73f-129">Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="bf73f-130">För räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="bf73f-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="bf73f-131">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="bf73f-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="bf73f-132">Avskrivningen justeras för varje period.</span><span class="sxs-lookup"><span data-stu-id="bf73f-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="bf73f-133">Längden på nästa räkenskapsår bestäms av inställningen för perioder på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="bf73f-134">Om du väljer **Skatt** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:</span><span class="sxs-lookup"><span data-stu-id="bf73f-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="bf73f-135">**Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="bf73f-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="bf73f-136">**Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="bf73f-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="bf73f-137">Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="bf73f-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="bf73f-138">Exempel på en degressiv avskrivning på 200 %</span><span class="sxs-lookup"><span data-stu-id="bf73f-138">Example of 200% reducing balance depreciation</span></span>

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| <span data-ttu-id="bf73f-139">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="bf73f-139">Acquisition cost</span></span>               | <span data-ttu-id="bf73f-140">11 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-140">11,000</span></span> |
| <span data-ttu-id="bf73f-141">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="bf73f-141">Salvage value</span></span>                  | <span data-ttu-id="bf73f-142">1 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-142">1, 000</span></span> |
| <span data-ttu-id="bf73f-143">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="bf73f-143">Depreciation base</span></span>              | <span data-ttu-id="bf73f-144">10 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-144">10,000</span></span> |
| <span data-ttu-id="bf73f-145">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="bf73f-145">Service life years</span></span>             | <span data-ttu-id="bf73f-146">5</span><span class="sxs-lookup"><span data-stu-id="bf73f-146">5</span></span>      |
| <span data-ttu-id="bf73f-147">Årlig avskrivningsprocent</span><span class="sxs-lookup"><span data-stu-id="bf73f-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="bf73f-148">40 %</span><span class="sxs-lookup"><span data-stu-id="bf73f-148">40%</span></span>    |

<span data-ttu-id="bf73f-149">Den degressiva avskrivningsmetoden på 200 % delar 200 procent med tjänstelivstiden i år.</span><span class="sxs-lookup"><span data-stu-id="bf73f-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="bf73f-150">Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="bf73f-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="bf73f-151">Period</span><span class="sxs-lookup"><span data-stu-id="bf73f-151">Period</span></span> | <span data-ttu-id="bf73f-152">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="bf73f-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="bf73f-153">Bokfört värde</span><span class="sxs-lookup"><span data-stu-id="bf73f-153">Book value</span></span>             | <span data-ttu-id="bf73f-154">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="bf73f-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="bf73f-155">År 1</span><span class="sxs-lookup"><span data-stu-id="bf73f-155">Year 1</span></span> | <span data-ttu-id="bf73f-156">(11 000 – 1 000) × 40 % = 4 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="bf73f-157">11 000 – 4 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="bf73f-158">11 000 – 1 000 – 4 000 = 6 000</span><span class="sxs-lookup"><span data-stu-id="bf73f-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="bf73f-159">År 2</span><span class="sxs-lookup"><span data-stu-id="bf73f-159">Year 2</span></span> | <span data-ttu-id="bf73f-160">6 000 × 40 % = 2 400</span><span class="sxs-lookup"><span data-stu-id="bf73f-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="bf73f-161">7 000 – 2 400 = 4 600</span><span class="sxs-lookup"><span data-stu-id="bf73f-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="bf73f-162">6 000 – 2 400 = 3 600</span><span class="sxs-lookup"><span data-stu-id="bf73f-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="bf73f-163">År 3</span><span class="sxs-lookup"><span data-stu-id="bf73f-163">Year 3</span></span> | <span data-ttu-id="bf73f-164">3 600 × 40 % = 1 440</span><span class="sxs-lookup"><span data-stu-id="bf73f-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="bf73f-165">4 600 – 1 440 = 3 160</span><span class="sxs-lookup"><span data-stu-id="bf73f-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="bf73f-166">3 600 – 1 440 = 2 160</span><span class="sxs-lookup"><span data-stu-id="bf73f-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="bf73f-167">Om beloppet som beräknas med den degressiva avskrivningsmetoden 200 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="bf73f-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]