---
title: Artikelplacering för lagerställe
description: Den här ämnet innehåller information om artikelplacering för lagerställe. Artikelplacering för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status beställt, reserverat eller frisläppt. Det underlättar för lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
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
ms.openlocfilehash: 31b86837735ca16610a1d304eab611b12a6aceeb
ms.sourcegitcommit: be4b9d557511bbb43e71a93f2c3b23b5f1a4669d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/24/2020
ms.locfileid: "4627759"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="a2a72-105">Artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="a2a72-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2a72-106">Flera funktioner artikelplacering för distributionslager är tillgängliga för att hjälpa till lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="a2a72-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="a2a72-107">*Funktioner för artikelplacering* för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status *beställt*, *reserverat* eller *frisläppt*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="a2a72-108">Genererade behov kan sedan tillämpas på platser som ska användas för plockning, baserat på kvantitet, enhet, fysiska dimensioner, fasta platser och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="a2a72-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="a2a72-109">När artikelplaceringsplanen har fastställts kan du skapa ett lagerpåfyllnadsarbete för att hämta en lämplig lagermängd till varje plats.</span><span class="sxs-lookup"><span data-stu-id="a2a72-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="a2a72-110">Funktionen *Artikelplacering för distributionslager för överföringsorder* kan lagerchefer fylla på plockplatser baserat på efterfrågan från överföringsorder som ännu inte släppts till lagret.</span><span class="sxs-lookup"><span data-stu-id="a2a72-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="a2a72-111">Det säkerställer att plockplatser innehåller alla artiklar som krävs för överföringsorder när de har frisläppts till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a2a72-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="a2a72-112">Denna funktion kräver att du även aktiverar funktionen för funktionen *Artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="a2a72-113">Funktionen *förbättrad allokering av artikelplacering för distributionslager* lägger till ett alternativ för de mallrader som används i funktionen *artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="a2a72-114">Alternativet gör det möjligt att överväga befintlig lagerbehållning på en målplats.</span><span class="sxs-lookup"><span data-stu-id="a2a72-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="a2a72-115">Därför kan färre påfyllningar genereras för artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="a2a72-116">Funktionen *förbättrad allokering av artikelplacering för distributionslager* kräver att du även aktiverar funktionen *artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="a2a72-117">Den kan också användas tillsammans med funktionen *Artikelplacering för distributionslager för överföringsorder*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="a2a72-118">Aktivera funktionen artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="a2a72-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="a2a72-119">Innan du kan använda dessa funktioner måste de aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="a2a72-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="a2a72-120">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs.</span><span class="sxs-lookup"><span data-stu-id="a2a72-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="a2a72-121">Aktivera följande funktioner om det behövs:</span><span class="sxs-lookup"><span data-stu-id="a2a72-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="a2a72-122">Lagerställets tilldelningsfunktion</span><span class="sxs-lookup"><span data-stu-id="a2a72-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="a2a72-123">Artikelplacering i distributionslager för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="a2a72-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a2a72-124">Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="a2a72-125">Förbättringar av allokering av artikelplacering i distributionslager</span><span class="sxs-lookup"><span data-stu-id="a2a72-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a2a72-126">Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="a2a72-127">Ställ in artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="a2a72-127">Set up warehouse slotting</span></span>

