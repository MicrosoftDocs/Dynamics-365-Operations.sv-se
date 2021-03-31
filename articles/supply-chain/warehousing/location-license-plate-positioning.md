---
title: Placering för plats-ID-nummer
description: Med hjälp av placering av ID-nummer kan du se var ett ID-nummer finns på en plats för flera lastpallar, t.ex. en plats där dubbel djupgående lastpall används.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: cfab8c36adb08f799305a153589926bfc1ae31fe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217111"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="730e5-103">Placering för plats-ID-nummer</span><span class="sxs-lookup"><span data-stu-id="730e5-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="730e5-104">Med hjälp av placering av ID-nummer kan du se var ett ID-nummer finns på en plats för flera lastpallar, t.ex. en plats där dubbel djupgående lastpall används.</span><span class="sxs-lookup"><span data-stu-id="730e5-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="730e5-105">Funktionen lägger till ett löpnummer för varje ID-nummer som placeras på en lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="730e5-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="730e5-106">Detta sekvensnumme används för att beställa ID-nummer på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="730e5-107">Det innebär att funktionen intelligent stöder scenarier där kunder använder ett gravitations hyllsystem och måste känna till vilka ID-nummer som finns på framsidan.</span><span class="sxs-lookup"><span data-stu-id="730e5-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="730e5-108">Det här ämnet innehåller en sammanfattning av hur du ställer in och använder funktionen.</span><span class="sxs-lookup"><span data-stu-id="730e5-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="730e5-109">Aktivera funktionen för placering av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="730e5-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="730e5-110">Innan du kan använda positionering av ID-nummer måste funktionen aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="730e5-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="730e5-111">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="730e5-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="730e5-112">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="730e5-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="730e5-113">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="730e5-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="730e5-114">**Funktionens namn:** *Plats för positionering av ID-nummer*</span><span class="sxs-lookup"><span data-stu-id="730e5-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="730e5-115">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="730e5-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="730e5-116">Gör exempeldata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="730e5-116">Make sample data available</span></span>

<span data-ttu-id="730e5-117">För att arbeta igenom scenariot genom att använda värdena som föreslås här måste du arbeta på ett system där exempeldata är installerat.</span><span class="sxs-lookup"><span data-stu-id="730e5-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="730e5-118">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="730e5-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="730e5-119">Ställ in funktionen för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="730e5-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="730e5-120">Slutför följande procedurer för att ställa in funktionen *Plats för positionering av ID-nummer* för det scenario som visas i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="730e5-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="730e5-121">Platsprofiler</span><span class="sxs-lookup"><span data-stu-id="730e5-121">Location profiles</span></span>

<span data-ttu-id="730e5-122">Funktionen måste vara aktiverad i platsprofilen för varje plats där den ska användas.</span><span class="sxs-lookup"><span data-stu-id="730e5-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="730e5-123">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="730e5-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="730e5-124">I listan över platsprofiler i det vänstra fönstret väljer du **BULK-06**.</span><span class="sxs-lookup"><span data-stu-id="730e5-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="730e5-125">På snabbfliken **Allmänt** har två nya alternativ lagts till av funktionen.</span><span class="sxs-lookup"><span data-stu-id="730e5-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="730e5-126">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="730e5-126">Set the following values:</span></span>

    - <span data-ttu-id="730e5-127">**Aktivera placering av ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="730e5-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="730e5-128">När det här alternativet är inställt på *Ja* placeringen av ID-nummer att behållas för ID-nummer på platsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="730e5-129">**Visa mobila enhetens LP-position:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="730e5-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="730e5-130">När det här alternativet är inställt på *Ja* visas ID-numrets position för användare av mobila enheter vid justering och inventering.</span><span class="sxs-lookup"><span data-stu-id="730e5-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="730e5-131">Du kan bara ändra inställningen för det här alternativet om funktionen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="730e5-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="730e5-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="730e5-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="730e5-133">Platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="730e5-133">Location directives</span></span>

