---
title: Degressiv avskrivning
description: Den här avsnittet ger en översikt över metoden för degressiv avskrivning.
author: ShylaThompson
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 25d34392819d9f687c306c1bf52153e0d074371a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826237"
---
# <a name="reduce-balance-depreciation"></a><span data-ttu-id="a8a64-103">Degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="a8a64-103">Reduce balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8a64-104">Den här avsnittet ger en översikt över metoden för degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="a8a64-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="a8a64-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer Degressiv avskrivning i fältet Metod på sidan Avskrivningsprofiler skrivs tillgångarna som har tilldelats den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="a8a64-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="a8a64-106">Om du vill ställa in degressiv avskrivning måste du också göra val i fält på Allmänt snabbfliken på sidan Avskrivningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="a8a64-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="a8a64-107">Först väljer du ett år i fältet Avskrivningsår.</span><span class="sxs-lookup"><span data-stu-id="a8a64-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="a8a64-108">Beroende på valet visas olika alternativ i fältet Periodfrekvens, vilket beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="a8a64-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="a8a64-109">Du måste också ange ett värde i fältet Procent för avskrivningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="a8a64-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="a8a64-110">Om du väljer alternativet Full avskrivning tas kvarstående avskrivningsunderlag i den sista avskrivningsperioden och kan vara ett stort belopp.</span><span class="sxs-lookup"><span data-stu-id="a8a64-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="a8a64-111">Vissa länder/regioner använder inte en omställning till en linjär metod.</span><span class="sxs-lookup"><span data-stu-id="a8a64-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="a8a64-112">Omställning sker när den alternativa avskrivningsmetodens mängd är större än eller lika med den primära avskrivningsprofilens mängd och den alternativa metodens mängd väljs som avskrivningsmängd.</span><span class="sxs-lookup"><span data-stu-id="a8a64-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="a8a64-113">Eftersom en tillgång aldrig skrivs av helt med en procentberäkning måste du välja det alternativet Full avskrivning för att skriva av en tillgång helt.</span><span class="sxs-lookup"><span data-stu-id="a8a64-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="a8a64-114">Välj ett avskrivningsår</span><span class="sxs-lookup"><span data-stu-id="a8a64-114">Select a depreciation year</span></span>
<span data-ttu-id="a8a64-115">Du kan välja Kalender eller Räkenskapsår i fältet Avskrivningår på sidan Avskrivningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="a8a64-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="a8a64-116">Valet avgör vilka alternativ som är tillgängliga i fältet Periodfrekvens.</span><span class="sxs-lookup"><span data-stu-id="a8a64-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="a8a64-117">Standardalternativet är Kalender.</span><span class="sxs-lookup"><span data-stu-id="a8a64-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="a8a64-118">Kalender</span><span class="sxs-lookup"><span data-stu-id="a8a64-118">Calendar</span></span>

<span data-ttu-id="a8a64-119">Med alternativet Kalender uppdaterar du avskrivningsbasen som vanligtvis är bokfört nettovärde minus skrotvärde, den 1 januari varje år.</span><span class="sxs-lookup"><span data-stu-id="a8a64-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="a8a64-120">I exemplet på degressiv avskrivning senare i det här avsnittet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningen som görs i kolumnen Beräkning.</span><span class="sxs-lookup"><span data-stu-id="a8a64-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="a8a64-121">Om du väljer Kalender är följande alternativ tillgängliga i fältet Periodfrekvens, som definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret:</span><span class="sxs-lookup"><span data-stu-id="a8a64-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="a8a64-122">Årligen bokför den 31 december.</span><span class="sxs-lookup"><span data-stu-id="a8a64-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="a8a64-123">Månadsvis bokför ett månatligt belopp i slutet av varje månad.</span><span class="sxs-lookup"><span data-stu-id="a8a64-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="a8a64-124">Kvartalvis bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).</span><span class="sxs-lookup"><span data-stu-id="a8a64-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="a8a64-125">Halvårsvis bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).</span><span class="sxs-lookup"><span data-stu-id="a8a64-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="a8a64-126">Dagligen bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.</span><span class="sxs-lookup"><span data-stu-id="a8a64-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="a8a64-127">Om du till exempel väljer Årligen, bokförs årets avskrivning alltså bara en gång, den 31 december varje år.</span><span class="sxs-lookup"><span data-stu-id="a8a64-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="a8a64-128">Om du väljer Månadsvis, bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="a8a64-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="a8a64-129">Skatt</span><span class="sxs-lookup"><span data-stu-id="a8a64-129">Fiscal</span></span>

