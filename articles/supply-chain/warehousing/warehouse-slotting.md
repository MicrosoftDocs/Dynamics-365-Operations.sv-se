---
title: Artikelplacering för lagerställe
description: Den här ämnet innehåller information om artikelplacering för lagerställe. Artikelplacering för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status beställt, reserverat eller frisläppt. Det underlättar för lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ed9e6eae2ecc8de8d5eeef4699678e93dd74f193
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017424"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="9c725-105">Artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="9c725-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c725-106">Artikelplacering för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status *beställt* , *reserverat* eller *frisläppt*.</span><span class="sxs-lookup"><span data-stu-id="9c725-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered* , *Reserved* , or *Released*.</span></span> <span data-ttu-id="9c725-107">Genererade behov kan sedan tillämpas på platser som ska användas för plockning, baserat på kvantitet, enhet, fysiska dimensioner, fasta platser och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="9c725-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="9c725-108">När artikelplaceringsplanen har fastställts kan du skapa ett lagerpåfyllnadsarbete för att hämta en lämplig lagermängd till varje plats.</span><span class="sxs-lookup"><span data-stu-id="9c725-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="9c725-109">Denna funktion underlättar för lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9c725-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="9c725-110">Aktivera funktionen artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="9c725-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="9c725-111">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="9c725-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="9c725-112">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="9c725-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="9c725-113">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="9c725-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="9c725-114">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="9c725-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="9c725-115">**Funktionens namn:** *Funktionen artikelplacering för lagerställe*</span><span class="sxs-lookup"><span data-stu-id="9c725-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="9c725-116">Ställ in artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="9c725-116">Set up warehouse slotting</span></span>

<span data-ttu-id="9c725-117">Om du vill använda artikelplacering för lagerställe måste du ställa följande element i systemet:</span><span class="sxs-lookup"><span data-stu-id="9c725-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="9c725-118">Skapa måttenhetsnivåer för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="9c725-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="9c725-119">Enhetsmåttnivåer gör att flera måttenheter kan grupperas tillsammans i en artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="9c725-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="9c725-120">Om t.ex. flera storlekar av lådorna har valts från samma låda, kan en nivå skapas för alla storlekar.</span><span class="sxs-lookup"><span data-stu-id="9c725-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="9c725-121">**En rad måste skapas för varje måttenhet som ska ingå i nivån.**</span><span class="sxs-lookup"><span data-stu-id="9c725-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="9c725-122">Gå till **Lagerstyrning \> Inställningar \> Påfyllning \> Måttenhetsnivåer för artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="9c725-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="9c725-123">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9c725-123">Select **New**.</span></span>
1. <span data-ttu-id="9c725-124">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="9c725-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="9c725-125">**Enhetsnivå:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="9c725-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="9c725-126">**Beskrivning:** *Varje låda, lastpall*</span><span class="sxs-lookup"><span data-stu-id="9c725-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="9c725-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9c725-127">Select **Save**.</span></span>
1. <span data-ttu-id="9c725-128">På snabbfliken **Måttenheter** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9c725-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="9c725-129">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-130">**Enhet:** *låda*</span><span class="sxs-lookup"><span data-stu-id="9c725-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="9c725-131">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9c725-132">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9c725-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9c725-133">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="9c725-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9c725-134">Välj **Ny** om du vill lägga till andra rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9c725-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="9c725-135">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-136">**Enhet:** *ea*</span><span class="sxs-lookup"><span data-stu-id="9c725-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="9c725-137">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9c725-138">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9c725-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9c725-139">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="9c725-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9c725-140">Välj **Ny** om du vill lägga till tredje rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9c725-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="9c725-141">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-142">**Enhet:** *PL*</span><span class="sxs-lookup"><span data-stu-id="9c725-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="9c725-143">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="9c725-144">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9c725-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="9c725-145">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="9c725-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="9c725-146">Välj **Spara** för att spara nivån.</span><span class="sxs-lookup"><span data-stu-id="9c725-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="9c725-147">Skapa en direktivkod för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="9c725-147">Create a directive code for slotting</span></span>

