---
title: Placera på vägg – placera i butik
description: Det här avsnittet innehåller information om funktionen Placera på vägg – placera i butik. Med den här funktionen kan du hantera situationer där du måste konsolidera en produkt till ett förpackat mellanlagringsområdet, baserat på konfigurerbara kriterier. Den hjälper till att minska plocktiden eftersom den möjliggör plockning på en målnummer-ID och kan använda fler befattningar än klusterplockning.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3f2ae63758fcb6247c5e56433645d9252576c755
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996285"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="3735e-105">Placera på vägg – placera i butik</span><span class="sxs-lookup"><span data-stu-id="3735e-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3735e-106">Med funktionen *Placera på vägg – placera i butik* kan du hantera situationer där du måste konsolidera en produkt till ett förpackat mellanlagringsområdet, baserat på konfigurerbara kriterier.</span><span class="sxs-lookup"><span data-stu-id="3735e-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="3735e-107">Eftersom den här funktionen tillåter plockning på en enda målnummer-ID och kan använda fler positioner än för klusterplockning, kommer företag som levererar att lagra eller hantera små artiklar att dra nytta av minskad plockningstid.</span><span class="sxs-lookup"><span data-stu-id="3735e-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="3735e-108">Arbetsflödet för denna funktion riktar plockad produkt till en sorteringsplats för distribution i olika typer av behållare.</span><span class="sxs-lookup"><span data-stu-id="3735e-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="3735e-109">Varje sorteringsplats innehåller i allmänhet flera sorteringspositioner.</span><span class="sxs-lookup"><span data-stu-id="3735e-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="3735e-110">Varje sorteringsposition tilldelas enligt kriterierna som ställs in av affärsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3735e-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="3735e-111">Typiska kriterier är slutdestination, leverans eller last.</span><span class="sxs-lookup"><span data-stu-id="3735e-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="3735e-112">När en produkt har inlevererats distribueras den till varje sorteringsposition, baserat på den kvantitet som är kopplad till ordern, destinationen, försändelsen eller lasten.</span><span class="sxs-lookup"><span data-stu-id="3735e-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="3735e-113">När en behållare är full eller fullständig flyttas den till en mellanlagringsplats eller en leveransplats för ytterligare hantering, beroende på affärsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3735e-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="3735e-114">Dessa lagerfunktioner kallas även andra namn, t.ex. placera i ljus och paus öppna.</span><span class="sxs-lookup"><span data-stu-id="3735e-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="3735e-115">Aktivera funktionen för utgående sortering</span><span class="sxs-lookup"><span data-stu-id="3735e-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="3735e-116">Innan du kan använda funktionen *Placera på vägg – placera i butik* måste funktionen *Utgående sortering* vara aktiverad i systemet.</span><span class="sxs-lookup"><span data-stu-id="3735e-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="3735e-117">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="3735e-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="3735e-118">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3735e-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3735e-119">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="3735e-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="3735e-120">**Funktionsnamn:** *utgående sortering*</span><span class="sxs-lookup"><span data-stu-id="3735e-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="3735e-121">Funktionen *Utgående sortering* kan användas tillsammans med den funktionen *Påfyllnadsstegkod för hela organisationen* om den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="3735e-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="3735e-122">Du måste också aktivera den här funktionen om du vill använda fördefinierade koder som har ställts in i koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="3735e-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="3735e-123">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3735e-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="3735e-124">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="3735e-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="3735e-125">**Funktionsnamn:** *Påfyllnadsstegkod för hela organisationen*</span><span class="sxs-lookup"><span data-stu-id="3735e-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="3735e-126">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="3735e-126">Setup</span></span>

<span data-ttu-id="3735e-127">För denna demo används standard Contoso-data och lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="3735e-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="3735e-128">Vissa tillägg som anges senare används också.</span><span class="sxs-lookup"><span data-stu-id="3735e-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="3735e-129">Platstyp</span><span class="sxs-lookup"><span data-stu-id="3735e-129">Location type</span></span>

1. <span data-ttu-id="3735e-130">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platstyper**.</span><span class="sxs-lookup"><span data-stu-id="3735e-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="3735e-131">I åtgärdsfönstret, välj **Ny** för att skapa en platstyp som ska användas för sortering.</span><span class="sxs-lookup"><span data-stu-id="3735e-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="3735e-132">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-132">Set the following values:</span></span>

    - <span data-ttu-id="3735e-133">**Platstyp:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="3735e-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="3735e-134">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="3735e-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="3735e-136">Parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="3735e-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="3735e-137">Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="3735e-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="3735e-138">På fliken **Allmänt** på snabbfliken **Platstyper** ange fältet **Sortera platstyp** till *SORT*.</span><span class="sxs-lookup"><span data-stu-id="3735e-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="3735e-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="3735e-140">Platsprofiler</span><span class="sxs-lookup"><span data-stu-id="3735e-140">Location profile</span></span>

1. <span data-ttu-id="3735e-141">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="3735e-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="3735e-142">I åtgärdsfönstret, välj **Ny** för att skapa en platsprofil som ska användas för sorteringsplats.</span><span class="sxs-lookup"><span data-stu-id="3735e-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="3735e-143">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="3735e-144">**Platsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="3735e-145">**Namn:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="3735e-146">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="3735e-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3735e-147">**Platsformat:** *PACKET*</span><span class="sxs-lookup"><span data-stu-id="3735e-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="3735e-148">**Platstyp:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="3735e-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="3735e-149">**Använd spårning av ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="3735e-150">**Tillåt blandade artiklar:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="3735e-151">**Tillåt blandade lagerstatusvärden:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="3735e-152">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="3735e-153">Platser</span><span class="sxs-lookup"><span data-stu-id="3735e-153">Locations</span></span>

