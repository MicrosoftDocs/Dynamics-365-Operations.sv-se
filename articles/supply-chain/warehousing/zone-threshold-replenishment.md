---
title: Zontröskel för lagerpåfyllnad
description: Vid en zonbaserad lagerpåfyllnad används en återanskaffningsstrategi av minsta/högsta (min/max), men den utvärderar hela lagerzoner istället för bara enskilda platser. Därför kan lagerchefer lära sig snabbare om ytterligare lager krävs i en plockzon.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6f4ddd03ec16ac43b007b904eb688563735e0941
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654182"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="e39bc-104">Zontröskel för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e39bc-105">Vid en zonbaserad lagerpåfyllnad används en [återanskaffnings](replenishment.md)-strategi av minsta/högsta (min/max), men den utvärderar hela lagerzoner istället för bara enskilda platser.</span><span class="sxs-lookup"><span data-stu-id="e39bc-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="e39bc-106">Därför kan lagerchefer lära sig snabbare om ytterligare lager krävs i en plockzon.</span><span class="sxs-lookup"><span data-stu-id="e39bc-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="e39bc-107">Inställningen för den här funktionen liknar inställningen för platsbaserad lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="e39bc-108">När du ställer in en mall för den minsta/högsta lagerpåfyllnad kan du också ange om tröskeln ska utvärderas per lagerställe eller per zon.</span><span class="sxs-lookup"><span data-stu-id="e39bc-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="e39bc-109">Om du ställer in utvärdering som baseras på zoner måste du lägga till specifika zoner i urvalsfrågan för zoner.</span><span class="sxs-lookup"><span data-stu-id="e39bc-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="e39bc-110">T.ex. platsbaserad min/max lagerpåfyllnad, zonbaserade krav på min/max lagerpåfyllnad baseras på inställningen av ett minsta lagertröskelvärde som utlöser ett lagerpåfyllningsarbete för valda artiklar.</span><span class="sxs-lookup"><span data-stu-id="e39bc-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="e39bc-111">Detta lagerpåfyllningsarbete ökar lagret till det angivna maximala tröskelvärdet för zonen.</span><span class="sxs-lookup"><span data-stu-id="e39bc-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="e39bc-112">Zonåteranskaffningsprocesser för produktvarianter stöds inte i den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="e39bc-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="e39bc-113">Till skillnad från platsbaserad minsta lagerpåfyllnad, kräver zonbaserade min/max lagerpåfyllnad inte fasta platser för att utvärdera om platser ska lagra en viss artikel.</span><span class="sxs-lookup"><span data-stu-id="e39bc-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="e39bc-114">Med hjälp av zonbaserad lagerpåfyllnad kan du därför använda min/max lagerpåfyllnad även om du inte har fasta platser för varje artikel eller artikelvariant i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="e39bc-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="e39bc-115">När en kvantitet i zonen ligger under det angivna minimitröskelvärdet skapas lagerpåfyllnadsarbetet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="e39bc-116">Platsdirektiv avgör vilken plats lagret ska placeras i.</span><span class="sxs-lookup"><span data-stu-id="e39bc-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="e39bc-117">Aktivera funktionen Zontröskel för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="e39bc-118">Innan du kan använda funktionen *Zontröskel för lagerpåfyllnad* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="e39bc-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="e39bc-119">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="e39bc-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="e39bc-120">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e39bc-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="e39bc-121">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="e39bc-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e39bc-122">**Funktionens namn:** *Zontröskel för lagerpåfyllnad*</span><span class="sxs-lookup"><span data-stu-id="e39bc-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="e39bc-123">Ställ in zonbaserad lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="e39bc-124">Om du vill ställa in zonbaserad lagerpåfyllnad måste du konfigurera flera delar av systemet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="e39bc-125">Det här avsnittet innehåller en introduktion till de olika inställningarna och innehåller datavärden för demonstrationer som du kan ange om du vill arbeta genom scenariot i slutet av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="e39bc-126">Ställ in direktivkoder</span><span class="sxs-lookup"><span data-stu-id="e39bc-126">Set up directive codes</span></span>