<span data-ttu-id="9c725-148">Du måste välja den direktivkod som ska associeras med en mall.</span><span class="sxs-lookup"><span data-stu-id="9c725-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="9c725-149">Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.</span><span class="sxs-lookup"><span data-stu-id="9c725-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="9c725-150">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9c725-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9c725-151">I fältet **Direktivkod** , ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="9c725-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="9c725-152">I fältet **Beskrivning av direktivkod** , ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="9c725-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="9c725-153">Ställ in artikelplaceringsmallar</span><span class="sxs-lookup"><span data-stu-id="9c725-153">Set up slotting templates</span></span>

<span data-ttu-id="9c725-154">Varje artikelplaceringsmall styr hur lagret tilldelas till platser för ett visst lagerställe.</span><span class="sxs-lookup"><span data-stu-id="9c725-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="9c725-155">Varje mall måste innehålla en rad för varje artikelplaceringsspecifikation.</span><span class="sxs-lookup"><span data-stu-id="9c725-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="9c725-156">Använd procedurerna i det här avsnittet om du vill ställa in artikelplaceringsmallar.</span><span class="sxs-lookup"><span data-stu-id="9c725-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="9c725-157">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar**.</span><span class="sxs-lookup"><span data-stu-id="9c725-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="9c725-158">Skapa en ny mall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="9c725-158">Select **New** to create a template.</span></span>

