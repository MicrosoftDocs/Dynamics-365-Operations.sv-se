---
title: "Konfigurera en manuell uppgift i ett arbetsflöde"
description: "I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för en manuell uppgift."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 09bd86ff7a4aa8ae64cfa4a38fba643f9117d6eb
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="configure-a-manual-task-in-a-workflow"></a><span data-ttu-id="af973-103">Konfigurera en manuell uppgift i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="af973-103">Configure a manual task in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="af973-104">I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för en manuell uppgift.</span><span class="sxs-lookup"><span data-stu-id="af973-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="af973-105">Högerklicka uppgiften och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera en manuell uppgift i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="af973-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="af973-106">Använd sedan följande procedurer när du vill konfigurera egenskaperna för den manuella uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="af973-107">Ange ett namn på uppgiften</span><span class="sxs-lookup"><span data-stu-id="af973-107">Name the task</span></span>
<span data-ttu-id="af973-108">Följ dessa steg när du vill ange ett namn för den manuella uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-108">Follow these steps to enter a name for the manual task.</span></span>

1.  <span data-ttu-id="af973-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="af973-110">I fältet **Namn** anger du ett unikt namn för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="af973-111">Ange en ämnesrad och instruktioner</span><span class="sxs-lookup"><span data-stu-id="af973-111">Enter a subject line and instructions</span></span>
<span data-ttu-id="af973-112">Du måste ange en ämnesrad och instruktioner för användare som är tilldelade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="af973-113">Om du till exempel konfigurerar en uppgift för inköpsrekvisitioner, kan användaren som tilldelats uppgiften se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="af973-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="af973-114">Ämnesraden visas i ett meddelandefält på sidan.</span><span class="sxs-lookup"><span data-stu-id="af973-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="af973-115">Användaren kan sedan klicka på ikonen i meddelandefältet för att visa instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="af973-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="af973-116">Följ dessa steg när du vill ange en ämnesrad och instruktioner.</span><span class="sxs-lookup"><span data-stu-id="af973-116">Follow these steps to enter a subject line and instructions.</span></span>

1.  <span data-ttu-id="af973-117">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-117">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="af973-118">Ange ämnesraden i fältet **Ämne för arbetsartikel**.</span><span class="sxs-lookup"><span data-stu-id="af973-118">In the **Work item subject** field, enter the subject line.</span></span>
3.  <span data-ttu-id="af973-119">Om du vill göra ämnesraden mer personlig kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="af973-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="af973-120">Platshållare ersätts med lämpliga data när ämnesraden visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="af973-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="af973-121">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="af973-121">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="af973-122">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="af973-122">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="af973-123">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="af973-123">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="af973-124">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-124">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="af973-125">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="af973-125">Click **Insert**.</span></span>

4.  <span data-ttu-id="af973-126">Om du vill lägga till översättningar av ämnesraden följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="af973-126">To add translations of the subject line, follow these steps:</span></span>
    1.  <span data-ttu-id="af973-127">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="af973-127">Click **Translations**.</span></span>
    2.  <span data-ttu-id="af973-128">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-128">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="af973-129">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="af973-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="af973-130">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="af973-130">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="af973-131">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.</span><span class="sxs-lookup"><span data-stu-id="af973-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6.  <span data-ttu-id="af973-132">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="af973-132">Click **Close**.</span></span>

5.  <span data-ttu-id="af973-133">I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="af973-133">In the **Work item instructions** field, enter the instructions.</span></span>
6.  <span data-ttu-id="af973-134">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="af973-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="af973-135">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="af973-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="af973-136">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="af973-136">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="af973-137">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="af973-137">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="af973-138">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="af973-138">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="af973-139">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-139">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="af973-140">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="af973-140">Click **Insert**.</span></span>

7.  <span data-ttu-id="af973-141">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="af973-141">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="af973-142">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="af973-142">Click **Translations**.</span></span>
    2.  <span data-ttu-id="af973-143">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-143">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="af973-144">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="af973-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="af973-145">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="af973-145">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="af973-146">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.</span><span class="sxs-lookup"><span data-stu-id="af973-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6.  <span data-ttu-id="af973-147">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="af973-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="af973-148">Tilldela åtgärden</span><span class="sxs-lookup"><span data-stu-id="af973-148">Assign the task</span></span>
