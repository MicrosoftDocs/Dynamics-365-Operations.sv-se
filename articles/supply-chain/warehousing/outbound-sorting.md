---
title: Utgående sortering
description: Den här ämnet innehåller information om utgående sortering. Den här funktionen gör det enklare att hantera små behållare och hjälper lagerarbetarna bättre att planera och organisera lastpallkapaciteten i lastbilen.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3c576209a86f776ac424f7fb9f2b606bea774a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828404"
---
# <a name="outbound-sorting"></a><span data-ttu-id="20539-104">Utgående sortering</span><span class="sxs-lookup"><span data-stu-id="20539-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20539-105">Den här funktionen gör det enklare att hantera små behållare och hjälper lagerarbetarna bättre att planera och organisera lastpallkapaciteten i lastbilen.</span><span class="sxs-lookup"><span data-stu-id="20539-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="20539-106">När du använder utgående sortering kan du sortera packade behållare efter rätt lastpall efter att ha varit på en förpackningsstation.</span><span class="sxs-lookup"><span data-stu-id="20539-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="20539-107">Du kan också skapa en packningshierarki.</span><span class="sxs-lookup"><span data-stu-id="20539-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="20539-108">Med den här funktionen kan du bygga lastpallar från behållare som är förpackade via packningsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="20539-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="20539-109">Behållaren skickas inte till den slutgiltiga leveransplatsen som den befinner sig i det ursprungliga förpackningsflödet.</span><span class="sxs-lookup"><span data-stu-id="20539-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="20539-110">I stället kan arbetare stänga behållaren och flytta den till en sorteringstypplats.</span><span class="sxs-lookup"><span data-stu-id="20539-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="20539-111">De kan sedan sortera behållare efter befattningar, som var och en har ID-nummer (LP).</span><span class="sxs-lookup"><span data-stu-id="20539-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="20539-112">När behållarna har sorterats kan arbete skapas för att skicka hela LP till de slutliga leveransplatserna eller fasplatser, baserat på platsdirektiv eller dina egna krav.</span><span class="sxs-lookup"><span data-stu-id="20539-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="20539-113">Dessutom kan lagrets stängningsposition omedelbart flytta lagret till den slutgiltiga leveransplatsen och plocka det till ordern.</span><span class="sxs-lookup"><span data-stu-id="20539-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="20539-114">Aktivera funktionen för utgående sortering</span><span class="sxs-lookup"><span data-stu-id="20539-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="20539-115">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="20539-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="20539-116">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="20539-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="20539-117">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="20539-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="20539-118">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="20539-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="20539-119">**Funktionsnamn:** *utgående sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="20539-120">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="20539-120">Setup</span></span>

<span data-ttu-id="20539-121">I det här scenariot måste du använda standard **USMF** för demodata och lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="20539-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="20539-122">Du måste också slutföra inställningarna som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="20539-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="20539-123">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="20539-123">Set up a wave template</span></span>

<span data-ttu-id="20539-124">Den här inställningen kommer automatiskt bearbeta påfyllnaden och skapa arbete när en rad frisläpps till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20539-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="20539-125">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="20539-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="20539-126">I mallistan välj **lagerställe 62**.</span><span class="sxs-lookup"><span data-stu-id="20539-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="20539-127">På snabbfliken **Allmänt** ser du till att alternativet **Bearbeta påfyllnaden vid släpp till lager** anges till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="20539-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="20539-128">Skapa en arbetare</span><span class="sxs-lookup"><span data-stu-id="20539-128">Set up a worker</span></span>

<span data-ttu-id="20539-129">Förpackningsstationen anses vara en plats.</span><span class="sxs-lookup"><span data-stu-id="20539-129">The packing station is considered a location.</span></span> <span data-ttu-id="20539-130">Lagerarbetare som loggar in på förpackningsstationen kan se och arbeta på endast försändelser och behållare som planeras vid den specifika förpackningsplatsen.</span><span class="sxs-lookup"><span data-stu-id="20539-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="20539-131">En användare som loggar in på Microsoft Dynamics 365 måste ställas in som arbetare i lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="20539-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="20539-132">Om användarens namn inte visas i listan över arbetsuppgifter lägger du till det med hjälp av följande procedur.</span><span class="sxs-lookup"><span data-stu-id="20539-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="20539-133">Dessa steg utgår från att användaren redan finns i systemet och att den har associerats med en medarbetare eller arbetare i modulen **personal**.</span><span class="sxs-lookup"><span data-stu-id="20539-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="20539-134">Gå till **Lagerstyrning \> Inställningar \> Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="20539-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="20539-135">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="20539-135">Select **New**.</span></span>
1. <span data-ttu-id="20539-136">I fältet **Arbetare** väljer du målanvändaren i listan med medarbetare.</span><span class="sxs-lookup"><span data-stu-id="20539-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="20539-137">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="20539-137">Select **Select**.</span></span>
1. <span data-ttu-id="20539-138">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="20539-139">På snabbfliken **Användare** väljer **Ny** för att skapa ett mobilenhetskonto och anger följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="20539-140">**Användar-ID:** Ange ett unikt ID.</span><span class="sxs-lookup"><span data-stu-id="20539-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="20539-141">**Användarnamn:** Ange ett namn på ID.</span><span class="sxs-lookup"><span data-stu-id="20539-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="20539-142">**Standardlagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-143">**Menynamn:** *huvud*</span><span class="sxs-lookup"><span data-stu-id="20539-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="20539-144">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="20539-145">Dialogrutan **Ange lösenord** visas, där du kan skapa ett enkelt lösenord som användaren kan använda för att logga in på mobilappen.</span><span class="sxs-lookup"><span data-stu-id="20539-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="20539-146">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="20539-146">Set the following values:</span></span>

    - <span data-ttu-id="20539-147">**Lösenord:** Ange ett enkelt lösenord.</span><span class="sxs-lookup"><span data-stu-id="20539-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="20539-148">**Bekräfta lösenord:** Ange samma lösenord igen.</span><span class="sxs-lookup"><span data-stu-id="20539-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="20539-149">Välj **Ange lösenord**.</span><span class="sxs-lookup"><span data-stu-id="20539-149">Select **Set password**.</span></span>

    <span data-ttu-id="20539-150">Ett meddelande i åtgärdscentret meddelar att lösenordet har ställts in för den användare som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="20539-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="20539-151">Skapa en platstyp</span><span class="sxs-lookup"><span data-stu-id="20539-151">Create a location type</span></span>

