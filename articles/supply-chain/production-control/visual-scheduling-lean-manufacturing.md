---
title: "Visuell tidsplanering för lean manufacturing"
description: "Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6218f54364e096bdd718ea35edb0b3666e65f2c1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="visual-scheduling-for-lean-manufacturing"></a><span data-ttu-id="9f718-103">Visuell tidsplanering för lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="9f718-103">Visual scheduling for lean manufacturing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9f718-104">Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-104">This topic provides information about the Kanban schedule board, which the production planner can use to control and optimize the production plan for kanban jobs.</span></span>

<span data-ttu-id="9f718-105">Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-105">This topic provides information about the Kanban schedule board, which the production planner can use to control and optimize the production plan for kanban jobs.</span></span>

<span data-ttu-id="9f718-106">Kanban-schematavlan tillåter produktionsplaneraren att styra och optimera produktionsplanen för kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-106">The Kanban schedule board lets the production planner control and optimize the production plan for kanban jobs.</span></span> <span data-ttu-id="9f718-107">Det gör flödet för kanban-jobb transparent och ger produktionsplaneraren ett verktyg som optimerar och justerar produktionsplanen för arbetsgruppen för lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="9f718-107">It makes the flow of kanban jobs transparent, and gives the production planner a tool that optimizes and adjusts the production plan for the lean manufacturing work cell.</span></span>

## <a name="visual-scheduling-of-kanban-jobs"></a><span data-ttu-id="9f718-108">Visuell tidplanering av kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="9f718-108">Visual scheduling of kanban jobs</span></span>
<span data-ttu-id="9f718-109">Ett kanban-jobb kan bestå av en eller flera kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-109">A kanban job can consist of one or many kanban jobs.</span></span> <span data-ttu-id="9f718-110">Det finns två typer av kanban-jobb:</span><span class="sxs-lookup"><span data-stu-id="9f718-110">There are two types of kanban jobs:</span></span>

-   <span data-ttu-id="9f718-111">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="9f718-111">Process</span></span>
-   <span data-ttu-id="9f718-112">Överför</span><span class="sxs-lookup"><span data-stu-id="9f718-112">Transfer</span></span>

<span data-ttu-id="9f718-113">Du kan bara tidsplanera jobb av typen **Process**.</span><span class="sxs-lookup"><span data-stu-id="9f718-113">You can schedule only jobs of the **Process** type.</span></span> <span data-ttu-id="9f718-114">Kanban-jobbet och dess egenskaper, till exempel aktivitetstid, har definierats i produktionsflödet kanban.</span><span class="sxs-lookup"><span data-stu-id="9f718-114">The kanban job and its properties, such as the activity time, are defined in the production kanban flow.</span></span> <span data-ttu-id="9f718-115">Vid produktionen av kanban-flödet tilldelas även en arbetsgrupp till kanban-jobbet.</span><span class="sxs-lookup"><span data-stu-id="9f718-115">In the production kanban flow, the kanban job is also assigned to a work cell.</span></span> <span data-ttu-id="9f718-116">Arbetsgruppens dagliga kapacitet beräknas utifrån arbetsgruppens kapacitet som har angetts för resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="9f718-116">The work cell's daily capacity is calculated based on the work cell capacity that is set on the resource group.</span></span> <span data-ttu-id="9f718-117">Den har justerats efter den dagliga arbetstid i den relaterade kalendern.</span><span class="sxs-lookup"><span data-stu-id="9f718-117">It's adjusted by the daily working time in the related calendar.</span></span> <span data-ttu-id="9f718-118">När ett kanban-jobb tidsplaneras laddar jobbet kapaciteten för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9f718-118">When a kanban job is scheduled, the job loads the capacity of the work cell.</span></span> <span data-ttu-id="9f718-119">Kanban-schematavlan ger följande huvudfunktioner:</span><span class="sxs-lookup"><span data-stu-id="9f718-119">The Kanban schedule board provides the following main features:</span></span>