<span data-ttu-id="a2a72-128">Om du vill använda artikelplacering för lagerställe måste du ställa följande element i systemet:</span><span class="sxs-lookup"><span data-stu-id="a2a72-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="a2a72-129">Måttenhetsnivåer för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="a2a72-130">Direktivkoder</span><span class="sxs-lookup"><span data-stu-id="a2a72-130">Directive codes</span></span>
- <span data-ttu-id="a2a72-131">Artikelplaceringsmallar</span><span class="sxs-lookup"><span data-stu-id="a2a72-131">Slotting templates</span></span>
- <span data-ttu-id="a2a72-132">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="a2a72-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="a2a72-133">Skapa måttenhetsnivåer för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="a2a72-134">Enhetsmåttnivåer gör att flera måttenheter kan grupperas tillsammans i en artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="a2a72-135">Om t.ex. flera storlekar av lådorna har valts från samma låda, kan en nivå skapas för alla storlekar.</span><span class="sxs-lookup"><span data-stu-id="a2a72-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="a2a72-136">**En rad måste skapas för varje måttenhet som ska ingå i nivån.**</span><span class="sxs-lookup"><span data-stu-id="a2a72-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="a2a72-137">Gå till **Lagerstyrning \> Inställningar \> Påfyllning \> Måttenhetsnivåer för artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="a2a72-138">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-138">Select **New**.</span></span>
1. <span data-ttu-id="a2a72-139">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="a2a72-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="a2a72-140">**Enhetsnivå:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="a2a72-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="a2a72-141">**Beskrivning:** *Varje låda, lastpall*</span><span class="sxs-lookup"><span data-stu-id="a2a72-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="a2a72-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-142">Select **Save**.</span></span>
1. <span data-ttu-id="a2a72-143">På snabbfliken **Måttenheter** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a2a72-144">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-145">**Enhet:** *låda*</span><span class="sxs-lookup"><span data-stu-id="a2a72-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="a2a72-146">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="a2a72-147">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="a2a72-148">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="a2a72-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="a2a72-149">Välj **Ny** om du vill lägga till andra rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="a2a72-150">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-151">**Enhet:** *ea*</span><span class="sxs-lookup"><span data-stu-id="a2a72-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="a2a72-152">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="a2a72-153">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="a2a72-154">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="a2a72-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="a2a72-155">Välj **Ny** om du vill lägga till tredje rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="a2a72-156">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-157">**Enhet:** *PL*</span><span class="sxs-lookup"><span data-stu-id="a2a72-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="a2a72-158">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="a2a72-159">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="a2a72-160">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="a2a72-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="a2a72-161">Välj **Spara** för att spara nivån.</span><span class="sxs-lookup"><span data-stu-id="a2a72-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="a2a72-162">Skapa en direktivkod för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-162">Create a directive code for slotting</span></span>

<span data-ttu-id="a2a72-163">Du måste välja den direktivkod som ska associeras med en mall.</span><span class="sxs-lookup"><span data-stu-id="a2a72-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="a2a72-164">Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="a2a72-165">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a2a72-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a2a72-166">I fältet **Direktivkod**, ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="a2a72-167">I fältet **Beskrivning av direktivkod**, ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="a2a72-168">Ställ in artikelplaceringsmallar</span><span class="sxs-lookup"><span data-stu-id="a2a72-168">Set up slotting templates</span></span>

<span data-ttu-id="a2a72-169">Varje artikelplaceringsmall styr hur lagret tilldelas till platser för ett visst lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a2a72-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="a2a72-170">Varje mall måste innehålla en rad för varje artikelplaceringsspecifikation.</span><span class="sxs-lookup"><span data-stu-id="a2a72-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="a2a72-171">Använd procedurerna i det här avsnittet om du vill ställa in artikelplaceringsmallar.</span><span class="sxs-lookup"><span data-stu-id="a2a72-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="a2a72-172">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="a2a72-173">Skapa en ny mall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-173">Select **New** to create a template.</span></span>

