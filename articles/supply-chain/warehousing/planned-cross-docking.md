---
title: Planerad direktleverans
description: I det här avsnittet beskrivs avancerad, planerad direktleverans, där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde. Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 49807c90c145eee55fae2d515fd19925eb2d944c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810424"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="88c45-104">Planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="88c45-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88c45-105">I det här avsnittet beskrivs avancerad, planerad direktleverans.</span><span class="sxs-lookup"><span data-stu-id="88c45-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="88c45-106">Direktleverans är en lagerställesprocess där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde.</span><span class="sxs-lookup"><span data-stu-id="88c45-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="88c45-107">Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="88c45-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="88c45-108">Direktleverans låter medarbetare hoppa över inkommande artikelinförsel och utgående plockning av lager som redan har markerats för en utgående order.</span><span class="sxs-lookup"><span data-stu-id="88c45-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="88c45-109">Därför minimeras antalet gånger som lagret vidrörs, om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="88c45-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="88c45-110">Eftersom det är mindre interaktion med systemet ökas dessutom tid och utrymmesbesparingar på lagret.</span><span class="sxs-lookup"><span data-stu-id="88c45-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="88c45-111">Innan direktleverans kan köras måste användaren konfigurera en ny mall för direktleverans där leveranskällan och andra uppsättningar krav för direktleverans har angetts.</span><span class="sxs-lookup"><span data-stu-id="88c45-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="88c45-112">När den utgående ordern skapas måste raden markeras mot en inkommande order som innehåller samma artikel.</span><span class="sxs-lookup"><span data-stu-id="88c45-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="88c45-113">Vid tiden för inleverans av inkommande order identifierar inställningen för direktleverans automatiskt behovet av direktleverans och skapar flyttningsarbetet för den begärda kvantiteten, baserat på inställningen för platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="88c45-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="88c45-114">Lagertransaktioner avregistreras **inte** när jobbet för direktleverans avbryts, även om inställningen för denna funktion aktiveras i parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="88c45-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="88c45-115">Aktivera funktionen planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="88c45-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="88c45-116">Om systemet inte redan har de funktioner som beskrivs i det här avsnittet går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar följande funktioner i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="88c45-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="88c45-117">*Planerad direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="88c45-118">*Mallar för direktleverans med platsdirektiv*</span><span class="sxs-lookup"><span data-stu-id="88c45-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="88c45-119">Ställ in</span><span class="sxs-lookup"><span data-stu-id="88c45-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="88c45-120">Generera om lastbokföringsmetoder</span><span class="sxs-lookup"><span data-stu-id="88c45-120">Regenerate load posting methods</span></span>