-   <span data-ttu-id="9f718-120">En grafisk översikt över produktionsplanen i en resurssnål arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="9f718-120">A graphical overview of the production plan in a lean work cell.</span></span> <span data-ttu-id="9f718-121">Den här översikten visar planerade kanban-processjobb i angivna perioder.</span><span class="sxs-lookup"><span data-stu-id="9f718-121">This overview shows the planned kanban process jobs in the defined periods.</span></span>
-   <span data-ttu-id="9f718-122">Ett verktyg som gör att du kan tidsplanera oplanerade kanban-jobb och tidsplanera om tidigare schemalagda jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-122">A tool that lets you schedule unplanned kanban jobs and reschedule previously scheduled jobs.</span></span>

## <a name="kanban-schedule-board"></a><span data-ttu-id="9f718-123">Kanban-schematavla</span><span class="sxs-lookup"><span data-stu-id="9f718-123">Kanban schedule board</span></span>
<span data-ttu-id="9f718-124">Sidan **Kanban-schematavla** innehåller sju huvudelement som visas på bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="9f718-124">The **Kanban schedule board** page contains seven main elements, as shown in the following illustration.</span></span> 

![Kanban-schematavla](./media/kanban-schedule-board-1024x554.png)
1.  <span data-ttu-id="9f718-126">Åtgärdsfönster</span><span class="sxs-lookup"><span data-stu-id="9f718-126">Action Pane</span></span>
2.  <span data-ttu-id="9f718-127">Filtrera fält</span><span class="sxs-lookup"><span data-stu-id="9f718-127">Filter fields</span></span>
3.  <span data-ttu-id="9f718-128">Knapp för oförutsedda jobb</span><span class="sxs-lookup"><span data-stu-id="9f718-128">Button for unplanned jobs</span></span>
4.  <span data-ttu-id="9f718-129">Periodnod</span><span class="sxs-lookup"><span data-stu-id="9f718-129">Period node</span></span>
5.  <span data-ttu-id="9f718-130">Kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="9f718-130">Kanban job</span></span>
6.  <span data-ttu-id="9f718-131">Kapacitetsstapel</span><span class="sxs-lookup"><span data-stu-id="9f718-131">Capacity bar</span></span>
7.  <span data-ttu-id="9f718-132">Tidsskala</span><span class="sxs-lookup"><span data-stu-id="9f718-132">Time scale</span></span>

### <a name="view-the-time-scale"></a><span data-ttu-id="9f718-133">Visa tidsskalan</span><span class="sxs-lookup"><span data-stu-id="9f718-133">View the time scale</span></span>

