---
title: Konfigurera godkännandesteg i ett arbetsflöde
description: I det här avsnittet beskrivs hur du konfigurerar egenskaperna för ett godkännandesteg.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5bd5300a061e12ccabdea83c20863c95e15fe19
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124691"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="77266-103">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="77266-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77266-104">I det här avsnittet beskrivs hur du konfigurerar egenskaperna för ett godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="77266-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="77266-105">Högerklicka på godkännandesteget och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**, om du vill konfigurera ett godkännandesteg i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="77266-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="77266-106">Använd sedan följande procedurer när du vill konfigurera egenskaperna för godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="77266-107">Ange ett namn på steget</span><span class="sxs-lookup"><span data-stu-id="77266-107">Name the step</span></span>
<span data-ttu-id="77266-108">Följ dessa steg när du vill ange ett namn för godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="77266-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="77266-110">Ange ett unikt namn för godkännandesteget i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="77266-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="77266-111">Ange en ämnesrad och instruktioner</span><span class="sxs-lookup"><span data-stu-id="77266-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="77266-112">Du måste ange en ämnesrad och instruktioner för användare som har tilldelats godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="77266-113">Om du till exempel konfigurerar ett godkännandesteg för inköpsrekvisitioner kan användaren som tilldelats steget se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="77266-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="77266-114">Ämnesraden visas i ett meddelandefält på sidan.</span><span class="sxs-lookup"><span data-stu-id="77266-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="77266-115">Användaren kan sedan klicka på ikonen i meddelandefältet för att läsa instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="77266-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="77266-116">Följ dessa steg när du vill ange en ämnesrad och instruktioner.</span><span class="sxs-lookup"><span data-stu-id="77266-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="77266-117">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="77266-118">Ange ämnesraden i fältet **Ämne för arbetsartikel**.</span><span class="sxs-lookup"><span data-stu-id="77266-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="77266-119">Om du vill göra ämnesraden mer personlig kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="77266-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="77266-120">Platshållare ersätts med lämpliga data när ämnesraden visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="77266-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="77266-121">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="77266-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="77266-122">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="77266-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="77266-123">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="77266-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="77266-124">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="77266-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="77266-125">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="77266-125">Click **Insert**.</span></span>

4. <span data-ttu-id="77266-126">Om du vill lägga till översättningar av ämnesraden följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="77266-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="77266-127">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="77266-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="77266-128">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="77266-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="77266-129">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="77266-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="77266-130">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="77266-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="77266-131">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.</span><span class="sxs-lookup"><span data-stu-id="77266-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="77266-132">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="77266-132">Click **Close**.</span></span>

5. <span data-ttu-id="77266-133">I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="77266-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="77266-134">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="77266-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="77266-135">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="77266-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="77266-136">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="77266-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="77266-137">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="77266-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="77266-138">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="77266-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="77266-139">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="77266-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="77266-140">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="77266-140">Click **Insert**.</span></span>

7. <span data-ttu-id="77266-141">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="77266-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="77266-142">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="77266-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="77266-143">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="77266-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="77266-144">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="77266-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="77266-145">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="77266-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="77266-146">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.</span><span class="sxs-lookup"><span data-stu-id="77266-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="77266-147">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="77266-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="77266-148">Tilldela godkännandesteget</span><span class="sxs-lookup"><span data-stu-id="77266-148">Assign the approval step</span></span>

