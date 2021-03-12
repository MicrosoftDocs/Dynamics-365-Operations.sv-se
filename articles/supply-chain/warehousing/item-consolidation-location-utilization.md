---
title: Artikelkonsolidering – platsutnyttjande
description: I det här avsnittet finns information om funktioner som gör det enkelt för lagerchefer att visa och filtrera platsens användning över hela lagerstället. Chefer kan välja platser och skapa lagerförflyttningar direkt från sidan artikelkonsolidering för att konsolidera artiklar och därmed bättre utnyttja lagerställets utrymme.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6edabc51981d8935672b44e53b453cfbaca9031b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004662"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="20a7b-104">Artikelkonsolidering – platsutnyttjande</span><span class="sxs-lookup"><span data-stu-id="20a7b-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20a7b-105">I det här avsnittet finns information om funktioner som gör det enkelt för lagerchefer att visa och filtrera platsens användning över hela lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20a7b-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="20a7b-106">Chefer kan välja platser och skapa lagerförflyttningar direkt från sidan **artikelkonsolidering** för att konsolidera artiklar och därmed bättre utnyttja lagerställets utrymme.</span><span class="sxs-lookup"><span data-stu-id="20a7b-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="20a7b-107">Aktivera en funktioner</span><span class="sxs-lookup"><span data-stu-id="20a7b-107">Turn on the features</span></span>

<span data-ttu-id="20a7b-108">Innan du kan använda funktionerna som beskrivs i det här avsnittet måste du aktivera dem i systemet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="20a7b-109">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs.</span><span class="sxs-lookup"><span data-stu-id="20a7b-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="20a7b-110">Aktivera båda följande funktioner i angiven ordning.</span><span class="sxs-lookup"><span data-stu-id="20a7b-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="20a7b-111">(Båda funktionerna gäller för modulen **Lagerstyrning** .)</span><span class="sxs-lookup"><span data-stu-id="20a7b-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="20a7b-112">Distributionslagrets platsstatus</span><span class="sxs-lookup"><span data-stu-id="20a7b-112">Warehouse location status</span></span>
2. <span data-ttu-id="20a7b-113">Utnyttjande av artikelns konsolideringsplats</span><span class="sxs-lookup"><span data-stu-id="20a7b-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="20a7b-114">Distributionslagrets platsstatus</span><span class="sxs-lookup"><span data-stu-id="20a7b-114">Warehouse location status</span></span>

