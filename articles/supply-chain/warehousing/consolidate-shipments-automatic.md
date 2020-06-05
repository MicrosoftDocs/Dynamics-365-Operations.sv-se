---
title: Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatiskt släpp av försäljningsorder
description: Detta ämne innehåller ett scenario där flera order frigörs till lagerstället i samma automatiska, periodiska procedur för släpp-till-lagerställe.
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
ms.openlocfilehash: 373b6bf6219ef76bacef3c67a816aec4c084c405
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383863"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="329af-103">Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatiskt släpp av försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="329af-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="329af-104">Detta ämne innehåller ett scenario där flera order frigörs till lagerstället i samma automatiska, periodiska procedur för släpp-till-lagerställe.</span><span class="sxs-lookup"><span data-stu-id="329af-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="329af-105">Order konsolideras automatiskt till leveranser, baserat på regler som har definierats som policyer för leveranskonsolidering.</span><span class="sxs-lookup"><span data-stu-id="329af-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="329af-106">Under scenariot skapar du uppsättningar med försäljningsorder och släpper varje uppsättning till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="329af-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="329af-107">Du kommer sedan att granska de leveranser som skapas eller uppdateras under leveranskonsolideringen, baserat på de konfigurerade policyerna.</span><span class="sxs-lookup"><span data-stu-id="329af-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="329af-108">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="329af-108">Make demo data available</span></span>

<span data-ttu-id="329af-109">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="329af-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="329af-110">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="329af-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="329af-111">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="329af-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="329af-112">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="329af-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="329af-113">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="329af-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="329af-114">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="329af-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="329af-115">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="329af-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="329af-116">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="329af-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="329af-117">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="329af-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="329af-118">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="329af-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="329af-119">Skapa orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="329af-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="329af-120">Försäljningsorder 1-1</span><span class="sxs-lookup"><span data-stu-id="329af-120">Sales order 1-1</span></span>

1. <span data-ttu-id="329af-121">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-122">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-123">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="329af-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="329af-124">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-125">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-126">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="329af-127">Försäljningsorder 1-2</span><span class="sxs-lookup"><span data-stu-id="329af-127">Sales order 1-2</span></span>

1. <span data-ttu-id="329af-128">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-129">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-130">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="329af-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="329af-131">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-132">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-133">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="329af-134">Försäljningsorder 1-3</span><span class="sxs-lookup"><span data-stu-id="329af-134">Sales order 1-3</span></span>

1. <span data-ttu-id="329af-135">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-136">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-137">**Leveranssätt:** *10*</span><span class="sxs-lookup"><span data-stu-id="329af-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="329af-138">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-139">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-140">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="329af-141">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-142">**Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-143">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="329af-144">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="329af-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="329af-145">Skapa orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="329af-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="329af-146">Försäljningsorder 2-1 och 2-2</span><span class="sxs-lookup"><span data-stu-id="329af-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="329af-147">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-148">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="329af-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="329af-149">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-150">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="329af-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="329af-151">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="329af-152">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-153">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="329af-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="329af-154">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="329af-155">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="329af-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="329af-156">Skapa orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="329af-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="329af-157">Försäljningsorder 3-1</span><span class="sxs-lookup"><span data-stu-id="329af-157">Sales order 3-1</span></span>

1. <span data-ttu-id="329af-158">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-159">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="329af-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="329af-160">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-161">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="329af-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="329af-162">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="329af-163">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-164">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="329af-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="329af-165">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="329af-166">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="329af-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="329af-167">Ordern är identisk med de två order som du skapade för orderuppsättning 2.</span><span class="sxs-lookup"><span data-stu-id="329af-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="329af-168">Den är dock listad som en orderuppsättning eftersom den frigörs separat senare i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="329af-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="329af-169">Skapa orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="329af-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="329af-170">Försäljningsorder 4-1</span><span class="sxs-lookup"><span data-stu-id="329af-170">Sales order 4-1</span></span>