<span data-ttu-id="88c45-121">Planerad direktleverans är implementerad som en lastbokföringsmetod.</span><span class="sxs-lookup"><span data-stu-id="88c45-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="88c45-122">När du har aktiverat funktionen måste du generera om metoderna.</span><span class="sxs-lookup"><span data-stu-id="88c45-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="88c45-123">Gå till **Lagerstyrning \> Inställningar \> Lastbokföringsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="88c45-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="88c45-124">Klicka på **återskapa metoder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="88c45-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="88c45-125">När återskapandet är slutfört visas en metod med ett värde för **metodnamn** på *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="88c45-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="88c45-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="88c45-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="88c45-127">Skapa en direktleveransmall.</span><span class="sxs-lookup"><span data-stu-id="88c45-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="88c45-128">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Mallar för direktleverans**.</span><span class="sxs-lookup"><span data-stu-id="88c45-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="88c45-129">I åtgärdsfönstret, välj **Ny** för att skapa en mall.</span><span class="sxs-lookup"><span data-stu-id="88c45-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="88c45-130">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="88c45-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="88c45-131">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="88c45-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="88c45-132">I det här fältet definieras ordningen som mallarna utvärderas i.</span><span class="sxs-lookup"><span data-stu-id="88c45-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="88c45-133">**Mall-ID för direktleverans:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="88c45-134">**Beskrivning:** *lagerställe 51*</span><span class="sxs-lookup"><span data-stu-id="88c45-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="88c45-135">**Frisläppning av efterfrågan:** *Före leverans av inleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="88c45-136">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="88c45-137">Inställningen på snabbfliken **Planering** styr hur mallen fungerar.</span><span class="sxs-lookup"><span data-stu-id="88c45-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="88c45-138">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="88c45-138">Set the following values:</span></span>

    - <span data-ttu-id="88c45-139">**Krav på begäran:** *Inga*</span><span class="sxs-lookup"><span data-stu-id="88c45-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="88c45-140">Det här fältet definierar kraven för efterfrågelager.</span><span class="sxs-lookup"><span data-stu-id="88c45-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="88c45-141">Om behovet måste kopplas till leveransen före frisläppning väljer du markera *markering*.</span><span class="sxs-lookup"><span data-stu-id="88c45-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="88c45-142">Om efter frågan måste vara orderreserverad mot försörjningen före frisläppning väljer du *Orderreservation*.</span><span class="sxs-lookup"><span data-stu-id="88c45-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="88c45-143">**Söka efter typ:** *utleveransplatser*</span><span class="sxs-lookup"><span data-stu-id="88c45-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="88c45-144">Det här fältet definierar om direktleveransen ska använda för produktions-/lastplatserna från leverans, eller om den ska använda platsdirektiv för att hitta sina egna mellanlagrings- eller lastplatser.</span><span class="sxs-lookup"><span data-stu-id="88c45-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="88c45-145">**Arbetsmall:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="88c45-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="88c45-146">Det här fältet definierar arbetsmallen som ska användas när direktleverans skapas.</span><span class="sxs-lookup"><span data-stu-id="88c45-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="88c45-147">**Validera på leveranskvitto igen:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="88c45-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="88c45-148">Det här alternativet anger om leveransen ska omvalideras under inleverans.</span><span class="sxs-lookup"><span data-stu-id="88c45-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="88c45-149">Om det här alternativet har värdet *Ja* kontrolleras både det maximala tidsfönstret och intervallet för utgångsdagar.</span><span class="sxs-lookup"><span data-stu-id="88c45-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="88c45-150">**Direktivkod** Lämna det här fältet tomt</span><span class="sxs-lookup"><span data-stu-id="88c45-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="88c45-151">Med det här alternativet kan platsdirektiv användas för att avgöra vilken som är den bästa platsen att flytta direktutleverans av lager till.</span><span class="sxs-lookup"><span data-stu-id="88c45-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="88c45-152">Du kan ställa in den genom att tilldela en direktivkod till varje relevant direktutleveransmall.</span><span class="sxs-lookup"><span data-stu-id="88c45-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="88c45-153">Varje kod till direktiv identifierar ett unikt platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="88c45-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="88c45-154">**Validera tidsfönster:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="88c45-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="88c45-155">Det här alternativet anger om det maximala tidsfönstret ska utvärderas när en leveranskälla väljs.</span><span class="sxs-lookup"><span data-stu-id="88c45-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="88c45-156">Om det här alternativet är inställt på *Ja* blir fälten som är relaterade till den maximala och minsta tidsfönstret tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="88c45-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="88c45-157">**Maximalt tidsfönster:** *5*</span><span class="sxs-lookup"><span data-stu-id="88c45-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="88c45-158">Detta fält definierar den maximala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="88c45-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="88c45-159">**Enheten maximalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="88c45-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="88c45-160">**Minsta tidsfönster:** *0*</span><span class="sxs-lookup"><span data-stu-id="88c45-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="88c45-161">Detta fält definierar den minimala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="88c45-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="88c45-162">**Enheten minimalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="88c45-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="88c45-163">**Intervall med förfallodagar:** *0*</span><span class="sxs-lookup"><span data-stu-id="88c45-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="88c45-164">*FEFO-kriterier (först utgått, först ut):* Det här fältet definierar det maximala antalet dagar mellan utgångsdatumet för den första utgående batch som för närvarande finns i lagerstället och den batch som inlevereras.</span><span class="sxs-lookup"><span data-stu-id="88c45-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="88c45-165">På snabbfliken **Leveranskällor** anger du vilka typer av leveranser som är giltiga för den här mallen.</span><span class="sxs-lookup"><span data-stu-id="88c45-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="88c45-166">Välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="88c45-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="88c45-167">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="88c45-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="88c45-168">**Leveranskälla:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="88c45-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="88c45-169">Skapa en arbetsklass</span><span class="sxs-lookup"><span data-stu-id="88c45-169">Create a work class</span></span>

