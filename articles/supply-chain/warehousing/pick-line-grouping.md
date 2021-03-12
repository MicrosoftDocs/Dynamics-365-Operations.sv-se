---
title: Plockradsgruppering
description: Det här ämnet ger en översikt över plockradsgruppering.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: e70244d46ec2787fefdb097d0354af7910b55e9c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989728"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="366cc-103">Plockradsgruppering</span><span class="sxs-lookup"><span data-stu-id="366cc-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="366cc-104">I plockradgruppering kan flera arbetsrader som har samma artikel och plats kombineras till en enda plockning som visas för användaren på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="366cc-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="366cc-105">Därför kan lagerarbetare få de mest effektiva instruktionerna, men nödvändig arbetsradeparation (för olika behållare, beställningar och så vidare) kan fortfarande bibehållas i systemet.</span><span class="sxs-lookup"><span data-stu-id="366cc-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="366cc-106">Aktivera funktionen plockradsgruppering</span><span class="sxs-lookup"><span data-stu-id="366cc-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="366cc-107">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="366cc-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="366cc-108">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="366cc-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="366cc-109">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="366cc-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="366cc-110">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="366cc-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="366cc-111">**Funktionsnamn:** *Plocka radgruppering*</span><span class="sxs-lookup"><span data-stu-id="366cc-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="366cc-112">Ställ in plockradsgruppering</span><span class="sxs-lookup"><span data-stu-id="366cc-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="366cc-113">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="366cc-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="366cc-114">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="366cc-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="366cc-115">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="366cc-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="366cc-116">I fältet **Menyartikelnamn** ange *Plockning av försäljningsgrupprad*.</span><span class="sxs-lookup"><span data-stu-id="366cc-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="366cc-117">I fältet **Rubrik** ange *Plockning av försäljningsgrupprad*.</span><span class="sxs-lookup"><span data-stu-id="366cc-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="366cc-118">Den här rubriken visas på menyn för den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="366cc-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="366cc-119">Välj **Arbete** i fältet *Läge*.</span><span class="sxs-lookup"><span data-stu-id="366cc-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="366cc-120">Ange alternativet **Använd befintligt arbete** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="366cc-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="366cc-121">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="366cc-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="366cc-122">I fältet **Dirigerad av** välj *Användarstyrd*.</span><span class="sxs-lookup"><span data-stu-id="366cc-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="366cc-123">Ange det här alternativet **Generera registreringsskylt** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="366cc-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="366cc-124">Ge alternativet **Grupplockning** värdet *Ja*.</span><span class="sxs-lookup"><span data-stu-id="366cc-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="366cc-125">Acceptera standardvärden för kvarvarande alternativ.</span><span class="sxs-lookup"><span data-stu-id="366cc-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="366cc-126">Följ dessa steg för att konfigurera de giltiga arbetsklasserna för mobila enhetens menyalternativ:</span><span class="sxs-lookup"><span data-stu-id="366cc-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="366cc-127">På snabbflikarna **Arbetsklasser** väljer du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="366cc-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="366cc-128">I fältet **Arbetsklass-ID** välj *Försäljning* eller *SO plocka*, beroende på vilket lagerställe du ska använda.</span><span class="sxs-lookup"><span data-stu-id="366cc-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="366cc-129">För det här scenariot väljer du *SO plocka*.</span><span class="sxs-lookup"><span data-stu-id="366cc-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="366cc-130">Fältet **Arbetsordertyp** anges automatiskt till *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="366cc-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="366cc-131">Ställ in mobil enhet för lagerställe</span><span class="sxs-lookup"><span data-stu-id="366cc-131">Set up a mobile device menu</span></span>