1. <span data-ttu-id="329af-171">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-172">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-173">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="329af-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="329af-174">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-175">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-176">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="329af-177">Skapa orderuppsättning 5</span><span class="sxs-lookup"><span data-stu-id="329af-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="329af-178">Försäljningsorder 5-1 och 5-2</span><span class="sxs-lookup"><span data-stu-id="329af-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="329af-179">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-180">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-181">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="329af-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="329af-182">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-183">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-184">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="329af-185">Försäljningsorder 5-3</span><span class="sxs-lookup"><span data-stu-id="329af-185">Sales order 5-3</span></span>

1. <span data-ttu-id="329af-186">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="329af-187">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="329af-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="329af-188">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="329af-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="329af-189">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-190">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-191">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="329af-192">Skapa orderuppsättning 6</span><span class="sxs-lookup"><span data-stu-id="329af-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="329af-193">Försäljningsorder 6-1 och 6-2</span><span class="sxs-lookup"><span data-stu-id="329af-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="329af-194">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-195">**Kundkonto:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="329af-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="329af-196">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="329af-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="329af-197">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-198">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-199">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="329af-200">Försäljningsorder 6-3 och 6-4</span><span class="sxs-lookup"><span data-stu-id="329af-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="329af-201">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-202">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="329af-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="329af-203">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="329af-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="329af-204">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-205">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-206">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="329af-207">Försäljningsorder 6-5 och 6-6</span><span class="sxs-lookup"><span data-stu-id="329af-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="329af-208">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-209">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="329af-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="329af-210">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="329af-210">**Site:** *6*</span></span>
    - <span data-ttu-id="329af-211">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="329af-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="329af-212">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="329af-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="329af-213">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-214">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-215">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="329af-216">Försäljningsorder 6-7 och 6-8</span><span class="sxs-lookup"><span data-stu-id="329af-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="329af-217">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="329af-218">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="329af-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="329af-219">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="329af-219">**Site:** *6*</span></span>
    - <span data-ttu-id="329af-220">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="329af-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="329af-221">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="329af-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="329af-222">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="329af-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="329af-223">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="329af-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="329af-224">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="329af-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="329af-225">Automatiskt släpp av försäljningsorder till lagerstället</span><span class="sxs-lookup"><span data-stu-id="329af-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="329af-226">För varje uppsättning försäljningsorder som du skapade tidigare kommer du att slutföra en procedur för automatiskt släpp till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="329af-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="329af-227">I varje enskilt fall kommer du att arbeta genom den [grundläggande process för släpp-till-lagerställe](#release-procedure) som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="329af-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="329af-228">Grundläggande procedur för släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="329af-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="329af-229">För varje enskild uppsättning försäljningsorder som du skapade tidigare kommer du att genomföra de tre procedurer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="329af-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="329af-230">Uppdatera den påfyllnadsmall som ska användas under släpp</span><span class="sxs-lookup"><span data-stu-id="329af-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="329af-231">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="329af-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="329af-232">Ställ in fältet **Malltyp för påfyllnad** som *Levereras*.</span><span class="sxs-lookup"><span data-stu-id="329af-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="329af-233">Hitta och välj den påfyllnadsmall som är kopplad till det lagerställe som du har använt i de orderuppsättningar du skapat för scenariot.</span><span class="sxs-lookup"><span data-stu-id="329af-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="329af-234">Om du till exempel har använt lagerställe *24* ska du välja påfyllnadsmallen **Standardleverans för 24**.</span><span class="sxs-lookup"><span data-stu-id="329af-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="329af-235">Om du använt lagerställe *61* ska du välja påfyllnadsmallen **Leverans för 61**.</span><span class="sxs-lookup"><span data-stu-id="329af-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="329af-236">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="329af-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="329af-237">Ange alternativet **Bearbeta påfyllnad vid släpp till lagerställe** som *Nej*.</span><span class="sxs-lookup"><span data-stu-id="329af-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="329af-238">Släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="329af-238">Release to the warehouse</span></span>