1. <span data-ttu-id="88c45-170">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="88c45-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="88c45-171">I åtgärdsfönstret, välj **Ny** för att skapa en arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="88c45-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="88c45-172">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="88c45-172">Set the following values:</span></span>

    - <span data-ttu-id="88c45-173">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="88c45-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="88c45-174">**Beskrivning:** *Direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="88c45-175">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="88c45-176">Skapa en arbetsuppgiftsmall</span><span class="sxs-lookup"><span data-stu-id="88c45-176">Create a work template</span></span>

1. <span data-ttu-id="88c45-177">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="88c45-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="88c45-178">Ange fältet **Inköpsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="88c45-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="88c45-179">I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="88c45-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="88c45-180">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="88c45-181">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="88c45-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="88c45-182">**Arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="88c45-183">**Beskrivning av arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="88c45-184">Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="88c45-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="88c45-185">På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="88c45-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="88c45-186">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="88c45-187">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="88c45-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="88c45-188">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="88c45-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="88c45-189">Välj **Ny** för att lägga till en till rad och ställa in följande värden på den:</span><span class="sxs-lookup"><span data-stu-id="88c45-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="88c45-190">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="88c45-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="88c45-191">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="88c45-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="88c45-192">Välj **Spara** och bekräfta att kryssrutan **Giltig** är markerad för mallen *51 direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="88c45-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="88c45-193">Arbetsklass-ID för arbetstyperna *Plocka* och *Placera* måste vara samma.</span><span class="sxs-lookup"><span data-stu-id="88c45-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="88c45-194">Skapa platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="88c45-194">Create location directives</span></span>

1. <span data-ttu-id="88c45-195">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="88c45-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="88c45-196">I vänster ruta ange fältet **Arbetsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="88c45-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="88c45-197">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="88c45-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="88c45-198">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="88c45-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="88c45-199">**Namn:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="88c45-200">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="88c45-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="88c45-201">**Plats:** *5*</span><span class="sxs-lookup"><span data-stu-id="88c45-201">**Site:** *5*</span></span>
    - <span data-ttu-id="88c45-202">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="88c45-203">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="88c45-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="88c45-204">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="88c45-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="88c45-205">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="88c45-206">**Från kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="88c45-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="88c45-207">**Till kvantitet:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="88c45-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="88c45-208">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="88c45-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="88c45-209">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="88c45-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="88c45-210">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="88c45-211">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="88c45-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="88c45-212">**Användning av fast lagerplats:** *Fasta och ej fasta platser*</span><span class="sxs-lookup"><span data-stu-id="88c45-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="88c45-213">Välj **Spara** så att knappen **Redigera fråga** i verktygsfältet **Platsdirektivåtgärder** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="88c45-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="88c45-214">Välj **Redigera fråga** för att öppna frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="88c45-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="88c45-215">På fliken **Intervall** ser du till att följande två rader har konfigurerats:</span><span class="sxs-lookup"><span data-stu-id="88c45-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="88c45-216">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="88c45-216">Line 1:</span></span>

        - <span data-ttu-id="88c45-217">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="88c45-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="88c45-218">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="88c45-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="88c45-219">**Fält:** *lagerställe*</span><span class="sxs-lookup"><span data-stu-id="88c45-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="88c45-220">**Kriterier:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="88c45-221">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="88c45-221">Line 2:</span></span>

        - <span data-ttu-id="88c45-222">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="88c45-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="88c45-223">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="88c45-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="88c45-224">**Fält:** *Plats*</span><span class="sxs-lookup"><span data-stu-id="88c45-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="88c45-225">**Kriterier:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="88c45-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="88c45-226">Stäng frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="88c45-227">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="88c45-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="88c45-228">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="88c45-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="88c45-229">I listan över menyalternativ i det vänstra fönstret väljer du **inköpsartikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="88c45-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="88c45-230">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="88c45-230">Select **Edit**.</span></span>
1. <span data-ttu-id="88c45-231">På snabbfliken **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="88c45-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="88c45-232">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="88c45-233">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="88c45-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="88c45-234">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="88c45-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="88c45-235">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88c45-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="88c45-236">Scenario</span><span class="sxs-lookup"><span data-stu-id="88c45-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="88c45-237">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="88c45-237">Create a purchase order</span></span>

