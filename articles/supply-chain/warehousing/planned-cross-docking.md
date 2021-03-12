---
title: Planerad direktleverans
description: I det här avsnittet beskrivs avancerad, planerad direktleverans, där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde. Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: fb598b3ac7dd72e8c500f0c2eaf07462009c67f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970316"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="b0566-104">Planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="b0566-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0566-105">I det här avsnittet beskrivs avancerad, planerad direktleverans.</span><span class="sxs-lookup"><span data-stu-id="b0566-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="b0566-106">Direktleverans är en lagerställesprocess där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde.</span><span class="sxs-lookup"><span data-stu-id="b0566-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="b0566-107">Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="b0566-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="b0566-108">Direktleverans låter medarbetare hoppa över inkommande artikelinförsel och utgående plockning av lager som redan har markerats för en utgående order.</span><span class="sxs-lookup"><span data-stu-id="b0566-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="b0566-109">Därför minimeras antalet gånger som lagret vidrörs, om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="b0566-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="b0566-110">Eftersom det är mindre interaktion med systemet ökas dessutom tid och utrymmesbesparingar på lagret.</span><span class="sxs-lookup"><span data-stu-id="b0566-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="b0566-111">Innan direktleverans kan köras måste användaren konfigurera en ny mall för direktleverans där leveranskällan och andra uppsättningar krav för direktleverans har angetts.</span><span class="sxs-lookup"><span data-stu-id="b0566-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="b0566-112">När den utgående ordern skapas måste raden markeras mot en inkommande order som innehåller samma artikel.</span><span class="sxs-lookup"><span data-stu-id="b0566-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="b0566-113">Vid tiden för inleverans av inkommande order identifierar inställningen för direktleverans automatiskt behovet av direktleverans och skapar flyttningsarbetet för den begärda kvantiteten, baserat på inställningen för platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="b0566-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="b0566-114">Lagertransaktioner avregistreras **inte** när jobbet för direktleverans avbryts, även om inställningen för denna funktion aktiveras i parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="b0566-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-feature"></a><span data-ttu-id="b0566-115">Aktivera funktionen planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="b0566-115">Turn on the Planned cross docking feature</span></span>

<span data-ttu-id="b0566-116">Innan du kan använda funktionen avancerad direktleverans måste funktionen aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="b0566-116">Before you can use advanced planned cross-docking, the feature must be turned on in your system.</span></span> <span data-ttu-id="b0566-117">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b0566-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b0566-118">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b0566-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b0566-119">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="b0566-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b0566-120">**Funktionens namn:** *Planerad direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-120">**Feature name:** *Planned cross docking*</span></span>

## <a name="setup"></a><span data-ttu-id="b0566-121">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="b0566-121">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="b0566-122">Generera om lastbokföringsmetoder</span><span class="sxs-lookup"><span data-stu-id="b0566-122">Regenerate load posting methods</span></span>

<span data-ttu-id="b0566-123">Planerad direktleverans är implementerad som en lastbokföringsmetod.</span><span class="sxs-lookup"><span data-stu-id="b0566-123">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="b0566-124">När du har aktiverat funktionen måste du generera om metoderna.</span><span class="sxs-lookup"><span data-stu-id="b0566-124">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="b0566-125">Gå till **Lagerstyrning \> Inställningar \> Lastbokföringsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="b0566-125">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="b0566-126">Klicka på **återskapa metoder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b0566-126">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="b0566-127">När återskapandet är slutfört visas en metod med ett värde för **metodnamn** på *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="b0566-127">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="b0566-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b0566-128">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="b0566-129">Skapa en direktleveransmall.</span><span class="sxs-lookup"><span data-stu-id="b0566-129">Create a cross-docking template</span></span>

