---
title: Arbetsdelning
description: Det här avsnittet innehåller information om funktionen arbetsdelning. Med den här funktionen kan du dela upp stora arbetsorder i flera mindre arbetsorder som du sedan kan tilldela till flera lagerarbetare. På så sätt kan samma arbete plockas samtidigt av flera lagerarbetare.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e74b630e72d70829938f0f34efd624509b1ba7c3
ms.sourcegitcommit: 531be324bf706ca727d777720df899d6ddd3c2d7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "4438142"
---
# <a name="work-split"></a><span data-ttu-id="d4001-105">Arbetsdelning</span><span class="sxs-lookup"><span data-stu-id="d4001-105">Work split</span></span>

<span data-ttu-id="d4001-106">Med funktion för arbetsdelning kan du dela stora arbets-ID (det vill säga arbetsorder som har flera rader) i flera mindre arbets-ID som du sedan kan tilldela till flera lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="d4001-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="d4001-107">På så sätt kan samma nummer för arbetsskapande plockas samtidigt av flera lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="d4001-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4001-108">Du kan bara dela arbetsorder som har statusen *öppen* eller *pågående*.</span><span class="sxs-lookup"><span data-stu-id="d4001-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="d4001-109">Aktivera funktionen dela arbete</span><span class="sxs-lookup"><span data-stu-id="d4001-109">Turn on the work split functionality</span></span>

<span data-ttu-id="d4001-110">Innan du kan använda funktionen för delning av resurser måste du aktivera funktionen och dess nödvändiga funktion i systemet.</span><span class="sxs-lookup"><span data-stu-id="d4001-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="d4001-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="d4001-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="d4001-112">Börja med att aktivera funktionen *Arbetsspärr för hela organisationen* om den inte redan är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="d4001-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="d4001-113">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d4001-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="d4001-114">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="d4001-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d4001-115">**Funktionsnamn:** *Arbetsspärr för hela organisationen*</span><span class="sxs-lookup"><span data-stu-id="d4001-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="d4001-116">När den här funktionen aktiveras används en datauppgradering automatiskt när funktionen har aktiverats för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="d4001-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="d4001-117">Aktivera sedan funktionen *Arbetsdelning*, som visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d4001-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="d4001-118">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="d4001-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d4001-119">**Funktionens namn:** *Arbetsdelning*</span><span class="sxs-lookup"><span data-stu-id="d4001-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="d4001-120">Förbättringar av arbetsuppgifter och alla arbetssidor</span><span class="sxs-lookup"><span data-stu-id="d4001-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="d4001-121">Funktionen *Arbetsdelning* lägger till följande två knappar på **Arbete** i åtgärdsfönstret för sidan **Arbetsuppgifterna** och **Allt arbete**:</span><span class="sxs-lookup"><span data-stu-id="d4001-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="d4001-122">**Dela arbetsuppgift** – Dela aktuellt arbets-ID i flera mindre arbete-ID som kan bearbetas av olika personer.</span><span class="sxs-lookup"><span data-stu-id="d4001-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="d4001-123">**Avbryt arbetsdelningssession** – Avbryt arbetssessionen för arbetet och gör arbetet tillgängligt för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="d4001-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="d4001-124">![Knappar för dela upp arbete och avbryt arbetsdelningssessioner](media/Work_split_buttons.png "Knappar för dela upp arbete och avbryt arbetsdelningssessioner")</span><span class="sxs-lookup"><span data-stu-id="d4001-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4001-125">Knappen **Dela arbete** är inte tillgänglig om något av följande villkor är uppfyllt:</span><span class="sxs-lookup"><span data-stu-id="d4001-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="d4001-126">Arbetsstatus är något annat än *öppen* eller *pågår*.</span><span class="sxs-lookup"><span data-stu-id="d4001-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="d4001-127">Ett behållar-ID associeras med arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="d4001-128">(En behållare kan inte delas upp på ett systematiskt sätt, eftersom den kräver fysiska åtgärder.)</span><span class="sxs-lookup"><span data-stu-id="d4001-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="d4001-129">Arbetet associeras med ett kluster.</span><span class="sxs-lookup"><span data-stu-id="d4001-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="d4001-130">Arbetsordertypen är något annat än någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="d4001-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="d4001-131">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="d4001-131">Sales orders</span></span>
>    - <span data-ttu-id="d4001-132">Råmaterialhämtning</span><span class="sxs-lookup"><span data-stu-id="d4001-132">Raw material picking</span></span>
>    - <span data-ttu-id="d4001-133">Överför leverans</span><span class="sxs-lookup"><span data-stu-id="d4001-133">Transfer issue</span></span>
>
> - <span data-ttu-id="d4001-134">Arbetet håller på att delas av en annan användare.</span><span class="sxs-lookup"><span data-stu-id="d4001-134">The work is currently being split by another user.</span></span> <span data-ttu-id="d4001-135">Om du försöker öppna delningssidan för arbete som redan delas av en annan användare visas följande felmeddelande: "arbetet med ID \#\#\#\# håller på att delas.</span><span class="sxs-lookup"><span data-stu-id="d4001-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="d4001-136">Försök igen om några minuter.</span><span class="sxs-lookup"><span data-stu-id="d4001-136">Retry in a few minutes.</span></span> <span data-ttu-id="d4001-137">Kontakta en arbetsledare om du fortsätter att få det här meddelandet".</span><span class="sxs-lookup"><span data-stu-id="d4001-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="d4001-138">Ett nytt arbetsblockerande skäl *Dela arbete* anger när arbets-ID håller på att delas.</span><span class="sxs-lookup"><span data-stu-id="d4001-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="d4001-139">Den visas både på sidan **Dela arbete** och i distributionslagerappen om en användare försöker köra arbetet.</span><span class="sxs-lookup"><span data-stu-id="d4001-139">It's shown both on the **Split work** page and in the warehouse app if a user tries to run the work.</span></span> <span data-ttu-id="d4001-140">När spärrningsorsaker används ändras namnet på fältet **spärrad påfyllnad** från arbets-ID till **spärrat**.</span><span class="sxs-lookup"><span data-stu-id="d4001-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="d4001-141">Starta en arbetsdelning</span><span class="sxs-lookup"><span data-stu-id="d4001-141">Initiate a work split</span></span>

