---
title: Plockradsgruppering
description: Det här ämnet ger en översikt över plockradsgruppering.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 4b9cd7dac680c1691fb4c6dd4078f109254be784
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215611"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="30eea-103">Plockradsgruppering</span><span class="sxs-lookup"><span data-stu-id="30eea-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30eea-104">I plockradgruppering kan flera arbetsrader som har samma artikel och plats kombineras till en enda plockning som visas för användaren på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="30eea-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="30eea-105">Lagerarbetare kan därför få de mest effektiva instruktioner som är möjliga, men den nödvändiga uppdelningen av arbetsrader i systemet upprätthålls också (till exempel för olika behållare och order).</span><span class="sxs-lookup"><span data-stu-id="30eea-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="30eea-106">Ställ in plockradsgruppering</span><span class="sxs-lookup"><span data-stu-id="30eea-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="30eea-107">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="30eea-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="30eea-108">Gå till **Lagerstyrning \> Konfigurera \> Mobil enhet \> Menyalternativ på mobil enhet** och skapa ett nytt menyalternativ som heter **Plockning av försäljningsgrupprad - Användarriktad**.</span><span class="sxs-lookup"><span data-stu-id="30eea-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="30eea-109">Under **Menyalternativ på mobil enhet**, ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="30eea-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="30eea-110">I fältet **Menyartikelnamn** ange **Försäljningsplockning - Grupprad**.</span><span class="sxs-lookup"><span data-stu-id="30eea-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="30eea-111">I fältet **Rubrik** ange **Försäljningsplockning - Grupprad**.</span><span class="sxs-lookup"><span data-stu-id="30eea-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="30eea-112">Välj **Arbete** i fältet **Läge**.</span><span class="sxs-lookup"><span data-stu-id="30eea-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="30eea-113">Ange alternativet **Använd befintligt arbete** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="30eea-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="30eea-114">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="30eea-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="30eea-115">I fältet **Dirigerad av** välj **Användarstyrd**.</span><span class="sxs-lookup"><span data-stu-id="30eea-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="30eea-116">Ange det här alternativet **Generera registreringsskylt** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="30eea-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="30eea-117">Ge alternativet **Grupplockning** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="30eea-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="30eea-118">På snabbfliken **arbetsklasser** följer du dessa steg för att konfigurera de giltiga arbetsklasserna för mobila enhetens menyalternativ:</span><span class="sxs-lookup"><span data-stu-id="30eea-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="30eea-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="30eea-119">Select **New**.</span></span>
    2. <span data-ttu-id="30eea-120">I fältet **Arbetsklass-ID** välj **Försäljning** eller **SO plocka**, beroende på vilket lagerställe du ska använda.</span><span class="sxs-lookup"><span data-stu-id="30eea-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="30eea-121">Välj **Inköpsorder** i fältet **Försäljningsarbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="30eea-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="30eea-122">Ställ in mobil enhet för lagerställe</span><span class="sxs-lookup"><span data-stu-id="30eea-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="30eea-123">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="30eea-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="30eea-124">Lägg till menyalternativet som du nyss skapade i önskad meny.</span><span class="sxs-lookup"><span data-stu-id="30eea-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="30eea-125">Ställ in en arbetsmall</span><span class="sxs-lookup"><span data-stu-id="30eea-125">Set up a work template</span></span>

1. <span data-ttu-id="30eea-126">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="30eea-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="30eea-127">Leta reda på arbetsmallen som ska användas med den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="30eea-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="30eea-128">I det här exemplet väljer du standard **51 välj till fas** Contoso arbetsmallen.</span><span class="sxs-lookup"><span data-stu-id="30eea-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="30eea-129">Välj på menyn **redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="30eea-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="30eea-130">Välj **Sortering** välj **Lägg till** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="30eea-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="30eea-131">I fältet **Tabell** väljer du **Tillfälliga arbetsstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="30eea-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="30eea-132">I fältet **Härlett register** väljer du **Tillfälliga arbetsstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="30eea-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="30eea-133">I fältet **Fält**, välj **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="30eea-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="30eea-134">I fält **Sökriktning** välj **Stigande**.</span><span class="sxs-lookup"><span data-stu-id="30eea-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="30eea-135">För att funktionen plockradsgruppering ska fungera måste arbetsraderna sorteras efter artikel-ID.</span><span class="sxs-lookup"><span data-stu-id="30eea-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="30eea-136">Om rader som har samma objekt inte sekvenseras en efter en grupperas de inte.</span><span class="sxs-lookup"><span data-stu-id="30eea-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="30eea-137">Exempel</span><span class="sxs-lookup"><span data-stu-id="30eea-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="30eea-138">Skapa plockarbete</span><span class="sxs-lookup"><span data-stu-id="30eea-138">Create picking work</span></span>