<span data-ttu-id="a2a72-174">Sedan måste du ställa in mallhuvudet, artikelplaceringsspecifikation och platsdirektiven, enligt beskrivningen i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="a2a72-175">Inställningen för artikelplacering för överföringsorder liknar inställningen för artikelplacering för försäljningsorder, men **Efterfrågetyp** anges till *Överföringsorder* istället för *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="a2a72-176">Ställ in rubriken för en mall för att skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="a2a72-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="a2a72-177">Ange följande värden i mallens rubrik:</span><span class="sxs-lookup"><span data-stu-id="a2a72-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="a2a72-178">**Artikelplaceringsmall:** _61_</span><span class="sxs-lookup"><span data-stu-id="a2a72-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="a2a72-179">**Beskrivning:** _61_</span><span class="sxs-lookup"><span data-stu-id="a2a72-179">**Description:** _61_</span></span>
    - <span data-ttu-id="a2a72-180">**Efterfrågetyp:** *försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="a2a72-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="a2a72-181">För närvarande är *Försäljningsorder* och *Överföringsorder* de enda typer av efterfrågan som stöds.</span><span class="sxs-lookup"><span data-stu-id="a2a72-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="a2a72-182">Du kan bara välja *Överföringsorder* om funktionen *Artikelplacering i distributionslager för överföringsorder* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="a2a72-183">**Efterfrågestrategi:** _beställt_</span><span class="sxs-lookup"><span data-stu-id="a2a72-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="a2a72-184">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="a2a72-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="a2a72-185">**Beställt** – hela den beställda kvantiteten på försäljningsordern ska behandlas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="a2a72-186">**Reserverat** – endast försäljningsorderradens kvantitet som är reserverade (fysiska och beställda) ska betraktas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="a2a72-187">**Frisläppt** – den frisläppta kvantiteten ska behandlas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="a2a72-188">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="a2a72-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="a2a72-189">**Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="a2a72-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="a2a72-190">Du kan även ange en fråga för att begränsa omfattningen av den efterfrågan som utvärderas.</span><span class="sxs-lookup"><span data-stu-id="a2a72-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="a2a72-191">Ställa in en artikelplaceringsspecifikation för varje mall</span><span class="sxs-lookup"><span data-stu-id="a2a72-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="a2a72-192">För varje försäljningsordermall som du skapar lägger du till en rad för varje artikelplaceringsspecifikation genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="a2a72-193">På snabbfliken **Information artikelplaceringsspecifikation** välj **Ny** för att skapa en mallrad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="a2a72-194">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-195">**Sekvens:** _1_</span><span class="sxs-lookup"><span data-stu-id="a2a72-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="a2a72-196">**Beskrivning:** _Fast plats_</span><span class="sxs-lookup"><span data-stu-id="a2a72-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="a2a72-197">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="a2a72-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="a2a72-198">I det här fältet definieras den minsta kvantitet efter frågan som krävs för raden.</span><span class="sxs-lookup"><span data-stu-id="a2a72-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="a2a72-199">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="a2a72-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="a2a72-200">I det här fältet definieras den högsta kvantitet för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="a2a72-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="a2a72-201">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="a2a72-202">I det här fältet anges den måttenhet som lägsta och högsta kvantiteter refererar till.</span><span class="sxs-lookup"><span data-stu-id="a2a72-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="a2a72-203">**Måttenhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="a2a72-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="a2a72-204">I det här fältet definieras den enhetsnivå för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="a2a72-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="a2a72-205">(Mer information finns i avsnittet [Ange måttenhetsnivå för artikelplacering](#unit-tiers) tidigare i det här avsnittet.)</span><span class="sxs-lookup"><span data-stu-id="a2a72-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="a2a72-206">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="a2a72-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="a2a72-207">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="a2a72-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="a2a72-208">**Antag vara tom** – det här systemet ska anta att alla platser i plockområdet är tomma och inte ska kontrollera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="a2a72-209">**Överväg kvantitet** – Systemet bör kontrollera platserna i plockningsområdet för inventering och bör hoppa över alla platser som inte är tomma.</span><span class="sxs-lookup"><span data-stu-id="a2a72-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="a2a72-210">**Överväg lagerbehållning** – systemet bör kontrollera om det finns icke reserverade kvantiteter för artikeln på efterfrågeraden.</span><span class="sxs-lookup"><span data-stu-id="a2a72-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="a2a72-211">Om kvantiteten är tillräckligt stor för att kunna uppfylla minst en enhet av efterfrågeraden, reduceras den genererade artikelplaceringsposten med det tillgängliga beloppet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="a2a72-212">Om efter frågan t.ex. är 10 ärenden och ett ärende är i handen, kommer den efterfrågan att vara nio ärende.</span><span class="sxs-lookup"><span data-stu-id="a2a72-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="a2a72-213">Om efterfrågan är 10 ärenden och varje är i handen, kommer den efterfrågan att vara 10 ärenden.</span><span class="sxs-lookup"><span data-stu-id="a2a72-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="a2a72-214">Det här värdet är bara tillgängligt om funktionen *Förbättringar av allokering av artikelplacering i distributionslager* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="a2a72-215">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="a2a72-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="a2a72-216">I det här fältet definieras det platsdirektiv som används för att hitta plockplatsen för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="a2a72-217">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="a2a72-218">Det här fältet definierar det lagerställe som har placerats på om det inte går att hitta en plats för kvantiteten när raden bearbetas.</span><span class="sxs-lookup"><span data-stu-id="a2a72-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="a2a72-219">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="a2a72-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="a2a72-220">Om det här alternativet är inställt på *Ja*, kommer flyttningsarbetet att skapas för att ta ut lagret med lagerställen, men där inget har öppnats.</span><span class="sxs-lookup"><span data-stu-id="a2a72-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="a2a72-221">Mallen körs sedan igen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-221">The template is then run again.</span></span> <span data-ttu-id="a2a72-222">Den här gången ignoreras lagret på platserna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="a2a72-223">Den här funktionen fungerar bäst om fältet **Tilldela kortplatskriterier** är inställt på _Överväg kvantitet_.</span><span class="sxs-lookup"><span data-stu-id="a2a72-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="a2a72-224">**Användning av fast lagerplats:** _Endast fasta lagerplatser för produkten_</span><span class="sxs-lookup"><span data-stu-id="a2a72-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="a2a72-225">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="a2a72-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="a2a72-226">**Fasta och icke-fasta lagerplatser** – systemet ska inte begränsas till att bara använda fasta lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="a2a72-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="a2a72-227">**Endast fasta lagerplatser för produkten** – systemet ska endast kortas till platser som är fasta lagerplatser för produkten.</span><span class="sxs-lookup"><span data-stu-id="a2a72-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="a2a72-228">**Endast fasta lagerplatser för produktvarianten** – systemet ska endast kortas till platser som är fasta lagerplatser för produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="a2a72-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="a2a72-229">Om artikelplaceringsmallen innehåller minst en rad där fältet **Tilldela kortkriterier** anges *Överväg lagerbehållning*, minskningar är inte längre tillåtna för någon rad i mallen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="a2a72-230">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-230">Select **Save**.</span></span>
1. <span data-ttu-id="a2a72-231">Klicka på **Ny** för att skapa en andra mallrad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="a2a72-232">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-233">**Sekvens:** _2_</span><span class="sxs-lookup"><span data-stu-id="a2a72-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="a2a72-234">**Beskrivning:** _andra_</span><span class="sxs-lookup"><span data-stu-id="a2a72-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="a2a72-235">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="a2a72-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="a2a72-236">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="a2a72-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="a2a72-237">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="a2a72-238">**Enhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="a2a72-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="a2a72-239">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="a2a72-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="a2a72-240">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="a2a72-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="a2a72-241">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="a2a72-242">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="a2a72-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="a2a72-243">**Använda fasta lagerplatser:** _Fasta och ej fasta platser_</span><span class="sxs-lookup"><span data-stu-id="a2a72-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="a2a72-244">I frågan för den andra raden kommer du nu att ange de kriterier som används för att bestämma vilka platser som efter frågan för den raden kan avsättas till.</span><span class="sxs-lookup"><span data-stu-id="a2a72-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="a2a72-245">Välj raden där fältet **Sekvens** är inställt på *2*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="a2a72-246">Välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="a2a72-247">På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="a2a72-248">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-249">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="a2a72-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a2a72-250">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="a2a72-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a2a72-251">**Fält:** *platsprofil-ID*</span><span class="sxs-lookup"><span data-stu-id="a2a72-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="a2a72-252">**Kriterier:** *Plocka-06* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Plocka-06* - *Plockplats 6*.)</span><span class="sxs-lookup"><span data-stu-id="a2a72-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="a2a72-253">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="a2a72-254">Ställ in platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="a2a72-254">Set up location directives</span></span>

<span data-ttu-id="a2a72-255">Minst ett platsdirektiv måste ställas in för att stödja plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="a2a72-256">Använd procedurerna i det här avsnittet om du vill skapa ett nytt *platsdirektiv för påfyllnad* för plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="a2a72-257">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a2a72-258">I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *lagerpåfyllnad*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="a2a72-259">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a2a72-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a2a72-260">I rubriken för det nya platsdirektivet anger du i fältet **Namn** *61 plocka artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="a2a72-261">I fältet **Löpnummer** acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="a2a72-262">Konfigurera snabbfliken platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="a2a72-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="a2a72-263">Ange följande värden på snabbfliken **Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="a2a72-264">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="a2a72-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="a2a72-265">**Arbetstyp:** _plockning_</span><span class="sxs-lookup"><span data-stu-id="a2a72-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="a2a72-266">**Plats:** _6_</span><span class="sxs-lookup"><span data-stu-id="a2a72-266">**Site:** _6_</span></span>
    - <span data-ttu-id="a2a72-267">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="a2a72-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="a2a72-268">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="a2a72-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="a2a72-269">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a2a72-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="a2a72-270">Konfigurera snabbfliken Rader</span><span class="sxs-lookup"><span data-stu-id="a2a72-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="a2a72-271">På snabbfliken **Rader**, klicka på **Ny** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="a2a72-272">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="a2a72-273">**Från kvantitet:** _0_</span><span class="sxs-lookup"><span data-stu-id="a2a72-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="a2a72-274">**Till kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="a2a72-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="a2a72-275">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="a2a72-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="a2a72-276">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a2a72-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="a2a72-277">Konfigurera snabbfliken Platsdirektivåtgärder</span><span class="sxs-lookup"><span data-stu-id="a2a72-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="a2a72-278">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="a2a72-279">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="a2a72-279">On the new line, set the following values.</span></span> <span data-ttu-id="a2a72-280">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="a2a72-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="a2a72-281">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="a2a72-282">**Namn:** _Bulk_</span><span class="sxs-lookup"><span data-stu-id="a2a72-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="a2a72-283">**Strategi:** _ingen_</span><span class="sxs-lookup"><span data-stu-id="a2a72-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="a2a72-284">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="a2a72-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="a2a72-285">Välj **Spara** om du vill göra knappen **Redigera fråga** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a2a72-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="a2a72-286">Redigera frågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-286">Edit the query</span></span>

1. <span data-ttu-id="a2a72-287">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="a2a72-288">På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="a2a72-289">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-290">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="a2a72-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a2a72-291">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="a2a72-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a2a72-292">**Fält:** *zon-ID*</span><span class="sxs-lookup"><span data-stu-id="a2a72-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="a2a72-293">**Kriterier:** *Bulk* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Bulk*.)</span><span class="sxs-lookup"><span data-stu-id="a2a72-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="a2a72-294">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="a2a72-295">Scenario</span><span class="sxs-lookup"><span data-stu-id="a2a72-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="a2a72-296">Ställ in scenario</span><span class="sxs-lookup"><span data-stu-id="a2a72-296">Set up the scenario</span></span>

<span data-ttu-id="a2a72-297">I det här scenariot ska du använda de inbyggda exempeldata och skapa posterna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="a2a72-298">Använd exempeldata för USMF</span><span class="sxs-lookup"><span data-stu-id="a2a72-298">Use the USMF sample data</span></span>

<span data-ttu-id="a2a72-299">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="a2a72-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="a2a72-300">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="a2a72-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="a2a72-301">Skapa efterfrågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-301">Create demand</span></span>

<span data-ttu-id="a2a72-302">Skapa den efter frågan som du vill använda skåra på genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="a2a72-303">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="a2a72-304">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="a2a72-305">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-007_.</span><span class="sxs-lookup"><span data-stu-id="a2a72-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="a2a72-306">I fältet **Lagerställe**, välj _61_.</span><span class="sxs-lookup"><span data-stu-id="a2a72-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="a2a72-307">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-307">Select **OK**.</span></span>
1. <span data-ttu-id="a2a72-308">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="a2a72-308">The new sales order is opened.</span></span> <span data-ttu-id="a2a72-309">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a2a72-310">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-311">**Artikel:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="a2a72-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="a2a72-312">**Kvantitet:** _20_</span><span class="sxs-lookup"><span data-stu-id="a2a72-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="a2a72-313">Välj **Lägg till rad** för att lägga till en nya rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="a2a72-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="a2a72-314">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="a2a72-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="a2a72-315">**Kvantitet:** _8_</span><span class="sxs-lookup"><span data-stu-id="a2a72-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="a2a72-316">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-316">Select **Save**.</span></span>
1. <span data-ttu-id="a2a72-317">Skapa en andra försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="a2a72-318">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-008_.</span><span class="sxs-lookup"><span data-stu-id="a2a72-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="a2a72-319">I fältet **Lagerställe**, välj _61_.</span><span class="sxs-lookup"><span data-stu-id="a2a72-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="a2a72-320">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="a2a72-320">The new sales order is opened.</span></span> <span data-ttu-id="a2a72-321">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a2a72-322">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="a2a72-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="a2a72-323">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="a2a72-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="a2a72-324">**Kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="a2a72-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="a2a72-325">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="a2a72-326">Gå igenom ett vanligt artikelplaceringsscenario</span><span class="sxs-lookup"><span data-stu-id="a2a72-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="a2a72-327">När alla nödvändiga element är på rätt sätt, så som beskrivs i föregående avsnitt, är du redo att testa funktionen genom att arbeta igenom varje övning i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="a2a72-328">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-328">Generate demand</span></span>

1. <span data-ttu-id="a2a72-329">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar** och välj artikelplaceringsmallen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a2a72-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="a2a72-330">Välj **efterfrågeprognoser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a2a72-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="a2a72-331">Det här kommandot utvärderar alla efter frågan i systemet och matchar den i artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="a2a72-332">Den totala efter frågan på alla order konsolideras sedan på en rad per kvantitet/måttenhet.</span><span class="sxs-lookup"><span data-stu-id="a2a72-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="a2a72-333">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a2a72-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="a2a72-334">Efterfrågan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-334">Slotting demand</span></span>

<span data-ttu-id="a2a72-335">*Behovet av artikelplacering* visar resultatet av efterfrågegenereringen, baserat på inställningarna för den artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="a2a72-336">I åtgärdsfönstret, välj **Behovet av artikelplacering** du vill visa resultaten från kommandot **Efterfrågeprognoser**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="a2a72-337">Raderna i artikelplaceringsbehov kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="a2a72-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="a2a72-338">Du kan ta bort en rad, lägga till en ny rad eller redigera raddetaljerna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="a2a72-339">Du kan redigera efter frågan manuellt eller också kan du importera den från ett externt system genom att använda datahantering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="a2a72-340">Det som finns i artikelplaceringsbehov kommer att användas i nästa steg, oavsett var det kom från.</span><span class="sxs-lookup"><span data-stu-id="a2a72-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="a2a72-341">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-341">Locate demand</span></span>

<span data-ttu-id="a2a72-342">Efter att efterfrågan har genererats måste du använda kommandot **Hitta efterfrågan** för att generera den *Artikelplaceringsplanen*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="a2a72-343">Välj **Hitta efterfrågan** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a2a72-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="a2a72-344">Artikelplaceringsprocessen körs.</span><span class="sxs-lookup"><span data-stu-id="a2a72-344">The slotting process runs.</span></span> <span data-ttu-id="a2a72-345">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a2a72-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="a2a72-346">Plan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-346">Slotting plan</span></span>

<span data-ttu-id="a2a72-347">Artikelplaceringsplanen visar platsen som varje artikel/kvantitet har tilldelats för, om spill användes, om det är fråga om att arbeta med rader och vilka mallrader som användes.</span><span class="sxs-lookup"><span data-stu-id="a2a72-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="a2a72-348">*Alla efterfrågan som inte kan skåras markeras i artikelplacering.*</span><span class="sxs-lookup"><span data-stu-id="a2a72-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="a2a72-349">I åtgärdsfönstret, välj **Artikelplaceringsplan** du vill visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="a2a72-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="a2a72-350">Processen **Generera efterfrågan**, **Hitta efterfrågan** och **Kör lagerpåfyllnad** processer i ett begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="a2a72-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="a2a72-351">(Dessa processer är tillgängliga från åtgärdsfönstret på sidan **artikelplaceringsmallar**).</span><span class="sxs-lookup"><span data-stu-id="a2a72-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="a2a72-352">Processer **Generera efterfrågan**, **Lokalisera efterfrågan** och **Kör lagerpåfyllnad** processer har ett lås för att säkerställa att de inte kan utlösas samtidigt.</span><span class="sxs-lookup"><span data-stu-id="a2a72-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="a2a72-353">I annat fall kan data som används tas bort.</span><span class="sxs-lookup"><span data-stu-id="a2a72-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="a2a72-354">Processerna **Generera efterfrågan** och **Lokalisera efterfrågan** visar en varning om körningen inte genererade poster, eller om det saknas information om posterna.</span><span class="sxs-lookup"><span data-stu-id="a2a72-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="a2a72-355">När du väljer en **Plan för artikelplacering** har inte sidan knapparna **Ny**, **Redigera** eller **Ta bort** i åtgärdsfönstret eftersom datakällan inte kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="a2a72-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="a2a72-356">När du väljer **Kör påfyllnad**, validerar systemet den valda platsens mall och processer.</span><span class="sxs-lookup"><span data-stu-id="a2a72-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="a2a72-357">Skapa lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="a2a72-357">Create replenishment</span></span>

<span data-ttu-id="a2a72-358">När du har skapat en artikelplaceringsplan måste du skapa *lagerpåfyllningsarbete* baserat på planen.</span><span class="sxs-lookup"><span data-stu-id="a2a72-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="a2a72-359">I åtgärdsfönstret, klicka på **Kör lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="a2a72-360">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a2a72-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="a2a72-361">Det här meddelandet visar antalet huvuden som har skapats för versions-ID för arbete.</span><span class="sxs-lookup"><span data-stu-id="a2a72-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="a2a72-362">De platsdirektiv som kommer att användas identifieras utifrån den direktivkod som anges på varje rad i en mall.</span><span class="sxs-lookup"><span data-stu-id="a2a72-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="a2a72-363">Tips:</span><span class="sxs-lookup"><span data-stu-id="a2a72-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="a2a72-364">Ställ in automatisk artikelplacering</span><span class="sxs-lookup"><span data-stu-id="a2a72-364">Set up automatic slotting</span></span>

<span data-ttu-id="a2a72-365">När alla nödvändiga element är på plats kan du ställa in artikelplacering så att de körs automatiskt genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a2a72-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="a2a72-366">Gå till **Lagerstyrning \> Lagerpåfyllnad \> Köra artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="a2a72-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="a2a72-367">Ange de artikelplaceringssteg som ska köras.</span><span class="sxs-lookup"><span data-stu-id="a2a72-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="a2a72-368">Välj ett eller flera av följande artikelplaceringssteg:</span><span class="sxs-lookup"><span data-stu-id="a2a72-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="a2a72-369">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-369">Generate demand</span></span>
    - <span data-ttu-id="a2a72-370">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="a2a72-370">Locate demand</span></span>
    - <span data-ttu-id="a2a72-371">Skapa lagerpåfyllnadsarbete</span><span class="sxs-lookup"><span data-stu-id="a2a72-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2a72-372">Artikelplaceringsstegen är progressiva.</span><span class="sxs-lookup"><span data-stu-id="a2a72-372">The slotting steps are progressive.</span></span> <span data-ttu-id="a2a72-373">Om du vill välja *Hitta efterfrågan* måste du först välja *Generera efterfrågan*.</span><span class="sxs-lookup"><span data-stu-id="a2a72-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="a2a72-374">Ange vilken artikelplaceringsmall som ska användas.</span><span class="sxs-lookup"><span data-stu-id="a2a72-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="a2a72-375">Ställ in upprepning så att körningen sker automatiskt om du vill.</span><span class="sxs-lookup"><span data-stu-id="a2a72-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="a2a72-376">I övningarna i scenariot ska du **inte** ställa in automatisk artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="a2a72-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
