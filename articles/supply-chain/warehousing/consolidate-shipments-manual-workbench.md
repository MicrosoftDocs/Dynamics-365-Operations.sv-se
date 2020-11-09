---
title: Konsolidera leveranser genom att använda workbench för leveranskonsolidering
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras till leveranser senare genom att använda workbench för leveranskonsolidering.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1eec1a8e3a9a2a0f95302e1d6ea68eb90b9a3b93
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016826"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="6d0ff-103">Konsolidera leveranser genom att använda workbench för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d0ff-104">Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras till leveranser senare genom att använda workbench för leveranskonsolidering.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="6d0ff-105">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="6d0ff-105">Make demo data available</span></span>

<span data-ttu-id="6d0ff-106">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="6d0ff-107">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="6d0ff-108">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="6d0ff-109">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="6d0ff-110">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="6d0ff-111">Aktivera funktionen för manuell leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="6d0ff-112">Innan du kan använda funktionen *Manuell leveranskonsolidering* måste du aktivera den i systemet.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="6d0ff-113">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="6d0ff-114">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6d0ff-115">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6d0ff-116">**Funktionsnamn:** *Manuell leveranskonsolidering*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="6d0ff-117">Som omnämnts i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) måste du också aktivera funktionen *Konsolidera leverans* innan du kan skapa policyer.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="6d0ff-118">Du bör dock redan ha slutfört detta steg.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="6d0ff-119">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="6d0ff-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="6d0ff-120">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="6d0ff-121">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="6d0ff-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="6d0ff-122">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="6d0ff-123">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-123">Go to **Accounts receivable \> Orders \> All sales orders** , and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="6d0ff-124">Skapa orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="6d0ff-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="6d0ff-125">Försäljningsorder 1-1 och 1-2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="6d0ff-126">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-127">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6d0ff-128">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="6d0ff-129">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-130">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-131">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-132">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-132">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="6d0ff-133">Försäljningsorder 1-3</span><span class="sxs-lookup"><span data-stu-id="6d0ff-133">Sales order 1-3</span></span>

