---
title: "Stöd för kanban-överföringstavla för streckkodsskanner"
description: "Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="bf92a-103">Stöd för kanban-överföringstavla för streckkodsskanner</span><span class="sxs-lookup"><span data-stu-id="bf92a-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf92a-104">Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="bf92a-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="bf92a-105">Registreringslägen</span><span class="sxs-lookup"><span data-stu-id="bf92a-105">Registration modes</span></span>
------------------

<span data-ttu-id="bf92a-106">På snabbfliken **Skannerregistrering** kan du välja det registreringsläge som styr åtgärden när du skannar ett kanban-kortnummer eller skriver in numret manuellt numret i fältet för kanban-kortnumret.</span><span class="sxs-lookup"><span data-stu-id="bf92a-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="bf92a-107">Ange registreringsläge</span><span class="sxs-lookup"><span data-stu-id="bf92a-107">Set registration mode</span></span> | <span data-ttu-id="bf92a-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bf92a-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="bf92a-109">Starta</span><span class="sxs-lookup"><span data-stu-id="bf92a-109">Start</span></span>                 | <span data-ttu-id="bf92a-110">Registrera ett kanban-överföringsjobb som pågående.</span><span class="sxs-lookup"><span data-stu-id="bf92a-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="bf92a-111">Slutförd</span><span class="sxs-lookup"><span data-stu-id="bf92a-111">Complete</span></span>              | <span data-ttu-id="bf92a-112">Registrera ett kanban-överföringsjobb som slutfört.</span><span class="sxs-lookup"><span data-stu-id="bf92a-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="bf92a-113">Tom</span><span class="sxs-lookup"><span data-stu-id="bf92a-113">Empty</span></span>                 | <span data-ttu-id="bf92a-114">Registrera den materialhanteringsenhet som refereras av kanban-kortet som tomt.</span><span class="sxs-lookup"><span data-stu-id="bf92a-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="bf92a-115">Välj</span><span class="sxs-lookup"><span data-stu-id="bf92a-115">Select</span></span>                | <span data-ttu-id="bf92a-116">Registrera ett kanban-kortnummer och välj automatiskt det jobb som refereras i kanban-listan</span><span class="sxs-lookup"><span data-stu-id="bf92a-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="bf92a-117">Registreringsläge Välj</span><span class="sxs-lookup"><span data-stu-id="bf92a-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="bf92a-118">När du använder en streckkodsläsare för att välja ett jobb, ändras visningsläget på kanban-tavlan.</span><span class="sxs-lookup"><span data-stu-id="bf92a-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="bf92a-119">I detta läge gäller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="bf92a-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="bf92a-120">Endast skannade kanban-jobb visas.</span><span class="sxs-lookup"><span data-stu-id="bf92a-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="bf92a-121">Information om det utvalda jobbet visas på snabbfliken **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="bf92a-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="bf92a-122">Snabbfliken **Meddelanden** visas bara för det valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="bf92a-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="bf92a-123">Du kan ändra status för jobbet genom att använda funktionerna som är tillgängliga på Åtgärdsfönster.</span><span class="sxs-lookup"><span data-stu-id="bf92a-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="bf92a-124">Kanban-överföringstavla fortsätter att endast visa ett enskilt jobb under denna tid.</span><span class="sxs-lookup"><span data-stu-id="bf92a-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="bf92a-125">Du kan uppdatera informationen i listan över jobb manuellt genom att klicka på **Uppdatera** (Shift+F5) på åtgärdsfliken.</span><span class="sxs-lookup"><span data-stu-id="bf92a-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="bf92a-126">När du har uppdaterat informationen visas de fullständiga resultaten för jobbfiltret igen.</span><span class="sxs-lookup"><span data-stu-id="bf92a-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="bf92a-127">Jobbstatus och möjliga åtgärder</span><span class="sxs-lookup"><span data-stu-id="bf92a-127">Job status and possible actions</span></span>
<span data-ttu-id="bf92a-128">Status för valda jobb och status för alla fixerade jobb för händelsekanban avgör om du kan ytterligare bearbeta jobbet.</span><span class="sxs-lookup"><span data-stu-id="bf92a-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="bf92a-129">Följande tabell visar information om dessa status och uppgifter:</span><span class="sxs-lookup"><span data-stu-id="bf92a-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="bf92a-130">Status som är tillgängliga för jobb, eller för materialhanteringsenheterna som refereras av jobben.</span><span class="sxs-lookup"><span data-stu-id="bf92a-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="bf92a-131">Varje uppgift som du kan utföra för jobbet.</span><span class="sxs-lookup"><span data-stu-id="bf92a-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf92a-132">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="bf92a-132">Job type</span></span></th>
<th><span data-ttu-id="bf92a-133">Jobbstatus eller materialhanteringsenhetstatus</span><span class="sxs-lookup"><span data-stu-id="bf92a-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="bf92a-134">Uppdatera plocklista</span><span class="sxs-lookup"><span data-stu-id="bf92a-134">Update picking list</span></span></th>
<th><span data-ttu-id="bf92a-135">Starta</span><span class="sxs-lookup"><span data-stu-id="bf92a-135">Start</span></span></th>
<th><span data-ttu-id="bf92a-136">Uppdatera registrering</span><span class="sxs-lookup"><span data-stu-id="bf92a-136">Update registration</span></span></th>
<th><span data-ttu-id="bf92a-137">Slutförd</span><span class="sxs-lookup"><span data-stu-id="bf92a-137">Complete</span></span></th>
<th><span data-ttu-id="bf92a-138">Tom</span><span class="sxs-lookup"><span data-stu-id="bf92a-138">Empty</span></span></th>
<th><span data-ttu-id="bf92a-139">Skapa händelse-kanban</span><span class="sxs-lookup"><span data-stu-id="bf92a-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bf92a-140">Överför</span><span class="sxs-lookup"><span data-stu-id="bf92a-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="bf92a-141">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="bf92a-141">Not planned</span></span></li>
<li><span data-ttu-id="bf92a-142">Inga fixerade jobb eller fixerade jobb är slutförda</span><span class="sxs-lookup"><span data-stu-id="bf92a-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="bf92a-143">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-143">Yes</span></span></td>
<td><span data-ttu-id="bf92a-144">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-144">Yes</span></span></td>
<td><span data-ttu-id="bf92a-145">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-145">Yes</span></span></td>
<td><span data-ttu-id="bf92a-146">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-146">Yes</span></span></td>
<td><span data-ttu-id="bf92a-147">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-147">No</span></span></td>
<td><span data-ttu-id="bf92a-148">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bf92a-149">Överför</span><span class="sxs-lookup"><span data-stu-id="bf92a-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="bf92a-150">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="bf92a-150">Not planned</span></span></li>
<li><span data-ttu-id="bf92a-151">Det fixerade jobbet är inte avslutat</span><span class="sxs-lookup"><span data-stu-id="bf92a-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="bf92a-152">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-152">Yes</span></span></td>
<td><span data-ttu-id="bf92a-153">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-153">No</span></span></td>
<td><span data-ttu-id="bf92a-154">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-154">Yes</span></span></td>
<td><span data-ttu-id="bf92a-155">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-155">No</span></span></td>
<td><span data-ttu-id="bf92a-156">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-156">No</span></span></td>
<td><span data-ttu-id="bf92a-157">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bf92a-158">Överför</span><span class="sxs-lookup"><span data-stu-id="bf92a-158">Transfer</span></span></td>
<td><span data-ttu-id="bf92a-159">Pågår</span><span class="sxs-lookup"><span data-stu-id="bf92a-159">In progress</span></span></td>
<td><span data-ttu-id="bf92a-160">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-160">Yes</span></span></td>
<td><span data-ttu-id="bf92a-161">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-161">No</span></span></td>
<td><span data-ttu-id="bf92a-162">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-162">Yes</span></span></td>
<td><span data-ttu-id="bf92a-163">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-163">Yes</span></span></td>
<td><span data-ttu-id="bf92a-164">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-164">No</span></span></td>
<td><span data-ttu-id="bf92a-165">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bf92a-166">Överför</span><span class="sxs-lookup"><span data-stu-id="bf92a-166">Transfer</span></span></td>
<td><span data-ttu-id="bf92a-167">Slutförd</span><span class="sxs-lookup"><span data-stu-id="bf92a-167">Completed</span></span></td>
<td><span data-ttu-id="bf92a-168">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-168">No</span></span></td>
<td><span data-ttu-id="bf92a-169">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-169">No</span></span></td>
<td><span data-ttu-id="bf92a-170">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-170">No</span></span></td>
<td><span data-ttu-id="bf92a-171">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-171">No</span></span></td>
<td><span data-ttu-id="bf92a-172">Ja</span><span class="sxs-lookup"><span data-stu-id="bf92a-172">Yes</span></span></td>
<td><span data-ttu-id="bf92a-173">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bf92a-174">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="bf92a-174">Transfer or process</span></span></td>
<td><span data-ttu-id="bf92a-175">Tom</span><span class="sxs-lookup"><span data-stu-id="bf92a-175">Empty</span></span></td>
<td><span data-ttu-id="bf92a-176">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-176">No</span></span></td>
<td><span data-ttu-id="bf92a-177">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-177">No</span></span></td>
<td><span data-ttu-id="bf92a-178">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-178">No</span></span></td>
<td><span data-ttu-id="bf92a-179">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-179">No</span></span></td>
<td><span data-ttu-id="bf92a-180">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-180">No</span></span></td>
<td><span data-ttu-id="bf92a-181">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bf92a-182">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="bf92a-182">Transfer or process</span></span></td>
<td><span data-ttu-id="bf92a-183">Ett kanban-kort hittades inte</span><span class="sxs-lookup"><span data-stu-id="bf92a-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="bf92a-184">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-184">No</span></span></td>
<td><span data-ttu-id="bf92a-185">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-185">No</span></span></td>
<td><span data-ttu-id="bf92a-186">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-186">No</span></span></td>
<td><span data-ttu-id="bf92a-187">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-187">No</span></span></td>
<td><span data-ttu-id="bf92a-188">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-188">No</span></span></td>
<td><span data-ttu-id="bf92a-189">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bf92a-190">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="bf92a-190">Transfer or process</span></span></td>
<td><span data-ttu-id="bf92a-191">Ett kanban-kort hittades, men det har tilldelats en kanban</span><span class="sxs-lookup"><span data-stu-id="bf92a-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="bf92a-192">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-192">No</span></span></td>
<td><span data-ttu-id="bf92a-193">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-193">No</span></span></td>
<td><span data-ttu-id="bf92a-194">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-194">No</span></span></td>
<td><span data-ttu-id="bf92a-195">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-195">No</span></span></td>
<td><span data-ttu-id="bf92a-196">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-196">No</span></span></td>
<td><span data-ttu-id="bf92a-197">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bf92a-198">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="bf92a-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="bf92a-199">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="bf92a-199">Not planned</span></span></li>
<li><span data-ttu-id="bf92a-200">Förberedd</span><span class="sxs-lookup"><span data-stu-id="bf92a-200">Prepared</span></span></li>
<li><span data-ttu-id="bf92a-201">Pågår</span><span class="sxs-lookup"><span data-stu-id="bf92a-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="bf92a-202">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-202">No</span></span></td>
<td><span data-ttu-id="bf92a-203">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-203">No</span></span></td>
<td><span data-ttu-id="bf92a-204">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-204">No</span></span></td>
<td><span data-ttu-id="bf92a-205">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-205">No</span></span></td>
<td><span data-ttu-id="bf92a-206">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-206">No</span></span></td>
<td><span data-ttu-id="bf92a-207">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bf92a-208">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="bf92a-208">Process</span></span></td>
<td><span data-ttu-id="bf92a-209">Slutförd</span><span class="sxs-lookup"><span data-stu-id="bf92a-209">Completed</span></span></td>
<td><span data-ttu-id="bf92a-210">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-210">No</span></span></td>
<td><span data-ttu-id="bf92a-211">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-211">No</span></span></td>
<td><span data-ttu-id="bf92a-212">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-212">No</span></span></td>
<td><span data-ttu-id="bf92a-213">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-213">No</span></span></td>
<td><span data-ttu-id="bf92a-214">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-214">No</span></span></td>
<td><span data-ttu-id="bf92a-215">Nej</span><span class="sxs-lookup"><span data-stu-id="bf92a-215">No</span></span></td>
</tr>
</tbody>
</table>






