---
title: Systemstyrd arbetssekvensering
description: I det här avsnittet finns information om hur du dirigerar arbetssekvensering. Med den här funktionen kan du sortera och filtrera arbetsorder som systemet visar för användare för körning. Det är praktiskt i scenarier där det krävs fler kriterier för att köra plockningsprocessen för lager.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 2884c480d20090266f7cffb5e7d0aca58c1174f0
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2020
ms.locfileid: "3534860"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="cbcd5-105">Systemstyrd arbetssekvensering</span><span class="sxs-lookup"><span data-stu-id="cbcd5-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbcd5-106">Systemstyrd arbetssekvensering låter dig sortera och filtrera arbetsorder som systemet visar för användare för körning.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="cbcd5-107">Det är praktiskt i situationer där ytterligare kriterier (t.ex. leveranstid, plockningszon, platsprofil eller en kombination av olika kriterier) krävs för att köra lagerplockningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="cbcd5-108">Den här funktionen utökar den aktuella systembaserade plockningsfunktionen genom att lägga till en systemriktad frågeorder där användarna kan ställa in en sekvens och en eller flera frågor som ska utvärdera alla arbetsorder som skapas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="cbcd5-109">Endast arbetsorder som uppfyller de kriterier som anges i inställningarna för menyalternativet för mobil enhet hämtas och presenteras.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="cbcd5-110">Denna funktion gör det enklare att optimera lagerplockningsprocesserna när de identifierar arbetsorder som matchar de angivna villkoren, tilldelar dem till rätt menyalternativ för mobila enheter och visar dem sedan till en arbetare, baserat på en viss färdighetsuppsättning, plockningsutrustning eller annat behov.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="cbcd5-111">Om det behövs andra kriterier måste flera menyalternativ på mobil enhet användas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="cbcd5-112">Aktivera funktionen för systemstyrd arbetssekvensering på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="cbcd5-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="cbcd5-113">Innan du kan använda funktionen systemstyrd arbetssekvensering måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="cbcd5-114">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="cbcd5-115">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="cbcd5-116">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="cbcd5-117">**Funktionsnamn:** *systemstyrd arbetssekvensering på organisationsnivå*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="cbcd5-118">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="cbcd5-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="cbcd5-119">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="cbcd5-119">Make demo data available</span></span>

<span data-ttu-id="cbcd5-120">För att arbeta igenom scenariot genom att använda värdena som presenteras i det här ämnet måste du arbeta på ett system där standarddemodata är installerat.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="cbcd5-121">Dessutom måste du välja den **USMF** juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="cbcd5-122">Scenariot använder lagerställe *51* från demodata.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbcd5-123">Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på order.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="cbcd5-124">Standard USMF-data bör stödja det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="cbcd5-125">Om du inte använder demodata, granska inställningen **platsdirektiv** för att lära dig vilka plockplatser som används för plockning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="cbcd5-126">Om du måste justera inventeringen kan du skapa manuella rörelser, använda påfyllning eller använda något annat flöde.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="cbcd5-127">Ställ in menyalternativ för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="cbcd5-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="cbcd5-128">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="cbcd5-129">I listan menyalternativ för mobila enheter, välj **Försäljningsplockning – System**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="cbcd5-130">Det menyalternativ som krävs ska redan finnas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="cbcd5-131">Bekräfta följande inställning:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="cbcd5-132">På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *Systemdirigerat*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="cbcd5-133">Snabbfliken **arbetsgrupper** ska innehålla följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="cbcd5-134">Arbetsklass-ID</span><span class="sxs-lookup"><span data-stu-id="cbcd5-134">Work class ID</span></span> | <span data-ttu-id="cbcd5-135">Typ av arbetsorder</span><span class="sxs-lookup"><span data-stu-id="cbcd5-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="cbcd5-136">Försäljning</span><span class="sxs-lookup"><span data-stu-id="cbcd5-136">Sales</span></span> | <span data-ttu-id="cbcd5-137">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="cbcd5-137">Sales orders</span></span> |
        | <span data-ttu-id="cbcd5-138">SÅ välj</span><span class="sxs-lookup"><span data-stu-id="cbcd5-138">SO Pick</span></span> | <span data-ttu-id="cbcd5-139">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="cbcd5-139">Sales orders</span></span> |

