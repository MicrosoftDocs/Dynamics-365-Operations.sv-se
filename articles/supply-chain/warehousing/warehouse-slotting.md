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
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fb39daba393944471ee5d412b1eb61754843926f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993763"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="51b89-105">Artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="51b89-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51b89-106">Flera funktioner artikelplacering för distributionslager är tillgängliga för att hjälpa till lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="51b89-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="51b89-107">*Funktioner för artikelplacering* för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status *beställt*, *reserverat* eller *frisläppt*.</span><span class="sxs-lookup"><span data-stu-id="51b89-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="51b89-108">Genererade behov kan sedan tillämpas på platser som ska användas för plockning, baserat på kvantitet, enhet, fysiska dimensioner, fasta platser och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="51b89-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="51b89-109">När artikelplaceringsplanen har fastställts kan du skapa ett lagerpåfyllnadsarbete för att hämta en lämplig lagermängd till varje plats.</span><span class="sxs-lookup"><span data-stu-id="51b89-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="51b89-110">Funktionen *Artikelplacering för distributionslager för överföringsorder* kan lagerchefer fylla på plockplatser baserat på efterfrågan från överföringsorder som ännu inte släppts till lagret.</span><span class="sxs-lookup"><span data-stu-id="51b89-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="51b89-111">Det säkerställer att plockplatser innehåller alla artiklar som krävs för överföringsorder när de har frisläppts till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="51b89-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="51b89-112">Denna funktion kräver att du även aktiverar funktionen för funktionen *Artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="51b89-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="51b89-113">Funktionen *förbättrad allokering av artikelplacering för distributionslager* lägger till ett alternativ för de mallrader som används i funktionen *artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="51b89-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="51b89-114">Alternativet gör det möjligt att överväga befintlig lagerbehållning på en målplats.</span><span class="sxs-lookup"><span data-stu-id="51b89-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="51b89-115">Därför kan färre påfyllningar genereras för artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="51b89-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="51b89-116">Funktionen *förbättrad allokering av artikelplacering för distributionslager* kräver att du även aktiverar funktionen *artikelplacering för distributionslager*.</span><span class="sxs-lookup"><span data-stu-id="51b89-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="51b89-117">Den kan också användas tillsammans med funktionen *Artikelplacering för distributionslager för överföringsorder*.</span><span class="sxs-lookup"><span data-stu-id="51b89-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="51b89-118">Aktivera funktionen artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="51b89-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="51b89-119">Innan du kan använda dessa funktioner måste de aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="51b89-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="51b89-120">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs.</span><span class="sxs-lookup"><span data-stu-id="51b89-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="51b89-121">Aktivera följande funktioner om det behövs:</span><span class="sxs-lookup"><span data-stu-id="51b89-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="51b89-122">Lagerställets tilldelningsfunktion</span><span class="sxs-lookup"><span data-stu-id="51b89-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="51b89-123">Artikelplacering i distributionslager för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="51b89-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="51b89-124">Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="51b89-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="51b89-125">Förbättringar av allokering av artikelplacering i distributionslager</span><span class="sxs-lookup"><span data-stu-id="51b89-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="51b89-126">Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="51b89-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="51b89-127">Ställ in artikelplacering för lagerställe</span><span class="sxs-lookup"><span data-stu-id="51b89-127">Set up warehouse slotting</span></span>