<span data-ttu-id="d4001-142">Funktionen lägger till en ny sida **delad arbete** där användarna kan dela upp arbetsrader från arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="d4001-143">När sidan öppnas visas rader med arbetsstatus *öppen* och som är tillgängliga för delning.</span><span class="sxs-lookup"><span data-stu-id="d4001-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="d4001-144">I åtgärdsfönstret, välj **Dela arbete** för att bearbeta det valda arbetet.</span><span class="sxs-lookup"><span data-stu-id="d4001-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="d4001-145">Om du vill dela arbete följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d4001-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="d4001-146">Öppna en av följande arbetssidor:</span><span class="sxs-lookup"><span data-stu-id="d4001-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="d4001-147">**Arbetsdetaljer** (**Lagerstyrning \> Arbete \> Arbetsdetaljer**)</span><span class="sxs-lookup"><span data-stu-id="d4001-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="d4001-148">**Allt arbete** (**Lagerstyrning \> Arbete \> Allt arbete**)</span><span class="sxs-lookup"><span data-stu-id="d4001-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="d4001-149">Välj ett arbets-ID som du vill dela i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="d4001-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="d4001-150">Fältet **arbetsordertyp** måste ha ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="d4001-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="d4001-151">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="d4001-151">Sales orders</span></span>
    - <span data-ttu-id="d4001-152">Råmaterialhämtning</span><span class="sxs-lookup"><span data-stu-id="d4001-152">Raw material picking</span></span>
    - <span data-ttu-id="d4001-153">Överför leverans</span><span class="sxs-lookup"><span data-stu-id="d4001-153">Transfer issue</span></span>