<span data-ttu-id="e39bc-127">[Direktivkoder](control-warehouse-location-directives.md) låter dig vara mer specifik när du definierar platsmallen som används i en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="e39bc-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="e39bc-128">Varje kod bestämmer ett gemensamt värde som du kan referera till när du konfigurerar respektive malltyp.</span><span class="sxs-lookup"><span data-stu-id="e39bc-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="e39bc-129">Visa och redigera direktivkoder</span><span class="sxs-lookup"><span data-stu-id="e39bc-129">View and edit directive codes</span></span>

<span data-ttu-id="e39bc-130">Gå till om du vill se eller redigera dina direktivkoder **Lagerstyrning \> Inställning \> Direktivkoder**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="e39bc-131">Förbered demodata, direktivkoder</span><span class="sxs-lookup"><span data-stu-id="e39bc-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="e39bc-132">Det här exemplet visar hur du förbereder en direktivkod.</span><span class="sxs-lookup"><span data-stu-id="e39bc-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="e39bc-133">Om du planerar att arbeta genom scenariot i slutet av det här avsnittet ska du använda de datavärden för demon som finns här.</span><span class="sxs-lookup"><span data-stu-id="e39bc-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="e39bc-134">I annat fall använder du dina egna värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="e39bc-135">Välj den juridiska personen **USMF** för att arbeta med demodata.</span><span class="sxs-lookup"><span data-stu-id="e39bc-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="e39bc-136">Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="e39bc-137">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-138">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-139">**Direktivkod:** _Zonlagerp_</span><span class="sxs-lookup"><span data-stu-id="e39bc-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="e39bc-140">**Direktivbeskrivning:** _Zonlagerpåfyllnad_</span><span class="sxs-lookup"><span data-stu-id="e39bc-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="e39bc-141">Välj **Spara** för att spara den nya koden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="e39bc-142">Konfigurera mallar för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-142">Set up replenishment templates</span></span>

<span data-ttu-id="e39bc-143">[Mallar för min/max lagerpåfyllnad](tasks/set-up-min-max-replenishment-process.md) är den primära mekanismen för att bibehålla optimala nivåer på plockplatser.</span><span class="sxs-lookup"><span data-stu-id="e39bc-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="e39bc-144">I dessa mallar måste du ställa in de regler som ska användas för att fylla på lagret i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="e39bc-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="e39bc-145">Påfyllningen som mallarna kan användas för inkluderar zonbaserad lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="e39bc-146">Visa och redigera påfyllnadsmallar</span><span class="sxs-lookup"><span data-stu-id="e39bc-146">View and edit replenishment templates</span></span>

