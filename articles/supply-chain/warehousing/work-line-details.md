---
title: Arbetsradsdetaljer
description: Det här avsnittet innehåller information om sidan arbetsraddetaljer, som innehåller en omfattande, sorterbar och filterbar lista över de enskilda arbetsraderna i systemet.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 07dbfa301e4b242f50a9c2758b11b5ad2c31b261
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998363"
---
# <a name="work-line-details"></a><span data-ttu-id="6176c-103">Arbetsradsdetaljer</span><span class="sxs-lookup"><span data-stu-id="6176c-103">Work line details</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6176c-104">Sidan **Information om arbetsrad** visar en omfattande, sorterbar och filtrerbar lista över de enskilda arbetslinjerna i ditt system.</span><span class="sxs-lookup"><span data-stu-id="6176c-104">The **Work line details** page shows a comprehensive, sortable, and filterable list of the individual work lines in your system.</span></span> <span data-ttu-id="6176c-105">Den ger en fullständig översikt över arbete som planeras och körs i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="6176c-105">It provides a complete overview of work that is being planned and executed in the warehouse.</span></span> <span data-ttu-id="6176c-106">Du kan enkelt växla mellan att visa alla arbetsrader och bara visa öppna arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="6176c-106">You can easily switch between viewing all work lines and viewing only open work lines.</span></span> <span data-ttu-id="6176c-107">Information som finns för varje rad är arbetsstatus, artikelnummer, plats, arbetskvantitet, last-ID och leverans-ID.</span><span class="sxs-lookup"><span data-stu-id="6176c-107">Details that are provided for each line include the work status, item number, location, work quantity, load ID, and shipment ID.</span></span>

## <a name="turn-on-the-work-line-details-feature"></a><span data-ttu-id="6176c-108">Aktivera funktionen arbetsraddetaljer</span><span class="sxs-lookup"><span data-stu-id="6176c-108">Turn on the work line details feature</span></span>

<span data-ttu-id="6176c-109">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="6176c-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6176c-110">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="6176c-110">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6176c-111">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="6176c-111">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6176c-112">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="6176c-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6176c-113">**Funktionsnamn:** *Arbetsraddetaljer*</span><span class="sxs-lookup"><span data-stu-id="6176c-113">**Feature name:** *Work line details*</span></span>

## <a name="open-and-use-the-work-line-details-page"></a><span data-ttu-id="6176c-114">Öppna och använd sidan med information om arbetsrader</span><span class="sxs-lookup"><span data-stu-id="6176c-114">Open and use the Work line details page</span></span>

<span data-ttu-id="6176c-115">Om du vill visa listan med arbetsraddetaljer går du till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="6176c-115">To view the list of work line details, go to **Warehouse management \> Work \> Work line details**.</span></span> <span data-ttu-id="6176c-116">Härifrån kan du sedan utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="6176c-116">From here, you can perform the following actions:</span></span>