1. <span data-ttu-id="b0566-130">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Mallar för direktleverans**.</span><span class="sxs-lookup"><span data-stu-id="b0566-130">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="b0566-131">I åtgärdsfönstret, välj **Ny** för att skapa en mall.</span><span class="sxs-lookup"><span data-stu-id="b0566-131">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="b0566-132">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="b0566-132">In the header, set the following values:</span></span>

    - <span data-ttu-id="b0566-133">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0566-133">**Sequence:** *1*</span></span>

        <span data-ttu-id="b0566-134">I det här fältet definieras ordningen som mallarna utvärderas i.</span><span class="sxs-lookup"><span data-stu-id="b0566-134">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="b0566-135">**Mall-ID för direktleverans:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-135">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="b0566-136">**Beskrivning:** *lagerställe 51*</span><span class="sxs-lookup"><span data-stu-id="b0566-136">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="b0566-137">**Frisläppning av efterfrågan:** *Före leverans av inleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-137">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="b0566-138">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-138">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b0566-139">Inställningen på snabbfliken **Planering** styr hur mallen fungerar.</span><span class="sxs-lookup"><span data-stu-id="b0566-139">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="b0566-140">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="b0566-140">Set the following values:</span></span>

    - <span data-ttu-id="b0566-141">**Krav på begäran:** *Inga*</span><span class="sxs-lookup"><span data-stu-id="b0566-141">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="b0566-142">Det här fältet definierar kraven för efterfrågelager.</span><span class="sxs-lookup"><span data-stu-id="b0566-142">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="b0566-143">Om behovet måste kopplas till leveransen före frisläppning väljer du markera *markering*.</span><span class="sxs-lookup"><span data-stu-id="b0566-143">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="b0566-144">Om efter frågan måste vara orderreserverad mot försörjningen före frisläppning väljer du *Orderreservation*.</span><span class="sxs-lookup"><span data-stu-id="b0566-144">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="b0566-145">**Söka efter typ:** *utleveransplatser*</span><span class="sxs-lookup"><span data-stu-id="b0566-145">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="b0566-146">Det här fältet definierar om direktleveransen ska använda för produktions-/lastplatserna från leverans, eller om den ska använda platsdirektiv för att hitta sina egna mellanlagrings- eller lastplatser.</span><span class="sxs-lookup"><span data-stu-id="b0566-146">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="b0566-147">**Arbetsmall:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="b0566-147">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="b0566-148">Det här fältet definierar arbetsmallen som ska användas när direktleverans skapas.</span><span class="sxs-lookup"><span data-stu-id="b0566-148">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="b0566-149">**Validera på leveranskvitto igen:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="b0566-149">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="b0566-150">Det här alternativet anger om leveransen ska omvalideras under inleverans.</span><span class="sxs-lookup"><span data-stu-id="b0566-150">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="b0566-151">Om det här alternativet har värdet *Ja* kontrolleras både det maximala tidsfönstret och intervallet för utgångsdagar.</span><span class="sxs-lookup"><span data-stu-id="b0566-151">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="b0566-152">**Validera tidsfönster:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="b0566-152">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="b0566-153">Det här alternativet anger om det maximala tidsfönstret ska utvärderas när en leveranskälla väljs.</span><span class="sxs-lookup"><span data-stu-id="b0566-153">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="b0566-154">Om det här alternativet är inställt på *Ja* blir fälten som är relaterade till den maximala och minsta tidsfönstret tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b0566-154">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="b0566-155">**Maximalt tidsfönster:** *5*</span><span class="sxs-lookup"><span data-stu-id="b0566-155">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="b0566-156">Detta fält definierar den maximala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="b0566-156">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b0566-157">**Enheten maximalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="b0566-157">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b0566-158">**Minsta tidsfönster:** *0*</span><span class="sxs-lookup"><span data-stu-id="b0566-158">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="b0566-159">Detta fält definierar den minimala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="b0566-159">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b0566-160">**Enheten minimalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="b0566-160">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b0566-161">**Intervall med förfallodagar:** *0*</span><span class="sxs-lookup"><span data-stu-id="b0566-161">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="b0566-162">*FEFO-kriterier (först utgått, först ut):* Det här fältet definierar det maximala antalet dagar mellan utgångsdatumet för den första utgående batch som för närvarande finns i lagerstället och den batch som inlevereras.</span><span class="sxs-lookup"><span data-stu-id="b0566-162">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="b0566-163">På snabbfliken **Leveranskällor** anger du vilka typer av leveranser som är giltiga för den här mallen.</span><span class="sxs-lookup"><span data-stu-id="b0566-163">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="b0566-164">Välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="b0566-164">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b0566-165">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0566-165">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b0566-166">**Leveranskälla:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="b0566-166">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="b0566-167">Skapa en arbetsklass</span><span class="sxs-lookup"><span data-stu-id="b0566-167">Create a work class</span></span>

1. <span data-ttu-id="b0566-168">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="b0566-168">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="b0566-169">I åtgärdsfönstret, välj **Ny** för att skapa en arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="b0566-169">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="b0566-170">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="b0566-170">Set the following values:</span></span>

    - <span data-ttu-id="b0566-171">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b0566-171">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b0566-172">**Beskrivning:** *Direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-172">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="b0566-173">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-173">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="b0566-174">Skapa en arbetsuppgiftsmall</span><span class="sxs-lookup"><span data-stu-id="b0566-174">Create a work template</span></span>