1. <span data-ttu-id="6d0ff-134">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-135">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6d0ff-136">**Leveranssätt:** *10*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="6d0ff-137">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-138">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-139">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-140">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-140">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="6d0ff-141">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-142">**Artikelnummer:** *A0002* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-143">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="6d0ff-144">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="6d0ff-145">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-145">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="6d0ff-146">Skapa orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="6d0ff-147">Försäljningsorder 2-1 och 2-2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="6d0ff-148">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-149">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="6d0ff-150">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="6d0ff-151">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-152">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt* )</span><span class="sxs-lookup"><span data-stu-id="6d0ff-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable* )</span></span>
    - <span data-ttu-id="6d0ff-153">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-154">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-154">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="6d0ff-155">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-156">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt* )</span><span class="sxs-lookup"><span data-stu-id="6d0ff-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive* )</span></span>
    - <span data-ttu-id="6d0ff-157">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="6d0ff-158">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="6d0ff-159">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-159">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="6d0ff-160">Skapa orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="6d0ff-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="6d0ff-161">Försäljningsorder 3-1 och 3-2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="6d0ff-162">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-163">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6d0ff-164">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="6d0ff-165">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-166">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-167">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-168">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-168">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="6d0ff-169">Försäljningsorder 3-3 och 3-4</span><span class="sxs-lookup"><span data-stu-id="6d0ff-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="6d0ff-170">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-171">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6d0ff-172">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="6d0ff-173">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-174">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-175">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-176">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-176">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="6d0ff-177">Skapa orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="6d0ff-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="6d0ff-178">Försäljningsorder 4-1 och 4-2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="6d0ff-179">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-180">**Kundkonto:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="6d0ff-181">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-182">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-183">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-184">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-184">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="6d0ff-185">Försäljningsorder 4-3 och 4-4</span><span class="sxs-lookup"><span data-stu-id="6d0ff-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="6d0ff-186">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-187">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="6d0ff-188">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-189">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-190">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-191">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-191">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="6d0ff-192">Försäljningsorder 4-5 och 4-6</span><span class="sxs-lookup"><span data-stu-id="6d0ff-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="6d0ff-193">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-194">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="6d0ff-195">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-195">**Site:** *6*</span></span>
    - <span data-ttu-id="6d0ff-196">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="6d0ff-197">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="6d0ff-198">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-199">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-200">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-201">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-201">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="6d0ff-202">Försäljningsorder 4-7 och 4-8</span><span class="sxs-lookup"><span data-stu-id="6d0ff-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="6d0ff-203">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="6d0ff-204">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="6d0ff-205">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-205">**Site:** *6*</span></span>
    - <span data-ttu-id="6d0ff-206">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="6d0ff-207">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="6d0ff-208">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="6d0ff-209">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="6d0ff-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="6d0ff-210">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="6d0ff-211">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-211">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="6d0ff-212">Släpp order till lagerställe</span><span class="sxs-lookup"><span data-stu-id="6d0ff-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="6d0ff-213">Följ dessa steg för att släppa varje försäljningsorder som du har skapat för scenariot till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="6d0ff-214">Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6d0ff-215">Hitta och markera den försäljningsorder som du vill släppa.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="6d0ff-216">På fliken **Lagerställe** i åtgärdsfönstret väljer du **Åtgärder \> Släpp till lagerställe** för att släppa vald försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="6d0ff-217">Upprepa den här proceduren för alla andra försäljningsorder som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="6d0ff-218">Konsolidera leveranserna genom att använda workbench för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="6d0ff-219">Gå till **Lagerstyrning \> Släpp till lagerställe \> Workbench för leveranskonsolidering**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="6d0ff-220">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6d0ff-221">På fliken **Intervall** i dialogrutan för frågeredigerare väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="6d0ff-222">**Register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="6d0ff-223">**Fält:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="6d0ff-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="6d0ff-224">**Kriterier:** Ange en kommaavgränsad lista med försäljningsordernummer för varje orderuppsättning som du har skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="6d0ff-225">Välj **OK** om du vill spara din fråga och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="6d0ff-226">I åtgärdsfönstret väljer du **Konsolidera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="6d0ff-227">Välj alla leveranser och välj sedan **Konsolidera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="6d0ff-228">Verifiera leveranserna</span><span class="sxs-lookup"><span data-stu-id="6d0ff-228">Verify the shipments</span></span>

<span data-ttu-id="6d0ff-229">Med följande procedur kan du verifiera de leveranser som har skapats eller uppdaterats som ett resultat av leveranskonsolideringen.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="6d0ff-230">Granska varje orderuppsättning som du har skapat för det här scenariot, och granska sedan de underavsnitt som följer för att se till att du har fått de förväntade resultaten.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="6d0ff-231">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="6d0ff-232">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="6d0ff-233">Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="6d0ff-234">Relaterade leveranser för orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="6d0ff-234">Related shipments for order set 1</span></span>

<span data-ttu-id="6d0ff-235">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="6d0ff-236">Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="6d0ff-237">Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="6d0ff-238">Relaterade leveranser för orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="6d0ff-238">Related shipments for order set 2</span></span>

<span data-ttu-id="6d0ff-239">Tre leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="6d0ff-240">Den första leveransen innehåller de *brandfarliga* artiklarna.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="6d0ff-241">Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="6d0ff-242">Relaterade leveranser för orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="6d0ff-242">Related shipments for order set 3</span></span>

<span data-ttu-id="6d0ff-243">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="6d0ff-244">Den första leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *1*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="6d0ff-245">Den andra leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *2*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="6d0ff-246">Relaterade leveranser för orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="6d0ff-246">Related shipments for order set 4</span></span>

<span data-ttu-id="6d0ff-247">Fyra leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="6d0ff-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="6d0ff-248">Rader från två försäljningsorder för kund *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="6d0ff-249">Rader från två försäljningsorder för kund *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="6d0ff-250">Rader från försäljningsorder 4-5 och 4-6 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="6d0ff-251">Rader från försäljningsorder 4-7 och 4-8 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="6d0ff-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d0ff-252">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6d0ff-252">Additional resources</span></span>

- [<span data-ttu-id="6d0ff-253">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="6d0ff-254">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="6d0ff-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
