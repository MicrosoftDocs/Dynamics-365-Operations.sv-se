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
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911258"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="76ce6-104">Planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="76ce6-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76ce6-105">I det här avsnittet beskrivs avancerad, planerad direktleverans.</span><span class="sxs-lookup"><span data-stu-id="76ce6-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="76ce6-106">Direktleverans är en lagerställesprocess där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde.</span><span class="sxs-lookup"><span data-stu-id="76ce6-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="76ce6-107">Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="76ce6-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="76ce6-108">Direktleverans låter medarbetare hoppa över inkommande artikelinförsel och utgående plockning av lager som redan har markerats för en utgående order.</span><span class="sxs-lookup"><span data-stu-id="76ce6-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="76ce6-109">Därför minimeras antalet gånger som lagret vidrörs, om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="76ce6-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="76ce6-110">Eftersom det är mindre interaktion med systemet ökas dessutom tid och utrymmesbesparingar på lagret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="76ce6-111">Innan du kan köra direktleverans måste du konfigurera en ny mall för direktleverans där leveranskällan och andra uppsättningar krav för direktleverans har angetts.</span><span class="sxs-lookup"><span data-stu-id="76ce6-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="76ce6-112">När den utgående ordern skapas måste raden markeras mot en inkommande order som innehåller samma artikel.</span><span class="sxs-lookup"><span data-stu-id="76ce6-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="76ce6-113">Du kan välja kodfältet för direktiv i direktutleveransmallen, på liknande sätt som du konfigurerar lagerpåfyllnads- och inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="76ce6-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="76ce6-114">Vid tiden för inleverans av inkommande order identifierar inställningen för direktleverans automatiskt behovet av direktleverans och skapar flyttningsarbetet för den begärda kvantiteten, baserat på inställningen för platsdirektivet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="76ce6-115">Lagertransaktioner avregistreras *inte* när jobbet för direktleverans avbryts, även om inställningen för denna funktion aktiveras i parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="76ce6-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="76ce6-116">Aktivera funktionen planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="76ce6-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="76ce6-117">Om systemet inte redan har de funktioner som beskrivs i det här avsnittet går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar följande funktioner i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="76ce6-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="76ce6-118">*Planerad direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="76ce6-119">*Mallar för direktleverans med platsdirektiv*</span><span class="sxs-lookup"><span data-stu-id="76ce6-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="76ce6-120">Med hjälp av denna funktion kan fältet **Direktivkod** anges i direktleveransmallen, på liknande sätt som du ställer in påfyllnadsmallar.</span><span class="sxs-lookup"><span data-stu-id="76ce6-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="76ce6-121">Genom att aktivera den här funktionen förhindrar du att du lägger till en kod för direktiv på direktleveransens arbetsmallrader för den slutgiltiga *Placera*-raden.</span><span class="sxs-lookup"><span data-stu-id="76ce6-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="76ce6-122">På så sätt ser du till att den slutliga placeringsplatsen kan fastställas under skapandet av arbetet innan arbetsmallar övervägs.</span><span class="sxs-lookup"><span data-stu-id="76ce6-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="76ce6-123">Ställ in</span><span class="sxs-lookup"><span data-stu-id="76ce6-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="76ce6-124">Generera om lastbokföringsmetoder</span><span class="sxs-lookup"><span data-stu-id="76ce6-124">Regenerate load posting methods</span></span>

