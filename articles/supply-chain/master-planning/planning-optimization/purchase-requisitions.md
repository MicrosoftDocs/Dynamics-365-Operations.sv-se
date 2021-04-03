---
title: Inköpsrekvisitioner
description: Det här ämnet beskriver hur inköpsrekvisitioner stöds i Planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 20b4012e054a25d7d21c6f017d8ebcf18f6ee28d
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501088"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="c20e0-103">Inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="c20e0-103">Purchase requisitions</span></span>

<span data-ttu-id="c20e0-104">Huvudplaneringen kan fylla på godkända inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="c20e0-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="c20e0-105">För att täcka inköpsrekvisitioner behöver därför användarna inte använda ett arbetsflöde för att skapa inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c20e0-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="c20e0-106">I stället kan inköpsrekvisitioner täckas av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="c20e0-107">På grund av den här funktionen kan en inköpsrekvisition producera en inköpsorder, en överföringsorder eller en tillverkningsorder, beroende på värdet för **Planerad ordertyp** som har angetts för den relaterade produkten.</span><span class="sxs-lookup"><span data-stu-id="c20e0-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="c20e0-108">Aktivera huvudplaner för att inkludera rekvisitioner</span><span class="sxs-lookup"><span data-stu-id="c20e0-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="c20e0-109">Följ de här stegen om du vill ta med rekvisitioner under disponeringsberäkningen för en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="c20e0-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="c20e0-110">Gå till **Huvudplanering** \> **Inställningar** \> **Planer** \> **Huvudplaner**.</span><span class="sxs-lookup"><span data-stu-id="c20e0-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="c20e0-111">Skapa eller välj huvudplan.</span><span class="sxs-lookup"><span data-stu-id="c20e0-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="c20e0-112">På snabbfliken **allmänt** anger du alternativet **Inkludera rekvisitioner** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="c20e0-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="c20e0-113">Upprepa steg 2 och 3 för varje ytterligare huvudplan där du vill ta med rekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="c20e0-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="c20e0-114">Godkänd rekvisitionstidsgräns</span><span class="sxs-lookup"><span data-stu-id="c20e0-114">Approved requisitions time fence</span></span>

<span data-ttu-id="c20e0-115">Den *godkända rekvisitionstidsgränsen* anger hur långt tillbaka (i dagar) en huvudplan kommer att omfatta efterfrågan från godkända påfyllnadsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="c20e0-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="c20e0-116">Du kan ställa in en godkänd rekvisitionstidsgräns på både disponeringsgruppnivå och huvudplansnivå.</span><span class="sxs-lookup"><span data-stu-id="c20e0-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="c20e0-117">Ställa in tidsgräns för godkända rekvisitioner för en disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="c20e0-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="c20e0-118">Gå till **huvudplanering** \> **inställningar** \> **täckning** \> **disponeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="c20e0-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**.</span></span>
1. <span data-ttu-id="c20e0-119">Skapa eller välj en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c20e0-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="c20e0-120">På snabbfliken **Annat** anger du **tidsgränsen för godkända rekvisitioner (dagar)** till antalet dagar som ska inkluderas i tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="c20e0-121">Upprepa steg 2 och 3 för varje ytterligare disponeringsgrupp där du vill ställa in en godkänd tidsgräns för rekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="c20e0-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="c20e0-122">Ställa in tidsgräns för godkända rekvisitioner för en individuell huvudplan</span><span class="sxs-lookup"><span data-stu-id="c20e0-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="c20e0-123">När du anger en godkänd rekvisitionstidsgräns för en enskild huvudplan åsidosätter inställningen tidsgränsinställningen för disponeringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="c20e0-124">Gå till **Huvudplanering** \> **Inställningar** \> **Planer** \> **Huvudplaner**.</span><span class="sxs-lookup"><span data-stu-id="c20e0-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="c20e0-125">Skapa eller välj huvudplan.</span><span class="sxs-lookup"><span data-stu-id="c20e0-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="c20e0-126">På snabbfliken **Tidsgräns i dagar** anger du **tidsgränsen för godkända rekvisitioner (dagar)** till antalet dagar som ska inkluderas i tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="c20e0-127">Upprepa steg 2 och 3 för varje ytterligare huvudplan där du vill ställa in en godkänd tidsgräns för rekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="c20e0-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c20e0-128">**Kommer snart:** Godkända rekvisitioner tidsgränser stöds ännu inte för Planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="c20e0-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="c20e0-129">Till dess att de stöds ignoreras alla värden som du anger i fältet **tidsgränsen för godkända rekvisitioner (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="c20e0-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="c20e0-130">Oberoende leverans, oavsett disponeringskod</span><span class="sxs-lookup"><span data-stu-id="c20e0-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="c20e0-131">Inköpsrekvisitioner omfattas alltid av oberoende planerade order, oavsett disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="c20e0-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="c20e0-132">Detta garanterar en tydlig spårning och arbetsflöden mellan inköpsrekvisitioner och påfyllnadsorder.</span><span class="sxs-lookup"><span data-stu-id="c20e0-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="c20e0-133">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="c20e0-133">Example 1</span></span>