1. <span data-ttu-id="d4001-154">I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Dela arbete**.</span><span class="sxs-lookup"><span data-stu-id="d4001-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="d4001-155">Sidan **Dela arbete** visas och visar de arbetsrader som är öppna och som är tillgängliga för delning.</span><span class="sxs-lookup"><span data-stu-id="d4001-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="d4001-156">Som standard visas endast tillgängliga arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="d4001-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="d4001-157">Om du vill visa alla rader för arbets-ID (till exempel rader med arbetstyp *Placera*), välj **Visa alla rader** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="d4001-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="d4001-158">Följande meddelande visas: "användarna kan inte bearbeta rader i arbetet förrän du har slutfört delningen och stängt sidan".</span><span class="sxs-lookup"><span data-stu-id="d4001-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="d4001-159">Fältet **Arbetsblockerande skäl** för aktuellt arbete kommer att anges till *Delat arbete* och arbetet blockeras. </span><span class="sxs-lookup"><span data-stu-id="d4001-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="d4001-160">![Spärrningsorsak](media/Blocking_reason.png "Spärrningsorsak")</span><span class="sxs-lookup"><span data-stu-id="d4001-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="d4001-161">Markera de rader som du vill ta bort från aktuellt arbets-ID och lägg till i ett nytt arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="d4001-162">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="d4001-162">The following events occur:</span></span>

    - <span data-ttu-id="d4001-163">När du delar upp arbetet annulleras den markerade raden eller raderna från det ursprungliga arbets-ID och kopieras sedan till ett nytt arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="d4001-164">Den befintliga arbetsmallstrukturen och placeringens plats (och även framtida plocknings-/placeringspar) bevaras.</span><span class="sxs-lookup"><span data-stu-id="d4001-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="d4001-165">Värden för följande arbets-ID-fält kopieras från original arbetet till det nya arbetet:</span><span class="sxs-lookup"><span data-stu-id="d4001-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="d4001-166">Last-ID</span><span class="sxs-lookup"><span data-stu-id="d4001-166">Load ID</span></span>
        - <span data-ttu-id="d4001-167">Leverans-ID</span><span class="sxs-lookup"><span data-stu-id="d4001-167">Shipment ID</span></span>
        - <span data-ttu-id="d4001-168">Typ av arbetsorder</span><span class="sxs-lookup"><span data-stu-id="d4001-168">Work order type</span></span>
        - <span data-ttu-id="d4001-169">Ordernummer</span><span class="sxs-lookup"><span data-stu-id="d4001-169">Order number</span></span>
        - <span data-ttu-id="d4001-170">Site</span><span class="sxs-lookup"><span data-stu-id="d4001-170">Site</span></span>
        - <span data-ttu-id="d4001-171">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="d4001-171">Warehouse</span></span>
        - <span data-ttu-id="d4001-172">Arbetsprioritet</span><span class="sxs-lookup"><span data-stu-id="d4001-172">Work priority</span></span>
        - <span data-ttu-id="d4001-173">ID för arbetspool</span><span class="sxs-lookup"><span data-stu-id="d4001-173">Work pool ID</span></span>
        - <span data-ttu-id="d4001-174">Påfyllnads-ID</span><span class="sxs-lookup"><span data-stu-id="d4001-174">Wave ID</span></span>
        - <span data-ttu-id="d4001-175">Nummer för att skapa arbete</span><span class="sxs-lookup"><span data-stu-id="d4001-175">Work creation number</span></span>

    - <span data-ttu-id="d4001-176">Följande fält kopieras inte till det nya arbets-ID:</span><span class="sxs-lookup"><span data-stu-id="d4001-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="d4001-177">**Arbets-ID** – ett nytt arbets-ID skapas från en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="d4001-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="d4001-178">**Arbetsstatus** – detta fält är inställt på *öppen*.</span><span class="sxs-lookup"><span data-stu-id="d4001-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="d4001-179">**Låst av** – det här fältet ställs från början till tom.</span><span class="sxs-lookup"><span data-stu-id="d4001-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="d4001-180">**Mål ID-nummer** – detta fält lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="d4001-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="d4001-181">**Skapat datum och tid** – fältet ställs in på aktuellt datum och aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="d4001-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="d4001-182">**Spärrad påfyllnad/fryst** – det här fältet har omberäknats för det ursprungliga arbets-ID och det nya arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="d4001-183">Klicka på **Dela arbete** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d4001-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="d4001-184">När arbetet delas upp visas följande meddelande: "bearbetningsåtgärd - dela arbete".</span><span class="sxs-lookup"><span data-stu-id="d4001-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="d4001-185">Även om det här meddelandet visas kan du avbryta åtgärden genom att välja **Avbryt** i meddelanderutan.</span><span class="sxs-lookup"><span data-stu-id="d4001-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="d4001-186">Om kryssrutan **Visa alla rader** är avmarkerad visas inte längre den rad som delades och annullerades i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="d4001-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="d4001-187">Om kryssrutan är markerad bör du se att värdet i fältet **Arbetsstatus** för den raden har ändrats till *Annullerat*.</span><span class="sxs-lookup"><span data-stu-id="d4001-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="d4001-188">Följande meddelande visar att det nya arbets-ID har skapats: "arbete \#\#\#\# har skapats genom att dela från ursprungligt arbete \#\#\#\# ."</span><span class="sxs-lookup"><span data-stu-id="d4001-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="d4001-189">Andra arbetsrader från det ursprungliga arbets-ID (t.ex. *placera* rader) justeras efter behov för att återspegla de arbetsrader som har annullerats.</span><span class="sxs-lookup"><span data-stu-id="d4001-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="d4001-190">Om det ursprungliga arbets-ID t.ex. har raden *placera* för kvantiteten 15 och rader *plocka* med en total kvantitet på 10 har annullerats, kommer den nya kvantiteten *placera* i det ursprungliga arbets-ID att vara 5.</span><span class="sxs-lookup"><span data-stu-id="d4001-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="d4001-191">Det nya arbetet tilldelas inte omedelbart till någon användare.</span><span class="sxs-lookup"><span data-stu-id="d4001-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="d4001-192">Du kan dock tilldela den till en användare vid behov genom att använda standardfunktionerna på sidan **arbetsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="d4001-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4001-193">Du kan bara dela arbets-ID som innehåller två eller flera tillgängliga arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="d4001-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="d4001-194">Om du väljer **dela arbete** när det bara finns en arbetsrad visas följande felmeddelande: "minst en arbetsrader måste finnas kvar på det ursprungliga arbetet".</span><span class="sxs-lookup"><span data-stu-id="d4001-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="d4001-195">I det här fallet görs ingen delning.</span><span class="sxs-lookup"><span data-stu-id="d4001-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="d4001-196">Avsluta en arbetsdelning</span><span class="sxs-lookup"><span data-stu-id="d4001-196">Finish a work split</span></span>

