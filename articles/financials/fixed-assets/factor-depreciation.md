---
title: Faktoravskrivning
description: Den här artikeln ger en översikt över faktoravskrivningsmetoden.
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
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa8bc4566def9dd770a97facb459e6b977bfaffb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "338807"
---
# <a name="factor-depreciation"></a><span data-ttu-id="dd5f0-103">Faktoravskrivning</span><span class="sxs-lookup"><span data-stu-id="dd5f0-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd5f0-104">Den här artikeln ger en översikt över faktoravskrivningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="dd5f0-105">Faktorer är de procentsatser som används till att skriva av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="dd5f0-106">När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer värdet **Faktor** i fältet **Metod** på sidan för **Avskrivningsprofiler** kan du ställa in progressiv, digressiv eller linjär avskrivning:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="dd5f0-107">I progressiv avskrivning ökar avskrivningsbeloppet för varje avskrivningsperiod.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="dd5f0-108">I digressiv avskrivning, minskar avskrivningsbeloppet per period med tiden.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="dd5f0-109">I linjär avskrivning är avskrivningen densamma för varje period.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="dd5f0-110">Reglerna och exemplen nedan anger hur du kan ställa in faktorer för varje avskrivningstyp.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="dd5f0-111">När du väljer **Faktor** i fältet **Metod** kommer fälten **Faktor** och **Intervall** att visas.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="dd5f0-112">Progressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="dd5f0-112">Progressive depreciation</span></span>
<span data-ttu-id="dd5f0-113">Värdet i fältet **Faktor** är mer än **50**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="dd5f0-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="dd5f0-114">Example</span></span>

<span data-ttu-id="dd5f0-115">Anskaffningspriset är 100 000, faktorn är 70, livslängden är 10 år och avskrivningen börjar den 1 januari.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="dd5f0-116">Avskrivningsbeloppen och bokförda nettovärdesbelopp visas endast för de första sex åren av livslängden.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="dd5f0-117">År</span><span class="sxs-lookup"><span data-stu-id="dd5f0-117">Year</span></span> | <span data-ttu-id="dd5f0-118">Period</span><span class="sxs-lookup"><span data-stu-id="dd5f0-118">Period</span></span>      | <span data-ttu-id="dd5f0-119">Avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="dd5f0-119">Depreciation amount</span></span> | <span data-ttu-id="dd5f0-120">Bokfört nettovärdebelopp</span><span class="sxs-lookup"><span data-stu-id="dd5f0-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="dd5f0-121">1</span><span class="sxs-lookup"><span data-stu-id="dd5f0-121">1</span></span>    | <span data-ttu-id="dd5f0-122">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-122">December 31</span></span> | <span data-ttu-id="dd5f0-123">307,69</span><span class="sxs-lookup"><span data-stu-id="dd5f0-123">307.69</span></span>              | <span data-ttu-id="dd5f0-124">99 692,31</span><span class="sxs-lookup"><span data-stu-id="dd5f0-124">99,692.31</span></span>             |
| <span data-ttu-id="dd5f0-125">2</span><span class="sxs-lookup"><span data-stu-id="dd5f0-125">2</span></span>    | <span data-ttu-id="dd5f0-126">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-126">December 31</span></span> | <span data-ttu-id="dd5f0-127">1 447,21</span><span class="sxs-lookup"><span data-stu-id="dd5f0-127">1,447.21</span></span>            | <span data-ttu-id="dd5f0-128">98 245,10</span><span class="sxs-lookup"><span data-stu-id="dd5f0-128">98,245.10</span></span>             |
| <span data-ttu-id="dd5f0-129">3</span><span class="sxs-lookup"><span data-stu-id="dd5f0-129">3</span></span>    | <span data-ttu-id="dd5f0-130">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-130">December 31</span></span> | <span data-ttu-id="dd5f0-131">3 104,50</span><span class="sxs-lookup"><span data-stu-id="dd5f0-131">3,104.50</span></span>            | <span data-ttu-id="dd5f0-132">95 140,60</span><span class="sxs-lookup"><span data-stu-id="dd5f0-132">95,140.60</span></span>             |
| <span data-ttu-id="dd5f0-133">4</span><span class="sxs-lookup"><span data-stu-id="dd5f0-133">4</span></span>    | <span data-ttu-id="dd5f0-134">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-134">December 31</span></span> | <span data-ttu-id="dd5f0-135">5 150,21</span><span class="sxs-lookup"><span data-stu-id="dd5f0-135">5,150.21</span></span>            | <span data-ttu-id="dd5f0-136">89 990,39</span><span class="sxs-lookup"><span data-stu-id="dd5f0-136">89,990.39</span></span>             |
| <span data-ttu-id="dd5f0-137">5</span><span class="sxs-lookup"><span data-stu-id="dd5f0-137">5</span></span>    | <span data-ttu-id="dd5f0-138">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-138">December 31</span></span> | <span data-ttu-id="dd5f0-139">7 522,95</span><span class="sxs-lookup"><span data-stu-id="dd5f0-139">7,522.95</span></span>            | <span data-ttu-id="dd5f0-140">82 467,44</span><span class="sxs-lookup"><span data-stu-id="dd5f0-140">82,467.44</span></span>             |
| <span data-ttu-id="dd5f0-141">6</span><span class="sxs-lookup"><span data-stu-id="dd5f0-141">6</span></span>    | <span data-ttu-id="dd5f0-142">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-142">December 31</span></span> | <span data-ttu-id="dd5f0-143">10 184,06</span><span class="sxs-lookup"><span data-stu-id="dd5f0-143">10,184.06</span></span>           | <span data-ttu-id="dd5f0-144">72 283,38</span><span class="sxs-lookup"><span data-stu-id="dd5f0-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="dd5f0-145">Digressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="dd5f0-145">Digressive depreciation</span></span>
<span data-ttu-id="dd5f0-146">Värdet i fältet **Faktor** är mindre än **50**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="dd5f0-147">Exempel</span><span class="sxs-lookup"><span data-stu-id="dd5f0-147">Example</span></span>