1. <span data-ttu-id="cbcd5-140">I åtgärdsfönstret väljer du **Systeminriktade arbetsordningsfrågor**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="cbcd5-141">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-141">Select **Edit**.</span></span>
1. <span data-ttu-id="cbcd5-142">Ta bort den befintliga raden och bekräfta sedan åtgärden genom att välja **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="cbcd5-143">I åtgärdsfönstret, välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="cbcd5-144">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-145">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="cbcd5-146">**Fältet Beskrivning:** *Arbetskvantitet mindre än 20 och fallande*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="cbcd5-147">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-147">Select **Save**.</span></span>
1. <span data-ttu-id="cbcd5-148">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="cbcd5-149">På fliken **Kopplingar** expanderar du kopplingshierarkin för att visa tabellen **Arbetsrader**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="cbcd5-150">Välj tabellen **Arbetsrader**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="cbcd5-151">Välj **Lägg till registerkoppling**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="cbcd5-152">Leta upp och markera den rad som har följande inställningar i listan som visas:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="cbcd5-153">**Kopplingsläge:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="cbcd5-154">**Relation:** *Platser (plats)*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="cbcd5-155">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-155">Select **Select**.</span></span>

    <span data-ttu-id="cbcd5-156">Platser läggs till i registerkoppling.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="cbcd5-157">På fliken **Sortering**, välj **Lägg till** om du vill lägga till en rad.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="cbcd5-158">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-159">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-160">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-161">**Fält:** *Arbetskvantitet* (i meddelanderutan som visas väljer du **Ja** om du vill lägga till sortering i det här fältet.)</span><span class="sxs-lookup"><span data-stu-id="cbcd5-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="cbcd5-162">**Sökriktning:** *Fallande*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="cbcd5-163">Välj fliken **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="cbcd5-164">Om bara specifika arbetskriterier ska inkluderas i ordningsföljden kan du ange dem på fliken **Intervall**. I det här exemplet vill du bara inkludera arbete där kvantiteten är mindre än 20 ea (den lägsta måttenheten).</span><span class="sxs-lookup"><span data-stu-id="cbcd5-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="cbcd5-165">Lägg märke till att vissa rader redan ingår.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-165">Notice that some lines are already included.</span></span> <span data-ttu-id="cbcd5-166">Dessa rader bör inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="cbcd5-167">Välj **Lägg till** för att lägga till en rad.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="cbcd5-168">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-169">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-170">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-171">**Fält:** *Inventarisk arbetskvantitet*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="cbcd5-172">**Kriterier:** *\<20* (mindre än 20)</span><span class="sxs-lookup"><span data-stu-id="cbcd5-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="cbcd5-173">Välj **Lägg till** för att lägga till en annan rad.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="cbcd5-174">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-175">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-176">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="cbcd5-177">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="cbcd5-178">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="cbcd5-179">Välj **Lägg till** för att lägga till en annan rad.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="cbcd5-180">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-181">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="cbcd5-182">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="cbcd5-183">**Fält:** *platsprofil-ID*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="cbcd5-184">**Villkor:** *!FAS*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="cbcd5-185">Se till att du tar med utropstecknet (*!*) framför *FAS*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="cbcd5-186">Välj **OK** om du vill spara och stänga frågan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="cbcd5-187">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-187">Select **Save**.</span></span>
1. <span data-ttu-id="cbcd5-188">Stäng sidan och gå tillbaka till sidan **Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="cbcd5-189">Inställningen definierar de kriterier som används för att mata berättigat arbete till menyalternativet på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="cbcd5-190">Om du lägger till fler villkorsrader i frågan använder systemet först den orderrad som har lägst serienummer.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="cbcd5-191">Med andra ord visas först alla stödberättigande arbeten för löpnummer 1 för användaren och sedan allt arbete för löpnummer 2.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="cbcd5-192">Om ett visst intervall och sortering måste användas tillsammans, ska detta därför anges i samma systemstyrda arbetssekvensfråga.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="cbcd5-193">Med den här inställningen sparas alla arbeten som har minst en rad där kvantiteten är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="cbcd5-194">Om arbetet har en rad där kvantiteten är exakt 20 ea eller mer än 20 ea, blir den därför giltig, förutsatt att den också har minst en rad där kvantiteten är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="cbcd5-195">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="cbcd5-195">Location directives</span></span>