1. <span data-ttu-id="3735e-154">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.</span><span class="sxs-lookup"><span data-stu-id="3735e-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="3735e-155">Rensa kryssrutan **Generera kontrollsiffra för plats**.</span><span class="sxs-lookup"><span data-stu-id="3735e-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="3735e-156">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="3735e-157">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="3735e-158">**Plats:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="3735e-159">**Platsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="3735e-160">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="3735e-161">Packprofiler</span><span class="sxs-lookup"><span data-stu-id="3735e-161">Packing profiles</span></span>

1. <span data-ttu-id="3735e-162">Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="3735e-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="3735e-163">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="3735e-164">**Förpackningsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="3735e-165">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="3735e-166">**Policyer för packning av behållare:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="3735e-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="3735e-167">**Läge för behållar-ID:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="3735e-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="3735e-168">**Behållartyp:** *LASTPALL 48X48*</span><span class="sxs-lookup"><span data-stu-id="3735e-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="3735e-169">**Skapa behållare automatiskt vid stängning av behållare:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="3735e-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="3735e-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="3735e-171">Koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="3735e-171">Wave step codes</span></span>

<span data-ttu-id="3735e-172">Om du aktiverar funktioner *Påfyllnadsstegkod för hela organisationen* ange följande kod.</span><span class="sxs-lookup"><span data-stu-id="3735e-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="3735e-173">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Koder för påfyllnadssteg**.</span><span class="sxs-lookup"><span data-stu-id="3735e-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="3735e-174">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="3735e-175">**Kod för påfyllnadssteg:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="3735e-176">**Beskrivning för påfyllnadssteg:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="3735e-177">**Typ av påfyllnadssteg:** *Sortera mall*</span><span class="sxs-lookup"><span data-stu-id="3735e-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="3735e-178">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="3735e-179">Mall för utgående sortering</span><span class="sxs-lookup"><span data-stu-id="3735e-179">Outbound sorting template</span></span>