<span data-ttu-id="77266-149">Gör på följande sätt när du vill ange vem som ska tilldelas godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="77266-150">Klicka på **Tilldelning** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="77266-151">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.</span><span class="sxs-lookup"><span data-stu-id="77266-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="77266-152">Alternativ</span><span class="sxs-lookup"><span data-stu-id="77266-152">Option</span></span></th>
    <th><span data-ttu-id="77266-153">Användare som tilldelas godkännandesteget</span><span class="sxs-lookup"><span data-stu-id="77266-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="77266-154">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="77266-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="77266-155">Deltagare</span><span class="sxs-lookup"><span data-stu-id="77266-155">Participant</span></span></td>
    <td><span data-ttu-id="77266-156">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="77266-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="77266-157">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="77266-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="77266-158">Välj den grupp eller roll i listan <strong>Deltagare</strong> som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="77266-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="77266-159">Hierarki</span><span class="sxs-lookup"><span data-stu-id="77266-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="77266-160">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="77266-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="77266-161">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="77266-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="77266-162">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="77266-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="77266-163">Dessa namn representerar användare som kan tilldelas steget.</span><span class="sxs-lookup"><span data-stu-id="77266-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="77266-164">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="77266-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="77266-165">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="77266-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="77266-166">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="77266-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="77266-167">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="77266-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="77266-168">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas steget:</span><span class="sxs-lookup"><span data-stu-id="77266-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="77266-169"><strong>Tilldela samtliga hämtade användare</strong> – Steget tilldelas alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="77266-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="77266-170"><strong>Tilldela endast till senast hämtade användare</strong> – Steget tilldelas endast den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="77266-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="77266-171"><strong>Exkludera användare med följande villkor</strong> – Steget har inte tilldelats till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="77266-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="77266-172">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="77266-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="77266-173">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="77266-173">Workflow user</span></span></td>
    <td><span data-ttu-id="77266-174">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="77266-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="77266-175">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="77266-176">Användare</span><span class="sxs-lookup"><span data-stu-id="77266-176">User</span></span></td>
    <td><span data-ttu-id="77266-177">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="77266-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="77266-178">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="77266-179">Listan <strong>Tillgängliga användare</strong> innehåller alla systemanvändare.</span><span class="sxs-lookup"><span data-stu-id="77266-179">The <strong>Available users</strong> list includes all system users.</span></span> <span data-ttu-id="77266-180">Markera de användare som ska tilldelas steget och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="77266-181">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="77266-182">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="77266-182">Select one of the following options:</span></span>

    - <span data-ttu-id="77266-183">**Timmar** – Ange antalet timmar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="77266-184">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="77266-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="77266-185">**Dagar** – Ange antalet dagar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="77266-186">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="77266-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="77266-187">**Veckor** – Ange antalet veckor som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="77266-188">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="77266-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="77266-189">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="77266-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="77266-190">**År** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="77266-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="77266-191">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="77266-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="77266-192">Om användaren inte vidtar åtgärder för dokumentet inom den tilldelade tiden, är dokumentet försenat.</span><span class="sxs-lookup"><span data-stu-id="77266-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="77266-193">Ett dokument som försenas eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="77266-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="77266-194">Om du har tilldelat godkännandesteget till flera användare eller grupper av användare, välj då ett av följande alternativ i fliken **Slutförandepolicy**:</span><span class="sxs-lookup"><span data-stu-id="77266-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="77266-195">**Enskild godkännare** – Den åtgärd som tillämpas på dokumentet avgörs av den första personen som svarar.</span><span class="sxs-lookup"><span data-stu-id="77266-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="77266-196">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="77266-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="77266-197">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="77266-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="77266-198">Om Sue är den första personen som svarar på dokumentet, är det hon som bestämmer vilken åtgärd som ska vidtas.</span><span class="sxs-lookup"><span data-stu-id="77266-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="77266-199">Om Sue avvisar dokumentet, avslås det och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="77266-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="77266-200">Om Sue godkänner dokumentet, skickas det vidare till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="77266-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Arbetsflöde med en godkännandeprocess](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="77266-202">**Majoritet av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när majoriteten av godkännarna har svarat.</span><span class="sxs-lookup"><span data-stu-id="77266-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="77266-203">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="77266-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="77266-204">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="77266-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="77266-205">Om Sue och Jo är de första två godkännarna som svarar, tillämpas den åtgärd de vidtar på dokumentet.</span><span class="sxs-lookup"><span data-stu-id="77266-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="77266-206">Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="77266-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="77266-207">Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="77266-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="77266-208">**Procent av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när en viss procent av godkännarna har svarat.</span><span class="sxs-lookup"><span data-stu-id="77266-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="77266-209">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="77266-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="77266-210">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill, och du har angett **50** som procentandel.</span><span class="sxs-lookup"><span data-stu-id="77266-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="77266-211">Om Sue och Jo och är de två första godkännarna som svarar, används den åtgärd som de vidtar på dokumentet eftersom de uppfyller kravet på 50 procent av godkännarna.</span><span class="sxs-lookup"><span data-stu-id="77266-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="77266-212">Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="77266-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="77266-213">Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="77266-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="77266-214">**Alla godkännare** – Alla godkännare måste godkänna dokumentet.</span><span class="sxs-lookup"><span data-stu-id="77266-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="77266-215">I annat fall kan inte arbetsflödet fortsätta.</span><span class="sxs-lookup"><span data-stu-id="77266-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="77266-216">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="77266-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="77266-217">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="77266-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="77266-218">Om Sue och Jo godkänner dokumentet men Bill avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="77266-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="77266-219">Om Sue, Jo och Bill alla godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="77266-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="77266-220">Ange när godkännandesteget krävs</span><span class="sxs-lookup"><span data-stu-id="77266-220">Specify when the approval step is required</span></span>

