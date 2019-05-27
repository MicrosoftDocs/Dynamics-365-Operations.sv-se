---
title: Manuell avskrivning
description: Det här avsnittet innehåller en översikt över den manuella avskrivningsmetoden.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14e385e60e10146a0855a467af57a0a31fcc53bd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558745"
---
# <a name="manual-depreciation"></a><span data-ttu-id="0d726-103">Manuell avskrivning</span><span class="sxs-lookup"><span data-stu-id="0d726-103">Manual depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d726-104">Det här avsnittet innehåller en översikt över den manuella avskrivningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="0d726-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="0d726-105">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Manuellt** i fältet **Metod** på sidan **Avskrivningsprofiler** avgörs avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen av procenten som du anger för varje intervall under kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="0d726-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="0d726-106">Intervallen som du ställer in procenttal för bokförs enligt det värde du valt i fältet **Periodfrekvens** på snabbfliken **Allmänt** på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="0d726-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="0d726-107">Du kan välja följande värden:</span><span class="sxs-lookup"><span data-stu-id="0d726-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="0d726-108">Årligen</span><span class="sxs-lookup"><span data-stu-id="0d726-108">Yearly</span></span>
-   <span data-ttu-id="0d726-109">Varje månad</span><span class="sxs-lookup"><span data-stu-id="0d726-109">Monthly</span></span>
-   <span data-ttu-id="0d726-110">Varje kvartal</span><span class="sxs-lookup"><span data-stu-id="0d726-110">Quarterly</span></span>
-   <span data-ttu-id="0d726-111">Halvårsvis</span><span class="sxs-lookup"><span data-stu-id="0d726-111">Half-Yearly</span></span>
-   <span data-ttu-id="0d726-112">Dagligen</span><span class="sxs-lookup"><span data-stu-id="0d726-112">Daily</span></span>

<span data-ttu-id="0d726-113">När du har valt periodfrekvens klickar du på **Manuella tidsplaner**och ställer in procenttal frö varje bokföringsintervall.</span><span class="sxs-lookup"><span data-stu-id="0d726-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="0d726-114">Tillsammans definierar de manuella tidsplanerna och bokföringsintervallen avskrivningsbeloppet, enligt exemplen senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="0d726-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="0d726-115">Manuell avskrivning beräknas alltid i procent av anskaffningspriset.</span><span class="sxs-lookup"><span data-stu-id="0d726-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="0d726-116">För manuell avskrivning behöver de avskrivningsintervall du anger inte utgöra 100 procent.</span><span class="sxs-lookup"><span data-stu-id="0d726-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="0d726-117">Manuell avskrivning är en flexibel avskrivningsmetod som ofta används för att definiera en extraordinär avskrivningsprofil på sidan **Böcker**, till exempel en icke-periodisk avskrivning av speciella skäl (kanske skatteskäl).</span><span class="sxs-lookup"><span data-stu-id="0d726-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="0d726-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="0d726-118">Examples</span></span>
<span data-ttu-id="0d726-119">Anskaffningspris: 11 000,00 Förväntat skrotvärde: 1 000,00 Följande tabell visar de intervall och procentsatser som du ställer in på sidan **Tidsplaner för anläggningstillgångens avskrivningsprofil**.</span><span class="sxs-lookup"><span data-stu-id="0d726-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="0d726-120">Intervallnummer</span><span class="sxs-lookup"><span data-stu-id="0d726-120">Interval number</span></span> | <span data-ttu-id="0d726-121">Procent</span><span class="sxs-lookup"><span data-stu-id="0d726-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="0d726-122">1</span><span class="sxs-lookup"><span data-stu-id="0d726-122">1</span></span>               | <span data-ttu-id="0d726-123">10,00</span><span class="sxs-lookup"><span data-stu-id="0d726-123">10.00</span></span>      |
| <span data-ttu-id="0d726-124">2</span><span class="sxs-lookup"><span data-stu-id="0d726-124">2</span></span>               | <span data-ttu-id="0d726-125">50,00</span><span class="sxs-lookup"><span data-stu-id="0d726-125">50.00</span></span>      |
| <span data-ttu-id="0d726-126">3</span><span class="sxs-lookup"><span data-stu-id="0d726-126">3</span></span>               | <span data-ttu-id="0d726-127">8,00</span><span class="sxs-lookup"><span data-stu-id="0d726-127">8.00</span></span>       |