<span data-ttu-id="3735e-180">Sorterings mal len styr om sorteringsbefattningar skapas, vilka kriterier som används och andra attribut för sorteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3735e-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="3735e-181">Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar**.</span><span class="sxs-lookup"><span data-stu-id="3735e-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="3735e-182">I åtgärdsfönstret, välj **Ny** för att skapa en sorteringsmall.</span><span class="sxs-lookup"><span data-stu-id="3735e-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="3735e-183">Ange följande värden i nya mallens rubrik:</span><span class="sxs-lookup"><span data-stu-id="3735e-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="3735e-184">**Mall för utgående sorterings-ID:** *påfyllnadsortering*</span><span class="sxs-lookup"><span data-stu-id="3735e-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="3735e-185">**Beskrivning:** *påfyllnadsortering*</span><span class="sxs-lookup"><span data-stu-id="3735e-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="3735e-186">**Sortera malltyp:** *Lagerpåfyllnad*</span><span class="sxs-lookup"><span data-stu-id="3735e-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="3735e-187">Det här fältet definierar den process som sorteringsmallen används för.</span><span class="sxs-lookup"><span data-stu-id="3735e-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="3735e-188">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="3735e-188">The following values are available:</span></span>

        - <span data-ttu-id="3735e-189">**Lagerpåfyllnad** – sorteringsmallen används för processen *Placera på vägg*.</span><span class="sxs-lookup"><span data-stu-id="3735e-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="3735e-190">Denna malltyp används för att kringgå packstationen och bearbeta inventeringen direkt ur påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="3735e-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="3735e-191">Du kan bara använda den här typen om **sortering** påfyllnadsmetod ingår i påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="3735e-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="3735e-192">**Behållare** – sorteringsmallen används för processen *lastpallbyggnad efter förpackning*.</span><span class="sxs-lookup"><span data-stu-id="3735e-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="3735e-193">Malltyp används för bearbetning av behållare som stängs vid packningsstationen och behöver sorteras på lastpallar.</span><span class="sxs-lookup"><span data-stu-id="3735e-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="3735e-194">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="3735e-195">**Plats:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="3735e-196">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="3735e-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3735e-197">**Sortera verifieringstyp:** *positionsskanning*</span><span class="sxs-lookup"><span data-stu-id="3735e-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="3735e-198">Det här fältet definierar den verifiering som krävs vid sorteringen.</span><span class="sxs-lookup"><span data-stu-id="3735e-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="3735e-199">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="3735e-199">The following values are available:</span></span>

        - <span data-ttu-id="3735e-200">None</span><span class="sxs-lookup"><span data-stu-id="3735e-200">None</span></span>
        - <span data-ttu-id="3735e-201">Skanna ett ID-nummer</span><span class="sxs-lookup"><span data-stu-id="3735e-201">License plate scan</span></span>
        - <span data-ttu-id="3735e-202">Platsskanning</span><span class="sxs-lookup"><span data-stu-id="3735e-202">Position scan</span></span>

    - <span data-ttu-id="3735e-203">**Skapa arbete vi positionsstängning:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="3735e-204">Om detta alternativ är inställt på *Ja*, när positionen är stängd kommer arbetet att skapas för att flytta lager till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="3735e-205">Om den är inställd på *Nej*, lager kommer omedelbart att väljas till beställningen när positionen är stängd.</span><span class="sxs-lookup"><span data-stu-id="3735e-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="3735e-206">**Befattningstilldelning:** *manuell*</span><span class="sxs-lookup"><span data-stu-id="3735e-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="3735e-207">Det här fältet definierar typen av befattningstilldelning.</span><span class="sxs-lookup"><span data-stu-id="3735e-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="3735e-208">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="3735e-208">The following values are available:</span></span>

        - <span data-ttu-id="3735e-209">**Manuell** – användaren måste ange vilken plats som lagret sorteras till.</span><span class="sxs-lookup"><span data-stu-id="3735e-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="3735e-210">**Automatisk** – System kommer automatiskt att leda lagret till en plats som när det är möjligt baseras på sorteringsmallens uppdelningar.</span><span class="sxs-lookup"><span data-stu-id="3735e-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="3735e-211">**Tilldela sorteringsvillkor för position:** *Använd endast tom position*</span><span class="sxs-lookup"><span data-stu-id="3735e-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="3735e-212">Detta fält kontrollerar om inventarier som redan finns på sorteringspositioner beaktas när en position tilldelas för efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="3735e-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="3735e-213">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="3735e-213">The following values are available:</span></span>

        - <span data-ttu-id="3735e-214">**Använd endast tom befattning** – befattningar som redan har lagret kopplat till dem kommer att tas med i beräkningen</span><span class="sxs-lookup"><span data-stu-id="3735e-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="3735e-215">**Anta befattning tom** – alla lager som redan finns på befattningen ignoreras under tilldelningen.</span><span class="sxs-lookup"><span data-stu-id="3735e-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="3735e-216">Alla tillgängliga befattningar kommer att användas.</span><span class="sxs-lookup"><span data-stu-id="3735e-216">All available positions will be used.</span></span>

    - <span data-ttu-id="3735e-217">**Kod för påfyllnadssteg:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="3735e-218">Om funktionen *Påfyllnadsstegkod för hela organisationen* är aktiverad måste påfyllnadsstegkoden *Sortera* också aktiveras i påfyllnadsstegkoder.</span><span class="sxs-lookup"><span data-stu-id="3735e-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="3735e-219">**Automatiskt stängning av sorteringsordning:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="3735e-220">Om det här alternativet ställs in på *Ja* stängs sorteringspositionen automatiskt när allt arbete som kommer till positionen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="3735e-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="3735e-221">**Antal nya sorteringspositioner:** *3*</span><span class="sxs-lookup"><span data-stu-id="3735e-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="3735e-222">Det här fältet definierar det maximala antalet sorteringspositioner som systemet skapar.</span><span class="sxs-lookup"><span data-stu-id="3735e-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="3735e-223">**Prefix för sorteringsposition:** *SP-*</span><span class="sxs-lookup"><span data-stu-id="3735e-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="3735e-224">Det här fältet definierar det prefix som systemet tilldelar före befattningsnumret.</span><span class="sxs-lookup"><span data-stu-id="3735e-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="3735e-225">**Automatiskt packning av sorteringsordning:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="3735e-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="3735e-226">Om det här alternativet ställs in på *Ja* kommer lagret på sorteringsposition att packas in i en behållare när positionen är stängd.</span><span class="sxs-lookup"><span data-stu-id="3735e-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="3735e-227">**Förpackningsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="3735e-228">Det här fältet definierar den packprofil som ska användas när sorteringspositionen packas i en behållare.</span><span class="sxs-lookup"><span data-stu-id="3735e-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="3735e-229">I åtgärdsfönstret, välj **Redigera fråga** för att ange de kriterier som används för den här sorteringsmallen.</span><span class="sxs-lookup"><span data-stu-id="3735e-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="3735e-230">I frågerutan på fliken **Sortering** välj **Ny** för att lägga till en rad och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="3735e-231">**Register:** *Lastinformation*</span><span class="sxs-lookup"><span data-stu-id="3735e-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="3735e-232">**Härlett register:** *Lastinformation*</span><span class="sxs-lookup"><span data-stu-id="3735e-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="3735e-233">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="3735e-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="3735e-234">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="3735e-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="3735e-235">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-235">Select **OK**.</span></span>
1. <span data-ttu-id="3735e-236">Följande meddelande kan visas: "gruppering återställs, fortsätt?"</span><span class="sxs-lookup"><span data-stu-id="3735e-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="3735e-237">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3735e-237">Select **Yes**.</span></span>

    <span data-ttu-id="3735e-238">Knappen **utgående sorterings sorteringsmallens uppdelningar** i åtgärdsfönstret blir tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3735e-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="3735e-239">I åtgärdsfönstret väljer du **utgående sorterings sorteringsmallens uppdelningar**.</span><span class="sxs-lookup"><span data-stu-id="3735e-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="3735e-240">Välj kryssrutan **Gruppera efter fält** till grupp genom leverans-ID.</span><span class="sxs-lookup"><span data-stu-id="3735e-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="3735e-241">Med den här inställningen skapas en sorteringsposition per försändelse som är en behållare i påfyllnaden.</span><span class="sxs-lookup"><span data-stu-id="3735e-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="3735e-242">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="3735e-243">Metoder för bearbetning av påfyllnad</span><span class="sxs-lookup"><span data-stu-id="3735e-243">Wave process methods</span></span>

1. <span data-ttu-id="3735e-244">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="3735e-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="3735e-245">Klicka på **återskapa metoder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="3735e-246">Metoden **Sortering** läggs till i listan över tillgängliga metoder och påfyllnadsmallstypen *leverans* har valts.</span><span class="sxs-lookup"><span data-stu-id="3735e-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="3735e-247">Påfyllnadsmallar</span><span class="sxs-lookup"><span data-stu-id="3735e-247">Wave templates</span></span>

