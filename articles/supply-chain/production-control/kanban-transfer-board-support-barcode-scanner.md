---
title: Stöd för kanban-överföringstavla för streckkodsskanner
description: Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bd6f1bdd847f74cee7d3594d19b72454063c0cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207196"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="a152c-103">Stöd för kanban-överföringstavla för streckkodsskanner</span><span class="sxs-lookup"><span data-stu-id="a152c-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a152c-104">Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="a152c-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="a152c-105">Registreringslägen</span><span class="sxs-lookup"><span data-stu-id="a152c-105">Registration modes</span></span>
------------------

<span data-ttu-id="a152c-106">På snabbfliken **Skannerregistrering** kan du välja det registreringsläge som styr åtgärden när du skannar ett kanban-kortnummer eller skriver in numret manuellt numret i fältet för kanban-kortnumret.</span><span class="sxs-lookup"><span data-stu-id="a152c-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="a152c-107">Ange registreringsläge</span><span class="sxs-lookup"><span data-stu-id="a152c-107">Set registration mode</span></span> | <span data-ttu-id="a152c-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a152c-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a152c-109">Starta</span><span class="sxs-lookup"><span data-stu-id="a152c-109">Start</span></span>                 | <span data-ttu-id="a152c-110">Registrera ett kanban-överföringsjobb som pågående.</span><span class="sxs-lookup"><span data-stu-id="a152c-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="a152c-111">Slutförd</span><span class="sxs-lookup"><span data-stu-id="a152c-111">Complete</span></span>              | <span data-ttu-id="a152c-112">Registrera ett kanban-överföringsjobb som slutfört.</span><span class="sxs-lookup"><span data-stu-id="a152c-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="a152c-113">Tom</span><span class="sxs-lookup"><span data-stu-id="a152c-113">Empty</span></span>                 | <span data-ttu-id="a152c-114">Registrera den materialhanteringsenhet som refereras av kanban-kortet som tomt.</span><span class="sxs-lookup"><span data-stu-id="a152c-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="a152c-115">Välj</span><span class="sxs-lookup"><span data-stu-id="a152c-115">Select</span></span>                | <span data-ttu-id="a152c-116">Registrera ett kanban-kortnummer och välj automatiskt det jobb som refereras i kanban-listan</span><span class="sxs-lookup"><span data-stu-id="a152c-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="a152c-117">Registreringsläge Välj</span><span class="sxs-lookup"><span data-stu-id="a152c-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="a152c-118">När du använder en streckkodsläsare för att välja ett jobb, ändras visningsläget på kanban-tavlan.</span><span class="sxs-lookup"><span data-stu-id="a152c-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="a152c-119"> I detta läge gäller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a152c-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="a152c-120">Endast skannade kanban-jobb visas.</span><span class="sxs-lookup"><span data-stu-id="a152c-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="a152c-121">Information om det utvalda jobbet visas på snabbfliken **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="a152c-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="a152c-122">Snabbfliken **Meddelanden** visas bara för det valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="a152c-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="a152c-123">Du kan ändra status för jobbet genom att använda funktionerna som är tillgängliga på Åtgärdsfönster.</span><span class="sxs-lookup"><span data-stu-id="a152c-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="a152c-124">Kanban-överföringstavla fortsätter att endast visa ett enskilt jobb under denna tid.</span><span class="sxs-lookup"><span data-stu-id="a152c-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="a152c-125">Du kan uppdatera informationen i listan över jobb manuellt genom att klicka på **Uppdatera** (Shift+F5) på åtgärdsfliken.</span><span class="sxs-lookup"><span data-stu-id="a152c-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="a152c-126">När du har uppdaterat informationen visas de fullständiga resultaten för jobbfiltret igen.</span><span class="sxs-lookup"><span data-stu-id="a152c-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="a152c-127">Jobbstatus och möjliga åtgärder</span><span class="sxs-lookup"><span data-stu-id="a152c-127">Job status and possible actions</span></span>
<span data-ttu-id="a152c-128">Status för valda jobb och status för alla fixerade jobb för händelsekanban avgör om du kan ytterligare bearbeta jobbet.</span><span class="sxs-lookup"><span data-stu-id="a152c-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="a152c-129">Följande tabell visar information om dessa status och uppgifter:</span><span class="sxs-lookup"><span data-stu-id="a152c-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="a152c-130">Status som är tillgängliga för jobb, eller för materialhanteringsenheterna som refereras av jobben.</span><span class="sxs-lookup"><span data-stu-id="a152c-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="a152c-131">Varje uppgift som du kan utföra för jobbet.</span><span class="sxs-lookup"><span data-stu-id="a152c-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="a152c-132">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="a152c-132">Job type</span></span></th>
<th><span data-ttu-id="a152c-133">Jobbstatus eller materialhanteringsenhetstatus</span><span class="sxs-lookup"><span data-stu-id="a152c-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="a152c-134">Uppdatera plocklista</span><span class="sxs-lookup"><span data-stu-id="a152c-134">Update picking list</span></span></th>
<th><span data-ttu-id="a152c-135">Starta</span><span class="sxs-lookup"><span data-stu-id="a152c-135">Start</span></span></th>
<th><span data-ttu-id="a152c-136">Uppdatera registrering</span><span class="sxs-lookup"><span data-stu-id="a152c-136">Update registration</span></span></th>
<th><span data-ttu-id="a152c-137">Slutförd</span><span class="sxs-lookup"><span data-stu-id="a152c-137">Complete</span></span></th>
<th><span data-ttu-id="a152c-138">Tom</span><span class="sxs-lookup"><span data-stu-id="a152c-138">Empty</span></span></th>
<th><span data-ttu-id="a152c-139">Skapa händelse-kanban</span><span class="sxs-lookup"><span data-stu-id="a152c-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a152c-140">Överför</span><span class="sxs-lookup"><span data-stu-id="a152c-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a152c-141">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="a152c-141">Not planned</span></span></li>
<li><span data-ttu-id="a152c-142">Inga fixerade jobb eller fixerade jobb är slutförda</span><span class="sxs-lookup"><span data-stu-id="a152c-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a152c-143">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-143">Yes</span></span></td>
<td><span data-ttu-id="a152c-144">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-144">Yes</span></span></td>
<td><span data-ttu-id="a152c-145">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-145">Yes</span></span></td>
<td><span data-ttu-id="a152c-146">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-146">Yes</span></span></td>
<td><span data-ttu-id="a152c-147">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-147">No</span></span></td>
<td><span data-ttu-id="a152c-148">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a152c-149">Överför</span><span class="sxs-lookup"><span data-stu-id="a152c-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a152c-150">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="a152c-150">Not planned</span></span></li>
<li><span data-ttu-id="a152c-151">Det fixerade jobbet är inte avslutat</span><span class="sxs-lookup"><span data-stu-id="a152c-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a152c-152">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-152">Yes</span></span></td>
<td><span data-ttu-id="a152c-153">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-153">No</span></span></td>
<td><span data-ttu-id="a152c-154">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-154">Yes</span></span></td>
<td><span data-ttu-id="a152c-155">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-155">No</span></span></td>
<td><span data-ttu-id="a152c-156">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-156">No</span></span></td>
<td><span data-ttu-id="a152c-157">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a152c-158">Överför</span><span class="sxs-lookup"><span data-stu-id="a152c-158">Transfer</span></span></td>
<td><span data-ttu-id="a152c-159">Pågår</span><span class="sxs-lookup"><span data-stu-id="a152c-159">In progress</span></span></td>
<td><span data-ttu-id="a152c-160">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-160">Yes</span></span></td>
<td><span data-ttu-id="a152c-161">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-161">No</span></span></td>
<td><span data-ttu-id="a152c-162">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-162">Yes</span></span></td>
<td><span data-ttu-id="a152c-163">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-163">Yes</span></span></td>
<td><span data-ttu-id="a152c-164">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-164">No</span></span></td>
<td><span data-ttu-id="a152c-165">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a152c-166">Överför</span><span class="sxs-lookup"><span data-stu-id="a152c-166">Transfer</span></span></td>
<td><span data-ttu-id="a152c-167">Slutförd</span><span class="sxs-lookup"><span data-stu-id="a152c-167">Completed</span></span></td>
<td><span data-ttu-id="a152c-168">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-168">No</span></span></td>
<td><span data-ttu-id="a152c-169">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-169">No</span></span></td>
<td><span data-ttu-id="a152c-170">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-170">No</span></span></td>
<td><span data-ttu-id="a152c-171">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-171">No</span></span></td>
<td><span data-ttu-id="a152c-172">Ja</span><span class="sxs-lookup"><span data-stu-id="a152c-172">Yes</span></span></td>
<td><span data-ttu-id="a152c-173">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a152c-174">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="a152c-174">Transfer or process</span></span></td>
<td><span data-ttu-id="a152c-175">Tom</span><span class="sxs-lookup"><span data-stu-id="a152c-175">Empty</span></span></td>
<td><span data-ttu-id="a152c-176">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-176">No</span></span></td>
<td><span data-ttu-id="a152c-177">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-177">No</span></span></td>
<td><span data-ttu-id="a152c-178">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-178">No</span></span></td>
<td><span data-ttu-id="a152c-179">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-179">No</span></span></td>
<td><span data-ttu-id="a152c-180">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-180">No</span></span></td>
<td><span data-ttu-id="a152c-181">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a152c-182">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="a152c-182">Transfer or process</span></span></td>
<td><span data-ttu-id="a152c-183">Ett kanban-kort hittades inte</span><span class="sxs-lookup"><span data-stu-id="a152c-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="a152c-184">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-184">No</span></span></td>
<td><span data-ttu-id="a152c-185">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-185">No</span></span></td>
<td><span data-ttu-id="a152c-186">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-186">No</span></span></td>
<td><span data-ttu-id="a152c-187">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-187">No</span></span></td>
<td><span data-ttu-id="a152c-188">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-188">No</span></span></td>
<td><span data-ttu-id="a152c-189">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a152c-190">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="a152c-190">Transfer or process</span></span></td>
<td><span data-ttu-id="a152c-191">Ett kanban-kort hittades, men det har tilldelats en kanban</span><span class="sxs-lookup"><span data-stu-id="a152c-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="a152c-192">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-192">No</span></span></td>
<td><span data-ttu-id="a152c-193">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-193">No</span></span></td>
<td><span data-ttu-id="a152c-194">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-194">No</span></span></td>
<td><span data-ttu-id="a152c-195">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-195">No</span></span></td>
<td><span data-ttu-id="a152c-196">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-196">No</span></span></td>
<td><span data-ttu-id="a152c-197">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a152c-198">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="a152c-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="a152c-199">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="a152c-199">Not planned</span></span></li>
<li><span data-ttu-id="a152c-200">Förberedd</span><span class="sxs-lookup"><span data-stu-id="a152c-200">Prepared</span></span></li>
<li><span data-ttu-id="a152c-201">Pågår</span><span class="sxs-lookup"><span data-stu-id="a152c-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="a152c-202">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-202">No</span></span></td>
<td><span data-ttu-id="a152c-203">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-203">No</span></span></td>
<td><span data-ttu-id="a152c-204">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-204">No</span></span></td>
<td><span data-ttu-id="a152c-205">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-205">No</span></span></td>
<td><span data-ttu-id="a152c-206">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-206">No</span></span></td>
<td><span data-ttu-id="a152c-207">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a152c-208">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="a152c-208">Process</span></span></td>
<td><span data-ttu-id="a152c-209">Slutförd</span><span class="sxs-lookup"><span data-stu-id="a152c-209">Completed</span></span></td>
<td><span data-ttu-id="a152c-210">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-210">No</span></span></td>
<td><span data-ttu-id="a152c-211">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-211">No</span></span></td>
<td><span data-ttu-id="a152c-212">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-212">No</span></span></td>
<td><span data-ttu-id="a152c-213">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-213">No</span></span></td>
<td><span data-ttu-id="a152c-214">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-214">No</span></span></td>
<td><span data-ttu-id="a152c-215">Nej</span><span class="sxs-lookup"><span data-stu-id="a152c-215">No</span></span></td>
</tr>
</tbody>
</table>