<span data-ttu-id="cbcd5-196">Om du använder Contoso-standarddata behöver frågan för åtgärdsrad för platsdirektiv inte ändras.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="cbcd5-197">Om du vill vara säker på att platsdirektiven kommer att fånga in artiklarna på försäljningsordern när du tillämpar funktionen i en icke-Contoso-miljö, ska du dock skapa ett nytt lokaliseringsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="cbcd5-198">Kontrollera inställningarna i demomiljön enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="cbcd5-199">Gå till **Lagerstyrning** \> **Ställ in** \> **Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="cbcd5-200">Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="cbcd5-201">Välj platsdirektivet med namnet *51 plockning*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="cbcd5-202">På snabbfliken **Platsdirektivåtgärd** välj raden för åtgärden **Plocka**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="cbcd5-203">Välj **redigeringsfråga** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="cbcd5-204">Kontrollera frågan **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="cbcd5-205">Hitta raden där fältet **Fält** är inställt på *Plats*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="cbcd5-206">Kontrollera att fältet **Kriterier** är tomt (dvs. det finns inga begränsningar).</span><span class="sxs-lookup"><span data-stu-id="cbcd5-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="cbcd5-207">Scenario</span><span class="sxs-lookup"><span data-stu-id="cbcd5-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="cbcd5-208">Skapa plockningsarbete för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="cbcd5-208">Create sales order picking work</span></span>

<span data-ttu-id="cbcd5-209">Innan systembaserade plockningen bör en del utgående arbete skapas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="cbcd5-210">I det här scenariot skapar du fyra försäljningsorder som baseras på angivna systeminriktade arbetsordningsfrågor.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="cbcd5-211">Du kommer att reservera lagerkvantiteter för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="cbcd5-212">Detta innebär att reserverade lager inte kan hämtas från lagerstället för andra order om inte lagerreservationen, eller delar av den, annulleras.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="cbcd5-213">Därefter frigörs varje försäljningsorder till lagerstället så att det utgående arbetet skapas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="cbcd5-214">Försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="cbcd5-214">Sales order 1</span></span>

1. <span data-ttu-id="cbcd5-215">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="cbcd5-216">I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="cbcd5-217">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-218">I avsnittet **Kund** ställer du in fältet **Kundkonto** på *US-004*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="cbcd5-219">I avsnittet **Allmänt** anger du fältet **Lagerställe** till *51*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="cbcd5-220">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="cbcd5-221">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="cbcd5-222">Lägg till en rad till den nya försäljningsorden och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-223">**Artikelnummer:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="cbcd5-224">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="cbcd5-225">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="cbcd5-226">På sidan **Reservation**, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="cbcd5-227">Stäng sidan **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="cbcd5-228">I åtgärdsfönstret på fliken **Lagerställe** väljer du **Släpp till lagerställe** för att skapa arbete för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="cbcd5-229">Du får informationsmeddelanden som visar det påfyllnads-ID och leverans-ID som skapades för försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="cbcd5-230">Försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="cbcd5-230">Sales order 2</span></span>

1. <span data-ttu-id="cbcd5-231">I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="cbcd5-232">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-233">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="cbcd5-234">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="cbcd5-235">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="cbcd5-236">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="cbcd5-237">Lägg till en rad till den nya försäljningsorden och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-238">**Artikelnummer:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="cbcd5-239">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="cbcd5-240">Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-241">**Artikelnummer:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="cbcd5-242">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="cbcd5-243">Reservera lager för båda raderna.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="cbcd5-244">Släpp order till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="cbcd5-245">Försäljningsorder 3</span><span class="sxs-lookup"><span data-stu-id="cbcd5-245">Sales order 3</span></span>