<span data-ttu-id="366cc-132">Följ dessa steg om du vill lägga till menyalternativet som du just skapade på **utgående** meny.</span><span class="sxs-lookup"><span data-stu-id="366cc-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="366cc-133">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="366cc-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="366cc-134">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="366cc-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="366cc-135">I listfönstret visas alla befintliga menyer för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="366cc-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="366cc-136">Välj *utgående* i listan.</span><span class="sxs-lookup"><span data-stu-id="366cc-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="366cc-137">I rutnätet **Tillgängliga menyer och artiklar** hitta och välj menyalternativet *Plockning av försäljningsgrupprad* som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="366cc-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="366cc-138">Klicka på högerpilen för att flytta menyalternativet *Plockning av försäljningsgrupprad* till listan **Menystruktur**.</span><span class="sxs-lookup"><span data-stu-id="366cc-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="366cc-139">Använd uppilen eller nedpilen om du vill flytta menyalternativet till önskad plats på menystrukturen.</span><span class="sxs-lookup"><span data-stu-id="366cc-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="366cc-140">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="366cc-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="366cc-141">Ställ in en arbetsmall</span><span class="sxs-lookup"><span data-stu-id="366cc-141">Set up a work template</span></span>

1. <span data-ttu-id="366cc-142">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="366cc-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="366cc-143">Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="366cc-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="366cc-144">I rutnätet **Översikt** välj arbetsmallen som ska användas med den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="366cc-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="366cc-145">För detta scenario, välj mallen *51 välj till fas*.</span><span class="sxs-lookup"><span data-stu-id="366cc-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="366cc-146">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="366cc-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="366cc-147">I frågerutan på fliken **Sortering** välj **Lägg till** för att lägga till en rad och ange sedan följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="366cc-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="366cc-148">I kolumnen **Tabell** väljer du *Tillfälliga arbetstransaktioner*.</span><span class="sxs-lookup"><span data-stu-id="366cc-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="366cc-149">I kolumnen **Härlett register** väljer du *Tillfälliga arbetsstransaktioner*.</span><span class="sxs-lookup"><span data-stu-id="366cc-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="366cc-150">I kolumnen **Fält**, välj *Artikelnummer*.</span><span class="sxs-lookup"><span data-stu-id="366cc-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="366cc-151">I kolumnen **Sökriktning** välj *Stigande*.</span><span class="sxs-lookup"><span data-stu-id="366cc-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="366cc-152">Välj **OK** om du vill spara inställningarna och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="366cc-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="366cc-153">Följande meddelande kan visas: "gruppering återställs, fortsätt?"</span><span class="sxs-lookup"><span data-stu-id="366cc-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="366cc-154">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="366cc-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="366cc-155">För att funktionen plockradsgruppering ska fungera måste arbetsraderna sorteras efter artikel-ID.</span><span class="sxs-lookup"><span data-stu-id="366cc-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="366cc-156">Om rader som har samma objekt inte sekvenseras en efter en grupperas de inte.</span><span class="sxs-lookup"><span data-stu-id="366cc-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="366cc-157">Exempel</span><span class="sxs-lookup"><span data-stu-id="366cc-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="366cc-158">Skapa plockarbete</span><span class="sxs-lookup"><span data-stu-id="366cc-158">Create picking work</span></span>