<span data-ttu-id="a8a64-130">Om du väljer Räkenskapsår i fältet Avskrivning används den linjära avskrivningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="a8a64-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="a8a64-131">Det beräknas utifrån räkenskapsåret, som ställs in på sidan Räkenskapskalendrar som väljs på sidan Redovisning.</span><span class="sxs-lookup"><span data-stu-id="a8a64-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="a8a64-132">Exempelvis för räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="a8a64-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="a8a64-133">Räkenskapsåret kan vara längre eller kortare än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="a8a64-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="a8a64-134">Avskrivningen justeras för varje räkenskapsperiod.</span><span class="sxs-lookup"><span data-stu-id="a8a64-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="a8a64-135">Längden på nästa räkenskapsår baseras på de räkenskapsperioder som du ställer in när du skapar ett nytt räkenskapsår på sidan Räkenskapskalendrar.</span><span class="sxs-lookup"><span data-stu-id="a8a64-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="a8a64-136">Om du väljer Räkenskapsår har du följande alternativ i fältet Räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="a8a64-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="a8a64-137">Årligen bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.</span><span class="sxs-lookup"><span data-stu-id="a8a64-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="a8a64-138">Räkenskapsperioden bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret. Beloppet periodiseras till de räkenskapsperioder som definierats för räkenskapskalendern som väljs på redovisningssidan, eller för den räkenskapskalender som väljs för boken för en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="a8a64-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="a8a64-139">Exempel på en degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="a8a64-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="a8a64-140">Anta att anskaffningspriset för anläggningstillgången är 11 000, kassationsvärdet är 1 000 och procentfaktorn för avskrivning är 30.</span><span class="sxs-lookup"><span data-stu-id="a8a64-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="a8a64-141">Med metoden för degressiv avskrivning beräknas 30 procent av avskrivningsbasen (bokfört nettovärde minus kassationsvärde) i slutet av föregående avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="a8a64-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="a8a64-142">Avskrivning för de första tre åren visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8a64-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="a8a64-143">Period</span><span class="sxs-lookup"><span data-stu-id="a8a64-143">Period</span></span> | <span data-ttu-id="a8a64-144">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="a8a64-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="a8a64-145">Bokfört nettovärde i slutet av året</span><span class="sxs-lookup"><span data-stu-id="a8a64-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="a8a64-146">År 1</span><span class="sxs-lookup"><span data-stu-id="a8a64-146">Year 1</span></span> | <span data-ttu-id="a8a64-147">(11 000 – 1 000) \* 30% = 3 000</span><span class="sxs-lookup"><span data-stu-id="a8a64-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="a8a64-148">(11 000 – 1 000) – 3 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="a8a64-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="a8a64-149">År 2</span><span class="sxs-lookup"><span data-stu-id="a8a64-149">Year 2</span></span> | <span data-ttu-id="a8a64-150">(7 000 – 1 000) \* 30% = 1 800</span><span class="sxs-lookup"><span data-stu-id="a8a64-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="a8a64-151">(7 000 -1 800) = 5 200</span><span class="sxs-lookup"><span data-stu-id="a8a64-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="a8a64-152">År 3</span><span class="sxs-lookup"><span data-stu-id="a8a64-152">Year 3</span></span> | <span data-ttu-id="a8a64-153">(5 200 – 1 000) \* 30% = 1 260</span><span class="sxs-lookup"><span data-stu-id="a8a64-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="a8a64-154">(5 200 – 1 260) = 3 940</span><span class="sxs-lookup"><span data-stu-id="a8a64-154">(5,200 - 1,260) = 3,940</span></span>               |


-







[!INCLUDE[footer-include](../../includes/footer-banner.md)]