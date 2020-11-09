---
title: Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Släpp till lagerställe
description: Detta ämne innehåller ett scenario där en eller flera försäljningsrader måste släppas manuellt till lagerstället från sidan Släpp till lagerställe, och den systemdefinierade policyn för leveranskonsolidering måste åsidosättas före frisläppandet.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 96f994e9f3440721105545f96d7d8475fcab2b6b
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016803"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="05c5e-103">Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="05c5e-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05c5e-104">Detta ämne innehåller ett scenario där en eller flera försäljningsrader måste släppas manuellt till lagerstället från sidan **Släpp till lagerställe** , och den systemdefinierade policyn för leveranskonsolidering måste åsidosättas före frisläppandet.</span><span class="sxs-lookup"><span data-stu-id="05c5e-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="05c5e-105">Det kan krävas en åsidosättning av policyn för leveranskonsoliderings om en order som exempelvis normalt sett inte konsolideras med öppna leveranser nu måste konsolideras med öppna leveranser.</span><span class="sxs-lookup"><span data-stu-id="05c5e-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="05c5e-106">Under scenariot kommer du att skapa en uppsättning försäljningsorder och sedan åsidosätta standardpolicyn för leveranskonsolidering innan du släpper orderna i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="05c5e-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="05c5e-107">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="05c5e-107">Make demo data available</span></span>

<span data-ttu-id="05c5e-108">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="05c5e-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="05c5e-109">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="05c5e-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="05c5e-110">Ställ in policyer och produktfilter för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="05c5e-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="05c5e-111">Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där.</span><span class="sxs-lookup"><span data-stu-id="05c5e-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="05c5e-112">Var noga med att göra övningarna innan du fortsätter med det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="05c5e-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="05c5e-113">Skapa försäljningsorder för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="05c5e-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="05c5e-114">Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa sedan tre identiska försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="05c5e-114">Go to **Accounts receivable \> Orders \> All sales orders** , and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="05c5e-115">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="05c5e-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="05c5e-116">Lägg till en orderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="05c5e-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="05c5e-117">**Artikelnummer:** *A0001* (en artikel som inget **Kod 4** -filter tilldelas till)</span><span class="sxs-lookup"><span data-stu-id="05c5e-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="05c5e-118">**Kvantitet:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="05c5e-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="05c5e-119">Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.</span><span class="sxs-lookup"><span data-stu-id="05c5e-119">Select **Inventory \> Reservation** , and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="05c5e-120">Frisläpp försäljningsorder från sidan Släpp till lagerställe</span><span class="sxs-lookup"><span data-stu-id="05c5e-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="05c5e-121">Följ dessa steg om du vill åsidosätta policyn för leveranskonsolidering under frisläppandet till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="05c5e-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="05c5e-122">Gå till **Lagerstyrning \> Släpp till lagerställe \> Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="05c5e-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="05c5e-123">I det övre fönstret väljer du den förstaförsäljnings order som du har skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="05c5e-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="05c5e-124">Välj **Lägg till** om du vill lägga till raden om frisläppande till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="05c5e-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="05c5e-125">Observera att konsolideringspolicyn *Standard* för leveranser tillämpas i det nedre fönstret.</span><span class="sxs-lookup"><span data-stu-id="05c5e-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="05c5e-126">I det nedre fönstret väljer du **Välj ny konsolideringspolicy för leverans**.</span><span class="sxs-lookup"><span data-stu-id="05c5e-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="05c5e-127">Välj en policy som möjliggör konsolidering med andra öppna leveranser tillhörande samma policy.</span><span class="sxs-lookup"><span data-stu-id="05c5e-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="05c5e-128">Välj till exempel policyn *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="05c5e-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="05c5e-129">Välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="05c5e-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="05c5e-130">Välj den andra och tredje försäljningsorder som du skapat för detta scenario.</span><span class="sxs-lookup"><span data-stu-id="05c5e-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="05c5e-131">Välj **Lägg till** om du vill lägga till rader om frisläppande till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="05c5e-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="05c5e-132">Observera att policyn *Standard* tillämpas i det nedre fönstret.</span><span class="sxs-lookup"><span data-stu-id="05c5e-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="05c5e-133">Markera den andra raden och sedan, i fältet **Välj ny konsolideringspolicy för leverans** , policyn *CustomerORderNo*.</span><span class="sxs-lookup"><span data-stu-id="05c5e-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="05c5e-134">Välj **Släpp till lagerställe** för båda raderna.</span><span class="sxs-lookup"><span data-stu-id="05c5e-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="05c5e-135">Verifiera leveranserna</span><span class="sxs-lookup"><span data-stu-id="05c5e-135">Verify the shipments</span></span>

<span data-ttu-id="05c5e-136">Två leveranser bör ha skapats:</span><span class="sxs-lookup"><span data-stu-id="05c5e-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="05c5e-137">Den första leveransen innehåller två rader och har skapats med hjälp av konsolideringspolicyn *CustomerOrderNo* leverans.</span><span class="sxs-lookup"><span data-stu-id="05c5e-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="05c5e-138">Den andra leveransen innehåller en rad och har skapats med hjälp av konsolideringspolicyn *Standard* för leverans.</span><span class="sxs-lookup"><span data-stu-id="05c5e-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="05c5e-139">Följ de här stegen för att granska de leveranser som har skapats.</span><span class="sxs-lookup"><span data-stu-id="05c5e-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="05c5e-140">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="05c5e-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="05c5e-141">Sök och välj önskad leverans.</span><span class="sxs-lookup"><span data-stu-id="05c5e-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="05c5e-142">I fältet **Policy för leveranskonsolidering** granskar du den konsolideringspolicy som användes när leveransen skapades.</span><span class="sxs-lookup"><span data-stu-id="05c5e-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05c5e-143">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="05c5e-143">Additional resources</span></span>

- [<span data-ttu-id="05c5e-144">Policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="05c5e-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="05c5e-145">Konfigurera policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="05c5e-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