<span data-ttu-id="366cc-159">Innan du kan ställa in plockradsgruppering måste du skapa vissa kvalificerade utgående arbete.</span><span class="sxs-lookup"><span data-stu-id="366cc-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="366cc-160">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="366cc-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="366cc-161">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="366cc-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="366cc-162">I fältet **kundkonto** välj *US-004*.</span><span class="sxs-lookup"><span data-stu-id="366cc-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="366cc-163">På snabbfliken **Allmänt** i fältet **Lagerställe**, välj *51*.</span><span class="sxs-lookup"><span data-stu-id="366cc-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="366cc-164">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="366cc-164">Select **OK**.</span></span>
1. <span data-ttu-id="366cc-165">På snabbfliken **Försäljningsorderrader**, lägg till följande sex rader:</span><span class="sxs-lookup"><span data-stu-id="366cc-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="366cc-166">**Rad 1:** I fältet **Artikelnummer** välj *M9200*.</span><span class="sxs-lookup"><span data-stu-id="366cc-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="366cc-167">I fältet **Kvantitet**, ange *3*.</span><span class="sxs-lookup"><span data-stu-id="366cc-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="366cc-168">**Rad 2:** I fältet **Artikelnummer** välj *M9201*.</span><span class="sxs-lookup"><span data-stu-id="366cc-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="366cc-169">I fältet **Kvantitet**, ange *3*.</span><span class="sxs-lookup"><span data-stu-id="366cc-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="366cc-170">**Rad 3:** I fältet **Artikelnummer** välj *M9202*.</span><span class="sxs-lookup"><span data-stu-id="366cc-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="366cc-171">I fältet **Kvantitet**, ange *2*.</span><span class="sxs-lookup"><span data-stu-id="366cc-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="366cc-172">**Rad 4:** I fältet **Artikelnummer** välj *M9200*.</span><span class="sxs-lookup"><span data-stu-id="366cc-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="366cc-173">I fältet **Kvantitet**, ange *1*.</span><span class="sxs-lookup"><span data-stu-id="366cc-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="366cc-174">**Rad 5:** I fältet **Artikelnummer** välj *M9200*.</span><span class="sxs-lookup"><span data-stu-id="366cc-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="366cc-175">I fältet **Kvantitet**, ange *3*.</span><span class="sxs-lookup"><span data-stu-id="366cc-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="366cc-176">**Rad 6:** I fältet **Artikelnummer** välj *M9202*.</span><span class="sxs-lookup"><span data-stu-id="366cc-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="366cc-177">I fältet **Kvantitet**, ange *7*.</span><span class="sxs-lookup"><span data-stu-id="366cc-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="366cc-178">Här är en sammanfattning av de totala kvantiteterna för varje artikel:</span><span class="sxs-lookup"><span data-stu-id="366cc-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="366cc-179">**Artikel M9200:** *7* var</span><span class="sxs-lookup"><span data-stu-id="366cc-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="366cc-180">**Artikel M9201:** *3* var</span><span class="sxs-lookup"><span data-stu-id="366cc-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="366cc-181">**Artikel M9202:** *9* var</span><span class="sxs-lookup"><span data-stu-id="366cc-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="366cc-182">Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på alla order.</span><span class="sxs-lookup"><span data-stu-id="366cc-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="366cc-183">Granska inställningen **platsdirektiv** för att avgöra vilka plockplatser som används för plockning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="366cc-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="366cc-184">Om du använder Contoso-demodatamiljön för lagerställe *51* ska du bekräfta att det finns tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="366cc-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="366cc-185">Du måste nu reservera lagret för varje rad.</span><span class="sxs-lookup"><span data-stu-id="366cc-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="366cc-186">På snabbfliken **Försäljningsorderrader** välj en av raderna som måste reserveras.</span><span class="sxs-lookup"><span data-stu-id="366cc-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="366cc-187">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="366cc-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="366cc-188">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att tillämpa reservationen.</span><span class="sxs-lookup"><span data-stu-id="366cc-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="366cc-189">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="366cc-189">Then close the page.</span></span>
1. <span data-ttu-id="366cc-190">Upprepa steg 8 till 10 för de rader som återstår att reservera.</span><span class="sxs-lookup"><span data-stu-id="366cc-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="366cc-191">Du måste nu släppa försäljningsordern till lagret.</span><span class="sxs-lookup"><span data-stu-id="366cc-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="366cc-192">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="366cc-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="366cc-193">Du får ett meddelande om att en försändelse och en påfyllnad har skapats och att påfyllnad har skickats för körning i en batch.</span><span class="sxs-lookup"><span data-stu-id="366cc-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="366cc-194">När påfyllnad och alla jobb som är lediga skapas ett arbets-ID för arbete som har sex rader.</span><span class="sxs-lookup"><span data-stu-id="366cc-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="366cc-195">Raderna sorteras efter artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="366cc-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="366cc-196">Gå till **Lagerstyrning \> Arbete \> Allt arbete** för att visa det arbete som har skapats.</span><span class="sxs-lookup"><span data-stu-id="366cc-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="366cc-197">Anteckna värdet för **Arbets-ID** eftersom du behöver det i nästa procedur.</span><span class="sxs-lookup"><span data-stu-id="366cc-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="366cc-198">Initiera plockning från den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="366cc-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="366cc-199">Logga in på mobila enheten som en användare som är inställd på lagerstället *51*.</span><span class="sxs-lookup"><span data-stu-id="366cc-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="366cc-200">På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="366cc-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="366cc-201">För det här scenariot väljer du **Utgående**.</span><span class="sxs-lookup"><span data-stu-id="366cc-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="366cc-202">Välj menyalternativet **Plockning av försäljningsgrupprad** och initiera plockningen.</span><span class="sxs-lookup"><span data-stu-id="366cc-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="366cc-203">Ange värdet **arbets-ID** som du gjorde en notering i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="366cc-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="366cc-204">Du bör se ett plockningssteg där alla plockrader för artikel *M9200* grupperas och du bör få en instruktion för att plocka *7* varje artikel *M9200*.</span><span class="sxs-lookup"><span data-stu-id="366cc-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="366cc-205">På den mobila enheten har plockarbetet för de tre plockarbeteraderna aggregerats till ett plockningssteg för användaren.</span><span class="sxs-lookup"><span data-stu-id="366cc-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="366cc-206">Bekräfta plockningssteget.</span><span class="sxs-lookup"><span data-stu-id="366cc-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="366cc-207">Gå till arbetssidan för det arbets-ID som pågår och lägg märke till att alla tre plockningsrader för artikel *M9200* stängdes samtidigt.</span><span class="sxs-lookup"><span data-stu-id="366cc-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="366cc-208">Gå tillbaka till den mobila enheten och fortsätt att plocka.</span><span class="sxs-lookup"><span data-stu-id="366cc-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="366cc-209">Arbetsrad 4 för artikel *M9201* ska presenteras.</span><span class="sxs-lookup"><span data-stu-id="366cc-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="366cc-210">Eftersom det bara fanns en arbetsrad på ordern finns det inget att slå ihop.</span><span class="sxs-lookup"><span data-stu-id="366cc-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="366cc-211">Bekräfta plockningssteget.</span><span class="sxs-lookup"><span data-stu-id="366cc-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="366cc-212">Det sista plockningssteget på den mobila enheten sammanställer de två sista plockningsraderna från arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="366cc-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="366cc-213">Slutför plockningssteget för *9* var och en av artikel *M9202*.</span><span class="sxs-lookup"><span data-stu-id="366cc-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="366cc-214">Bekräfta inlagringssteget och eventuella ytterligare utskriftssteget efter inlagringssteget för att slutföra arbetet.</span><span class="sxs-lookup"><span data-stu-id="366cc-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="366cc-215">Arbetsrader kan bara grupperas om de är i sekvens.</span><span class="sxs-lookup"><span data-stu-id="366cc-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="366cc-216">Följande funktioner stöds inte:</span><span class="sxs-lookup"><span data-stu-id="366cc-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="366cc-217">Fångstviktartiklar</span><span class="sxs-lookup"><span data-stu-id="366cc-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="366cc-218">Om det finns några fångstviktartiklar i arbetet, visas ett felmeddelande innan du börjar plocka.</span><span class="sxs-lookup"><span data-stu-id="366cc-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="366cc-219">Enhetsplockning</span><span class="sxs-lookup"><span data-stu-id="366cc-219">Piece picking</span></span>
>   - <span data-ttu-id="366cc-220">Arbetsrader som har oavslutade lagerpåfyllnadsarbete</span><span class="sxs-lookup"><span data-stu-id="366cc-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="366cc-221">Överplockning</span><span class="sxs-lookup"><span data-stu-id="366cc-221">Over-picking</span></span>
>   - <span data-ttu-id="366cc-222">Kort plockning med omallokering av artiklar</span><span class="sxs-lookup"><span data-stu-id="366cc-222">Short picking with item reallocation</span></span>