1. <span data-ttu-id="20539-152">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platstyper**.</span><span class="sxs-lookup"><span data-stu-id="20539-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="20539-153">I åtgärdsfönstret väljer du **Ny** för att skapa en platstyp och anger följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="20539-154">**Platstyp:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="20539-155">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="20539-156">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="20539-157">Ställ in parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="20539-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="20539-158">Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="20539-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="20539-159">På fliken **Allmänt** på snabbfliken **Platstyper** ange fältet **Sortera platstyp** till *SORTERA*.</span><span class="sxs-lookup"><span data-stu-id="20539-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="20539-160">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="20539-161">Konfigurera en platsprofil</span><span class="sxs-lookup"><span data-stu-id="20539-161">Set up a location profile</span></span>

1. <span data-ttu-id="20539-162">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="20539-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="20539-163">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-164">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="20539-165">**Platsprofil-ID:** *sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="20539-166">**Namn:** *sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="20539-167">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="20539-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-168">**Platsformat:** *ASRB* (gång-rack-hylla-fack)</span><span class="sxs-lookup"><span data-stu-id="20539-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="20539-169">**Platstyp:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="20539-170">**Använd spårning av ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="20539-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="20539-171">**Tillåt blandade artiklar:** *Ja* (om du ställer in det här alternativet till *Ja* kommer alternativet **Tillåt blandade lagerbatchar** automatiskt till *Ja* och kan inte ändras separat.)</span><span class="sxs-lookup"><span data-stu-id="20539-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="20539-172">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="20539-173">Konfigurera en profil</span><span class="sxs-lookup"><span data-stu-id="20539-173">Set up a location</span></span>

1. <span data-ttu-id="20539-174">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.</span><span class="sxs-lookup"><span data-stu-id="20539-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="20539-175">I rubriken, rensa kryssrutan **Generera kontrollsiffra för plats**.</span><span class="sxs-lookup"><span data-stu-id="20539-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="20539-176">I åtgärdsfönstret väljer du **Ny** för att skapa en plats och anger följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="20539-177">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-178">**Plats:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="20539-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="20539-179">**Platsprofil-ID:** *SORTERAERING*</span><span class="sxs-lookup"><span data-stu-id="20539-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="20539-180">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="20539-181">Ställa in en mall för utgående sortering</span><span class="sxs-lookup"><span data-stu-id="20539-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="20539-182">Mallen för utgående sortering avgör om arbetet skapas utanför sorteringsplatsen och om sortering utförs manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="20539-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="20539-183">I det här scenariot ska du skapa en mall för utgående sortering för att skapa lastpallar efter förpackningsstationen.</span><span class="sxs-lookup"><span data-stu-id="20539-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="20539-184">Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar**.</span><span class="sxs-lookup"><span data-stu-id="20539-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="20539-185">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-186">Ange följande värden i nya mallens rubrik:</span><span class="sxs-lookup"><span data-stu-id="20539-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="20539-187">**Mall för utgående sorterings-ID:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="20539-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="20539-188">**Beskrivning:** *Skapa automatiskt arbete*</span><span class="sxs-lookup"><span data-stu-id="20539-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="20539-189">**Malltyp för utgående sortering:** *Behållare*</span><span class="sxs-lookup"><span data-stu-id="20539-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="20539-190">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-191">**Plats:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="20539-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="20539-192">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="20539-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-193">**Sortera verifieringstyp:** *positionsskanning*</span><span class="sxs-lookup"><span data-stu-id="20539-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="20539-194">**Skapa arbete vi positionsstängning:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="20539-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="20539-195">Om detta alternativ är inställt på *Ja*, när positionen är stängd kommer arbetet att skapas för att flytta lager till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="20539-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="20539-196">Om den är inställd på *Nej*, lager kommer omedelbart att väljas till beställningen när positionen är stängd.</span><span class="sxs-lookup"><span data-stu-id="20539-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="20539-197">**Befattningstilldelning:** *Automatisk*</span><span class="sxs-lookup"><span data-stu-id="20539-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="20539-198">I detta fält anges till *Manuell*, måste användaren ange vilken plats som lagret sorteras till.</span><span class="sxs-lookup"><span data-stu-id="20539-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="20539-199">Om detta anges till *automatisk* kommer systemet automatiskt att leda lagret till en plats som när det är möjligt baseras på sorteringsmallens uppdelningar.</span><span class="sxs-lookup"><span data-stu-id="20539-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="20539-200">Välj **Spara** för att göra knappen **Redigera fråga** i åtgärdsfönstret tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="20539-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="20539-201">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="20539-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="20539-202">I frågeredigeraren, på fliken **Sortering** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="20539-203">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="20539-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="20539-204">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="20539-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="20539-205">**Fält:** *Transportföretag*</span><span class="sxs-lookup"><span data-stu-id="20539-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="20539-206">När du har valt det här värdet kan följande meddelande visas: "fältet transportföretagstjänst är inte ett indexfält.</span><span class="sxs-lookup"><span data-stu-id="20539-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="20539-207">Vill du lägga till sortering i det här? "</span><span class="sxs-lookup"><span data-stu-id="20539-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="20539-208">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="20539-208">Select **Yes**.</span></span>

    - <span data-ttu-id="20539-209">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="20539-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="20539-210">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-210">Select **OK**.</span></span>
1. <span data-ttu-id="20539-211">Följande meddelande kan visas: "gruppering återställs, fortsätt?"</span><span class="sxs-lookup"><span data-stu-id="20539-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="20539-212">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="20539-212">Select **Yes**.</span></span>

    <span data-ttu-id="20539-213">Knappen **utgående sorterings sorteringsmallens uppdelningar** i åtgärdsfönstret blir tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="20539-214">I åtgärdsfönstret väljer du **utgående sorterings sorteringsmallens uppdelningar**.</span><span class="sxs-lookup"><span data-stu-id="20539-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="20539-215">I dialogrutan **Utgående sorteringskriterier** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="20539-216">**Referensregisternamn:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="20539-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="20539-217">**Referensfältnamn:** *Transportföretag*</span><span class="sxs-lookup"><span data-stu-id="20539-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="20539-218">**Gruppera efter fält:** Markera den här kryssrutan om du vill gruppera försändelser per transportföretag.</span><span class="sxs-lookup"><span data-stu-id="20539-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="20539-219">Välj **OK** om du vill spara inställningarna och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="20539-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="20539-220">Ställa in policyer för packning av behållare</span><span class="sxs-lookup"><span data-stu-id="20539-220">Set up container packing policies</span></span>