- <span data-ttu-id="6176c-117">Använd fältet **Filter** om du vill söka efter rader som har ett specifikt värde för valfri tillgänglig parameter.</span><span class="sxs-lookup"><span data-stu-id="6176c-117">Use the **Filter** field to search for lines that have a specific value for any available parameter.</span></span> <span data-ttu-id="6176c-118">(Tillgängliga parametrar inkluderar många parametrar som inte visas som kolumner i rutnätet.)</span><span class="sxs-lookup"><span data-stu-id="6176c-118">(Available parameters include many parameters that aren't shown as columns in the grid.)</span></span>
- <span data-ttu-id="6176c-119">Använd kryssrutan **Visa stängda** om du vill visa eller dölja stängda rader.</span><span class="sxs-lookup"><span data-stu-id="6176c-119">Use the **Show closed** check box to show or hide closed lines.</span></span>
- <span data-ttu-id="6176c-120">Välj **Visa dimensioner** du vill öppna dialogrutan **Dimensionsvisning** där du kan välja att visa eller dölja olika dimensionskolumner i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="6176c-120">Select **Display dimensions** to open the **Dimensions display** dialog box, where you can choose to show or hide various dimension columns in the grid.</span></span>
- <span data-ttu-id="6176c-121">Välj en kolumnrubrik om du vill öppna en meny där du kan välja att sortera eller filtrera listan efter värden i den kolumnen.</span><span class="sxs-lookup"><span data-stu-id="6176c-121">Select any column heading to open a menu where you can choose to sort or filter the list by values in that column.</span></span>
- <span data-ttu-id="6176c-122">Markera en arbetsrad och välj sedan **ändra plats** du vill öppna en dialogruta där du kan ändra platsen för arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="6176c-122">Select a work line, and then select **Change location** to open a dialog box where you can change the location for that work line.</span></span> <span data-ttu-id="6176c-123">Den plats du anger åsidosätter inställningen för platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="6176c-123">The location that you specify will override the setup of the location directive.</span></span>
- <span data-ttu-id="6176c-124">Markera en arbetsrad och välj sedan **Avbryt arbetsrad** om du vill öppna en dialogruta där du helt eller delvis kan minska kvantiteten för den arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="6176c-124">Select a work line, and then select **Cancel work line** to open a dialog box where you can partially or fully reduce the quantity of that work line.</span></span>
- <span data-ttu-id="6176c-125">Justera kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="6176c-125">Adjust quantities.</span></span>
- <span data-ttu-id="6176c-126">Visa transaktionerna bakom valfri arbetsrad.</span><span class="sxs-lookup"><span data-stu-id="6176c-126">View the transactions behind any work line.</span></span>

## <a name="try-out-the-feature"></a><span data-ttu-id="6176c-127">Testa funktionen</span><span class="sxs-lookup"><span data-stu-id="6176c-127">Try out the feature</span></span>

<span data-ttu-id="6176c-128">Det här avsnittet innehåller en demonstration på tre delar som visar hur du arbetar med arbetsraddetaljer.</span><span class="sxs-lookup"><span data-stu-id="6176c-128">This section provides a three-part demo that shows how to work with work line details.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="6176c-129">Gör exempeldata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="6176c-129">Make sample data available</span></span>

<span data-ttu-id="6176c-130">Om du vill arbeta genom denna demo med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="6176c-130">To work through this demo by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="6176c-131">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="6176c-131">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="6176c-132">Du kan också använda denna demo som vägledning när du arbetar med ett produktionssystem.</span><span class="sxs-lookup"><span data-stu-id="6176c-132">You can also use this demo as guidance when you work on a production system.</span></span> <span data-ttu-id="6176c-133">Du måste emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.</span><span class="sxs-lookup"><span data-stu-id="6176c-133">However, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a><span data-ttu-id="6176c-134">Kontrollera att scenarioinställningen innehåller tillräckligt med tillgängligt lager</span><span class="sxs-lookup"><span data-stu-id="6176c-134">Verify that the scenario setup includes enough available inventory</span></span>

<span data-ttu-id="6176c-135">Om du arbetar med **USMF** demodata, bör du först se till att ditt system är konfigurerat så att tillräckligt med lager finns tillgängliga på varje relevant plats.</span><span class="sxs-lookup"><span data-stu-id="6176c-135">If you're working with the **USMF** demo data, you should first make sure that your system is set up so that enough inventory is available at each relevant pick location.</span></span> <span data-ttu-id="6176c-136">I den här demon är det förväntat att du har följande lager tillgängligt:</span><span class="sxs-lookup"><span data-stu-id="6176c-136">For this demo, the expectation is that you have the following inventory available:</span></span>

- <span data-ttu-id="6176c-137">**Artikel M9200:** 45 ea.</span><span class="sxs-lookup"><span data-stu-id="6176c-137">**Item M9200:** 45 ea.</span></span> <span data-ttu-id="6176c-138">(eller mer)</span><span class="sxs-lookup"><span data-stu-id="6176c-138">(or more)</span></span>
- <span data-ttu-id="6176c-139">**Artikel M9202:** 10 ea.</span><span class="sxs-lookup"><span data-stu-id="6176c-139">**Item M9202:** 10 ea.</span></span> <span data-ttu-id="6176c-140">(eller mer)</span><span class="sxs-lookup"><span data-stu-id="6176c-140">(or more)</span></span>

<span data-ttu-id="6176c-141">Följ dessa steg för att kontrollera att det finns tillräckligt med tillgängligt lager och du måste göra eventuella justeringar.</span><span class="sxs-lookup"><span data-stu-id="6176c-141">Follow these steps to verify that enough inventory is available and to make any adjustments that are required.</span></span>

1. <span data-ttu-id="6176c-142">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv** och bestäm vilka plockningsplatser som används för plockning av försäljningsorder på lagerställe 51.</span><span class="sxs-lookup"><span data-stu-id="6176c-142">Go to **Warehouse management \> Setup \> Location directives**, and determine which picking locations are used for sales order picking at warehouse 51.</span></span> <span data-ttu-id="6176c-143">(Mer information finns i [Lagerpåfyllnad och Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).)</span><span class="sxs-lookup"><span data-stu-id="6176c-143">(For more information, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md).)</span></span>
1. <span data-ttu-id="6176c-144">Kontrollera lagernivåerna på de relevanta platserna.</span><span class="sxs-lookup"><span data-stu-id="6176c-144">Check the inventory levels at the relevant locations.</span></span>
1. <span data-ttu-id="6176c-145">Justera lagret efter behov.</span><span class="sxs-lookup"><span data-stu-id="6176c-145">Adjust inventory as required.</span></span> <span data-ttu-id="6176c-146">Du kan skapa manuella transporter, använda återanskaffning eller använda andra flöden för att justera lagret.</span><span class="sxs-lookup"><span data-stu-id="6176c-146">You can create manual movements, use replenishment, or apply any other flow to adjust the inventory.</span></span>