<span data-ttu-id="9f718-134">Tavlan är indelad i perioder som var och en representeras av en nod (4).</span><span class="sxs-lookup"><span data-stu-id="9f718-134">The board is divided into periods, each of which is represented as a node (4).</span></span> <span data-ttu-id="9f718-135">Periodens noder visas på den lodräta axeln och den vågräta åtkomsten representerar en tidsskala (7) som visar periodens längd.</span><span class="sxs-lookup"><span data-stu-id="9f718-135">The period nodes are listed on the vertical axis, and the horizontal access represents a time scale (7) that shows the length of the period.</span></span> <span data-ttu-id="9f718-136">En period är antingen en dag eller en vecka.</span><span class="sxs-lookup"><span data-stu-id="9f718-136">A period has a length of either one day or one week.</span></span> <span data-ttu-id="9f718-137">Periodens längd fastställs av konfigurationen av den arbetsgrupp som valts för kanban-schematavlan (2).</span><span class="sxs-lookup"><span data-stu-id="9f718-137">The period length is determined by the configuration of the work cell that is selected for the Kanban schedule board (2).</span></span> <span data-ttu-id="9f718-138">Kanban-schematavlan anger hur många planerade kanban-jobb som läser in under perioden för varje periodnod.</span><span class="sxs-lookup"><span data-stu-id="9f718-138">For each period node, the Kanban schedule board indicates how much the scheduled kanban jobs are loading the period.</span></span> <span data-ttu-id="9f718-139">Det finns även en indikation på maximalt flöde under perioden.</span><span class="sxs-lookup"><span data-stu-id="9f718-139">There is also an indication of the maximum throughput for the period.</span></span> <span data-ttu-id="9f718-140">Om det planerade flödet överskrider det maximala flödet, anses perioden vara överbelastad och en röd varningssymbol visas.</span><span class="sxs-lookup"><span data-stu-id="9f718-140">If the scheduled throughput exceeds the maximum throughput, the period is considered as overloaded, and a red warning symbol appears.</span></span> <span data-ttu-id="9f718-141">Ett tidsplanerat kanban-jobb visas under en period som har tidsplanerade start- och sluttider (5).</span><span class="sxs-lookup"><span data-stu-id="9f718-141">A scheduled kanban job appears in a period that has scheduled start and end times (5).</span></span> <span data-ttu-id="9f718-142">Jobbets varaktighet motsvarar aktivitetstiden.</span><span class="sxs-lookup"><span data-stu-id="9f718-142">The length of the job is equal to the activity time.</span></span> <span data-ttu-id="9f718-143">Kanban-jobb visas som överlappning under en period om deras aktivitetstider överskrider takttiden för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9f718-143">Kanban jobs appear as overlapping in a period if their activity times exceed the takt time of the work cell.</span></span>

### <a name="view-job-status"></a><span data-ttu-id="9f718-144">Visa jobbstatus</span><span class="sxs-lookup"><span data-stu-id="9f718-144">View job status</span></span>

<span data-ttu-id="9f718-145">Mer information om ett kanban-jobb finns i knappbeskrivningen som visas när du för pekaren över jobbet.</span><span class="sxs-lookup"><span data-stu-id="9f718-145">More information about a kanban job is available in the tooltip that appears when you hover the pointer over the job.</span></span> <span data-ttu-id="9f718-146">En symbol innehåller information om statusen på jobbet.</span><span class="sxs-lookup"><span data-stu-id="9f718-146">A symbol provides information about the status of the job.</span></span> <span data-ttu-id="9f718-147">Exempelvis indikerar en klocksymbole att kanban-jobbet har förfallit.</span><span class="sxs-lookup"><span data-stu-id="9f718-147">For example, a clock symbol indicates that the kanban job is overdue.</span></span>

### <a name="use-colors-to-view-the-kanban-schedule-board"></a><span data-ttu-id="9f718-148">Använda färger för att visa kanban-schematavlan</span><span class="sxs-lookup"><span data-stu-id="9f718-148">Use colors to view the Kanban schedule board</span></span>

<span data-ttu-id="9f718-149">Du kan använda färger för att förbättra översikten över kanban-schematavlan och särskilja kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-149">To enhance the overview that the Kanban schedule board provides, you can use colors to distinguish kanban jobs.</span></span> <span data-ttu-id="9f718-150">Färgen på kanban-jobb konfigureras i den resurssnåla schemagruppen där du kan aggregera produkter som ska produceras i samma ordning.</span><span class="sxs-lookup"><span data-stu-id="9f718-150">The color of a kanban job is configured in the lean schedule group, where you can aggregate the products that should be produced in the same sequence.</span></span> <span data-ttu-id="9f718-151">Med knappen **Använd temafärger** i fliken **Tavla** i åtgärdsfönstret kan du växla mellan programmets temafärger och färgerna som har konfigurerats i den resurssnåla schemagruppen.</span><span class="sxs-lookup"><span data-stu-id="9f718-151">The **Use theme colors** button on the **Board** tab of the Action Pane lets you switch between the application theme colors and the colors that are configured in the lean schedule group.</span></span> <span data-ttu-id="9f718-152">För varje period visar en kapacitetsstapel (6) hur många av antalet tillgängliga timmar för perioden som har lästs in med kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-152">For each period, a capacity bar (6) indicates how many of the available hours for the period have been loaded with kanban jobs.</span></span> <span data-ttu-id="9f718-153">Om perioden är överbelastad är kapacitetsstapeln tjockare och röd.</span><span class="sxs-lookup"><span data-stu-id="9f718-153">If the period is overloaded, the capacity bar appears thicker and in red.</span></span> <span data-ttu-id="9f718-154">Alla dessa funktioner är tillgängliga i fliken **Tavla** i åtgärdsfönstret (1) högst upp på sidan **Kanban-schematavla**.</span><span class="sxs-lookup"><span data-stu-id="9f718-154">All these functions are available on the **Board** tab of the Action Pane (1) at the top of the **Kanban schedule board** page.</span></span>