<span data-ttu-id="dd5f0-148">Anskaffningspriset är 100 000, faktorn är 20, livslängden är 10 år och avskrivningen börjar den 1 januari.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="dd5f0-149">Avskrivningsbeloppen och bokförda nettovärdesbelopp visas endast för de första sex åren av livslängden.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="dd5f0-150">År</span><span class="sxs-lookup"><span data-stu-id="dd5f0-150">Year</span></span> | <span data-ttu-id="dd5f0-151">Period</span><span class="sxs-lookup"><span data-stu-id="dd5f0-151">Period</span></span>      | <span data-ttu-id="dd5f0-152">Avskrivningsbelopp</span><span class="sxs-lookup"><span data-stu-id="dd5f0-152">Depreciation amount</span></span> | <span data-ttu-id="dd5f0-153">Bokfört nettovärdebelopp</span><span class="sxs-lookup"><span data-stu-id="dd5f0-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="dd5f0-154">1</span><span class="sxs-lookup"><span data-stu-id="dd5f0-154">1</span></span>    | <span data-ttu-id="dd5f0-155">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-155">December 31</span></span> | <span data-ttu-id="dd5f0-156">56 080,43</span><span class="sxs-lookup"><span data-stu-id="dd5f0-156">56,080.43</span></span>           | <span data-ttu-id="dd5f0-157">43 919,57</span><span class="sxs-lookup"><span data-stu-id="dd5f0-157">43,919.57</span></span>             |
| <span data-ttu-id="dd5f0-158">2</span><span class="sxs-lookup"><span data-stu-id="dd5f0-158">2</span></span>    | <span data-ttu-id="dd5f0-159">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-159">December 31</span></span> | <span data-ttu-id="dd5f0-160">10 665,70</span><span class="sxs-lookup"><span data-stu-id="dd5f0-160">10,665.70</span></span>           | <span data-ttu-id="dd5f0-161">33 253,87</span><span class="sxs-lookup"><span data-stu-id="dd5f0-161">33,253.87</span></span>             |
| <span data-ttu-id="dd5f0-162">3</span><span class="sxs-lookup"><span data-stu-id="dd5f0-162">3</span></span>    | <span data-ttu-id="dd5f0-163">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-163">December 31</span></span> | <span data-ttu-id="dd5f0-164">7 156,22</span><span class="sxs-lookup"><span data-stu-id="dd5f0-164">7,156.22</span></span>            | <span data-ttu-id="dd5f0-165">26 097,65</span><span class="sxs-lookup"><span data-stu-id="dd5f0-165">26,097.65</span></span>             |
| <span data-ttu-id="dd5f0-166">4</span><span class="sxs-lookup"><span data-stu-id="dd5f0-166">4</span></span>    | <span data-ttu-id="dd5f0-167">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-167">December 31</span></span> | <span data-ttu-id="dd5f0-168">5 538,06</span><span class="sxs-lookup"><span data-stu-id="dd5f0-168">5,538.06</span></span>            | <span data-ttu-id="dd5f0-169">20 559,59</span><span class="sxs-lookup"><span data-stu-id="dd5f0-169">20,559.59</span></span>             |
| <span data-ttu-id="dd5f0-170">5</span><span class="sxs-lookup"><span data-stu-id="dd5f0-170">5</span></span>    | <span data-ttu-id="dd5f0-171">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-171">December 31</span></span> | <span data-ttu-id="dd5f0-172">4 579,89</span><span class="sxs-lookup"><span data-stu-id="dd5f0-172">4,579.89</span></span>            | <span data-ttu-id="dd5f0-173">15 979,70</span><span class="sxs-lookup"><span data-stu-id="dd5f0-173">15,979.70</span></span>             |
| <span data-ttu-id="dd5f0-174">6</span><span class="sxs-lookup"><span data-stu-id="dd5f0-174">6</span></span>    | <span data-ttu-id="dd5f0-175">31 december</span><span class="sxs-lookup"><span data-stu-id="dd5f0-175">December 31</span></span> | <span data-ttu-id="dd5f0-176">3 937,36</span><span class="sxs-lookup"><span data-stu-id="dd5f0-176">3,937.36</span></span>            | <span data-ttu-id="dd5f0-177">12 042,34</span><span class="sxs-lookup"><span data-stu-id="dd5f0-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="dd5f0-178">Linjär avskrivning</span><span class="sxs-lookup"><span data-stu-id="dd5f0-178">Straight line depreciation</span></span>
<span data-ttu-id="dd5f0-179">Värdet i fältet **Faktor** är lika med **50**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="dd5f0-180">I detta fall är avskrivningen densamma för varje period och du bör beakta följderna av värdena som du har angett i andra fält, enligt beskrivningen i [Linjär avskrivning av tjänstelivstid](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="dd5f0-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