<span data-ttu-id="af973-149">Följ dessa steg för att ange vem som ska tilldelas den manuella uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1.  <span data-ttu-id="af973-150">Klicka på **Tilldelning** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-150">In the left pane, click **Assignment**.</span></span>
2.  <span data-ttu-id="af973-151">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.</span><span class="sxs-lookup"><span data-stu-id="af973-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="af973-152">Alternativ</span><span class="sxs-lookup"><span data-stu-id="af973-152">Option</span></span></th>
    <th><span data-ttu-id="af973-153">Användare som tilldelas uppgiften</span><span class="sxs-lookup"><span data-stu-id="af973-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="af973-154">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="af973-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="af973-155">Deltagare</span><span class="sxs-lookup"><span data-stu-id="af973-155">Participant</span></span></td>
    <td><span data-ttu-id="af973-156">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="af973-156">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-157">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>, innan du väljer den grupp- eller rolltyp som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="af973-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="af973-158">Välj den grupp eller roll i listan <strong>Deltagare</strong> som du vill tilldela uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="af973-159">Hierarki</span><span class="sxs-lookup"><span data-stu-id="af973-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="af973-160">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="af973-160">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-161">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill tilldela uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="af973-162">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="af973-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="af973-163">Dessa namn representerar användare som kan tilldelas uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="af973-164">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="af973-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="af973-165">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="af973-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="af973-166">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="af973-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="af973-167">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="af973-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="af973-168">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas uppgiften:</span><span class="sxs-lookup"><span data-stu-id="af973-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="af973-169"><strong>Tilldela samtliga hämtade användare</strong> – Uppgiften tilldelas alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="af973-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="af973-170"><strong>Tilldela endast till senast hämtade användare</strong> – Uppgiften tilldelas endast den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="af973-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="af973-171"><strong>Exkludera användare med följande villkor</strong> – Uppgiften tilldelas inte till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="af973-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="af973-172">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="af973-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="af973-173">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="af973-173">Workflow user</span></span></td>
    <td><span data-ttu-id="af973-174">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="af973-174">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="af973-175">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="af973-176">Användare</span><span class="sxs-lookup"><span data-stu-id="af973-176">User</span></span></td>
    <td><span data-ttu-id="af973-177">Specifika användare av Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="af973-177">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-178">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="af973-179">Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="af973-179">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="af973-180">Markera de användare som ska tilldelas uppgiften och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="af973-181">Kö</span><span class="sxs-lookup"><span data-stu-id="af973-181">Queue</span></span></td>
    <td><span data-ttu-id="af973-182">En arbetsuppgiftskö</span><span class="sxs-lookup"><span data-stu-id="af973-182">A work item queue</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-183">Klicka på fliken <strong>Köbaserad</strong>när du har markerat <strong>Kö</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="af973-184">Följ dessa steg om du vill tilldela uppgiften till en specifik kö:</span><span class="sxs-lookup"><span data-stu-id="af973-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="af973-185">I listan <strong>Kötyp</strong> väljer du <strong>Arbetsuppgiftskö</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="af973-186">Välj kön i listan <strong>Könamn</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="af973-187">Om ett visst villkor ska bestämma vilken kö beslutet har tilldelats, följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="af973-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="af973-188">I listan <strong>Kötyp</strong> väljer du <strong>Villkorsbelagda arbetsuppgiftsköer</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="af973-189">I listan <strong>Könamn</strong> väljer du <strong>Villkorsbaserad kö</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol></li>
    </ol><span data-ttu-id="af973-190">
    <strong>Obs!</strong> Detta alternativ används bara för vissa arbetsflöden, till exempel ärendehantering.</span><span class="sxs-lookup"><span data-stu-id="af973-190">
    <strong>Note:</strong> This option is used for only a few workflows, such as Case management.</span></span></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="af973-191">I fliken **Tidsgräns** i fältet **Tidslängd** anger du hur mycket tid som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="af973-192">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="af973-192">Select one of the following options:</span></span>
    -   <span data-ttu-id="af973-193">**Timmar** – Ange antalet timmar som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="af973-194">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-195">**Dagar** – Ange antalet dagar som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="af973-196">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-197">**Veckor** – Ange antalet veckor som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    -   <span data-ttu-id="af973-198">**Månader –** – Välj dag och vecka då användaren senast måste slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="af973-199">Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="af973-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="af973-200">**År** – Välj dag, vecka och månad då användaren senast måste slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="af973-201">Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="af973-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="af973-202">Om användaren inte slutför uppgiften inom den tilldelade tiden, är uppgiften försenad.</span><span class="sxs-lookup"><span data-stu-id="af973-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="af973-203">En uppgift som försenas eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="af973-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="af973-204">Ange vad som händer när en uppgift är försenad</span><span class="sxs-lookup"><span data-stu-id="af973-204">Specify what happens when the task is overdue</span></span>
