---
title: "Gemensamma källor till produktionsavvikelser"
description: "Det här avsnittet beskriver olika typiska källor till varje typ av produktionsavvikelse."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fd01f742ee7a45e9c7d4feee4f3bf58dce4a3bf7
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="common-sources-of-production-variances"></a><span data-ttu-id="87799-103">Gemensamma källor till produktionsavvikelser</span><span class="sxs-lookup"><span data-stu-id="87799-103">Common sources of production variances</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="87799-104">Det här avsnittet beskriver olika typiska källor till varje typ av produktionsavvikelse.</span><span class="sxs-lookup"><span data-stu-id="87799-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="87799-105">Nedan följer några typiska källor till en avvikelse i **partistorlek**:</span><span class="sxs-lookup"><span data-stu-id="87799-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="87799-106">Den godkända kvantiteten för en tillverkningsorder avviker från den beräknade kvantitet som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="87799-107">Kvantiteten ligger till grund för periodiseringen av konstanta kostnader.</span><span class="sxs-lookup"><span data-stu-id="87799-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="87799-108">Värdet av de konstanta kostnaderna på produktionsordern avviker från de konstanta kostnader som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="87799-109">De konstanta kostnaderna på produktionsordern kan avvika av flera skäl.</span><span class="sxs-lookup"><span data-stu-id="87799-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="87799-110">Exempelvis kan de konstanta kostnaderna avspegla följande faktorer:</span><span class="sxs-lookup"><span data-stu-id="87799-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="87799-111">Manuella ändringar av produktionsstrukturlistan (BOM) eller flödet</span><span class="sxs-lookup"><span data-stu-id="87799-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="87799-112">Valet av en annan strukturlisteversion eller flödesversion när produktionsordern skapas</span><span class="sxs-lookup"><span data-stu-id="87799-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="87799-113">Planerade teknikändringar till den strukturlisteversion eller flödesversion som har tilldelats till artikeln</span><span class="sxs-lookup"><span data-stu-id="87799-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="87799-114">Nedan följer några typiska källor till en avvikelse i **produktionspris**:</span><span class="sxs-lookup"><span data-stu-id="87799-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="87799-115">Kostnadskategorin (och dess kostnadskategoripris) för den rapporterade förbrukningen av en flödesåtgärd avviker från den kostnadskategori som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="87799-116">Den aktiva kostnaden för kostnadskategoripriset avviker från det kostnadskategoripris som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="87799-117">Nedan följer några typiska källor till en avvikelse i **produktionskvantitet**:</span><span class="sxs-lookup"><span data-stu-id="87799-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="87799-118">Över- eller underuttag av en materialkomponent.</span><span class="sxs-lookup"><span data-stu-id="87799-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="87799-119">Över- eller underrapportering av tid för en flödesåtgärd.</span><span class="sxs-lookup"><span data-stu-id="87799-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="87799-120">Du tar emot mer eller mindre av den godkända kvantiteten av den överordnade artikeln i relation till orderkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="87799-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="87799-121">Du utfärdar dock komponenter och rapporteringsoperationer fullständigt, baserat på orderkvantiteten för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="87799-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="87799-122">Nedan följer några typiska källor till en avvikelse i **produktionsersättning**:</span><span class="sxs-lookup"><span data-stu-id="87799-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="87799-123">Uttag av en materialkomponent som inte finns i produktionsstrukturlistan.</span><span class="sxs-lookup"><span data-stu-id="87799-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="87799-124">Manuellt tillägg av en komponent i produktionsstrukturlistan och rapportering av den komponenten som förbrukad.</span><span class="sxs-lookup"><span data-stu-id="87799-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="87799-125">Rapportering av en artikel som förbrukad utan att den läggs till manuellt i produktionsstrukturlistan.</span><span class="sxs-lookup"><span data-stu-id="87799-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="87799-126">Manuellt tillägg av en åtgärd i produktionsflödet och rapportering av den åtgärden som förbrukad.</span><span class="sxs-lookup"><span data-stu-id="87799-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="87799-127">Vid skapandet av en produktionsorder väljer du en strukturlisteversionen som avviker från den som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="87799-128">Vid skapandet av produktionsordern väljer du en flödesversionen som avviker från den flödesversion som används i standardkostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="87799-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>