<span data-ttu-id="51b89-128">Om du vill använda artikelplacering för lagerställe måste du ställa följande element i systemet:</span><span class="sxs-lookup"><span data-stu-id="51b89-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="51b89-129">Måttenhetsnivåer för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="51b89-130">Direktivkoder</span><span class="sxs-lookup"><span data-stu-id="51b89-130">Directive codes</span></span>
- <span data-ttu-id="51b89-131">Artikelplaceringsmallar</span><span class="sxs-lookup"><span data-stu-id="51b89-131">Slotting templates</span></span>
- <span data-ttu-id="51b89-132">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="51b89-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="51b89-133">Skapa måttenhetsnivåer för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="51b89-134">Enhetsmåttnivåer gör att flera måttenheter kan grupperas tillsammans i en artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="51b89-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="51b89-135">Om t.ex. flera storlekar av lådorna har valts från samma låda, kan en nivå skapas för alla storlekar.</span><span class="sxs-lookup"><span data-stu-id="51b89-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="51b89-136">**En rad måste skapas för varje måttenhet som ska ingå i nivån.**</span><span class="sxs-lookup"><span data-stu-id="51b89-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="51b89-137">Gå till **Lagerstyrning \> Inställningar \> Påfyllning \> Måttenhetsnivåer för artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="51b89-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="51b89-138">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51b89-138">Select **New**.</span></span>
1. <span data-ttu-id="51b89-139">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="51b89-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="51b89-140">**Enhetsnivå:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="51b89-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="51b89-141">**Beskrivning:** *Varje låda, lastpall*</span><span class="sxs-lookup"><span data-stu-id="51b89-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="51b89-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51b89-142">Select **Save**.</span></span>
1. <span data-ttu-id="51b89-143">På snabbfliken **Måttenheter** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="51b89-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="51b89-144">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-145">**Enhet:** *låda*</span><span class="sxs-lookup"><span data-stu-id="51b89-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="51b89-146">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="51b89-147">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="51b89-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="51b89-148">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="51b89-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="51b89-149">Välj **Ny** om du vill lägga till andra rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="51b89-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="51b89-150">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-151">**Enhet:** *ea*</span><span class="sxs-lookup"><span data-stu-id="51b89-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="51b89-152">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="51b89-153">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="51b89-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="51b89-154">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="51b89-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="51b89-155">Välj **Ny** om du vill lägga till tredje rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="51b89-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="51b89-156">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-157">**Enhet:** *PL*</span><span class="sxs-lookup"><span data-stu-id="51b89-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="51b89-158">**Beskrivning:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="51b89-159">Den fylls i automatiskt när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="51b89-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="51b89-160">**Enhetsklass:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="51b89-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="51b89-161">Välj **Spara** för att spara nivån.</span><span class="sxs-lookup"><span data-stu-id="51b89-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="51b89-162">Skapa en direktivkod för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-162">Create a directive code for slotting</span></span>

<span data-ttu-id="51b89-163">Du måste välja den direktivkod som ska associeras med en mall.</span><span class="sxs-lookup"><span data-stu-id="51b89-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="51b89-164">Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.</span><span class="sxs-lookup"><span data-stu-id="51b89-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="51b89-165">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="51b89-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="51b89-166">I fältet **Direktivkod**, ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="51b89-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="51b89-167">I fältet **Beskrivning av direktivkod**, ange *Artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="51b89-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="51b89-168">Ställ in artikelplaceringsmallar</span><span class="sxs-lookup"><span data-stu-id="51b89-168">Set up slotting templates</span></span>

<span data-ttu-id="51b89-169">Varje artikelplaceringsmall styr hur lagret tilldelas till platser för ett visst lagerställe.</span><span class="sxs-lookup"><span data-stu-id="51b89-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="51b89-170">Varje mall måste innehålla en rad för varje artikelplaceringsspecifikation.</span><span class="sxs-lookup"><span data-stu-id="51b89-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="51b89-171">Använd procedurerna i det här avsnittet om du vill ställa in artikelplaceringsmallar.</span><span class="sxs-lookup"><span data-stu-id="51b89-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="51b89-172">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar**.</span><span class="sxs-lookup"><span data-stu-id="51b89-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="51b89-173">Skapa en ny mall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="51b89-173">Select **New** to create a template.</span></span>