<span data-ttu-id="30eea-139">Innan du kan ställa in plockradsgruppering måste du skapa vissa kvalificerade utgående arbete.</span><span class="sxs-lookup"><span data-stu-id="30eea-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="30eea-140">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="30eea-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="30eea-141">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="30eea-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="30eea-142">Markera en kund i fältet **Kundkonto**.</span><span class="sxs-lookup"><span data-stu-id="30eea-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="30eea-143">På snabbfliken **Allmänt** i fältet **Lagerställe**, välj **51**.</span><span class="sxs-lookup"><span data-stu-id="30eea-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="30eea-144">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="30eea-144">Then select **OK**.</span></span>
5. <span data-ttu-id="30eea-145">Under **Försäljningsorderrader**, lägg till följande sex rader:</span><span class="sxs-lookup"><span data-stu-id="30eea-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="30eea-146">**Rad 1:** I fältet **Artikelnummer** välj **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30eea-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30eea-147">I fältet **Kvantitet**, ange **3**.</span><span class="sxs-lookup"><span data-stu-id="30eea-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="30eea-148">**Rad 2:** I fältet **Artikelnummer** välj **M9201**.</span><span class="sxs-lookup"><span data-stu-id="30eea-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="30eea-149">I fältet **Kvantitet**, ange **3**.</span><span class="sxs-lookup"><span data-stu-id="30eea-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="30eea-150">**Rad 3:** I fältet **Artikelnummer** välj **M9202**.</span><span class="sxs-lookup"><span data-stu-id="30eea-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="30eea-151">I fältet **Kvantitet**, ange **2**.</span><span class="sxs-lookup"><span data-stu-id="30eea-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="30eea-152">**Rad 4:** I fältet **Artikelnummer** välj **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30eea-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30eea-153">I fältet **Kvantitet**, ange **1**.</span><span class="sxs-lookup"><span data-stu-id="30eea-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="30eea-154">**Rad 5:** I fältet **Artikelnummer** välj **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30eea-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30eea-155">I fältet **Kvantitet**, ange **3**.</span><span class="sxs-lookup"><span data-stu-id="30eea-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="30eea-156">**Rad 6:** I fältet **Artikelnummer** välj **M9202**.</span><span class="sxs-lookup"><span data-stu-id="30eea-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="30eea-157">I fältet **Kvantitet**, ange **7**.</span><span class="sxs-lookup"><span data-stu-id="30eea-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="30eea-158">Här är en sammanfattning av de totala kvantiteterna för varje artikel:</span><span class="sxs-lookup"><span data-stu-id="30eea-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="30eea-159">**Artikel M9200:** 7 var</span><span class="sxs-lookup"><span data-stu-id="30eea-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="30eea-160">**Artikel M9201:** 3 var</span><span class="sxs-lookup"><span data-stu-id="30eea-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="30eea-161">**Artikel M9202:** 9 var</span><span class="sxs-lookup"><span data-stu-id="30eea-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="30eea-162">Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på alla order.</span><span class="sxs-lookup"><span data-stu-id="30eea-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="30eea-163">Granska inställningen **platsdirektiv** för att avgöra vilka plockplatser som används för plockning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="30eea-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="30eea-164">Reservera lagret och släpp det till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="30eea-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="30eea-165">Ett arbets-ID som har sex rader skapas.</span><span class="sxs-lookup"><span data-stu-id="30eea-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="30eea-166">Raderna sorteras efter artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="30eea-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="30eea-167">Kör det mobila enhetsflödet</span><span class="sxs-lookup"><span data-stu-id="30eea-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="30eea-168">På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="30eea-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="30eea-169">Välj menyalternativet **försäljningsplockning – grupprad** och initiera plockningen.</span><span class="sxs-lookup"><span data-stu-id="30eea-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="30eea-170">När du har valt menyn och ange arbets-ID, visas plockningssteget där alla plockningsrader för artikel M9200 grupperas.</span><span class="sxs-lookup"><span data-stu-id="30eea-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="30eea-171">Du får en instruktion att välja 7 var och en av artikel M9200.</span><span class="sxs-lookup"><span data-stu-id="30eea-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="30eea-172">Bekräfta plockningssteget.</span><span class="sxs-lookup"><span data-stu-id="30eea-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="30eea-173">Gå till klientskärmen för det arbete som pågår och lägg märke till att alla tre plockningsrader för artikel M9200 stängdes samtidigt.</span><span class="sxs-lookup"><span data-stu-id="30eea-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="30eea-174">Arbetsrad 4 presenteras.</span><span class="sxs-lookup"><span data-stu-id="30eea-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="30eea-175">Bekräfta plockningssteget.</span><span class="sxs-lookup"><span data-stu-id="30eea-175">Confirm the pick step.</span></span>

    <span data-ttu-id="30eea-176">Det sista plockningssteget på den mobila enheten sammanställer de två sista plockningsraderna från arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="30eea-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="30eea-177">Slutför plockningssteget för 9 var och en av artikel M9202.</span><span class="sxs-lookup"><span data-stu-id="30eea-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="30eea-178">Bekräfta inlagringssteget och eventuella ytterligare utskriftssteget efter inlagringssteget för att slutföra arbetet.</span><span class="sxs-lookup"><span data-stu-id="30eea-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="30eea-179">Arbetsrader kan bara grupperas om de är i sekvens.</span><span class="sxs-lookup"><span data-stu-id="30eea-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="30eea-180">Följande funktioner stöds inte:</span><span class="sxs-lookup"><span data-stu-id="30eea-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="30eea-181">Fångstviktartiklar.</span><span class="sxs-lookup"><span data-stu-id="30eea-181">Catch-weight items.</span></span> <span data-ttu-id="30eea-182">Om det finns några fångstviktartiklar i arbetet, visas ett felmeddelande innan du börjar plocka.</span><span class="sxs-lookup"><span data-stu-id="30eea-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="30eea-183">Enhetsplockning.</span><span class="sxs-lookup"><span data-stu-id="30eea-183">Piece picking.</span></span>
>    - <span data-ttu-id="30eea-184">Arbetsrader som har oavslutade lagerpåfyllnadsarbete.</span><span class="sxs-lookup"><span data-stu-id="30eea-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="30eea-185">Överplockning.</span><span class="sxs-lookup"><span data-stu-id="30eea-185">Over-picking.</span></span>
