---
title: Avskrivningsmetoder och praxis
description: Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds av Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be8e05a386178b9172a906109e015269dc72b32e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "331125"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="82f16-103">Avskrivningsmetoder och praxis</span><span class="sxs-lookup"><span data-stu-id="82f16-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82f16-104">Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds av Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="82f16-104">This article provides an overview of the depreciation conventions and depreciation methods that are supported by Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="82f16-105">Du kan välja olika avskrivningsmetoder och -praxis.</span><span class="sxs-lookup"><span data-stu-id="82f16-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="82f16-106">Syftet med metoderna är att fördela anläggningstillgångens avskrivbara värde i räkenskapsperioder.</span><span class="sxs-lookup"><span data-stu-id="82f16-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="82f16-107">Anläggningstillgångens avskrivbara värde är anskaffningspriset minus eventuellt kassationsvärde.</span><span class="sxs-lookup"><span data-stu-id="82f16-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="82f16-108">Om du använder avskrivningspraxis och ändrar senaste körningsdatum för avskrivning för en tillgång, som orsakar att vissa avskrivningar hoppas över, kan avskrivningen för förra året bli högre eller lägre än förväntat.</span><span class="sxs-lookup"><span data-stu-id="82f16-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="82f16-109">Avskrivningen justeras med antalet avskrivningsperioder som påverkas av ändringen av senaste körningsdatum för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="82f16-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="82f16-110">Om du till exempel använder praxis för halvårsavskrivning över tre år sker avskrivning normalt över 3 1/2 år.</span><span class="sxs-lookup"><span data-stu-id="82f16-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="82f16-111">Om du ändrar senaste körningsdatum för avskrivning under de 3 1/2 åren, flyttar det senaste avskrivningsåret ut antalet perioder som påverkas.</span><span class="sxs-lookup"><span data-stu-id="82f16-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="82f16-112">Om du flyttar datumet tre månader har förra året nio månaders avskrivning, medan det normalt skulle vara sex månaders avskrivning.</span><span class="sxs-lookup"><span data-stu-id="82f16-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="82f16-113">Du kan välja bland följande avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="82f16-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="82f16-114">Halvår</span><span class="sxs-lookup"><span data-stu-id="82f16-114">Half year</span></span>
-   <span data-ttu-id="82f16-115">Hel månad</span><span class="sxs-lookup"><span data-stu-id="82f16-115">Full month</span></span>
-   <span data-ttu-id="82f16-116">Mellankvartal</span><span class="sxs-lookup"><span data-stu-id="82f16-116">Mid quarter</span></span>
-   <span data-ttu-id="82f16-117">Mitt i månaden (första i månaden)</span><span class="sxs-lookup"><span data-stu-id="82f16-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="82f16-118">Mitt i månaden (15:e i månaden)</span><span class="sxs-lookup"><span data-stu-id="82f16-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="82f16-119">Halvår (start på året)</span><span class="sxs-lookup"><span data-stu-id="82f16-119">Half year (start of year)</span></span>
-   <span data-ttu-id="82f16-120">Halvår (nästa år)</span><span class="sxs-lookup"><span data-stu-id="82f16-120">Half year (next year)</span></span>

<span data-ttu-id="82f16-121">Du kan välja mellan följande avskrivningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="82f16-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="82f16-122">Linjär tjänstelivstid</span><span class="sxs-lookup"><span data-stu-id="82f16-122">Straight line service life</span></span>
-   <span data-ttu-id="82f16-123">Degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-123">Reducing balance</span></span>
-   <span data-ttu-id="82f16-124">Manuell</span><span class="sxs-lookup"><span data-stu-id="82f16-124">Manual</span></span>
-   <span data-ttu-id="82f16-125">Faktor</span><span class="sxs-lookup"><span data-stu-id="82f16-125">Factor</span></span>
-   <span data-ttu-id="82f16-126">Förbrukning</span><span class="sxs-lookup"><span data-stu-id="82f16-126">Consumption</span></span>
-   <span data-ttu-id="82f16-127">Linjär återstående livstid</span><span class="sxs-lookup"><span data-stu-id="82f16-127">Straight line life remaining</span></span>
-   <span data-ttu-id="82f16-128">200 % degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-128">200% reducing balance</span></span>
-   <span data-ttu-id="82f16-129">175 % degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-129">175% reducing balance</span></span>
-   <span data-ttu-id="82f16-130">150 % degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-130">150% reducing balance</span></span>
-   <span data-ttu-id="82f16-131">125 % degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="82f16-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="82f16-132">Additional resources</span></span>
--------

[<span data-ttu-id="82f16-133">Avskrivning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="82f16-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="82f16-134">Linjär avskrivning av tjänstelivstid</span><span class="sxs-lookup"><span data-stu-id="82f16-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="82f16-135">Degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-135">Reducing balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="82f16-136">Manuell avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="82f16-137">Faktoravskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="82f16-138">Förbrukningsavskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="82f16-139">Linjär avskrivning kvarstående livstid</span><span class="sxs-lookup"><span data-stu-id="82f16-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="82f16-140">125 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="82f16-141">150 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="82f16-142">175 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="82f16-143">200 procent degressiv avskrivning</span><span class="sxs-lookup"><span data-stu-id="82f16-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)