1. <span data-ttu-id="cbcd5-246">I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 3.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="cbcd5-247">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-248">**Kundkonto:** *US-009*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="cbcd5-249">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="cbcd5-250">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="cbcd5-251">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="cbcd5-252">Lägg till en rad till den nya försäljningsorden och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-253">**Artikelnummer:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="cbcd5-254">**Kvantitet:** *7*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="cbcd5-255">Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-256">**Artikelnummer:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="cbcd5-257">**Kvantitet:** *8*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="cbcd5-258">Reservera lager för båda raderna.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="cbcd5-259">Släpp order till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="cbcd5-260">Försäljningsorder 4</span><span class="sxs-lookup"><span data-stu-id="cbcd5-260">Sales order 4</span></span>

1. <span data-ttu-id="cbcd5-261">I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 4.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="cbcd5-262">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="cbcd5-263">**Kundkonto:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="cbcd5-264">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="cbcd5-265">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="cbcd5-266">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="cbcd5-267">Lägg till en rad till den nya försäljningsorden och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-268">**Artikelnummer:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="cbcd5-269">**Kvantitet:** *25*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="cbcd5-270">Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="cbcd5-271">**Artikelnummer:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="cbcd5-272">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="cbcd5-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="cbcd5-273">Reservera lager för båda raderna.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="cbcd5-274">Släpp order till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="cbcd5-275">Hämta arbets-ID för det arbete som har skapats</span><span class="sxs-lookup"><span data-stu-id="cbcd5-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="cbcd5-276">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="cbcd5-277">Filtrera i fältet **lagerställe** så att endast arbete för lagerställe *51* visas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="cbcd5-278">Fyra arbets-ID bör ha skapats.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-278">Four work IDs should have been created.</span></span> <span data-ttu-id="cbcd5-279">Anteckna arbets-ID:t för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="cbcd5-280">ID för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="cbcd5-280">Sales order ID</span></span> | <span data-ttu-id="cbcd5-281">Arbets-ID</span><span class="sxs-lookup"><span data-stu-id="cbcd5-281">Work ID</span></span> | <span data-ttu-id="cbcd5-282">Arbetskvantitet</span><span class="sxs-lookup"><span data-stu-id="cbcd5-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="cbcd5-283">Försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="cbcd5-283">Sales Order 1</span></span> | <span data-ttu-id="cbcd5-284">Arbets-ID 1</span><span class="sxs-lookup"><span data-stu-id="cbcd5-284">Work ID 1</span></span> | <span data-ttu-id="cbcd5-285">20 ea</span><span class="sxs-lookup"><span data-stu-id="cbcd5-285">20 ea</span></span> |
    | <span data-ttu-id="cbcd5-286">Försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="cbcd5-286">Sales Order 2</span></span> | <span data-ttu-id="cbcd5-287">Arbets-ID 2</span><span class="sxs-lookup"><span data-stu-id="cbcd5-287">Work ID 2</span></span> | <span data-ttu-id="cbcd5-288">6 ea (summan av båda raderna)</span><span class="sxs-lookup"><span data-stu-id="cbcd5-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="cbcd5-289">Försäljningsorder 3</span><span class="sxs-lookup"><span data-stu-id="cbcd5-289">Sales Order 3</span></span> | <span data-ttu-id="cbcd5-290">Arbets-ID 3</span><span class="sxs-lookup"><span data-stu-id="cbcd5-290">Work ID 3</span></span> | <span data-ttu-id="cbcd5-291">15 ea (summan av båda raderna)</span><span class="sxs-lookup"><span data-stu-id="cbcd5-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="cbcd5-292">Försäljningsorder 4</span><span class="sxs-lookup"><span data-stu-id="cbcd5-292">Sales Order 4</span></span> | <span data-ttu-id="cbcd5-293">Arbets-ID 4</span><span class="sxs-lookup"><span data-stu-id="cbcd5-293">Work ID 4</span></span> | <span data-ttu-id="cbcd5-294">35 ea (summan av båda raderna)</span><span class="sxs-lookup"><span data-stu-id="cbcd5-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="cbcd5-295">Innan du kör flödet på den mobila enheten ska du kontrollera att endast det arbete som du just skapade är status *Öppna* för lagerställe *51* och arbetsordertyp *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="cbcd5-296">I annat fall kan testresultatet variera, eftersom systemdirekt plockning kommer att inkludera allt kvalificerat arbete.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="cbcd5-297">Gå till **Lagerstyrning \> Arbeta \> Utgående \> Öppet försäljningsarbete**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="cbcd5-298">I rutnätet **Öppet försäljningsarbete** filtrera fältet **Lagerställe** så att endast arbete för lagerställe *51* visas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="cbcd5-299">Kontrollera att endast de fyra arbets-ID:n som du skapade tidigare visas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="cbcd5-300">Stäng sidan **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="cbcd5-301">Flödeskörning för mobil enhet</span><span class="sxs-lookup"><span data-stu-id="cbcd5-301">Mobile device flow execution</span></span>

