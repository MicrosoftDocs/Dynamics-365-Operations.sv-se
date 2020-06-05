---
title: Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 396a038dbf2f4b6835ecbb5fd8cb39a3a3608af7
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383866"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="d99b2-103">Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="d99b2-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d99b2-104">Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.</span><span class="sxs-lookup"><span data-stu-id="d99b2-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="d99b2-105">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="d99b2-105">Make demo data available</span></span>

<span data-ttu-id="d99b2-106">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d99b2-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d99b2-107">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="d99b2-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="d99b2-108">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="d99b2-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="d99b2-109">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="d99b2-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="d99b2-110">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="d99b2-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="d99b2-111">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="d99b2-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="d99b2-112">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="d99b2-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="d99b2-113">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="d99b2-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="d99b2-114">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="d99b2-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="d99b2-115">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="d99b2-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="d99b2-116">Skapa orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="d99b2-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="d99b2-117">Försäljningsorder 1-1</span><span class="sxs-lookup"><span data-stu-id="d99b2-117">Sales order 1-1</span></span>

1. <span data-ttu-id="d99b2-118">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-119">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d99b2-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d99b2-120">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="d99b2-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d99b2-121">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-122">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-123">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-124">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="d99b2-125">Försäljningsorder 1-2</span><span class="sxs-lookup"><span data-stu-id="d99b2-125">Sales order 1-2</span></span>

1. <span data-ttu-id="d99b2-126">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-127">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d99b2-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d99b2-128">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="d99b2-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d99b2-129">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-130">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-131">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-132">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="d99b2-133">Försäljningsorder 1-3</span><span class="sxs-lookup"><span data-stu-id="d99b2-133">Sales order 1-3</span></span>

1. <span data-ttu-id="d99b2-134">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-135">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d99b2-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d99b2-136">**Leveranssätt:** *10*</span><span class="sxs-lookup"><span data-stu-id="d99b2-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="d99b2-137">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-138">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-139">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-140">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="d99b2-141">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-142">**Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-143">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="d99b2-144">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="d99b2-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d99b2-145">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="d99b2-146">Skapa orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="d99b2-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="d99b2-147">Försäljningsorder 2-1 och 2-2</span><span class="sxs-lookup"><span data-stu-id="d99b2-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="d99b2-148">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-149">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="d99b2-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="d99b2-150">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-151">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="d99b2-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="d99b2-152">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-153">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="d99b2-154">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-155">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="d99b2-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="d99b2-156">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="d99b2-157">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="d99b2-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="d99b2-158">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="d99b2-159">Skapa orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="d99b2-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="d99b2-160">Försäljningsorder 3-1 och 3-2</span><span class="sxs-lookup"><span data-stu-id="d99b2-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="d99b2-161">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-162">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d99b2-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d99b2-163">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="d99b2-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="d99b2-164">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-165">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-166">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-167">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="d99b2-168">Försäljningsorder 3-3 och 3-4</span><span class="sxs-lookup"><span data-stu-id="d99b2-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="d99b2-169">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-170">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="d99b2-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="d99b2-171">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="d99b2-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="d99b2-172">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-173">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-174">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-175">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="d99b2-176">Skapa orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="d99b2-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="d99b2-177">Försäljningsorder 4-1 och 4-2</span><span class="sxs-lookup"><span data-stu-id="d99b2-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="d99b2-178">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-179">**Kundkonto:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="d99b2-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="d99b2-180">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-181">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-182">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-183">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="d99b2-184">Försäljningsorder 4-3 och 4-4</span><span class="sxs-lookup"><span data-stu-id="d99b2-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="d99b2-185">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-186">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="d99b2-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="d99b2-187">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-188">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-189">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-190">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="d99b2-191">Försäljningsorder 4-5 och 4-6</span><span class="sxs-lookup"><span data-stu-id="d99b2-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="d99b2-192">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-193">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="d99b2-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="d99b2-194">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="d99b2-194">**Site:** *6*</span></span>
    - <span data-ttu-id="d99b2-195">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="d99b2-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="d99b2-196">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="d99b2-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="d99b2-197">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-198">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-199">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-200">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="d99b2-201">Försäljningsorder 4-7 och 4-8</span><span class="sxs-lookup"><span data-stu-id="d99b2-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="d99b2-202">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d99b2-203">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="d99b2-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="d99b2-204">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="d99b2-204">**Site:** *6*</span></span>
    - <span data-ttu-id="d99b2-205">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="d99b2-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="d99b2-206">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="d99b2-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="d99b2-207">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d99b2-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d99b2-208">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="d99b2-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d99b2-209">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d99b2-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d99b2-210">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="d99b2-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="d99b2-211">Använd workbench för lastplanering för att skapa beläggningar och släppa dem till lagerstället</span><span class="sxs-lookup"><span data-stu-id="d99b2-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="d99b2-212">Följ dessa steg för att skapa en beläggning för varje orderuppsättning som du har skapat för scenariot och sedan släppa den till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="d99b2-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="d99b2-213">Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="d99b2-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="d99b2-214">På fliken **Försäljningsrader** letar du upp och markerar alla försäljningsorderrader från en av orderuppsättningar som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="d99b2-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="d99b2-215">I åtgärdsfönstret väljer du **tillgång och efterfrågan**, väljer **Lägg till \> Till ny beläggning** om du vill lägga till valda orderlinjer i en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="d99b2-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="d99b2-216">I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *Stnd Load Template*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="d99b2-217">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="d99b2-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="d99b2-218">I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du just skapat.</span><span class="sxs-lookup"><span data-stu-id="d99b2-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="d99b2-219">Välj **Släpp \> Släpp till lagerställe** om du vill frisläppa den valda beläggningen till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="d99b2-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="d99b2-220">Upprepa den här proceduren för samtliga de tre andra orderuppsättningar som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="d99b2-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="d99b2-221">Verifiera leveranserna</span><span class="sxs-lookup"><span data-stu-id="d99b2-221">Verify the shipments</span></span>