1. <span data-ttu-id="20539-221">Gå till **Lagerstyrning \> Inställningar \> Behållare \> Policyer för packning av behållare**.</span><span class="sxs-lookup"><span data-stu-id="20539-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="20539-222">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-223">Ange följande värden i nya policyns rubrik:</span><span class="sxs-lookup"><span data-stu-id="20539-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="20539-224">**Policyer för packning av behållare:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="20539-225">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="20539-226">Ange följande värden på snabbfliken **Översikt**:</span><span class="sxs-lookup"><span data-stu-id="20539-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-227">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-228">**Standardplats för sortering:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="20539-229">**Viktenhet:** *kg*</span><span class="sxs-lookup"><span data-stu-id="20539-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="20539-230">**Policyn för stängning av behållare:** *Automatiskt släpp*</span><span class="sxs-lookup"><span data-stu-id="20539-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="20539-231">**Policyn för stängning av behållare:** *Tilldela behållare till utgående sorteringsposition*</span><span class="sxs-lookup"><span data-stu-id="20539-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="20539-232">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="20539-233">Ställa in förpackningsprofiler</span><span class="sxs-lookup"><span data-stu-id="20539-233">Set up packing profiles</span></span>

<span data-ttu-id="20539-234">Skapa en ny förpackningsprofil som ska användas tillsammans med sorteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="20539-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="20539-235">Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="20539-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="20539-236">I åtgärdsfönstret väljer du **Ny** för att skapa en rad och anger följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="20539-237">**Förpackningsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="20539-238">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="20539-239">**Policyer för packning av behållare:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="20539-240">**Läge för behållar-ID:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="20539-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="20539-241">**Behållartyp:** *Kartong-stor*</span><span class="sxs-lookup"><span data-stu-id="20539-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="20539-242">**Skapa behållare automatiskt när behållare stängs:** avmarkerad (= *Nr*)</span><span class="sxs-lookup"><span data-stu-id="20539-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="20539-243">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="20539-244">Ställa in arbetsklasser</span><span class="sxs-lookup"><span data-stu-id="20539-244">Set up work classes</span></span>

<span data-ttu-id="20539-245">Skapa en arbetsklass som ska användas tillsammans med sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="20539-246">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="20539-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="20539-247">I åtgärdsfönstret väljer du **Ny** för att skapa en arbetsklass för sortering och anger följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="20539-248">**Arbetsklass-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="20539-249">**Beskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="20539-250">**Arbetsordertyp:** *Sorterad lagerplockning*</span><span class="sxs-lookup"><span data-stu-id="20539-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="20539-251">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="20539-252">Ställ in menyalternativ för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="20539-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="20539-253">Ställ in menyalternativ för ny lastpallen</span><span class="sxs-lookup"><span data-stu-id="20539-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="20539-254">Skapa en menyartikel för mobila enheter för att skapa lastpallar under sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="20539-255">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="20539-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="20539-256">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-257">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="20539-258">**Menyalternativnamn:** *Lastpallsversion*</span><span class="sxs-lookup"><span data-stu-id="20539-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="20539-259">**Rubrik:** *Lastpallsversion*</span><span class="sxs-lookup"><span data-stu-id="20539-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="20539-260">**Läge:** *Indirekt*</span><span class="sxs-lookup"><span data-stu-id="20539-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="20539-261">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="20539-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="20539-262">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="20539-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-263">**Aktivitetskod:** *Utgående sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="20539-264">När det här fältet är inställt på *Utgående sortering* visas fältet **Mall för utgående sorterings-ID** visas.</span><span class="sxs-lookup"><span data-stu-id="20539-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="20539-265">**Använd processguide:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="20539-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="20539-266">När fältet **Aktivitetskod** anges till *Utgående sortering* anges det här alternativet automatiskt till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="20539-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="20539-267">**Mall för utgående sorterings-ID:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="20539-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="20539-268">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="20539-269">Ställ in menyalternativ för ny lastning</span><span class="sxs-lookup"><span data-stu-id="20539-269">Set up a new loading menu item</span></span>

<span data-ttu-id="20539-270">Skapa sedan ett menyalternativ där användarna kan flytta de sorterade lagerartiklarna till leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="20539-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="20539-271">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="20539-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="20539-272">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-273">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="20539-274">**Menyalternativnamn:** *Lasta från sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="20539-275">**Rubrik:** *Lasta från sortering*</span><span class="sxs-lookup"><span data-stu-id="20539-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="20539-276">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="20539-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="20539-277">**Använd befintligt arbete:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="20539-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="20539-278">På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *Användardirigerat*.</span><span class="sxs-lookup"><span data-stu-id="20539-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="20539-279">På snabbfliken **Arbetsklasser** välj **Ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="20539-280">**Arbetsklass-ID:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="20539-281">**Arbetsordertyp:** *Sorterad lagerplockning*</span><span class="sxs-lookup"><span data-stu-id="20539-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="20539-282">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="20539-283">Ställ in meny för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="20539-283">Set up the mobile device menu</span></span>

<span data-ttu-id="20539-284">Nu måste du lägga till nya menyalternativ på menyn för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="20539-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="20539-285">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="20539-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="20539-286">Välj menyn **Utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="20539-287">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="20539-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="20539-288">I kolumnen **Tillgängliga menyer och artiklar** hitta och välj **Lastpallsversion**.</span><span class="sxs-lookup"><span data-stu-id="20539-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="20539-289">Klicka på högerpilen om du vill flytta **Lastpallsversion** till en kolumn **Menystrukturen**.</span><span class="sxs-lookup"><span data-stu-id="20539-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="20539-290">Använd pil upp och pil ned för att sätta menyalternativet **Lastpallsversion** i önskad position på menyalternativ för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="20539-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="20539-291">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-291">Select **Save**.</span></span>
1. <span data-ttu-id="20539-292">Upprepa den här proceduren om du vill lägga till menyalternativet **Lasta från sortering** till menyn **Utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="20539-293">Ställ in platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="20539-293">Set up location directives</span></span>