<span data-ttu-id="0d726-128">Följande tabell visar hur avskrivningen för varje intervall beräknas.</span><span class="sxs-lookup"><span data-stu-id="0d726-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="0d726-129">Intervallnummer</span><span class="sxs-lookup"><span data-stu-id="0d726-129">Interval number</span></span> | <span data-ttu-id="0d726-130">Beräkning av årligt avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="0d726-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="0d726-131">Bokfört nettovärde i slutet av intervallet</span><span class="sxs-lookup"><span data-stu-id="0d726-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="0d726-132">1</span><span class="sxs-lookup"><span data-stu-id="0d726-132">1</span></span>                | <span data-ttu-id="0d726-133">(11 000–1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="0d726-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="0d726-134">10 000 (11 000–1 000)</span><span class="sxs-lookup"><span data-stu-id="0d726-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="0d726-135">2</span><span class="sxs-lookup"><span data-stu-id="0d726-135">2</span></span>                | <span data-ttu-id="0d726-136">(11 000–1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="0d726-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="0d726-137">5 000 (10 000–5 000)</span><span class="sxs-lookup"><span data-stu-id="0d726-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="0d726-138">3</span><span class="sxs-lookup"><span data-stu-id="0d726-138">3</span></span>                | <span data-ttu-id="0d726-139">(11 000–1 000) × 8 % = 800</span><span class="sxs-lookup"><span data-stu-id="0d726-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="0d726-140">4 200 (5 000–800)</span><span class="sxs-lookup"><span data-stu-id="0d726-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="0d726-141">Om du väljer **Varje månad** i fältet **Periodfrekvens** ställer du in 12 manuella schemaintervall.</span><span class="sxs-lookup"><span data-stu-id="0d726-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="0d726-142">Följande tabell visar avskrivningsbeloppen för de två första intervallen.</span><span class="sxs-lookup"><span data-stu-id="0d726-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="0d726-143">Intervall</span><span class="sxs-lookup"><span data-stu-id="0d726-143">Interval</span></span> | <span data-ttu-id="0d726-144">Avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="0d726-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="0d726-145">Januari</span><span class="sxs-lookup"><span data-stu-id="0d726-145">January</span></span>  | <span data-ttu-id="0d726-146">(11 000–1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="0d726-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="0d726-147">Februari</span><span class="sxs-lookup"><span data-stu-id="0d726-147">February</span></span> | <span data-ttu-id="0d726-148">(11 000–1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="0d726-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="0d726-149">Om du väljer <strong>Halvårsvis</strong> i fältet *<strong><em>Periodfrekvens</em>*</strong> ställer du in två manuella schemaintervall.</span><span class="sxs-lookup"><span data-stu-id="0d726-149">If you select <strong>Half-Yearly</strong> in the *<strong><em>Period frequency</em>* field</strong>, you set up two manual schedule intervals.</span></span> <span data-ttu-id="0d726-150">Följande tabell visar avskrivningsbeloppen för de två intervallen.</span><span class="sxs-lookup"><span data-stu-id="0d726-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="0d726-151">Intervall</span><span class="sxs-lookup"><span data-stu-id="0d726-151">Interval</span></span>    | <span data-ttu-id="0d726-152">Avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="0d726-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="0d726-153">30 juni</span><span class="sxs-lookup"><span data-stu-id="0d726-153">June 30</span></span>     | <span data-ttu-id="0d726-154">(11 000–1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="0d726-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="0d726-155">31 december</span><span class="sxs-lookup"><span data-stu-id="0d726-155">December 31</span></span> | <span data-ttu-id="0d726-156">(11 000–1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="0d726-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="0d726-157">Den sammanlagda procentsatsen för alla intervall behöver inte vara 100.</span><span class="sxs-lookup"><span data-stu-id="0d726-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="0d726-158">Du kommer emellertid att erhålla ett meddelande om värdet i fältet **Ackumulerad procent** på sidan **Avskrivningsprofilscheman för anläggningstillgångar** inte är **100**.</span><span class="sxs-lookup"><span data-stu-id="0d726-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>