## <a name="plan-unplanned-jobs"></a><span data-ttu-id="9f718-155">Planera oplanerade jobb</span><span class="sxs-lookup"><span data-stu-id="9f718-155">Plan unplanned jobs</span></span>
<span data-ttu-id="9f718-156">Du kan schemalägga oplanerade kanban-jobb från dialogrutan **Planera oförutsedda jobb**.</span><span class="sxs-lookup"><span data-stu-id="9f718-156">You can schedule unplanned kanban jobs from the **Plan unplanned jobs** dialog box.</span></span> <span data-ttu-id="9f718-157">Om du vill öppna den här dialogrutan, klicka på knappen **Oplanerade jobb** som visar det aktuella antalet oplanerade jobb.</span><span class="sxs-lookup"><span data-stu-id="9f718-157">To open this dialog box, click the **Unplanned jobs** button that shows the current number of unplanned jobs.</span></span> <span data-ttu-id="9f718-158">Alternativt kan du klicka på **Planera oplanerade jobb** i fliken **Tavla** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9f718-158">Alternatively, click **Plan unplanned jobs** on the **Board** tab of the Action Pane.</span></span> <span data-ttu-id="9f718-159">I dialogrutan visas en lista med oplanerade kanban-jobb för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9f718-159">The dialog box shows a list of the unplanned kanban jobs for the work cell.</span></span> <span data-ttu-id="9f718-160">Du kan använda fältet **Filter** för att filtrera efter alla fält i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9f718-160">You can use the **Filter** field to filter on all fields in the grid.</span></span> <span data-ttu-id="9f718-161">Du kan till exempel filtrera på kanban-jobb för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="9f718-161">For example, you can filter on kanban jobs for a specific product.</span></span> <span data-ttu-id="9f718-162">När du har skapat en filtrerad lista över de jobb som du vill tidsplanera markerar du dem i listan och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f718-162">After you have a filtered list of the jobs that you want to schedule, select them in the list, and then click **OK**.</span></span> <span data-ttu-id="9f718-163">Om du vill använda automatisk planering för att tidsplaner, ställ in alternativet **Automatisk planering** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9f718-163">To use automatic planning to schedule the jobs, set the **Automatic planning** option to **Yes**.</span></span> <span data-ttu-id="9f718-164">I detta fall tidsplaneras jobben till en period efter sina förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="9f718-164">In this case, the jobs are scheduled into a period according to their due date.</span></span> <span data-ttu-id="9f718-165">Du kan också tidsplanera jobb per period.</span><span class="sxs-lookup"><span data-stu-id="9f718-165">You can also schedule the jobs by period.</span></span> <span data-ttu-id="9f718-166">Välj bara en period i fältet **Period**.</span><span class="sxs-lookup"><span data-stu-id="9f718-166">Just select a period in the **Period** field.</span></span> <span data-ttu-id="9f718-167">Följande bild visar ett exempel på dialogrutan **Planera oplanerade jobb**.</span><span class="sxs-lookup"><span data-stu-id="9f718-167">The following illustration shows an example of the **Plan unplanned jobs** dialog box.</span></span> 