<span data-ttu-id="20539-294">*Placering av direktiven* är regler som hjälper till att identifiera och sätta platserna för lager.</span><span class="sxs-lookup"><span data-stu-id="20539-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="20539-295">Du måste nu skapa en regel för att hantera sorteringsarbetet.</span><span class="sxs-lookup"><span data-stu-id="20539-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="20539-296">Ställa in ett SKU-direktiv</span><span class="sxs-lookup"><span data-stu-id="20539-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="20539-297">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="20539-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="20539-298">I den vänstra rutan, ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.</span><span class="sxs-lookup"><span data-stu-id="20539-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="20539-299">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-300">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="20539-301">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-302">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="20539-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="20539-303">Ange följande värden på snabbfliken **Platsdirektiv**:</span><span class="sxs-lookup"><span data-stu-id="20539-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-304">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="20539-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="20539-305">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="20539-305">**Site:** *6*</span></span>
    - <span data-ttu-id="20539-306">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-307">**Flera SKU:** *Nr*</span><span class="sxs-lookup"><span data-stu-id="20539-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="20539-308">Välj **Spara** om du vill göra verktygsfältet för snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="20539-309">På snabbfliken **Rader** välj **Ny** och ange sedan följande värden på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="20539-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="20539-310">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="20539-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="20539-311">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-312">**Från:** *0*</span><span class="sxs-lookup"><span data-stu-id="20539-312">**From:** *0*</span></span>
    - <span data-ttu-id="20539-313">**Till:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="20539-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="20539-314">Välj **Spara** om du vill göra verktygsfältet på snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="20539-315">På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="20539-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="20539-316">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="20539-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="20539-317">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-318">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="20539-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="20539-319">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-319">Select **Save**.</span></span>
1. <span data-ttu-id="20539-320">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="20539-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="20539-321">I frågeredigeraren på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*.</span><span class="sxs-lookup"><span data-stu-id="20539-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="20539-322">Ställ in fältet **villkor** för den här raden till *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="20539-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="20539-323">Välj **OK** om du vill spara dina inställningar och stänga frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="20539-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="20539-324">Ställa in flera SKU-direktiv</span><span class="sxs-lookup"><span data-stu-id="20539-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="20539-325">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="20539-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="20539-326">I den vänstra rutan, ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.</span><span class="sxs-lookup"><span data-stu-id="20539-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="20539-327">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-328">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="20539-329">**Sekvens:** *2*</span><span class="sxs-lookup"><span data-stu-id="20539-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="20539-330">**Namn:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="20539-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="20539-331">Ange följande värden på snabbfliken **Platsdirektiv**:</span><span class="sxs-lookup"><span data-stu-id="20539-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-332">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="20539-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="20539-333">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="20539-333">**Site:** *6*</span></span>
    - <span data-ttu-id="20539-334">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-335">**Flera SKU:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="20539-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="20539-336">Välj **Spara** om du vill göra verktygsfältet för snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="20539-337">På snabbfliken **Rader** välj **Ny** och ange sedan följande värden på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="20539-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="20539-338">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="20539-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="20539-339">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-340">**Från:** *0*</span><span class="sxs-lookup"><span data-stu-id="20539-340">**From:** *0*</span></span>
    - <span data-ttu-id="20539-341">**Till:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="20539-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="20539-342">Välj **Spara** om du vill göra verktygsfältet på snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="20539-343">På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="20539-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="20539-344">Acceptera standardvärden i alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="20539-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="20539-345">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-346">**Namn:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="20539-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="20539-347">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-347">Select **Save**.</span></span>
1. <span data-ttu-id="20539-348">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="20539-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="20539-349">I frågeredigeraren på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*.</span><span class="sxs-lookup"><span data-stu-id="20539-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="20539-350">Ställ in fältet **villkor** för den här raden till *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="20539-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="20539-351">Välj **OK** om du vill spara dina inställningar och stänga frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="20539-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="20539-352">Ställ in arbetsmallar</span><span class="sxs-lookup"><span data-stu-id="20539-352">Set up work templates</span></span>

1. <span data-ttu-id="20539-353">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="20539-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="20539-354">Ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.</span><span class="sxs-lookup"><span data-stu-id="20539-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="20539-355">I åtgärdsfönstret, välj **Ny** för att skapa en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="20539-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="20539-356">Ange följande värden på fliken **Översikt**:</span><span class="sxs-lookup"><span data-stu-id="20539-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="20539-357">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="20539-358">**Kod för arbetsmall:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="20539-359">**Arbetsmallbeskrivning:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="20539-360">Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="20539-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="20539-361">På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="20539-362">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="20539-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="20539-363">**Arbetsklass-ID:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="20539-364">Välj **Ny** igen för att lägga till en andra rad och ställa sedan in följande värden för den:</span><span class="sxs-lookup"><span data-stu-id="20539-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="20539-365">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="20539-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="20539-366">**Arbetsklass-ID:** *SORTERA*</span><span class="sxs-lookup"><span data-stu-id="20539-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="20539-367">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20539-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="20539-368">Scenario</span><span class="sxs-lookup"><span data-stu-id="20539-368">Scenario</span></span>

<span data-ttu-id="20539-369">Det här scenariot simulerar en situation där packade behållare automatiskt ska sorteras mot olika positioner (lastpallar) efter förpackningsstationen, beroende på transportföretagets tjänst.</span><span class="sxs-lookup"><span data-stu-id="20539-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="20539-370">När alla artiklar från lasten har packats upp och sorterats efter adress, flyttas lastpallarna till vikdörren.</span><span class="sxs-lookup"><span data-stu-id="20539-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="20539-371">Skapa försäljningsorder och plockningsarbete</span><span class="sxs-lookup"><span data-stu-id="20539-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="20539-372">Skapa försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="20539-372">Create sales order 1</span></span>

