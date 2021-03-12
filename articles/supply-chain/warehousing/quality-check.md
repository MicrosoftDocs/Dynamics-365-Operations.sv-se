---
title: Kvalitetskontroll
description: Det här ämnet innehåller information om funktionen för kvalitetskontroll. Med den här funktionen kan lagerarbetarna göra snabba stickprov för att kontrollera kvaliteten medan de tar emot artiklar på inlastningsplatsen.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 585ca933726cb932290f8abf8504aeb13848a0e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996262"
---
# <a name="quality-check"></a><span data-ttu-id="72d78-104">Kvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72d78-105">Med funktionen *Kvalitetskontroll* kan lagerarbetarna göra snabba stickprov för att kontrollera kvaliteten medan de tar emot artiklar på inlastningsplatsen.</span><span class="sxs-lookup"><span data-stu-id="72d78-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="72d78-106">Dessa stickprov är fördelaktiga när arbetarna inspekterar emballage eller andra lätt igenkännbara delar av en artikel.</span><span class="sxs-lookup"><span data-stu-id="72d78-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="72d78-107">Med hjälp av funktionen kan arbetarna ta en snabbt titt på om något är uppenbart trasigt eller skadat innan det lagerförs på dess inlagringsplats.</span><span class="sxs-lookup"><span data-stu-id="72d78-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="72d78-108">Den här funktionen är ett alternativ till standardprocessen för kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="72d78-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="72d78-109">Den erbjuder större flexibilitet och snabbare bearbetning.</span><span class="sxs-lookup"><span data-stu-id="72d78-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="72d78-110">När du använder den här funktionen inträffar införsel och kvalitetskontrollen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="72d78-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="72d78-111">När en leverans ankommer registrerar en lagerarbetare införseln.</span><span class="sxs-lookup"><span data-stu-id="72d78-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="72d78-112">Arbetaren söker också igenom ett ID-nummer för att registrera platsen.</span><span class="sxs-lookup"><span data-stu-id="72d78-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="72d78-113">Arbetaren gör en snabb kvalitetskontroll och registrerar resultatet (godkänd eller underkänd) för det ID-numret.</span><span class="sxs-lookup"><span data-stu-id="72d78-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="72d78-114">En av följande åtgärder inträffar:</span><span class="sxs-lookup"><span data-stu-id="72d78-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="72d78-115">Om kvalitetskontrollen har godkänts accepteras ID-numret och guidas till mottagningsplatsen, som vanligt.</span><span class="sxs-lookup"><span data-stu-id="72d78-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="72d78-116">Om kvalitetskontrollen misslyckas avvisas ID-numret och befintligt inlagringsarbete för den dirigeras om till en alternativ plats för vidare granskning.</span><span class="sxs-lookup"><span data-stu-id="72d78-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="72d78-117">En ny kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="72d78-117">A new quality order is created.</span></span> <span data-ttu-id="72d78-118">Om du vill visa kvalitetsordern som skapas med hjälp av den misslyckade kvalitetskontrollen går du till **lagerhantering \> periodiska uppgifter \> kvalitetshantering \> kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="72d78-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="72d78-119">Den här processen kan också ställas in så att alla ID-nummer omedelbart omdirigeras till kvalitetskontrollplatsen.</span><span class="sxs-lookup"><span data-stu-id="72d78-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="72d78-120">Aktivera funktionen kvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="72d78-121">Innan du kan använda funktionen *kvalitetskontroll* måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="72d78-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="72d78-122">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="72d78-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="72d78-123">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="72d78-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="72d78-124">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="72d78-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="72d78-125">**Funktionsnamn:** *kvalitetskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="72d78-126">Ställ in funktionen för det här exempelscenariot</span><span class="sxs-lookup"><span data-stu-id="72d78-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="72d78-127">Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du ställer in funktionen *kvalitetskontroll* och förbereder exempeldata för scenariot som ges senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="72d78-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="72d78-128">Gör exempeldata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="72d78-128">Make sample data available</span></span>

<span data-ttu-id="72d78-129">Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="72d78-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="72d78-130">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="72d78-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="72d78-131">Mall för kvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-131">Quality check template</span></span>

