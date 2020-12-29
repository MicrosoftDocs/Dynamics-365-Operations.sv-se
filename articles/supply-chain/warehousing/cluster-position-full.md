---
title: Klusterposition full
description: Det här ämnet innehåller information om funktionen klusterposition. Den här funktionen erbjuder ett alternativ till en striktare tillämpning av regler för arbetsavbrott när klusterplockning används, eftersom det möjliggör en större felmarginal i volymetriska begränsningar för behållare eller last.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3610725815b35609ee98b69b367db2945bbf166a
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438028"
---
# <a name="cluster-position-full"></a><span data-ttu-id="6437f-104">Klusterposition full</span><span class="sxs-lookup"><span data-stu-id="6437f-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6437f-105">Funktionen *Klusterposition full* erbjuder ett alternativ till en striktare tillämpning av regler för arbetsavbrott när klusterplockning används, eftersom det möjliggör en större felmarginal i volymetriska begränsningar för behållare eller last.</span><span class="sxs-lookup"><span data-stu-id="6437f-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="6437f-106">I ett vanligt scenario ryms inte alla objekt på en arbetsorder i en vald behållare.</span><span class="sxs-lookup"><span data-stu-id="6437f-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="6437f-107">Lagerarbetare som är klusterplockning har få alternativ i det här scenariot: de måste antingen byta till en större behållare eller arbeta med deras arbetsledare för att komma in i en annan lösning.</span><span class="sxs-lookup"><span data-stu-id="6437f-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="6437f-108">Med den här funktionen kan du köra knappen **Full** på en av arbetsenheterna i ett kluster.</span><span class="sxs-lookup"><span data-stu-id="6437f-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="6437f-109">I äldre versioner är det här alternativet bara tillgängligt för plockning med vanlig order, inte för klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="6437f-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="6437f-110">Den här funktionen skiljer sig emellertid från standardknappen **full** för alla på så vis att den avbryter det återstående arbetet.</span><span class="sxs-lookup"><span data-stu-id="6437f-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="6437f-111">Det föreslår inte att användaren lägger till en annan lagerplats i samma kluster och det nya arbetet skapas inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6437f-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="6437f-112">Aktivera funktionen för klusterposition full</span><span class="sxs-lookup"><span data-stu-id="6437f-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="6437f-113">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="6437f-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6437f-114">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="6437f-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="6437f-115">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="6437f-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6437f-116">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="6437f-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6437f-117">**Funktionsnamn:** *Klusterposition full*</span><span class="sxs-lookup"><span data-stu-id="6437f-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="6437f-118">Ställ in</span><span class="sxs-lookup"><span data-stu-id="6437f-118">Setup</span></span>

<span data-ttu-id="6437f-119">Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du ställer in och använder funktion *Klusterposition full*.</span><span class="sxs-lookup"><span data-stu-id="6437f-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="6437f-120">Gör exempeldata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="6437f-120">Make sample data available</span></span>

<span data-ttu-id="6437f-121">Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="6437f-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="6437f-122">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="6437f-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="6437f-123">Du kan också använda exempelscenariot som vägledning för att arbeta med den här funktionen i ett produktionssystem.</span><span class="sxs-lookup"><span data-stu-id="6437f-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="6437f-124">I så fall måste du dock ersätta dina egna värden för varje inställning som beskrivs här.</span><span class="sxs-lookup"><span data-stu-id="6437f-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="6437f-125">Klusterprofiler</span><span class="sxs-lookup"><span data-stu-id="6437f-125">Cluster profiles</span></span>