1. <span data-ttu-id="730e5-134">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="730e5-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="730e5-135">I det vänstra fönstret kontrollerar du att fältet **Arbetsordertyp** är inställt på *försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="730e5-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="730e5-136">I listan över platsdirektiv väljer du **61 SO plockningsorder**.</span><span class="sxs-lookup"><span data-stu-id="730e5-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="730e5-137">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="730e5-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="730e5-138">På snabbfliken **Rader** markerar du raden som har ett **Löpnummer** värde på *2*.</span><span class="sxs-lookup"><span data-stu-id="730e5-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="730e5-139">På snabbfliken **Platsdirektivåtgärder** markerar du raden som har värdet **Namn** för *Plocka för mindre än lastpall* (den ska vara en enda rad) och ändra värdet för **löpnumret** till *2*.</span><span class="sxs-lookup"><span data-stu-id="730e5-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="730e5-140">Välj **Ny** ovanför rutnätet för att lägga till en rad för en ny platsdirektivåtgärd.</span><span class="sxs-lookup"><span data-stu-id="730e5-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="730e5-141">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="730e5-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="730e5-142">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="730e5-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="730e5-143">**Namn:** *Välj position 1*</span><span class="sxs-lookup"><span data-stu-id="730e5-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="730e5-144">Medan den nya raden fortfarande är markerad väljer du **redigeringsfråga** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="730e5-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="730e5-145">I frågeredigeraren, välj fliken **kopplingar**.</span><span class="sxs-lookup"><span data-stu-id="730e5-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="730e5-146">Expandera registerkoppling **Platser** för att visa kopplingen till registret **Lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="730e5-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="730e5-147">Expandera registerkoppling **Lagerdimensioner** för att visa kopplingen till registret **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="730e5-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="730e5-148">Välj **Lagerdimensioner** och välj sedan **Lägg till registerkoppling**.</span><span class="sxs-lookup"><span data-stu-id="730e5-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="730e5-149">I listan över register som visas i kolumnen **Relation** välj **ID-nummer (ID-nummer)**.</span><span class="sxs-lookup"><span data-stu-id="730e5-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="730e5-150">Välj sedan **Välj** för att lägga till **ID-nummer** i registerkoppling **Lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="730e5-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="730e5-151">När **ID-nummer** fortfarande är markerad väljer du **Lägg till registerkoppling**.</span><span class="sxs-lookup"><span data-stu-id="730e5-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="730e5-152">I listan över register som visas i kolumnen **Relation** välj **Plats för positionering av ID-nummer (ID-nummer)**.</span><span class="sxs-lookup"><span data-stu-id="730e5-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="730e5-153">Välj sedan **Välj** för att lägga till **Plats för positionering av ID-nummer** i registerkoppling **Lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="730e5-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="730e5-154">![Registerkopplingar](media/LpTableJoin.png "Registerkopplingar")</span><span class="sxs-lookup"><span data-stu-id="730e5-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="730e5-155">Välj **OK** om du vill bekräfta de uppdaterade kopplade register och stäng frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="730e5-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="730e5-156">På snabbfliken **Platsdirektivåtgärd**, välj **Redigera fråga** igen för att öppna frågeredigeraren igen.</span><span class="sxs-lookup"><span data-stu-id="730e5-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="730e5-157">På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="730e5-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="730e5-158">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="730e5-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="730e5-159">**Register:** *Plats för positionering av ID-nummer*</span><span class="sxs-lookup"><span data-stu-id="730e5-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="730e5-160">**Härlett register:** *Plats för positionering av ID-nummer*</span><span class="sxs-lookup"><span data-stu-id="730e5-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="730e5-161">**Fält:** *LP-position*</span><span class="sxs-lookup"><span data-stu-id="730e5-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="730e5-162">**Kriterier:** *1*</span><span class="sxs-lookup"><span data-stu-id="730e5-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="730e5-163">![Nytt intervall](media/LpPositionCriteria.png "Nytt intervall")</span><span class="sxs-lookup"><span data-stu-id="730e5-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="730e5-164">Välj **OK** om du vill bekräfta dina ändringar fråga och stänga frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="730e5-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="730e5-165">Ställ in exempeldata för det här scenariot</span><span class="sxs-lookup"><span data-stu-id="730e5-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="730e5-166">I det här scenariot måste användaren logga in på mobilappen för lagerstyrning genom att använda en arbetare som har ställts in för lagerställe *61* för att utföra arbete.</span><span class="sxs-lookup"><span data-stu-id="730e5-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="730e5-167">Användaren måste också genomföra transaktioner.</span><span class="sxs-lookup"><span data-stu-id="730e5-167">The user must also complete transactions.</span></span>