<span data-ttu-id="9c725-159">Sedan måste du ställa in mallhuvudet, artikelplaceringsspecifikation och platsdirektiven, enligt beskrivningen i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="9c725-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="9c725-160">Ställa in ett artikelplacering mallhuvud</span><span class="sxs-lookup"><span data-stu-id="9c725-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="9c725-161">Ange följande värden i mallens rubrik:</span><span class="sxs-lookup"><span data-stu-id="9c725-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="9c725-162">**Artikelplaceringsmall:** _61_</span><span class="sxs-lookup"><span data-stu-id="9c725-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="9c725-163">**Beskrivning:** _61_</span><span class="sxs-lookup"><span data-stu-id="9c725-163">**Description:** _61_</span></span>
    - <span data-ttu-id="9c725-164">**Efterfrågetyp:** *försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="9c725-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="9c725-165">För närvarande är den enda efterfrågetypen som stöds *försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="9c725-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="9c725-166">**Efterfrågestrategi:** _beställt_</span><span class="sxs-lookup"><span data-stu-id="9c725-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="9c725-167">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="9c725-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="9c725-168">**Beställt** – hela den beställda kvantiteten på försäljningsordern ska behandlas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="9c725-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="9c725-169">**Reserverat** – endast försäljningsorderradens kvantitet som är reserverade (fysiska och beställda) ska betraktas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="9c725-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="9c725-170">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="9c725-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="9c725-171">**Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="9c725-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="9c725-172">Du kan även ange en fråga för att begränsa omfattningen av den efterfrågan som utvärderas.</span><span class="sxs-lookup"><span data-stu-id="9c725-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="9c725-173">Ställa in en artikelplaceringsspecifikation för varje mall</span><span class="sxs-lookup"><span data-stu-id="9c725-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="9c725-174">För varje mall som du skapar lägger du till en rad för varje artikelplaceringsspecifikation genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9c725-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="9c725-175">På snabbfliken **Information artikelplaceringsspecifikation** välj **Ny** för att skapa en mallrad.</span><span class="sxs-lookup"><span data-stu-id="9c725-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="9c725-176">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-177">**Sekvens:** _1_</span><span class="sxs-lookup"><span data-stu-id="9c725-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="9c725-178">**Beskrivning:** _Fast plats_</span><span class="sxs-lookup"><span data-stu-id="9c725-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="9c725-179">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="9c725-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="9c725-180">I det här fältet definieras den minsta kvantitet efter frågan som krävs för raden.</span><span class="sxs-lookup"><span data-stu-id="9c725-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="9c725-181">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9c725-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="9c725-182">I det här fältet definieras den högsta kvantitet för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="9c725-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="9c725-183">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="9c725-184">I det här fältet anges den måttenhet som lägsta och högsta kvantiteter refererar till.</span><span class="sxs-lookup"><span data-stu-id="9c725-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="9c725-185">**Måttenhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="9c725-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="9c725-186">I det här fältet definieras den enhetsnivå för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="9c725-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="9c725-187">(Mer information finns i avsnittet [Ange måttenhetsnivå för artikelplacering](#unit-tiers) tidigare i det här avsnittet.)</span><span class="sxs-lookup"><span data-stu-id="9c725-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="9c725-188">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="9c725-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="9c725-189">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="9c725-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="9c725-190">**Antag vara tom** – det här systemet ska anta att alla platser i plockområdet är tomma och inte ska kontrollera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="9c725-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="9c725-191">**Överväg kvantitet** – Systemet bör kontrollera platserna i plockningsområdet för inventering och bör hoppa över alla platser som inte är tomma.</span><span class="sxs-lookup"><span data-stu-id="9c725-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="9c725-192">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="9c725-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="9c725-193">I det här fältet definieras det platsdirektiv som används för att hitta plockplatsen för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="9c725-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="9c725-194">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="9c725-195">Det här fältet definierar det lagerställe som har placerats på om det inte går att hitta en plats för kvantiteten när raden bearbetas.</span><span class="sxs-lookup"><span data-stu-id="9c725-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="9c725-196">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="9c725-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="9c725-197">Om det här alternativet är inställt på *Ja* , kommer flyttningsarbetet att skapas för att ta ut lagret med lagerställen, men där inget har öppnats.</span><span class="sxs-lookup"><span data-stu-id="9c725-197">When this option is set to *Yes* , if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="9c725-198">Mallen körs sedan igen.</span><span class="sxs-lookup"><span data-stu-id="9c725-198">The template is then run again.</span></span> <span data-ttu-id="9c725-199">Den här gången ignoreras lagret på platserna.</span><span class="sxs-lookup"><span data-stu-id="9c725-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="9c725-200">Den här funktionen fungerar bäst om fältet **Tilldela kortplatskriterier** är inställt på _Överväg kvantitet_.</span><span class="sxs-lookup"><span data-stu-id="9c725-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="9c725-201">**Användning av fast lagerplats:** _Endast fasta lagerplatser för produkten_</span><span class="sxs-lookup"><span data-stu-id="9c725-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="9c725-202">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="9c725-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="9c725-203">**Fasta och icke-fasta lagerplatser** – systemet ska inte begränsas till att bara använda fasta lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="9c725-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="9c725-204">**Endast fasta lagerplatser för produkten** – systemet ska endast kortas till platser som är fasta lagerplatser för produkten.</span><span class="sxs-lookup"><span data-stu-id="9c725-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="9c725-205">**Endast fasta lagerplatser för produktvarianten** – systemet ska endast kortas till platser som är fasta lagerplatser för produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="9c725-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="9c725-206">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9c725-206">Select **Save**.</span></span>
1. <span data-ttu-id="9c725-207">Klicka på **Ny** för att skapa en andra mallrad.</span><span class="sxs-lookup"><span data-stu-id="9c725-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="9c725-208">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-209">**Sekvens:** _2_</span><span class="sxs-lookup"><span data-stu-id="9c725-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="9c725-210">**Beskrivning:** _andra_</span><span class="sxs-lookup"><span data-stu-id="9c725-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="9c725-211">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="9c725-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="9c725-212">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9c725-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="9c725-213">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="9c725-214">**Enhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="9c725-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="9c725-215">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="9c725-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="9c725-216">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="9c725-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="9c725-217">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="9c725-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="9c725-218">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="9c725-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="9c725-219">**Använda fasta lagerplatser:** _Fasta och ej fasta platser_</span><span class="sxs-lookup"><span data-stu-id="9c725-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="9c725-220">I frågan för den andra raden kommer du nu att ange de kriterier som används för att bestämma vilka platser som efter frågan för den raden kan avsättas till.</span><span class="sxs-lookup"><span data-stu-id="9c725-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="9c725-221">Välj raden där fältet **Sekvens** är inställt på *2*.</span><span class="sxs-lookup"><span data-stu-id="9c725-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="9c725-222">Välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="9c725-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="9c725-223">På fliken **intervall** , välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9c725-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="9c725-224">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-225">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="9c725-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9c725-226">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="9c725-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9c725-227">**Fält:** *platsprofil-ID*</span><span class="sxs-lookup"><span data-stu-id="9c725-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="9c725-228">**Kriterier:** *Plocka-06* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Plocka-06* - *Plockplats 6*.)</span><span class="sxs-lookup"><span data-stu-id="9c725-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="9c725-229">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c725-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="9c725-230">Ställ in platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="9c725-230">Set up location directives</span></span>

<span data-ttu-id="9c725-231">Minst ett platsdirektiv måste ställas in för att stödja plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="9c725-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="9c725-232">Använd procedurerna i det här avsnittet om du vill skapa ett nytt *platsdirektiv för påfyllnad* för plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="9c725-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="9c725-233">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="9c725-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="9c725-234">I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *lagerpåfyllnad*.</span><span class="sxs-lookup"><span data-stu-id="9c725-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="9c725-235">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9c725-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9c725-236">I rubriken för det nya platsdirektivet anger du i fältet **Namn** *61 plocka artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="9c725-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="9c725-237">Konfigurera snabbfliken platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="9c725-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="9c725-238">Ange följande värden på snabbfliken **Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="9c725-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="9c725-239">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="9c725-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="9c725-240">**Arbetstyp:** _plockning_</span><span class="sxs-lookup"><span data-stu-id="9c725-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="9c725-241">**Plats:** _6_</span><span class="sxs-lookup"><span data-stu-id="9c725-241">**Site:** _6_</span></span>
    - <span data-ttu-id="9c725-242">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="9c725-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="9c725-243">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="9c725-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="9c725-244">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9c725-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="9c725-245">Konfigurera snabbfliken Rader</span><span class="sxs-lookup"><span data-stu-id="9c725-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="9c725-246">På snabbfliken **Rader** , klicka på **Ny** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="9c725-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="9c725-247">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="9c725-247">On the new line, set the following values.</span></span> <span data-ttu-id="9c725-248">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="9c725-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="9c725-249">**Från kvantitet:** _0_</span><span class="sxs-lookup"><span data-stu-id="9c725-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="9c725-250">**Till kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="9c725-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="9c725-251">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9c725-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="9c725-252">Konfigurera snabbfliken Platsdirektivåtgärder</span><span class="sxs-lookup"><span data-stu-id="9c725-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="9c725-253">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="9c725-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="9c725-254">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="9c725-254">On the new line, set the following values.</span></span> <span data-ttu-id="9c725-255">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="9c725-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="9c725-256">**Namn:** _Bulk_</span><span class="sxs-lookup"><span data-stu-id="9c725-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="9c725-257">**Strategi:** _ingen_</span><span class="sxs-lookup"><span data-stu-id="9c725-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="9c725-258">Välj **Spara** om du vill göra knappen **Redigera fråga** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9c725-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="9c725-259">Redigera frågan</span><span class="sxs-lookup"><span data-stu-id="9c725-259">Edit the query</span></span>

1. <span data-ttu-id="9c725-260">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="9c725-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="9c725-261">På fliken **intervall** , välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9c725-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="9c725-262">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9c725-263">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="9c725-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9c725-264">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="9c725-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9c725-265">**Fält:** *zon-ID*</span><span class="sxs-lookup"><span data-stu-id="9c725-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="9c725-266">**Kriterier:** *Bulk* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Bulk*.)</span><span class="sxs-lookup"><span data-stu-id="9c725-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="9c725-267">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c725-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="9c725-268">Scenario</span><span class="sxs-lookup"><span data-stu-id="9c725-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="9c725-269">Ställ in scenario</span><span class="sxs-lookup"><span data-stu-id="9c725-269">Set up the scenario</span></span>

<span data-ttu-id="9c725-270">I det här scenariot ska du använda de inbyggda exempeldata och skapa posterna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9c725-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="9c725-271">Använd exempeldata för USMF</span><span class="sxs-lookup"><span data-stu-id="9c725-271">Use the USMF sample data</span></span>

<span data-ttu-id="9c725-272">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="9c725-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="9c725-273">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="9c725-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="9c725-274">Skapa efterfrågan</span><span class="sxs-lookup"><span data-stu-id="9c725-274">Create demand</span></span>

<span data-ttu-id="9c725-275">Skapa den efter frågan som du vill använda skåra på genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9c725-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="9c725-276">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9c725-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="9c725-277">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9c725-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="9c725-278">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-007_.</span><span class="sxs-lookup"><span data-stu-id="9c725-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="9c725-279">I fältet **Lagerställe** , välj _61_.</span><span class="sxs-lookup"><span data-stu-id="9c725-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="9c725-280">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c725-280">Select **OK**.</span></span>
1. <span data-ttu-id="9c725-281">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="9c725-281">The new sales order is opened.</span></span> <span data-ttu-id="9c725-282">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="9c725-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="9c725-283">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="9c725-284">**Artikel:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="9c725-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="9c725-285">**Kvantitet:** _20_</span><span class="sxs-lookup"><span data-stu-id="9c725-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="9c725-286">Välj **Lägg till rad** för att lägga till en nya rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="9c725-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="9c725-287">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="9c725-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="9c725-288">**Kvantitet:** _8_</span><span class="sxs-lookup"><span data-stu-id="9c725-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="9c725-289">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9c725-289">Select **Save**.</span></span>
1. <span data-ttu-id="9c725-290">Skapa en andra försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9c725-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="9c725-291">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-008_.</span><span class="sxs-lookup"><span data-stu-id="9c725-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="9c725-292">I fältet **Lagerställe** , välj _61_.</span><span class="sxs-lookup"><span data-stu-id="9c725-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="9c725-293">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="9c725-293">The new sales order is opened.</span></span> <span data-ttu-id="9c725-294">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="9c725-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="9c725-295">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="9c725-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="9c725-296">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="9c725-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="9c725-297">**Kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="9c725-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="9c725-298">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9c725-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="9c725-299">Gå igenom ett vanligt artikelplaceringsscenario</span><span class="sxs-lookup"><span data-stu-id="9c725-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="9c725-300">När alla nödvändiga element är på rätt sätt, så som beskrivs i föregående avsnitt, är du redo att testa funktionen genom att arbeta igenom varje övning i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9c725-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="9c725-301">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="9c725-301">Generate demand</span></span>

1. <span data-ttu-id="9c725-302">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar** och välj artikelplaceringsmallen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="9c725-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates** , and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="9c725-303">Välj **efterfrågeprognoser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9c725-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="9c725-304">Det här kommandot utvärderar alla efter frågan i systemet och matchar den i artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="9c725-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="9c725-305">Den totala efter frågan på alla order konsolideras sedan på en rad per kvantitet/måttenhet.</span><span class="sxs-lookup"><span data-stu-id="9c725-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="9c725-306">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9c725-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="9c725-307">Efterfrågan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="9c725-307">Slotting demand</span></span>

<span data-ttu-id="9c725-308">*Behovet av artikelplacering* visar resultatet av efterfrågegenereringen, baserat på inställningarna för den artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="9c725-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="9c725-309">I åtgärdsfönstret, välj **Behovet av artikelplacering** du vill visa resultaten från kommandot **Efterfrågeprognoser**.</span><span class="sxs-lookup"><span data-stu-id="9c725-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="9c725-310">Raderna i artikelplaceringsbehov kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="9c725-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="9c725-311">Du kan ta bort en rad, lägga till en ny rad eller redigera raddetaljerna.</span><span class="sxs-lookup"><span data-stu-id="9c725-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="9c725-312">Du kan redigera efter frågan manuellt eller också kan du importera den från ett externt system genom att använda datahantering.</span><span class="sxs-lookup"><span data-stu-id="9c725-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="9c725-313">Det som finns i artikelplaceringsbehov kommer att användas i nästa steg, oavsett var det kom från.</span><span class="sxs-lookup"><span data-stu-id="9c725-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="9c725-314">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="9c725-314">Locate demand</span></span>

<span data-ttu-id="9c725-315">Efter att efterfrågan har genererats måste du använda kommandot **Hitta efterfrågan** för att generera den *Artikelplaceringsplanen*.</span><span class="sxs-lookup"><span data-stu-id="9c725-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="9c725-316">Välj **Hitta efterfrågan** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9c725-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="9c725-317">Artikelplaceringsprocessen körs.</span><span class="sxs-lookup"><span data-stu-id="9c725-317">The slotting process runs.</span></span> <span data-ttu-id="9c725-318">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9c725-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="9c725-319">Plan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="9c725-319">Slotting plan</span></span>

<span data-ttu-id="9c725-320">Artikelplaceringsplanen visar platsen som varje artikel/kvantitet har tilldelats för, om spill användes, om det är fråga om att arbeta med rader och vilka mallrader som användes.</span><span class="sxs-lookup"><span data-stu-id="9c725-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="9c725-321">**Alla efterfrågan som inte kan skåras markeras i artikelplacering.**</span><span class="sxs-lookup"><span data-stu-id="9c725-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="9c725-322">I åtgärdsfönstret, välj **Artikelplaceringsplan** du vill visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="9c725-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="9c725-323">Skapa lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="9c725-323">Create replenishment</span></span>

<span data-ttu-id="9c725-324">När du har skapat en artikelplaceringsplan måste du skapa *lagerpåfyllningsarbete* baserat på planen.</span><span class="sxs-lookup"><span data-stu-id="9c725-324">After the slotting plan has been created, you must create *replenishment work* , based on the plan.</span></span>

- <span data-ttu-id="9c725-325">I åtgärdsfönstret, klicka på **Kör lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="9c725-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="9c725-326">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9c725-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="9c725-327">Det här meddelandet visar antalet huvuden som har skapats för versions-ID för arbete.</span><span class="sxs-lookup"><span data-stu-id="9c725-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="9c725-328">De platsdirektiv som kommer att användas identifieras utifrån den direktivkod som anges på varje rad i en mall.</span><span class="sxs-lookup"><span data-stu-id="9c725-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="9c725-329">Tips:</span><span class="sxs-lookup"><span data-stu-id="9c725-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="9c725-330">Ställ in automatisk artikelplacering</span><span class="sxs-lookup"><span data-stu-id="9c725-330">Set up automatic slotting</span></span>

<span data-ttu-id="9c725-331">När alla nödvändiga element är på plats kan du ställa in artikelplacering så att de körs automatiskt genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9c725-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="9c725-332">Gå till **Lagerstyrning \> Lagerpåfyllnad \> Köra artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="9c725-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="9c725-333">Ange de artikelplaceringssteg som ska köras.</span><span class="sxs-lookup"><span data-stu-id="9c725-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="9c725-334">Välj ett eller flera av följande artikelplaceringssteg:</span><span class="sxs-lookup"><span data-stu-id="9c725-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="9c725-335">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="9c725-335">Generate demand</span></span>
    - <span data-ttu-id="9c725-336">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="9c725-336">Locate demand</span></span>
    - <span data-ttu-id="9c725-337">Skapa lagerpåfyllnadsarbete</span><span class="sxs-lookup"><span data-stu-id="9c725-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c725-338">Artikelplaceringsstegen är progressiva.</span><span class="sxs-lookup"><span data-stu-id="9c725-338">The slotting steps are progressive.</span></span> <span data-ttu-id="9c725-339">Om du vill välja *Hitta efterfrågan* måste du först välja *Generera efterfrågan*.</span><span class="sxs-lookup"><span data-stu-id="9c725-339">If you want to select *Locate demand* , you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="9c725-340">Ange vilken artikelplaceringsmall som ska användas.</span><span class="sxs-lookup"><span data-stu-id="9c725-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="9c725-341">Ställ in upprepning så att körningen sker automatiskt om du vill.</span><span class="sxs-lookup"><span data-stu-id="9c725-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="9c725-342">I övningarna i scenariot ska du **inte** ställa in automatisk artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="9c725-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