<span data-ttu-id="6437f-126">Du måste ange om kluster-ID ska genereras automatiskt, hur många positioner som används, när kluster bryts och hur plockningsarbetet sekvenseras och verifieras.</span><span class="sxs-lookup"><span data-stu-id="6437f-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="6437f-127">Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.</span><span class="sxs-lookup"><span data-stu-id="6437f-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="6437f-128">I listfönstret, välj **Skapa kluster**.</span><span class="sxs-lookup"><span data-stu-id="6437f-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="6437f-129">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="6437f-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="6437f-130">**Generera kluster-ID:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="6437f-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="6437f-131">**Aktivera positioner:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="6437f-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="6437f-132">**Antal positioner:** *2*</span><span class="sxs-lookup"><span data-stu-id="6437f-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="6437f-133">**Positionsnamn:** *numerisk*</span><span class="sxs-lookup"><span data-stu-id="6437f-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="6437f-134">**Bryt kluster på:** *placera*</span><span class="sxs-lookup"><span data-stu-id="6437f-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="6437f-135">**Sortera verifieringstyp:** *positionsskanning*</span><span class="sxs-lookup"><span data-stu-id="6437f-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="6437f-136">På snabbfliken **klustersortering**.</span><span class="sxs-lookup"><span data-stu-id="6437f-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="6437f-137">Rutnätet bör vara tomt (dvs inte ha några rader).</span><span class="sxs-lookup"><span data-stu-id="6437f-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="6437f-138">Arbetsmallar</span><span class="sxs-lookup"><span data-stu-id="6437f-138">Work templates</span></span>

<span data-ttu-id="6437f-139">Du måste definiera hur plockningsarbetet för klusterplockning skapas.</span><span class="sxs-lookup"><span data-stu-id="6437f-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="6437f-140">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="6437f-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="6437f-141">Ställ in knappen högst upp på sidan **arbetsordertyp** till *försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="6437f-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="6437f-142">Se till att följande arbetsmallar från demonstrationsdata visas i listan.</span><span class="sxs-lookup"><span data-stu-id="6437f-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="6437f-143">Om de inte är tillgängliga kan du inte slutföra scenariot.</span><span class="sxs-lookup"><span data-stu-id="6437f-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="6437f-144">61 SO steg</span><span class="sxs-lookup"><span data-stu-id="6437f-144">61 SO Stage</span></span>
    - <span data-ttu-id="6437f-145">61 SO klusterplockning</span><span class="sxs-lookup"><span data-stu-id="6437f-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="6437f-146">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="6437f-146">Location directives</span></span>

<span data-ttu-id="6437f-147">Du måste ange var artiklar plockas från och var de placeras.</span><span class="sxs-lookup"><span data-stu-id="6437f-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="6437f-148">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="6437f-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6437f-149">I listrubriken, ange **Inköpsorder** i fältet till *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="6437f-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="6437f-150">Se till att följande försäljningsorderdirektiv från demonstrationsdata visas i listan.</span><span class="sxs-lookup"><span data-stu-id="6437f-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="6437f-151">Om de inte är tillgängliga kan du inte slutföra scenariot.</span><span class="sxs-lookup"><span data-stu-id="6437f-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="6437f-152">61 klusterplockning</span><span class="sxs-lookup"><span data-stu-id="6437f-152">61 Cluster pick</span></span>
    - <span data-ttu-id="6437f-153">61 SO välj order</span><span class="sxs-lookup"><span data-stu-id="6437f-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="6437f-154">Menyalternativ på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="6437f-154">Mobile device menu items</span></span>