<span data-ttu-id="730e5-168">Eftersom funktionen *Plats för positionering av ID-nummer* lägger till en ny identifierare för ID-nummer på en plats måste du först skapa vissa data för att stödja scenariot.</span><span class="sxs-lookup"><span data-stu-id="730e5-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="730e5-169">Punktinventering för den första platsen</span><span class="sxs-lookup"><span data-stu-id="730e5-169">Spot-count the first location</span></span>

1. <span data-ttu-id="730e5-170">Öppna lagermobilappen och logga in på lagerställe *61*.</span><span class="sxs-lookup"><span data-stu-id="730e5-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="730e5-171">Gå till **Lager \> Punktinventering**.</span><span class="sxs-lookup"><span data-stu-id="730e5-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="730e5-172">På sidan **Punktinventering** ange fältet **Plats** till *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="730e5-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="730e5-173">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-173">Select **OK**.</span></span>

    <span data-ttu-id="730e5-174">På sidan visas den plats du har angett.</span><span class="sxs-lookup"><span data-stu-id="730e5-174">The page shows the location that you entered.</span></span> <span data-ttu-id="730e5-175">Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"</span><span class="sxs-lookup"><span data-stu-id="730e5-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="730e5-176">Välj **uppdatera** om du vill lägga till ett antal på platsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="730e5-177">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0001*.</span><span class="sxs-lookup"><span data-stu-id="730e5-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="730e5-178">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-178">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-179">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan värdet *LP1001* (eller något annat alternativ för ID-numret som du väljer).</span><span class="sxs-lookup"><span data-stu-id="730e5-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="730e5-180">Sidan **Rullande inventering: Lägg till ny LP eller artikel** visar **Placering av ID-nummer 1**.</span><span class="sxs-lookup"><span data-stu-id="730e5-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="730e5-181">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-181">Select **OK**.</span></span>

    <span data-ttu-id="730e5-182">Du måste nu ange kvantiteten för den artikel som räknas på ID-numret.</span><span class="sxs-lookup"><span data-stu-id="730e5-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="730e5-183">Ange fältet **Kvt** till *10*.</span><span class="sxs-lookup"><span data-stu-id="730e5-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="730e5-184">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-184">Select **OK**.</span></span>

    <span data-ttu-id="730e5-185">På sidan visas den plats du har angett.</span><span class="sxs-lookup"><span data-stu-id="730e5-185">The page shows the location that you entered.</span></span> <span data-ttu-id="730e5-186">Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"</span><span class="sxs-lookup"><span data-stu-id="730e5-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="730e5-187">Välj **uppdatera** om du vill lägga till ett annat antal på platsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="730e5-188">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0002*.</span><span class="sxs-lookup"><span data-stu-id="730e5-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="730e5-189">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-189">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-190">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan det värde *LP1002* (eller något annat ID-nummer som du har valt, förutsatt att det skiljer sig från det ID-nummer som du angav tidigare).</span><span class="sxs-lookup"><span data-stu-id="730e5-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="730e5-191">Ändra placeringen av ID-nummer genom att ställa in fältet **LP-position** på *2*.</span><span class="sxs-lookup"><span data-stu-id="730e5-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="730e5-192">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-192">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-193">Ange kvantiteten för artikeln som inventeras på ID-numret genom att ställa in fältet **Kvt** på *10*.</span><span class="sxs-lookup"><span data-stu-id="730e5-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="730e5-194">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-194">Select **OK**.</span></span>

    <span data-ttu-id="730e5-195">På sidan visas den plats du har angett.</span><span class="sxs-lookup"><span data-stu-id="730e5-195">The page shows the location that you entered.</span></span> <span data-ttu-id="730e5-196">Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"</span><span class="sxs-lookup"><span data-stu-id="730e5-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="730e5-197">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-197">Select **OK**.</span></span>

