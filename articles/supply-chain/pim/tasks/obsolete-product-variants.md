---
title: Sök efter inaktuella produktvarianter
description: Den här proceduren visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 807297a87a7f0e59023d80fbd371bffbf2b086bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808002"
---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="9479d-103">Sök efter inaktuella produktvarianter</span><span class="sxs-lookup"><span data-stu-id="9479d-103">Find obsolete product variants</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9479d-104">Den här proceduren visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna.</span><span class="sxs-lookup"><span data-stu-id="9479d-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="9479d-105">Förutsättning: Du måste definiera minst ett produktlivscykeltillstånd som har inaktiverats för planering innan du kan spela upp denna uppgiftsguide.</span><span class="sxs-lookup"><span data-stu-id="9479d-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="9479d-106">Kör en simulering</span><span class="sxs-lookup"><span data-stu-id="9479d-106">Run a simulation</span></span>
1. <span data-ttu-id="9479d-107">Gå till produktinformationshantering > periodiska uppgifter > ändra status för gamla produkter.</span><span class="sxs-lookup"><span data-stu-id="9479d-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="9479d-108">Ange eller välj ett värde i fältet Nytt produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="9479d-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="9479d-109">Välj Ja i fältet Kör en simulering utan att uppdatera produktdata.</span><span class="sxs-lookup"><span data-stu-id="9479d-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="9479d-110">Ange ett nummer i fältet Undanta produkter som har skapats inom detta antal dagar.</span><span class="sxs-lookup"><span data-stu-id="9479d-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="9479d-111">Ange ett nummer i fältet Undanta produkter som används i transkationer inom detta antal dagar.</span><span class="sxs-lookup"><span data-stu-id="9479d-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="9479d-112">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="9479d-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="9479d-113">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="9479d-113">Click Filter.</span></span>
8. <span data-ttu-id="9479d-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9479d-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="9479d-115">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="9479d-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="9479d-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9479d-116">Click OK.</span></span>
11. <span data-ttu-id="9479d-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9479d-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="9479d-118">Du rekommenderas att köra simuleringen i batch om du tänker söka ett stort antal produkter.</span><span class="sxs-lookup"><span data-stu-id="9479d-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="9479d-119">Kontrollera också att simuleringen inte körs under den mest aktiva arbetstiden för företaget.</span><span class="sxs-lookup"><span data-stu-id="9479d-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="9479d-120">Granska simuleringsresultatet.</span><span class="sxs-lookup"><span data-stu-id="9479d-120">Review the simulation results</span></span>
1. <span data-ttu-id="9479d-121">Gå till produktinformationshantering > förfrågningar och rapporter > Underhållshistorik för produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="9479d-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="9479d-122">På den här sidan kan du också granska resultaten för simulering och bedöma hur många produkter och produktvarianter som ska kopplas till ett nytt produktlivscykeltillstånd när du kör uppdateringen utan simulering.</span><span class="sxs-lookup"><span data-stu-id="9479d-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="9479d-123">Kör uppdateringen av produktlivscykeltillstånd för föråldrade produkter</span><span class="sxs-lookup"><span data-stu-id="9479d-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="9479d-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9479d-124">Close the page.</span></span>
2. <span data-ttu-id="9479d-125">Gå till produktinformationshantering > periodiska uppgifter > ändra status för gamla produkter.</span><span class="sxs-lookup"><span data-stu-id="9479d-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="9479d-126">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="9479d-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="9479d-127">Observera att den senaste markeringen har sparats.</span><span class="sxs-lookup"><span data-stu-id="9479d-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="9479d-128">Välj Ne i fältet Kör en simulering utan att uppdatera produktdata.</span><span class="sxs-lookup"><span data-stu-id="9479d-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="9479d-129">Expandera avsnittet Kör i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="9479d-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="9479d-130">Beroende på hur många produkterna och produktvarianterna påverka, överväg det här jobbet i batch.</span><span class="sxs-lookup"><span data-stu-id="9479d-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="9479d-131">Se till att du inte kör ett jobb för större uppdatering under företagets mest aktiva arbetstid.</span><span class="sxs-lookup"><span data-stu-id="9479d-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="9479d-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9479d-132">Click OK.</span></span>
7. <span data-ttu-id="9479d-133">Gå till produktinformationshantering > förfrågningar och rapporter > Underhållshistorik för produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="9479d-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="9479d-134">Granska de ändrade frisläppta produkterna och produktvarianterna</span><span class="sxs-lookup"><span data-stu-id="9479d-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="9479d-135">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9479d-135">In the list, find and select the desired record.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]