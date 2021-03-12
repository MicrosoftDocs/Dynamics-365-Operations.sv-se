---
title: Övervaka en huvudplaneringskörning
description: Det här ämnet förklarar hur produktionsplanerare kan se om en huvudplaneringskörning pågår.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1cbe2c55ef9e3ed35db30ca927f3472c750c1db5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999816"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="f6d06-103">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="f6d06-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="f6d06-104">Visualisera huvudplaneringsförlopp med hjälp av ett Gantt-diagram</span><span class="sxs-lookup"><span data-stu-id="f6d06-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="f6d06-105">På sidan **Visa huvudplaneringsförlopp** kan du visa detaljer om historisk huvudplanering som körs som ett Gantt-diagram.</span><span class="sxs-lookup"><span data-stu-id="f6d06-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="f6d06-106">Med hjälp av den här funktionen kan du förstå hur lång tid som ägnas åt olika faser i huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="f6d06-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="f6d06-107">För ett aktuellt aktivt planeringsjobb kan du använda sidan **Visa huvudplaneringsförlopp** för att spåra status och visa den uppskattade återstående tiden.</span><span class="sxs-lookup"><span data-stu-id="f6d06-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="f6d06-108">Aktivera och använda funktionen för visualisering av huvudplanstatus</span><span class="sxs-lookup"><span data-stu-id="f6d06-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="f6d06-109">Du använder funktionen genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f6d06-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="f6d06-110">I arbetsytan **Funktionshantering** på fliken **Ny**, välj **Visualisering av huvudplaneringsförlopp** i listan.</span><span class="sxs-lookup"><span data-stu-id="f6d06-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="f6d06-111">Om funktionen inte visas på fliken **Ny** tittar du på flikarna **Ej aktiverad** och **Alla**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="f6d06-112">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-112">Select **Enable now**.</span></span> <span data-ttu-id="f6d06-113">Du kan också välja **schema** och sedan välja den tidpunkt då funktionen ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f6d06-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="f6d06-114">Sidan **Visa huvudplaneringsförlopp** kan visa både historiska planeringsjobb och aktiva planeringsjobb.</span><span class="sxs-lookup"><span data-stu-id="f6d06-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="f6d06-115">Det finns två alternativ för att visa historiska planeringsjobb.</span><span class="sxs-lookup"><span data-stu-id="f6d06-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="f6d06-116">Gå till **huvudplanering \> inställningar \> planer \> huvudplaner** och välj sedan **historik** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f6d06-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="f6d06-117">Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**</span><span class="sxs-lookup"><span data-stu-id="f6d06-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="f6d06-118">Gå till **huvudplanering \> arbetsytor \> huvudplanering** och klicka på **historik** på panelen Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="f6d06-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="f6d06-119">Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**</span><span class="sxs-lookup"><span data-stu-id="f6d06-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="f6d06-120">Det finns två alternativ för att visa aktiva planeringsjobb.</span><span class="sxs-lookup"><span data-stu-id="f6d06-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="f6d06-121">Gå till **Huvudplanering \> Arbetsytor \> Huvudplanering** i åtgärdsfönstret välj **Oavslutade planeringsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="f6d06-122">Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="f6d06-123">Gå till **huvudplanering \> arbetsytor \> huvudplanering** och klicka på **Visa förlopp** på panelen Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="f6d06-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="f6d06-124">Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**</span><span class="sxs-lookup"><span data-stu-id="f6d06-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="f6d06-125">Observera att du kan bara visa aktiva jobb när ett planeringsjobb bearbetas.</span><span class="sxs-lookup"><span data-stu-id="f6d06-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="f6d06-126">Analysera ett huvudplaneringsjobb</span><span class="sxs-lookup"><span data-stu-id="f6d06-126">Analyze a master planning job</span></span>

<span data-ttu-id="f6d06-127">I Gantt-diagrammet kan du expandera var och en av följande planeringsprocesser för att visa mer information om tiden som förbrukas:</span><span class="sxs-lookup"><span data-stu-id="f6d06-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="f6d06-128">Initierar</span><span class="sxs-lookup"><span data-stu-id="f6d06-128">Initializing</span></span>
- <span data-ttu-id="f6d06-129">Tar bort och infogar data</span><span class="sxs-lookup"><span data-stu-id="f6d06-129">Deleting and inserting data</span></span>
- <span data-ttu-id="f6d06-130">Disponeringsplanering</span><span class="sxs-lookup"><span data-stu-id="f6d06-130">Coverage planning</span></span>
- <span data-ttu-id="f6d06-131">Fördröjningar</span><span class="sxs-lookup"><span data-stu-id="f6d06-131">Delays</span></span>
- <span data-ttu-id="f6d06-132">Åtgärdsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="f6d06-132">Action messages</span></span>
- <span data-ttu-id="f6d06-133">Slutförande</span><span class="sxs-lookup"><span data-stu-id="f6d06-133">Finalization</span></span>
- <span data-ttu-id="f6d06-134">Automatisk bekräftelse</span><span class="sxs-lookup"><span data-stu-id="f6d06-134">Auto-firming</span></span>