<span data-ttu-id="3735e-248">Redigera påfyllnadsmallen som används för att sortera om påfyllnadsbegäran.</span><span class="sxs-lookup"><span data-stu-id="3735e-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="3735e-249">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="3735e-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="3735e-250">Ställ in fältet **Malltyp för påfyllnad** som *Levereras*.</span><span class="sxs-lookup"><span data-stu-id="3735e-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="3735e-251">Välj den befintliga mallen **62 leveransstandard**.</span><span class="sxs-lookup"><span data-stu-id="3735e-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="3735e-252">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3735e-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3735e-253">Ange följande ändringar på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="3735e-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="3735e-254">Ange alternativet **Bearbeta påfyllnad vid släpp till lagerställe** som *Nej*.</span><span class="sxs-lookup"><span data-stu-id="3735e-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="3735e-255">Ange alternativet **Automatisera släpp av påfyllnad** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="3735e-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="3735e-256">På snabbfliken **metoder** ställer du in metoden **sortering**:</span><span class="sxs-lookup"><span data-stu-id="3735e-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="3735e-257">I rutnätet **återstående metoder** välj **sortering**.</span><span class="sxs-lookup"><span data-stu-id="3735e-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="3735e-258">Välj höger pil för att flytta **sortering** till rutnätet **Valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="3735e-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="3735e-259">I rutnätet **valda metoder** välj **sortering**.</span><span class="sxs-lookup"><span data-stu-id="3735e-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="3735e-260">Ange fältet **Kod för påfyllnadssteg** till *Sortera*.</span><span class="sxs-lookup"><span data-stu-id="3735e-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="3735e-261">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="3735e-262">Menyalternativ på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="3735e-262">Mobile device menu items</span></span>

1. <span data-ttu-id="3735e-263">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="3735e-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="3735e-264">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3735e-265">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="3735e-266">**Menyalternativnamn:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="3735e-267">**Rubrik:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="3735e-268">**Läge:** *Indirekt*</span><span class="sxs-lookup"><span data-stu-id="3735e-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="3735e-269">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="3735e-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="3735e-270">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="3735e-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3735e-271">**Aktivitetskod:** *Utgående sortering*</span><span class="sxs-lookup"><span data-stu-id="3735e-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="3735e-272">**Använd processguide:** *Ja* (standardvärde)</span><span class="sxs-lookup"><span data-stu-id="3735e-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="3735e-273">**Mall för utgående sorterings-ID:** *påfyllnadsortering*</span><span class="sxs-lookup"><span data-stu-id="3735e-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="3735e-274">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="3735e-275">Meny på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="3735e-275">Mobile device menu</span></span>

1. <span data-ttu-id="3735e-276">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="3735e-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="3735e-277">I listan över menyer, välj **Utgående**.</span><span class="sxs-lookup"><span data-stu-id="3735e-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="3735e-278">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3735e-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3735e-279">I rutnätet **Tillgängliga menyer och artiklar** hitta och välj menyalternativet **Sortera** som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="3735e-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="3735e-280">Klicka på högerpilen om du vill flytta **Sortera** till rutnätet **Menystruktur**.</span><span class="sxs-lookup"><span data-stu-id="3735e-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="3735e-281">På det här sättet lägger du till det nya menyalternativet på menyn **Utgående**.</span><span class="sxs-lookup"><span data-stu-id="3735e-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="3735e-282">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="3735e-283">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="3735e-283">Location directives</span></span>

<span data-ttu-id="3735e-284">Du måste skapa platsdirektiv för att vägleda arbetet som skapas efter att sorteringen slutförts.</span><span class="sxs-lookup"><span data-stu-id="3735e-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="3735e-285">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="3735e-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="3735e-286">Välj **Sorterad lagerplockning** i fältet *Typ av arbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="3735e-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="3735e-287">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3735e-288">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="3735e-289">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="3735e-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="3735e-290">**Namn:** *Placera på Baydoor*</span><span class="sxs-lookup"><span data-stu-id="3735e-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="3735e-291">Ange följande värden på snabbfliken **Platsdirektiv**:</span><span class="sxs-lookup"><span data-stu-id="3735e-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3735e-292">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="3735e-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="3735e-293">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="3735e-293">**Site:** *6*</span></span>
    - <span data-ttu-id="3735e-294">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="3735e-295">**Direktivkod:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="3735e-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="3735e-296">**Flera SKU:** *Nr*</span><span class="sxs-lookup"><span data-stu-id="3735e-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="3735e-297">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3735e-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="3735e-298">På snabbfliken **Rader** välj **Ny** och ange sedan följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="3735e-299">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="3735e-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="3735e-300">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="3735e-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="3735e-301">**Från kvantitet:** *0*</span><span class="sxs-lookup"><span data-stu-id="3735e-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="3735e-302">**Till kvantitet:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="3735e-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="3735e-303">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3735e-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="3735e-304">På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="3735e-305">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="3735e-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="3735e-306">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="3735e-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="3735e-307">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="3735e-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="3735e-308">Välj **Spara** så att knappen **Redigera fråga** i snabbfliken **Platsdirektivåtgärder** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3735e-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="3735e-309">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="3735e-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="3735e-310">I dialogrutan för fråga på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*.</span><span class="sxs-lookup"><span data-stu-id="3735e-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="3735e-311">Ställ in fältet **villkor** för den här raden till *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="3735e-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="3735e-312">Bekräfta redigeringen genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="3735e-313">Arbetsklasser</span><span class="sxs-lookup"><span data-stu-id="3735e-313">Work classes</span></span>

