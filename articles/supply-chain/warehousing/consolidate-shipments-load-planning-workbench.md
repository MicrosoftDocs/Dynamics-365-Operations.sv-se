---
title: Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 30824bf1c8e84bab08b6885ee812ed5e3e9937bb
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117191"
---
# <a name="consolidate-shipments-by-releasing-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="62be8-103">Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="62be8-103">Consolidate shipments by releasing to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62be8-104">Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.</span><span class="sxs-lookup"><span data-stu-id="62be8-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="62be8-105">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="62be8-105">Make demo data available</span></span>

<span data-ttu-id="62be8-106">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="62be8-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="62be8-107">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="62be8-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="62be8-108">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="62be8-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="62be8-109">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="62be8-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="62be8-110">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="62be8-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="62be8-111">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="62be8-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="62be8-112">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="62be8-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="62be8-113">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="62be8-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="62be8-114">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="62be8-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="62be8-115">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="62be8-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="62be8-116">Skapa orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="62be8-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="62be8-117">Försäljningsorder 1-1</span><span class="sxs-lookup"><span data-stu-id="62be8-117">Sales order 1-1</span></span>

1. <span data-ttu-id="62be8-118">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="62be8-119">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="62be8-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="62be8-120">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="62be8-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="62be8-121">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-122">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-123">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-124">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="62be8-125">Försäljningsorder 1-2</span><span class="sxs-lookup"><span data-stu-id="62be8-125">Sales order 1-2</span></span>

1. <span data-ttu-id="62be8-126">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="62be8-127">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="62be8-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="62be8-128">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="62be8-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="62be8-129">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-130">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-131">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-132">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="62be8-133">Försäljningsorder 1-3</span><span class="sxs-lookup"><span data-stu-id="62be8-133">Sales order 1-3</span></span>

1. <span data-ttu-id="62be8-134">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="62be8-135">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="62be8-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="62be8-136">**Leveranssätt:** *10*</span><span class="sxs-lookup"><span data-stu-id="62be8-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="62be8-137">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-138">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-139">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-140">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="62be8-141">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-142">**Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-143">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="62be8-144">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="62be8-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="62be8-145">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="62be8-146">Skapa orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="62be8-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="62be8-147">Försäljningsorder 2-1 och 2-2</span><span class="sxs-lookup"><span data-stu-id="62be8-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="62be8-148">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-149">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="62be8-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="62be8-150">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-151">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="62be8-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="62be8-152">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-153">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="62be8-154">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-155">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="62be8-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="62be8-156">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="62be8-157">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="62be8-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="62be8-158">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="62be8-159">Skapa orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="62be8-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="62be8-160">Försäljningsorder 3-1 och 3-2</span><span class="sxs-lookup"><span data-stu-id="62be8-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="62be8-161">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-162">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="62be8-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="62be8-163">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="62be8-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="62be8-164">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-165">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-166">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-167">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="62be8-168">Försäljningsorder 3-3 och 3-4</span><span class="sxs-lookup"><span data-stu-id="62be8-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="62be8-169">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-170">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="62be8-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="62be8-171">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="62be8-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="62be8-172">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-173">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-174">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-175">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="62be8-176">Skapa orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="62be8-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="62be8-177">Försäljningsorder 4-1 och 4-2</span><span class="sxs-lookup"><span data-stu-id="62be8-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="62be8-178">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-179">**Kundkonto:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="62be8-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="62be8-180">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-181">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-182">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-183">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="62be8-184">Försäljningsorder 4-3 och 4-4</span><span class="sxs-lookup"><span data-stu-id="62be8-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="62be8-185">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-186">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="62be8-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="62be8-187">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-188">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-189">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-190">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="62be8-191">Försäljningsorder 4-5 och 4-6</span><span class="sxs-lookup"><span data-stu-id="62be8-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="62be8-192">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-193">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="62be8-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="62be8-194">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="62be8-194">**Site:** *6*</span></span>
    - <span data-ttu-id="62be8-195">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="62be8-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="62be8-196">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="62be8-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="62be8-197">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-198">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-199">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-200">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="62be8-201">Försäljningsorder 4-7 och 4-8</span><span class="sxs-lookup"><span data-stu-id="62be8-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="62be8-202">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62be8-203">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="62be8-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="62be8-204">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="62be8-204">**Site:** *6*</span></span>
    - <span data-ttu-id="62be8-205">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="62be8-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="62be8-206">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="62be8-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="62be8-207">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62be8-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62be8-208">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="62be8-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62be8-209">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62be8-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62be8-210">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="62be8-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="62be8-211">Använd workbench för lastplanering för att skapa beläggningar och släppa dem till lagerstället</span><span class="sxs-lookup"><span data-stu-id="62be8-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="62be8-212">Följ dessa steg för att skapa en beläggning för varje orderuppsättning som du har skapat för scenariot och sedan släppa den till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="62be8-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="62be8-213">Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="62be8-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="62be8-214">På fliken **Försäljningsrader** letar du upp och markerar alla försäljningsorderrader från en av orderuppsättningar som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="62be8-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="62be8-215">I åtgärdsfönstret väljer du **tillgång och efterfrågan**, väljer **Lägg till \> Till ny beläggning** om du vill lägga till valda orderlinjer i en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="62be8-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="62be8-216">I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *Stnd Load Template*.</span><span class="sxs-lookup"><span data-stu-id="62be8-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="62be8-217">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="62be8-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="62be8-218">I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du just skapat.</span><span class="sxs-lookup"><span data-stu-id="62be8-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="62be8-219">Välj **Släpp \> Släpp till lagerställe** om du vill frisläppa den valda beläggningen till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="62be8-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="62be8-220">Upprepa den här proceduren för samtliga de tre andra orderuppsättningar som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="62be8-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="62be8-221">Verifiera leveranserna</span><span class="sxs-lookup"><span data-stu-id="62be8-221">Verify the shipments</span></span>