<span data-ttu-id="76ce6-125">Planerad direktleverans är implementerad som en lastbokföringsmetod.</span><span class="sxs-lookup"><span data-stu-id="76ce6-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="76ce6-126">När du har aktiverat funktionen måste du generera om metoderna.</span><span class="sxs-lookup"><span data-stu-id="76ce6-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="76ce6-127">Gå till **Lagerstyrning \> Inställningar \> Lastbokföringsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="76ce6-128">Klicka på **återskapa metoder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="76ce6-129">När återskapandet är slutfört visas en metod med ett värde för **metodnamn** på *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="76ce6-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="76ce6-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="76ce6-131">Skapa en direktleveransmall.</span><span class="sxs-lookup"><span data-stu-id="76ce6-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="76ce6-132">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Mallar för direktleverans**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="76ce6-133">I åtgärdsfönstret, välj **Ny** för att skapa en mall.</span><span class="sxs-lookup"><span data-stu-id="76ce6-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="76ce6-134">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="76ce6-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="76ce6-135">**Sekvens:** *1*</span><span class="sxs-lookup"><span data-stu-id="76ce6-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="76ce6-136">I det här fältet definieras ordningen som mallarna utvärderas i.</span><span class="sxs-lookup"><span data-stu-id="76ce6-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="76ce6-137">**Mall-ID för direktleverans:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="76ce6-138">**Beskrivning:** *lagerställe 51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="76ce6-139">**Frisläppning av efterfrågan:** *Före leverans av inleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="76ce6-140">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="76ce6-141">Inställningen på snabbfliken **Planering** styr hur mallen fungerar.</span><span class="sxs-lookup"><span data-stu-id="76ce6-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="76ce6-142">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="76ce6-142">Set the following values:</span></span>

    - <span data-ttu-id="76ce6-143">**Krav på begäran:** *Inga*</span><span class="sxs-lookup"><span data-stu-id="76ce6-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="76ce6-144">Det här fältet definierar kraven för efterfrågelager.</span><span class="sxs-lookup"><span data-stu-id="76ce6-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="76ce6-145">Om behovet måste kopplas till leveransen före frisläppning väljer du markera *markering*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="76ce6-146">Om efter frågeställningen måste vara orderreserverad mot försörjningen före frisläppning väljer du *Orderreservation*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="76ce6-147">**Söka efter typ:** *utleveransplatser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="76ce6-148">Det här fältet definierar om direktleveransen ska använda för produktions-/lastplatserna från leverans, eller om den ska använda platsdirektiv för att hitta sina egna mellanlagrings- eller lastplatser.</span><span class="sxs-lookup"><span data-stu-id="76ce6-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="76ce6-149">**Arbetsmall:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="76ce6-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="76ce6-150">Det här fältet definierar arbetsmallen som ska användas när direktleverans skapas.</span><span class="sxs-lookup"><span data-stu-id="76ce6-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="76ce6-151">**Validera på leveranskvitto igen:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="76ce6-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="76ce6-152">Det här alternativet anger om leveransen ska omvalideras under inleverans.</span><span class="sxs-lookup"><span data-stu-id="76ce6-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="76ce6-153">Om det här alternativet har värdet *Ja* kontrolleras både det maximala tidsfönstret och intervallet för utgångsdagar.</span><span class="sxs-lookup"><span data-stu-id="76ce6-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="76ce6-154">**Direktivkod:** Lämna det här fältet tomt</span><span class="sxs-lookup"><span data-stu-id="76ce6-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="76ce6-155">Detta alternativ aktiveras med hjälp av funktionen *Mallar för direktutleverans med platsdirektiv*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="76ce6-156">Systemet använder platsdirektiv för att avgöra vilken som är den bästa platsen att flytta lager för direktleverans till.</span><span class="sxs-lookup"><span data-stu-id="76ce6-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="76ce6-157">Du kan ställa in den genom att tilldela en direktivkod till varje relevant direktutleveransmall.</span><span class="sxs-lookup"><span data-stu-id="76ce6-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="76ce6-158">Om en direktivkod ställs in kommer systemet att söka efter platsdirektiv med direktivkod när arbete genereras.</span><span class="sxs-lookup"><span data-stu-id="76ce6-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="76ce6-159">På detta sätt kan du begränsa platsdirektiv som används för en viss direktleveransmall.</span><span class="sxs-lookup"><span data-stu-id="76ce6-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="76ce6-160">**Validera tidsfönster:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="76ce6-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="76ce6-161">Det här alternativet anger om det maximala tidsfönstret ska utvärderas när en leveranskälla väljs.</span><span class="sxs-lookup"><span data-stu-id="76ce6-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="76ce6-162">Om det här alternativet är inställt på *Ja* blir fälten som är relaterade till den maximala och minsta tidsfönstret tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="76ce6-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="76ce6-163">**Maximalt tidsfönster:** *5*</span><span class="sxs-lookup"><span data-stu-id="76ce6-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="76ce6-164">Detta fält definierar den maximala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="76ce6-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="76ce6-165">**Enheten maximalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="76ce6-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="76ce6-166">**Minsta tidsfönster:** *0*</span><span class="sxs-lookup"><span data-stu-id="76ce6-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="76ce6-167">Detta fält definierar den minimala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.</span><span class="sxs-lookup"><span data-stu-id="76ce6-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="76ce6-168">**Enheten minimalt tidsfönster:** *Dagar*</span><span class="sxs-lookup"><span data-stu-id="76ce6-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="76ce6-169">**Intervall med förfallodagar:** *0*</span><span class="sxs-lookup"><span data-stu-id="76ce6-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="76ce6-170">*FEFO-kriterier (först utgått, först ut):* Det här fältet definierar det maximala antalet dagar mellan utgångsdatumet för den första utgående batch som för närvarande finns i lagerstället och den batch som inlevereras.</span><span class="sxs-lookup"><span data-stu-id="76ce6-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="76ce6-171">På snabbfliken **Leveranskällor** anger du vilka typer av leveranser som är giltiga för den här mallen.</span><span class="sxs-lookup"><span data-stu-id="76ce6-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="76ce6-172">Välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="76ce6-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="76ce6-173">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="76ce6-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="76ce6-174">**Leveranskälla:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="76ce6-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="76ce6-175">Skapa en arbetsklass</span><span class="sxs-lookup"><span data-stu-id="76ce6-175">Create a work class</span></span>