1. <span data-ttu-id="3735e-314">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="3735e-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="3735e-315">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3735e-316">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="3735e-317">**Arbetsklass-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="3735e-318">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="3735e-319">**Arbetsordertyp:** *Sorterad lagerplockning*</span><span class="sxs-lookup"><span data-stu-id="3735e-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="3735e-320">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="3735e-321">Arbetsmallar</span><span class="sxs-lookup"><span data-stu-id="3735e-321">Work templates</span></span>

1. <span data-ttu-id="3735e-322">Gå till **Lagerstyrning \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="3735e-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="3735e-323">Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="3735e-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="3735e-324">I rutnätet väljer du arbetsmallen **62 välj för packa**.</span><span class="sxs-lookup"><span data-stu-id="3735e-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="3735e-325">Klicka på **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="3735e-326">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3735e-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3735e-327">På raden där fältet **Fältnamn** anges till *Leverans-ID*, rensa kryssrutan **Gruppera efter detta fält**.</span><span class="sxs-lookup"><span data-stu-id="3735e-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="3735e-328">Välj **Spara** och stäng sedan dialogrutan **Arbetsuppgiftshuvudet delas**.</span><span class="sxs-lookup"><span data-stu-id="3735e-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="3735e-329">Välj **Sorterad lagerplockning** i fältet *Typ av arbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="3735e-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="3735e-330">Skapa en ny arbetsmall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="3735e-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="3735e-331">Ange följande värden i avsnittet **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="3735e-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="3735e-332">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="3735e-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="3735e-333">**Arbetsmall:** *sorterad plockning*</span><span class="sxs-lookup"><span data-stu-id="3735e-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="3735e-334">**Arbetsmallbeskrivning:** *sorterad plockning*</span><span class="sxs-lookup"><span data-stu-id="3735e-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="3735e-335">Välj **Spara** om du vill göra avsnittet **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3735e-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="3735e-336">I avsnittet **Arbetsmallinformation** skapar du två rader.</span><span class="sxs-lookup"><span data-stu-id="3735e-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="3735e-337">Välj **ny** och ange sedan följande värden för rad 1:</span><span class="sxs-lookup"><span data-stu-id="3735e-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="3735e-338">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="3735e-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="3735e-339">**Obligatorisk:** markerad (= *Ja*)</span><span class="sxs-lookup"><span data-stu-id="3735e-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="3735e-340">**Arbetsklass-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="3735e-341">Välj **ny** igen och ange sedan följande värden för rad 2:</span><span class="sxs-lookup"><span data-stu-id="3735e-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="3735e-342">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="3735e-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="3735e-343">**Obligatorisk:** markerad (= *Ja*)</span><span class="sxs-lookup"><span data-stu-id="3735e-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="3735e-344">**Arbetsklass-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="3735e-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="3735e-345">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3735e-346">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="3735e-346">Example scenario</span></span>

<span data-ttu-id="3735e-347">Det här scenariot simulerar en situation där lagerställen lagras i mindre artiklar och måste packas in i rutor innan de skickas, och där funktionerna för förpackningsstationen egentligen inte är lämpliga.</span><span class="sxs-lookup"><span data-stu-id="3735e-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="3735e-348">Arbetare plockar order för flera kunder och olika adresser samtidigt för att öka plockningshastigheten.</span><span class="sxs-lookup"><span data-stu-id="3735e-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="3735e-349">När plockningen har slutförts kommer arbetare till sorteringsplatsen där de plockade artiklarna kan sorteras i rätt ruta utifrån de kriterier som krävs.</span><span class="sxs-lookup"><span data-stu-id="3735e-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="3735e-350">I det här exemplet används leverans-ID för att bestämma rätt låda, eftersom varje leverans har en annan adress.</span><span class="sxs-lookup"><span data-stu-id="3735e-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="3735e-351">När alla artiklar från lasten har packats och sorterats efter leverans, flyttas lådorna till mellanlagringsområdet och slutligen till lastbil.</span><span class="sxs-lookup"><span data-stu-id="3735e-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="3735e-352">Innan du startar scenariot ska du se till att alla standardfunktioner för lagerställe är korrekt inställda för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="3735e-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="3735e-353">Standard Contoso-lagerstället *62* används för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="3735e-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="3735e-354">Standardkonfigurationer har inte ändrats, förutom vad som beskrivs i inställningarna.</span><span class="sxs-lookup"><span data-stu-id="3735e-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="3735e-355">Skapa efterfrågan</span><span class="sxs-lookup"><span data-stu-id="3735e-355">Create demand</span></span>

<span data-ttu-id="3735e-356">Innan du kan visa funktionerna måste du skapa vissa behov.</span><span class="sxs-lookup"><span data-stu-id="3735e-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="3735e-357">I det här scenariot skapar du tre försäljningsorder för tre olika kunder för att simulera olika leveransadresser.</span><span class="sxs-lookup"><span data-stu-id="3735e-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="3735e-358">På det här sättet skapar du tre separata försändelser.</span><span class="sxs-lookup"><span data-stu-id="3735e-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="3735e-359">Innan du skapar försäljningsorder och leveranser måste du se till att plockplatserna har tillräckligt med lager för alla objekt på ordern.</span><span class="sxs-lookup"><span data-stu-id="3735e-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="3735e-360">Granska inställningen platsdirektiv för att bekräfta vilka plockplatser som används för plockning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="3735e-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="3735e-361">Om du måste justera inventeringen kan du skapa manuella rörelser, använda påfyllning eller använda något annat flöde.</span><span class="sxs-lookup"><span data-stu-id="3735e-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="3735e-362">Reservera sedan lagerkvantiteter.</span><span class="sxs-lookup"><span data-stu-id="3735e-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="3735e-363">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="3735e-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3735e-364">Skapa en försäljningsorder för order 1 genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3735e-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="3735e-365">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3735e-366">**Kund:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="3735e-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="3735e-367">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="3735e-368">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-368">Select **OK**.</span></span>
1. <span data-ttu-id="3735e-369">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="3735e-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3735e-370">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-370">Set the following values:</span></span>

    - <span data-ttu-id="3735e-371">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3735e-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3735e-372">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="3735e-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="3735e-373">Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="3735e-374">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="3735e-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="3735e-375">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="3735e-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="3735e-376">Upprepa följande steg för varje försäljningsrad på ordern för att reservera lager för den:</span><span class="sxs-lookup"><span data-stu-id="3735e-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="3735e-377">På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="3735e-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="3735e-378">På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="3735e-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="3735e-379">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-379">Select **Save**.</span></span>

