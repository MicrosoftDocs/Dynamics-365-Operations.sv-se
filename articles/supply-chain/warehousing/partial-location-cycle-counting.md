---
title: Rullande inventering av del av platser
description: Planer för rullande inventering guidar de faktiska räkningsoperationerna. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f07c7754dbe36334e8972d49edf9fb84a78f5d0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215687"
---
# <a name="partial-location-cycle-counting"></a><span data-ttu-id="8d659-104">Rullande inventering av del av platser</span><span class="sxs-lookup"><span data-stu-id="8d659-104">Partial location cycle counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d659-105">Planer för rullande inventering guidar de faktiska räkningsoperationerna.</span><span class="sxs-lookup"><span data-stu-id="8d659-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="8d659-106">Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.</span><span class="sxs-lookup"><span data-stu-id="8d659-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="8d659-107">Du kan vägleda de faktiska räkningsoperationerna genom att använda planer för rullande inventering för att skapa räkningsarbeten.</span><span class="sxs-lookup"><span data-stu-id="8d659-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="8d659-108">Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.</span><span class="sxs-lookup"><span data-stu-id="8d659-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="8d659-109">Genom att filtrera efter specifika produkter kan lagerchefen minska granskningsomkostnaderna, undvika konsolideringsmisstag och spara tid.</span><span class="sxs-lookup"><span data-stu-id="8d659-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="8d659-110">Så här konfigurerar du partiell rullande inventering för plats</span><span class="sxs-lookup"><span data-stu-id="8d659-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="8d659-111">När du använder arbetsprocessen för lagerställe för inventeringsoperationer skapas en arbetsrubrik för varje plats.</span><span class="sxs-lookup"><span data-stu-id="8d659-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="8d659-112">När du definierar planen för rullande inventering kan du använda frågan **Välj platser** för att begränsa arbetet för rullande inventering som skapas.</span><span class="sxs-lookup"><span data-stu-id="8d659-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="8d659-113">När du väljer produkter för planen för rullande inventering kan du välja både produkt- och produktvariantfrågor för att begränsa det som räknas.</span><span class="sxs-lookup"><span data-stu-id="8d659-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="8d659-114">Du kan associera en **arbetsmall** med en plan för rullande inventering för att definiera hur arbetet för rullande inventering ska skapas.</span><span class="sxs-lookup"><span data-stu-id="8d659-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="8d659-115">Arbetsmallen för inventeringsoperationer refereras direkt från planen för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="8d659-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="8d659-116">När du definierar arbetets mallinformation kan du använda alternativet **Arbetsradbrytningar** för att ange om inventeringsrader för arbete måste grupperas efter artikelnummer eller produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="8d659-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="8d659-117">Denna konfiguration krävs om du vill inventera tillgänglig lagerbehållning endast för specifika produkter på en plats.</span><span class="sxs-lookup"><span data-stu-id="8d659-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="8d659-118">Arbetsraderna för rullande inventering som skapas får den mängd information som du definierar här, och de vägledda räkneoperationerna hanteras baserat på denna nivå.</span><span class="sxs-lookup"><span data-stu-id="8d659-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="8d659-119">Om du associerar planerna för rullande inventering med arbetsmallar genom att använda alternativet **Arbetsradbrytningar**, väljs fältet **Partiell rullande inventering** för det arbete för rullande inventering som skapas, och multipla arbetsrader för rullande inventering skapas baserat på arbetsmallens definition.</span><span class="sxs-lookup"><span data-stu-id="8d659-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="8d659-120">Innan arbetet för partiell rullande inventering kan bearbetas, måste du välja minst **Visa artikelnummer** för menyalternativet för mobil enhet som en del av konfigurationen för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="8d659-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="8d659-121">Lageroperatören kommer att uppmanas att registrera endast inventeringsinformation som är relaterad till inventeringsraderna (artikelnummer och produktdimensioner).</span><span class="sxs-lookup"><span data-stu-id="8d659-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="8d659-122">Alla andra tillgängliga lager kommer att ignoreras för den här inventeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8d659-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="8d659-123">För den partiella rullande inventeringsprocessen kommer datum/tid för **Senaste rullande inventering** inte att uppdateras för platsen.</span><span class="sxs-lookup"><span data-stu-id="8d659-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="8d659-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="8d659-124">Example</span></span>
<span data-ttu-id="8d659-125">I det här exemplet måste bara artikelnumret A0001 räknas i lagerställe 61.</span><span class="sxs-lookup"><span data-stu-id="8d659-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="8d659-126">En ny arbetsmall skapas för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="8d659-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="8d659-127">Alternativet **Arbetsradbrytningar** används för att gruppera inventeringsrader för arbete efter artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8d659-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="8d659-128">Det arbete för rullande inventering som skapas kommer får därför rader per artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8d659-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="8d659-129">Du kan också gruppera raderna efter produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="8d659-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="8d659-130">En ny plan för rullande inventering som hänvisar till den nyskapade arbetsmallen skapas.</span><span class="sxs-lookup"><span data-stu-id="8d659-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="8d659-131">Planen för rullande inventering innehåller alla platser på lagerställe 61 (frågan **Välj platser**) som håller lager för artikelnummer A0001.</span><span class="sxs-lookup"><span data-stu-id="8d659-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="8d659-132">Valet av specifika produkter definieras i avsnittet **Produkturval för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="8d659-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="8d659-133">Du kan välja produkter för planer för rullande inventering genom att ange fältet **tomma platser** till **utelämna tomma**.</span><span class="sxs-lookup"><span data-stu-id="8d659-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.</span></span> <span data-ttu-id="8d659-134">När planen för rullande inventering bearbetas, skapas delvis rullande inventeringsarbete för artikelnummer A0001.</span><span class="sxs-lookup"><span data-stu-id="8d659-134">When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="8d659-135">Den faktiska inventeringsprocessen kan utföras genom att använda ett menyalternativ för guidad rullande inventering i en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="8d659-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="additional-resources"></a><span data-ttu-id="8d659-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8d659-136">Additional resources</span></span>
--------

[<span data-ttu-id="8d659-137">Rullande inventering</span><span class="sxs-lookup"><span data-stu-id="8d659-137">Cycle counting</span></span>](cycle-counting.md)