<span data-ttu-id="72d78-132">Mallen för kvalitetskontroll definierar reglerna för att göra snabba stickprov av kvalitet vid mottagandet.</span><span class="sxs-lookup"><span data-stu-id="72d78-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="72d78-133">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Kvalitetskontrollmall**.</span><span class="sxs-lookup"><span data-stu-id="72d78-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="72d78-134">Välj **Ny** om du vill lägga till en mall i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="72d78-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="72d78-135">Ange följande värden för att definiera den nya mallen:</span><span class="sxs-lookup"><span data-stu-id="72d78-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="72d78-136">**Mallnamn för kvalitetskontroll:** *Lastkajskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="72d78-137">Ange ett namn som identifierar de principer som används för den här mallen.</span><span class="sxs-lookup"><span data-stu-id="72d78-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="72d78-138">**Acceptansprincip:** *Fråga användaren*</span><span class="sxs-lookup"><span data-stu-id="72d78-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="72d78-139">Ange om användarna ska uppmanas att acceptera eller avvisa kvaliteten på lagret under bearbetningen av arbetet, eller om kvaliteten automatiskt ska avvisas.</span><span class="sxs-lookup"><span data-stu-id="72d78-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="72d78-140">De tillgängliga alternativen är *automatiskt avvisa* och *fråga användaren*.</span><span class="sxs-lookup"><span data-stu-id="72d78-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="72d78-141">**Kvalitetsbearbetningsprincip:** *skapa kvalitetsorder*</span><span class="sxs-lookup"><span data-stu-id="72d78-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="72d78-142">Välj den policy som ska användas när lagerkvalitet avvisas.</span><span class="sxs-lookup"><span data-stu-id="72d78-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="72d78-143">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="72d78-143">The following options are available:</span></span>

        - <span data-ttu-id="72d78-144">*Skapa endast arbete* – Skapa bara arbete för att underlätta lagerrörelser.</span><span class="sxs-lookup"><span data-stu-id="72d78-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="72d78-145">*Skapa kvalitetsorder* – skapa en kvalitetsorder för att underlätta kvalitetstester.</span><span class="sxs-lookup"><span data-stu-id="72d78-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="72d78-146">**Testgrupp:** *bilaga*</span><span class="sxs-lookup"><span data-stu-id="72d78-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="72d78-147">Ange testgruppen som ska användas i den kvalitetsorder som skapas.</span><span class="sxs-lookup"><span data-stu-id="72d78-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="72d78-148">Testgrupper ställs in i modulen **Lagerhantering**.</span><span class="sxs-lookup"><span data-stu-id="72d78-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="72d78-149">Lämna alternativet **Destruktiv text** inaktiverat för testgruppen.</span><span class="sxs-lookup"><span data-stu-id="72d78-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="72d78-150">Det här alternativet definierar om provet ska förstöras under testerna i testgruppen.</span><span class="sxs-lookup"><span data-stu-id="72d78-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="72d78-151">Om ett destruktivt test används genererar systemet en lagertransaktion när en kvalitetsorder skapas för ett objekt.</span><span class="sxs-lookup"><span data-stu-id="72d78-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="72d78-152">Den nya lagertransaktionen förutsäger lagerreduceringen för testkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="72d78-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="72d78-153">Lagerreduktionen inträffar när kvalitetsordern slutförs genom valideringssteget.</span><span class="sxs-lookup"><span data-stu-id="72d78-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="72d78-154">Lagertransaktionen identifieras som en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="72d78-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="72d78-155">Arbetsklass – kvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-155">Work class – Quality check</span></span>

