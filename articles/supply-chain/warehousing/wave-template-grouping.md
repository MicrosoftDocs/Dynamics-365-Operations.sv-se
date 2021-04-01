---
title: Gruppering av påfyllnadsmall
description: Gruppering av påfyllnadsmall gör att systemet kan använda inställningar för påfyllnadsmall för att fastställa, baserat på kriterier som du definierar, hur den ska dela upp frisläppta rader och tilldela dem till ny eller befintlig påfyllnad. Den här funktionen kan vara användbar i lagerställen där påfyllnad skapas baserat på specifika kriterier, men där chefer föredrar att skapa påfyllnad automatiskt i stället för manuellt.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 520338683443105ffd1df7fc2569cd95a5f50879
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245140"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="2b5a6-104">Gruppering av påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b5a6-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b5a6-105">Gruppering av påfyllnadsmall gör att systemet kan använda inställningar för [påfyllnadsmall](tasks/configure-wave-processing.md) för att fastställa, baserat på kriterier som du definierar, hur den ska dela upp frisläppta rader och tilldela dem till ny eller befintlig påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="2b5a6-106">Den här funktionen kan vara användbar i lagerställen där påfyllnad skapas baserat på specifika kriterier, men där chefer föredrar att skapa påfyllnad automatiskt i stället för manuellt.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="2b5a6-107">Det gör det möjligt för systemet att lägga till varje ny frisläppt utleverans till den första påfyllnad som den finner som har matchande värden i en grupp.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="2b5a6-108">Om ingen matchning hittas skapar systemet en ny påfyllnad för den nya försändelsen.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b5a6-109">Gruppering av påfyllnadsmallar stöds inte för arbetstypen *produktion av råmaterialplockning* eller *Kanban-plockning*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="2b5a6-110">Detta beror på att påfyllnadsgrupperingen baseras på försändelser och att dessa arbetstyper inte använder försändelser.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="2b5a6-111">Aktivera funktionen gruppering av påfyllnadsmallar</span><span class="sxs-lookup"><span data-stu-id="2b5a6-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="2b5a6-112">Innan du kan använda funktionen *Gruppering av påfyllnadsmall* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="2b5a6-113">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="2b5a6-114">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="2b5a6-115">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2b5a6-116">**Funktionsnamn:** *Gruppering av påfyllnadsmall*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="2b5a6-117">Ställa in en påfyllnadsmall för att använda en gruppering av påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b5a6-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="2b5a6-118">Följ stegen för att ställa in din gruppering av påfyllnadsmall tillgänglig [påfyllnadsmall](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="2b5a6-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="2b5a6-119">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="2b5a6-120">Välj den påfyllnadsmall som du vill ställa in i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="2b5a6-121">Om du förbereder dig att arbeta under scenariot senare i det här avsnittet genom att använda demodata, ska du välja mallen **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="2b5a6-122">Välj **Redigera** om du vill placera sidan i redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="2b5a6-123">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-124">**Automatisera skapande av påfyllnad:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="2b5a6-125">**Tilldela till öppna vågor:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="2b5a6-126">**Bearbeta påfyllnaden vid släpp till lager:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="2b5a6-127">I åtgärdsfönstret, välj **Redigera fråga** för att öppna dialogrutan för fråga.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="2b5a6-128">I dialogrutan för fråga, på fliken **Sortera** granska sorteringskriterierna och se till att det finns en regel som innehåller fältet som du vill använda för att gruppera dina påfyllnader.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="2b5a6-129">Om du förbereder dig att arbeta genom scenariot genom att använda demodata, lägger du till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="2b5a6-130">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="2b5a6-131">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="2b5a6-132">**Fält:** *Transportföretag*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b5a6-133">När du har valt det här värdet kan följande meddelande visas: "fältet transportföretagstjänst är inte ett indexfält.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="2b5a6-134">Vill du lägga till sortering i det här? "</span><span class="sxs-lookup"><span data-stu-id="2b5a6-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="2b5a6-135">Välj **Ja** om du vill lägga till sortering.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="2b5a6-136">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b5a6-137">Välj **OK** om du vill spara dina ändringar fråga och stänga dialogrutan för fråga.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="2b5a6-138">I åtgärdsfönstret, välj **Gruppering av påfyllnadsmall**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="2b5a6-139">På sidan **Gruppering av påfyllnadsmall**, välj kryssrutan **Gruppera efter** för varje rad som du vill använda för att gruppera dina orderrader i påfyllnad, efter behov.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="2b5a6-140">Om du förbereder dig att arbeta genom scenariot genom att använda demodata markerar du kryssrutan **Gruppera efter** för *Transportföretagstjänsten*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="2b5a6-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-141">Select **Save**.</span></span>
1. <span data-ttu-id="2b5a6-142">Stäng sidan **Gruppering av påfyllnadsmall**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="2b5a6-143">Spara din mall genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="2b5a6-144">Scenario</span><span class="sxs-lookup"><span data-stu-id="2b5a6-144">Scenario</span></span>