<span data-ttu-id="e39bc-147">En mall för lagerpåfyllnad är en uppsättning regler som kontrollerar hur en plats fylls på.</span><span class="sxs-lookup"><span data-stu-id="e39bc-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="e39bc-148">Du väljer en mall som styr när och hur påfyllnaden görs.</span><span class="sxs-lookup"><span data-stu-id="e39bc-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="e39bc-149">Om du vill visa eller redigera dina påfyllningsmallar, gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="e39bc-150">Förbereda en demodata mall för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="e39bc-151">Det här exemplet visar hur du förbereder en mall för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="e39bc-152">Om du planerar att arbeta genom scenariot i slutet av det här avsnittet ska du använda de datavärden för demon som finns här.</span><span class="sxs-lookup"><span data-stu-id="e39bc-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="e39bc-153">I annat fall använder du dina egna värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="e39bc-154">Välj den juridiska personen **USMF** för att arbeta med demodata.</span><span class="sxs-lookup"><span data-stu-id="e39bc-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="e39bc-155">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mall för lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="e39bc-156">Välj **Redigera** om du vill placera sidan i redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="e39bc-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="e39bc-157">I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="e39bc-158">I den nya raden anger du följande värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-158">In the new row, set the following values.</span></span> <span data-ttu-id="e39bc-159">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="e39bc-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="e39bc-160">**Lagerpåfyllnadsmall:** _Zon min/max lagerp_</span><span class="sxs-lookup"><span data-stu-id="e39bc-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="e39bc-161">**Beskrivning:** _Zon min/max lagerpåfyllnad_</span><span class="sxs-lookup"><span data-stu-id="e39bc-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="e39bc-162">**Lagerpåfyllnadstyp:** _Minimum eller maximum_</span><span class="sxs-lookup"><span data-stu-id="e39bc-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="e39bc-163">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-163">Select **Save**.</span></span>
1. <span data-ttu-id="e39bc-164">Medan den nya raden fortfarande är markerad i rutnätet **Översikt**, välj **Ny** ovanför rutnätet **Information om mall för lagerpåfyllnad** för att lägga till en rad som är kopplad till *Zon min/max lagerp* som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="e39bc-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="e39bc-165">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-166">**Löpnummer:** Ange _1_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="e39bc-167">**Beskrivning:** Ange _Välj zonlagerpåfyllnad_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="e39bc-168">**Påfyllningsenhet:** Välj _ea_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="e39bc-169">**Begärandetyp:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="e39bc-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="e39bc-170">**Direktivkod:** Det här fältet länkar påfyllningsmallen med ett platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="e39bc-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="e39bc-171">Välj den versionskod för demodata som du skapade tidigare (_Zonlagerp_).</span><span class="sxs-lookup"><span data-stu-id="e39bc-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="e39bc-172">**Arbetsmall:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="e39bc-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="e39bc-173">**Minsta kvantitet:** Det här fältet anges den kvantitet som påfyllnaden ska utlösas vid.</span><span class="sxs-lookup"><span data-stu-id="e39bc-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="e39bc-174">Ange _50_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-174">Enter _50_.</span></span>
    - <span data-ttu-id="e39bc-175">**Högsta kvantitet:** Det här fältet anger den maximala kvantiteten för en artikel som kan finnas i en zon.</span><span class="sxs-lookup"><span data-stu-id="e39bc-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="e39bc-176">Genererat återanskaffningsarbete ökar lagret till denna kvantitet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="e39bc-177">Ange _150_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-177">Enter _150_.</span></span>
    - <span data-ttu-id="e39bc-178">**Enhet:** Det här fältet anger enheten för minimi- och maximivärden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="e39bc-179">Välj _ea_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-179">Select _ea_.</span></span>
    - <span data-ttu-id="e39bc-180">**Efterfråganökning:** Välj _Avrunda uppåt_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="e39bc-181">**Fyll på tomma fasta lagerplatser:** Välj denna kryssruta.</span><span class="sxs-lookup"><span data-stu-id="e39bc-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="e39bc-182">**Fyll endast på tomma fasta lagerplatser:** Rensa den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-183">**Läget produktfråga:** Välj _Produktfråga_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="e39bc-184">**Tröskelomfattning för lagerpåfyllnad:** Det här fältet definieras om mallen ska utvärdera per zon eller efter ett visst lagerställe.</span><span class="sxs-lookup"><span data-stu-id="e39bc-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="e39bc-185">Välj _Zon_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-185">Select _Zone_.</span></span>
    - <span data-ttu-id="e39bc-186">**Lagerställe:** Välj _61_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="e39bc-187">Välj **Välj produkter** ovanför rutnätet **Information om mall för lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="e39bc-188">I dialogrutan **Produktfråga** på fliken **Intervall** välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-189">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-190">**Register:** _Artiklar_</span><span class="sxs-lookup"><span data-stu-id="e39bc-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="e39bc-191">**Härlett register:** _Artiklar_</span><span class="sxs-lookup"><span data-stu-id="e39bc-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="e39bc-192">**Fält:** _Artikelnummer_</span><span class="sxs-lookup"><span data-stu-id="e39bc-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="e39bc-193">**Kriterier:** _A0001_</span><span class="sxs-lookup"><span data-stu-id="e39bc-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="e39bc-194">Välj **OK** om du vill spara din fråga och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="e39bc-195">Välj **Välj zoner att fylla på** ovanför rutnätet **Information om mall för lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="e39bc-196">I dialogrutan **Zonfråga** på fliken **Intervall** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-197">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-198">**Register:** _Lagerställezon_</span><span class="sxs-lookup"><span data-stu-id="e39bc-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="e39bc-199">**Härlett register:** _Lagerställezon_</span><span class="sxs-lookup"><span data-stu-id="e39bc-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="e39bc-200">**Fält:** _zon-ID_</span><span class="sxs-lookup"><span data-stu-id="e39bc-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="e39bc-201">**Kriterier:** _VÅNING_</span><span class="sxs-lookup"><span data-stu-id="e39bc-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="e39bc-202">Välj **OK** om du vill spara din fråga och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="e39bc-203">Ställ in platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="e39bc-203">Set up location directives</span></span>