<span data-ttu-id="20a7b-115">Funktionen *platsstatus för lagerställe* lägger till fyra nya fält på sidan **Platser** för att spåra ytterligare information om platsens aktuella status:</span><span class="sxs-lookup"><span data-stu-id="20a7b-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="20a7b-116">**Artikelnummer** – Den artikel som för närvarande finns på platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="20a7b-117">Om lagerstället innehåller flera artiklar är det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="20a7b-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="20a7b-118">**Datum och tid för senaste aktivitet** – Tidsstämpeln för den senaste lagertransaktion som har utförts mot platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="20a7b-119">**Åldersdatum** – Det datum då lagret på platsen förts in i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20a7b-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="20a7b-120">Det här datumet beräknas utifrån ID-numrets åldersdatum.</span><span class="sxs-lookup"><span data-stu-id="20a7b-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="20a7b-121">Även om detta datum är korrekt för platser som är ID-nummerspårade, men är kanske inte korrekt för platser som inte är ID-nummerspårade.</span><span class="sxs-lookup"><span data-stu-id="20a7b-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="20a7b-122">**Platsstatus** – platsens status.</span><span class="sxs-lookup"><span data-stu-id="20a7b-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="20a7b-123">Fyra värden är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="20a7b-123">Four values are available:</span></span>

    - <span data-ttu-id="20a7b-124">**Obestämd** – Platsprofilen kan inte spåra status.</span><span class="sxs-lookup"><span data-stu-id="20a7b-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="20a7b-125">Därför är aktuell status okänd.</span><span class="sxs-lookup"><span data-stu-id="20a7b-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="20a7b-126">**Tom** – Det finns för närvarande inga lager på platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="20a7b-127">**Plockning** – Utgående transaktioner har utförts mot platsen efter den senast var tom.</span><span class="sxs-lookup"><span data-stu-id="20a7b-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="20a7b-128">**Lagring** – Endast ingående transaktioner har utförts sedan platsen senast var tom.</span><span class="sxs-lookup"><span data-stu-id="20a7b-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="20a7b-129">De här fälten gör det möjligt för lagerställechefer att få en bättre översikt över statusen för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20a7b-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="20a7b-130">De möjliggör även mer avancerad rapportering och filtrering.</span><span class="sxs-lookup"><span data-stu-id="20a7b-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="20a7b-131">Ställ in artikelkonsolidering och platsutnyttjande</span><span class="sxs-lookup"><span data-stu-id="20a7b-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="20a7b-132">I det här avsnittet beskrivs hur du förbereder systemet för att använda artikelkonsolidering och platsanvändning.</span><span class="sxs-lookup"><span data-stu-id="20a7b-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="20a7b-133">Procedurerna använder exempelvärden från standard demodata.</span><span class="sxs-lookup"><span data-stu-id="20a7b-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="20a7b-134">Om du planerar att arbeta genom det exempelscenario som finns senare i det här avsnittet väljer du den **USMF** juridiska personen (som innehåller standard demodata) och skapar varje post som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="20a7b-135">Om du inte planerar att arbeta genom exempelscenariot, kan de värden som anges här beaktas som exempel på de typer av inställningar som du måste slutföra för att kunna använda funktionerna.</span><span class="sxs-lookup"><span data-stu-id="20a7b-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="20a7b-136">Frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="20a7b-136">Released product</span></span>

1. <span data-ttu-id="20a7b-137">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="20a7b-138">I fältet **artikelnummer** välj *M9201* och öppna informationssidan.</span><span class="sxs-lookup"><span data-stu-id="20a7b-138">In the **Item number** field, select *M9201*, and open the details page.</span></span>
1. <span data-ttu-id="20a7b-139">I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="20a7b-140">På sidan **fysiska dimensioner** i åtgärdsfönstret väljer du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="20a7b-141">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-141">A new line is added to the grid.</span></span> <span data-ttu-id="20a7b-142">Fältet **artikelnummer** är förval.</span><span class="sxs-lookup"><span data-stu-id="20a7b-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="20a7b-143">Välj *ea* i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="20a7b-144">De återstående fälten på raden ställs in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="20a7b-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="20a7b-145">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="20a7b-145">Select **Save**, and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="20a7b-146">Platsprofiler</span><span class="sxs-lookup"><span data-stu-id="20a7b-146">Location profile</span></span>

1. <span data-ttu-id="20a7b-147">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="20a7b-148">I listan över platsprofiler, välj **FLOOR-05**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="20a7b-149">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="20a7b-150">På snabbfliken **Allmänt** ser du till att båda följande alternativ är inställda på *Ja*:</span><span class="sxs-lookup"><span data-stu-id="20a7b-150">On the **General** FastTab, make sure that both the following options are set to *Yes*:</span></span>

    - <span data-ttu-id="20a7b-151">Aktivera artikel på plats</span><span class="sxs-lookup"><span data-stu-id="20a7b-151">Enable item in location</span></span>
    - <span data-ttu-id="20a7b-152">Aktivera platsens status</span><span class="sxs-lookup"><span data-stu-id="20a7b-152">Enable location status</span></span>

