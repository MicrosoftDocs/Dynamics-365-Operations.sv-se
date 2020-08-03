---
title: Ändra arbetspool för arbete
description: I det här avsnittet beskrivs hur du kan använda knappen Ändra arbetsgrupp för arbetsuppgifter när du vill ändra arbetsgrupp för befintligt arbete.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 33238b114f0939711163b19ae7af98be7c8d0744
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597562"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="b1551-103">Ändra arbetspool för arbete</span><span class="sxs-lookup"><span data-stu-id="b1551-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1551-104">Du kan använda arbetspooler för att strukturera arbete i grupper.</span><span class="sxs-lookup"><span data-stu-id="b1551-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="b1551-105">Du kan till exempel skapa en arbetspool för att klassificera arbete som uppstår på ett visst lagerställe.</span><span class="sxs-lookup"><span data-stu-id="b1551-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="b1551-106">Med funktionen *Ändra arbetspool för arbete* lägger till en knapp **Ändra arbetspool** i åtgärdsfönstret för arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b1551-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="b1551-107">Därför kan lagerchefer enkelt ändra arbetsgruppen för befintligt arbete.</span><span class="sxs-lookup"><span data-stu-id="b1551-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="b1551-108">Med hjälp av den här funktionen reagerar våra chefer snabbt på ändringar på verkstadsgolvet och förbättrar deras förmåga att anpassa sig till att ändra situationer och behovet att överföra arbete till en annan arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b1551-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="b1551-109">Aktivera funktionen ändra arbetspool för arbete</span><span class="sxs-lookup"><span data-stu-id="b1551-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="b1551-110">Innan du börjar ställa in eller använda den här funktionen måste du se till att den är tillgänglig i ditt-system.</span><span class="sxs-lookup"><span data-stu-id="b1551-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="b1551-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b1551-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b1551-112">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b1551-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b1551-113">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="b1551-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b1551-114">**Funktionens namn:** *Ändra arbetspool för arbete*</span><span class="sxs-lookup"><span data-stu-id="b1551-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="b1551-115">Ange funktionen ändra arbetspool för arbete</span><span class="sxs-lookup"><span data-stu-id="b1551-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="b1551-116">Om du vill använda den här funktionen måste du ha ställt in vissa arbetspooler.</span><span class="sxs-lookup"><span data-stu-id="b1551-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="b1551-117">Du kan också ställa in arbetsmallarna så att de tilldelar en pool automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b1551-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="b1551-118">Om du vill arbeta i ett exempelscenario som finns senare i det här avsnittet konfigurerar du systemet enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b1551-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="b1551-119">Ställa in arbetspooler</span><span class="sxs-lookup"><span data-stu-id="b1551-119">Set up work pools</span></span>

<span data-ttu-id="b1551-120">Med hjälp av arbetspooler kan du ordna arbetsuppgifter efter typ.</span><span class="sxs-lookup"><span data-stu-id="b1551-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="b1551-121">Om du vill arbeta med funktionen *Ändra arbetspool för arbete* måste du ha minst två arbetspooler tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b1551-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="b1551-122">Så här lägger du till arbetspooler.</span><span class="sxs-lookup"><span data-stu-id="b1551-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="b1551-123">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspooler**.</span><span class="sxs-lookup"><span data-stu-id="b1551-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="b1551-124">Om du arbetar med demo data från **USMF** företaget och kommer att arbeta genom exempelscenariot senare i det här avsnittet, lägger du till två arbetspooler som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b1551-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="b1551-125">Arbetspool 1:</span><span class="sxs-lookup"><span data-stu-id="b1551-125">Work pool 1:</span></span>

        - <span data-ttu-id="b1551-126">**Arbetspools-ID:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="b1551-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="b1551-127">**Beskrivning:** *Webbutik*</span><span class="sxs-lookup"><span data-stu-id="b1551-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="b1551-128">Arbetspool 2:</span><span class="sxs-lookup"><span data-stu-id="b1551-128">Work pool 2:</span></span>

        - <span data-ttu-id="b1551-129">**Arbetspools-ID:** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="b1551-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="b1551-130">**Beskrivning:** *Kundtjänst*</span><span class="sxs-lookup"><span data-stu-id="b1551-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="b1551-131">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b1551-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="b1551-132">Ställ in arbetsmallar</span><span class="sxs-lookup"><span data-stu-id="b1551-132">Set up work templates</span></span>

<span data-ttu-id="b1551-133">För varje arbetsmall kan du ställa in en standardpool för arbetsgrupp, efter behov.</span><span class="sxs-lookup"><span data-stu-id="b1551-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="b1551-134">För varje relevant mall tilldelar du en arbetsgrupp i kolumnen **arbetspools-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1551-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="b1551-135">I det här fallet ärver alla arbetsuppgifter som genereras med hjälp av en given mall automatiskt den tilldelade arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b1551-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="b1551-136">Om du arbetar med demo data från **USMF** företaget och kommer att arbeta genom exempelscenariot senare i det här avsnittet, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b1551-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="b1551-137">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="b1551-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b1551-138">I åtgärdsfönstret, välj **Redigera** för att placera sidan i redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b1551-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="b1551-139">Redigera mallen genom att ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="b1551-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="b1551-140">**Arbetsmallen:** *62 Välj för packa*</span><span class="sxs-lookup"><span data-stu-id="b1551-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="b1551-141">**Arbetspools-ID:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="b1551-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="b1551-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1551-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b1551-143">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="b1551-143">Example scenario</span></span>