<span data-ttu-id="d4001-197">För att slutföra delningsarbetet måste spärrningsorsak *Dela arbete* tas bort.</span><span class="sxs-lookup"><span data-stu-id="d4001-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="d4001-198">Det finns två sätt att slutföra detta steg:</span><span class="sxs-lookup"><span data-stu-id="d4001-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="d4001-199">Användaren som delar upp arbetet stänger sidan **Dela arbete** genom att välja knappen **Stäng** (**X**) i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d4001-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="d4001-200">När sidan stängs tas blockeringsorsaken till det *delade arbetet* bort.</span><span class="sxs-lookup"><span data-stu-id="d4001-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="d4001-201">Det *spärrade* tillståndet för det här arbetet kommer att omberäknas och, om det inte finns några återstående spärrningsorsaker för det här arbetet, kommer arbetet att avblockeras.</span><span class="sxs-lookup"><span data-stu-id="d4001-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="d4001-202">Alla användare öppnar arbets-ID och väljer knappen **Avbryt arbetssession** för arbete i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d4001-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="d4001-203">Spärrningsorsak *Delat arbete* kommer att tas bort och *Blockerat* tillstånd för det här arbetet kommer att omberäknas, precis som **Delat arbete** är stängd.</span><span class="sxs-lookup"><span data-stu-id="d4001-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="d4001-204">När blockeringsorsaken *Delat arbete* tas bort kan arbetet köras på den mobila enheten, förutsatt att **Blockerat** tillstånd är inställt på *Nej* på arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="d4001-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-app"></a><span data-ttu-id="d4001-205">Användarspärr i distributionslagerappen</span><span class="sxs-lookup"><span data-stu-id="d4001-205">User blocking on the warehouse app</span></span>

<span data-ttu-id="d4001-206">Om du försöker använda distributionslagerappen för att köra plockningsarbete mot ett arbets-ID som redan delas av en annan användare visas följande felmeddelande: "arbetet med ID \#\#\#\# håller på att delas.</span><span class="sxs-lookup"><span data-stu-id="d4001-206">If you try to use the warehouse app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="d4001-207">Om du får detta meddelande väljer du **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="d4001-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="d4001-208">Därefter kan du fortsätta att bearbeta annat arbete.</span><span class="sxs-lookup"><span data-stu-id="d4001-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="d4001-209">Andra blockerade operationer</span><span class="sxs-lookup"><span data-stu-id="d4001-209">Other blocked operations</span></span>

<span data-ttu-id="d4001-210">Alla operationer som ändrar arbetsrader, arbetslagertransaktioner eller lagerpåfyllnadslänkar som är relaterade till arbete som delas kommer att misslyckas, och följande felmeddelande visas: "arbetet med ID håller \#\#\#\# just nu på att delas."</span><span class="sxs-lookup"><span data-stu-id="d4001-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>