### <a name="part-1-create-picking-work"></a><span data-ttu-id="6176c-147">Del 1: Skapa plockarbete</span><span class="sxs-lookup"><span data-stu-id="6176c-147">Part 1: Create picking work</span></span>

<span data-ttu-id="6176c-148">Innan du börjar skapa arbete ska du se till att distributionslagret är inställt på att svara på arbetsförfrågningar på det sätt som förväntas.</span><span class="sxs-lookup"><span data-stu-id="6176c-148">Before you start to create work, make sure that your warehouse is set up to respond to work requests in the expected manner.</span></span>

<span data-ttu-id="6176c-149">Följ dessa steg för att skapa lite plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="6176c-149">Follow these steps to create some picking work.</span></span>

1. <span data-ttu-id="6176c-150">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="6176c-150">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6176c-151">Välj **Ny** om du vill öppna dialogrutan **Skapa försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="6176c-151">Select **New** to open the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="6176c-152">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="6176c-152">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6176c-153">På snabbfliken **Kund** ställer du in fältet **Kundkonto** på _US-001_.</span><span class="sxs-lookup"><span data-stu-id="6176c-153">On the **Customer** FastTab, set the **Customer account** field to _US-001_.</span></span>
    - <span data-ttu-id="6176c-154">På snabbfliken **Allmänt** anger du fältet **Lagerställe** till _51_.</span><span class="sxs-lookup"><span data-stu-id="6176c-154">On the **General** FastTab, set the **Warehouse** field to _51_.</span></span>

1. <span data-ttu-id="6176c-155">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6176c-155">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="6176c-156">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="6176c-156">Your new sales order is opened.</span></span> <span data-ttu-id="6176c-157">Den innehåller en ny, tom rad i rutnätet **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="6176c-157">It includes a new, empty row in the **Sales order lines** grid.</span></span> <span data-ttu-id="6176c-158">Ställ in följande värden på denna orderrad:</span><span class="sxs-lookup"><span data-stu-id="6176c-158">On this order line, set the following values:</span></span>

    - <span data-ttu-id="6176c-159">**Artikelnummer:** _M9200_</span><span class="sxs-lookup"><span data-stu-id="6176c-159">**Item number:** _M9200_</span></span>
    - <span data-ttu-id="6176c-160">**Kvantitet:** _20_</span><span class="sxs-lookup"><span data-stu-id="6176c-160">**Quantity:** _20_</span></span>
    - <span data-ttu-id="6176c-161">**Enhet:** _ea_</span><span class="sxs-lookup"><span data-stu-id="6176c-161">**Unit:** _ea_</span></span>