<span data-ttu-id="88c45-238">Följ stegen nedan när du vill skapa en inköpsorder som leveranskälla.</span><span class="sxs-lookup"><span data-stu-id="88c45-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="88c45-239">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="88c45-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="88c45-240">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="88c45-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="88c45-241">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="88c45-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="88c45-242">**Leverantörskonto:** *104*</span><span class="sxs-lookup"><span data-stu-id="88c45-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="88c45-243">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="88c45-244">Välj **OK** och anteckna ordernumret.</span><span class="sxs-lookup"><span data-stu-id="88c45-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="88c45-245">En ny rad läggs till i rutnätet på snabbfliken **Inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="88c45-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="88c45-246">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="88c45-247">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="88c45-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="88c45-248">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="88c45-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="88c45-249">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="88c45-249">Create a sales order</span></span>

<span data-ttu-id="88c45-250">Följ stegen nedan när du vill skapa en försäljningsorder som behovskälla.</span><span class="sxs-lookup"><span data-stu-id="88c45-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="88c45-251">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="88c45-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="88c45-252">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="88c45-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="88c45-253">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="88c45-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="88c45-254">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="88c45-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="88c45-255">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="88c45-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="88c45-256">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-256">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-257">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="88c45-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="88c45-258">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="88c45-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="88c45-259">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="88c45-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="88c45-260">**Kvantitet:** *3*</span><span class="sxs-lookup"><span data-stu-id="88c45-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="88c45-261">Skapa planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="88c45-261">Create planned cross-docking</span></span>