1. <span data-ttu-id="20539-373">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="20539-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="20539-374">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-375">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="20539-376">**Kundkonto:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="20539-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="20539-377">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="20539-378">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="20539-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="20539-379">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="20539-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="20539-380">Växla till vyn **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="20539-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="20539-381">På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="20539-382">**Transportföretag:** *Luftfrakt*</span><span class="sxs-lookup"><span data-stu-id="20539-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="20539-383">**Transportföretag:** *Flyg*</span><span class="sxs-lookup"><span data-stu-id="20539-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="20539-384">Växla till vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="20539-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="20539-385">Om en ny rad inte läggs till automatiskt till rutnätet på snabbfliken **försäljningsorderrader** välj **lägg till rad** för att lägga till en.</span><span class="sxs-lookup"><span data-stu-id="20539-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="20539-386">Ställ in följande värden på den nya orderraden:</span><span class="sxs-lookup"><span data-stu-id="20539-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="20539-387">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="20539-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="20539-388">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="20539-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="20539-389">Medan den nya orderraden fortfarande är markerad på snabbfliken **försäljningsorderrader** väljer du menyn **lager** och **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="20539-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="20539-390">På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20539-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="20539-391">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="20539-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="20539-392">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="20539-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="20539-393">Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern.</span><span class="sxs-lookup"><span data-stu-id="20539-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="20539-394">Anteckna påfyllnadens ID och försändelsens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="20539-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="20539-395">Försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="20539-395">Sales order 2</span></span>

1. <span data-ttu-id="20539-396">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="20539-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="20539-397">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="20539-398">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="20539-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="20539-399">**Kundkonto:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="20539-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="20539-400">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="20539-401">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="20539-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="20539-402">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="20539-402">The new sales order is opened.</span></span> <span data-ttu-id="20539-403">Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="20539-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="20539-404">Ställ in följande värden på denna orderrad:</span><span class="sxs-lookup"><span data-stu-id="20539-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="20539-405">**Artikel:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="20539-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="20539-406">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="20539-407">På snabbfliken **Raddetaljer** på fliken **leverans**, ange fältet **Leveranssätt** till *Flowe-ST*.</span><span class="sxs-lookup"><span data-stu-id="20539-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="20539-408">På snabbfliken **Försäljningsorderrader** välj **Lägg till rad** och ange sedan följande värden på den andra raden:</span><span class="sxs-lookup"><span data-stu-id="20539-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="20539-409">**Artikel:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="20539-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="20539-410">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="20539-411">På snabbfliken **Raddetaljer** på fliken **leverans**, ändra värdet för fältet **Leveranssätt** till *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="20539-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="20539-412">På snabbfliken **Försäljningsorderrader** välj den första orderraden.</span><span class="sxs-lookup"><span data-stu-id="20539-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="20539-413">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="20539-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="20539-414">På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20539-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="20539-415">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="20539-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="20539-416">På snabbfliken **Försäljningsorderrader** välj den andra orderraden.</span><span class="sxs-lookup"><span data-stu-id="20539-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="20539-417">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="20539-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="20539-418">På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20539-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="20539-419">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="20539-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="20539-420">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="20539-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="20539-421">Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern.</span><span class="sxs-lookup"><span data-stu-id="20539-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="20539-422">Observera att två påfyllnads-ID-nummer och två leverans-ID-nummer har skapats, ett för varje leverans sätt för försäljningsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="20539-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="20539-423">Hämta arbets-ID från arbetsinformationen</span><span class="sxs-lookup"><span data-stu-id="20539-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="20539-424">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="20539-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="20539-425">På sidan visas de arbets-ID som har skapats från försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="20539-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="20539-426">Använd påfyllnads-ID och leverans-ID från försäljningsorder som du har skapat för att hitta arbets-ID för varje påfyllnad och leverans.</span><span class="sxs-lookup"><span data-stu-id="20539-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="20539-427">Anteckna dessa arbets-ID eftersom du kommer att behöva dem i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="20539-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="20539-428">Observera att två arbets-ID:n har skapats för den andra försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="20539-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="20539-429">Om olika artiklar plockas från olika platser genereras separata ord-ID:n.</span><span class="sxs-lookup"><span data-stu-id="20539-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="20539-430">Plocka artiklar för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="20539-430">Pick items for the sales orders</span></span>

<span data-ttu-id="20539-431">Slutför det skapade arbetet genom att flytta dem till paketstationen med hjälp av den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="20539-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="20539-432">Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).</span><span class="sxs-lookup"><span data-stu-id="20539-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="20539-433">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="20539-434">I menyn **utgående** välj **försäljningsplockning**.</span><span class="sxs-lookup"><span data-stu-id="20539-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="20539-435">I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="20539-436">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-436">Select **OK**.</span></span>
1. <span data-ttu-id="20539-437">På sidan **försäljningsorder – plocka** anger du en mål LP som skapades för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="20539-438">Observera att plockplatsen (*bulk-001*), artikel (*A0001*) och kvantitet (*2 stycken*) visas.</span><span class="sxs-lookup"><span data-stu-id="20539-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="20539-439">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-439">Select **OK**.</span></span>
1. <span data-ttu-id="20539-440">Granska informationen på sidan **Inköpsorder – placera**.</span><span class="sxs-lookup"><span data-stu-id="20539-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="20539-441">Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.</span><span class="sxs-lookup"><span data-stu-id="20539-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="20539-442">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-442">Select **OK**.</span></span>

    <span data-ttu-id="20539-443">På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete", vilket anger att arbets-ID från försäljningsorder 1 har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="20539-444">Du kommer nu att välja försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="20539-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="20539-445">I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 2 där rad 1 har artikel *A0001*.</span><span class="sxs-lookup"><span data-stu-id="20539-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="20539-446">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-446">Select **OK**.</span></span>