<span data-ttu-id="e39bc-204">Till skillnad från platsbaserad min/max påfyllnadsenhet, zonbaserade min/max lagerpåfyllnad kräver att du måste ställa in både platsdirektiv för plockning och platsdirektiv för placering eftersom systemet utvärderar hela zonen istället för bara plockningsplatsen för utgående arbete.</span><span class="sxs-lookup"><span data-stu-id="e39bc-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="e39bc-205">Visa och redigera platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="e39bc-205">View and edit location directives</span></span>

<span data-ttu-id="e39bc-206">Gå till om du vill se eller redigera dina platsdirektiv **Lagerstyrning \> Inställning \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="e39bc-207">Se nästa avsnitt för exempel som visar hur du använder inställningarna för att skapa de obligatoriska platsdirektiven för plockning och platsdirektiven för placering.</span><span class="sxs-lookup"><span data-stu-id="e39bc-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="e39bc-208">Förbered demodata, platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="e39bc-208">Prepare demo data location directives</span></span>

<span data-ttu-id="e39bc-209">Om du vill förbereda demodata så att de kan användas i scenariot i slutet av det här ämnet måste du skapa två platsdirektiv: ett för plockning och en för placering.</span><span class="sxs-lookup"><span data-stu-id="e39bc-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="e39bc-210">Skapa en platsdirektiv för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="e39bc-211">Välj den juridiska personen **USMF** för att arbeta med demodata.</span><span class="sxs-lookup"><span data-stu-id="e39bc-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="e39bc-212">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="e39bc-213">I vänster ruta ange fältet **Arbetsordertyp** till _Lagerpåfyllnad_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="e39bc-214">I åtgärdsfönstret, välj **Ny** för att skapa ett nytt direktiv.</span><span class="sxs-lookup"><span data-stu-id="e39bc-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="e39bc-215">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-215">Set the following values:</span></span>

    - <span data-ttu-id="e39bc-216">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="e39bc-217">**Namn:** Ange _Zonlpockning_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="e39bc-218">**Arbetstyp:** Välj _Plocka_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="e39bc-219">**Plats:** Välj _6_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="e39bc-220">**Lagerställe:** Välj _61_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="e39bc-221">**Direktivkod:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="e39bc-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="e39bc-222">**Flera SKU:** Ange det här alternativet till _Nej_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="e39bc-223">Välj **Spara** om du vill skapa ett direktiv med de inställningar som du har konfigurerat hittills.</span><span class="sxs-lookup"><span data-stu-id="e39bc-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="e39bc-224">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e39bc-225">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="e39bc-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e39bc-226">**Löpnummer:** Ange _1_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="e39bc-227">**Från kvantitet:** Ange _0_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="e39bc-228">**Till kvantitet:** Ange _10000000_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="e39bc-229">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="e39bc-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="e39bc-230">**Lokalisera kvantitet:** Välj _Ingen_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="e39bc-231">**Begränsa efter enhet:** avmarkera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-232">**Avrunda till enhet:** avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-233">**Sök efter förpackningskvantitet:** avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-234">**Tillåt delning:** Markera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="e39bc-235">Välj **Spara** för att spara den nya raden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="e39bc-236">Även om den nya raden fortfarande är markerad i rutnätet **Rader** välj **Ny** snabbfliken **Åtgärder för platsdirektiv** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-237">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-238">**Löpnummer:** Ange _1_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="e39bc-239">**Namn:** Ange _Plockning från bulk_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="e39bc-240">**Användning av fast lagerplats:** Välj _Fasta och ej fasta platser_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="e39bc-241">**Tillåt negativt lager:** Avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-242">**Batchaktiverad:** Avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-243">**Strategi:** Välj _ingen_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="e39bc-244">Välj **Spara** för att spara den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="e39bc-245">Medan den nya åtgärden fortfarande är markerad väljer du **Redigeringsfråga** ovanför rutnätet **Platsdirektivåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="e39bc-246">Dialogruta för fråga visas där du kan välja vilka platser som ska fyllas på från.</span><span class="sxs-lookup"><span data-stu-id="e39bc-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="e39bc-247">På fliken **intervall**, välj **Lägg till** om du vill lägga till rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-248">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-249">**Register:** _platser_</span><span class="sxs-lookup"><span data-stu-id="e39bc-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="e39bc-250">**Härlett register:** _platser_</span><span class="sxs-lookup"><span data-stu-id="e39bc-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="e39bc-251">**Fält:** _zon-ID_</span><span class="sxs-lookup"><span data-stu-id="e39bc-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="e39bc-252">**Kriterier:** _BULK_</span><span class="sxs-lookup"><span data-stu-id="e39bc-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="e39bc-253">Välj **OK** om du vill spara din fråga och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="e39bc-254">Välj **Spara** om du vill spara dina platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="e39bc-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="e39bc-255">Skapa ett placeringsdirektiv för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="e39bc-256">På sidan **Platsdirektiv** i det vänstra fönstret, kontrollerar du att fältet **Typ av arbetsorder** fortfarande är inställt på _Lagerpåfyllnad_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="e39bc-257">I åtgärdsfönstret, välj **Ny** för att skapa ett nytt direktiv.</span><span class="sxs-lookup"><span data-stu-id="e39bc-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="e39bc-258">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-258">Set the following values:</span></span>

    - <span data-ttu-id="e39bc-259">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="e39bc-260">**Namn:** Ange _Zonplacering_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="e39bc-261">**Arbetsordertyp:** Välj _Placera_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="e39bc-262">**Plats:** Välj _6_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="e39bc-263">**Lagerställe:** Välj _61_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="e39bc-264">**Direktivkod:** Välj _Zonlagerp_ om du vill länka det här platsdirektivet till den lagerpåfyllnadsmall som du skapade tidigare med hjälp av koden som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e39bc-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="e39bc-265">**Flera SKU:** Ange det här alternativet till _Nej_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="e39bc-266">Välj **Spara** om du vill skapa ett direktiv med de inställningar som du har konfigurerat hittills.</span><span class="sxs-lookup"><span data-stu-id="e39bc-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="e39bc-267">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e39bc-268">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="e39bc-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e39bc-269">**Löpnummer:** Ange _1_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="e39bc-270">**Från kvantitet:** Ange _0_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="e39bc-271">**Till kvantitet:** Ange _10000000_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="e39bc-272">**Enhet:** Lämna detta fält tomt.</span><span class="sxs-lookup"><span data-stu-id="e39bc-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="e39bc-273">**Lokalisera kvantitet:** Välj _Ingen_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="e39bc-274">**Begränsa efter enhet:** avmarkera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-275">**Avrunda till enhet:** avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-276">**Sök efter förpackningskvantitet:** avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-277">**Tillåt delning:** Markera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="e39bc-278">Välj **Spara** för att spara den nya raden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="e39bc-279">Även om den nya raden fortfarande är markerad i rutnätet **Rader** välj **Ny** snabbfliken **Åtgärder för platsdirektiv** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-280">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-281">**Löpnummer:** Ange _1_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="e39bc-282">**Namn:** Ange _Zonplacering_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="e39bc-283">**Användning av fast lagerplats:** Välj _Fasta och ej fasta platser_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="e39bc-284">**Tillåt negativt lager:** Avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-285">**Batchaktiverad:** Avmarkera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="e39bc-286">**Strategi:** Välj _konsolidera_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="e39bc-287">Välj **Spara** för att spara den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="e39bc-288">Medan den nya åtgärden fortfarande är markerad väljer du **Redigeringsfråga** ovanför rutnätet **Platsdirektivåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="e39bc-289">Dialogruta för fråga visas där du kan välja vilka zonen som ska fyllas på till.</span><span class="sxs-lookup"><span data-stu-id="e39bc-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="e39bc-290">Den här zonen ska vara samma zon som anges i mallen för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="e39bc-291">På fliken **intervall**, välj **Lägg till** om du vill lägga till rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="e39bc-292">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="e39bc-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="e39bc-293">**Register:** _platser_</span><span class="sxs-lookup"><span data-stu-id="e39bc-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="e39bc-294">**Härlett register:** _platser_</span><span class="sxs-lookup"><span data-stu-id="e39bc-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="e39bc-295">**Fält:** _zon-ID_</span><span class="sxs-lookup"><span data-stu-id="e39bc-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="e39bc-296">**Kriterier:** _VÅNING_</span><span class="sxs-lookup"><span data-stu-id="e39bc-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="e39bc-297">Välj **OK** om du vill spara din fråga och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="e39bc-298">Välj **Spara** om du vill spara dina platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="e39bc-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="e39bc-299">Scenario</span><span class="sxs-lookup"><span data-stu-id="e39bc-299">Scenario</span></span>

