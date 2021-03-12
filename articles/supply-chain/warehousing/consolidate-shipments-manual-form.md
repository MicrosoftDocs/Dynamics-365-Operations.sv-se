---
title: Konsolidera leveranser manuellt via sidan Konsolidera leveranser
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras senare genom att använda sidan Konsolidera leveranser.
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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0e580253de0d787b721c2f729ecc96db56b91af0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983027"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="c6fea-103">Konsolidera leveranser manuellt via sidan Konsolidera leveranser</span><span class="sxs-lookup"><span data-stu-id="c6fea-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6fea-104">Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras senare genom att använda sidan **Konsolidera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="c6fea-105">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="c6fea-105">Make demo data available</span></span>

<span data-ttu-id="c6fea-106">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c6fea-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c6fea-107">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="c6fea-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="c6fea-108">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="c6fea-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="c6fea-109">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="c6fea-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="c6fea-110">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="c6fea-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="c6fea-111">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="c6fea-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="c6fea-112">Börja med att skapa en samling med försäljningsorder som du kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="c6fea-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="c6fea-113">Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS).</span><span class="sxs-lookup"><span data-stu-id="c6fea-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="c6fea-114">Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="c6fea-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="c6fea-115">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="c6fea-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="c6fea-116">Skapa försäljningsorder 1 och 2</span><span class="sxs-lookup"><span data-stu-id="c6fea-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="c6fea-117">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6fea-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c6fea-118">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c6fea-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c6fea-119">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="c6fea-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="c6fea-120">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6fea-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c6fea-121">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="c6fea-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c6fea-122">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c6fea-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c6fea-123">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="c6fea-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="c6fea-124">Skapa försäljningsorder 3 och 4</span><span class="sxs-lookup"><span data-stu-id="c6fea-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="c6fea-125">Skapa två identiska försäljningsorder som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6fea-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c6fea-126">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c6fea-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c6fea-127">**Pool:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="c6fea-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="c6fea-128">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6fea-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c6fea-129">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="c6fea-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c6fea-130">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c6fea-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c6fea-131">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="c6fea-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="c6fea-132">Släpp order till lagerställe</span><span class="sxs-lookup"><span data-stu-id="c6fea-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="c6fea-133">Följ dessa steg för att släppa varje försäljningsorder som du har skapat för scenariot till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="c6fea-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="c6fea-134">Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c6fea-135">Hitta och markera den försäljningsorder som du vill släppa.</span><span class="sxs-lookup"><span data-stu-id="c6fea-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="c6fea-136">På fliken **Lagerställe** i åtgärdsfönstret väljer du **Åtgärder \> Släpp till lagerställe** för att släppa vald försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c6fea-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="c6fea-137">Upprepa den här proceduren för alla andra försäljningsorder som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="c6fea-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="c6fea-138">Konsolidera leveranser</span><span class="sxs-lookup"><span data-stu-id="c6fea-138">Consolidate shipments</span></span>

1. <span data-ttu-id="c6fea-139">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="c6fea-140">Sök efter och välj en leverans som skapades när försäljningsorder 1 släpptes till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="c6fea-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="c6fea-141">(Dess fält **Konsolideringspolicy för leverans** ska vara inställt på *Orderpool*.)</span><span class="sxs-lookup"><span data-stu-id="c6fea-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="c6fea-142">På fliken **Leveranser** i åtgärdsfältet väljer du **Leveranser \> Konsolidera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="c6fea-143">Verifiera de leveranser som föreslås för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="c6fea-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="c6fea-144">Endast en leverans som har samma policy bör föreslås för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="c6fea-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="c6fea-145">Stäng sidan **Leveranskonsolidering**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="c6fea-146">Sök efter och välj en leverans som skapades när försäljningsorder 3 släpptes till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="c6fea-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="c6fea-147">(Dess fält **Policy för leveranskonslidering** bör anges som *Standard*.)</span><span class="sxs-lookup"><span data-stu-id="c6fea-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="c6fea-148">På fliken **Leveranser** i åtgärdsfältet väljer du **Leveranser \> Konsolidera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="c6fea-149">Bekräfta att inga leveranser föreslås för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="c6fea-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="c6fea-150">Välj **Visa filter**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="c6fea-151">I fönstret **Filter** tar du bort filtret **Ordernummer** och väljer sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="c6fea-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="c6fea-152">Verifiera de leveranser som föreslås för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="c6fea-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="c6fea-153">Endast en leverans som har samma policy bör föreslås för konsolidering.</span><span class="sxs-lookup"><span data-stu-id="c6fea-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6fea-154">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c6fea-154">Additional resources</span></span>

- [<span data-ttu-id="c6fea-155">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="c6fea-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="c6fea-156">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="c6fea-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)