1. <span data-ttu-id="6176c-162">Välj den nya orderraden och sedan på menyn **Lager** väljer du **Reservation** för att öppna sidan **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="6176c-162">Select the new order line, and then, on the **Inventory** menu, select **Reservation** to open the **Reservation** page.</span></span>
1. <span data-ttu-id="6176c-163">På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="6176c-163">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="6176c-164">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="6176c-164">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="6176c-165">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="6176c-165">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span> <span data-ttu-id="6176c-166">Systemet skapar en leverans, lägger till den i en ny last och skapar det begärda arbetet.</span><span class="sxs-lookup"><span data-stu-id="6176c-166">The system creates a shipment, adds it to a new load, and creates the required work.</span></span>
1. <span data-ttu-id="6176c-167">Skapa en andra försäljningsorder för samma kundkonto och lagerställe som du använde för den första ordern.</span><span class="sxs-lookup"><span data-stu-id="6176c-167">Create a second sales order for the same customer account and warehouse that you used for the first order.</span></span> <span data-ttu-id="6176c-168">Lägg till följande två orderrader till denna order:</span><span class="sxs-lookup"><span data-stu-id="6176c-168">Add the following two order lines to this order:</span></span>

    - <span data-ttu-id="6176c-169">**Rad 1:** Ställ in fältet **Artikelnummer** till _M9200_, fältet **Kvantitet** till _25_ och fältet **Enhet** till _ea_.</span><span class="sxs-lookup"><span data-stu-id="6176c-169">**Line 1:** Set the **Item number** field to _M9200_, the **Quantity** field to _25_, and the **Unit** field to _ea_.</span></span>
    - <span data-ttu-id="6176c-170">**Rad 2:** Ställ in fältet **Artikelnummer** till _M9202_, fältet **Kvantitet** till _10_ och fältet **Enhet** till _ea_.</span><span class="sxs-lookup"><span data-stu-id="6176c-170">**Line 2:** Set the **Item number** field to _M9202_, the **Quantity** field to _10_, and the **Unit** field to _ea_.</span></span>

1. <span data-ttu-id="6176c-171">Upprepa steg 6 till 8 för att reservera lagret för varje orderrad (ett i taget) och upprepa sedan steg 9 för att frisläppa ordern till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="6176c-171">Repeat steps 6 through 8 to reserve the inventory for each order line (one at a time), and then repeat step 9 to release the order to the warehouse.</span></span>

### <a name="part-2-change-the-location-for-a-work-line"></a><span data-ttu-id="6176c-172">Del 2: ändra platsen för en arbetsrad</span><span class="sxs-lookup"><span data-stu-id="6176c-172">Part 2: Change the location for a work line</span></span>

1. <span data-ttu-id="6176c-173">Gå till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="6176c-173">Go to **Warehouse management \> Work \> Work line details**.</span></span>
1. <span data-ttu-id="6176c-174">Sök reda på och välj en av de arbetsrader som du har skapat för den här demon.</span><span class="sxs-lookup"><span data-stu-id="6176c-174">Find and select one of the work lines that you created for this demo.</span></span>
1. <span data-ttu-id="6176c-175">Välj **Ändra plats** om du vill öppna dialogrutan **Välj ny plats**.</span><span class="sxs-lookup"><span data-stu-id="6176c-175">Select **Change location** to open the **Select new location** dialog box.</span></span>
1. <span data-ttu-id="6176c-176">I dialogrutan **Välj ny plats** i fältet **Plats** väljer du en ny plats för arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="6176c-176">In the **Select new location** dialog box, in the **Location** field, select a new location for the work line.</span></span>
1. <span data-ttu-id="6176c-177">Välj **OK** om du vill tillämpa ändringen och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6176c-177">Select **OK** to apply your change and close the dialog box.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6176c-178">Du kan bara skicka platsändringar om det finns tillräckligt med lager tillgängligt för den nya lagerstället (för en plockning) eller om det skickar validering av platstyp (för en läggning).</span><span class="sxs-lookup"><span data-stu-id="6176c-178">You can submit location changes only if the new location has enough inventory available (for a pick), or if it passes location-type validation (for a put).</span></span>

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a><span data-ttu-id="6176c-179">Del 3: ändra kvantiteten för en arbetsrad eller avbryt en arbetsrad</span><span class="sxs-lookup"><span data-stu-id="6176c-179">Part 3: Change the quantity of a work line or cancel a work line</span></span>

