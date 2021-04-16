---
title: Degressiv avskrivning efter en delning
description: I det här avsnittet beskrivs den metod som används i Anläggningstillgångar för att beräkna avskrivning efter att en tillgång har delats med metoden Degressiv avskrivning.
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 056808b7d4d490bc4d60aa058108d159c1d4867c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826261"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="b5d8f-103">Degressiv avskrivning efter en delning</span><span class="sxs-lookup"><span data-stu-id="b5d8f-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5d8f-104">I det här avsnittet beskrivs den metod som används i Anläggningstillgångar för att beräkna avskrivning efter att en tillgång har delats till en annan tillgång med metoden Degressiv avskrivning.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="b5d8f-105">Det avskrivningsår som är konfigurerat i tillgångsboken är räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="b5d8f-106">Mer information finns i [Degressiv avskrivning](reduce-balance-depreciation.md) och [Dela en anläggningstillgång](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="b5d8f-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="b5d8f-107">Om du delar en anläggningstillgång under en räkenskapsperiod som infaller senare än perioden då tillgången förvärvades, kommer den degressiva avskrivningen att redovisas mot tillgångens bokförda nettovärde (BNV) för föregående år.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="b5d8f-108">Det tar också hänsyn till de anskaffnings- och avskrivningsjusteringstransaktioner som genererades från transaktionen som delade upp tillgången.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="b5d8f-109">Detta förutsätter att tillgången förvärvades under ett räkenskapsår och delas upp i ett senare räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="b5d8f-110">Det belopp som måste skrivas av för den ursprungliga tillgången efter delningen reflekterar tillgångens BNV innan tillgången delades, och anskaffnings- och avskrivningsjusteringstransaktionen som bokfördes för delningen.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="b5d8f-111">Följande villkor gäller till exempel:</span><span class="sxs-lookup"><span data-stu-id="b5d8f-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="b5d8f-112">Räkenskapsperioden är från den 30 juni till den 1 juli.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="b5d8f-113">Den degressiva avskrivningen i procent är 18 procent, och en tillgång förvärvas i juni 2019 till ett anskaffningspris på 10 000 USD.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="b5d8f-114">Avskrivningen för det första räkenskapsåret är lika med 18 000 USD, månadsavskrivningen är lika med 150 USD och tillgången avskrivs sedan tills 2019 november, till beloppet 738,75 USD.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="b5d8f-115">I november 2019 delas 80 procent av tillgången till en annan anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="b5d8f-116">[![Degressiv avskrivning efter en delning](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="b5d8f-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="b5d8f-117">Det belopp som ska skrivas av för den ursprungliga till gången är 1 822,25 USD.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="b5d8f-118">Det här beloppet är lika med BNV innan delningstransaktionen bokförs (9 111,25 USD) plus den anskaffningsjustering som genereras vid bokföringen av den uppdelade transaktionen (-8 000 USD) plus den avskrivningsjustering som genererades under delningstransaktionen (711 USD).</span><span class="sxs-lookup"><span data-stu-id="b5d8f-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="b5d8f-119">Därför är avskrivningen för det andra året (1 822,25 × 18 procent) ÷ 12 = 27,33 USD.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="b5d8f-120">Beloppet som ska skrivas av för den nya anläggningstillgången under det första året är (8 000 × 18 procent) ÷ 12 = 120 USD.</span><span class="sxs-lookup"><span data-stu-id="b5d8f-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]