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
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aedfe7ef96d62401b1d0de0f2cd035036c68e51a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007076"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="eb8f7-103">Stöd för kanban-överföringstavla för streckkodsskanner</span><span class="sxs-lookup"><span data-stu-id="eb8f7-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb8f7-104">Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="eb8f7-105">Registreringslägen</span><span class="sxs-lookup"><span data-stu-id="eb8f7-105">Registration modes</span></span>
------------------

<span data-ttu-id="eb8f7-106">På snabbfliken **Skannerregistrering** kan du välja det registreringsläge som styr åtgärden när du skannar ett kanban-kortnummer eller skriver in numret manuellt numret i fältet för kanban-kortnumret.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="eb8f7-107">Ange registreringsläge</span><span class="sxs-lookup"><span data-stu-id="eb8f7-107">Set registration mode</span></span> | <span data-ttu-id="eb8f7-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="eb8f7-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="eb8f7-109">Starta</span><span class="sxs-lookup"><span data-stu-id="eb8f7-109">Start</span></span>                 | <span data-ttu-id="eb8f7-110">Registrera ett kanban-överföringsjobb som pågående.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="eb8f7-111">Slutförd</span><span class="sxs-lookup"><span data-stu-id="eb8f7-111">Complete</span></span>              | <span data-ttu-id="eb8f7-112">Registrera ett kanban-överföringsjobb som slutfört.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="eb8f7-113">Tom</span><span class="sxs-lookup"><span data-stu-id="eb8f7-113">Empty</span></span>                 | <span data-ttu-id="eb8f7-114">Registrera den materialhanteringsenhet som refereras av kanban-kortet som tomt.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="eb8f7-115">Välj</span><span class="sxs-lookup"><span data-stu-id="eb8f7-115">Select</span></span>                | <span data-ttu-id="eb8f7-116">Registrera ett kanban-kortnummer och välj automatiskt det jobb som refereras i kanban-listan</span><span class="sxs-lookup"><span data-stu-id="eb8f7-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="eb8f7-117">Registreringsläge Välj</span><span class="sxs-lookup"><span data-stu-id="eb8f7-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="eb8f7-118">När du använder en streckkodsläsare för att välja ett jobb, ändras visningsläget på kanban-tavlan.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="eb8f7-119">I detta läge gäller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="eb8f7-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="eb8f7-120">Endast skannade kanban-jobb visas.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="eb8f7-121">Information om det utvalda jobbet visas på snabbfliken **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="eb8f7-122">Snabbfliken **Meddelanden** visas bara för det valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="eb8f7-123">Du kan ändra status för jobbet genom att använda funktionerna som är tillgängliga på Åtgärdsfönster.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="eb8f7-124">Kanban-överföringstavla fortsätter att endast visa ett enskilt jobb under denna tid.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="eb8f7-125">Du kan uppdatera informationen i listan över jobb manuellt genom att klicka på **Uppdatera** (Shift+F5) på åtgärdsfliken.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="eb8f7-126">När du har uppdaterat informationen visas de fullständiga resultaten för jobbfiltret igen.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="eb8f7-127">Jobbstatus och möjliga åtgärder</span><span class="sxs-lookup"><span data-stu-id="eb8f7-127">Job status and possible actions</span></span>
<span data-ttu-id="eb8f7-128">Status för valda jobb och status för alla fixerade jobb för händelsekanban avgör om du kan ytterligare bearbeta jobbet.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="eb8f7-129">Följande tabell visar information om dessa status och uppgifter:</span><span class="sxs-lookup"><span data-stu-id="eb8f7-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="eb8f7-130">Status som är tillgängliga för jobb, eller för materialhanteringsenheterna som refereras av jobben.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="eb8f7-131">Varje uppgift som du kan utföra för jobbet.</span><span class="sxs-lookup"><span data-stu-id="eb8f7-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="eb8f7-132">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="eb8f7-132">Job type</span></span></th>
<th><span data-ttu-id="eb8f7-133">Jobbstatus eller materialhanteringsenhetstatus</span><span class="sxs-lookup"><span data-stu-id="eb8f7-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="eb8f7-134">Uppdatera plocklista</span><span class="sxs-lookup"><span data-stu-id="eb8f7-134">Update picking list</span></span></th>
<th><span data-ttu-id="eb8f7-135">Starta</span><span class="sxs-lookup"><span data-stu-id="eb8f7-135">Start</span></span></th>
<th><span data-ttu-id="eb8f7-136">Uppdatera registrering</span><span class="sxs-lookup"><span data-stu-id="eb8f7-136">Update registration</span></span></th>
<th><span data-ttu-id="eb8f7-137">Slutförd</span><span class="sxs-lookup"><span data-stu-id="eb8f7-137">Complete</span></span></th>
<th><span data-ttu-id="eb8f7-138">Tom</span><span class="sxs-lookup"><span data-stu-id="eb8f7-138">Empty</span></span></th>
<th><span data-ttu-id="eb8f7-139">Skapa händelse-kanban</span><span class="sxs-lookup"><span data-stu-id="eb8f7-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eb8f7-140">Överför</span><span class="sxs-lookup"><span data-stu-id="eb8f7-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="eb8f7-141">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="eb8f7-141">Not planned</span></span></li>
<li><span data-ttu-id="eb8f7-142">Inga fixerade jobb eller fixerade jobb är slutförda</span><span class="sxs-lookup"><span data-stu-id="eb8f7-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="eb8f7-143">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-143">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-144">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-144">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-145">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-145">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-146">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-146">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-147">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-147">No</span></span></td>
<td><span data-ttu-id="eb8f7-148">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb8f7-149">Överför</span><span class="sxs-lookup"><span data-stu-id="eb8f7-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="eb8f7-150">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="eb8f7-150">Not planned</span></span></li>
<li><span data-ttu-id="eb8f7-151">Det fixerade jobbet är inte avslutat</span><span class="sxs-lookup"><span data-stu-id="eb8f7-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="eb8f7-152">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-152">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-153">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-153">No</span></span></td>
<td><span data-ttu-id="eb8f7-154">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-154">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-155">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-155">No</span></span></td>
<td><span data-ttu-id="eb8f7-156">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-156">No</span></span></td>
<td><span data-ttu-id="eb8f7-157">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb8f7-158">Överför</span><span class="sxs-lookup"><span data-stu-id="eb8f7-158">Transfer</span></span></td>
<td><span data-ttu-id="eb8f7-159">Pågår</span><span class="sxs-lookup"><span data-stu-id="eb8f7-159">In progress</span></span></td>
<td><span data-ttu-id="eb8f7-160">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-160">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-161">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-161">No</span></span></td>
<td><span data-ttu-id="eb8f7-162">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-162">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-163">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-163">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-164">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-164">No</span></span></td>
<td><span data-ttu-id="eb8f7-165">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb8f7-166">Överför</span><span class="sxs-lookup"><span data-stu-id="eb8f7-166">Transfer</span></span></td>
<td><span data-ttu-id="eb8f7-167">Slutförd</span><span class="sxs-lookup"><span data-stu-id="eb8f7-167">Completed</span></span></td>
<td><span data-ttu-id="eb8f7-168">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-168">No</span></span></td>
<td><span data-ttu-id="eb8f7-169">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-169">No</span></span></td>
<td><span data-ttu-id="eb8f7-170">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-170">No</span></span></td>
<td><span data-ttu-id="eb8f7-171">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-171">No</span></span></td>
<td><span data-ttu-id="eb8f7-172">Ja</span><span class="sxs-lookup"><span data-stu-id="eb8f7-172">Yes</span></span></td>
<td><span data-ttu-id="eb8f7-173">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb8f7-174">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="eb8f7-174">Transfer or process</span></span></td>
<td><span data-ttu-id="eb8f7-175">Tom</span><span class="sxs-lookup"><span data-stu-id="eb8f7-175">Empty</span></span></td>
<td><span data-ttu-id="eb8f7-176">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-176">No</span></span></td>
<td><span data-ttu-id="eb8f7-177">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-177">No</span></span></td>
<td><span data-ttu-id="eb8f7-178">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-178">No</span></span></td>
<td><span data-ttu-id="eb8f7-179">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-179">No</span></span></td>
<td><span data-ttu-id="eb8f7-180">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-180">No</span></span></td>
<td><span data-ttu-id="eb8f7-181">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb8f7-182">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="eb8f7-182">Transfer or process</span></span></td>
<td><span data-ttu-id="eb8f7-183">Ett kanban-kort hittades inte</span><span class="sxs-lookup"><span data-stu-id="eb8f7-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="eb8f7-184">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-184">No</span></span></td>
<td><span data-ttu-id="eb8f7-185">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-185">No</span></span></td>
<td><span data-ttu-id="eb8f7-186">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-186">No</span></span></td>
<td><span data-ttu-id="eb8f7-187">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-187">No</span></span></td>
<td><span data-ttu-id="eb8f7-188">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-188">No</span></span></td>
<td><span data-ttu-id="eb8f7-189">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb8f7-190">Överföring eller process</span><span class="sxs-lookup"><span data-stu-id="eb8f7-190">Transfer or process</span></span></td>
<td><span data-ttu-id="eb8f7-191">Ett kanban-kort hittades, men det har tilldelats en kanban</span><span class="sxs-lookup"><span data-stu-id="eb8f7-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="eb8f7-192">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-192">No</span></span></td>
<td><span data-ttu-id="eb8f7-193">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-193">No</span></span></td>
<td><span data-ttu-id="eb8f7-194">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-194">No</span></span></td>
<td><span data-ttu-id="eb8f7-195">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-195">No</span></span></td>
<td><span data-ttu-id="eb8f7-196">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-196">No</span></span></td>
<td><span data-ttu-id="eb8f7-197">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb8f7-198">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="eb8f7-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="eb8f7-199">Inte planerad</span><span class="sxs-lookup"><span data-stu-id="eb8f7-199">Not planned</span></span></li>
<li><span data-ttu-id="eb8f7-200">Förberedd</span><span class="sxs-lookup"><span data-stu-id="eb8f7-200">Prepared</span></span></li>
<li><span data-ttu-id="eb8f7-201">Pågår</span><span class="sxs-lookup"><span data-stu-id="eb8f7-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="eb8f7-202">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-202">No</span></span></td>
<td><span data-ttu-id="eb8f7-203">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-203">No</span></span></td>
<td><span data-ttu-id="eb8f7-204">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-204">No</span></span></td>
<td><span data-ttu-id="eb8f7-205">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-205">No</span></span></td>
<td><span data-ttu-id="eb8f7-206">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-206">No</span></span></td>
<td><span data-ttu-id="eb8f7-207">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb8f7-208">Bearbeta</span><span class="sxs-lookup"><span data-stu-id="eb8f7-208">Process</span></span></td>
<td><span data-ttu-id="eb8f7-209">Slutförd</span><span class="sxs-lookup"><span data-stu-id="eb8f7-209">Completed</span></span></td>
<td><span data-ttu-id="eb8f7-210">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-210">No</span></span></td>
<td><span data-ttu-id="eb8f7-211">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-211">No</span></span></td>
<td><span data-ttu-id="eb8f7-212">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-212">No</span></span></td>
<td><span data-ttu-id="eb8f7-213">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-213">No</span></span></td>
<td><span data-ttu-id="eb8f7-214">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-214">No</span></span></td>
<td><span data-ttu-id="eb8f7-215">Nej</span><span class="sxs-lookup"><span data-stu-id="eb8f7-215">No</span></span></td>
</tr>
</tbody>
</table>