1. <span data-ttu-id="20539-447">På sidan **Försäljningsorder – Placera** anger du mål-LP.</span><span class="sxs-lookup"><span data-stu-id="20539-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="20539-448">Observera att plockplatsen (*bulk-001*), artikel (*A0001*) och kvantitet (*1 stycken*) visas.</span><span class="sxs-lookup"><span data-stu-id="20539-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="20539-449">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-449">Select **OK**.</span></span>
1. <span data-ttu-id="20539-450">Granska informationen på sidan **Inköpsorder – placera**.</span><span class="sxs-lookup"><span data-stu-id="20539-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="20539-451">Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.</span><span class="sxs-lookup"><span data-stu-id="20539-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="20539-452">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-452">Select **OK**.</span></span>

    <span data-ttu-id="20539-453">På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete".</span><span class="sxs-lookup"><span data-stu-id="20539-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="20539-454">Det här meddelandet anger att arbets-ID från rad 1 för försäljningsorder 2 har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="20539-455">I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 2 där rad 2 har artikel *A0002*.</span><span class="sxs-lookup"><span data-stu-id="20539-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="20539-456">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-456">Select **OK**.</span></span>
1. <span data-ttu-id="20539-457">På sidan **Försäljningsorder – Placera** anger du mål-LP.</span><span class="sxs-lookup"><span data-stu-id="20539-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="20539-458">Observera att plockplatsen (*bulk-002*), artikel (*A0001*) och kvantitet (*1 stycken*) visas.</span><span class="sxs-lookup"><span data-stu-id="20539-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="20539-459">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-459">Select **OK**.</span></span>
1. <span data-ttu-id="20539-460">Granska informationen på sidan **Inköpsorder – placera**.</span><span class="sxs-lookup"><span data-stu-id="20539-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="20539-461">Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.</span><span class="sxs-lookup"><span data-stu-id="20539-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="20539-462">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-462">Select **OK**.</span></span>

    <span data-ttu-id="20539-463">På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete".</span><span class="sxs-lookup"><span data-stu-id="20539-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="20539-464">Det här meddelandet anger att arbets-ID från rad 2 för försäljningsorder 2 har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="20539-465">Packa försäljningsorder i behållare</span><span class="sxs-lookup"><span data-stu-id="20539-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="20539-466">Packa försäljningsorder 1 i behållare</span><span class="sxs-lookup"><span data-stu-id="20539-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="20539-467">Gå till **lagerstyrning \> packa och skapa behållare \> packa**.</span><span class="sxs-lookup"><span data-stu-id="20539-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="20539-468">Dialogrutan **Välj packningsstation** visas.</span><span class="sxs-lookup"><span data-stu-id="20539-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="20539-469">Som standard ska fältet **arbetare** vara inställt på namnet på den arbetare som du ställer in tidigare.</span><span class="sxs-lookup"><span data-stu-id="20539-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="20539-470">Ställ in följande värden för att visa och arbeta med försändelser och behållare som planeras på den specifika förpackningsplatsen:</span><span class="sxs-lookup"><span data-stu-id="20539-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="20539-471">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="20539-471">**Site:** *6*</span></span>
    - <span data-ttu-id="20539-472">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="20539-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="20539-473">**Plats:** *Packa*</span><span class="sxs-lookup"><span data-stu-id="20539-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="20539-474">**Förpackningsprofil-ID:** *Sortera*</span><span class="sxs-lookup"><span data-stu-id="20539-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="20539-475">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="20539-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="20539-476">På sidan **Packa** i fältet **ID-nummer eller leverans** ange mål-LP för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="20539-477">Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.</span><span class="sxs-lookup"><span data-stu-id="20539-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="20539-478">Klicka på **Ny behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="20539-479">Godkänn alla standardinställningar och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="20539-480">Gör en notering av behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="20539-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="20539-481">Ange följande värden på snabbfliken **artikelpackning**:</span><span class="sxs-lookup"><span data-stu-id="20539-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-482">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="20539-483">**Identifierare:** Artikel *A0001*</span><span class="sxs-lookup"><span data-stu-id="20539-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="20539-484">Klicka på **Stäng behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="20539-485">I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="20539-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="20539-486">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-486">Select **OK**.</span></span> <span data-ttu-id="20539-487">Behållaren flyttas till platsen *SORTERA* och är klar för sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="20539-488">Skapa en andra behållare för att lägga till den andra artikeln från LP för försäljningsorder 1 till en ny behållare.</span><span class="sxs-lookup"><span data-stu-id="20539-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="20539-489">Klicka på **Ny behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="20539-490">Godkänn alla standardinställningar och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="20539-491">Gör en notering av behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="20539-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="20539-492">Ange följande värden på snabbfliken **artikelpackning**:</span><span class="sxs-lookup"><span data-stu-id="20539-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-493">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="20539-494">**Identifierare:** Artikel *A0001*</span><span class="sxs-lookup"><span data-stu-id="20539-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="20539-495">Klicka på **Stäng behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="20539-496">I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="20539-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="20539-497">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-497">Select **OK**.</span></span> <span data-ttu-id="20539-498">Behållaren flyttas till platsen *SORTERA* och är klar för sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="20539-499">Packa försäljningsorder 2 i behållare</span><span class="sxs-lookup"><span data-stu-id="20539-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="20539-500">På sidan **Packa** i fältet **ID-nummer eller leverans** ange mål-LP för rad 1 i försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="20539-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="20539-501">Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.</span><span class="sxs-lookup"><span data-stu-id="20539-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="20539-502">Klicka på **Ny behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="20539-503">Godkänn alla standardinställningar och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="20539-504">Gör en notering av behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="20539-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="20539-505">Ange följande värden på snabbfliken **artikelpackning**:</span><span class="sxs-lookup"><span data-stu-id="20539-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-506">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="20539-507">**Identifierare:** Artikel *A0001*</span><span class="sxs-lookup"><span data-stu-id="20539-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="20539-508">Klicka på **Stäng behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="20539-509">I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="20539-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="20539-510">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-510">Select **OK**.</span></span> <span data-ttu-id="20539-511">Behållaren flyttas till platsen *SORTERA* och är klar för sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="20539-512">I fältet **ID-nummer eller leverans** ange mål-LP för rad 2 i försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="20539-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="20539-513">Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.</span><span class="sxs-lookup"><span data-stu-id="20539-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="20539-514">Klicka på **Ny behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="20539-515">Godkänn alla standardinställningar och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="20539-516">Gör en notering av behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="20539-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="20539-517">Ange följande värden på snabbfliken **artikelpackning**:</span><span class="sxs-lookup"><span data-stu-id="20539-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20539-518">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="20539-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="20539-519">**Identifierarfält:** artikel *A0002*</span><span class="sxs-lookup"><span data-stu-id="20539-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="20539-520">Klicka på **Stäng behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="20539-521">I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="20539-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="20539-522">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-522">Select **OK**.</span></span> <span data-ttu-id="20539-523">Behållaren flyttas till platsen *SORTERA* och är klar för sortering.</span><span class="sxs-lookup"><span data-stu-id="20539-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="20539-524">Om du vill visa behållardetaljer går du till **Hantering av distributionslager \> Förpackning och skapande av behållare \> behållare** och söker efter de behållar-ID:n som skapades under packningen.</span><span class="sxs-lookup"><span data-stu-id="20539-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="20539-525">Sortera behållarna</span><span class="sxs-lookup"><span data-stu-id="20539-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20539-526">När du öppnar menyalternativet **Lastpallsversion** på mobilappen för att utföra utgående sortering visas en knapp har etiketten **Full**.</span><span class="sxs-lookup"><span data-stu-id="20539-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="20539-527">*Använd inte knappen **Full** för att sortera eller stänga positionen.*</span><span class="sxs-lookup"><span data-stu-id="20539-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="20539-528">Knappen **Full** tillhandahålls som standard och kan inte inaktiveras eller tas bort från sidan.</span><span class="sxs-lookup"><span data-stu-id="20539-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="20539-529">Den används inte för funktionen *Utgående data*.</span><span class="sxs-lookup"><span data-stu-id="20539-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="20539-530">Sortera den första behållaren</span><span class="sxs-lookup"><span data-stu-id="20539-530">Sort the first container</span></span>