1. <span data-ttu-id="76ce6-176">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="76ce6-177">I åtgärdsfönstret, välj **Ny** för att skapa en arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="76ce6-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="76ce6-178">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="76ce6-178">Set the following values:</span></span>

    - <span data-ttu-id="76ce6-179">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="76ce6-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="76ce6-180">**Beskrivning:** *Direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="76ce6-181">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="76ce6-182">Skapa en arbetsuppgiftsmall</span><span class="sxs-lookup"><span data-stu-id="76ce6-182">Create a work template</span></span>

1. <span data-ttu-id="76ce6-183">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="76ce6-184">Ange fältet **Inköpsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="76ce6-185">I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="76ce6-186">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-187">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="76ce6-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="76ce6-188">**Arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="76ce6-189">**Beskrivning av arbetsmall:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="76ce6-190">Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="76ce6-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="76ce6-191">På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="76ce6-192">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-193">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="76ce6-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="76ce6-194">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="76ce6-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="76ce6-195">Välj **Ny** för att lägga till en till rad och ställa in följande värden på den:</span><span class="sxs-lookup"><span data-stu-id="76ce6-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="76ce6-196">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="76ce6-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="76ce6-197">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="76ce6-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="76ce6-198">Välj **Spara** och bekräfta att kryssrutan **Giltig** är markerad för mallen *51 direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="76ce6-199">Arbetsklass-ID för arbetstyperna *Plocka* och *Placera* måste vara samma.</span><span class="sxs-lookup"><span data-stu-id="76ce6-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="76ce6-200">Skapa platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="76ce6-200">Create location directives</span></span>

1. <span data-ttu-id="76ce6-201">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="76ce6-202">I vänster ruta ange fältet **Arbetsordertyp** till *Direktleverans*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="76ce6-203">I åtgärdsfönstret, välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="76ce6-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="76ce6-204">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="76ce6-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="76ce6-205">**Namn:** *51 direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="76ce6-206">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="76ce6-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="76ce6-207">**Plats:** *5*</span><span class="sxs-lookup"><span data-stu-id="76ce6-207">**Site:** *5*</span></span>
    - <span data-ttu-id="76ce6-208">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="76ce6-209">Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="76ce6-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="76ce6-210">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="76ce6-211">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-212">**Från kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="76ce6-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="76ce6-213">**Till kvantitet:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="76ce6-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="76ce6-214">Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="76ce6-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="76ce6-215">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="76ce6-216">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-217">**Namn:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="76ce6-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="76ce6-218">**Användning av fast lagerplats:** *Fasta och ej fasta platser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="76ce6-219">Välj **Spara** så att knappen **Redigera fråga** i verktygsfältet **Platsdirektivåtgärder** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="76ce6-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="76ce6-220">Välj **Redigera fråga** för att öppna frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="76ce6-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="76ce6-221">På fliken **Intervall** ser du till att följande två rader har konfigurerats:</span><span class="sxs-lookup"><span data-stu-id="76ce6-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="76ce6-222">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="76ce6-222">Line 1:</span></span>

        - <span data-ttu-id="76ce6-223">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="76ce6-224">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="76ce6-225">**Fält:** *lagerställe*</span><span class="sxs-lookup"><span data-stu-id="76ce6-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="76ce6-226">**Kriterier:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="76ce6-227">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="76ce6-227">Line 2:</span></span>

        - <span data-ttu-id="76ce6-228">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="76ce6-229">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="76ce6-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="76ce6-230">**Fält:** *Plats*</span><span class="sxs-lookup"><span data-stu-id="76ce6-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="76ce6-231">**Kriterier:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="76ce6-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="76ce6-232">Stäng frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="76ce6-233">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="76ce6-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="76ce6-234">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="76ce6-235">I listan över menyalternativ i det vänstra fönstret väljer du **inköpsartikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="76ce6-236">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-236">Select **Edit**.</span></span>