<span data-ttu-id="af973-205">Om en användare inte slutför den manuella uppgiften inom den tilldelade tiden, är uppgiften försenad.</span><span class="sxs-lookup"><span data-stu-id="af973-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="af973-206">En uppgift som är försenad kan eskaleras eller automatiskt tilldelas en annan användare.</span><span class="sxs-lookup"><span data-stu-id="af973-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="af973-207">Följ dessa steg för att eskalera uppgiften om den är försenad.</span><span class="sxs-lookup"><span data-stu-id="af973-207">Follow these steps to escalate the task if it's overdue.</span></span>

1.  <span data-ttu-id="af973-208">Klicka på **Eskalering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-208">In the left pane, click **Escalation**.</span></span>
2.  <span data-ttu-id="af973-209">Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="af973-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="af973-210">Systemet tilldelar automatiskt uppgiften till de användare som har listats i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="af973-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="af973-211">Till exempel representerar följande register en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="af973-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="af973-212">Sekvens</span><span class="sxs-lookup"><span data-stu-id="af973-212">Sequence</span></span> | <span data-ttu-id="af973-213">Eskaleringsväg</span><span class="sxs-lookup"><span data-stu-id="af973-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="af973-214">1</span><span class="sxs-lookup"><span data-stu-id="af973-214">1</span></span>        | <span data-ttu-id="af973-215">Tilldela till: Donna</span><span class="sxs-lookup"><span data-stu-id="af973-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="af973-216">2</span><span class="sxs-lookup"><span data-stu-id="af973-216">2</span></span>        | <span data-ttu-id="af973-217">Tilldela till: Erin</span><span class="sxs-lookup"><span data-stu-id="af973-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="af973-218">3</span><span class="sxs-lookup"><span data-stu-id="af973-218">3</span></span>        | <span data-ttu-id="af973-219">Slutlig åtgärd: Avvisa</span><span class="sxs-lookup"><span data-stu-id="af973-219">Final action: Reject</span></span> |

    <span data-ttu-id="af973-220">I detta scenario tilldelar systemet den försenade uppgiften till Donna.</span><span class="sxs-lookup"><span data-stu-id="af973-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="af973-221">Om Donna inte slutför uppgiften inom angiven tidsperiod, tilldelar systemet uppgiften till Erin.</span><span class="sxs-lookup"><span data-stu-id="af973-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="af973-222">Om Erin inte slutför uppgiften inom den tilldelade tiden, avslår systemet dokumentet som skickats in för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="af973-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>