<span data-ttu-id="77266-221">Du kan ange när godkännandesteget krävs.</span><span class="sxs-lookup"><span data-stu-id="77266-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="77266-222">Godkännandesteget kan alltid krävas, eller också kan det krävas endast om specifika villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="77266-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="77266-223">Godkännandesteget krävs alltid</span><span class="sxs-lookup"><span data-stu-id="77266-223">The approval step is always required</span></span>

<span data-ttu-id="77266-224">Följ dessa steg om godkännandesteget alltid krävs.</span><span class="sxs-lookup"><span data-stu-id="77266-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="77266-225">Klicka på **Villkor** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="77266-226">Välj alternativet **Kör alltid det här steget**.</span><span class="sxs-lookup"><span data-stu-id="77266-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="77266-227">Godkännandesteget krävs under vissa förhållanden</span><span class="sxs-lookup"><span data-stu-id="77266-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="77266-228">Godkännandesteget som du konfigurerar kanske endast krävs då specifika villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="77266-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="77266-229">Om du till exempel konfigurerar ett godkännandesteg för ett inköpsrekvisitionsarbetsflöde, kan du tillämpa att godkännandesteget endast inträffar om inköpsrekvisitionens belopp överstiger 10 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="77266-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="77266-230">Följ dessa steg för att ange när godkännandesteget krävs.</span><span class="sxs-lookup"><span data-stu-id="77266-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="77266-231">Klicka på **Villkor** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="77266-232">Välj alternativet **Kör bara det här steget när följande villkor uppfylls**.</span><span class="sxs-lookup"><span data-stu-id="77266-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="77266-233">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="77266-233">Enter a condition.</span></span>
4. <span data-ttu-id="77266-234">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="77266-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="77266-235">Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="77266-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="77266-236">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="77266-236">Click **Test**.</span></span>
    2. <span data-ttu-id="77266-237">På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.</span><span class="sxs-lookup"><span data-stu-id="77266-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="77266-238">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="77266-238">Click **Test**.</span></span> <span data-ttu-id="77266-239">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="77266-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="77266-240">När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="77266-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="77266-241">Ange vad som ska hända när dokumentet är försenat</span><span class="sxs-lookup"><span data-stu-id="77266-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="77266-242">Om en användare inte vidtar åtgärder för ett dokument inom den tilldelade tiden, är dokumentet försenat.</span><span class="sxs-lookup"><span data-stu-id="77266-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="77266-243">Ett dokument som är försenat kan eskaleras eller automatiskt tilldelas till en annan användare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="77266-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="77266-244">Följ dessa steg för att eskalera dokumentet om det är försenat.</span><span class="sxs-lookup"><span data-stu-id="77266-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="77266-245">Klicka på **Eskalering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="77266-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="77266-246">Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="77266-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="77266-247">Systemet tilldelar automatiskt dokumentet till de användare som listats i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="77266-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="77266-248">Till exempel representerar följande register en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="77266-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="77266-249">Sekvens</span><span class="sxs-lookup"><span data-stu-id="77266-249">Sequence</span></span> | <span data-ttu-id="77266-250">Eskaleringsväg</span><span class="sxs-lookup"><span data-stu-id="77266-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="77266-251">1</span><span class="sxs-lookup"><span data-stu-id="77266-251">1</span></span>        | <span data-ttu-id="77266-252">Tilldela till: Donna</span><span class="sxs-lookup"><span data-stu-id="77266-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="77266-253">2</span><span class="sxs-lookup"><span data-stu-id="77266-253">2</span></span>        | <span data-ttu-id="77266-254">Tilldela till: Erin</span><span class="sxs-lookup"><span data-stu-id="77266-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="77266-255">3</span><span class="sxs-lookup"><span data-stu-id="77266-255">3</span></span>        | <span data-ttu-id="77266-256">Slutlig åtgärd: Avvisa</span><span class="sxs-lookup"><span data-stu-id="77266-256">Final action: Reject</span></span> |

    <span data-ttu-id="77266-257">I detta scenario tilldelar systemet det försenade dokumentet till Donna.</span><span class="sxs-lookup"><span data-stu-id="77266-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="77266-258">Om Donna inte svarar inom angiven tidsperiod, tilldelar systemet dokumentet till Erin.</span><span class="sxs-lookup"><span data-stu-id="77266-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="77266-259">Om Erin inte svarar inom angiven tidsperiod, avslår systemet dokumentet.</span><span class="sxs-lookup"><span data-stu-id="77266-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="77266-260">Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="77266-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="77266-261">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.</span><span class="sxs-lookup"><span data-stu-id="77266-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="77266-262">Alternativ</span><span class="sxs-lookup"><span data-stu-id="77266-262">Option</span></span></th>
    <th><span data-ttu-id="77266-263">Användare som dokumentet eskaleras till</span><span class="sxs-lookup"><span data-stu-id="77266-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="77266-264">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="77266-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="77266-265">Hierarki</span><span class="sxs-lookup"><span data-stu-id="77266-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="77266-266">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="77266-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="77266-267">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och därefter den hierarkityp som du vill eskalera dokumentet till.</span><span class="sxs-lookup"><span data-stu-id="77266-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="77266-268">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="77266-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="77266-269">Dessa namn representerar användare som dokumentet kan eskaleras till.</span><span class="sxs-lookup"><span data-stu-id="77266-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="77266-270">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="77266-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="77266-271">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="77266-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="77266-272">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="77266-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="77266-273">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="77266-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="77266-274">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som dokumentet ska eskaleras till:</span><span class="sxs-lookup"><span data-stu-id="77266-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="77266-275"><strong>Tilldela till samtliga hämtade användare</strong> – Dokumentet eskaleras till alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="77266-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="77266-276"><strong>Tilldela endast till senast hämtade användare</strong> – Dokumentet eskaleras endast till den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="77266-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="77266-277"><strong>Exkludera användare med följande villkor</strong> – Dokumentet har inte eskalerats till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="77266-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="77266-278">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="77266-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="77266-279">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="77266-279">Workflow user</span></span></td>
    <td><span data-ttu-id="77266-280">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="77266-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="77266-281">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="77266-282">Användare</span><span class="sxs-lookup"><span data-stu-id="77266-282">User</span></span></td>
    <td><span data-ttu-id="77266-283">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="77266-283">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="77266-284">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="77266-285">Listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="77266-285">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="77266-286">Markera de användare som dokumentet ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="77266-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="77266-287">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="77266-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="77266-288">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="77266-288">Select one of the following options:</span></span>

    - <span data-ttu-id="77266-289">**Timmar** – Ange antalet timmar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="77266-290">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="77266-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="77266-291">**Dagar** – Ange antalet dagar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="77266-292">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="77266-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="77266-293">**Veckor** – Ange antalet veckor som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="77266-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="77266-294">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="77266-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="77266-295">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="77266-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="77266-296">**År** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="77266-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="77266-297">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="77266-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="77266-298">Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="77266-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="77266-299">Du kan ändra alla användarnas ordningsföljd.</span><span class="sxs-lookup"><span data-stu-id="77266-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="77266-300">Om användarna i eskaleringsvägen inte svarar inom den tillåtna tidsperioden, kommer automatiska åtgärder att vidtas för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="77266-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="77266-301">Om du vill ange den åtgärd som systemet ska vidta, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="77266-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