1. <span data-ttu-id="b0566-175">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="b0566-175">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b0566-176">Ange fältet **Inköpsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="b0566-176">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b0566-177">I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="b0566-177">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="b0566-178">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-178">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0566-179">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0566-179">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b0566-180">**Arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-180">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="b0566-181">**Beskrivning av arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-181">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="b0566-182">Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b0566-182">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="b0566-183">På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b0566-183">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b0566-184">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-184">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0566-185">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="b0566-185">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="b0566-186">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b0566-186">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b0566-187">Välj **Ny** för att lägga till en till rad och ställa in följande värden på den:</span><span class="sxs-lookup"><span data-stu-id="b0566-187">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="b0566-188">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="b0566-188">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b0566-189">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b0566-189">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b0566-190">Välj **Spara** och bekräfta att kryssrutan **Giltig** är markerad för mallen *51 direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="b0566-190">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="b0566-191">Arbetsklass-ID för arbetstyperna *Plocka* och *Placera* måste vara samma.</span><span class="sxs-lookup"><span data-stu-id="b0566-191">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="b0566-192">Skapa platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="b0566-192">Create location directives</span></span>

1. <span data-ttu-id="b0566-193">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="b0566-193">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b0566-194">I vänster ruta ange fältet **Arbetsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="b0566-194">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b0566-195">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="b0566-195">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="b0566-196">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0566-196">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b0566-197">**Namn:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-197">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="b0566-198">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="b0566-198">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b0566-199">**Plats:** *5*</span><span class="sxs-lookup"><span data-stu-id="b0566-199">**Site:** *5*</span></span>
    - <span data-ttu-id="b0566-200">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-200">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b0566-201">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b0566-201">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="b0566-202">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b0566-202">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b0566-203">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-203">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0566-204">**Från kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="b0566-204">**From quantity:** *1*</span></span>
    - <span data-ttu-id="b0566-205">**Till kvantitet:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="b0566-205">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="b0566-206">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b0566-206">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b0566-207">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b0566-207">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b0566-208">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0566-209">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b0566-209">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="b0566-210">**Användning av fast lagerplats:** *Fasta och ej fasta platser*</span><span class="sxs-lookup"><span data-stu-id="b0566-210">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="b0566-211">Välj **Spara** så att knappen **Redigera fråga** i verktygsfältet **Platsdirektivåtgärder** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b0566-211">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="b0566-212">Välj **Redigera fråga** för att öppna frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="b0566-212">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="b0566-213">På fliken **Intervall** ser du till att följande två rader har konfigurerats:</span><span class="sxs-lookup"><span data-stu-id="b0566-213">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="b0566-214">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="b0566-214">Line 1:</span></span>

        - <span data-ttu-id="b0566-215">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="b0566-215">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b0566-216">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="b0566-216">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b0566-217">**Fält:** *lagerställe*</span><span class="sxs-lookup"><span data-stu-id="b0566-217">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="b0566-218">**Kriterier:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-218">**Criteria:** *51*</span></span>

    - <span data-ttu-id="b0566-219">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="b0566-219">Line 2:</span></span>

        - <span data-ttu-id="b0566-220">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="b0566-220">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b0566-221">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="b0566-221">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b0566-222">**Fält:** *Plats*</span><span class="sxs-lookup"><span data-stu-id="b0566-222">**Field:** *Location*</span></span>
        - <span data-ttu-id="b0566-223">**Kriterier:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b0566-223">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="b0566-224">Stäng frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-224">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="b0566-225">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="b0566-225">Create a mobile device menu item</span></span>

1. <span data-ttu-id="b0566-226">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="b0566-226">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b0566-227">I listan över menyalternativ i det vänstra fönstret väljer du **inköpsartikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="b0566-227">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="b0566-228">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b0566-228">Select **Edit**.</span></span>
1. <span data-ttu-id="b0566-229">På snabbfliken **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b0566-229">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b0566-230">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-230">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0566-231">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b0566-231">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b0566-232">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="b0566-232">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="b0566-233">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b0566-233">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b0566-234">Scenario</span><span class="sxs-lookup"><span data-stu-id="b0566-234">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="b0566-235">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="b0566-235">Create a purchase order</span></span>