1. <span data-ttu-id="3735e-380">Skapa en försäljningsorder för order 2 genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3735e-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="3735e-381">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3735e-382">**Kund:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="3735e-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="3735e-383">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="3735e-384">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-384">Select **OK**.</span></span>
1. <span data-ttu-id="3735e-385">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="3735e-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3735e-386">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-386">Set the following values:</span></span>

    - <span data-ttu-id="3735e-387">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3735e-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3735e-388">**Kvantitet:** *7*</span><span class="sxs-lookup"><span data-stu-id="3735e-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="3735e-389">Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="3735e-390">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="3735e-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="3735e-391">**Kvantitet:** *3*</span><span class="sxs-lookup"><span data-stu-id="3735e-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="3735e-392">Upprepa följande steg för varje försäljningsrad på ordern för att reservera lager för den:</span><span class="sxs-lookup"><span data-stu-id="3735e-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="3735e-393">På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="3735e-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="3735e-394">På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="3735e-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="3735e-395">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-395">Select **Save**.</span></span>

1. <span data-ttu-id="3735e-396">Skapa en försäljningsorder för order 3 genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3735e-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="3735e-397">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="3735e-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3735e-398">**Kund:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="3735e-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="3735e-399">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="3735e-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="3735e-400">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3735e-400">Select **OK**.</span></span>
1. <span data-ttu-id="3735e-401">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="3735e-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3735e-402">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="3735e-402">Set the following values:</span></span>

    - <span data-ttu-id="3735e-403">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3735e-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3735e-404">**Kvantitet:** *8*</span><span class="sxs-lookup"><span data-stu-id="3735e-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="3735e-405">Följ dessa steg för att reservera lager för försäljningsraden:</span><span class="sxs-lookup"><span data-stu-id="3735e-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="3735e-406">På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="3735e-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="3735e-407">På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="3735e-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="3735e-408">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3735e-408">Select **Save**.</span></span>