3.  <span data-ttu-id="af973-223">Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="af973-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="af973-224">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.</span><span class="sxs-lookup"><span data-stu-id="af973-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="af973-225">Alternativ</span><span class="sxs-lookup"><span data-stu-id="af973-225">Option</span></span></th>
    <th><span data-ttu-id="af973-226">Användare som uppgiften eskaleras till</span><span class="sxs-lookup"><span data-stu-id="af973-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="af973-227">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="af973-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="af973-228">Hierarki</span><span class="sxs-lookup"><span data-stu-id="af973-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="af973-229">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="af973-229">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-230">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill eskalera uppgiften till.</span><span class="sxs-lookup"><span data-stu-id="af973-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="af973-231">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="af973-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="af973-232">Dessa namn representerar användare som uppgiften kan eskaleras till.</span><span class="sxs-lookup"><span data-stu-id="af973-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="af973-233">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="af973-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="af973-234">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="af973-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="af973-235">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="af973-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="af973-236">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="af973-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="af973-237">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som uppgiften ska eskaleras till:</span><span class="sxs-lookup"><span data-stu-id="af973-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="af973-238"><strong>Tilldela samtliga hämtade användare</strong> – Uppgiften eskaleras till alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="af973-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="af973-239"><strong>Tilldela endast till senast hämtade användare</strong> – Uppgiften eskaleras endast till den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="af973-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="af973-240"><strong>Exkludera användare med följande villkor</strong> – Denna uppgift eskaleras inte till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="af973-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="af973-241">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="af973-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="af973-242">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="af973-242">Workflow user</span></span></td>
    <td><span data-ttu-id="af973-243">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="af973-243">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="af973-244">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="af973-245">Användare</span><span class="sxs-lookup"><span data-stu-id="af973-245">User</span></span></td>
    <td><span data-ttu-id="af973-246">Specifika Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="af973-246">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-247">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="af973-248">Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="af973-248">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="af973-249">Markera de användare som uppgiften ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  <span data-ttu-id="af973-250">I fliken **Tidsgräns** i fältet **Tidslängd** anger du hur mycket tid som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="af973-251">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="af973-251">Select one of the following options:</span></span>
    -   <span data-ttu-id="af973-252">**Timmar** – Ange antalet timmar som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="af973-253">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-254">**Dagar** – Ange antalet dagar som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="af973-255">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-256">**Veckor** – Ange antalet veckor som användaren har på sig att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    -   <span data-ttu-id="af973-257">**Månader –** – Välj dag och vecka då användaren senast måste slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="af973-258">Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="af973-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="af973-259">**År** – Välj dag, vecka och månad då användaren senast måste slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="af973-260">Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="af973-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5.  <span data-ttu-id="af973-261">Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="af973-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="af973-262">Du kan ändra alla användarnas ordningsföljd.</span><span class="sxs-lookup"><span data-stu-id="af973-262">You can change the order of the users.</span></span>
6.  <span data-ttu-id="af973-263">Om användarna i eskaleringsvägen inte slutför uppgiften inom den tillåtna tidsperioden, utförs uppgiften automatiskt i systemet.</span><span class="sxs-lookup"><span data-stu-id="af973-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="af973-264">Om du vill ange den åtgärd som systemet ska vidta, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="af973-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="af973-265">Ange när systemet ska agera automatiskt på uppgiften</span><span class="sxs-lookup"><span data-stu-id="af973-265">Specify when the system automatically acts on the task</span></span>
<span data-ttu-id="af973-266">Du kan konfigurera systemet så att detta automatiskt utför en manuell uppgift när särskilda villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="af973-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="af973-267">Till exempel kräver en uppgift att en medlem av utgiftsrapportavdelningen granskar de kvitton som skickas in tillsammans med en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="af973-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="af973-268">Enligt företagets policy måste denna uppgift utföras om det totala beloppet för utgiftsrapporten är större än 100 USD.</span><span class="sxs-lookup"><span data-stu-id="af973-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="af973-269">I så fall kan du konfigurera systemet för att automatiskt markera uppgiften som **Slutförd** om totalbeloppet är mindre än 100.</span><span class="sxs-lookup"><span data-stu-id="af973-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="af973-270">Följ dessa steg för att ange när systemet vidtar en åtgärd för den manuella uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1.  <span data-ttu-id="af973-271">Klicka på **Automatiska åtgärder** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-271">In the left pane, click **Automatic actions**.</span></span>
2.  <span data-ttu-id="af973-272">Markera kryssrutan **Aktivera automatiska åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="af973-272">Select the **Enable automatic actions** check box.</span></span>
3.  <span data-ttu-id="af973-273">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="af973-273">Click **Add condition**.</span></span>
4.  <span data-ttu-id="af973-274">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="af973-274">Enter a condition.</span></span>
5.  <span data-ttu-id="af973-275">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="af973-275">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="af973-276">Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="af973-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="af973-277">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="af973-277">Click **Test**.</span></span>
    2.  <span data-ttu-id="af973-278">På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.</span><span class="sxs-lookup"><span data-stu-id="af973-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="af973-279">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="af973-279">Click **Test**.</span></span> <span data-ttu-id="af973-280">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="af973-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="af973-281">När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="af973-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7.  <span data-ttu-id="af973-282">I listan **Automatisk slutförandeåtgärd** väljer du den åtgärd som systemet ska vidta för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="af973-283">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="af973-283">Specify when notifications are sent</span></span>