<span data-ttu-id="d99b2-222">Med följande procedur kan du verifiera de leveranser som har skapats eller uppdaterats som ett resultat av leveranskonsolideringen.</span><span class="sxs-lookup"><span data-stu-id="d99b2-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="d99b2-223">Granska varje orderuppsättning som du har skapat för det här scenariot, och granska sedan de underavsnitt som följer för att se till att du har fått de förväntade resultaten.</span><span class="sxs-lookup"><span data-stu-id="d99b2-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="d99b2-224">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="d99b2-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="d99b2-225">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="d99b2-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="d99b2-226">Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="d99b2-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="d99b2-227">Frisläpp orderuppsättning 1 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="d99b2-227">Release order set 1 in one load</span></span>

<span data-ttu-id="d99b2-228">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="d99b2-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="d99b2-229">Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.</span><span class="sxs-lookup"><span data-stu-id="d99b2-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="d99b2-230">Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.</span><span class="sxs-lookup"><span data-stu-id="d99b2-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="d99b2-231">Frisläpp orderuppsättning 2 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="d99b2-231">Release order set 2 in one load</span></span>

<span data-ttu-id="d99b2-232">Tre leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="d99b2-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="d99b2-233">Den första leveransen innehåller de *brandfarliga* artiklarna.</span><span class="sxs-lookup"><span data-stu-id="d99b2-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="d99b2-234">Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="d99b2-235">Frisläpp orderuppsättning 3 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="d99b2-235">Release order set 3 in one load</span></span>

<span data-ttu-id="d99b2-236">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="d99b2-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="d99b2-237">Den första leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *1*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="d99b2-238">Den andra leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *2*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="d99b2-239">Frisläpp orderuppsättning 4 i en (1) beläggning</span><span class="sxs-lookup"><span data-stu-id="d99b2-239">Release order set 4 in one load</span></span>

<span data-ttu-id="d99b2-240">Fyra leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="d99b2-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="d99b2-241">Rader från två försäljningsorder för kundkonto *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d99b2-242">Rader från två försäljningsorder för kundkonto *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d99b2-243">Rader från försäljningsorder 4-5 och 4-6 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="d99b2-244">Rader från försäljningsorder 4-7 och 4-8 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="d99b2-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d99b2-245">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d99b2-245">Additional resources</span></span>

- [<span data-ttu-id="d99b2-246">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="d99b2-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="d99b2-247">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="d99b2-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
