---
title: "Linjär avskrivning kvarstående livstid"
description: "Det här avsnittet ger en översikt över metoden för linjär återstående livstid för avskrivning."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4ad82f3177e4abb7b9cb575b910aabc69901f475
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="straight-line-life-remaining-depreciation"></a><span data-ttu-id="9b461-103">Linjär avskrivning kvarstående livstid</span><span class="sxs-lookup"><span data-stu-id="9b461-103">Straight line life remaining depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9b461-104">Det här avsnittet ger en översikt över metoden för linjär återstående livstid för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="9b461-104">This article gives an overview of the Straight line life remaining method of depreciation.</span></span>

<span data-ttu-id="9b461-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Linjär återstående livstid** i fältet **Metod** i formuläret **Avskrivningsprofiler** baseras avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen på tillgångens återstående tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="9b461-105">When you set up a fixed asset depreciation profile and select **Straight line life remaining** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is based on the remaining service life of the asset.</span></span> <span data-ttu-id="9b461-106">Avskrivningsbeloppet är vanligtvis samma i varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="9b461-106">The depreciation amount is generally the same in each depreciation period.</span></span> <span data-ttu-id="9b461-107">Om du vill ställa in linjär avskrivning kvarstående livstid måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="9b461-107">To set up straight line life remaining depreciation, you also must select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9b461-108">De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.</span><span class="sxs-lookup"><span data-stu-id="9b461-108">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="9b461-109">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="9b461-109">Select a depreciation year</span></span>
<span data-ttu-id="9b461-110">Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="9b461-110">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9b461-111">Standardvärdet är **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="9b461-111">The default value is **Calendar**.</span></span> <span data-ttu-id="9b461-112">Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="9b461-112">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="9b461-113">Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="9b461-113">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="9b461-114">Kalender</span><span class="sxs-lookup"><span data-stu-id="9b461-114">Calendar</span></span>

<span data-ttu-id="9b461-115">Om du väljer **Kalender** i fältet ***Avskrivningsår*** kommer ett år från 1 januari till 31 december att antas, även om du har definierat räkenskapskalendern annorlunda.</span><span class="sxs-lookup"><span data-stu-id="9b461-115">If you select **Calendar** in the ***Depreciation year*** field, a year of January 1 through December 31 is assumed, even if you've defined the fiscal calendar differently.</span></span> <span data-ttu-id="9b461-116">Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="9b461-116">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="9b461-117">Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet.</span><span class="sxs-lookup"><span data-stu-id="9b461-117">Typically, the depreciation base is the net book value minus the salvage value.</span></span> <span data-ttu-id="9b461-118">I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen.</span><span class="sxs-lookup"><span data-stu-id="9b461-118">In the example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> <span data-ttu-id="9b461-119">Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="9b461-119">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9b461-120">**Årlig** bokför ett belopp den 31 december.</span><span class="sxs-lookup"><span data-stu-id="9b461-120">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="9b461-121">**Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.</span><span class="sxs-lookup"><span data-stu-id="9b461-121">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="9b461-122">**Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="9b461-122">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="9b461-123">**Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="9b461-123">**Half-Yearly** posts a half-yearly amount at the end of each calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="9b461-124">**Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="9b461-124">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

<span data-ttu-id="9b461-125">Om du till exempel **Årligen** bokförs årets avskrivning alltså bara en gång, den 31 december varje år.</span><span class="sxs-lookup"><span data-stu-id="9b461-125">For example, if you select **Yearly**, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="9b461-126">Om du väljer **Månadsvis** bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="9b461-126">If you select **Monthly**, the monthly depreciation is posted each month, as one-twelfth of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="9b461-127">Skatt</span><span class="sxs-lookup"><span data-stu-id="9b461-127">Fiscal</span></span>

<span data-ttu-id="9b461-128">Om du väljer **Räkenskapsår** i fältet **Avskrivningsår** används linjär avskrivning kvarstående livstid.</span><span class="sxs-lookup"><span data-stu-id="9b461-128">If you select **Fiscal** in the **Depreciation year** field, straight line life remaining depreciation is used.</span></span> <span data-ttu-id="9b461-129">Avskrivningen beräknas utifrån vad som är kvar av räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="9b461-129">Depreciation is calculated based on the fiscal years remaining.</span></span> <span data-ttu-id="9b461-130">För räkenskapsåret 1 juli 2015 - 30 juni 2016 startar alltså avskrivningsberäkningen alltså den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="9b461-130">For example, for the fiscal year July 1, 2015, through June 30, 2016, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="9b461-131">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="9b461-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="9b461-132">Avskrivningen justeras för varje räkenskapsperiod.</span><span class="sxs-lookup"><span data-stu-id="9b461-132">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="9b461-133">Längden på nästa räkenskapsår bestäms av de räkenskapsperioder som är inställda på sidan **Räkenskapskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="9b461-133">The length of the next fiscal year is determined by the fiscal periods that are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="9b461-134">Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:</span><span class="sxs-lookup"><span data-stu-id="9b461-134">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9b461-135">**Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="9b461-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="9b461-136">**Räkenskapsperiod** beräknar det totala avskrivningsbeloppet för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="9b461-136">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="9b461-137">Detta belopp periodiseras sedan till de räkenskapsperioder som har definierats på sidan **Räkenskapskalendrar** för den räkenskapskalender som angetts för boken.</span><span class="sxs-lookup"><span data-stu-id="9b461-137">This amount is then accrued into the fiscal periods that are defined on the **Fiscal calendars** page for the fiscal calendar that is specified for the book.</span></span>

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a><span data-ttu-id="9b461-138">Exempel på linjär avskrivning av en oförändrad anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="9b461-138">Example of straight line depreciation of an unchanged fixed asset</span></span>
<span data-ttu-id="9b461-139">En anläggningstillgång har följande egenskaper.</span><span class="sxs-lookup"><span data-stu-id="9b461-139">A fixed asset has the following characteristics.</span></span>