<span data-ttu-id="af973-284">Du kan skicka meddelanden till andra när en manuell uppgift har delegerats, eskalerats, slutförts eller avvisats, eller när en ändring har begärts.</span><span class="sxs-lookup"><span data-stu-id="af973-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="af973-285">Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.</span><span class="sxs-lookup"><span data-stu-id="af973-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1.  <span data-ttu-id="af973-286">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-286">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="af973-287">Markera kryssrutan bredvid händelserna som meddelandena ska skickas för:</span><span class="sxs-lookup"><span data-stu-id="af973-287">Select the check box next to the events that notifications should be sent for:</span></span>
    -   <span data-ttu-id="af973-288">**Delegera** – Den här uppgiften har tilldelats till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="af973-288">**Delegate** – The task has been assigned to another user.</span></span>
    -   <span data-ttu-id="af973-289">**Eskalera** – Den tilldelade användaren har inte slutfört uppgiften inom angiven tid.</span><span class="sxs-lookup"><span data-stu-id="af973-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    -   <span data-ttu-id="af973-290">**Slutför** – Den tilldelade användaren har slutfört uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-290">**Complete** – The assigned user has completed the task.</span></span>
    -   <span data-ttu-id="af973-291">**Avvisa** – Den tilldelade användaren har avvisat dokumentet som skickats in.</span><span class="sxs-lookup"><span data-stu-id="af973-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    -   <span data-ttu-id="af973-292">**Begär ändring** – Den tilldelade användaren har begärt en ändring av dokumentet som skickats in.</span><span class="sxs-lookup"><span data-stu-id="af973-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3.  <span data-ttu-id="af973-293">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="af973-293">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="af973-294">Ange meddelandetexten i textrutan i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="af973-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5.  <span data-ttu-id="af973-295">Om du vill anpassa meddelandet kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="af973-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="af973-296">Platshållare ersätts med lämplig information när meddelandet visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="af973-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="af973-297">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="af973-297">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="af973-298">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="af973-298">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="af973-299">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="af973-299">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="af973-300">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-300">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="af973-301">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="af973-301">Click **Insert**.</span></span>

6.  <span data-ttu-id="af973-302">Om du vill lägga till översättningar av meddelandet följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="af973-302">To add translations of the notification, follow these steps:</span></span>
    1.  <span data-ttu-id="af973-303">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="af973-303">Click **Translations**.</span></span>
    2.  <span data-ttu-id="af973-304">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="af973-304">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="af973-305">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="af973-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="af973-306">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="af973-306">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="af973-307">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 5.</span><span class="sxs-lookup"><span data-stu-id="af973-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6.  <span data-ttu-id="af973-308">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="af973-308">Click **Close**.</span></span>

7.  <span data-ttu-id="af973-309">Ange vem meddelandena ska skickas till i fliken **Mottagare**.</span><span class="sxs-lookup"><span data-stu-id="af973-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="af973-310">I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 8.</span><span class="sxs-lookup"><span data-stu-id="af973-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="af973-311">Alternativ</span><span class="sxs-lookup"><span data-stu-id="af973-311">Option</span></span></th>
    <th><span data-ttu-id="af973-312">Meddelandemottagare</span><span class="sxs-lookup"><span data-stu-id="af973-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="af973-313">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="af973-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="af973-314">Deltagare</span><span class="sxs-lookup"><span data-stu-id="af973-314">Participant</span></span></td>
    <td><span data-ttu-id="af973-315">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="af973-315">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-316">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="af973-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="af973-317">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="af973-318">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="af973-318">Workflow user</span></span></td>
    <td><span data-ttu-id="af973-319">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="af973-319">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="af973-320">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="af973-321">Användare</span><span class="sxs-lookup"><span data-stu-id="af973-321">User</span></span></td>
    <td><span data-ttu-id="af973-322">Specifika Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="af973-322">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="af973-323">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="af973-324">Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="af973-324">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="af973-325">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="af973-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="af973-326">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="af973-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="af973-327">Ange en tidsgräns</span><span class="sxs-lookup"><span data-stu-id="af973-327">Set a time limit</span></span>