<span data-ttu-id="88c45-262">Följ dessa steg för att skapa den planerade direktleveransen från försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="88c45-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="88c45-263">På sidan **försäljningsorderinformation** för försäljningsordern som du just skapat, i åtgärdsfönstret på fliken **Lagerställe** i gruppen **Åtgärder** väljer du **Frisläpp till lager**.</span><span class="sxs-lookup"><span data-stu-id="88c45-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="88c45-264">Åtgärden frisläpp till lager skapar en leverans- och lastrad för försäljningsorderraden och försöker allokera lager.</span><span class="sxs-lookup"><span data-stu-id="88c45-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="88c45-265">Du får ett informativt meddelande.</span><span class="sxs-lookup"><span data-stu-id="88c45-265">You receive an informational message.</span></span> <span data-ttu-id="88c45-266">Följande varningsmeddelande visas också: "inget arbete har skapats för påfyllnad XXXX.</span><span class="sxs-lookup"><span data-stu-id="88c45-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="88c45-267">Mer information finns i loggen över arbetsskapande."</span><span class="sxs-lookup"><span data-stu-id="88c45-267">See the work creation history log for details."</span></span> <span data-ttu-id="88c45-268">Det här beteendet förväntas eftersom det inte finns något lager i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="88c45-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="88c45-269">På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Leveransinformation**.</span><span class="sxs-lookup"><span data-stu-id="88c45-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="88c45-270">Sidan **Leveransinformation** visas och visar den leverans som har skapats för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="88c45-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="88c45-271">På snabbfliken **Lastrader** ser du att fältet **Kvantitet i planerad direktleverans** har värdet *3*.</span><span class="sxs-lookup"><span data-stu-id="88c45-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="88c45-272">Eftersom det inte fanns något lager tillgängligt i lagerstället, men en giltig leveranskälla kommer in inom tidsfönstret som definieras i mallen för direktleverans, skapades kvantiteten för direktleverans.</span><span class="sxs-lookup"><span data-stu-id="88c45-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="88c45-273">På snabbfliken **Lastrader** välj **Planerad direktleverans** om du vill visa information om direktleverans som har skapats.</span><span class="sxs-lookup"><span data-stu-id="88c45-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="88c45-274">Bearbeta direktleverans.</span><span class="sxs-lookup"><span data-stu-id="88c45-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="88c45-275">Inleverans av inköpsorder med mobilappen för lagerhantering</span><span class="sxs-lookup"><span data-stu-id="88c45-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="88c45-276">Kvantiteten för 5 tas emot från inköpsordern till mottagningsplatsen och två arbetsuppgifter skapas.</span><span class="sxs-lookup"><span data-stu-id="88c45-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="88c45-277">Det första arbets-ID som skapas har värdet **Arbetsordertyp** för *Direktleverans* och är kopplat till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="88c45-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="88c45-278">Den har kvantiteten 3 och dirigeras till den slutgiltiga leveransplatsen så att den kan skickas direkt.</span><span class="sxs-lookup"><span data-stu-id="88c45-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="88c45-279">Det andra arbets-ID som skapas har värdet **Arbetsordertyp** för *Inköpsorder* och är kopplat till inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="88c45-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="88c45-280">Den innehåller den återstående kvantiteten 2 som inte har direktlevereras och dirigeras till artikelinförseln till lagret.</span><span class="sxs-lookup"><span data-stu-id="88c45-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="88c45-281">Logga in på den mobila enheten för en användare i lager ställe *51*.</span><span class="sxs-lookup"><span data-stu-id="88c45-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="88c45-282">Gå till **inkommande \> inleverans av inköp**.</span><span class="sxs-lookup"><span data-stu-id="88c45-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="88c45-283">I fältet **PONum** anger du inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="88c45-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="88c45-284">I fältet **Kvt**, ange *5*.</span><span class="sxs-lookup"><span data-stu-id="88c45-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="88c45-285">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-285">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-286">På nästa sida anger du fältet **artikel** till *A0001*.</span><span class="sxs-lookup"><span data-stu-id="88c45-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="88c45-287">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-287">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-288">På nästa sida bekräfta värdena **PONum**, **Artikel** och **Kvt** genom att klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="88c45-289">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="88c45-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="88c45-290">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="88c45-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="88c45-291">Artikelinförsel till direktleverans och bulk</span><span class="sxs-lookup"><span data-stu-id="88c45-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="88c45-292">För närvarande har båda arbets-ID:n samma ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="88c45-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="88c45-293">För att slutföra de kommande stegen måste du ha arbets-ID:t och målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="88c45-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="88c45-294">Den här informationen kan du få från arbetsuppgifterna för inköpsorderraden och försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="88c45-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="88c45-295">Du kan också gå till information om **Lagerstyrning \> Arbete \> Arbetsinformation** och filtrera fram det arbete där värde **Lagerstället** är *51*.</span><span class="sxs-lookup"><span data-stu-id="88c45-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="88c45-296">Gå till den mobila enheten **Inkommande \> Inköpsartikelinförsel** och ange målnummer-ID från arbetet.</span><span class="sxs-lookup"><span data-stu-id="88c45-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="88c45-297">I fältet **ID** ange målnummer-ID från arbetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="88c45-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="88c45-298">Plocksidan för direktleverans visar plockplatsen (*RECV*), målnummer-ID (*ID-nummer*), artikel (*A0001*) och kvantitet (*3*).</span><span class="sxs-lookup"><span data-stu-id="88c45-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="88c45-299">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-299">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-300">I fältet **Mål LP** anger du en målnummer-ID för det licensserver-ID som ska placeras (direktlevereras) på leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="88c45-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="88c45-301">Du kan välja valfritt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="88c45-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="88c45-302">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-302">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-303">På nästa sida i fältet **ID** ange målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="88c45-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="88c45-304">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-304">Select **OK**.</span></span>
1. <span data-ttu-id="88c45-305">Bekräfta arbetet för plockning av resterande kvantitet av 2 och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="88c45-306">På nästa sida väljer **Klar** för att avsluta plockningsprocessen och påbörjar artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="88c45-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="88c45-307">I mobilappen får du en plats och ett ID-nummer platta att inlagra artikeln i.</span><span class="sxs-lookup"><span data-stu-id="88c45-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="88c45-308">Bekräfta masslagringen **Placera** genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="88c45-309">På nästa sida bekräfta direktleverans **Placera** och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c45-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="88c45-310">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="88c45-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="88c45-311">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="88c45-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="88c45-312">Följande illustration visar hur det slutförda direktleveransen kan visas i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="88c45-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="88c45-313">![Direktleveransarbete har slutförts](media/PlannedCrossDockingWork.png "Direktleveransarbete har slutförts")</span><span class="sxs-lookup"><span data-stu-id="88c45-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]