1. <span data-ttu-id="20539-531">Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).</span><span class="sxs-lookup"><span data-stu-id="20539-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="20539-532">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="20539-533">I menyn **utgående** välj **Lastpallsversion**.</span><span class="sxs-lookup"><span data-stu-id="20539-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="20539-534">I fältet **LP/Con** ange det första behållar-ID som är associerat med försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="20539-535">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-535">Select **OK**.</span></span>
1. <span data-ttu-id="20539-536">Eftersom det inte finns några sorteringspositioner för närvarande måste du ange en.</span><span class="sxs-lookup"><span data-stu-id="20539-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="20539-537">I fältet **Sorteringsposition-ID** ange *SP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="20539-538">Eftersom ingen LP för närvarande är associerad med sorteringspositionen *SP01*, måste du ange ett.</span><span class="sxs-lookup"><span data-stu-id="20539-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="20539-539">I fältet **LP** anger du *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="20539-540">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-540">Select **OK**.</span></span>
1. <span data-ttu-id="20539-541">Eftersom valideringen av sorteringsposition är aktiverad måste du ange sorteringspositionens ID igen.</span><span class="sxs-lookup"><span data-stu-id="20539-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="20539-542">I fältet **Sorteringsposition-ID** ange *SP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="20539-543">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-543">Select **OK**.</span></span>

    <span data-ttu-id="20539-544">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="20539-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="20539-545">Om du vill visa sorteringspositionen och LP i den går du till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.</span><span class="sxs-lookup"><span data-stu-id="20539-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="20539-546">På sidan **Positionstilldelningar för utgående sortering** visas alla aktiva sorteringspositioner.</span><span class="sxs-lookup"><span data-stu-id="20539-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="20539-547">Fältet **Sortera positionstransaktioner** visar det LP som är kopplat till varje sorteringsposition och de behållare som finns i sorteringspositionen.</span><span class="sxs-lookup"><span data-stu-id="20539-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="20539-548">Lägg märke till att en sorteringsposition finns för närvarande och att snabbfliken **Sortera positionskriterier** visar ett villkor för **Leverans – Transportföretag - flyg**.</span><span class="sxs-lookup"><span data-stu-id="20539-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="20539-549">Sortera de kvarvarande behållarna</span><span class="sxs-lookup"><span data-stu-id="20539-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="20539-550">Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).</span><span class="sxs-lookup"><span data-stu-id="20539-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="20539-551">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="20539-552">I menyn **utgående** välj **Lastpallsversion**.</span><span class="sxs-lookup"><span data-stu-id="20539-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="20539-553">I fältet **LP/Con** ange det andra behållar-ID som är associerat med försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="20539-554">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-554">Select **OK**.</span></span> <span data-ttu-id="20539-555">Eftersom sorteringsmallen är inställd på att sortera automatiskt och det redan finns en sorteringsposition som har matchande kriterier, dirigeras du automatiskt till rätt sorteringsposition.</span><span class="sxs-lookup"><span data-stu-id="20539-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="20539-556">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-556">Select **OK**.</span></span>
1. <span data-ttu-id="20539-557">Bekräfta sorteringspositionens ID för att ange att lagret är på rätt plats.</span><span class="sxs-lookup"><span data-stu-id="20539-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="20539-558">I fältet **Sorteringsposition-ID** ange *SP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="20539-559">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-559">Select **OK**.</span></span>

    <span data-ttu-id="20539-560">Arbetet har slutförts på den andra behållaren från försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="20539-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="20539-561">Du kommer nu att sortera resten av behållarna från försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="20539-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="20539-562">I fältet **LP/Con** ange behållar-ID för behållaren från försäljningsorder 2 som innehåller artikel *A0001*.</span><span class="sxs-lookup"><span data-stu-id="20539-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="20539-563">Eftersom transportföretaget skiljer sig åt, uppmanas du att ange en ny sorteringsposition och tilldela en LP till den positionen.</span><span class="sxs-lookup"><span data-stu-id="20539-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="20539-564">Använd sorteringsposition *SP02* och LP *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="20539-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="20539-565">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-565">Select **OK**.</span></span>
1. <span data-ttu-id="20539-566">Bekräfta sorteringspositionen genom att ange *SP02* i fältet **sorteringspositions-ID**.</span><span class="sxs-lookup"><span data-stu-id="20539-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="20539-567">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-567">Select **OK**.</span></span>

    <span data-ttu-id="20539-568">Arbetet har slutförts på behållaren.</span><span class="sxs-lookup"><span data-stu-id="20539-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="20539-569">I fältet **LP/Con** ange behållar-ID för behållaren från återstående försäljningsorder 2 som innehåller artikel *A0002*.</span><span class="sxs-lookup"><span data-stu-id="20539-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="20539-570">Eftersom transportföretaget är samma som transportföretaget för försäljningsorder 1, visar systemet den befintliga sorteringsposition som har matchande kriterier.</span><span class="sxs-lookup"><span data-stu-id="20539-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="20539-571">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-571">Select **OK**.</span></span>