<span data-ttu-id="62be8-222">Med följande procedur kan du verifiera de leveranser som har skapats eller uppdaterats som ett resultat av leveranskonsolideringen.</span><span class="sxs-lookup"><span data-stu-id="62be8-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="62be8-223">Granska varje orderuppsättning som du har skapat för det här scenariot, och granska sedan de underavsnitt som följer för att se till att du har fått de förväntade resultaten.</span><span class="sxs-lookup"><span data-stu-id="62be8-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="62be8-224">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="62be8-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="62be8-225">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="62be8-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="62be8-226">Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="62be8-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="62be8-227">Frisläpp orderuppsättning 1 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="62be8-227">Release order set 1 in one load</span></span>

<span data-ttu-id="62be8-228">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="62be8-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="62be8-229">Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.</span><span class="sxs-lookup"><span data-stu-id="62be8-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="62be8-230">Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.</span><span class="sxs-lookup"><span data-stu-id="62be8-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="62be8-231">Frisläpp orderuppsättning 2 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="62be8-231">Release order set 2 in one load</span></span>

<span data-ttu-id="62be8-232">Tre leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="62be8-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="62be8-233">Den första leveransen innehåller de *brandfarliga* artiklarna.</span><span class="sxs-lookup"><span data-stu-id="62be8-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="62be8-234">Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.</span><span class="sxs-lookup"><span data-stu-id="62be8-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="62be8-235">Frisläpp orderuppsättning 3 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="62be8-235">Release order set 3 in one load</span></span>

<span data-ttu-id="62be8-236">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="62be8-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="62be8-237">Den första leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *1*.</span><span class="sxs-lookup"><span data-stu-id="62be8-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="62be8-238">Den andra leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *2*.</span><span class="sxs-lookup"><span data-stu-id="62be8-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="62be8-239">Frisläpp orderuppsättning 4 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="62be8-239">Release order set 4 in one load</span></span>

<span data-ttu-id="62be8-240">Fyra leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="62be8-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="62be8-241">Rader från två försäljningsorder för kundkonto *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="62be8-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="62be8-242">Rader från två försäljningsorder för kundkonto *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="62be8-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="62be8-243">Rader från försäljningsorder 4-5 och 4-6 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="62be8-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="62be8-244">Rader från försäljningsorder 4-7 och 4-8 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="62be8-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62be8-245">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="62be8-245">Additional resources</span></span>

- [<span data-ttu-id="62be8-246">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="62be8-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="62be8-247">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="62be8-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]