<span data-ttu-id="3735e-409">Slutför följande procedur för att frisläppa varje försäljningsorder till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="3735e-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="3735e-410">Tre olika försändelser kommer att skapas.</span><span class="sxs-lookup"><span data-stu-id="3735e-410">Three different shipments will be created.</span></span> <span data-ttu-id="3735e-411">Du kommer sedan att lägga till alla tre försändelser till en ny påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="3735e-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="3735e-412">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="3735e-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3735e-413">I rutnätet väljer du den första försäljningsorder som du skapade.</span><span class="sxs-lookup"><span data-stu-id="3735e-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="3735e-414">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="3735e-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="3735e-415">Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="3735e-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="3735e-416">Upprepa de föregående stegen för att frisläppa försäljningsorder 2 och 3 till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="3735e-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="3735e-417">Observera att det informationsmeddelande som visas anger att en leverans har lagts till i påfyllnaden som skapades när du släppte försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="3735e-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="3735e-418">Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.</span><span class="sxs-lookup"><span data-stu-id="3735e-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="3735e-419">Välj påfyllnads-ID som skapades från frisläppandet av försäljningsorder för att öppna sidan **påfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="3735e-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="3735e-420">På den här sidan visas påfyllnadsdetaljerna.</span><span class="sxs-lookup"><span data-stu-id="3735e-420">This page shows the wave details.</span></span> <span data-ttu-id="3735e-421">Snabbfliken **påfyllnadsrader** visar de försändelser som har skapats.</span><span class="sxs-lookup"><span data-stu-id="3735e-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="3735e-422">Du måste nu skapa arbete för att hämta artiklar från plockplatserna till sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="3735e-423">Välj **Process** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="3735e-424">Under påfyllnadsbearbetning använder sorteringsmetoden sorteringsmallen för att tilldela lagret att sortera positioner.</span><span class="sxs-lookup"><span data-stu-id="3735e-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="3735e-425">När påfyllnadsbearbetning är klar får du ett informationsmeddelande som säger att påfyllnaden har publicerats och arbete har skapats.</span><span class="sxs-lookup"><span data-stu-id="3735e-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="3735e-426">I åtgärdsfönstret på fliken **Påfyllnad** i gruppen **Relaterad information** välj **Arbete** om du vill visa det arbete som har skapats.</span><span class="sxs-lookup"><span data-stu-id="3735e-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="3735e-427">Gör en notering av arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="3735e-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="3735e-428">Gå till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.</span><span class="sxs-lookup"><span data-stu-id="3735e-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="3735e-429">I den vänstra kolumnen kan du visa den avgående sorteringsposition som har skapats för varje leverans.</span><span class="sxs-lookup"><span data-stu-id="3735e-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="3735e-430">På snabbfliken **Sorteringsvillkor för position** kan du visa leverans-ID för den positionen.</span><span class="sxs-lookup"><span data-stu-id="3735e-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="3735e-431">Ett arbets-ID har skapats för att hämta artiklar från plockplatserna till sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="3735e-432">För att slutföra arbetet måste du ha det arbets-ID som skapades under påfyllnadsbearbetningen.</span><span class="sxs-lookup"><span data-stu-id="3735e-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="3735e-433">Försäljningsorder som plockas till sorteringsplatsen</span><span class="sxs-lookup"><span data-stu-id="3735e-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="3735e-434">Logga in på den mobila appen som en arbetare i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="3735e-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="3735e-435">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="3735e-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="3735e-436">I menyn **utgående** välj **försäljningsplockning**.</span><span class="sxs-lookup"><span data-stu-id="3735e-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="3735e-437">Markera fältet **ID** och ange sedan arbets-ID från påfyllnadsbearbetningen.</span><span class="sxs-lookup"><span data-stu-id="3735e-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="3735e-438">Bekräfta din inmatning.</span><span class="sxs-lookup"><span data-stu-id="3735e-438">Confirm your entry.</span></span>

    <span data-ttu-id="3735e-439">Sedan uppmanas du att ange ett målnummer-ID (LP).</span><span class="sxs-lookup"><span data-stu-id="3735e-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="3735e-440">Observera att rad 1 från försäljningsorder 1 är vad som måste plockas och läggas till målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="3735e-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="3735e-441">Artikelnummer, kvantitet, artikelbeskrivning och plockningsplats visas.</span><span class="sxs-lookup"><span data-stu-id="3735e-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="3735e-442">I fältet **Mål-LP** ange ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3735e-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="3735e-443">Du ska välja alla rader som har skapats från den bearbetade påfyllnaden på samma målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="3735e-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="3735e-444">Bekräfta din inmatning.</span><span class="sxs-lookup"><span data-stu-id="3735e-444">Confirm your entry.</span></span>

    <span data-ttu-id="3735e-445">I mobilappen visas nu en serie sidor **Plocka** som pekar dig till plockningsplatsen och till objektet och mängden som måste väljas.</span><span class="sxs-lookup"><span data-stu-id="3735e-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="3735e-446">När den plockade artikeln har lagts till i ID-nummer ska du bekräfta plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="3735e-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="3735e-447">Den sista sidan är arbetet där de plockade artiklarna placeras på sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="3735e-448">Bekräfta det första plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="3735e-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="3735e-449">Nästa plockningsarbete visas.</span><span class="sxs-lookup"><span data-stu-id="3735e-449">The next pick work is shown.</span></span> <span data-ttu-id="3735e-450">Bekräfta plockning.</span><span class="sxs-lookup"><span data-stu-id="3735e-450">Confirm the pick.</span></span>