<span data-ttu-id="b0566-236">Följ stegen nedan när du vill skapa en inköpsorder som leveranskälla.</span><span class="sxs-lookup"><span data-stu-id="b0566-236">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="b0566-237">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="b0566-237">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b0566-238">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b0566-238">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0566-239">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="b0566-239">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0566-240">**Leverantörskonto:** *104*</span><span class="sxs-lookup"><span data-stu-id="b0566-240">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="b0566-241">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-241">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b0566-242">Välj **OK** och anteckna ordernumret.</span><span class="sxs-lookup"><span data-stu-id="b0566-242">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="b0566-243">En ny rad läggs till i rutnätet på snabbfliken **Inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="b0566-243">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="b0566-244">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-244">On this line, set the following values:</span></span>

    - <span data-ttu-id="b0566-245">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b0566-245">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b0566-246">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="b0566-246">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="b0566-247">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="b0566-247">Create a sales order</span></span>

<span data-ttu-id="b0566-248">Följ stegen nedan när du vill skapa en försäljningsorder som behovskälla.</span><span class="sxs-lookup"><span data-stu-id="b0566-248">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="b0566-249">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="b0566-249">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b0566-250">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b0566-250">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0566-251">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="b0566-251">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0566-252">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b0566-252">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="b0566-253">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="b0566-253">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b0566-254">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-254">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-255">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="b0566-255">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b0566-256">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="b0566-256">On this line, set the following values:</span></span>

    - <span data-ttu-id="b0566-257">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b0566-257">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b0566-258">**Kvantitet:** *3*</span><span class="sxs-lookup"><span data-stu-id="b0566-258">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="b0566-259">Skapa planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="b0566-259">Create planned cross-docking</span></span>