|                     |        |
|---------------------|--------|
| <span data-ttu-id="9b461-140">Anskaffningskostnad</span><span class="sxs-lookup"><span data-stu-id="9b461-140">Acquisition cost</span></span>    | <span data-ttu-id="9b461-141">11 000</span><span class="sxs-lookup"><span data-stu-id="9b461-141">11,000</span></span> |
| <span data-ttu-id="9b461-142">Skrotvärde</span><span class="sxs-lookup"><span data-stu-id="9b461-142">Salvage value</span></span>       | <span data-ttu-id="9b461-143">1 000</span><span class="sxs-lookup"><span data-stu-id="9b461-143">1,000</span></span>  |
| <span data-ttu-id="9b461-144">Avskrivningsbas</span><span class="sxs-lookup"><span data-stu-id="9b461-144">Depreciation base</span></span>   | <span data-ttu-id="9b461-145">10 000</span><span class="sxs-lookup"><span data-stu-id="9b461-145">10,000</span></span> |
| <span data-ttu-id="9b461-146">Antal tjänsteår</span><span class="sxs-lookup"><span data-stu-id="9b461-146">Service life years</span></span>  | <span data-ttu-id="9b461-147">5</span><span class="sxs-lookup"><span data-stu-id="9b461-147">5</span></span>      |
| <span data-ttu-id="9b461-148">Årlig avskrivning</span><span class="sxs-lookup"><span data-stu-id="9b461-148">Yearly depreciation</span></span> | <span data-ttu-id="9b461-149">2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-149">2,000</span></span>  |

<span data-ttu-id="9b461-150">Avskrivningsbeloppet är samma varje år: Innan ÷tjänstelivstid (om anskaffning kostnadsberäknad – skrotvärde år)</span><span class="sxs-lookup"><span data-stu-id="9b461-150">The depreciation amount is the same every year: (Acquisition cost – Salvage value) ÷ Service life years</span></span>

| <span data-ttu-id="9b461-151">Period</span><span class="sxs-lookup"><span data-stu-id="9b461-151">Period</span></span> | <span data-ttu-id="9b461-152">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="9b461-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="9b461-153">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="9b461-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|---------------------------------------|
| <span data-ttu-id="9b461-154">År 1</span><span class="sxs-lookup"><span data-stu-id="9b461-154">Year 1</span></span> | <span data-ttu-id="9b461-155">(11 000 – 1 000) ÷ 5 = 2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-155">(11,000 – 1,000) ÷ 5 = 2,000</span></span>                  | <span data-ttu-id="9b461-156">9 000</span><span class="sxs-lookup"><span data-stu-id="9b461-156">9,000</span></span>                                 |
| <span data-ttu-id="9b461-157">År 2</span><span class="sxs-lookup"><span data-stu-id="9b461-157">Year 2</span></span> | <span data-ttu-id="9b461-158">(9 000 – 1 000) ÷ 4 = 2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-158">(9,000 – 1,000) ÷ 4 = 2,000</span></span>                   | <span data-ttu-id="9b461-159">7 000</span><span class="sxs-lookup"><span data-stu-id="9b461-159">7,000</span></span>                                 |
| <span data-ttu-id="9b461-160">År 3</span><span class="sxs-lookup"><span data-stu-id="9b461-160">Year 3</span></span> | <span data-ttu-id="9b461-161">(7 000 – 1 000) ÷ 3 = 2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-161">(7,000 – 1,000) ÷ 3 = 2,000</span></span>                   | <span data-ttu-id="9b461-162">5 000</span><span class="sxs-lookup"><span data-stu-id="9b461-162">5,000</span></span>                                 |
| <span data-ttu-id="9b461-163">År 4</span><span class="sxs-lookup"><span data-stu-id="9b461-163">Year 4</span></span> | <span data-ttu-id="9b461-164">(5 000 – 1 000) ÷ 2 = 2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-164">(5,000 – 1,000) ÷ 2 = 2,000</span></span>                   | <span data-ttu-id="9b461-165">3 000</span><span class="sxs-lookup"><span data-stu-id="9b461-165">3,000</span></span>                                 |
| <span data-ttu-id="9b461-166">År 5</span><span class="sxs-lookup"><span data-stu-id="9b461-166">Year 5</span></span> | <span data-ttu-id="9b461-167">(3 000 – 1 000) ÷ 1 = 2 000</span><span class="sxs-lookup"><span data-stu-id="9b461-167">(3,000 – 1,000) ÷ 1 = 2,000</span></span>                   | <span data-ttu-id="9b461-168">1 000</span><span class="sxs-lookup"><span data-stu-id="9b461-168">1,000</span></span>                                 |