<span data-ttu-id="cbcd5-302">Baserat på inställningarna kommer systemet att mata in det användararbete som är sorterat från den högsta kvantiteten för arbetsraden till den lägsta.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="cbcd5-303">Kvantiteten på varje rad är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="cbcd5-304">Kom ihåg att den här inställningen sparas alla arbeten som har minst en rad där kvantiteten är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="cbcd5-305">Om arbetet har en annan rad där kvantiteten är exakt 20 ea eller mer än 20 ea kommer den också att vara giltig.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="cbcd5-306">Mobilapp</span><span class="sxs-lookup"><span data-stu-id="cbcd5-306">Mobile app</span></span>

1. <span data-ttu-id="cbcd5-307">Logga in på lagerstyrningsappen en användare i lager ställe *51*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="cbcd5-308">Gå till **Utgående \> Försäljningsplockning - System**.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="cbcd5-309">Plockningssteget för arbets-ID *4* visas.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="cbcd5-310">Detta arbets-ID visas först på grund av inställningarna i systemriktad frågeordning, där du har angett att arbetet ska ordnas baserat på arbetsradens kvantitet i fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="cbcd5-311">Slutför den begärda plockningen och sätt att stänga arbets-ID:t.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="cbcd5-312">Sedan visas arbets-ID *3*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="cbcd5-313">En av dess arbetsrader ligger härnäst i sekvensen, baserad på arbetsradens kvantitet.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="cbcd5-314">Slutför plockningen och sätt att stänga arbets-ID:t.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="cbcd5-315">Sedan visas arbets-ID *2*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="cbcd5-316">Det här arbetets plockningsrad är härnäst i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="cbcd5-317">Slutför plockningen och sätt att stänga arbets-ID:t.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="cbcd5-318">Inget ytterligare arbete kan presenteras för dig.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-318">No further work should be presented to you.</span></span> <span data-ttu-id="cbcd5-319">Arbets-ID *1* är inte berättigat till menyalternativet för den mobila enheten eftersom frågan anger att arbetsrubrikerna endast ska beaktas om kvantiteten på arbetsraderna är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="cbcd5-320">Tips:</span><span class="sxs-lookup"><span data-stu-id="cbcd5-320">Tips</span></span>

<span data-ttu-id="cbcd5-321">Systemstyrda frågor för arbetsserier *inkluderar*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="cbcd5-322">Det är viktigt att du minns detta faktum för vissa inställningar.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="cbcd5-323">Du vill till exempel att en viss menyartikel endast ska behandla arbete där arbetsenheten är *ea* och du anger denna begränsning på fliken **intervall** i frågan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="cbcd5-324">I det här fallet skickas alla arbeten där minst en arbetsrad har inställningen för arbetsenhet inställd på *ea* till arbetare.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="cbcd5-325">Därför kan det här arbetet även omfatta arbete där arbetsenheten har en annan arbetsenhet än *ea* (t.ex. *ruta* eller *lastpall*).</span><span class="sxs-lookup"><span data-stu-id="cbcd5-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="cbcd5-326">Frågan utesluter endast arbete där arbetsenheten inte har satts till *ea*.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="cbcd5-327">I exemplet från det här scenariot har arbets-ID *4* också fångats in av frågan.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="cbcd5-328">När den skapades lades två rader till: en för 25 ea och en annan för 10 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="cbcd5-329">Arbetet uppvisades fortfarande för användaren, eftersom minst en arbetsrad har en kvantitet som är mindre än 20 ea.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="cbcd5-330">Beroende på scenariot kan du förhindra detta genom att använda arbetsavbrott.</span><span class="sxs-lookup"><span data-stu-id="cbcd5-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>