1. <span data-ttu-id="20539-572">Bekräfta sorteringspositionen genom att ange *SP01* i fältet **sorteringspositions-ID**.</span><span class="sxs-lookup"><span data-stu-id="20539-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="20539-573">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-573">Select **OK**.</span></span>

    <span data-ttu-id="20539-574">Arbetet har slutförts på behållaren.</span><span class="sxs-lookup"><span data-stu-id="20539-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="20539-575">Stäng de utgående sorteringspositionerna</span><span class="sxs-lookup"><span data-stu-id="20539-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="20539-576">När alla lager har sorterats måste positionen stängas innan arbetet kan skapas.</span><span class="sxs-lookup"><span data-stu-id="20539-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="20539-577">Sorterat lagerplockningsarbete kommer att skapas för att ta lagret till vikdörren.</span><span class="sxs-lookup"><span data-stu-id="20539-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="20539-578">Avsluta en position från den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="20539-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="20539-579">Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).</span><span class="sxs-lookup"><span data-stu-id="20539-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="20539-580">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="20539-581">I menyn **utgående** välj **Lastpallsversion**.</span><span class="sxs-lookup"><span data-stu-id="20539-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="20539-582">I fältet **LP/Con** anger du ett behållar-ID som har sorterats för att sortera positionen *SP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="20539-583">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-583">Select **OK**.</span></span>
1. <span data-ttu-id="20539-584">Följande meddelande visas: "behållaren har redan sorterats för att position SP01.</span><span class="sxs-lookup"><span data-stu-id="20539-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="20539-585">Stäng den här positionen?"</span><span class="sxs-lookup"><span data-stu-id="20539-585">Close the position?"</span></span> <span data-ttu-id="20539-586">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="20539-586">Select **Close**.</span></span>

    <span data-ttu-id="20539-587">Arbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="20539-588">Stäng en position från positionstilldelningar för utgående sortering</span><span class="sxs-lookup"><span data-stu-id="20539-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="20539-589">Gå till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.</span><span class="sxs-lookup"><span data-stu-id="20539-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="20539-590">I den vänstra kolumnen, välj **SP02**.</span><span class="sxs-lookup"><span data-stu-id="20539-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="20539-591">Den här utgående sorteringspositionsraden är den som du kommer att stänga.</span><span class="sxs-lookup"><span data-stu-id="20539-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="20539-592">Klicka på **Stäng position** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20539-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="20539-593">Den sorteringspositionens post är stängd och visas inte längre.</span><span class="sxs-lookup"><span data-stu-id="20539-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="20539-594">Om du vill visa alla poster med stängda positioner markerar du kryssrutan **Visa stängda**.</span><span class="sxs-lookup"><span data-stu-id="20539-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="20539-595">Plockning i sorterat lager</span><span class="sxs-lookup"><span data-stu-id="20539-595">Sorted inventory picking</span></span>

<span data-ttu-id="20539-596">Du måste slutföra det sorterade lagerplockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="20539-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="20539-597">När den är avslutad plockas lagret till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="20539-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="20539-598">Vid den punkten gäller alla andra lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="20539-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="20539-599">Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).</span><span class="sxs-lookup"><span data-stu-id="20539-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="20539-600">I huvudmenyn, välj **utgående**.</span><span class="sxs-lookup"><span data-stu-id="20539-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="20539-601">I menyn **Utgående** välj **Lasta från sortering**.</span><span class="sxs-lookup"><span data-stu-id="20539-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="20539-602">Ange mål-LP-ID från den första sorteringspositionen, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="20539-603">Ange fältet **ID** till *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="20539-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="20539-604">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-604">Select **OK**.</span></span>
1. <span data-ttu-id="20539-605">På sidan **Sorterad lagerplockning: Plocka** visas det plockningsarbete som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="20539-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="20539-606">Plocka från platsen *SORTERA* och mål-LP *PLP01*, som har flera artiklar och kvantiteten *3*.</span><span class="sxs-lookup"><span data-stu-id="20539-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="20539-607">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-607">Select **OK**.</span></span>
1. <span data-ttu-id="20539-608">På sidan **Sorterad lagerplockning: Placera** visas det placeringsarbete som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="20539-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="20539-609">Placera på platsen *Vikdörr* och mål-LP *PLP01*, som har flera artiklar och kvantiteten *3*.</span><span class="sxs-lookup"><span data-stu-id="20539-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="20539-610">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-610">Select **OK**.</span></span>

    <span data-ttu-id="20539-611">Arbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-611">Work is completed.</span></span>

1. <span data-ttu-id="20539-612">Ange målnummer-ID från den andra sorteringspositionen *SP02*.</span><span class="sxs-lookup"><span data-stu-id="20539-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="20539-613">Ange fältet **ID** till *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="20539-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="20539-614">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-614">Select **OK**.</span></span>
1. <span data-ttu-id="20539-615">På sidan **Sorterad lagerplockning: Plocka** visas det plockningsarbete som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="20539-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="20539-616">Plocka från platsen *SORTERA* och mål-LP *PLP02*, som har flera artiklar och kvantiteten *1*.</span><span class="sxs-lookup"><span data-stu-id="20539-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="20539-617">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-617">Select **OK**.</span></span>
1. <span data-ttu-id="20539-618">På sidan **Sorterad lagerplockning: Placera** visas det placeringsarbete som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="20539-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="20539-619">Placera på platsen *Vikdörr* och mål-LP *PLP02*, som har flera artiklar och kvantiteten *1*.</span><span class="sxs-lookup"><span data-stu-id="20539-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="20539-620">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20539-620">Select **OK**.</span></span>

    <span data-ttu-id="20539-621">Arbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="20539-621">Work is completed.</span></span>

<span data-ttu-id="20539-622">Från och med denna punkt gäller alla andra lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="20539-622">From this point forward, all other warehouse processes apply.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]