<span data-ttu-id="51b89-174">Sedan måste du ställa in mallhuvudet, artikelplaceringsspecifikation och platsdirektiven, enligt beskrivningen i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="51b89-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="51b89-175">Inställningen för artikelplacering för överföringsorder liknar inställningen för artikelplacering för försäljningsorder, men **Efterfrågetyp** anges till *Överföringsorder* istället för *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="51b89-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="51b89-176">Ställ in rubriken för en mall för att skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="51b89-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="51b89-177">Ange följande värden i mallens rubrik:</span><span class="sxs-lookup"><span data-stu-id="51b89-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="51b89-178">**Artikelplaceringsmall:** _61_</span><span class="sxs-lookup"><span data-stu-id="51b89-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="51b89-179">**Beskrivning:** _61_</span><span class="sxs-lookup"><span data-stu-id="51b89-179">**Description:** _61_</span></span>
    - <span data-ttu-id="51b89-180">**Efterfrågetyp:** *försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="51b89-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="51b89-181">För närvarande är *Försäljningsorder* och *Överföringsorder* de enda typer av efterfrågan som stöds.</span><span class="sxs-lookup"><span data-stu-id="51b89-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="51b89-182">Du kan bara välja *Överföringsorder* om funktionen *Artikelplacering i distributionslager för överföringsorder* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="51b89-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="51b89-183">**Efterfrågestrategi:** _beställt_</span><span class="sxs-lookup"><span data-stu-id="51b89-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="51b89-184">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="51b89-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="51b89-185">**Beställt** – hela den beställda kvantiteten på försäljningsordern ska behandlas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="51b89-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="51b89-186">**Reserverat** – endast försäljningsorderradens kvantitet som är reserverade (fysiska och beställda) ska betraktas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="51b89-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="51b89-187">**Frisläppt** – den frisläppta kvantiteten ska behandlas som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="51b89-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="51b89-188">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="51b89-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="51b89-189">**Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="51b89-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="51b89-190">Du kan även ange en fråga för att begränsa omfattningen av den efterfrågan som utvärderas.</span><span class="sxs-lookup"><span data-stu-id="51b89-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="51b89-191">Ställa in en artikelplaceringsspecifikation för varje mall</span><span class="sxs-lookup"><span data-stu-id="51b89-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="51b89-192">För varje försäljningsordermall som du skapar lägger du till en rad för varje artikelplaceringsspecifikation genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="51b89-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="51b89-193">På snabbfliken **Information artikelplaceringsspecifikation** välj **Ny** för att skapa en mallrad.</span><span class="sxs-lookup"><span data-stu-id="51b89-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="51b89-194">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-195">**Sekvens:** _1_</span><span class="sxs-lookup"><span data-stu-id="51b89-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="51b89-196">**Beskrivning:** _Fast plats_</span><span class="sxs-lookup"><span data-stu-id="51b89-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="51b89-197">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="51b89-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="51b89-198">I det här fältet definieras den minsta kvantitet efter frågan som krävs för raden.</span><span class="sxs-lookup"><span data-stu-id="51b89-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="51b89-199">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="51b89-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="51b89-200">I det här fältet definieras den högsta kvantitet för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="51b89-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="51b89-201">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="51b89-202">I det här fältet anges den måttenhet som lägsta och högsta kvantiteter refererar till.</span><span class="sxs-lookup"><span data-stu-id="51b89-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="51b89-203">**Måttenhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="51b89-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="51b89-204">I det här fältet definieras den enhetsnivå för efterfrågan som är giltig för raden.</span><span class="sxs-lookup"><span data-stu-id="51b89-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="51b89-205">(Mer information finns i avsnittet [Ange måttenhetsnivå för artikelplacering](#unit-tiers) tidigare i det här avsnittet.)</span><span class="sxs-lookup"><span data-stu-id="51b89-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="51b89-206">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="51b89-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="51b89-207">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="51b89-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="51b89-208">**Antag vara tom** – det här systemet ska anta att alla platser i plockområdet är tomma och inte ska kontrollera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="51b89-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="51b89-209">**Överväg kvantitet** – Systemet bör kontrollera platserna i plockningsområdet för inventering och bör hoppa över alla platser som inte är tomma.</span><span class="sxs-lookup"><span data-stu-id="51b89-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="51b89-210">**Överväg lagerbehållning** – systemet bör kontrollera om det finns icke reserverade kvantiteter för artikeln på efterfrågeraden.</span><span class="sxs-lookup"><span data-stu-id="51b89-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="51b89-211">Om kvantiteten är tillräckligt stor för att kunna uppfylla minst en enhet av efterfrågeraden, reduceras den genererade artikelplaceringsposten med det tillgängliga beloppet.</span><span class="sxs-lookup"><span data-stu-id="51b89-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="51b89-212">Om efter frågan t.ex. är 10 ärenden och ett ärende är i handen, kommer den efterfrågan att vara nio ärende.</span><span class="sxs-lookup"><span data-stu-id="51b89-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="51b89-213">Om efterfrågan är 10 ärenden och varje är i handen, kommer den efterfrågan att vara 10 ärenden.</span><span class="sxs-lookup"><span data-stu-id="51b89-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="51b89-214">Det här värdet är bara tillgängligt om funktionen *Förbättringar av allokering av artikelplacering i distributionslager* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="51b89-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="51b89-215">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="51b89-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="51b89-216">I det här fältet definieras det platsdirektiv som används för att hitta plockplatsen för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="51b89-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="51b89-217">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="51b89-218">Det här fältet definierar det lagerställe som har placerats på om det inte går att hitta en plats för kvantiteten när raden bearbetas.</span><span class="sxs-lookup"><span data-stu-id="51b89-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="51b89-219">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="51b89-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="51b89-220">Om det här alternativet är inställt på *Ja*, kommer flyttningsarbetet att skapas för att ta ut lagret med lagerställen, men där inget har öppnats.</span><span class="sxs-lookup"><span data-stu-id="51b89-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="51b89-221">Mallen körs sedan igen.</span><span class="sxs-lookup"><span data-stu-id="51b89-221">The template is then run again.</span></span> <span data-ttu-id="51b89-222">Den här gången ignoreras lagret på platserna.</span><span class="sxs-lookup"><span data-stu-id="51b89-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="51b89-223">Den här funktionen fungerar bäst om fältet **Tilldela kortplatskriterier** är inställt på _Överväg kvantitet_.</span><span class="sxs-lookup"><span data-stu-id="51b89-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="51b89-224">**Användning av fast lagerplats:** _Endast fasta lagerplatser för produkten_</span><span class="sxs-lookup"><span data-stu-id="51b89-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="51b89-225">Följande värden finns i detta fält:</span><span class="sxs-lookup"><span data-stu-id="51b89-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="51b89-226">**Fasta och icke-fasta lagerplatser** – systemet ska inte begränsas till att bara använda fasta lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="51b89-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="51b89-227">**Endast fasta lagerplatser för produkten** – systemet ska endast kortas till platser som är fasta lagerplatser för produkten.</span><span class="sxs-lookup"><span data-stu-id="51b89-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="51b89-228">**Endast fasta lagerplatser för produktvarianten** – systemet ska endast kortas till platser som är fasta lagerplatser för produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="51b89-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="51b89-229">Om artikelplaceringsmallen innehåller minst en rad där fältet **Tilldela kortkriterier** anges *Överväg lagerbehållning*, minskningar är inte längre tillåtna för någon rad i mallen.</span><span class="sxs-lookup"><span data-stu-id="51b89-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="51b89-230">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51b89-230">Select **Save**.</span></span>
1. <span data-ttu-id="51b89-231">Klicka på **Ny** för att skapa en andra mallrad.</span><span class="sxs-lookup"><span data-stu-id="51b89-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="51b89-232">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-233">**Sekvens:** _2_</span><span class="sxs-lookup"><span data-stu-id="51b89-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="51b89-234">**Beskrivning:** _andra_</span><span class="sxs-lookup"><span data-stu-id="51b89-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="51b89-235">**Minsta kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="51b89-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="51b89-236">**Högsta kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="51b89-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="51b89-237">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="51b89-238">**Enhetsnivå:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="51b89-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="51b89-239">**Tilldela kortkriterier:** _Överväg kvantitet_</span><span class="sxs-lookup"><span data-stu-id="51b89-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="51b89-240">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="51b89-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="51b89-241">**Spillplats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="51b89-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="51b89-242">**Tillåt låt upp:** _Ja_</span><span class="sxs-lookup"><span data-stu-id="51b89-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="51b89-243">**Använda fasta lagerplatser:** _Fasta och ej fasta platser_</span><span class="sxs-lookup"><span data-stu-id="51b89-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="51b89-244">I frågan för den andra raden kommer du nu att ange de kriterier som används för att bestämma vilka platser som efter frågan för den raden kan avsättas till.</span><span class="sxs-lookup"><span data-stu-id="51b89-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="51b89-245">Välj raden där fältet **Sekvens** är inställt på *2*.</span><span class="sxs-lookup"><span data-stu-id="51b89-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="51b89-246">Välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="51b89-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="51b89-247">På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="51b89-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="51b89-248">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-249">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="51b89-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="51b89-250">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="51b89-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="51b89-251">**Fält:** *platsprofil-ID*</span><span class="sxs-lookup"><span data-stu-id="51b89-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="51b89-252">**Kriterier:** *Plocka-06* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Plocka-06* - *Plockplats 6*.)</span><span class="sxs-lookup"><span data-stu-id="51b89-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="51b89-253">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="51b89-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="51b89-254">Ställ in platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="51b89-254">Set up location directives</span></span>

<span data-ttu-id="51b89-255">Minst ett platsdirektiv måste ställas in för att stödja plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="51b89-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="51b89-256">Använd procedurerna i det här avsnittet om du vill skapa ett nytt *platsdirektiv för påfyllnad* för plockning av artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="51b89-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="51b89-257">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="51b89-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="51b89-258">I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *lagerpåfyllnad*.</span><span class="sxs-lookup"><span data-stu-id="51b89-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="51b89-259">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="51b89-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="51b89-260">I rubriken för det nya platsdirektivet anger du i fältet **Namn** *61 plocka artikelplacering*.</span><span class="sxs-lookup"><span data-stu-id="51b89-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="51b89-261">I fältet **Löpnummer** acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="51b89-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="51b89-262">Konfigurera snabbfliken platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="51b89-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="51b89-263">Ange följande värden på snabbfliken **Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="51b89-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="51b89-264">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="51b89-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="51b89-265">**Arbetstyp:** _plockning_</span><span class="sxs-lookup"><span data-stu-id="51b89-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="51b89-266">**Plats:** _6_</span><span class="sxs-lookup"><span data-stu-id="51b89-266">**Site:** _6_</span></span>
    - <span data-ttu-id="51b89-267">**Lagerställe:** _61_</span><span class="sxs-lookup"><span data-stu-id="51b89-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="51b89-268">**Direktiv kod:** _Artikelplacering_</span><span class="sxs-lookup"><span data-stu-id="51b89-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="51b89-269">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="51b89-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="51b89-270">Konfigurera snabbfliken Rader</span><span class="sxs-lookup"><span data-stu-id="51b89-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="51b89-271">På snabbfliken **Rader**, klicka på **Ny** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="51b89-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="51b89-272">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="51b89-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="51b89-273">**Från kvantitet:** _0_</span><span class="sxs-lookup"><span data-stu-id="51b89-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="51b89-274">**Till kvantitet:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="51b89-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="51b89-275">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="51b89-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="51b89-276">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="51b89-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="51b89-277">Konfigurera snabbfliken Platsdirektivåtgärder</span><span class="sxs-lookup"><span data-stu-id="51b89-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="51b89-278">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="51b89-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="51b89-279">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="51b89-279">On the new line, set the following values.</span></span> <span data-ttu-id="51b89-280">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="51b89-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="51b89-281">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="51b89-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="51b89-282">**Namn:** _Bulk_</span><span class="sxs-lookup"><span data-stu-id="51b89-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="51b89-283">**Strategi:** _ingen_</span><span class="sxs-lookup"><span data-stu-id="51b89-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="51b89-284">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="51b89-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="51b89-285">Välj **Spara** om du vill göra knappen **Redigera fråga** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="51b89-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="51b89-286">Redigera frågan</span><span class="sxs-lookup"><span data-stu-id="51b89-286">Edit the query</span></span>

1. <span data-ttu-id="51b89-287">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="51b89-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="51b89-288">På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="51b89-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="51b89-289">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="51b89-290">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="51b89-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="51b89-291">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="51b89-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="51b89-292">**Fält:** *zon-ID*</span><span class="sxs-lookup"><span data-stu-id="51b89-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="51b89-293">**Kriterier:** *Bulk* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Bulk*.)</span><span class="sxs-lookup"><span data-stu-id="51b89-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="51b89-294">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="51b89-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="51b89-295">Scenario</span><span class="sxs-lookup"><span data-stu-id="51b89-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="51b89-296">Ställ in scenario</span><span class="sxs-lookup"><span data-stu-id="51b89-296">Set up the scenario</span></span>

<span data-ttu-id="51b89-297">I det här scenariot ska du använda de inbyggda exempeldata och skapa posterna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="51b89-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="51b89-298">Använd exempeldata för USMF</span><span class="sxs-lookup"><span data-stu-id="51b89-298">Use the USMF sample data</span></span>

<span data-ttu-id="51b89-299">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="51b89-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="51b89-300">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="51b89-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="51b89-301">Skapa efterfrågan</span><span class="sxs-lookup"><span data-stu-id="51b89-301">Create demand</span></span>

<span data-ttu-id="51b89-302">Skapa den efter frågan som du vill använda skåra på genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="51b89-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="51b89-303">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="51b89-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="51b89-304">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51b89-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="51b89-305">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-007_.</span><span class="sxs-lookup"><span data-stu-id="51b89-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="51b89-306">I fältet **Lagerställe**, välj _61_.</span><span class="sxs-lookup"><span data-stu-id="51b89-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="51b89-307">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="51b89-307">Select **OK**.</span></span>
1. <span data-ttu-id="51b89-308">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="51b89-308">The new sales order is opened.</span></span> <span data-ttu-id="51b89-309">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="51b89-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="51b89-310">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="51b89-311">**Artikel:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="51b89-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="51b89-312">**Kvantitet:** _20_</span><span class="sxs-lookup"><span data-stu-id="51b89-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="51b89-313">Välj **Lägg till rad** för att lägga till en nya rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="51b89-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="51b89-314">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="51b89-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="51b89-315">**Kvantitet:** _8_</span><span class="sxs-lookup"><span data-stu-id="51b89-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="51b89-316">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51b89-316">Select **Save**.</span></span>
1. <span data-ttu-id="51b89-317">Skapa en andra försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51b89-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="51b89-318">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-008_.</span><span class="sxs-lookup"><span data-stu-id="51b89-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="51b89-319">I fältet **Lagerställe**, välj _61_.</span><span class="sxs-lookup"><span data-stu-id="51b89-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="51b89-320">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="51b89-320">The new sales order is opened.</span></span> <span data-ttu-id="51b89-321">Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="51b89-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="51b89-322">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="51b89-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="51b89-323">**Artikel:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="51b89-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="51b89-324">**Kvantitet:** _1_</span><span class="sxs-lookup"><span data-stu-id="51b89-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="51b89-325">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51b89-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="51b89-326">Gå igenom ett vanligt artikelplaceringsscenario</span><span class="sxs-lookup"><span data-stu-id="51b89-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="51b89-327">När alla nödvändiga element är på rätt sätt, så som beskrivs i föregående avsnitt, är du redo att testa funktionen genom att arbeta igenom varje övning i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="51b89-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="51b89-328">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="51b89-328">Generate demand</span></span>

1. <span data-ttu-id="51b89-329">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar** och välj artikelplaceringsmallen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="51b89-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="51b89-330">Välj **efterfrågeprognoser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="51b89-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="51b89-331">Det här kommandot utvärderar alla efter frågan i systemet och matchar den i artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="51b89-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="51b89-332">Den totala efter frågan på alla order konsolideras sedan på en rad per kvantitet/måttenhet.</span><span class="sxs-lookup"><span data-stu-id="51b89-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="51b89-333">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="51b89-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="51b89-334">Efterfrågan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-334">Slotting demand</span></span>

<span data-ttu-id="51b89-335">*Behovet av artikelplacering* visar resultatet av efterfrågegenereringen, baserat på inställningarna för den artikelplaceringsmallen.</span><span class="sxs-lookup"><span data-stu-id="51b89-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="51b89-336">I åtgärdsfönstret, välj **Behovet av artikelplacering** du vill visa resultaten från kommandot **Efterfrågeprognoser**.</span><span class="sxs-lookup"><span data-stu-id="51b89-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="51b89-337">Raderna i artikelplaceringsbehov kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="51b89-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="51b89-338">Du kan ta bort en rad, lägga till en ny rad eller redigera raddetaljerna.</span><span class="sxs-lookup"><span data-stu-id="51b89-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="51b89-339">Du kan redigera efter frågan manuellt eller också kan du importera den från ett externt system genom att använda datahantering.</span><span class="sxs-lookup"><span data-stu-id="51b89-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="51b89-340">Det som finns i artikelplaceringsbehov kommer att användas i nästa steg, oavsett var det kom från.</span><span class="sxs-lookup"><span data-stu-id="51b89-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="51b89-341">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="51b89-341">Locate demand</span></span>

<span data-ttu-id="51b89-342">Efter att efterfrågan har genererats måste du använda kommandot **Hitta efterfrågan** för att generera den *Artikelplaceringsplanen*.</span><span class="sxs-lookup"><span data-stu-id="51b89-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="51b89-343">Välj **Hitta efterfrågan** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="51b89-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="51b89-344">Artikelplaceringsprocessen körs.</span><span class="sxs-lookup"><span data-stu-id="51b89-344">The slotting process runs.</span></span> <span data-ttu-id="51b89-345">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="51b89-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="51b89-346">Plan för artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-346">Slotting plan</span></span>

<span data-ttu-id="51b89-347">Artikelplaceringsplanen visar platsen som varje artikel/kvantitet har tilldelats för, om spill användes, om det är fråga om att arbeta med rader och vilka mallrader som användes.</span><span class="sxs-lookup"><span data-stu-id="51b89-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="51b89-348">*Alla efterfrågan som inte kan skåras markeras i artikelplacering.*</span><span class="sxs-lookup"><span data-stu-id="51b89-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="51b89-349">I åtgärdsfönstret, välj **Artikelplaceringsplan** du vill visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="51b89-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="51b89-350">Processen **Generera efterfrågan**, **Hitta efterfrågan** och **Kör lagerpåfyllnad** processer i ett begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="51b89-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="51b89-351">(Dessa processer är tillgängliga från åtgärdsfönstret på sidan **artikelplaceringsmallar**).</span><span class="sxs-lookup"><span data-stu-id="51b89-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="51b89-352">Processer **Generera efterfrågan**, **Lokalisera efterfrågan** och **Kör lagerpåfyllnad** processer har ett lås för att säkerställa att de inte kan utlösas samtidigt.</span><span class="sxs-lookup"><span data-stu-id="51b89-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="51b89-353">I annat fall kan data som används tas bort.</span><span class="sxs-lookup"><span data-stu-id="51b89-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="51b89-354">Processerna **Generera efterfrågan** och **Lokalisera efterfrågan** visar en varning om körningen inte genererade poster, eller om det saknas information om posterna.</span><span class="sxs-lookup"><span data-stu-id="51b89-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="51b89-355">När du väljer en **Plan för artikelplacering** har inte sidan knapparna **Ny**, **Redigera** eller **Ta bort** i åtgärdsfönstret eftersom datakällan inte kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="51b89-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="51b89-356">När du väljer **Kör påfyllnad**, validerar systemet den valda platsens mall och processer.</span><span class="sxs-lookup"><span data-stu-id="51b89-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="51b89-357">Skapa lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="51b89-357">Create replenishment</span></span>

<span data-ttu-id="51b89-358">När du har skapat en artikelplaceringsplan måste du skapa *lagerpåfyllningsarbete* baserat på planen.</span><span class="sxs-lookup"><span data-stu-id="51b89-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="51b89-359">I åtgärdsfönstret, klicka på **Kör lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="51b89-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="51b89-360">Ett informationsmeddelande visas när processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="51b89-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="51b89-361">Det här meddelandet visar antalet huvuden som har skapats för versions-ID för arbete.</span><span class="sxs-lookup"><span data-stu-id="51b89-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="51b89-362">De platsdirektiv som kommer att användas identifieras utifrån den direktivkod som anges på varje rad i en mall.</span><span class="sxs-lookup"><span data-stu-id="51b89-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="51b89-363">Tips:</span><span class="sxs-lookup"><span data-stu-id="51b89-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="51b89-364">Ställ in automatisk artikelplacering</span><span class="sxs-lookup"><span data-stu-id="51b89-364">Set up automatic slotting</span></span>

<span data-ttu-id="51b89-365">När alla nödvändiga element är på plats kan du ställa in artikelplacering så att de körs automatiskt genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="51b89-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="51b89-366">Gå till **Lagerstyrning \> Lagerpåfyllnad \> Köra artikelplacering**.</span><span class="sxs-lookup"><span data-stu-id="51b89-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="51b89-367">Ange de artikelplaceringssteg som ska köras.</span><span class="sxs-lookup"><span data-stu-id="51b89-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="51b89-368">Välj ett eller flera av följande artikelplaceringssteg:</span><span class="sxs-lookup"><span data-stu-id="51b89-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="51b89-369">Generera efterfrågan</span><span class="sxs-lookup"><span data-stu-id="51b89-369">Generate demand</span></span>
    - <span data-ttu-id="51b89-370">Hitta efterfrågan</span><span class="sxs-lookup"><span data-stu-id="51b89-370">Locate demand</span></span>
    - <span data-ttu-id="51b89-371">Skapa lagerpåfyllnadsarbete</span><span class="sxs-lookup"><span data-stu-id="51b89-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="51b89-372">Artikelplaceringsstegen är progressiva.</span><span class="sxs-lookup"><span data-stu-id="51b89-372">The slotting steps are progressive.</span></span> <span data-ttu-id="51b89-373">Om du vill välja *Hitta efterfrågan* måste du först välja *Generera efterfrågan*.</span><span class="sxs-lookup"><span data-stu-id="51b89-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="51b89-374">Ange vilken artikelplaceringsmall som ska användas.</span><span class="sxs-lookup"><span data-stu-id="51b89-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="51b89-375">Ställ in upprepning så att körningen sker automatiskt om du vill.</span><span class="sxs-lookup"><span data-stu-id="51b89-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="51b89-376">I övningarna i scenariot ska du **inte** ställa in automatisk artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="51b89-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