1. <span data-ttu-id="20a7b-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="20a7b-154">Om alternativen **Aktivera artikel på plats** och **Aktivera platsstatus** redan har ställts in på *Ja* går du vidare till anvisningarna för att ställa in snabbfliken **Dimensioner** i steg 10.</span><span class="sxs-lookup"><span data-stu-id="20a7b-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes*, skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="20a7b-155">Om alternativen inte redan har ställts in på *Ja* måste du köra en konsekvenskontroll för modulen **Lagerstyrning** när du har ställt in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="20a7b-155">If the options weren't already set to *Yes*, you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="20a7b-156">Fortsätt i så fall till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="20a7b-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="20a7b-157">Kör konsekvenskontrollen genom att gå till **Systemadministration \> periodiska uppgifter \> databas \> konsekvenskontroll**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="20a7b-158">I dialogrutan **konsekvenskontroll** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20a7b-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="20a7b-159">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="20a7b-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="20a7b-160">**Kontrollera/korrigera:** *Kontrollera*</span><span class="sxs-lookup"><span data-stu-id="20a7b-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="20a7b-161">**Från datum:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="20a7b-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="20a7b-162">**Konsekvenskontroll för lagerplatsstatus:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="20a7b-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="20a7b-163">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="20a7b-164">Ett meddelande visas när konsekvenskontrollen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="20a7b-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="20a7b-165">Öppna [Åtgärdscenter](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) för att visa meddelandet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="20a7b-166">Välj **Meddelandedetaljer** om du vill visa detaljerna.</span><span class="sxs-lookup"><span data-stu-id="20a7b-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="20a7b-167">Om meddelandet om konsekvenskontroll anger "felaktig platsstatusinformation hittades för plats XXXX i lagerställe XX" måste du köra konsekvenskontrollen igen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="20a7b-168">Den här gången anger du fältet **Kontrollera/åtgärda** för att *åtgärda felet*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="20a7b-169">Visa meddelandena och se till att inga fel hittades.</span><span class="sxs-lookup"><span data-stu-id="20a7b-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="20a7b-170">Du måste nu slutföra konfigurationen av platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="20a7b-171">Gå tillbaka till **lagerstyrning \> inställningar \> lager \> platsprofiler**, välj platsprofil **FLOOR-05** och välj sedan **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles**, select location profile **FLOOR-05**, and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="20a7b-172">Ange följande värden på snabbfliken **Dimensioner**:</span><span class="sxs-lookup"><span data-stu-id="20a7b-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20a7b-173">**Volymutnyttjandeprocent:** *100*</span><span class="sxs-lookup"><span data-stu-id="20a7b-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="20a7b-174">**Volymmetod som används för lagerställe:** *Använd platsvolym*</span><span class="sxs-lookup"><span data-stu-id="20a7b-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="20a7b-175">**Faktisk platshöjd:** *10*</span><span class="sxs-lookup"><span data-stu-id="20a7b-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="20a7b-176">**Faktisk platsbredd:** *10*</span><span class="sxs-lookup"><span data-stu-id="20a7b-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="20a7b-177">**Faktiskt platsdjup:** *10*</span><span class="sxs-lookup"><span data-stu-id="20a7b-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="20a7b-178">**Högsta vikt:** *100*</span><span class="sxs-lookup"><span data-stu-id="20a7b-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="20a7b-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="20a7b-180">Menyalternativ på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="20a7b-180">Mobile device menu items</span></span>

1. <span data-ttu-id="20a7b-181">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="20a7b-182">I åtgärdsfönstret, välj **Ny** för att skapa ett menyalternativ som ska användas för sortering.</span><span class="sxs-lookup"><span data-stu-id="20a7b-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="20a7b-183">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="20a7b-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="20a7b-184">**Menyalternativnamn:** *Justera i*</span><span class="sxs-lookup"><span data-stu-id="20a7b-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="20a7b-185">**Rubrik:** *Justera i*</span><span class="sxs-lookup"><span data-stu-id="20a7b-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="20a7b-186">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="20a7b-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="20a7b-187">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="20a7b-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="20a7b-188">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="20a7b-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="20a7b-189">**Arbetsskapandeprocess:** *justering i*</span><span class="sxs-lookup"><span data-stu-id="20a7b-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="20a7b-190">**Lagerjusteringstyper:** *Justera i*</span><span class="sxs-lookup"><span data-stu-id="20a7b-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="20a7b-191">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="20a7b-192">Meny på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="20a7b-192">Mobile device menu</span></span>