<span data-ttu-id="c20e0-134">En produkt ställs in så att den har ett **disponeringskodsvärde** för *Min/max*. Det har följande status för lager och rekvisitioner:</span><span class="sxs-lookup"><span data-stu-id="c20e0-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="c20e0-135">Lagerbehållningskvantitet = 10.</span><span class="sxs-lookup"><span data-stu-id="c20e0-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="c20e0-136">Minsta lagerkvantitet = 15.</span><span class="sxs-lookup"><span data-stu-id="c20e0-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="c20e0-137">Maximal lagerkvantitet = 20.</span><span class="sxs-lookup"><span data-stu-id="c20e0-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="c20e0-138">Det finns en inköpsrekvisition för en del.</span><span class="sxs-lookup"><span data-stu-id="c20e0-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="c20e0-139">Det har ett begärt datum för idag.</span><span class="sxs-lookup"><span data-stu-id="c20e0-139">It has a requested date of today.</span></span>

<span data-ttu-id="c20e0-140">När huvudplaneringen körs skapas två planerade order: en för tio enheter för att fylla på lagret till den största kvantiteten och en för en del för att fylla på inköpsrekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="c20e0-141">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="c20e0-141">Example 2</span></span>

<span data-ttu-id="c20e0-142">En produkt ställs in så att den har ett **disponeringskodsvärde** för *Min/max*. Det har följande status för lager och rekvisitioner:</span><span class="sxs-lookup"><span data-stu-id="c20e0-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="c20e0-143">Lagerbehållningskvantitet = 17.</span><span class="sxs-lookup"><span data-stu-id="c20e0-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="c20e0-144">Minsta lagerkvantitet = 15.</span><span class="sxs-lookup"><span data-stu-id="c20e0-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="c20e0-145">Maximal lagerkvantitet = 20.</span><span class="sxs-lookup"><span data-stu-id="c20e0-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="c20e0-146">Det finns en inköpsrekvisition för en del.</span><span class="sxs-lookup"><span data-stu-id="c20e0-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="c20e0-147">Det har ett begärt datum för idag.</span><span class="sxs-lookup"><span data-stu-id="c20e0-147">It has a requested date of today.</span></span>

<span data-ttu-id="c20e0-148">När huvudplaneringen körs skapas en planerad order för en del för att fylla på inköpsrekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="c20e0-149">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="c20e0-149">Example 3</span></span>

<span data-ttu-id="c20e0-150">En produkt ställs in så att den har ett **disponeringskodvärde** för *Period* och en periodlängd på sju dagar.</span><span class="sxs-lookup"><span data-stu-id="c20e0-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="c20e0-151">Den har följande status för lager, försäljningsorder och rekvisitioner:</span><span class="sxs-lookup"><span data-stu-id="c20e0-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="c20e0-152">Lagerbehållningskvantitet = 0.</span><span class="sxs-lookup"><span data-stu-id="c20e0-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="c20e0-153">Det finns en försäljningsorder med fem enheter.</span><span class="sxs-lookup"><span data-stu-id="c20e0-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="c20e0-154">Den har ett förväntat transportdatum för idag plus en dag.</span><span class="sxs-lookup"><span data-stu-id="c20e0-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="c20e0-155">Det finns en inköpsrekvisition för tre delar.</span><span class="sxs-lookup"><span data-stu-id="c20e0-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="c20e0-156">Det har ett begärt datum för idag plus tre dagar.</span><span class="sxs-lookup"><span data-stu-id="c20e0-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="c20e0-157">När huvudplaneringen körs skapas två planerade order: en för tre delar för att fylla på inköpsrekvisitionen och en för fem för att fylla på efterfrågan på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="c20e0-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="c20e0-158">När en planerad order som är pegging till en inköpsrekvisition har bekräftats, behåller planeringsmotorn peggingen på inköpsrekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="c20e0-159">Om den bekräftade ordern senare visar sig sakna en viss kvantitet som krävs för att uppfylla inköpsrekvisitionen, skapas en ny planerad order för differensen.</span><span class="sxs-lookup"><span data-stu-id="c20e0-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="c20e0-160">Mer information om inköpsrekvisitioner finns i [översikten över inköpsrekvisitioner](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c20e0-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]