1. <span data-ttu-id="76ce6-237">På snabbfliken **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="76ce6-238">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-239">**Arbetsklass-ID:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="76ce6-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="76ce6-240">**Typ av arbetsorder:** *direktleverans*</span><span class="sxs-lookup"><span data-stu-id="76ce6-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="76ce6-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="76ce6-242">Scenario</span><span class="sxs-lookup"><span data-stu-id="76ce6-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="76ce6-243">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="76ce6-243">Create a purchase order</span></span>

<span data-ttu-id="76ce6-244">Följ stegen nedan när du vill skapa en inköpsorder som leveranskälla.</span><span class="sxs-lookup"><span data-stu-id="76ce6-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="76ce6-245">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="76ce6-246">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="76ce6-247">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="76ce6-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="76ce6-248">**Leverantörskonto:** *104*</span><span class="sxs-lookup"><span data-stu-id="76ce6-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="76ce6-249">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="76ce6-250">Välj **OK** och anteckna ordernumret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="76ce6-251">En ny rad läggs till i rutnätet på snabbfliken **Inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="76ce6-252">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-253">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="76ce6-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="76ce6-254">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="76ce6-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="76ce6-255">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="76ce6-255">Create a sales order</span></span>

<span data-ttu-id="76ce6-256">Följ stegen nedan när du vill skapa en försäljningsorder som behovskälla.</span><span class="sxs-lookup"><span data-stu-id="76ce6-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="76ce6-257">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="76ce6-258">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="76ce6-259">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="76ce6-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="76ce6-260">**Kundkonto:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="76ce6-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="76ce6-261">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="76ce6-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="76ce6-262">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-262">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-263">En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="76ce6-264">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="76ce6-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="76ce6-265">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="76ce6-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="76ce6-266">**Kvantitet:** *3*</span><span class="sxs-lookup"><span data-stu-id="76ce6-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="76ce6-267">Skapa planerad direktleverans</span><span class="sxs-lookup"><span data-stu-id="76ce6-267">Create planned cross-docking</span></span>