1. <span data-ttu-id="329af-239">Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="329af-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="329af-240">Ställ in fältet **Kvantitet att släppa** som *Alla*.</span><span class="sxs-lookup"><span data-stu-id="329af-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="329af-241">På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att öppna dialogrutan för fråga.</span><span class="sxs-lookup"><span data-stu-id="329af-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="329af-242">På fliken **Intervall** väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="329af-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="329af-243">**Register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="329af-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="329af-244">**Härlett register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="329af-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="329af-245">**Fält:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="329af-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="329af-246">**Kriterier:** Ange en kommaavgränsad lista med försäljningsordernummer från önskad orderuppsättning.</span><span class="sxs-lookup"><span data-stu-id="329af-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="329af-247">Välj **OK** om du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="329af-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="329af-248">Välj **OK** om du vill starta proceduren *Automatiskt släpp till lagerställe*.</span><span class="sxs-lookup"><span data-stu-id="329af-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="329af-249">Granska leveransen som har skapats eller uppdaterats</span><span class="sxs-lookup"><span data-stu-id="329af-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="329af-250">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="329af-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="329af-251">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="329af-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="329af-252">Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="329af-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="329af-253">Släpp försäljningsorder från orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="329af-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="329af-254">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 1.</span><span class="sxs-lookup"><span data-stu-id="329af-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="329af-255">När du är klar bör du se att två leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="329af-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="329af-256">Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.</span><span class="sxs-lookup"><span data-stu-id="329af-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="329af-257">Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.</span><span class="sxs-lookup"><span data-stu-id="329af-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="329af-258">Frisläpp försäljningsorder från orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="329af-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="329af-259">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 2.</span><span class="sxs-lookup"><span data-stu-id="329af-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="329af-260">När du är klar bör du se att tre leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="329af-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="329af-261">Den första leveransen innehåller de *brandfarliga* artiklarna.</span><span class="sxs-lookup"><span data-stu-id="329af-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="329af-262">Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.</span><span class="sxs-lookup"><span data-stu-id="329af-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="329af-263">Frisläpp försäljningsorder från orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="329af-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="329af-264">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 3.</span><span class="sxs-lookup"><span data-stu-id="329af-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="329af-265">När du är klar ska du se att följande åtgärder har utförts:</span><span class="sxs-lookup"><span data-stu-id="329af-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="329af-266">En befintlig leverans (den som skapades när orderuppsättning 2 släpptes till lagerstället) uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="329af-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="329af-267">En rad med artikeln *brandfarlig* har lagts till.</span><span class="sxs-lookup"><span data-stu-id="329af-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="329af-268">En ny leverans som innehåller artikeln *explosiv* skapades.</span><span class="sxs-lookup"><span data-stu-id="329af-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="329af-269">Frisläpp försäljningsorder från orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="329af-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="329af-270">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 4.</span><span class="sxs-lookup"><span data-stu-id="329af-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="329af-271">När du är klar bör du se att en befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="329af-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="329af-272">En ny rad lades till i den.</span><span class="sxs-lookup"><span data-stu-id="329af-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="329af-273">Frisläpp försäljningsorder från orderuppsättning 5</span><span class="sxs-lookup"><span data-stu-id="329af-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="329af-274">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 5.</span><span class="sxs-lookup"><span data-stu-id="329af-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="329af-275">När du är klar ska du se att följande åtgärder har utförts:</span><span class="sxs-lookup"><span data-stu-id="329af-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="329af-276">En befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="329af-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="329af-277">En rad från försäljningsorder 5-3 (där fältet **Kundrekvisition** är inställt på *1*) har lagts till i den.</span><span class="sxs-lookup"><span data-stu-id="329af-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="329af-278">En ny leverans skapades, där rader från försäljningsorder 5-1 och 5-2 grupperas till en och samma leverans.</span><span class="sxs-lookup"><span data-stu-id="329af-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="329af-279">Frisläpp försäljningsorder från orderuppsättning 6</span><span class="sxs-lookup"><span data-stu-id="329af-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="329af-280">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 6.</span><span class="sxs-lookup"><span data-stu-id="329af-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="329af-281">När du är klar bör du se att fyra leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="329af-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="329af-282">Rader från två försäljningsorder för kund *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="329af-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="329af-283">Rader från två försäljningsorder för kund *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="329af-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="329af-284">Rader från försäljningsorder 6-5 och 6-6 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="329af-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="329af-285">Rader från försäljningsorder 6-7 och 6-8 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="329af-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="329af-286">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="329af-286">Additional resources</span></span>

- [<span data-ttu-id="329af-287">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="329af-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="329af-288">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="329af-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