1. <span data-ttu-id="20a7b-193">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="20a7b-194">I listan över menyer, välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="20a7b-195">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="20a7b-196">I listan **Tillgängliga menyer och artiklar** hittar du och väljer menyalternativet **Justera i**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="20a7b-197">Klicka på högerpilen om du vill flytta **Justera i** till listan **Menystruktur**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="20a7b-198">På det här sättet lägger du till det nya menyalternativet på den valda menyn.</span><span class="sxs-lookup"><span data-stu-id="20a7b-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="20a7b-199">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="20a7b-200">Rörelsetyper</span><span class="sxs-lookup"><span data-stu-id="20a7b-200">Movement types</span></span>

1. <span data-ttu-id="20a7b-201">Gå till **Lagerstyrning \> Inställningar \> Lager \> Rörelsetyper**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="20a7b-202">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="20a7b-202">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="20a7b-203">**Rörelsetypkod:** *KONSOLIDERA*</span><span class="sxs-lookup"><span data-stu-id="20a7b-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="20a7b-204">**Beskrivning:** *konsolidera platser*</span><span class="sxs-lookup"><span data-stu-id="20a7b-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="20a7b-205">**Arbetsklass-ID:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="20a7b-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="20a7b-206">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="20a7b-207">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="20a7b-207">Example scenario</span></span>

<span data-ttu-id="20a7b-208">I följande scenario används lagerställeappen på en mobil enhet för att göra en lager *justering in* på två platser i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="20a7b-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="20a7b-209">Lägg till lager till platser</span><span class="sxs-lookup"><span data-stu-id="20a7b-209">Add inventory to locations</span></span>

1. <span data-ttu-id="20a7b-210">Logga in på mobila enheten som en användare som är inställd på lagerstället *51*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="20a7b-211">Gå till **lager \> Justera i**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="20a7b-212">Nu ska du ange den första platsjusteringen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="20a7b-213">I uppgiften **Justera i** välj den plats som lagerjusteringen ska göras för.</span><span class="sxs-lookup"><span data-stu-id="20a7b-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="20a7b-214">I fältet **LOC** välj *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="20a7b-215">Bekräfta platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-215">Confirm the location.</span></span>
1. <span data-ttu-id="20a7b-216">Skapa ett ID-nummer för den artikel som ska läggas till på platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="20a7b-217">I fältet **LP** anger du *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="20a7b-218">Bekräfta ID-numret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="20a7b-219">Ange den artikel som ska läggas till i ID-numret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="20a7b-220">I fältet **ITEM** anger du *M9201*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="20a7b-221">Bekräfta artikeln.</span><span class="sxs-lookup"><span data-stu-id="20a7b-221">Confirm the item.</span></span>
1. <span data-ttu-id="20a7b-222">Ange kvantiteten av den artikel som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="20a7b-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="20a7b-223">I fältet **QTY** ange *10*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="20a7b-224">Bekräfta kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="20a7b-224">Confirm the quantity.</span></span>

    <span data-ttu-id="20a7b-225">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="20a7b-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="20a7b-226">Nu ska du ange den andra platsjusteringen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="20a7b-227">I uppgiften **Justera i** välj den plats som lagerjusteringen ska göras för.</span><span class="sxs-lookup"><span data-stu-id="20a7b-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="20a7b-228">I fältet **LOC** välj *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="20a7b-229">Bekräfta platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-229">Confirm the location.</span></span>