<span data-ttu-id="e39bc-300">Det här avsnittet innehåller ett exempel på ett scenario som visar hur funktionen fungerar.</span><span class="sxs-lookup"><span data-stu-id="e39bc-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="e39bc-301">Förbered de exempeldata som krävs för exempelscenariot</span><span class="sxs-lookup"><span data-stu-id="e39bc-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="e39bc-302">Innan du börjar arbeta i scenariot måste du aktivera exempeldata och ställa in funktionen enligt beskrivningen i det här avsnittet och i tidigare avsnitt i detta ämne.</span><span class="sxs-lookup"><span data-stu-id="e39bc-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="e39bc-303">Använd USMF juridiska personen</span><span class="sxs-lookup"><span data-stu-id="e39bc-303">Use the USMF legal entity</span></span>

<span data-ttu-id="e39bc-304">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="e39bc-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="e39bc-305">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="e39bc-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="e39bc-306">Förbered ytterligare exempeldata</span><span class="sxs-lookup"><span data-stu-id="e39bc-306">Prepare additional sample data</span></span>

<span data-ttu-id="e39bc-307">När du har valt den juridiska personen för **USMF** lägger du till de ytterligare exempeldata som krävs, enligt beskrivningen i avsnittet [Ställ in zonbaserad lagerpåfyllnad](#setup) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e39bc-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="e39bc-308">Kontrollera behållningslagret</span><span class="sxs-lookup"><span data-stu-id="e39bc-308">Check your on-hand inventory</span></span>

<span data-ttu-id="e39bc-309">Följ dessa steg för att se till att systemet har tillräckligt med inventering för att stödja exempelscenariot.</span><span class="sxs-lookup"><span data-stu-id="e39bc-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="e39bc-310">Kontrollera att det finns lagerbehållning för artikel *A0001* på två olika platser i pockzonen (*VÅNING*) som anges i mall för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="e39bc-311">Det totala lagret bör dock vara mindre än den obligatoriska minimikvantiteten (*50*) som anges i mallen för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="e39bc-312">På så sätt kan du simulera hur beräkningen sker för hela zonen istället för bara för en enda plats.</span><span class="sxs-lookup"><span data-stu-id="e39bc-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="e39bc-313">**Med någon av lagerprocesserna kan du justera lagret efter behov.**</span><span class="sxs-lookup"><span data-stu-id="e39bc-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="e39bc-314">Kontrollera att det finns tillräckligt med lager för artikeln *A0001* på en bulkplats som är angiven i området välj plats för zon där lagerpåfyllnadsarbetet ska plocka artiklar från zon-ID *BULK*.</span><span class="sxs-lookup"><span data-stu-id="e39bc-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="e39bc-315">Det totala lagret måste vara mindre än den obligatoriska maximala kvantiteten (*150*) som anges i mallen för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="e39bc-316">Valfritt men rekommenderat: Följ de här stegen för att skapa en lagerjusteringsjournal:</span><span class="sxs-lookup"><span data-stu-id="e39bc-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="e39bc-317">Gå till **Lagerhantering \> Journalposter \> Artiklar \> Lagerjustering**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="e39bc-318">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-318">Select **New**.</span></span>
    1. <span data-ttu-id="e39bc-319">I dialogrutan **Skapa lagerjournal** i fältet **Lagerställe** välj *61*.</span><span class="sxs-lookup"><span data-stu-id="e39bc-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="e39bc-320">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-320">Select **OK**.</span></span>
    1. <span data-ttu-id="e39bc-321">På snabbfliken **Journalrader** använder du knappen **Ny** för att lägga till tre rader i rutnätet och anger följande värden.</span><span class="sxs-lookup"><span data-stu-id="e39bc-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="e39bc-322">När du är klar med inställningarna för varje rad väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="e39bc-323">**Rad 1:**</span><span class="sxs-lookup"><span data-stu-id="e39bc-323">**Line 1:**</span></span>

            - <span data-ttu-id="e39bc-324">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e39bc-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="e39bc-325">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="e39bc-325">**Site:** *6*</span></span>
            - <span data-ttu-id="e39bc-326">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="e39bc-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="e39bc-327">**Plats:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="e39bc-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="e39bc-328">**ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="e39bc-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="e39bc-329">**Kvantitet:** *1000*</span><span class="sxs-lookup"><span data-stu-id="e39bc-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="e39bc-330">**Rad 2:**</span><span class="sxs-lookup"><span data-stu-id="e39bc-330">**Line 2:**</span></span>

            - <span data-ttu-id="e39bc-331">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e39bc-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="e39bc-332">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="e39bc-332">**Site:** *6*</span></span>
            - <span data-ttu-id="e39bc-333">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="e39bc-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="e39bc-334">**Plats:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="e39bc-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="e39bc-335">**ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="e39bc-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="e39bc-336">**Kvantitet:** *15*</span><span class="sxs-lookup"><span data-stu-id="e39bc-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="e39bc-337">**Rad 3:**</span><span class="sxs-lookup"><span data-stu-id="e39bc-337">**Line 3:**</span></span>

            - <span data-ttu-id="e39bc-338">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e39bc-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="e39bc-339">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="e39bc-339">**Site:** *6*</span></span>
            - <span data-ttu-id="e39bc-340">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="e39bc-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="e39bc-341">**Plats:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="e39bc-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="e39bc-342">**ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="e39bc-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="e39bc-343">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="e39bc-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="e39bc-344">I åtgärdsfönstret, välj **Validera**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="e39bc-345">Åtgärda eventuella fel som hittas innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="e39bc-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="e39bc-346">I åtgärdsfönstret, välj **Bokför** för att bokföra lager till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="e39bc-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="e39bc-347">Exempelscenario: kör zonbaserad min/max lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="e39bc-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="e39bc-348">När alla exempeldata som krävs finns på sin ställe kan du utlösa lagerpåfyllnad genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e39bc-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="e39bc-349">Gå till **Lagerstyrning \> Lagerpåfyllnad \> Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="e39bc-350">I dialogrutan **Lagerpåfyllnad** på snabbfliken **Poster som ska ingå** väljer **Filter**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="e39bc-351">I dialogrutan **Förfrågning** fliken **Sortiment** redigera standardtabellraden på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e39bc-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="e39bc-352">**Register:** Välj _lagerpåfyllnadsmallar_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="e39bc-353">**Härlett register:** Välj _lagerpåfyllnadsmallar_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="e39bc-354">**Fält:** Välj _lagerpåfyllnadsmall_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="e39bc-355">**Kriterier:** Välj _Zon min/max lagerp_.</span><span class="sxs-lookup"><span data-stu-id="e39bc-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="e39bc-356">Den här påfyllnadsmall är den påfyllnadsmall som du skapade när du förbereder demodata för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="e39bc-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="e39bc-357">Välj **OK** om du vill spara frågan och gå tillbaka dialogrutan **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="e39bc-358">Klicka på **OK** om du vill köra mall för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="e39bc-359">Lagerpåfyllnadsarbetet skapas nu för att plocka lagret från den *BULK* och sedan fylla på det till *VÅNING*.</span><span class="sxs-lookup"><span data-stu-id="e39bc-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="e39bc-360">Anteckningar och tips</span><span class="sxs-lookup"><span data-stu-id="e39bc-360">Notes and tips</span></span>

<span data-ttu-id="e39bc-361">Här följer några anmärkningar och tips för hur du arbetar med funktionen:</span><span class="sxs-lookup"><span data-stu-id="e39bc-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="e39bc-362">Om du vill ställa in påfyllningsarbetet som går till önskad zon kan du länka påfyllnadsgrupp och mallrad för lagerpåfyllnad på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e39bc-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="e39bc-363">Redigera frågan för direktivrubrik för plats och filtrera de valda mallrad för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e39bc-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="e39bc-364">Använd en direktivkod på raden för lagerpåfyllnad och matcha den med platsdirektiv för placering.</span><span class="sxs-lookup"><span data-stu-id="e39bc-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="e39bc-365">Om du använder dynamiska platser kommer lagerpåfyllnadsarbetet att skapas antingen för den första tillgängliga platsen eller för en plats som redan innehåller lager om åtgärden platsdirektiv har ställts in för att använda strategin **konsolidering**.</span><span class="sxs-lookup"><span data-stu-id="e39bc-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="e39bc-366">Om du använder fast lagerplats i stället för zoner bör du använda [standard för min/max lagerpåfyllnad](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="e39bc-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>