<span data-ttu-id="730e5-198">Arbetet har nu slutförts.</span><span class="sxs-lookup"><span data-stu-id="730e5-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="730e5-199">Punktinventering för den andra platsen</span><span class="sxs-lookup"><span data-stu-id="730e5-199">Spot-count the second location</span></span>

1. <span data-ttu-id="730e5-200">På sidan **Punktinventering** ange fältet **Plats** till *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="730e5-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="730e5-201">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-201">Select **OK**.</span></span>

    <span data-ttu-id="730e5-202">På sidan visas den plats du har angett.</span><span class="sxs-lookup"><span data-stu-id="730e5-202">The page shows the location that you entered.</span></span> <span data-ttu-id="730e5-203">Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"</span><span class="sxs-lookup"><span data-stu-id="730e5-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="730e5-204">Välj **uppdatera** om du vill lägga till ett antal på platsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="730e5-205">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0002*.</span><span class="sxs-lookup"><span data-stu-id="730e5-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="730e5-206">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-206">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-207">På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan det värde *LP1003* (eller något annat ID-nummer som du har valt, förutsatt att det skiljer sig från de båda ID-nummer som du angav i den föregående proceduren).</span><span class="sxs-lookup"><span data-stu-id="730e5-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="730e5-208">Sidan **Rullande inventering: Lägg till ny LP eller artikel** visar **Placering av ID-nummer 1**.</span><span class="sxs-lookup"><span data-stu-id="730e5-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="730e5-209">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-209">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-210">Ange kvantiteten för artikeln som inventeras på ID-numret genom att ställa in fältet **Kvt** på *10*.</span><span class="sxs-lookup"><span data-stu-id="730e5-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="730e5-211">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-211">Select **OK**.</span></span>

    <span data-ttu-id="730e5-212">På sidan visas den plats du har angett.</span><span class="sxs-lookup"><span data-stu-id="730e5-212">The page shows the location that you entered.</span></span> <span data-ttu-id="730e5-213">Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"</span><span class="sxs-lookup"><span data-stu-id="730e5-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="730e5-214">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-214">Select **OK**.</span></span>

