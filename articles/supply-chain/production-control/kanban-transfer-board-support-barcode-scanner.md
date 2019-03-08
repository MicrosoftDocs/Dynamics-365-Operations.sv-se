---
title: Stöd för kanban-överföringstavla för streckkodsskanner
description: Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "319464"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="70327-103">Stöd för kanban-överföringstavla för streckkodsskanner</span><span class="sxs-lookup"><span data-stu-id="70327-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70327-104">Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="70327-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="70327-105">Registreringslägen</span><span class="sxs-lookup"><span data-stu-id="70327-105">Registration modes</span></span>
------------------

<span data-ttu-id="70327-106">På snabbfliken **Skannerregistrering** kan du välja det registreringsläge som styr åtgärden när du skannar ett kanban-kortnummer eller skriver in numret manuellt numret i fältet för kanban-kortnumret.</span><span class="sxs-lookup"><span data-stu-id="70327-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="70327-107">Ange registreringsläge</span><span class="sxs-lookup"><span data-stu-id="70327-107">Set registration mode</span></span> | <span data-ttu-id="70327-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="70327-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="70327-109">Starta</span><span class="sxs-lookup"><span data-stu-id="70327-109">Start</span></span>                 | <span data-ttu-id="70327-110">Registrera ett kanban-överföringsjobb som pågående.</span><span class="sxs-lookup"><span data-stu-id="70327-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="70327-111">Slutförd</span><span class="sxs-lookup"><span data-stu-id="70327-111">Complete</span></span>              | <span data-ttu-id="70327-112">Registrera ett kanban-överföringsjobb som slutfört.</span><span class="sxs-lookup"><span data-stu-id="70327-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="70327-113">Tom</span><span class="sxs-lookup"><span data-stu-id="70327-113">Empty</span></span>                 | <span data-ttu-id="70327-114">Registrera den materialhanteringsenhet som refereras av kanban-kortet som tomt.</span><span class="sxs-lookup"><span data-stu-id="70327-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="70327-115">Välj</span><span class="sxs-lookup"><span data-stu-id="70327-115">Select</span></span>                | <span data-ttu-id="70327-116">Registrera ett kanban-kortnummer och välj automatiskt det jobb som refereras i kanban-listan</span><span class="sxs-lookup"><span data-stu-id="70327-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="70327-117">Registreringsläge Välj</span><span class="sxs-lookup"><span data-stu-id="70327-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="70327-118">När du använder en streckkodsläsare för att välja ett jobb, ändras visningsläget på kanban-tavlan.</span><span class="sxs-lookup"><span data-stu-id="70327-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="70327-119"> I detta läge gäller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="70327-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="70327-120">Endast skannade kanban-jobb visas.</span><span class="sxs-lookup"><span data-stu-id="70327-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="70327-121">Information om det utvalda jobbet visas på snabbfliken **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="70327-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="70327-122">Snabbfliken **Meddelanden** visas bara för det valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="70327-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="70327-123">Du kan ändra status för jobbet genom att använda funktionerna som är tillgängliga på Åtgärdsfönster.</span><span class="sxs-lookup"><span data-stu-id="70327-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="70327-124">Kanban-överföringstavla fortsätter att endast visa ett enskilt jobb under denna tid.</span><span class="sxs-lookup"><span data-stu-id="70327-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="70327-125">Du kan uppdatera informationen i listan över jobb manuellt genom att klicka på **Uppdatera** (Shift+F5) på åtgärdsfliken.</span><span class="sxs-lookup"><span data-stu-id="70327-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="70327-126">När du har uppdaterat informationen visas de fullständiga resultaten för jobbfiltret igen.</span><span class="sxs-lookup"><span data-stu-id="70327-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="70327-127">Jobbstatus och möjliga åtgärder</span><span class="sxs-lookup"><span data-stu-id="70327-127">Job status and possible actions</span></span>
<span data-ttu-id="70327-128">Status för valda jobb och status för alla fixerade jobb för händelsekanban avgör om du kan ytterligare bearbeta jobbet.</span><span class="sxs-lookup"><span data-stu-id="70327-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="70327-129">Följande tabell visar information om dessa status och uppgifter:</span><span class="sxs-lookup"><span data-stu-id="70327-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="70327-130">Status som är tillgängliga för jobb, eller för materialhanteringsenheterna som refereras av jobben.</span><span class="sxs-lookup"><span data-stu-id="70327-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="70327-131">Varje uppgift som du kan utföra för jobbet.</span><span class="sxs-lookup"><span data-stu-id="70327-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="70327-132">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="70327-132">Job type</span></span></th>
<th><span data-ttu-id="70327-133">Jobbstatus eller materialhanteringsenhetstatus</span><span class="sxs-lookup"><span data-stu-id="70327-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="70327-134">Uppdatera plocklista</span><span class="sxs-lookup"><span data-stu-id="70327-134">Update picking list</span></span></th>
<th><span data-ttu-id="70327-135">Starta</span><span class="sxs-lookup"><span data-stu-id="70327-135">Start</span></span></th>
<th><span data-ttu-id="70327-136">Uppdatera registrering</span><span class="sxs-lookup"><span data-stu-id="70327-136">Update registration</span></span></th>
<th><span data-ttu-id="70327-137">Slutförd</span><span class="sxs-lookup"><span data-stu-id="70327-137">Complete</span></span></th>
<th><span data-ttu-id="70327-138">Tom</span><span class="sxs-lookup"><span data-stu-id="70327-138">Empty</span></span></th>
<th><span data-ttu-id="70327-139">Skapa händelse-kanban</span><span class="sxs-lookup"><span data-stu-id="70327-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="70327-140">Överför</span><span class="sxs-lookup"><span data-stu-id="70327-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="70327-141">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="70327-141">Not planned</span></span></li>
<li><span data-ttu-id="70327-142">Inga fixerade jobb eller fixerade jobb är slutförda</span><span class="sxs-lookup"><span data-stu-id="70327-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="70327-143">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-143">Yes</span></span></td>
<td><span data-ttu-id="70327-144">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-144">Yes</span></span></td>
<td><span data-ttu-id="70327-145">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-145">Yes</span></span></td>
<td><span data-ttu-id="70327-146">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-146">Yes</span></span></td>
<td><span data-ttu-id="70327-147">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-147">No</span></span></td>
<td><span data-ttu-id="70327-148">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="70327-149">Överför</span><span class="sxs-lookup"><span data-stu-id="70327-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="70327-150">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="70327-150">Not planned</span></span></li>
<li><span data-ttu-id="70327-151">Det fixerade jobbet är inte avslutat</span><span class="sxs-lookup"><span data-stu-id="70327-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="70327-152">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-152">Yes</span></span></td>
<td><span data-ttu-id="70327-153">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-153">No</span></span></td>
<td><span data-ttu-id="70327-154">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-154">Yes</span></span></td>
<td><span data-ttu-id="70327-155">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-155">No</span></span></td>
<td><span data-ttu-id="70327-156">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-156">No</span></span></td>
<td><span data-ttu-id="70327-157">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="70327-158">Överför</span><span class="sxs-lookup"><span data-stu-id="70327-158">Transfer</span></span></td>
<td><span data-ttu-id="70327-159">Pågår</span><span class="sxs-lookup"><span data-stu-id="70327-159">In progress</span></span></td>
<td><span data-ttu-id="70327-160">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-160">Yes</span></span></td>
<td><span data-ttu-id="70327-161">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-161">No</span></span></td>
<td><span data-ttu-id="70327-162">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-162">Yes</span></span></td>
<td><span data-ttu-id="70327-163">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-163">Yes</span></span></td>
<td><span data-ttu-id="70327-164">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-164">No</span></span></td>
<td><span data-ttu-id="70327-165">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="70327-166">Överför</span><span class="sxs-lookup"><span data-stu-id="70327-166">Transfer</span></span></td>
<td><span data-ttu-id="70327-167">Slutförd</span><span class="sxs-lookup"><span data-stu-id="70327-167">Completed</span></span></td>
<td><span data-ttu-id="70327-168">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-168">No</span></span></td>
<td><span data-ttu-id="70327-169">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-169">No</span></span></td>
<td><span data-ttu-id="70327-170">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-170">No</span></span></td>
<td><span data-ttu-id="70327-171">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-171">No</span></span></td>
<td><span data-ttu-id="70327-172">Ja</span><span class="sxs-lookup"><span data-stu-id="70327-172">Yes</span></span></td>
<td><span data-ttu-id="70327-173">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="70327-174">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="70327-174">Transfer or process</span></span></td>
<td><span data-ttu-id="70327-175">Tom</span><span class="sxs-lookup"><span data-stu-id="70327-175">Empty</span></span></td>
<td><span data-ttu-id="70327-176">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-176">No</span></span></td>
<td><span data-ttu-id="70327-177">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-177">No</span></span></td>
<td><span data-ttu-id="70327-178">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-178">No</span></span></td>
<td><span data-ttu-id="70327-179">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-179">No</span></span></td>
<td><span data-ttu-id="70327-180">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-180">No</span></span></td>
<td><span data-ttu-id="70327-181">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="70327-182">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="70327-182">Transfer or process</span></span></td>
<td><span data-ttu-id="70327-183">Ett kanban-kort hittades inte</span><span class="sxs-lookup"><span data-stu-id="70327-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="70327-184">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-184">No</span></span></td>
<td><span data-ttu-id="70327-185">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-185">No</span></span></td>
<td><span data-ttu-id="70327-186">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-186">No</span></span></td>
<td><span data-ttu-id="70327-187">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-187">No</span></span></td>
<td><span data-ttu-id="70327-188">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-188">No</span></span></td>
<td><span data-ttu-id="70327-189">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="70327-190">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="70327-190">Transfer or process</span></span></td>
<td><span data-ttu-id="70327-191">Ett kanban-kort hittades, men det har tilldelats en kanban</span><span class="sxs-lookup"><span data-stu-id="70327-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="70327-192">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-192">No</span></span></td>
<td><span data-ttu-id="70327-193">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-193">No</span></span></td>
<td><span data-ttu-id="70327-194">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-194">No</span></span></td>
<td><span data-ttu-id="70327-195">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-195">No</span></span></td>
<td><span data-ttu-id="70327-196">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-196">No</span></span></td>
<td><span data-ttu-id="70327-197">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="70327-198">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="70327-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="70327-199">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="70327-199">Not planned</span></span></li>
<li><span data-ttu-id="70327-200">Förberedd</span><span class="sxs-lookup"><span data-stu-id="70327-200">Prepared</span></span></li>
<li><span data-ttu-id="70327-201">Pågår</span><span class="sxs-lookup"><span data-stu-id="70327-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="70327-202">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-202">No</span></span></td>
<td><span data-ttu-id="70327-203">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-203">No</span></span></td>
<td><span data-ttu-id="70327-204">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-204">No</span></span></td>
<td><span data-ttu-id="70327-205">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-205">No</span></span></td>
<td><span data-ttu-id="70327-206">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-206">No</span></span></td>
<td><span data-ttu-id="70327-207">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="70327-208">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="70327-208">Process</span></span></td>
<td><span data-ttu-id="70327-209">Slutförd</span><span class="sxs-lookup"><span data-stu-id="70327-209">Completed</span></span></td>
<td><span data-ttu-id="70327-210">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-210">No</span></span></td>
<td><span data-ttu-id="70327-211">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-211">No</span></span></td>
<td><span data-ttu-id="70327-212">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-212">No</span></span></td>
<td><span data-ttu-id="70327-213">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-213">No</span></span></td>
<td><span data-ttu-id="70327-214">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-214">No</span></span></td>
<td><span data-ttu-id="70327-215">Nej</span><span class="sxs-lookup"><span data-stu-id="70327-215">No</span></span></td>
</tr>
</tbody>
</table>