![Dialogrutan Planera oplanerade jobb](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a><span data-ttu-id="9f718-169">Sekvensen kanban-jobb inom samma period</span><span class="sxs-lookup"><span data-stu-id="9f718-169">Sequence kanban jobs within the same period</span></span>
<span data-ttu-id="9f718-170">Du kan ändra ordningen på en eller flera valda jobb inom en period.</span><span class="sxs-lookup"><span data-stu-id="9f718-170">You can change the sequence of one or more selected jobs within a period.</span></span> <span data-ttu-id="9f718-171">Detta kan vara användbart om du vill prioritera vissa jobb under perioden.</span><span class="sxs-lookup"><span data-stu-id="9f718-171">This capability can be useful if you want to prioritize some jobs within the period.</span></span> <span data-ttu-id="9f718-172">Alternativt kan behöva du ordna jobb som har samma produktattribut i sekvens för att optimera körningen.</span><span class="sxs-lookup"><span data-stu-id="9f718-172">Alternatively, you might want to sequence jobs that have the same product attributes, to optimize job execution.</span></span> <span data-ttu-id="9f718-173">Du kan ändra ordningen genom att dra och släppa eller genom att använda menyalternativen **Bakåt** och **Framåt** på fliken **Tavla** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9f718-173">You can change the sequence through a drag-and-drop operation, or by using the **Backward** and **Forward** menu items on the **Board** tab of the Action Pane.</span></span>

## <a name="reassign-kanban-jobs-across-periods"></a><span data-ttu-id="9f718-174">Tilldela om kanban-jobb över perioder</span><span class="sxs-lookup"><span data-stu-id="9f718-174">Reassign kanban jobs across periods</span></span>
<span data-ttu-id="9f718-175">Jobb kan tilldelas om från en period till en annan.</span><span class="sxs-lookup"><span data-stu-id="9f718-175">Jobs can be reassigned from one period to another.</span></span> <span data-ttu-id="9f718-176">Den här funktionen kan vara användbar om en period är överbelastad och du vill utjämna belastningen för perioder som har ledig kapacitet.</span><span class="sxs-lookup"><span data-stu-id="9f718-176">This capability can be useful if a period is overloaded and you want to level the load to periods that have spare capacity.</span></span> <span data-ttu-id="9f718-177">Du kan tilldela om jobb genom att dra och släppa eller genom att använda menyalternativen **Nästa period** och **Föregående period** på fliken **Tavla** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9f718-177">You can reassign jobs through a drag-and-drop operation, or by using the **Next period** and **Previous period** menu items on the **Board** tab of the Action Pane.</span></span>

## <a name="open-the-kanban-schedule-board"></a><span data-ttu-id="9f718-178">Öppna kanban-schematavlan</span><span class="sxs-lookup"><span data-stu-id="9f718-178">Open the Kanban schedule board</span></span>
<span data-ttu-id="9f718-179">Du kan öppna kanban-schematavlan genom att använda menyalternativet på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="9f718-179">You can open the Kanban schedule board by using the menu item on the following pages:</span></span>

-   <span data-ttu-id="9f718-180">Sidan **Produktionsområde**</span><span class="sxs-lookup"><span data-stu-id="9f718-180">**Production area** page</span></span>
-   <span data-ttu-id="9f718-181">Sidan **Planering av kanban-jobb**</span><span class="sxs-lookup"><span data-stu-id="9f718-181">**Kanban jobs scheduling** page</span></span>
-   <span data-ttu-id="9f718-182">Sidan **Visualisering av produktionsflöde**</span><span class="sxs-lookup"><span data-stu-id="9f718-182">**Production flow visualization** page</span></span>


<a name="see-also"></a><span data-ttu-id="9f718-183">Se även</span><span class="sxs-lookup"><span data-stu-id="9f718-183">See also</span></span>
--------

[<span data-ttu-id="9f718-184">Lean manufacturing – Kanban-jobbplanering</span><span class="sxs-lookup"><span data-stu-id="9f718-184">Lean manufacturing – Kanban job scheduling</span></span>](lean-manufacturing-kanban-job-scheduling.md)