<span data-ttu-id="730e5-215">Arbetet har nu slutförts.</span><span class="sxs-lookup"><span data-stu-id="730e5-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="730e5-216">Information om arbete</span><span class="sxs-lookup"><span data-stu-id="730e5-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="730e5-217">Antalet inventeringar från mobilappen för att skapa rullande inventeringsarbete i Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="730e5-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="730e5-218">Arbetet kräver att antalet tas emot innan de bokförs i lagret.</span><span class="sxs-lookup"><span data-stu-id="730e5-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="730e5-219">Logga in på Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="730e5-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="730e5-220">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="730e5-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="730e5-221">På fliken **Översikt** tittar du på de rader som har följande värden:</span><span class="sxs-lookup"><span data-stu-id="730e5-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="730e5-222">**Arbetsordertyp:** *Rullande inventering*</span><span class="sxs-lookup"><span data-stu-id="730e5-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="730e5-223">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="730e5-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="730e5-224">**Arbetsstatus:** *Väntar på granskning*</span><span class="sxs-lookup"><span data-stu-id="730e5-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="730e5-225">Två arbets-ID ska ha skapats för dessa rader.</span><span class="sxs-lookup"><span data-stu-id="730e5-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="730e5-226">Antalet för båda dessa arbets-ID måste accepteras.</span><span class="sxs-lookup"><span data-stu-id="730e5-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="730e5-227">I rutnätet väljer du det första arbets-ID:t för arbetsordertypen *Rullande inventering*.</span><span class="sxs-lookup"><span data-stu-id="730e5-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="730e5-228">I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="730e5-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="730e5-229">Två rader visas, en för varje artikel och ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="730e5-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="730e5-230">Värdena i fälten **Räknad kvantitet**, **Plats**, **ID-nummer** och **Artikel** bör matcha de inventeringsposter som du skapade på den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="730e5-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="730e5-231">Om något av dessa fält inte visas väljer du **Visa dimensioner** i åtgärdsfönstret för att lägga till dem i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="730e5-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="730e5-232">Markera båda raderna.</span><span class="sxs-lookup"><span data-stu-id="730e5-232">Select both lines.</span></span>
1. <span data-ttu-id="730e5-233">Välj **Godkänn inventering** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="730e5-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="730e5-234">Meddelandet "bokföring – journal" visas.</span><span class="sxs-lookup"><span data-stu-id="730e5-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="730e5-235">Välj **meddelandeinformation** om du vill visa det bokförda journalnumret.</span><span class="sxs-lookup"><span data-stu-id="730e5-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="730e5-236">Stäng meddelandeinformationen.</span><span class="sxs-lookup"><span data-stu-id="730e5-236">Close the message details.</span></span>
1. <span data-ttu-id="730e5-237">Uppdatera sidan **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="730e5-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="730e5-238">Det första arbets-ID:t har stängts och visas inte längre.</span><span class="sxs-lookup"><span data-stu-id="730e5-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="730e5-239">Om du vill visa stängt arbete markerar du kryssrutan **Visa stängd** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="730e5-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="730e5-240">Du kommer nu att acceptera arbetet för ID-numret på plats *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="730e5-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="730e5-241">På fliken **Översikt** väljer du det andra arbets-ID:t för arbetsordertypen *Rullande inventering*.</span><span class="sxs-lookup"><span data-stu-id="730e5-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="730e5-242">I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="730e5-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="730e5-243">En rad visas för artikeln och ID-numret.</span><span class="sxs-lookup"><span data-stu-id="730e5-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="730e5-244">Värdena i fälten **Räknad kvantitet**, **Plats**, **ID-nummer** och **Artikel** bör matcha de inventeringsposter som du skapade på den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="730e5-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="730e5-245">Markera raden.</span><span class="sxs-lookup"><span data-stu-id="730e5-245">Select the line.</span></span>
1. <span data-ttu-id="730e5-246">Välj **Godkänn inventering** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="730e5-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="730e5-247">Meddelandet "bokföring – journal" visas.</span><span class="sxs-lookup"><span data-stu-id="730e5-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="730e5-248">Välj **meddelandeinformation** om du vill visa det bokförda journalnumret.</span><span class="sxs-lookup"><span data-stu-id="730e5-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="730e5-249">Stäng meddelandeinformationen.</span><span class="sxs-lookup"><span data-stu-id="730e5-249">Close the message details.</span></span>
1. <span data-ttu-id="730e5-250">Uppdatera sidan **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="730e5-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="730e5-251">Det andra arbets-ID:t har stängts och visas inte längre.</span><span class="sxs-lookup"><span data-stu-id="730e5-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="730e5-252">Om du vill visa stängt arbete markerar du kryssrutan **Visa stängd** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="730e5-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="730e5-253">Behållning efter plats</span><span class="sxs-lookup"><span data-stu-id="730e5-253">On-hand by location</span></span>