<span data-ttu-id="f6d06-135">Gantt-diagrammet är ett användbart verktyg om du vill visa effekten av att använda åtgärdsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="f6d06-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="f6d06-136">Navigering i Gantt-diagrammet</span><span class="sxs-lookup"><span data-stu-id="f6d06-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="f6d06-137">Om du vill expandera den markerade gruppen och visa information markerar du plustecknet (**+**) i trädvyn.</span><span class="sxs-lookup"><span data-stu-id="f6d06-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="f6d06-138">Om du vill komprimera den markerade gruppen väljer du minustecknet (**–**) i trädvyn.</span><span class="sxs-lookup"><span data-stu-id="f6d06-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="f6d06-139">Du kan använda tangentbordet för att navigera.</span><span class="sxs-lookup"><span data-stu-id="f6d06-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="f6d06-140">Använd **uppilen** och **nedpilen** om du vill flytta mellan raderna.</span><span class="sxs-lookup"><span data-stu-id="f6d06-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="f6d06-141">Använd **högerpilen** och **vänsterpilen** för att visa eller dölja grupper.</span><span class="sxs-lookup"><span data-stu-id="f6d06-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="f6d06-142">Om du vill öppna eller stänga alla nivåer i Gantt-diagrammet väljer du **Visa alla** eller **Dölj alla**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="f6d06-143">Om du vill visa den relaterade bearbetningstiden hovrar du över en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="f6d06-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="f6d06-144">(Uppgifter är de lägsta nivåerna i Gantt-diagrammet.)</span><span class="sxs-lookup"><span data-stu-id="f6d06-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="f6d06-145">Visa en ytterligare huvudplaneringskörning för att jämföra jobb</span><span class="sxs-lookup"><span data-stu-id="f6d06-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="f6d06-146">Genom att välja ett huvudplaneringsjobb på fältet **Visa ytterligare huvudplaneringskörning**, men du kan visa ytterligare en huvudplaneringskörning i Gantt-diagrammet och jämföra de två jobben.</span><span class="sxs-lookup"><span data-stu-id="f6d06-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="f6d06-147">Visning på strukturnivå</span><span class="sxs-lookup"><span data-stu-id="f6d06-147">BOM-level display</span></span>