<span data-ttu-id="b1551-144">Det här scenariot visar hur du ändrar flödet för bearbetning för en befintlig arbetsuppgift genom att ändra dess arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b1551-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="b1551-145">Den använder demodata från **USMF** företaget och de inställningar som föreslogs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b1551-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="b1551-146">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="b1551-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="b1551-147">Kontrollera att det finns tillräckligt lagerbehållning för artiklarna *A0001* och *A0002* i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="b1551-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="b1551-148">Gå till **lagerstyrning \> förfrågningar och rapporter \> behållningslistan** och redigera filtren som det visas här:</span><span class="sxs-lookup"><span data-stu-id="b1551-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="b1551-149">**Lagerställe** värdet börjar med *62*.</span><span class="sxs-lookup"><span data-stu-id="b1551-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="b1551-150">**Artikelnummer** värdet är antingen *A001* eller *A002*.</span><span class="sxs-lookup"><span data-stu-id="b1551-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="b1551-151">Demonstrationsdata ska ha kvantiteten 10 styck.</span><span class="sxs-lookup"><span data-stu-id="b1551-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="b1551-152">Sedan måste du skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="b1551-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="b1551-153">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="b1551-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b1551-154">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b1551-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b1551-155">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="b1551-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b1551-156">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b1551-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b1551-157">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="b1551-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="b1551-158">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b1551-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="b1551-159">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="b1551-159">The new sales order is opened.</span></span> <span data-ttu-id="b1551-160">Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="b1551-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b1551-161">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="b1551-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="b1551-162">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b1551-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b1551-163">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="b1551-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b1551-164">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="b1551-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b1551-165">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="b1551-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="b1551-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1551-166">Close the page.</span></span>
1. <span data-ttu-id="b1551-167">På snabbfliken **Försäljningsorderrader** välj **Lägg till rad** för att lägga till en ny rad i din försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="b1551-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="b1551-168">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="b1551-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="b1551-169">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="b1551-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="b1551-170">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="b1551-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b1551-171">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="b1551-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b1551-172">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="b1551-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="b1551-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1551-173">Close the page.</span></span>
1. <span data-ttu-id="b1551-174">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b1551-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b1551-175">Du får informationsmeddelanden som visar det påfyllnads-ID och leverans-ID som skapades från versionen.</span><span class="sxs-lookup"><span data-stu-id="b1551-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="b1551-176">Gör en notering av påfyllnad-ID.</span><span class="sxs-lookup"><span data-stu-id="b1551-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="b1551-177">Granska den utgående påfyllnaden</span><span class="sxs-lookup"><span data-stu-id="b1551-177">Review the outbound wave</span></span>

1. <span data-ttu-id="b1551-178">Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.</span><span class="sxs-lookup"><span data-stu-id="b1551-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b1551-179">I rutnätet söker du efter det påfyllnads-ID som skapades från frisläppningen av försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b1551-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="b1551-180">Välj påfyllnads-ID för att visa detaljerna.</span><span class="sxs-lookup"><span data-stu-id="b1551-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="b1551-181">På snabbfliken **Påfyllnadsrader** ser du till att ett leverans-ID visas för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b1551-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="b1551-182">Om alternativet **Bearbeta påfyllnaden vid släpp till lager** anges till *Nej* i inställningarna för mallen leverans påfyllnad, måste du bearbeta påfyllnad manuellt genom att välja **Process** från flik **Påfyllnad** på åtgärdsfönstret för att skapa arbete.</span><span class="sxs-lookup"><span data-stu-id="b1551-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="b1551-183">Kontrollera att påfyllnad har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="b1551-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="b1551-184">Den här bearbetningen skapar det begärda arbetet.</span><span class="sxs-lookup"><span data-stu-id="b1551-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="b1551-185">Visa arbetsdetaljer och ändra arbetsgruppen</span><span class="sxs-lookup"><span data-stu-id="b1551-185">View work details and change the work pool</span></span>

<span data-ttu-id="b1551-186">Du kan använda sidan **Arbetsuppgifter** för att se det arbete som skapades och för att hantera arbetspoolen.</span><span class="sxs-lookup"><span data-stu-id="b1551-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="b1551-187">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="b1551-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="b1551-188">Markera raden för det arbete som just har skapats.</span><span class="sxs-lookup"><span data-stu-id="b1551-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="b1551-189">I kolumnen **Ordernummer** visas försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="b1551-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="b1551-190">Fältet **arbetspools-ID** kommer att anges till det arbetspools-ID som har angetts i arbetsmallen.</span><span class="sxs-lookup"><span data-stu-id="b1551-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="b1551-191">Om fältet **arbetspools-ID** lägger du till kolumnen i rutnätet och uppdaterar sidan.</span><span class="sxs-lookup"><span data-stu-id="b1551-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="b1551-192">Om du vill ändra vilken arbetsgrupp som är associerad med arbets-ID väljer du **Arbete** välj **Ändra arbetspool-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1551-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="b1551-193">I dialogrutan **Ändra arbetspool** på snabbfliken **Parametrar** i fältet **Arbetspool-ID** välj *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="b1551-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="b1551-194">Välj **OK** om du vill använda ändringen.</span><span class="sxs-lookup"><span data-stu-id="b1551-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="b1551-195">Observera att värdet i fältet **arbetspools-ID** nu har ändrats till *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="b1551-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1551-196">När **Ändra arbetspool** visas kanske fältet **arbetspool-ID** är tomt som standard.</span><span class="sxs-lookup"><span data-stu-id="b1551-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="b1551-197">Om fältet är tomt när du väljer **OK** för att tillämpa ändringarna tas arbetspoolen bort helt från arbetet.</span><span class="sxs-lookup"><span data-stu-id="b1551-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="b1551-198">Förutom att växla mellan arbetspooler kan du använda den här proceduren för att lägga till en resurspool i en arbetsuppgift som inte har en eller för att ta bort en resurspool från valfri arbetsuppgift som har en sådan.</span><span class="sxs-lookup"><span data-stu-id="b1551-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>
