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
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 7102eade4a26f4b4dc08adb395aa7b50a630b9d9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243953"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="4cf2c-103">Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatiskt släpp av försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="4cf2c-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4cf2c-104">Detta ämne innehåller ett scenario där flera order frigörs till lagerstället i samma automatiska, periodiska procedur för släpp-till-lagerställe.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="4cf2c-105">Order konsolideras automatiskt till leveranser, baserat på regler som har definierats som policyer för leveranskonsolidering.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="4cf2c-106">Under scenariot skapar du uppsättningar med försäljningsorder och släpper varje uppsättning till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="4cf2c-107">Du kommer sedan att granska de leveranser som skapas eller uppdateras under leveranskonsolideringen, baserat på de konfigurerade policyerna.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="4cf2c-108">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="4cf2c-108">Make demo data available</span></span>

<span data-ttu-id="4cf2c-109">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4cf2c-110">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="4cf2c-111">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="4cf2c-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="4cf2c-112">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="4cf2c-113">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="4cf2c-114">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="4cf2c-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="4cf2c-115">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="4cf2c-116">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="4cf2c-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="4cf2c-117">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="4cf2c-118">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="4cf2c-119">Skapa orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="4cf2c-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="4cf2c-120">Försäljningsorder 1-1</span><span class="sxs-lookup"><span data-stu-id="4cf2c-120">Sales order 1-1</span></span>

1. <span data-ttu-id="4cf2c-121">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-122">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-123">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4cf2c-124">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-125">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-126">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="4cf2c-127">Försäljningsorder 1-2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-127">Sales order 1-2</span></span>

1. <span data-ttu-id="4cf2c-128">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-129">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-130">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4cf2c-131">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-132">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-133">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="4cf2c-134">Försäljningsorder 1-3</span><span class="sxs-lookup"><span data-stu-id="4cf2c-134">Sales order 1-3</span></span>

1. <span data-ttu-id="4cf2c-135">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-136">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-137">**Leveranssätt:** *10*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="4cf2c-138">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-139">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-140">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf2c-141">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-142">**Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-143">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf2c-144">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="4cf2c-145">Skapa orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="4cf2c-146">Försäljningsorder 2-1 och 2-2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="4cf2c-147">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-148">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4cf2c-149">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-150">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4cf2c-151">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf2c-152">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-153">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4cf2c-154">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf2c-155">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="4cf2c-156">Skapa orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="4cf2c-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="4cf2c-157">Försäljningsorder 3-1</span><span class="sxs-lookup"><span data-stu-id="4cf2c-157">Sales order 3-1</span></span>

1. <span data-ttu-id="4cf2c-158">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-159">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4cf2c-160">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-161">**Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4cf2c-162">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf2c-163">Lägg till en andra orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-164">**Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4cf2c-165">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf2c-166">**Leveranssätt:** *Flygfrakt*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="4cf2c-167">Ordern är identisk med de två order som du skapade för orderuppsättning 2.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="4cf2c-168">Den är dock listad som en orderuppsättning eftersom den frigörs separat senare i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="4cf2c-169">Skapa orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="4cf2c-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="4cf2c-170">Försäljningsorder 4-1</span><span class="sxs-lookup"><span data-stu-id="4cf2c-170">Sales order 4-1</span></span>

1. <span data-ttu-id="4cf2c-171">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-172">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-173">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf2c-174">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-175">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-176">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="4cf2c-177">Skapa orderuppsättning 5</span><span class="sxs-lookup"><span data-stu-id="4cf2c-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="4cf2c-178">Försäljningsorder 5-1 och 5-2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="4cf2c-179">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-180">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-181">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4cf2c-182">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-183">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-184">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="4cf2c-185">Försäljningsorder 5-3</span><span class="sxs-lookup"><span data-stu-id="4cf2c-185">Sales order 5-3</span></span>

1. <span data-ttu-id="4cf2c-186">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-187">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf2c-188">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf2c-189">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-190">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-191">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="4cf2c-192">Skapa orderuppsättning 6</span><span class="sxs-lookup"><span data-stu-id="4cf2c-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="4cf2c-193">Försäljningsorder 6-1 och 6-2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="4cf2c-194">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-195">**Kundkonto:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="4cf2c-196">**Kundrekvisition:** *2*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4cf2c-197">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-198">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-199">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="4cf2c-200">Försäljningsorder 6-3 och 6-4</span><span class="sxs-lookup"><span data-stu-id="4cf2c-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="4cf2c-201">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-202">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="4cf2c-203">**Kundrekvisition:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf2c-204">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-205">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-206">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="4cf2c-207">Försäljningsorder 6-5 och 6-6</span><span class="sxs-lookup"><span data-stu-id="4cf2c-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="4cf2c-208">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-209">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4cf2c-210">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-210">**Site:** *6*</span></span>
    - <span data-ttu-id="4cf2c-211">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4cf2c-212">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="4cf2c-213">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-214">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-215">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="4cf2c-216">Försäljningsorder 6-7 och 6-8</span><span class="sxs-lookup"><span data-stu-id="4cf2c-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="4cf2c-217">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf2c-218">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4cf2c-219">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-219">**Site:** *6*</span></span>
    - <span data-ttu-id="4cf2c-220">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4cf2c-221">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="4cf2c-222">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf2c-223">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="4cf2c-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf2c-224">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="4cf2c-225">Automatiskt släpp av försäljningsorder till lagerstället</span><span class="sxs-lookup"><span data-stu-id="4cf2c-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="4cf2c-226">För varje uppsättning försäljningsorder som du skapade tidigare kommer du att slutföra en procedur för automatiskt släpp till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="4cf2c-227">I varje enskilt fall kommer du att arbeta genom den [grundläggande process för släpp-till-lagerställe](#release-procedure) som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="4cf2c-228">Grundläggande procedur för släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="4cf2c-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="4cf2c-229">För varje enskild uppsättning försäljningsorder som du skapade tidigare kommer du att genomföra de tre procedurer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="4cf2c-230">Uppdatera den påfyllnadsmall som ska användas under släpp</span><span class="sxs-lookup"><span data-stu-id="4cf2c-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="4cf2c-231">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="4cf2c-232">Ställ in fältet **Malltyp för påfyllnad** som *Levereras*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="4cf2c-233">Hitta och välj den påfyllnadsmall som är kopplad till det lagerställe som du har använt i de orderuppsättningar du skapat för scenariot.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="4cf2c-234">Om du till exempel har använt lagerställe *24* ska du välja påfyllnadsmallen **Standardleverans för 24**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="4cf2c-235">Om du använt lagerställe *61* ska du välja påfyllnadsmallen **Leverans för 61**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="4cf2c-236">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="4cf2c-237">Ange alternativet **Bearbeta påfyllnad vid släpp till lagerställe** som *Nej*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="4cf2c-238">Släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="4cf2c-238">Release to the warehouse</span></span>