<span data-ttu-id="2b5a6-145">I det här avsnittet finns ett skript som du kan arbeta igenom för att lära dig vad funktionen gör och hur du använder den.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="2b5a6-146">Gör exempeldata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="2b5a6-146">Make sample data available</span></span>

<span data-ttu-id="2b5a6-147">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="2b5a6-148">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="2b5a6-149">Du kan också använda detta scenario som vägledning för funktionen när du arbetar med ett produktionssystem.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="2b5a6-150">I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="2b5a6-151">Scenario: Gruppering av påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b5a6-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="2b5a6-152">Det här scenariot visar hur du använder en gruppering av påfyllnadsmall för att automatiskt skapa flera påfyllningar, baserat på de grupperingsinställningar som har definierats i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="2b5a6-153">I det här scenariot ställs påfyllnadsmallen in i systemet för att skapa en påfyllnad per transportföretagstjänst.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="2b5a6-154">Innan du börjar ska du förbereda din påfyllnadsmall på det sätt som beskrivs i [Ställa in en påfyllnadsmall för att använda en gruppering av påfyllnadsmall](#set-up-template) i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="2b5a6-155">Om du kommer att arbeta med demodata för det här scenariot måste du använda de demodatavärden som föreslås i den proceduren.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="2b5a6-156">Den här inställningen grupperar påfyllnader enligt den transportföretagstjänst som ställs in för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="2b5a6-157">Skapa försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-157">Create sales order 1</span></span>

1. <span data-ttu-id="2b5a6-158">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2b5a6-159">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="2b5a6-160">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-161">På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-004*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="2b5a6-162">På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="2b5a6-163">Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="2b5a6-164">Den nya försäljningsordern öppnas i vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="2b5a6-165">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2b5a6-166">Växla till vyn **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="2b5a6-167">På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-168">**Transportföretag:** *Luftfrakt*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="2b5a6-169">**Transportföretag:** *Flyg*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="2b5a6-170">Växla tillbaka till vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="2b5a6-171">I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="2b5a6-172">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-173">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="2b5a6-174">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="2b5a6-175">Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="2b5a6-176">På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="2b5a6-177">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="2b5a6-178">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="2b5a6-179">Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="2b5a6-180">Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="2b5a6-181">Visa påfyllnad som skapades från försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="2b5a6-182">Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="2b5a6-183">Välj påfyllnads-ID som skapades från försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="2b5a6-184">Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="2b5a6-185">Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="2b5a6-186">Skapa försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="2b5a6-186">Create sales order 2</span></span>

1. <span data-ttu-id="2b5a6-187">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2b5a6-188">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="2b5a6-189">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-190">På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-005*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="2b5a6-191">På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="2b5a6-192">Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="2b5a6-193">Den nya försäljningsordern öppnas i vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="2b5a6-194">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2b5a6-195">Växla till vyn **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="2b5a6-196">På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-197">**Transportföretag:** *blomma, flytta*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="2b5a6-198">**Transportföretag:** *Std*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="2b5a6-199">Växla tillbaka till vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="2b5a6-200">I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="2b5a6-201">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-202">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="2b5a6-203">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="2b5a6-204">Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="2b5a6-205">På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="2b5a6-206">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="2b5a6-207">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="2b5a6-208">Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="2b5a6-209">Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="2b5a6-210">Observera att påfyllnads-ID skiljer sig från påfyllnads-ID för den första försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="2b5a6-211">Visa påfyllnad som skapades från försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="2b5a6-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="2b5a6-212">Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="2b5a6-213">Välj påfyllnads-ID som skapades från den andra försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="2b5a6-214">Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="2b5a6-215">Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="2b5a6-216">En ny påfyllnad skapades för den här leveransen eftersom den använder en annan transportföretagstjänst än den första försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="2b5a6-217">Skapa försäljningsorder 3</span><span class="sxs-lookup"><span data-stu-id="2b5a6-217">Create sales order 3</span></span>

1. <span data-ttu-id="2b5a6-218">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2b5a6-219">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="2b5a6-220">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-221">På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-006*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="2b5a6-222">På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="2b5a6-223">Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="2b5a6-224">Den nya försäljningsordern öppnas i vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="2b5a6-225">Anteckna försäljningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2b5a6-226">Växla till vyn **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="2b5a6-227">På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-228">**Transportföretag:** *Luftfrakt*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="2b5a6-229">**Transportföretag:** *Flyg*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="2b5a6-230">Växla tillbaka till vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="2b5a6-231">I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="2b5a6-232">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="2b5a6-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2b5a6-233">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="2b5a6-234">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="2b5a6-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="2b5a6-235">Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="2b5a6-236">På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="2b5a6-237">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="2b5a6-238">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="2b5a6-239">Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="2b5a6-240">Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="2b5a6-241">Försändelsen har tilldelats den befintliga påfyllnaden från den första försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="2b5a6-242">Visa påfyllnad för försäljningsorder 1 och 3</span><span class="sxs-lookup"><span data-stu-id="2b5a6-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="2b5a6-243">Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="2b5a6-244">Välj påfyllnads-ID som skapades från den tredje försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="2b5a6-245">Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="2b5a6-246">Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**, tillsammans med leveransen för den första försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="2b5a6-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]