<span data-ttu-id="f6d06-148">Strukturlistenivåer visas på olika sätt vid disponeringsplanering, förseningar, åtgärder och bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="f6d06-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="f6d06-149">**Disponeringsplanering** – strukturnivåerna visas som förväntat.</span><span class="sxs-lookup"><span data-stu-id="f6d06-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="f6d06-150">De beräknas uppifrån och ned.</span><span class="sxs-lookup"><span data-stu-id="f6d06-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="f6d06-151">**Exempel:** Strukturlistenivå 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="f6d06-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="f6d06-152">**Fördröjningar** – strukturlistenivåer visas som disponeringsplanering för strukturlistenivåer multiplicerat med –1.</span><span class="sxs-lookup"><span data-stu-id="f6d06-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="f6d06-153">(Med andra ord har de ett negativt tecken.)</span><span class="sxs-lookup"><span data-stu-id="f6d06-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="f6d06-154">**Exempel:** Strukturlistenivå –2, –1, 0</span><span class="sxs-lookup"><span data-stu-id="f6d06-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="f6d06-155">**Åtgärdsmeddelande** – strukturnivåerna visas som förväntat.</span><span class="sxs-lookup"><span data-stu-id="f6d06-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="f6d06-156">De beräknas uppifrån och ned.</span><span class="sxs-lookup"><span data-stu-id="f6d06-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="f6d06-157">**Exempel:** Strukturlistenivå 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="f6d06-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="f6d06-158">**Automatisk bekräftelse** – strukturlistenivåerna visas som 999 minus nivån för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="f6d06-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="f6d06-159">**Exempel:** Strukturlistenivå 999, 998, 997</span><span class="sxs-lookup"><span data-stu-id="f6d06-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="f6d06-160">I följande tabell sammanfattas beteendet.</span><span class="sxs-lookup"><span data-stu-id="f6d06-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="f6d06-161">Strukturlistenivå som visas</span><span class="sxs-lookup"><span data-stu-id="f6d06-161">BOM level that is shown</span></span> | <span data-ttu-id="f6d06-162">Slutartikel</span><span class="sxs-lookup"><span data-stu-id="f6d06-162">End item</span></span> | <span data-ttu-id="f6d06-163">Delkomponent</span><span class="sxs-lookup"><span data-stu-id="f6d06-163">Subcomponent</span></span> | <span data-ttu-id="f6d06-164">Råmaterial</span><span class="sxs-lookup"><span data-stu-id="f6d06-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="f6d06-165">Disponeringsplanering</span><span class="sxs-lookup"><span data-stu-id="f6d06-165">Coverage planning</span></span> | <span data-ttu-id="f6d06-166">0</span><span class="sxs-lookup"><span data-stu-id="f6d06-166">0</span></span> | <span data-ttu-id="f6d06-167">1</span><span class="sxs-lookup"><span data-stu-id="f6d06-167">1</span></span> | <span data-ttu-id="f6d06-168">2</span><span class="sxs-lookup"><span data-stu-id="f6d06-168">2</span></span> |
| <span data-ttu-id="f6d06-169">Fördröjningar</span><span class="sxs-lookup"><span data-stu-id="f6d06-169">Delays</span></span> | <span data-ttu-id="f6d06-170">0</span><span class="sxs-lookup"><span data-stu-id="f6d06-170">0</span></span> | <span data-ttu-id="f6d06-171">–1</span><span class="sxs-lookup"><span data-stu-id="f6d06-171">–1</span></span> | <span data-ttu-id="f6d06-172">–2</span><span class="sxs-lookup"><span data-stu-id="f6d06-172">–2</span></span> |
| <span data-ttu-id="f6d06-173">Åtgärdsmeddelande</span><span class="sxs-lookup"><span data-stu-id="f6d06-173">Action message</span></span> | <span data-ttu-id="f6d06-174">0</span><span class="sxs-lookup"><span data-stu-id="f6d06-174">0</span></span> | <span data-ttu-id="f6d06-175">1</span><span class="sxs-lookup"><span data-stu-id="f6d06-175">1</span></span> | <span data-ttu-id="f6d06-176">2</span><span class="sxs-lookup"><span data-stu-id="f6d06-176">2</span></span> |
| <span data-ttu-id="f6d06-177">Automatisk bekräftelse</span><span class="sxs-lookup"><span data-stu-id="f6d06-177">Auto-firming</span></span> | <span data-ttu-id="f6d06-178">999</span><span class="sxs-lookup"><span data-stu-id="f6d06-178">999</span></span> | <span data-ttu-id="f6d06-179">998</span><span class="sxs-lookup"><span data-stu-id="f6d06-179">998</span></span> | <span data-ttu-id="f6d06-180">997</span><span class="sxs-lookup"><span data-stu-id="f6d06-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="f6d06-181">Visualisera förlopp</span><span class="sxs-lookup"><span data-stu-id="f6d06-181">Visualize progress</span></span>

<span data-ttu-id="f6d06-182">Om du visar ett huvudplaneringsjobb som körs visas förlopp via färger i Gantt-diagrammet.</span><span class="sxs-lookup"><span data-stu-id="f6d06-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="f6d06-183">Följande färger gäller för det blåa temat.</span><span class="sxs-lookup"><span data-stu-id="f6d06-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="f6d06-184">För andra färgteman skiljer sig färgerna åt.</span><span class="sxs-lookup"><span data-stu-id="f6d06-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="f6d06-185">**Mörkblå** – slutförda planeringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="f6d06-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="f6d06-186">**Orange** – den uppgift som pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="f6d06-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="f6d06-187">**Ljusblå** – uppskattningen för återstående uppgifter.</span><span class="sxs-lookup"><span data-stu-id="f6d06-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="f6d06-188">Färgen visas endast på den lägsta nivån i Gantt-diagrammet.</span><span class="sxs-lookup"><span data-stu-id="f6d06-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="f6d06-189">Välj **expandera alla** om du vill visa alla uppgifter i huvudplaneringsjobbet.</span><span class="sxs-lookup"><span data-stu-id="f6d06-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="f6d06-190">Uppskattningen av återstående uppgifter baseras på historiska huvudplaneringsjobb.</span><span class="sxs-lookup"><span data-stu-id="f6d06-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="f6d06-191">Kör huvudplanering och spårning av bearbetningstid</span><span class="sxs-lookup"><span data-stu-id="f6d06-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="f6d06-192">Välj **Huvudplanering** på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="f6d06-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="f6d06-193">I fältet **Plan**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="f6d06-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="f6d06-194">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-194">Select **Run**.</span></span>
1. <span data-ttu-id="f6d06-195">Ange alternativet **Spåra bearbetningstid** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="f6d06-196">Ange ett nummer i fältet **Antal trådar.**</span><span class="sxs-lookup"><span data-stu-id="f6d06-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="f6d06-197">På snabbfliken **Poster att inkludera**, välj **Filter**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="f6d06-198">I rutnätet väljer du den rad där fältet **fält** är inställt på **artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="f6d06-199">I fältet **Kriterier** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="f6d06-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="f6d06-200">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6d06-200">Select **OK**.</span></span>
