---
title: Produktionsplanering
description: Det här ämnet beskriver planering för produktion och förklarar hur du ändrar planerade tillverkningsorder genom att använda Planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f9b5e4122fbd83ff76e0605b2f0816e10d2d9aab
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470843"
---
# <a name="production-planning"></a><span data-ttu-id="c5fc3-103">Produktionsplanering</span><span class="sxs-lookup"><span data-stu-id="c5fc3-103">Production planning</span></span>

<span data-ttu-id="c5fc3-104">Planeringsoptimering stöder flera produktionsscenarier.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-104">Planning Optimizations supports several production scenarios.</span></span> <span data-ttu-id="c5fc3-105">Om du migrerar från den befintliga, inbyggda huvudplaneringsmotorn, är det viktigt att du känner till vissa ändrade beteende.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-105">If you're migrating from the existing, built-in master planning engine, it's important that you be aware of some changed behavior.</span></span>

<span data-ttu-id="c5fc3-106">Följande video ger en kort introduktion till några av de begrepp som diskuteras i detta ämne: [Dynamics 365 Supply Chain Management: Förbättringar av planeringsoptimering](https://youtu.be/u1pcmZuZBTw).</span><span class="sxs-lookup"><span data-stu-id="c5fc3-106">The following video gives a short introduction to some of the concepts discussed in this topic: [Dynamics 365 Supply Chain Management: Planning Optimization enhancements](https://youtu.be/u1pcmZuZBTw).</span></span>

## <a name="planned-production-orders"></a><span data-ttu-id="c5fc3-107">Planerade produktionsorder</span><span class="sxs-lookup"><span data-stu-id="c5fc3-107">Planned production orders</span></span>

<span data-ttu-id="c5fc3-108">När huvudplaneringen skapar planerade order för att uppfylla behov, bestäms ordertypen av värdet i fältet **Typ av planerad order**.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-108">When master planning creates planned orders to fulfill requirements, the order type is determined by the value of the **Planned order type** field.</span></span> <span data-ttu-id="c5fc3-109">Om fältet **Typ av planerad order** anges till *Produktion*, skapas planerade produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-109">If the **Planned order type** field is set to *Production*, planned production orders are created.</span></span> <span data-ttu-id="c5fc3-110">Dessa planerade tillverkningsorder innehåller information om den aktiva strukturlistan och flödes-ID från de relaterade produktionsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-110">These planned production orders include information about the active bill of materials (BOM) and the route ID from the related production setup.</span></span>

## <a name="requirements-from-boms"></a><span data-ttu-id="c5fc3-111">Krav från strukturlistor</span><span class="sxs-lookup"><span data-stu-id="c5fc3-111">Requirements from BOMs</span></span>

<span data-ttu-id="c5fc3-112">Strukturlisteinformationen används vid huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-112">BOM information is honored during master planning.</span></span> <span data-ttu-id="c5fc3-113">Planutleveransen omfattar materialleveranser för att täcka relaterad materialbehov för produktion.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-113">The plan output includes material supply to cover related material demand for production.</span></span>

<span data-ttu-id="c5fc3-114">Under huvudplaneringen används den aktuella aktiva strukturlistan för att avgöra vilket material som krävs för produktionen.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-114">During master planning, the current, active BOM is used to determine the materials that are required for production.</span></span> <span data-ttu-id="c5fc3-115">Detta steg görs genom alla nivåer i strukturlistestrukturen som hör till den tillverkningsorder som krävs.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-115">This step is done through all levels of the BOM structure that is related to the required production order.</span></span> <span data-ttu-id="c5fc3-116">Materialbehov uppfylls genom att använda tillgänglig lagerbehållning, befintlig lagerbehållning och godkända planerade order.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-116">Material requirement is fulfilled by using available on-hand inventory, existing on-order supply, and approved planned orders.</span></span> <span data-ttu-id="c5fc3-117">Om mer material krävs någonstans skapas en planerad order för att täcka efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-117">If additional material is required anywhere, a planned order is created to cover the demand.</span></span>

## <a name="scheduling-during-firming"></a><span data-ttu-id="c5fc3-118">Planering vid bekräftelse</span><span class="sxs-lookup"><span data-stu-id="c5fc3-118">Scheduling during firming</span></span>

<span data-ttu-id="c5fc3-119">Planerade tillverkningsorder innehåller det flödes-ID som krävs för produktionsplanering.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-119">Planned production orders include the route ID that is required for production scheduling.</span></span> <span data-ttu-id="c5fc3-120">Det pågår dock planeringssupport under planeringskörningen för planerade order.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-120">However, scheduling support during the planning run for planned orders is pending.</span></span> <span data-ttu-id="c5fc3-121">Flödes-ID:t används för att tidsplanera planerade tillverkningsorder under bekräftad.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-121">The route ID is used to schedule planned production orders during firming.</span></span> <span data-ttu-id="c5fc3-122">Därför kan produktionstiden för planerade tillverkningsorder skilja sig från produktionstiden för relaterade tidsplanerade, bekräftade tillverkningsorder som genereras från dem, enligt beskrivningen här:</span><span class="sxs-lookup"><span data-stu-id="c5fc3-122">Therefore, the lead time on planned production orders can differ from the lead time on related scheduled, firmed production orders that are generated from them, as described here:</span></span>

- <span data-ttu-id="c5fc3-123">**Planerad produktionsorder** – Produktionstiden baseras på den statiska produktionstiden från den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-123">**Planned production order** – The lead time is based on the static lead time from the released product.</span></span>
- <span data-ttu-id="c5fc3-124">**Bekräftad tillverkningsorder** – Produktionstiden baseras på tidsplanering där flödesinformation och relaterade resursbegränsningar används.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-124">**Firmed production order** – The lead time is based on scheduling that uses route information and related resource constraints.</span></span>

<span data-ttu-id="c5fc3-125">Mer information om förväntad tillgänglighet för funktioner finns i [planeringsoptimeringsanalys](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c5fc3-125">For more information about expected feature availability, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

<span data-ttu-id="c5fc3-126">Om du är beroende av produktionsfunktionerna som inte är tillgängliga för Planeringsoptimering ännu kan du fortsätta att använda den inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-126">If you depend on production functionality that isn't yet available for Planning Optimization, you can continue to use the built-in master planning engine.</span></span> <span data-ttu-id="c5fc3-127">Inget undantag behövs.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-127">No exception is required.</span></span>

## <a name="delays"></a><span data-ttu-id="c5fc3-128">Fördröjningar</span><span class="sxs-lookup"><span data-stu-id="c5fc3-128">Delays</span></span>

<span data-ttu-id="c5fc3-129">Om produktionstiden för det material som krävs är längre än perioden mellan dagens datum och materialbehovsdatumet försenas den planerade ordern för det begärda materialet och den relaterade tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-129">If the lead time for required material is longer than the period between today's date and the material requirement date, the planned order for the required material and the related production order will be delayed.</span></span> <span data-ttu-id="c5fc3-130">För planerade order beräknas förseningen (i dagar) baserat på produktionstiden från den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-130">For planned orders, the delay (in days) is calculated based on the lead time from the released product.</span></span> <span data-ttu-id="c5fc3-131">Fördröjningsinformationen sprids sedan genom alla nivåer i strukturlistestrukturen.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-131">The delay information is then propagated through all levels of the BOM structure.</span></span> <span data-ttu-id="c5fc3-132">Därför kan du följa inverkan från försenad råmaterial hela vägen till kundens försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-132">Therefore, you can follow the impact of delayed raw material all the way to the customer sales order.</span></span>

## <a name="modifying-planned-orders"></a><span data-ttu-id="c5fc3-133">Ändra planerade order</span><span class="sxs-lookup"><span data-stu-id="c5fc3-133">Modifying planned orders</span></span>

<span data-ttu-id="c5fc3-134">När du ändrar information om en planerad order visas följande meddelande: "Observera att effekten från manuella ändringar på planerade order inte kommer att återspeglas i resten av planen förrän nästa huvudplaneringskörning."</span><span class="sxs-lookup"><span data-stu-id="c5fc3-134">When you change information on a planned order, you receive the following message: "Note that the impact of manual changes on planned orders won't be reflected in the rest of the plan until the next master planning run."</span></span>

<span data-ttu-id="c5fc3-135">Följ de här stegen om du vill ändra informationen i en planerad order och se effekten på de relaterade materialbehoven.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-135">If you want to change information on a planned order and see the impact on the related material requirements, follow these steps.</span></span>

1. <span data-ttu-id="c5fc3-136">Uppdatera planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-136">Update the planned order.</span></span>
2. <span data-ttu-id="c5fc3-137">Godkänna planerade order.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-137">Approve the planned order.</span></span>
3. <span data-ttu-id="c5fc3-138">Kör Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-138">Run master planning.</span></span>

<span data-ttu-id="c5fc3-139">När du kör huvudplanering bör du inte använda filter om planerade tillverkningsorder inkluderas.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-139">When you run master planning, you should not use filters if planned production orders are included.</span></span> <span data-ttu-id="c5fc3-140">Mer information finns i avsnittet [Filter](#filters) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-140">For more information, see the [Filters](#filters) section later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="c5fc3-141">Om leveransdatumet för den planerade ordern ändras till ett senare datum kan efterfrågan pegged mot en ny planerad order.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-141">If the delivery date of the planned order is changed to a later date, the demand might be pegged against a new planned order.</span></span> <span data-ttu-id="c5fc3-142">Detta beteende inträffar när det nya leveransdatumet orsakar en fördröjning för den pegged efterfrågan, men enligt inställningarna för ledtid kan förseningen undviks.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-142">This behavior occurs when the new supply date causes a delay for the pegged demand but, according to the lead time settings, the delay can be avoided.</span></span>

## <a name="explosion-page"></a><span data-ttu-id="c5fc3-143">Nedbrytningssida</span><span class="sxs-lookup"><span data-stu-id="c5fc3-143">Explosion page</span></span>

<span data-ttu-id="c5fc3-144">På sidan **Nedbrytning** kan du analysera behovet av en viss tillverkningsorder eller planerad tillverkningsorder, tillhörande disponering och pegging-information.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-144">You can use the **Explosion** page to analyze the demand that is required for a specific production order or planned production order, the related coverage, and pegging information.</span></span> <span data-ttu-id="c5fc3-145">Informationen på sidan **Nedbrytning** uppdateras under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-145">Information on the **Explosion** page is updated during master planning.</span></span> <span data-ttu-id="c5fc3-146">Du kan inte uppdatera informationen direkt från sidan **Nedbrytning**.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-146">You can't update the information directly from the **Explosion** page.</span></span>

## <a name="filters"></a><a name="filters"></a><span data-ttu-id="c5fc3-147">Filter</span><span class="sxs-lookup"><span data-stu-id="c5fc3-147">Filters</span></span>

<span data-ttu-id="c5fc3-148">Vid planering av scenarier där produktion ingår bör du undvika filtrerade huvudplaneringskörningar.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-148">For planning scenarios that include production, we recommend that you avoid filtered master planning runs.</span></span> <span data-ttu-id="c5fc3-149">Om du vill vara säker på att Planeringsoptimering har den information som krävs för att beräkna rätt resultat, måste du inkludera alla produkter som har alla relationer till produkter i hela strukturlistestrukturen för den planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-149">To ensure that Planning Optimization has the information that is required to calculate the correct result, you must include all products that have any relation to products in the whole BOM structure of the planned order.</span></span>

<span data-ttu-id="c5fc3-150">Underordnade artiklar som är beroende hittas automatiskt och inkluderas i huvudplaneringskörningar när den inbyggda huvudplaneringsmotorn används, men den här åtgärden utförs inte under Planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-150">Although dependent child items are automatically detected and included in master planning runs when the built-in master planning engine is used, Planning Optimization doesn't perform this action.</span></span>

<span data-ttu-id="c5fc3-151">Om till exempel en enda blixt från strukturlistestrukturen för produkt A även används för att tillverka produkt B, måste alla produkter i strukturlistestrukturen för produkter A och B inkluderas i filtret.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-151">For example, if a single bolt from the BOM structure of product A is also used to produce product B, all products in the BOM structure of products A and B must be included in the filter.</span></span> <span data-ttu-id="c5fc3-152">Eftersom det kan vara mycket komplicerat att säkerställa att alla produkter ingår i filtret rekommenderar vi att du undviker filtrerade huvudplaneringskörningar när tillverkningsorder används.</span><span class="sxs-lookup"><span data-stu-id="c5fc3-152">Because it can be very complex to ensure that all products are part of the filter, we recommend that you avoid filtered master planning runs when production orders are involved.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]