<span data-ttu-id="af973-328">Följ dessa steg om den manuella uppgiften måste slutföras inom en viss tid.</span><span class="sxs-lookup"><span data-stu-id="af973-328">Follow these steps if the manual task must be completed in a specific time.</span></span> 

<span data-ttu-id="af973-329">**Obs!** De alternativ som du väljer i denna procedur åsidosätter alternativen som du valde i avsnitten **Tilldelning** och **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="af973-329">**Note:** The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1.  <span data-ttu-id="af973-330">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-330">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="af973-331">Markera kryssrutan **Ange en tidsgräns för arbetsflödeselement**.</span><span class="sxs-lookup"><span data-stu-id="af973-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3.  <span data-ttu-id="af973-332">Ange när uppgiften måste vara slutförd i fältet **Tidslängd**.</span><span class="sxs-lookup"><span data-stu-id="af973-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="af973-333">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="af973-333">Select one of the following options:</span></span>
    -   <span data-ttu-id="af973-334">**Timmar** – Ange det antal timmar inom vilket uppgiften måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="af973-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="af973-335">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-336">**Dagar** – Ange det antal dagar inom vilket uppgiften måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="af973-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="af973-337">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="af973-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="af973-338">**Veckor** – Ange det antal veckor inom vilket uppgiften måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="af973-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    -   <span data-ttu-id="af973-339">**Månader –** – Välj dag och vecka då uppgiften senast måste vara slutförd.</span><span class="sxs-lookup"><span data-stu-id="af973-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="af973-340">Du kanske till exempel vill att uppgiften ska ha slutförts senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="af973-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="af973-341">**År –** – Välj dag, vecka och månad då uppgiften senast måste vara slutförd.</span><span class="sxs-lookup"><span data-stu-id="af973-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="af973-342">Du kanske till exempel vill att uppgiften ska ha slutförts senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="af973-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="af973-343">Om tidsgränsen överskrids, utförs åtgärden automatiskt i systemet.</span><span class="sxs-lookup"><span data-stu-id="af973-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="af973-344">I listan **Åtgärd** väljer du den åtgärd som ska vidtas i systemet.</span><span class="sxs-lookup"><span data-stu-id="af973-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="af973-345">Ange vilka åtgärder som är tillgängliga för användaren</span><span class="sxs-lookup"><span data-stu-id="af973-345">Specify which actions are available to the user</span></span>
<span data-ttu-id="af973-346">När den manuella uppgiften tilldelas en användare, måste användaren vidta åtgärder för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="af973-347">Följ dessa steg för att ange vilka åtgärder som användaren kan vidta för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-347">Follow these steps to specify which actions the user can take on the task.</span></span> <span data-ttu-id="af973-348">**Obs!** Vilka åtgärder som står till buds varierar beroende på hur uppgiften har utformats.</span><span class="sxs-lookup"><span data-stu-id="af973-348">**Note:** The actions that are available vary, depending on the design of the task.</span></span>

1.  <span data-ttu-id="af973-349">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="af973-349">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="af973-350">Markera kryssrutan **Slutförd** om du vill att användaren ska kunna markera uppgiften som **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="af973-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3.  <span data-ttu-id="af973-351">Markera kryssrutan **Avvisa** om du vill att användaren ska kunna avvisa det inskickade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="af973-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4.  <span data-ttu-id="af973-352">Markera kryssrutan **Begär ändring** om du vill att användaren ska kunna begära ändringar av dokumentet som skickats.</span><span class="sxs-lookup"><span data-stu-id="af973-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5.  <span data-ttu-id="af973-353">Markera kryssrutan **Delegera** om du vill att användaren ska kunna tilldela uppgiften till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="af973-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6.  <span data-ttu-id="af973-354">Markera kryssrutan **Överlåt** om du vill att användaren ska kunna överlåta uppgiften till en annan användare i arbetsuppgiftskön.</span><span class="sxs-lookup"><span data-stu-id="af973-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7.  <span data-ttu-id="af973-355">Markera kryssrutan **Frisläpp** om du vill att användaren ska kunna överlåta uppgiften till arbetsuppgiftskön.</span><span class="sxs-lookup"><span data-stu-id="af973-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="af973-356">En annan användare kan sedan slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="af973-356">Another user can then complete the task.</span></span>