<span data-ttu-id="76ce6-268">Följ dessa steg för att skapa den planerade direktleveransen från försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="76ce6-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="76ce6-269">På sidan **försäljningsorderinformation** för försäljningsordern som du just skapat, i åtgärdsfönstret på fliken **Lagerställe** i gruppen **Åtgärder** väljer du **Frisläpp till lager**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="76ce6-270">Åtgärden frisläpp till lager skapar en leverans- och lastrad för försäljningsorderraden och försöker allokera lager.</span><span class="sxs-lookup"><span data-stu-id="76ce6-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="76ce6-271">Du får ett informativt meddelande.</span><span class="sxs-lookup"><span data-stu-id="76ce6-271">You receive an informational message.</span></span> <span data-ttu-id="76ce6-272">Följande varningsmeddelande visas också: "inget arbete har skapats för påfyllnad XXXX.</span><span class="sxs-lookup"><span data-stu-id="76ce6-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="76ce6-273">Mer information finns i loggen över arbetsskapande."</span><span class="sxs-lookup"><span data-stu-id="76ce6-273">See the work creation history log for details."</span></span> <span data-ttu-id="76ce6-274">Det här beteendet förväntas eftersom det inte finns något lager i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="76ce6-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="76ce6-275">På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Leveransinformation**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="76ce6-276">Sidan **Leveransinformation** visas och visar den leverans som har skapats för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="76ce6-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="76ce6-277">På snabbfliken **Lastrader** ser du att fältet **Kvantitet i planerad direktleverans** har värdet *3*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="76ce6-278">Eftersom det inte fanns något lager tillgängligt i lagerstället, men en giltig leveranskälla kommer in inom tidsfönstret som definieras i mallen för direktleverans, skapades kvantiteten för direktleverans.</span><span class="sxs-lookup"><span data-stu-id="76ce6-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="76ce6-279">På snabbfliken **Lastrader** välj **Planerad direktleverans** om du vill visa information om direktleverans som har skapats.</span><span class="sxs-lookup"><span data-stu-id="76ce6-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="76ce6-280">Bearbeta direktleverans.</span><span class="sxs-lookup"><span data-stu-id="76ce6-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="76ce6-281">Inleverans av inköpsorder med mobilappen för lagerhantering</span><span class="sxs-lookup"><span data-stu-id="76ce6-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="76ce6-282">Kvantiteten för 5 tas emot från inköpsordern till mottagningsplatsen och två arbetsuppgifter skapas.</span><span class="sxs-lookup"><span data-stu-id="76ce6-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="76ce6-283">Det första arbets-ID som skapas har värdet **Arbetsordertyp** för *Direktleverans* och är kopplat till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="76ce6-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="76ce6-284">Den har kvantiteten 3 och dirigeras till den slutgiltiga leveransplatsen så att den kan skickas direkt.</span><span class="sxs-lookup"><span data-stu-id="76ce6-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="76ce6-285">Det andra arbets-ID som skapas har värdet **Arbetsordertyp** för *Inköpsorder* och är kopplat till inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="76ce6-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="76ce6-286">Den innehåller den återstående kvantiteten 2 som inte har direktlevereras och dirigeras till artikelinförseln till lagret.</span><span class="sxs-lookup"><span data-stu-id="76ce6-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="76ce6-287">Logga in på den mobila enheten för en användare i lager ställe *51*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="76ce6-288">Gå till **inkommande \> inleverans av inköp**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="76ce6-289">I fältet **PONum** anger du inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="76ce6-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="76ce6-290">I fältet **Kvt**, ange *5*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="76ce6-291">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-291">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-292">På nästa sida anger du fältet **artikel** till *A0001*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="76ce6-293">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-293">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-294">På nästa sida bekräfta värdena **PONum**, **Artikel** och **Kvt** genom att klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="76ce6-295">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="76ce6-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="76ce6-296">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="76ce6-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="76ce6-297">Artikelinförsel till direktleverans och bulk</span><span class="sxs-lookup"><span data-stu-id="76ce6-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="76ce6-298">För närvarande har båda arbets-ID:n samma ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="76ce6-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="76ce6-299">För att slutföra de kommande stegen måste du ha arbets-ID:t och målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="76ce6-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="76ce6-300">Den här informationen kan du få från arbetsuppgifterna för inköpsorderraden och försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="76ce6-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="76ce6-301">Du kan också gå till information om **Lagerstyrning \> Arbete \> Arbetsinformation** och filtrera fram det arbete där värde **Lagerstället** är *51*.</span><span class="sxs-lookup"><span data-stu-id="76ce6-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="76ce6-302">Gå till den mobila enheten **Inkommande \> Inköpsartikelinförsel** och ange målnummer-ID från arbetet.</span><span class="sxs-lookup"><span data-stu-id="76ce6-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="76ce6-303">I fältet **ID** ange målnummer-ID från arbetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="76ce6-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="76ce6-304">Plocksidan för direktleverans visar plockplatsen (*RECV*), målnummer-ID (*ID-nummer*), artikel (*A0001*) och kvantitet (*3*).</span><span class="sxs-lookup"><span data-stu-id="76ce6-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="76ce6-305">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-305">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-306">I fältet **Mål LP** anger du en målnummer-ID för det licensserver-ID som ska placeras (direktlevereras) på leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="76ce6-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="76ce6-307">Du kan välja valfritt ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="76ce6-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="76ce6-308">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-308">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-309">På nästa sida i fältet **ID** ange målnummer-ID.</span><span class="sxs-lookup"><span data-stu-id="76ce6-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="76ce6-310">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-310">Select **OK**.</span></span>
1. <span data-ttu-id="76ce6-311">Bekräfta arbetet för plockning av resterande kvantitet av 2 och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="76ce6-312">På nästa sida väljer **Klar** för att avsluta plockningsprocessen och påbörjar artikelinförselprocessen.</span><span class="sxs-lookup"><span data-stu-id="76ce6-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="76ce6-313">I mobilappen får du en plats och ett ID-nummer platta att inlagra artikeln i.</span><span class="sxs-lookup"><span data-stu-id="76ce6-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="76ce6-314">Bekräfta masslagringen **Placera** genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="76ce6-315">På nästa sida bekräfta direktleverans **Placera** och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76ce6-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="76ce6-316">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="76ce6-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="76ce6-317">Välj **avbryt** för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="76ce6-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="76ce6-318">Följande illustration visar hur det slutförda direktleveransen kan visas i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76ce6-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="76ce6-319">![Direktleveransarbete har slutförts](media/PlannedCrossDockingWork.png "Direktleveransarbete har slutförts")</span><span class="sxs-lookup"><span data-stu-id="76ce6-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]