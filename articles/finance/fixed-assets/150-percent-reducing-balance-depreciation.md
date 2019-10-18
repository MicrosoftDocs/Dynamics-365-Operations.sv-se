---
title: 150 procent degressiv avskrivning
description: Det här avsnittet ger en översikt över 150-procentsmetoden för degressiv avskrivning.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a132a8d6e5eaf0dad54133fc9d0c12dcf5866c7c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179958"
---
# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="e9ba9-103">150 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="e9ba9-103">150 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e9ba9-104">Det här avsnittet ger en översikt över 150-procentsmetoden för degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="e9ba9-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **150 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="e9ba9-106">Denna procentsats beräknas baserat på tillgångens tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="e9ba9-107">Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 30 procent (150 % ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="e9ba9-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="e9ba9-108">Om du vill ställa in 150 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="e9ba9-109">De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="e9ba9-110">Val av avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="e9ba9-110">Selection of depreciation year</span></span>
<span data-ttu-id="e9ba9-111">Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="e9ba9-112">Standardvärdet är **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-112">The default value is **Calendar**.</span></span> <span data-ttu-id="e9ba9-113">Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="e9ba9-114">Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="e9ba9-115">Kalender</span><span class="sxs-lookup"><span data-stu-id="e9ba9-115">Calendar</span></span>

<span data-ttu-id="e9ba9-116">Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="e9ba9-117">Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="e9ba9-118">Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="e9ba9-119">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="e9ba9-120">Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="e9ba9-121">**Årlig** bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="e9ba9-122">**Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="e9ba9-123">**Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="e9ba9-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="e9ba9-124">**Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="e9ba9-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="e9ba9-125">**Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="e9ba9-126">Skatt</span><span class="sxs-lookup"><span data-stu-id="e9ba9-126">Fiscal</span></span>

<span data-ttu-id="e9ba9-127">Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 150 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="e9ba9-128">Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="e9ba9-129">För räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="e9ba9-130">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="e9ba9-131">Avskrivningen justeras för varje period.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="e9ba9-132">Längden på nästa räkenskapsår bestäms av inställningen för perioder på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="e9ba9-133">Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:</span><span class="sxs-lookup"><span data-stu-id="e9ba9-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="e9ba9-134">**Årlig** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="e9ba9-135">**Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="e9ba9-136">Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="e9ba9-137">Exempel på 150 % degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="e9ba9-137">Example of 150% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="e9ba9-138">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="e9ba9-138">Acquisition cost</span></span>               | <span data-ttu-id="e9ba9-139">11 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-139">11,000</span></span> |
| <span data-ttu-id="e9ba9-140">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="e9ba9-140">Salvage value</span></span>                  | <span data-ttu-id="e9ba9-141">1 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-141">1,000</span></span>  |
| <span data-ttu-id="e9ba9-142">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="e9ba9-142">Depreciation base</span></span>              | <span data-ttu-id="e9ba9-143">10 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-143">10,000</span></span> |
| <span data-ttu-id="e9ba9-144">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="e9ba9-144">Service life years</span></span>             | <span data-ttu-id="e9ba9-145">5</span><span class="sxs-lookup"><span data-stu-id="e9ba9-145">5</span></span>      |
| <span data-ttu-id="e9ba9-146">Årlig avskrivningsprocent</span><span class="sxs-lookup"><span data-stu-id="e9ba9-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="e9ba9-147">30 %</span><span class="sxs-lookup"><span data-stu-id="e9ba9-147">30%</span></span>    |

<span data-ttu-id="e9ba9-148">Den degressiva avskrivningsmetoden på 150 % delar 150 procent med tjänstelivstiden i år.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="e9ba9-149">Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="e9ba9-150">Period</span><span class="sxs-lookup"><span data-stu-id="e9ba9-150">Period</span></span> | <span data-ttu-id="e9ba9-151">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="e9ba9-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="e9ba9-152">Bokfört värde</span><span class="sxs-lookup"><span data-stu-id="e9ba9-152">Book value</span></span>             | <span data-ttu-id="e9ba9-153">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="e9ba9-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="e9ba9-154">År 1</span><span class="sxs-lookup"><span data-stu-id="e9ba9-154">Year 1</span></span> | <span data-ttu-id="e9ba9-155">(11 000 - 1 000) × 30 % = 3 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="e9ba9-156">11 000 - 3 000 = 8 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="e9ba9-157">11 000 - 1 000 - 3 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="e9ba9-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="e9ba9-158">År 2</span><span class="sxs-lookup"><span data-stu-id="e9ba9-158">Year 2</span></span> | <span data-ttu-id="e9ba9-159">7 000 × 30 % = 2 100</span><span class="sxs-lookup"><span data-stu-id="e9ba9-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="e9ba9-160">8 000 - 2 100 = 5 900</span><span class="sxs-lookup"><span data-stu-id="e9ba9-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="e9ba9-161">7 000 - 2 100 = 4 900</span><span class="sxs-lookup"><span data-stu-id="e9ba9-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="e9ba9-162">År 3</span><span class="sxs-lookup"><span data-stu-id="e9ba9-162">Year 3</span></span> | <span data-ttu-id="e9ba9-163">4 900 × 30 % = 1 470</span><span class="sxs-lookup"><span data-stu-id="e9ba9-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="e9ba9-164">5 900 - 1 470 = 4 430</span><span class="sxs-lookup"><span data-stu-id="e9ba9-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="e9ba9-165">4 900 - 1 470 = 3 430</span><span class="sxs-lookup"><span data-stu-id="e9ba9-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="e9ba9-166">Om beloppet som beräknas med den degressiva avskrivningsmetoden 150 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="e9ba9-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