<span data-ttu-id="6437f-155">Du måste konfigurera ett menyalternativ för mobila enheter för att använda befintligt arbete som dirigeras av klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="6437f-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="6437f-156">I menyalternativet för mobila enheter för klusterplockning måste parametern **Tillåt delning av arbete** vara aktiverad och arbetsklassen *SO plocka* måste läggas till.</span><span class="sxs-lookup"><span data-stu-id="6437f-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="6437f-157">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="6437f-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6437f-158">I listfönstret, välj **Skapa klusterplockning**.</span><span class="sxs-lookup"><span data-stu-id="6437f-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="6437f-159">Välj **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6437f-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="6437f-160">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="6437f-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6437f-161">**Dirigerad av:** *klusterplockning*</span><span class="sxs-lookup"><span data-stu-id="6437f-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="6437f-162">**Generera ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="6437f-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="6437f-163">**Tillåt delning av arbete:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="6437f-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="6437f-164">**Kluster profil-ID:** *skapa kluster*</span><span class="sxs-lookup"><span data-stu-id="6437f-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="6437f-165">Acceptera standardvärden för alla andra fält.</span><span class="sxs-lookup"><span data-stu-id="6437f-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="6437f-166">På snabbfliken **Arbetsklasser** lägger du till följande två rader, om det behövs:</span><span class="sxs-lookup"><span data-stu-id="6437f-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="6437f-167">Rad 1 (förekommer vanligen i demonstrationsdata):</span><span class="sxs-lookup"><span data-stu-id="6437f-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="6437f-168">**Arbetsklass-ID:** *Försäljning*</span><span class="sxs-lookup"><span data-stu-id="6437f-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="6437f-169">**Typ av arbetsorder:** *försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="6437f-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="6437f-170">Rad 2 (förekommer förmodligen inte i demonstrationsdata):</span><span class="sxs-lookup"><span data-stu-id="6437f-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="6437f-171">**Arbetsklass-ID:** *SO plockning*</span><span class="sxs-lookup"><span data-stu-id="6437f-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="6437f-172">**Typ av arbetsorder:** *försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="6437f-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="6437f-173">Gå till **Inställningar för arbetsbekräftelse** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6437f-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="6437f-174">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="6437f-174">Select **Edit**.</span></span>
1. <span data-ttu-id="6437f-175">Ange följande värden på raden i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="6437f-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="6437f-176">**Arbetstyp** - *plockning*</span><span class="sxs-lookup"><span data-stu-id="6437f-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="6437f-177">**Produktbekräftelse** - *Markera kryssrutan*</span><span class="sxs-lookup"><span data-stu-id="6437f-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="6437f-178">Välj **Spara** i åtgärdsfönstret och stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6437f-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="6437f-179">Skapa plockarbete</span><span class="sxs-lookup"><span data-stu-id="6437f-179">Create picking work</span></span>

<span data-ttu-id="6437f-180">Innan du kan starta klusterplockning måste du skapa ett visst utgående arbete.</span><span class="sxs-lookup"><span data-stu-id="6437f-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="6437f-181">Den klusterprofil som du skapade tidigare anger två klusterpositioner.</span><span class="sxs-lookup"><span data-stu-id="6437f-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="6437f-182">Därför måste minst två arbets-ID skapas för plockning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="6437f-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="6437f-183">I det här scenariot inträffar transaktionerna i lagerställe *61* och de använder artiklarna *L0101* och *T0100*.</span><span class="sxs-lookup"><span data-stu-id="6437f-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="6437f-184">Demonstrationsdata bör ha tillräcklig lagerbehållning av dessa artiklar.</span><span class="sxs-lookup"><span data-stu-id="6437f-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="6437f-185">Kontrollera att det finns tillräckligt med lager för att slutföra transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="6437f-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="6437f-186">Skapa försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="6437f-186">Create sales order 1</span></span>

1. <span data-ttu-id="6437f-187">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="6437f-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6437f-188">Skapa försäljningsorder 1 genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6437f-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="6437f-189">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="6437f-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6437f-190">**Kundkonto:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="6437f-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="6437f-191">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="6437f-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="6437f-192">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6437f-192">Select **OK**.</span></span>
1. <span data-ttu-id="6437f-193">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="6437f-193">The new sales order is opened.</span></span> <span data-ttu-id="6437f-194">På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6437f-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="6437f-195">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="6437f-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="6437f-196">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="6437f-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="6437f-197">På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="6437f-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="6437f-198">På snabbfliken **försäljningsorderrader** lägger du till en andra rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6437f-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="6437f-199">**Artikelnummer:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="6437f-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="6437f-200">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="6437f-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="6437f-201">På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="6437f-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="6437f-202">För varje rad som du just har lagt till följer du stegen nedan för att reservera lagret:</span><span class="sxs-lookup"><span data-stu-id="6437f-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="6437f-203">Välj den rad som du vill reservera.</span><span class="sxs-lookup"><span data-stu-id="6437f-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="6437f-204">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="6437f-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="6437f-205">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="6437f-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="6437f-206">Stäng sidan **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="6437f-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="6437f-207">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="6437f-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6437f-208">När släppningen är klar får du informationsmeddelanden som visar påfyllnads- och last-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="6437f-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="6437f-209">Skapa försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="6437f-209">Create sales order 2</span></span>