1. <span data-ttu-id="730e5-254">Gå till **Lagerstyrning \> Förfrågningar och rapporter \> Behållning efter plats**.</span><span class="sxs-lookup"><span data-stu-id="730e5-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="730e5-255">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="730e5-255">Set the following values:</span></span>

    - <span data-ttu-id="730e5-256">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="730e5-256">**Site:** *6*</span></span>
    - <span data-ttu-id="730e5-257">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="730e5-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="730e5-258">**Uppdatera mellan platser:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="730e5-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="730e5-259">Lägg märke till att platsen *01A01R1S1B* har två ID-nummer:</span><span class="sxs-lookup"><span data-stu-id="730e5-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="730e5-260">**A0001**, där fältet **LP-position** anges till *1*</span><span class="sxs-lookup"><span data-stu-id="730e5-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="730e5-261">**A0002**, där fältet **LP-position** anges till *2*</span><span class="sxs-lookup"><span data-stu-id="730e5-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="730e5-262">Lägg märke till att platsen *01A01R1S2B* har ett ID-nummer:</span><span class="sxs-lookup"><span data-stu-id="730e5-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="730e5-263">**A0002**, där fältet **LP-position** anges till *1*</span><span class="sxs-lookup"><span data-stu-id="730e5-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="730e5-264">Scenario för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="730e5-264">Sales order scenario</span></span>

<span data-ttu-id="730e5-265">Nu när funktionen *positionering av ID-nummer* har ställts in och lagret har mellanlagrats måste du skapa en försäljningsorder för att generera plockningsarbete som leder lagerarbetaren till att plocka artikeln *A0002* från lager platsen där lastpalls-ID finns i position *1*.</span><span class="sxs-lookup"><span data-stu-id="730e5-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="730e5-266">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="730e5-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="730e5-267">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="730e5-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="730e5-268">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="730e5-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="730e5-269">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="730e5-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="730e5-270">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="730e5-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="730e5-271">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="730e5-271">Select **OK**.</span></span>
1. <span data-ttu-id="730e5-272">En ny rad läggs till i rutnätet på snabbfliken **försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="730e5-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="730e5-273">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="730e5-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="730e5-274">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="730e5-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="730e5-275">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="730e5-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="730e5-276">I menyn **Lager** ovanför rutnätet, välj **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="730e5-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="730e5-277">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager för orderraden.</span><span class="sxs-lookup"><span data-stu-id="730e5-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="730e5-278">Stäng sidan **Reservation**.</span><span class="sxs-lookup"><span data-stu-id="730e5-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="730e5-279">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="730e5-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="730e5-280">Du får ett informationsmeddelande som visar det påfyllnads-ID och leverans-ID som skapades för ordern.</span><span class="sxs-lookup"><span data-stu-id="730e5-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="730e5-281">På snabbfliken **Försäljningsorderrader** på menyn **Lagerställe** ovanför rutnätet, välj **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="730e5-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="730e5-282">Sidan **arbete** visas och visar det arbete som har skapats för försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="730e5-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="730e5-283">Anteckna de arbets-ID som har visats.</span><span class="sxs-lookup"><span data-stu-id="730e5-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="730e5-284">Scenario för försäljningsplockning</span><span class="sxs-lookup"><span data-stu-id="730e5-284">Sales picking scenario</span></span>

1. <span data-ttu-id="730e5-285">Öppna mobilappen och logga in på lagerställe *61*.</span><span class="sxs-lookup"><span data-stu-id="730e5-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="730e5-286">Gå till **Utgående \> Försäljningsplockning**.</span><span class="sxs-lookup"><span data-stu-id="730e5-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="730e5-287">På sidan **Skanna ett arbets-ID/ID-nummer** välj fältet **ID** och anger sedan arbets-ID:t från försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="730e5-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="730e5-288">Observera att plockningsarbetet styr att du kan välja artikel *A0002* från plats *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="730e5-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="730e5-289">Den här instruktionen visas eftersom objektet *A0002* finns på ett ID-nummer som finns på position *1* på den platsen.</span><span class="sxs-lookup"><span data-stu-id="730e5-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="730e5-290">![Position 1 plats](media/LocationLicensePlatePositioning.png "Position 1 plats")</span><span class="sxs-lookup"><span data-stu-id="730e5-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="730e5-291">Ange det ID-nummer som du skapade för platsen och följ sedan instruktionerna för att plocka försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="730e5-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]