1. <span data-ttu-id="20a7b-230">Skapa ett ID-nummer för den artikel som ska läggas till på platsen.</span><span class="sxs-lookup"><span data-stu-id="20a7b-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="20a7b-231">I fältet **LP** anger du *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="20a7b-232">Bekräfta ID-numret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="20a7b-233">Ange den artikel som ska läggas till i ID-numret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="20a7b-234">I fältet **ITEM** anger du *M9201*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="20a7b-235">Bekräfta artikeln.</span><span class="sxs-lookup"><span data-stu-id="20a7b-235">Confirm the item.</span></span>
1. <span data-ttu-id="20a7b-236">Ange kvantiteten av den artikel som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="20a7b-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="20a7b-237">I fältet **QTY** ange *15*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="20a7b-238">Bekräfta kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="20a7b-238">Confirm the quantity.</span></span>

    <span data-ttu-id="20a7b-239">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="20a7b-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="20a7b-240">Välj Meny-knappen (kallas ibland hamburger eller knappen hamburger) och välj sedan **Avbryt** för att avsluta uppgiften **Justering**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="20a7b-241">Konsolidera platser</span><span class="sxs-lookup"><span data-stu-id="20a7b-241">Consolidate locations</span></span>

1. <span data-ttu-id="20a7b-242">Gå till **lagerstyrning \> periodiska uppgifter \> artikelkonsolidering**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="20a7b-243">Välj ett lagerställe att konsolidera för i huvudet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="20a7b-244">I fältet **Lagerställe**, ange *51*.</span><span class="sxs-lookup"><span data-stu-id="20a7b-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="20a7b-245">En post visas för varje plats där artikel *M9201* justeras.</span><span class="sxs-lookup"><span data-stu-id="20a7b-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="20a7b-246">Kolumnen **användningsprocent** visar den tillåtna platsens volymetriska utnyttjande.</span><span class="sxs-lookup"><span data-stu-id="20a7b-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="20a7b-247">Om du vill konsolidera lager markerar du alla lagerställen som måste konsolideras och väljer **konsolidera lager** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20a7b-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="20a7b-248">I dialogrutan **konsolidera lager** anger du plats och rörelsetyp som ska användas för att skapa arbetet för lagerförflyttning.</span><span class="sxs-lookup"><span data-stu-id="20a7b-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="20a7b-249">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="20a7b-249">Set the following values:</span></span>

    - <span data-ttu-id="20a7b-250">**Plats:** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="20a7b-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="20a7b-251">**Rörelsetypkod:** *KONSOLIDERA*</span><span class="sxs-lookup"><span data-stu-id="20a7b-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="20a7b-252">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-252">Select **OK**.</span></span>
1. <span data-ttu-id="20a7b-253">Du får ett informationsmeddelande som visar rörelsearbete som skapades.</span><span class="sxs-lookup"><span data-stu-id="20a7b-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="20a7b-254">Gör en notering av rörelsens arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="20a7b-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="20a7b-255">Visa rörelsens arbete</span><span class="sxs-lookup"><span data-stu-id="20a7b-255">View movement work</span></span>

1. <span data-ttu-id="20a7b-256">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="20a7b-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="20a7b-257">Visa det arbete som har skapats.</span><span class="sxs-lookup"><span data-stu-id="20a7b-257">View the work that was created.</span></span> <span data-ttu-id="20a7b-258">Använd arbets-ID för transport från lagerkonsolideringen om du vill filtrera eller söka i arbetsrutnätet.</span><span class="sxs-lookup"><span data-stu-id="20a7b-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="20a7b-259">I det här scenariot användes en befintlig plats som hade lagret som lager konsolideringsplats.</span><span class="sxs-lookup"><span data-stu-id="20a7b-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="20a7b-260">Därför har endast ett arbets-ID skapats.</span><span class="sxs-lookup"><span data-stu-id="20a7b-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="20a7b-261">Systemet skapar ett arbets-ID för varje förflyttning som måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="20a7b-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="20a7b-262">Om du anger en plats som redan innehåller lager, skapas bara ett arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="20a7b-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="20a7b-263">Om du anger en ny plats skapas två arbets-ID:n.</span><span class="sxs-lookup"><span data-stu-id="20a7b-263">If you specify a new location, two work IDs are created.</span></span>