1. <span data-ttu-id="3735e-451">Fortsätt att bekräfta resten av plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="3735e-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="3735e-452">Det sista steget är att slutföra det införda arbetet.</span><span class="sxs-lookup"><span data-stu-id="3735e-452">The last step is to complete the put work.</span></span> <span data-ttu-id="3735e-453">Bekräfta artikel införseln på sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="3735e-454">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="3735e-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="3735e-455">Avsluta **försäljningsplockningen** i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="3735e-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="3735e-456">Sortering/placera på vägg</span><span class="sxs-lookup"><span data-stu-id="3735e-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="3735e-457">Nu när hela lagret har placerats på sorteringsplatsen måste det vara sorterat på rätt sorteringsposition.</span><span class="sxs-lookup"><span data-stu-id="3735e-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="3735e-458">Logga in på mobilappen.</span><span class="sxs-lookup"><span data-stu-id="3735e-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="3735e-459">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="3735e-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="3735e-460">I menyn **Utgående** väljer du **Sortera** för att börja sortera objekten.</span><span class="sxs-lookup"><span data-stu-id="3735e-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="3735e-461">I fältet **LP/CON** anger du målregistreringsskylt för den plockade försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="3735e-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="3735e-462">Bekräfta din inmatning.</span><span class="sxs-lookup"><span data-stu-id="3735e-462">Confirm your entry.</span></span>
1. <span data-ttu-id="3735e-463">Ange det artikelnummer som ska sorteras först.</span><span class="sxs-lookup"><span data-stu-id="3735e-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="3735e-464">Systemet bestämmer den första sorteringsposition som ska visas.</span><span class="sxs-lookup"><span data-stu-id="3735e-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="3735e-465">Bekräfta sorteringspositionen.</span><span class="sxs-lookup"><span data-stu-id="3735e-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="3735e-466">Du uppmanas att tilldela ett ID-nummer till sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="3735e-467">Välj fältet **LP** ange ett ID-nummer och bekräfta din registrering.</span><span class="sxs-lookup"><span data-stu-id="3735e-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="3735e-468">Eftersom sorteringsposition är relaterad till leverans-ID sorteras de plockade artiklarna i ett ID-nummer som är specifik för den utgående leveransen och försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="3735e-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="3735e-469">På nästa sida visas artikel-ID, kvantitet, sorteringspositions-ID och "från" (plockning) och "till"-licensens ID-nummer (sortering).</span><span class="sxs-lookup"><span data-stu-id="3735e-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="3735e-470">Informationen på den här sidan instruerar dig att sortera den angivna artikeln och kvantiteten från plockningens ID-nummer till sorteringens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3735e-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="3735e-471">Bekräfta sorteringspositionen.</span><span class="sxs-lookup"><span data-stu-id="3735e-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="3735e-472">Sortera posterna på den första sorteringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="3735e-473">När du är klar dirigerar systemet dig till nästa sorteringsposition.</span><span class="sxs-lookup"><span data-stu-id="3735e-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="3735e-474">Upprepa den här processen för alla plockade rader på arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="3735e-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="3735e-475">Du bör även använda den här processen när det finns flera plockrader med samma artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="3735e-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="3735e-476">När du upprepar den här processen för alla artiklar utvärderas villkoren från nästa skannade artikel (arbetsraden) och avgör vilken sorteringsplats som den ska sättas på.</span><span class="sxs-lookup"><span data-stu-id="3735e-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="3735e-477">Du dirigeras automatiskt om till rätt sorteringsposition.</span><span class="sxs-lookup"><span data-stu-id="3735e-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="3735e-478">Beroende på bekräftelseinställningen måste du också bekräfta åtgärden genom att ange positionsnummer eller ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3735e-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3735e-479">Om automatisk sortering har aktiverats är manuell åsidosättning inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="3735e-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="3735e-480">När du är klar öppnas i Microsoft Dynamics 365 Supply Chain Management sidan **Positionstilldelningar för utgående sortering** för att granska status för positioner.</span><span class="sxs-lookup"><span data-stu-id="3735e-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="3735e-481">Om positionerna stängs automatiskt väljer du **Visa stängd** för att visa stängda positioner.</span><span class="sxs-lookup"><span data-stu-id="3735e-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="3735e-482">Observera att transaktioner för sorteringspositioner visas.</span><span class="sxs-lookup"><span data-stu-id="3735e-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="3735e-483">Artikeln och kvantiteten som bearbetades genom positionen visas.</span><span class="sxs-lookup"><span data-stu-id="3735e-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="3735e-484">När du ställer in mallen för utgående sortering ställer du in alternativet **Automatiskt stängning av sorteringsordning** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="3735e-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="3735e-485">Därför stängs positionen automatiskt när den sista förväntade lagerstället har placerats där.</span><span class="sxs-lookup"><span data-stu-id="3735e-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="3735e-486">Sorteringspositionerna har statusen **stängd** och arbetet har skapats för att flytta det sorterade lagret till platsen *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="3735e-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="3735e-487">Slutför det sorterade lagerplockningsarbetet för att flytta lagret till leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="3735e-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="3735e-488">När lagret är klart kan du bekräfta det för leverans.</span><span class="sxs-lookup"><span data-stu-id="3735e-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="3735e-489">För att sorterat lagerplockningsarbete ska bearbetas korrekt, ska en menyartikel för mobila enheter med arbetsklasss-ID där fältet **arbetsordertyp** tälls in för *sorterad lagerplockning* användas för transport och lastningsprocess.</span><span class="sxs-lookup"><span data-stu-id="3735e-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="3735e-490">Avsluta en position manuellt (valfritt)</span><span class="sxs-lookup"><span data-stu-id="3735e-490">Manually close a position (optional)</span></span>

<span data-ttu-id="3735e-491">Om sorteringspositionerna ska stängas manuellt måste alternativet **Automatiskt stängning av sorteringsordning** för mallen för utgående sortering ställas in på *Nej* och stängning måste göras innan lagret kan flyttas till vikdörren.</span><span class="sxs-lookup"><span data-stu-id="3735e-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="3735e-492">Positioner kan stängas på olika sätt:</span><span class="sxs-lookup"><span data-stu-id="3735e-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="3735e-493">Via lagerställeappen:</span><span class="sxs-lookup"><span data-stu-id="3735e-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="3735e-494">Användaren kan skanna ett av artiklarna som redan finns på befattningen och sedan välja **Stäng** för att stänga position.</span><span class="sxs-lookup"><span data-stu-id="3735e-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="3735e-495">Om användaren skannar en behållare som redan har sorterats som behållare visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="3735e-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="3735e-496">Användaren kan dock fortfarande fortsätta att stänga positionen.</span><span class="sxs-lookup"><span data-stu-id="3735e-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="3735e-497">Från sidan Microsoft Dynamics 365 Supply Chain Management sidan **Positionstilldelningar för utgående sortering**:</span><span class="sxs-lookup"><span data-stu-id="3735e-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="3735e-498">Användaren kan välja posten för den utgående sorteringspositionen och sedan välja **stängningsposition** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3735e-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="3735e-499">Tips:</span><span class="sxs-lookup"><span data-stu-id="3735e-499">Tips</span></span>

- <span data-ttu-id="3735e-500">Objekt kan inte flyttas mellan positioner när de har tilldelats en.</span><span class="sxs-lookup"><span data-stu-id="3735e-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="3735e-501">Systemet utvärderar hur många av varje objekt som ska gå till en viss position.</span><span class="sxs-lookup"><span data-stu-id="3735e-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="3735e-502">Sorteringsmallen kan konfigureras så att behållare skapas automatiskt när positioner stängs.</span><span class="sxs-lookup"><span data-stu-id="3735e-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="3735e-503">Den här metoden skapar ett standardbehållar-ID som baseras på den angivna förpackningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="3735e-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3735e-504">När du har skapat rörelsearbete från sorteringsplatsen, får du inte avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="3735e-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="3735e-505">I annat fall kommer positionen och behållarna i den att tas bort från systemet och inte användas för vidare behandling.</span><span class="sxs-lookup"><span data-stu-id="3735e-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="3735e-506">Även lagret tas bort.</span><span class="sxs-lookup"><span data-stu-id="3735e-506">The inventory will also be removed.</span></span>