1. <span data-ttu-id="4cf2c-239">Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="4cf2c-240">Ställ in fältet **Kvantitet att släppa** som *Alla*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="4cf2c-241">På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att öppna dialogrutan för fråga.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="4cf2c-242">På fliken **Intervall** väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="4cf2c-243">**Register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="4cf2c-244">**Härlett register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="4cf2c-245">**Fält:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="4cf2c-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="4cf2c-246">**Kriterier:** Ange en kommaavgränsad lista med försäljningsordernummer från önskad orderuppsättning.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="4cf2c-247">Välj **OK** om du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="4cf2c-248">Välj **OK** om du vill starta proceduren *Automatiskt släpp till lagerställe*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="4cf2c-249">Granska leveransen som har skapats eller uppdaterats</span><span class="sxs-lookup"><span data-stu-id="4cf2c-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="4cf2c-250">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="4cf2c-251">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="4cf2c-252">Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="4cf2c-253">Släpp försäljningsorder från orderuppsättning 1</span><span class="sxs-lookup"><span data-stu-id="4cf2c-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="4cf2c-254">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 1.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="4cf2c-255">När du är klar bör du se att två leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="4cf2c-256">Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf2c-257">Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="4cf2c-258">Frisläpp försäljningsorder från orderuppsättning 2</span><span class="sxs-lookup"><span data-stu-id="4cf2c-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="4cf2c-259">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 2.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="4cf2c-260">När du är klar bör du se att tre leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="4cf2c-261">Den första leveransen innehåller de *brandfarliga* artiklarna.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="4cf2c-262">Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="4cf2c-263">Frisläpp försäljningsorder från orderuppsättning 3</span><span class="sxs-lookup"><span data-stu-id="4cf2c-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="4cf2c-264">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 3.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="4cf2c-265">När du är klar ska du se att följande åtgärder har utförts:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4cf2c-266">En befintlig leverans (den som skapades när orderuppsättning 2 släpptes till lagerstället) uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="4cf2c-267">En rad med artikeln *brandfarlig* har lagts till.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="4cf2c-268">En ny leverans som innehåller artikeln *explosiv* skapades.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="4cf2c-269">Frisläpp försäljningsorder från orderuppsättning 4</span><span class="sxs-lookup"><span data-stu-id="4cf2c-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="4cf2c-270">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 4.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="4cf2c-271">När du är klar bör du se att en befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4cf2c-272">En ny rad lades till i den.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="4cf2c-273">Frisläpp försäljningsorder från orderuppsättning 5</span><span class="sxs-lookup"><span data-stu-id="4cf2c-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="4cf2c-274">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 5.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="4cf2c-275">När du är klar ska du se att följande åtgärder har utförts:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4cf2c-276">En befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4cf2c-277">En rad från försäljningsorder 5-3 (där fältet **Kundrekvisition** är inställt på *1*) har lagts till i den.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="4cf2c-278">En ny leverans skapades, där rader från försäljningsorder 5-1 och 5-2 grupperas till en och samma leverans.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="4cf2c-279">Frisläpp försäljningsorder från orderuppsättning 6</span><span class="sxs-lookup"><span data-stu-id="4cf2c-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="4cf2c-280">Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 6.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="4cf2c-281">När du är klar bör du se att fyra leveranser har skapats:</span><span class="sxs-lookup"><span data-stu-id="4cf2c-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="4cf2c-282">Rader från två försäljningsorder för kund *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf2c-283">Rader från två försäljningsorder för kund *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf2c-284">Rader från försäljningsorder 6-5 och 6-6 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf2c-285">Rader från försäljningsorder 6-7 och 6-8 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="4cf2c-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4cf2c-286">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4cf2c-286">Additional resources</span></span>

- [<span data-ttu-id="4cf2c-287">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="4cf2c-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="4cf2c-288">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="4cf2c-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]