1. <span data-ttu-id="6176c-180">Gå till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="6176c-180">Go to **Warehouse management \> Work \> Work line details**.</span></span>
1. <span data-ttu-id="6176c-181">Sök reda på och välj en av de arbetsrader som du har skapat för den här demon.</span><span class="sxs-lookup"><span data-stu-id="6176c-181">Find and select one of the work lines that you created for this demo.</span></span> <span data-ttu-id="6176c-182">Observera att du bara kan annullera eller ändra kvantiteter för arbetsrader där arbetstypen är _plocka_.</span><span class="sxs-lookup"><span data-stu-id="6176c-182">Note that you can cancel or change quantities only for work lines where the work type is _pick_.</span></span>
1. <span data-ttu-id="6176c-183">Välj **Avbryt arbetsrad** om du vill öppna dialogruta **Kvantitet att avbryta**.</span><span class="sxs-lookup"><span data-stu-id="6176c-183">Select **Cancel work line** to open the **Quantity to cancel** dialog box.</span></span>
1. <span data-ttu-id="6176c-184">I dialogrutan **Kvantitet att avbryta** ändrar du värdet i fältet **Kvantitet** för att ange den kvantitet som ska *dras av från* den kvantitet som redan har angetts för raden.</span><span class="sxs-lookup"><span data-stu-id="6176c-184">In the **Quantity to cancel** dialog box, change the value in the **Quantity** field to specify the quantity that should be *subtracted from* the quantity that is currently specified for the line.</span></span> <span data-ttu-id="6176c-185">Som standard visar fältet **kvantitet** hela kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6176c-185">By default, the **Quantity** field shows the full quantity.</span></span>

    - <span data-ttu-id="6176c-186">Om du avbryter hela kvantiteten kommer **Arbetsstatus** att ändras till _Annullerad_, men fältet **Arbetskvantitet** visar fortfarande det ursprungliga värdet.</span><span class="sxs-lookup"><span data-stu-id="6176c-186">If you cancel the full quantity, the **Work status** value will be changed to _Canceled_, but the **Work quantity** field will still show the original value.</span></span>
    - <span data-ttu-id="6176c-187">Om du endast avbryter en del av kvantiteten kommer fältet **Arbetskvantitet** att uppdateras och visa det nya värdet men värdet **Arbetsstatus** ändras inte.</span><span class="sxs-lookup"><span data-stu-id="6176c-187">If you cancel just part of the quantity, the **Work quantity** field will be updated to show the new value, but the **Work status** value won't change.</span></span>

1. <span data-ttu-id="6176c-188">Välj **OK** om du vill tillämpa ändringen och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6176c-188">Select **OK** to apply your change and close the dialog box.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6176c-189">Om du avbryter bara en del av kvantiteten för en arbetsrad, måste du också ta bort den inaktuella kvantiteten från lastraden.</span><span class="sxs-lookup"><span data-stu-id="6176c-189">If you cancel just part of the quantity for a work line, you must also remove the obsolete quantity from the load line.</span></span> <span data-ttu-id="6176c-190">Annars, om inte under leverans har ställts in korrekt, kan lastraden inte bekräftas för levererans.</span><span class="sxs-lookup"><span data-stu-id="6176c-190">Otherwise, unless under-delivery is set up correctly, the load line can't be ship-confirmed.</span></span>
