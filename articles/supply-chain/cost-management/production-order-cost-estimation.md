---
title: Kostnadsuppskattning av produktionsorder
description: Det här avsnittet innehåller information om produktionskostnadsuppskattning. Produktionskostnadsuppskattning ger dig information om material- och kapacitetsförbrukningskostnader vid produktion av en artikel i den kvantitet som anges på den planerade produktionsordern.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93546fc170757ee2c39144842bae12d78400fd32
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547800"
---
# <a name="production-order-cost-estimation"></a><span data-ttu-id="199bf-104">Kostnadsuppskattning av produktionsorder</span><span class="sxs-lookup"><span data-stu-id="199bf-104">Production order cost estimation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="199bf-105">Det här avsnittet innehåller information om produktionskostnadsuppskattning.</span><span class="sxs-lookup"><span data-stu-id="199bf-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="199bf-106">Produktionskostnadsuppskattning ger dig information om material- och kapacitetsförbrukningskostnader vid produktion av en artikel i den kvantitet som anges på den planerade produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="199bf-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="199bf-107">När du har skapat en produktionsorder måste du beräkna produktionskostnader.</span><span class="sxs-lookup"><span data-stu-id="199bf-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="199bf-108">Syftet är att uppskatta artikel- och flödesförbrukningen under produktionsprocessen eftersom dessa uppskattningar används för de efterföljande planerings- och produktionsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="199bf-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="199bf-109">Uppskattning av produktionskostnad</span><span class="sxs-lookup"><span data-stu-id="199bf-109">Production cost estimation</span></span>
<span data-ttu-id="199bf-110">Uppskattning av produktionskostnader baseras på följande information:</span><span class="sxs-lookup"><span data-stu-id="199bf-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="199bf-111">Kvantitet på produktionsordern</span><span class="sxs-lookup"><span data-stu-id="199bf-111">The quantity on the production order</span></span>
-   <span data-ttu-id="199bf-112">Komponenterna i produktionsstrukturlistorna (BOMs)</span><span class="sxs-lookup"><span data-stu-id="199bf-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="199bf-113">Flödesoperationerna i produktionsflödet</span><span class="sxs-lookup"><span data-stu-id="199bf-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="199bf-114">Indirekta kostnader som gäller för komponenter och operationer</span><span class="sxs-lookup"><span data-stu-id="199bf-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="199bf-115">Aktiva kostnadsdata vid beräkningsdatumet</span><span class="sxs-lookup"><span data-stu-id="199bf-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="199bf-116">Om det finns en fiktiv radartikel i produktionsstrukturlistan återspeglar beräkningarna den fiktiva artikelns komponenter och flödesoperationer.</span><span class="sxs-lookup"><span data-stu-id="199bf-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="199bf-117">Du kan använda uppskattningsuppgiften när du beräknar om uppskattade kostnader för att återspegla uppdaterad information.</span><span class="sxs-lookup"><span data-stu-id="199bf-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="199bf-118">Den uppdaterade informationen kan till exempel vara ändringar i tillverkningsorderkvantiteten, komponenterna i produktionsstrukturlistan, flödesoperationerna i produktionsflödet, de indirekta kostnaderna som gäller för de här komponenterna och operationerna eller aktiva kostnadsdata på omräkningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="199bf-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="199bf-119">Beräkningarna av uppskattad kostnad föreslår också ett försäljningspris för produktionsartikeln baserat på kostnader plus tillägg.</span><span class="sxs-lookup"><span data-stu-id="199bf-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="199bf-120">Beräkningarna av uppskattad kostnad kan också gälla för referensorder som återspeglar andra tillverkningsorder som är länkade till tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="199bf-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="199bf-121">Visa uppskattade kostnader</span><span class="sxs-lookup"><span data-stu-id="199bf-121">View the estimated costs</span></span>
<span data-ttu-id="199bf-122">När du har kört en uppskattning kan du visa resultaten på sidan **Prisberäkning**.</span><span class="sxs-lookup"><span data-stu-id="199bf-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="199bf-123">Vid uppskattningen beräknas följande värden:</span><span class="sxs-lookup"><span data-stu-id="199bf-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="199bf-124">**Produktionskostnad** – Produktionskostnaden visas på den översta raden i uppskattningen.</span><span class="sxs-lookup"><span data-stu-id="199bf-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="199bf-125">Här visas den fullständiga kostnaden för tillverkningsordern och det totala försäljningspriset för produktionen.</span><span class="sxs-lookup"><span data-stu-id="199bf-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="199bf-126">Detta är summan av alla kostnadsrader i uppskattningen.</span><span class="sxs-lookup"><span data-stu-id="199bf-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="199bf-127">**Flödes- eller resurskostnader** – Flödes- eller resurskostnader är kostnader för produktionsoperationerna.</span><span class="sxs-lookup"><span data-stu-id="199bf-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="199bf-128">De inkluderar kostnaden för element såsom inställningstid, körtid och omkostnader.</span><span class="sxs-lookup"><span data-stu-id="199bf-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="199bf-129">**Materialkostnader** – Materialkostnader är de kostnader och priser för strukturlistekomponenter som krävs för att tillverka artikeln.</span><span class="sxs-lookup"><span data-stu-id="199bf-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="199bf-130">De här kostnaderna har tidigare fastställts och registrerats i systemet.</span><span class="sxs-lookup"><span data-stu-id="199bf-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="199bf-131">Andra användningsområden för kostnadsuppskattning</span><span class="sxs-lookup"><span data-stu-id="199bf-131">Other uses of cost estimation</span></span>
<span data-ttu-id="199bf-132">En kostnadsuppskattning ger även följande information:</span><span class="sxs-lookup"><span data-stu-id="199bf-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="199bf-133">Välgrundande prisofferter</span><span class="sxs-lookup"><span data-stu-id="199bf-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="199bf-134">Uppskattning av orderns lönsamhet</span><span class="sxs-lookup"><span data-stu-id="199bf-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="199bf-135">Uppskattning av råmaterialanvändning</span><span class="sxs-lookup"><span data-stu-id="199bf-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="199bf-136">Jämförelser av kostnadsinformation från tidigare produktioner</span><span class="sxs-lookup"><span data-stu-id="199bf-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="199bf-137">Budget- och prognosinformation</span><span class="sxs-lookup"><span data-stu-id="199bf-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="199bf-138">Uppskattning av vilken produktionsstorlek som krävs för att upprätthålla en viss kostnad</span><span class="sxs-lookup"><span data-stu-id="199bf-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>