1. <span data-ttu-id="6437f-210">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="6437f-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6437f-211">Skapa försäljningsorder 2 genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6437f-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="6437f-212">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="6437f-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6437f-213">**Kundkonto:** *US-011*</span><span class="sxs-lookup"><span data-stu-id="6437f-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="6437f-214">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="6437f-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="6437f-215">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6437f-215">Select **OK**.</span></span>
1. <span data-ttu-id="6437f-216">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="6437f-216">The new sales order is opened.</span></span> <span data-ttu-id="6437f-217">På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6437f-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="6437f-218">**Artikelnummer:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="6437f-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="6437f-219">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="6437f-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="6437f-220">På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="6437f-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="6437f-221">På snabbfliken **försäljningsorderrader** lägger du till en andra rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6437f-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="6437f-222">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="6437f-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="6437f-223">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="6437f-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="6437f-224">På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="6437f-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="6437f-225">För varje rad som du just har lagt till följer du stegen nedan för att reservera lagret:</span><span class="sxs-lookup"><span data-stu-id="6437f-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="6437f-226">Välj den rad som du vill reservera.</span><span class="sxs-lookup"><span data-stu-id="6437f-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="6437f-227">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="6437f-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="6437f-228">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="6437f-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="6437f-229">Stäng sidan **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="6437f-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="6437f-230">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="6437f-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6437f-231">När släppningen är klar får du informationsmeddelanden som visar påfyllnads- och last-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="6437f-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="6437f-232">Hämta arbets-ID och ID-nummer</span><span class="sxs-lookup"><span data-stu-id="6437f-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="6437f-233">Två arbets-ID ska ha skapats, där alla har två plockningsrader.</span><span class="sxs-lookup"><span data-stu-id="6437f-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="6437f-234">Följ dessa steg för att hitta arbets-ID:n och tilldelningarna av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="6437f-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="6437f-235">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="6437f-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="6437f-236">I rutnätet **översikt** söker du i kolumnen **Ordernummer** efter de två försäljningsorder som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="6437f-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="6437f-237">Anteckna motsvarande arbets-ID för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="6437f-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="6437f-238">Markera raden för varje försäljningsorder om du vill visa relaterad information i rutnätet **rader**.</span><span class="sxs-lookup"><span data-stu-id="6437f-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="6437f-239">Anteckna platsen som varje artikel ska plockas från.</span><span class="sxs-lookup"><span data-stu-id="6437f-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="6437f-240">Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.</span><span class="sxs-lookup"><span data-stu-id="6437f-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="6437f-241">I åtgärdsfönstret välj **Dimensioner** om du vill öppna dialogrutan **Dimensionsvisning**.</span><span class="sxs-lookup"><span data-stu-id="6437f-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="6437f-242">Kontrollera att kryssrutorna **ID-nummer**, **Lagerställe** och **Artikelnummer** är markerade och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6437f-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="6437f-243">I rutan **Filter** ange följande filter:</span><span class="sxs-lookup"><span data-stu-id="6437f-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="6437f-244">**Artikelnummer** – **är ett av** – *L0101* och *T100*</span><span class="sxs-lookup"><span data-stu-id="6437f-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="6437f-245">**Lagerställe** – **börjar med** – *61*</span><span class="sxs-lookup"><span data-stu-id="6437f-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="6437f-246">Anteckna vilket värde **ID-numret** visar.</span><span class="sxs-lookup"><span data-stu-id="6437f-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="6437f-247">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="6437f-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="6437f-248">Flödeskörning av mobila enheter – arbetsbekräftelse inställningar för produkten</span><span class="sxs-lookup"><span data-stu-id="6437f-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="6437f-249">Logga in på distributionslagerappen en användare i lager ställe *61*.</span><span class="sxs-lookup"><span data-stu-id="6437f-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="6437f-250">Gå till **utgående \> Skapa klusterplockning**.</span><span class="sxs-lookup"><span data-stu-id="6437f-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="6437f-251">Sidan **UPPGIFT: tilldela arbete till kluster** visas.</span><span class="sxs-lookup"><span data-stu-id="6437f-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="6437f-252">Ange arbets-ID för försäljningsorder 1 om du vill tilldela det till klusterposition 1.</span><span class="sxs-lookup"><span data-stu-id="6437f-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="6437f-253">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-254">Ange arbets-ID för försäljningsorder 2 om du vill tilldela det till klusterposition 2.</span><span class="sxs-lookup"><span data-stu-id="6437f-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="6437f-255">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="6437f-256">Sidan **UPPGIFT: Skapa klusterplockning: plockning** visas och visar *objekt L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="6437f-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="6437f-257">Eftersom klusterprofilen ställer in antalet positioner till 2, dirigerar systemet automatiskt till den första konsolideringsplockningen: två lastpallar (PL) för artikel *L0101*.</span><span class="sxs-lookup"><span data-stu-id="6437f-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="6437f-258">Du kan när som helst under följande steg välja fliken **Detaljer** vill visa ytterligare information om uppgiften, t.ex. plockningsplatsen.</span><span class="sxs-lookup"><span data-stu-id="6437f-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="6437f-259">Ange fältet **ITEM** till *L0101*.</span><span class="sxs-lookup"><span data-stu-id="6437f-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="6437f-260">Detta bekräftar artikelnumret, vilket krävs för det här menyalternativet (du har konfigurerat det tidigare genom att välja **Inställningar för arbetsbekräftelse** på sidan **menyalternativ för mobila enheter** när du skapade menyalternativet).</span><span class="sxs-lookup"><span data-stu-id="6437f-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="6437f-261">Ange det ID-nummer som är kopplat till artikeln på det lagerställe som plockas.</span><span class="sxs-lookup"><span data-stu-id="6437f-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="6437f-262">Du ska plocka två lastpallar.</span><span class="sxs-lookup"><span data-stu-id="6437f-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="6437f-263">Ange fältet **LP** till *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="6437f-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="6437f-264">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="6437f-265">Sidan **UPPGIFT: sortera: skapa plockningsklustret** visas.</span><span class="sxs-lookup"><span data-stu-id="6437f-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="6437f-266">Här kan du sortera de två plockade lastpallarna på en plockposition.</span><span class="sxs-lookup"><span data-stu-id="6437f-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="6437f-267">Den här befattningen kan vara en last eller en behållare som används för att separera det plockade lagret efter försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="6437f-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="6437f-268">Visa de detaljer som visas för artikeln (*L0101*) och kvantiteten (*20* ea) som ska sorteras i position 1 (för försäljningsorder 1).</span><span class="sxs-lookup"><span data-stu-id="6437f-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="6437f-269">Ställ in fältet **POSITION NA** till *1*.</span><span class="sxs-lookup"><span data-stu-id="6437f-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="6437f-270">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-271">Visa de detaljer som visas för artikeln (*L0101*) och kvantiteten (*20* ea) som ska sorteras i position 2 (för försäljningsorder 2).</span><span class="sxs-lookup"><span data-stu-id="6437f-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="6437f-272">Ställ in fältet **POSITION NA** till *2*.</span><span class="sxs-lookup"><span data-stu-id="6437f-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="6437f-273">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="6437f-274">Sidan **UPPGIFT: Skapa klusterplockning: plockning** visas och visar *objekt T0100 7 ea*.</span><span class="sxs-lookup"><span data-stu-id="6437f-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="6437f-275">I det här scenariot kan position 1 inte acceptera hela kvantiteten av artiklar som måste plockas för att uppfylla försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="6437f-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="6437f-276">En position måste markeras som full.</span><span class="sxs-lookup"><span data-stu-id="6437f-276">A position must be marked as full.</span></span> <span data-ttu-id="6437f-277">I det här scenariot ska du utföra en delvis plockning av den andra artikeln.</span><span class="sxs-lookup"><span data-stu-id="6437f-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="6437f-278">Den andra artikeln plockas delvis för position 1 och nytt arbete skapas för att plocka den resterande kvantiteten för att uppfylla ordern.</span><span class="sxs-lookup"><span data-stu-id="6437f-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="6437f-279">Välj Meny-knappen (kallas ibland hamburger eller knappen hamburger) och välj sedan **Position full**.</span><span class="sxs-lookup"><span data-stu-id="6437f-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="6437f-280">Identifiera den befattning som är full och välj *1*.</span><span class="sxs-lookup"><span data-stu-id="6437f-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="6437f-281">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-282">Ange den plockningskvantitet som kan fortfarande plockas på position 1.</span><span class="sxs-lookup"><span data-stu-id="6437f-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="6437f-283">Systemet kan bestämma vilket artikelnummer som plockas.</span><span class="sxs-lookup"><span data-stu-id="6437f-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="6437f-284">Ange *2*.</span><span class="sxs-lookup"><span data-stu-id="6437f-284">Enter *2*.</span></span>
1. <span data-ttu-id="6437f-285">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-286">Bekräfta artikelnumret för att slutföra plockningen av den återstående artikeln på position 2.</span><span class="sxs-lookup"><span data-stu-id="6437f-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="6437f-287">Ange fältet **ITEM** till *T0100*.</span><span class="sxs-lookup"><span data-stu-id="6437f-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="6437f-288">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-289">Ange det ID-nummer som artikeln plockas från genom att ställa in fältet **LP** på *LPREPL04* .</span><span class="sxs-lookup"><span data-stu-id="6437f-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="6437f-290">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-291">Visa de detaljer som visas för artikeln (*T0100*) och kvantiteten (*2* ea) som ska sorteras i position 2 (för försäljningsorder 2).</span><span class="sxs-lookup"><span data-stu-id="6437f-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="6437f-292">Ställ in fältet **POSITION NA** till *2*.</span><span class="sxs-lookup"><span data-stu-id="6437f-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="6437f-293">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="6437f-294">Visa de detaljer som visas för artikeln (*T0100*) och kvantiteten (*2* ea) som ska sorteras i position 1 (för försäljningsorder 1).</span><span class="sxs-lookup"><span data-stu-id="6437f-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="6437f-295">Ställ in fältet **POSITION NA** till *1*.</span><span class="sxs-lookup"><span data-stu-id="6437f-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="6437f-296">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="6437f-297">Sidan **UPPGIFT: skapa plockningsklustret: placera** visas.</span><span class="sxs-lookup"><span data-stu-id="6437f-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="6437f-298">I det här scenariot har klusterplockningen slutförts och användaren måste föra in de plockade artiklarna från position 1 och position 2 till mellanlagringsplatsen *STAGE01* .</span><span class="sxs-lookup"><span data-stu-id="6437f-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="6437f-299">Granska informationen på sidan.</span><span class="sxs-lookup"><span data-stu-id="6437f-299">Review the information on the page.</span></span> <span data-ttu-id="6437f-300">Det visar att en total kvantitet på *44* kommer att placeras på mellanlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="6437f-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="6437f-301">Välj **OK** (kryssmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="6437f-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="6437f-302">Du får ett meddelande att "klustret är slutfört".</span><span class="sxs-lookup"><span data-stu-id="6437f-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="6437f-303">Nu kan du använda **försäljningsplockning** för att plocka den resterande kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6437f-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="6437f-304">Du kan sedan använda menyobjektet **försäljningslast** för att flytta artiklarna från mellanlagringsplatsen till lastkaj.</span><span class="sxs-lookup"><span data-stu-id="6437f-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>