<span data-ttu-id="b0566-260">Följ dessa steg för att skapa den planerade direktleveransen från försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b0566-260">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="b0566-261">På sidan **försäljningsorderinformation** för försäljningsordern som du just skapat, i åtgärdsfönstret på fliken **Lagerställe** i gruppen **Åtgärder** väljer du **Frisläpp till lager**.</span><span class="sxs-lookup"><span data-stu-id="b0566-261">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b0566-262">Åtgärden frisläpp till lager skapar en leverans- och lastrad för försäljningsorderraden och försöker allokera lager.</span><span class="sxs-lookup"><span data-stu-id="b0566-262">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="b0566-263">Du får ett informativt meddelande.</span><span class="sxs-lookup"><span data-stu-id="b0566-263">You receive an informational message.</span></span> <span data-ttu-id="b0566-264">Följande varningsmeddelande visas också: "inget arbete har skapats för påfyllnad XXXX.</span><span class="sxs-lookup"><span data-stu-id="b0566-264">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="b0566-265">Mer information finns i loggen över arbetsskapande."</span><span class="sxs-lookup"><span data-stu-id="b0566-265">See the work creation history log for details."</span></span> <span data-ttu-id="b0566-266">Det här beteendet förväntas eftersom det inte finns något lager i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="b0566-266">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="b0566-267">På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Leveransinformation**.</span><span class="sxs-lookup"><span data-stu-id="b0566-267">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="b0566-268">Sidan **Leveransinformation** visas och visar den leverans som har skapats för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b0566-268">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="b0566-269">På snabbfliken **Lastrader** ser du att fältet **Kvantitet i planerad direktleverans** har värdet *3*.</span><span class="sxs-lookup"><span data-stu-id="b0566-269">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="b0566-270">Eftersom det inte fanns något lager tillgängligt i lagerstället, men en giltig leveranskälla kommer in inom tidsfönstret som definieras i mallen för direktleverans, skapades kvantiteten för direktleverans.</span><span class="sxs-lookup"><span data-stu-id="b0566-270">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="b0566-271">På snabbfliken **Lastrader** välj **Planerad direktleverans** om du vill visa information om direktleverans som har skapats.</span><span class="sxs-lookup"><span data-stu-id="b0566-271">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="b0566-272">Bearbeta direktleverans.</span><span class="sxs-lookup"><span data-stu-id="b0566-272">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="b0566-273">Inleverans av inköpsorder med mobilappen för lagerhantering</span><span class="sxs-lookup"><span data-stu-id="b0566-273">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="b0566-274">Kvantiteten för 5 tas emot från inköpsordern till mottagningsplatsen och två arbetsuppgifter skapas.</span><span class="sxs-lookup"><span data-stu-id="b0566-274">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="b0566-275">Det första arbets-ID som skapas har värdet **Arbetsordertyp** för *Direktleverans* och är kopplat till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b0566-275">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="b0566-276">Den har kvantiteten 3 och dirigeras till den slutgiltiga leveransplatsen så att den kan skickas direkt.</span><span class="sxs-lookup"><span data-stu-id="b0566-276">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="b0566-277">Det andra arbets-ID som skapas har värdet **Arbetsordertyp** för *Inköpsorder* och är kopplat till inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="b0566-277">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="b0566-278">Den innehåller den återstående kvantiteten 2 som inte har direktlevereras och dirigeras till artikelinförseln till lagret.</span><span class="sxs-lookup"><span data-stu-id="b0566-278">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="b0566-279">Logga in på den mobila enheten för en användare i lager ställe *51*.</span><span class="sxs-lookup"><span data-stu-id="b0566-279">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="b0566-280">Gå till **inkommande \> inleverans av inköp**.</span><span class="sxs-lookup"><span data-stu-id="b0566-280">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="b0566-281">I fältet **PONum** anger du inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="b0566-281">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="b0566-282">I fältet **Kvt**, ange *5*.</span><span class="sxs-lookup"><span data-stu-id="b0566-282">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="b0566-283">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-283">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-284">På nästa sida anger du fältet **artikel** till *A0001*.</span><span class="sxs-lookup"><span data-stu-id="b0566-284">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="b0566-285">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-285">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-286">På nästa sida bekräfta värdena **PONum**, **Artikel** och **Kvt** genom att klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-286">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="b0566-287">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="b0566-287">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b0566-288">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="b0566-288">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="b0566-289">Artikelinförsel till direktleverans och bulk</span><span class="sxs-lookup"><span data-stu-id="b0566-289">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="b0566-290">För närvarande har båda arbets-ID:n samma ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="b0566-290">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="b0566-291">För att slutföra de kommande stegen måste du ha arbets-ID:t och målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="b0566-291">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="b0566-292">Den här informationen kan du få från arbetsuppgifterna för inköpsorderraden och försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="b0566-292">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="b0566-293">Du kan också gå till information om **Lagerstyrning \> Arbete \> Arbetsinformation** och filtrera fram det arbete där värde **Lagerstället** är *51*.</span><span class="sxs-lookup"><span data-stu-id="b0566-293">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="b0566-294">Gå till den mobila enheten **Inkommande \> Inköpsartikelinförsel** och ange målnummer-ID från arbetet.</span><span class="sxs-lookup"><span data-stu-id="b0566-294">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="b0566-295">I fältet **ID** ange målnummer-ID från arbetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="b0566-295">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="b0566-296">Plocksidan för direktleverans visar plockplatsen (*RECV*), målnummer-ID (*ID-nummer*), artikel (*A0001*) och kvantitet (*3*).</span><span class="sxs-lookup"><span data-stu-id="b0566-296">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="b0566-297">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-297">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-298">I fältet **Mål LP** anger du en målnummer-ID för det licensserver-ID som ska placeras (direktlevereras) på leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="b0566-298">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="b0566-299">Du kan välja valfritt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="b0566-299">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="b0566-300">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-300">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-301">På nästa sida i fältet **ID** ange målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="b0566-301">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="b0566-302">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-302">Select **OK**.</span></span>
1. <span data-ttu-id="b0566-303">Bekräfta arbetet för plockning av resterande kvantitet av 2 och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-303">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="b0566-304">På nästa sida väljer **Klar** för att avsluta plockningsprocessen och påbörjar artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="b0566-304">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="b0566-305">I mobilappen får du en plats och ett ID-nummer platta att inlagra artikeln i.</span><span class="sxs-lookup"><span data-stu-id="b0566-305">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="b0566-306">Bekräfta masslagringen **Placera** genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-306">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="b0566-307">På nästa sida bekräfta direktleverans **Placera** och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0566-307">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="b0566-308">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="b0566-308">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b0566-309">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="b0566-309">Select **Cancel** to exit.</span></span>

<span data-ttu-id="b0566-310">Följande illustration visar hur det slutförda direktleveransen kan visas i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b0566-310">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b0566-311">![Direktleveransarbete har slutförts](media/PlannedCrossDockingWork.png "Direktleveransarbete har slutförts")</span><span class="sxs-lookup"><span data-stu-id="b0566-311">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>