<span data-ttu-id="72d78-156">Arbetsklasser används för att styra och/eller begränsa den typ av arbetsorderrader som en lagerarbetare kan bearbeta på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="72d78-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="72d78-157">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="72d78-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="72d78-158">Skapa en arbetsklass genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="72d78-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="72d78-159">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="72d78-160">**Arbetsklass-ID:** *QC-kontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="72d78-161">Ange ett namn som identifierar arbetsklassen.</span><span class="sxs-lookup"><span data-stu-id="72d78-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="72d78-162">**Beskrivning:** *QC-kontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="72d78-163">Ange en kort beskrivning som anger vad arbetsklassen används till.</span><span class="sxs-lookup"><span data-stu-id="72d78-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="72d78-164">**Arbetsordertyp:** *kvalitet i kvalitetskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="72d78-165">Välj den typ av arbetsorder som skapas av arbetsklassen.</span><span class="sxs-lookup"><span data-stu-id="72d78-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="72d78-166">Välj alltid kvalitet under kvalitetskontroll när du ställer in *kvalitet i kvalitetskontroll*.</span><span class="sxs-lookup"><span data-stu-id="72d78-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="72d78-167">På snabbfliken **giltiga platstyper** lämnar du fältet **platstyp** tomt.</span><span class="sxs-lookup"><span data-stu-id="72d78-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="72d78-168">Om du väljer en platstyp kan du begränsa de platser där artiklar kan placeras efter att de har plockats.</span><span class="sxs-lookup"><span data-stu-id="72d78-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="72d78-169">Detta fält används när ett platsdirektiv försöker lösa platsen, eller om en lagerarbetare manuellt anger platsen för menyobjektet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="72d78-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="72d78-170">Mer information om arbetsklasser och hur du skapar dem finns i [skapa en arbetsklass](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="72d78-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="72d78-171">Arbetsmall</span><span class="sxs-lookup"><span data-stu-id="72d78-171">Work template</span></span>

<span data-ttu-id="72d78-172">Arbetsmallar låter dig definiera arbeten som måste utföras i lagret.</span><span class="sxs-lookup"><span data-stu-id="72d78-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="72d78-173">Typiskt, warehouse arbeten består av ett par åtgärder: en lagerarbetare plockar upp lagersaldot på en plats och sedan lägger de plockade lager ned på en annan plats.</span><span class="sxs-lookup"><span data-stu-id="72d78-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="72d78-174">En arbetsmall för kvalitetskontroll definierar vilka arbetsprocesser som ska utföra kvalitetskontroller.</span><span class="sxs-lookup"><span data-stu-id="72d78-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="72d78-175">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="72d78-175">Purchase orders</span></span>

1. <span data-ttu-id="72d78-176">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="72d78-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="72d78-177">I rubriken, ange **Inköpsorder** i fältet till *Inköpsorder*.</span><span class="sxs-lookup"><span data-stu-id="72d78-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="72d78-178">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="72d78-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="72d78-179">Välj en arbetsmall som ska innehålla ett kvalitetskontrollsteg.</span><span class="sxs-lookup"><span data-stu-id="72d78-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="72d78-180">I avsnittet **Översikt** i fältet **Arbetsmall** väljer du *51 IO-inleverans*.</span><span class="sxs-lookup"><span data-stu-id="72d78-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="72d78-181">I avsnittet **Arbetsmallinformation** lägg märke till att rutnätet har två befintliga rader: en för *Plocka* och en för *Placera*.</span><span class="sxs-lookup"><span data-stu-id="72d78-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="72d78-182">I avsnittet **Arbetsmallinformation** välj **Ny** om du vill lägga till en rad för kvalitetskontroll i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="72d78-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="72d78-183">Observera att fältet **radnummer** för den nya raden har värdet *3*.</span><span class="sxs-lookup"><span data-stu-id="72d78-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="72d78-184">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="72d78-184">On the new line, set the following values.</span></span> <span data-ttu-id="72d78-185">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="72d78-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="72d78-186">**Arbetstyp:** *kvalitetskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="72d78-187">**Arbetsklass-ID:** *Inköp*</span><span class="sxs-lookup"><span data-stu-id="72d78-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="72d78-188">**Mallnamn för kvalitetskontroll:** *Lastkajskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="72d78-189">Välj det unika ID:t för arbetsklassen.</span><span class="sxs-lookup"><span data-stu-id="72d78-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="72d78-190">Det här värdet används för att konfigurera menykommandona på den mobila enheten och typerna av arbete som dessa menykommandon kan bearbeta.</span><span class="sxs-lookup"><span data-stu-id="72d78-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="72d78-191">I åtgärdsfönstret, välj **Spara** för att spara ditt arbete hittills.</span><span class="sxs-lookup"><span data-stu-id="72d78-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="72d78-192">Du får ett informationsmeddelande om att "Ogiltig kvalitetskontroll måste komma direkt efter en plockning".</span><span class="sxs-lookup"><span data-stu-id="72d78-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="72d78-193">Därför måste du ändra värdet för **radnummer** för den rad som du just har lagt till.</span><span class="sxs-lookup"><span data-stu-id="72d78-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="72d78-194">Följ dessa steg för att ändra värdet för **radnummer** för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="72d78-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="72d78-195">I avsnittet **Arbetsmallinformation** väljer du den rad där fältet **Arbetstyp** anges till *Kvalitetskontroll*.</span><span class="sxs-lookup"><span data-stu-id="72d78-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="72d78-196">Markera knappen **Flytta upp** eller **Flytta ned** om du vill flytta raden *Kvalitetskontroll* så att den är efter raden *Plocka*.</span><span class="sxs-lookup"><span data-stu-id="72d78-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="72d78-197">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="72d78-198">Kvalitet på kvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-198">Quality in quality check</span></span>

<span data-ttu-id="72d78-199">Skapa sedan en arbetsmall för kvalitetskontrollen.</span><span class="sxs-lookup"><span data-stu-id="72d78-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="72d78-200">I rubriken på sidan **Arbetsmallar** ändra värdet på fältet **Arbetsordertyp** till *Kvalitet i kvalitetskontroll*.</span><span class="sxs-lookup"><span data-stu-id="72d78-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="72d78-201">I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet i avsnittet **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="72d78-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="72d78-202">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="72d78-203">**Arbetsmall:** *51 kvalitetkontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="72d78-204">Ange ett namn för mallen.</span><span class="sxs-lookup"><span data-stu-id="72d78-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="72d78-205">**Arbetsmallbeskrivning:** *51 kvalitetkontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="72d78-206">I åtgärdsfönstret, välj **Spara** om du vill göra avsnittet **Arbetsmallinformation** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="72d78-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="72d78-207">Medan den nya mallen fortfarande är markerad i avsnittet **Översikt** väljer du **Ny** i avsnittet **Arbetsmallinformation** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="72d78-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="72d78-208">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="72d78-209">**Arbetstyp:** *plockning*</span><span class="sxs-lookup"><span data-stu-id="72d78-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="72d78-210">**Arbetsklass-ID:** *QC-kontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="72d78-211">Välj namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="72d78-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="72d78-212">I avsnittet **Arbetsmallinformation** väljer du **Ny** igen för att lägga till en annan rad.</span><span class="sxs-lookup"><span data-stu-id="72d78-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="72d78-213">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="72d78-214">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="72d78-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="72d78-215">**Arbetsklass-ID:** *QC-kontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="72d78-216">Välj namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="72d78-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="72d78-217">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="72d78-218">Mer information om arbetsmallar finns i [Kontrollera lagerarbete med arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).</span><span class="sxs-lookup"><span data-stu-id="72d78-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="72d78-219">Plats direktiv – kvalitetsfel</span><span class="sxs-lookup"><span data-stu-id="72d78-219">Location directive – Quality failures</span></span>

<span data-ttu-id="72d78-220">Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager.</span><span class="sxs-lookup"><span data-stu-id="72d78-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="72d78-221">I en försäljningsordertransaktion fastställer till exempel ett direktiv platsen där artiklarna ska plockas och var de plockade artiklarna ska inlagras.</span><span class="sxs-lookup"><span data-stu-id="72d78-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="72d78-222">Du måste konfigurera en platsdirektivregel för att definiera hur misslyckade kvalitetskontroller ska hanteras.</span><span class="sxs-lookup"><span data-stu-id="72d78-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="72d78-223">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="72d78-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="72d78-224">I det vänstra fönstret anger du fältet **Arbetsordertyp** till *Inköpsorder* för att arbeta med platsdirektiv av den typen.</span><span class="sxs-lookup"><span data-stu-id="72d78-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="72d78-225">I åtgärdsfönstret, välj **Ny** för att skapa en platsdirektiv för kvalitetskontroller.</span><span class="sxs-lookup"><span data-stu-id="72d78-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="72d78-226">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="72d78-227">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="72d78-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="72d78-228">**Namn:** *51 till kvalitet*</span><span class="sxs-lookup"><span data-stu-id="72d78-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="72d78-229">Ange följande värden på snabbfliken **Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="72d78-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="72d78-230">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="72d78-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="72d78-231">**Arbetstyp:** *Placera*</span><span class="sxs-lookup"><span data-stu-id="72d78-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="72d78-232">**Plats:** *5*</span><span class="sxs-lookup"><span data-stu-id="72d78-232">**Site:** *5*</span></span>
    - <span data-ttu-id="72d78-233">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="72d78-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="72d78-234">I åtgärdsfönstret **Spara** för att spara dina direktiv och gör **Rader** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="72d78-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="72d78-235">På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="72d78-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="72d78-236">Ställ in följande värden på denna nya rad.</span><span class="sxs-lookup"><span data-stu-id="72d78-236">On the new line, set the following values.</span></span> <span data-ttu-id="72d78-237">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="72d78-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="72d78-238">**Från kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="72d78-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="72d78-239">**Till kvantitet:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="72d78-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="72d78-240">I åtgärdsfönstret **Spara** för att spara den nya raden och gör snabbfliken **Platsdirektivåtgärder** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="72d78-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="72d78-241">Medan den nya raden fortfarande är markerad på snabbfliken **Rader** välj **Ny** på snabbfliken **Platsdirektivåtgärder** för att lägga till en rad i rutnätet där, så att du kan ställa in en åtgärd för raden.</span><span class="sxs-lookup"><span data-stu-id="72d78-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="72d78-242">I nya rader, ange fältet **Namn** till *Kvalitet*.</span><span class="sxs-lookup"><span data-stu-id="72d78-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="72d78-243">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="72d78-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="72d78-244">I åtgärdsfönstret välj **Spara** så att knappen **Redigera fråga** i snabbfliken **Platsdirektivåtgärder** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="72d78-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="72d78-245">Medan raden som du just har lagt till fortfarande är markerad på snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga** för att öppna en dialogruta där du kan redigera frågan för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="72d78-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="72d78-246">På fliken **intervall**, välj **Lägg till** om du vill lägga till frågan.</span><span class="sxs-lookup"><span data-stu-id="72d78-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="72d78-247">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="72d78-248">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="72d78-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="72d78-249">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="72d78-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="72d78-250">**Fält:** *Plats*</span><span class="sxs-lookup"><span data-stu-id="72d78-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="72d78-251">**Kriterier:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="72d78-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="72d78-252">*QMS*-plats är ett lagerställe för kvalitet.</span><span class="sxs-lookup"><span data-stu-id="72d78-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="72d78-253">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="72d78-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="72d78-254">Du måste nu ändra ordningsföljden för direktiven för inköpsorderplats för lagerställe *51*.</span><span class="sxs-lookup"><span data-stu-id="72d78-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="72d78-255">Spara det nya *51 till kvalitet* platsdirektivet, uppdatera sidan och markera platsdirektivet i listan.</span><span class="sxs-lookup"><span data-stu-id="72d78-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="72d78-256">Använd sedan knapparna **Flytta upp** och **Flytta ned** i åtgärdsfönstret för att placera direktivet för lagerställe *51* i följande ordning.</span><span class="sxs-lookup"><span data-stu-id="72d78-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="72d78-257">(Innan du väljer **Flytta upp** eller **Flytta ned** måste du välja ett platsdirektiv i listan.)</span><span class="sxs-lookup"><span data-stu-id="72d78-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="72d78-258">51 till kvalitet</span><span class="sxs-lookup"><span data-stu-id="72d78-258">51 To Quality</span></span>
    2. <span data-ttu-id="72d78-259">51 PO direkt</span><span class="sxs-lookup"><span data-stu-id="72d78-259">51 PO Direct</span></span>
    3. <span data-ttu-id="72d78-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="72d78-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="72d78-261">Menyalternativ på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="72d78-261">Mobile device menu items</span></span>

<span data-ttu-id="72d78-262">Konfigurera ett menyalternativ så att funktionen för **kvalitetskontroll** kan utföras av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="72d78-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="72d78-263">Inlagring av inköp</span><span class="sxs-lookup"><span data-stu-id="72d78-263">Purchase putaway</span></span>

1. <span data-ttu-id="72d78-264">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="72d78-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="72d78-265">I listan, välj menyalternativet **inköpsartikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="72d78-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="72d78-266">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="72d78-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="72d78-267">På avsnittet **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="72d78-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="72d78-268">I den nya raden anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="72d78-269">**Arbetsklass-ID:** *QC-kontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="72d78-270">Ange namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="72d78-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="72d78-271">**Arbetsordertyp:** *kvalitet i kvalitetskontroll*</span><span class="sxs-lookup"><span data-stu-id="72d78-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="72d78-272">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="72d78-273">Inleverans av inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="72d78-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="72d78-274">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="72d78-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="72d78-275">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="72d78-276">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="72d78-277">**Menyalternativnamn:** *Inleverans av inköpsorderrad*</span><span class="sxs-lookup"><span data-stu-id="72d78-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="72d78-278">**Rubrik:** *Inleverans av inköpsorderrad*</span><span class="sxs-lookup"><span data-stu-id="72d78-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="72d78-279">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="72d78-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="72d78-280">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="72d78-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="72d78-281">Ange följande värden på snabbfliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="72d78-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="72d78-282">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="72d78-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="72d78-283">**Arbetsskapandeprocess:** *Inköpsorderrad har inlevererats och inlagrats*</span><span class="sxs-lookup"><span data-stu-id="72d78-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="72d78-284">**Generera ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="72d78-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="72d78-285">**Arbetsmallen:** *51 PO kvitto*</span><span class="sxs-lookup"><span data-stu-id="72d78-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="72d78-286">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="72d78-287">Lägg till menykommandot på en meny för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="72d78-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="72d78-288">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="72d78-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="72d78-289">Välj menyn **Ankommande** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="72d78-290">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="72d78-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="72d78-291">I kolumnen **Tillgängliga menyer och menyartiklar** väljer du det nya menyalternativet **Inleverans av inköpsorderrad**.</span><span class="sxs-lookup"><span data-stu-id="72d78-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="72d78-292">Klicka på högerpilen om du vill flytta **Inleverans av inköpsorderrad** till en kolumn **Menystrukturen**.</span><span class="sxs-lookup"><span data-stu-id="72d78-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="72d78-293">I kolumnen **Menystruktur** väljer du **Inleverans av inköpsorderrad** och sedan knappen uppil eller nedpil för att flytta menyalternativet till önskad plats på menyn för den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="72d78-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="72d78-294">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="72d78-295">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="72d78-295">Example scenario</span></span>

<span data-ttu-id="72d78-296">När du har gjort alla exempel data som du redan har beskrivit och ställt in dem kan du arbeta i det här scenariot för att testa funktionen *Kvalitetskontroll*.</span><span class="sxs-lookup"><span data-stu-id="72d78-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="72d78-297">De värden som visas i det här scenariot förutsätter att du arbetar med standard demodata, att du har valt den juridiska personen **USMF** och att du har förberett exempelposterna som beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="72d78-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="72d78-298">Det här scenariot fungerar även som ett exempel som visar hur funktionen kan användas i en produktionsinställning.</span><span class="sxs-lookup"><span data-stu-id="72d78-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="72d78-299">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="72d78-299">Create a purchase order</span></span>

1. <span data-ttu-id="72d78-300">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="72d78-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="72d78-301">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="72d78-302">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="72d78-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="72d78-303">**Leverantörskonto:** *104*</span><span class="sxs-lookup"><span data-stu-id="72d78-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="72d78-304">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="72d78-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="72d78-305">Välj **OK** för att stänga dialogrutan och öppna den nya inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="72d78-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="72d78-306">På snabbfliken **Inköpsorderrader** innehåller rutnätet en ny tom rad.</span><span class="sxs-lookup"><span data-stu-id="72d78-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="72d78-307">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="72d78-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="72d78-308">**Artikelnummer:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="72d78-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="72d78-309">**Kvantitet:** *3*</span><span class="sxs-lookup"><span data-stu-id="72d78-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="72d78-310">**Enhet:** *PL*</span><span class="sxs-lookup"><span data-stu-id="72d78-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="72d78-311">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72d78-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="72d78-312">Inleverans av processkvalitetskontroll</span><span class="sxs-lookup"><span data-stu-id="72d78-312">Process quality check receiving</span></span>

<span data-ttu-id="72d78-313">När inköps ordern har skapats kan den tas emot med hjälp av menyalternativet **Inleverans av inköpsorderrad** och funktionen för *Kvalitetskontroll*.</span><span class="sxs-lookup"><span data-stu-id="72d78-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="72d78-314">Inleverera lastpall 1</span><span class="sxs-lookup"><span data-stu-id="72d78-314">Receive pallet 1</span></span>

1. <span data-ttu-id="72d78-315">Logga in på distributionslagerappen en användare i lagerställe *51*.</span><span class="sxs-lookup"><span data-stu-id="72d78-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="72d78-316">(Ange *51* som användar-ID och *1* som lösenord.)</span><span class="sxs-lookup"><span data-stu-id="72d78-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="72d78-317">Gå till **inkommande \> inleverans av inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="72d78-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="72d78-318">I fältet **PONUM** anger du inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="72d78-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="72d78-319">Bekräfta inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="72d78-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="72d78-320">I fältet **LINENUM** anger du numret från den inköpsorderrad som inlevereras.</span><span class="sxs-lookup"><span data-stu-id="72d78-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="72d78-321">Eftersom ordern bara har en rad i det här scenariot ska du ange *1* i fältet **LINENUM** för varje mottagningssteg.</span><span class="sxs-lookup"><span data-stu-id="72d78-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="72d78-322">Bekräfta radnumret.</span><span class="sxs-lookup"><span data-stu-id="72d78-322">Confirm the line number.</span></span>
1. <span data-ttu-id="72d78-323">I fältet **QTY** anger du kvantiteten som ska inlevereras.</span><span class="sxs-lookup"><span data-stu-id="72d78-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="72d78-324">Eftersom inköpsordern är för tre lastpallar (*PL*) i det här scenariot och det finns tre mottagningssteg, anger du *1* i fältet **QTY** för varje mottagningssteg.</span><span class="sxs-lookup"><span data-stu-id="72d78-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="72d78-325">Bekräfta kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="72d78-325">Confirm the quantity.</span></span>

    <span data-ttu-id="72d78-326">Sidan **kvalitetskontroll** som visas har inga inmatningsfält.</span><span class="sxs-lookup"><span data-stu-id="72d78-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="72d78-327">Den har bara knappen bekräfta (bockmarkering) längst ned och menyknappen (**≡**) högst upp.</span><span class="sxs-lookup"><span data-stu-id="72d78-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="72d78-328">(Menyknappen kallas ibland för hamburger eller hamburgerknappen.) För att processen för kvalitetskontroll ska kunna påskyndas bekräftar användaren bara sidan kvalitetskontroll när lastpallen passerar **kvalitetskontrollen**.</span><span class="sxs-lookup"><span data-stu-id="72d78-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="72d78-329">![Sidan för kvalitetskontroll](media/quality-check.png "Sidan för kvalitetskontroll")</span><span class="sxs-lookup"><span data-stu-id="72d78-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="72d78-330">Välj knappen bekräftelse om du vill godkänna kvalitetskontrollen för lastpall 1 från rad 1.</span><span class="sxs-lookup"><span data-stu-id="72d78-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="72d78-331">Sidan **inköpsorder: Placera** som visas visar information om det införda arbetet:</span><span class="sxs-lookup"><span data-stu-id="72d78-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="72d78-332">**LOC:** platsen som identifierats av systemet</span><span class="sxs-lookup"><span data-stu-id="72d78-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="72d78-333">Den här platsen är den avsedda inlagringsplatsen för inleverans av inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="72d78-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="72d78-334">**LP:** Det systemgenererade ID-numret</span><span class="sxs-lookup"><span data-stu-id="72d78-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="72d78-335">**Artikel:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="72d78-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="72d78-336">**Qty:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="72d78-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="72d78-337">Även artikelbeskrivningen visas.</span><span class="sxs-lookup"><span data-stu-id="72d78-337">The item description is also shown.</span></span>

1. <span data-ttu-id="72d78-338">Bekräfta artikelinförselarbetet.</span><span class="sxs-lookup"><span data-stu-id="72d78-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="72d78-339">På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört".</span><span class="sxs-lookup"><span data-stu-id="72d78-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="72d78-340">Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.</span><span class="sxs-lookup"><span data-stu-id="72d78-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="72d78-341">Inleverera lastpall 2</span><span class="sxs-lookup"><span data-stu-id="72d78-341">Receive pallet 2</span></span>

<span data-ttu-id="72d78-342">I det här scenariot avvisas lastpall 2.</span><span class="sxs-lookup"><span data-stu-id="72d78-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="72d78-343">I fältet **LINENUM** ange *1* och bekräfta radnumret.</span><span class="sxs-lookup"><span data-stu-id="72d78-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="72d78-344">Fältet **QTY** är nu tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="72d78-344">The **QTY** field is now available.</span></span> <span data-ttu-id="72d78-345">Ange *1* och bekräfta kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="72d78-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="72d78-346">Sidan **Kvalitetskontroll** visas.</span><span class="sxs-lookup"><span data-stu-id="72d78-346">The **Quality check** page appears.</span></span> <span data-ttu-id="72d78-347">För det här inleveransen avvisas lastpallen för kvalitet och kommer att placeras på *QMS* kvalitetsplats.</span><span class="sxs-lookup"><span data-stu-id="72d78-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="72d78-348">Markera menyknappen (**≡**) längst upp på sidan och välj sedan **avvisa** på menyn.</span><span class="sxs-lookup"><span data-stu-id="72d78-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="72d78-349">På sidan **Uppgift** som visas anger du **QMS** som *Placera* plats dit lastpallen ska skickas för vidare granskning.</span><span class="sxs-lookup"><span data-stu-id="72d78-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="72d78-350">Sidan **kvalitet i kvalitetskontroll: Placera** som visas visar information om det införda arbetet:</span><span class="sxs-lookup"><span data-stu-id="72d78-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="72d78-351">**LOC:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="72d78-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="72d78-352">Den här platsen är den avsedda inlagringsplatsen för inleverans av avvisad kvalitet.</span><span class="sxs-lookup"><span data-stu-id="72d78-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="72d78-353">**LP:** Det systemgenererade ID-numret</span><span class="sxs-lookup"><span data-stu-id="72d78-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="72d78-354">**Artikel:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="72d78-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="72d78-355">**Qty:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="72d78-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="72d78-356">Även artikelbeskrivningen visas.</span><span class="sxs-lookup"><span data-stu-id="72d78-356">The item description is also shown.</span></span>

1. <span data-ttu-id="72d78-357">Bekräfta artikelinförselarbetet.</span><span class="sxs-lookup"><span data-stu-id="72d78-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="72d78-358">På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört".</span><span class="sxs-lookup"><span data-stu-id="72d78-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="72d78-359">Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.</span><span class="sxs-lookup"><span data-stu-id="72d78-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="72d78-360">Du har nu slutfört kvalitetskontrollen och skapat en kvalitetsorder för den avvisade lastpallen.</span><span class="sxs-lookup"><span data-stu-id="72d78-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="72d78-361">Om du vill visa den order som skapats gå till **lagerhantering \> periodiska uppgifter \> kvalitetshantering \> kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="72d78-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="72d78-362">Kvalitetsordertestning kan nu bearbetas.</span><span class="sxs-lookup"><span data-stu-id="72d78-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="72d78-363">Kvalitetstestning beskrivs inte i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="72d78-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="72d78-364">Mer information om kvalitetshantering finns i [Översikt över kvalitetshantering](../inventory/enable-quality-management.md).</span><span class="sxs-lookup"><span data-stu-id="72d78-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="72d78-365">Inleverera lastpall 3</span><span class="sxs-lookup"><span data-stu-id="72d78-365">Receive pallet 3</span></span>

<span data-ttu-id="72d78-366">I det här scenariot godkänns lastpall 3.</span><span class="sxs-lookup"><span data-stu-id="72d78-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="72d78-367">I fältet **LINENUM** ange *1* och bekräfta radnumret.</span><span class="sxs-lookup"><span data-stu-id="72d78-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="72d78-368">Fältet **QTY** är nu tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="72d78-368">The **QTY** field is now available.</span></span> <span data-ttu-id="72d78-369">Ange *1* och bekräfta kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="72d78-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="72d78-370">Sidan **Kvalitetskontroll** visas.</span><span class="sxs-lookup"><span data-stu-id="72d78-370">The **Quality check** page appears.</span></span> <span data-ttu-id="72d78-371">För det här inleveransen godkänns lastpallen för kvalitet och kommer att placeras på en inlagringsplatsen i bulk.</span><span class="sxs-lookup"><span data-stu-id="72d78-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="72d78-372">Välj knappen bekräftelse om du vill godkänna kvalitetskontrollen.</span><span class="sxs-lookup"><span data-stu-id="72d78-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="72d78-373">Sidan **inköpsorder: Placera** som visas visar information om det införda arbetet:</span><span class="sxs-lookup"><span data-stu-id="72d78-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="72d78-374">**LOC:** platsen som identifierats av systemet</span><span class="sxs-lookup"><span data-stu-id="72d78-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="72d78-375">Den här platsen är den avsedda inlagringsplatsen för inleverans av inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="72d78-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="72d78-376">**LP:** Det systemgenererade ID-numret</span><span class="sxs-lookup"><span data-stu-id="72d78-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="72d78-377">**Artikel:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="72d78-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="72d78-378">**Qty:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="72d78-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="72d78-379">Även artikelbeskrivningen visas.</span><span class="sxs-lookup"><span data-stu-id="72d78-379">The item description is also shown.</span></span>

1. <span data-ttu-id="72d78-380">Bekräfta artikelinförselarbetet.</span><span class="sxs-lookup"><span data-stu-id="72d78-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="72d78-381">På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört".</span><span class="sxs-lookup"><span data-stu-id="72d78-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="72d78-382">Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.</span><span class="sxs-lookup"><span data-stu-id="72d78-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="72d78-383">Markera menyknappen (**≡**) längst upp på sidan och välj sedan **avbryt** för att återgå till menyn.</span><span class="sxs-lookup"><span data-stu-id="72d78-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="72d78-384">Nu kan du stänga mobilappen.</span><span class="sxs-lookup"><span data-stu-id="72d78-384">You can now close the mobile app.</span></span>
