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
ms.openlocfilehash: 8f52b6ffed7c1edb97c7a673cefbc8bf486ba831
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570773"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="9da32-103">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="9da32-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9da32-104">I det här avsnittet beskrivs hur du konfigurerar egenskaperna för ett godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="9da32-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="9da32-105">Högerklicka på godkännandesteget och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**, om du vill konfigurera ett godkännandesteg i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="9da32-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="9da32-106">Använd sedan följande procedurer när du vill konfigurera egenskaperna för godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="9da32-107">Ange ett namn på steget</span><span class="sxs-lookup"><span data-stu-id="9da32-107">Name the step</span></span>
<span data-ttu-id="9da32-108">Följ dessa steg när du vill ange ett namn för godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="9da32-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9da32-110">Ange ett unikt namn för godkännandesteget i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9da32-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="9da32-111">Ange en ämnesrad och instruktioner</span><span class="sxs-lookup"><span data-stu-id="9da32-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="9da32-112">Du måste ange en ämnesrad och instruktioner för användare som har tilldelats godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="9da32-113">Om du till exempel konfigurerar ett godkännandesteg för inköpsrekvisitioner kan användaren som tilldelats steget se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="9da32-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="9da32-114">Ämnesraden visas i ett meddelandefält på sidan.</span><span class="sxs-lookup"><span data-stu-id="9da32-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="9da32-115">Användaren kan sedan klicka på ikonen i meddelandefältet för att läsa instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="9da32-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="9da32-116">Följ dessa steg när du vill ange en ämnesrad och instruktioner.</span><span class="sxs-lookup"><span data-stu-id="9da32-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="9da32-117">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9da32-118">Ange ämnesraden i fältet **Ämne för arbetsartikel**.</span><span class="sxs-lookup"><span data-stu-id="9da32-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="9da32-119">Om du vill göra ämnesraden mer personlig kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="9da32-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="9da32-120">Platshållare ersätts med lämpliga data när ämnesraden visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="9da32-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="9da32-121">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="9da32-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="9da32-122">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="9da32-123">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="9da32-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="9da32-124">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="9da32-125">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="9da32-125">Click **Insert**.</span></span>

4. <span data-ttu-id="9da32-126">Om du vill lägga till översättningar av ämnesraden följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="9da32-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="9da32-127">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="9da32-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="9da32-128">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="9da32-129">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="9da32-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="9da32-130">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="9da32-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="9da32-131">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.</span><span class="sxs-lookup"><span data-stu-id="9da32-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="9da32-132">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9da32-132">Click **Close**.</span></span>

5. <span data-ttu-id="9da32-133">I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="9da32-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="9da32-134">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="9da32-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="9da32-135">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="9da32-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="9da32-136">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="9da32-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="9da32-137">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="9da32-138">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="9da32-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="9da32-139">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="9da32-140">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="9da32-140">Click **Insert**.</span></span>

7. <span data-ttu-id="9da32-141">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="9da32-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="9da32-142">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="9da32-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="9da32-143">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="9da32-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="9da32-144">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="9da32-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="9da32-145">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="9da32-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="9da32-146">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.</span><span class="sxs-lookup"><span data-stu-id="9da32-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="9da32-147">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9da32-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="9da32-148">Tilldela godkännandesteget</span><span class="sxs-lookup"><span data-stu-id="9da32-148">Assign the approval step</span></span>

<span data-ttu-id="9da32-149">Gör på följande sätt när du vill ange vem som ska tilldelas godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="9da32-150">Klicka på **Tilldelning** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="9da32-151">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.</span><span class="sxs-lookup"><span data-stu-id="9da32-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="9da32-152">Alternativ</span><span class="sxs-lookup"><span data-stu-id="9da32-152">Option</span></span></th>
    <th><span data-ttu-id="9da32-153">Användare som tilldelas godkännandesteget</span><span class="sxs-lookup"><span data-stu-id="9da32-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="9da32-154">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="9da32-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="9da32-155">Deltagare</span><span class="sxs-lookup"><span data-stu-id="9da32-155">Participant</span></span></td>
    <td><span data-ttu-id="9da32-156">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="9da32-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9da32-157">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="9da32-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="9da32-158">Välj den grupp eller roll i listan <strong>Deltagare</strong> som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="9da32-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9da32-159">Hierarki</span><span class="sxs-lookup"><span data-stu-id="9da32-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="9da32-160">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="9da32-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9da32-161">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill tilldela steget.</span><span class="sxs-lookup"><span data-stu-id="9da32-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="9da32-162">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="9da32-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="9da32-163">Dessa namn representerar användare som kan tilldelas steget.</span><span class="sxs-lookup"><span data-stu-id="9da32-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="9da32-164">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="9da32-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="9da32-165">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="9da32-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="9da32-166">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="9da32-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="9da32-167">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="9da32-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="9da32-168">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas steget:</span><span class="sxs-lookup"><span data-stu-id="9da32-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="9da32-169"><strong>Tilldela samtliga hämtade användare</strong> – Steget tilldelas alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="9da32-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="9da32-170"><strong>Tilldela endast till senast hämtade användare</strong> – Steget tilldelas endast den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="9da32-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="9da32-171"><strong>Exkludera användare med följande villkor</strong> – Steget har inte tilldelats till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="9da32-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="9da32-172">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="9da32-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9da32-173">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="9da32-173">Workflow user</span></span></td>
    <td><span data-ttu-id="9da32-174">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="9da32-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="9da32-175">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9da32-176">Användare</span><span class="sxs-lookup"><span data-stu-id="9da32-176">User</span></span></td>
    <td><span data-ttu-id="9da32-177">Specifika Microsoft Dynamics 365 for Finance and Operations användare</span><span class="sxs-lookup"><span data-stu-id="9da32-177">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9da32-178">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="9da32-179">Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="9da32-179">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="9da32-180">Markera de användare som ska tilldelas steget och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="9da32-181">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="9da32-182">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="9da32-182">Select one of the following options:</span></span>

    - <span data-ttu-id="9da32-183">**Timmar** – Ange antalet timmar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="9da32-184">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="9da32-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9da32-185">**Dagar** – Ange antalet dagar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="9da32-186">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="9da32-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9da32-187">**Veckor** – Ange antalet veckor som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="9da32-188">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="9da32-189">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="9da32-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="9da32-190">**År** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="9da32-191">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="9da32-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="9da32-192">Om användaren inte vidtar åtgärder för dokumentet inom den tilldelade tiden, är dokumentet försenat.</span><span class="sxs-lookup"><span data-stu-id="9da32-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="9da32-193">Ett dokument som försenas eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="9da32-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="9da32-194">Om du har tilldelat godkännandesteget till flera användare eller grupper av användare, välj då ett av följande alternativ i fliken **Slutförandepolicy**:</span><span class="sxs-lookup"><span data-stu-id="9da32-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="9da32-195">**Enskild godkännare** – Den åtgärd som tillämpas på dokumentet avgörs av den första personen som svarar.</span><span class="sxs-lookup"><span data-stu-id="9da32-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="9da32-196">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="9da32-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9da32-197">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="9da32-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9da32-198">Om Sue är den första personen som svarar på dokumentet, är det hon som bestämmer vilken åtgärd som ska vidtas.</span><span class="sxs-lookup"><span data-stu-id="9da32-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="9da32-199">Om Sue avvisar dokumentet, avslås det och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="9da32-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="9da32-200">Om Sue godkänner dokumentet, skickas det vidare till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9da32-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Arbetsflöde med en godkännandeprocess](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="9da32-202">**Majoritet av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när majoriteten av godkännarna har svarat.</span><span class="sxs-lookup"><span data-stu-id="9da32-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="9da32-203">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="9da32-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9da32-204">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="9da32-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9da32-205">Om Sue och Jo är de första två godkännarna som svarar, tillämpas den åtgärd de vidtar på dokumentet.</span><span class="sxs-lookup"><span data-stu-id="9da32-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="9da32-206">Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="9da32-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="9da32-207">Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9da32-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="9da32-208">**Procent av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när en viss procent av godkännarna har svarat.</span><span class="sxs-lookup"><span data-stu-id="9da32-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="9da32-209">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="9da32-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9da32-210">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill, och du har angett **50** som procentandel.</span><span class="sxs-lookup"><span data-stu-id="9da32-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="9da32-211">Om Sue och Jo och är de två första godkännarna som svarar, används den åtgärd som de vidtar på dokumentet eftersom de uppfyller kravet på 50 procent av godkännarna.</span><span class="sxs-lookup"><span data-stu-id="9da32-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="9da32-212">Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="9da32-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="9da32-213">Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9da32-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="9da32-214">**Alla godkännare** – Alla godkännare måste godkänna dokumentet.</span><span class="sxs-lookup"><span data-stu-id="9da32-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="9da32-215">I annat fall kan inte arbetsflödet fortsätta.</span><span class="sxs-lookup"><span data-stu-id="9da32-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="9da32-216">Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="9da32-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9da32-217">Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill.</span><span class="sxs-lookup"><span data-stu-id="9da32-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9da32-218">Om Sue och Jo godkänner dokumentet men Bill avvisar det, avslås dokumentet och skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="9da32-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="9da32-219">Om Sue, Jo och Bill alla godkänner dokumentet, skickas det till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9da32-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="9da32-220">Ange när godkännandesteget krävs</span><span class="sxs-lookup"><span data-stu-id="9da32-220">Specify when the approval step is required</span></span>

<span data-ttu-id="9da32-221">Du kan ange när godkännandesteget krävs.</span><span class="sxs-lookup"><span data-stu-id="9da32-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="9da32-222">Godkännandesteget kan alltid krävas, eller också kan det krävas endast om specifika villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="9da32-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="9da32-223">Godkännandesteget krävs alltid</span><span class="sxs-lookup"><span data-stu-id="9da32-223">The approval step is always required</span></span>

<span data-ttu-id="9da32-224">Följ dessa steg om godkännandesteget alltid krävs.</span><span class="sxs-lookup"><span data-stu-id="9da32-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="9da32-225">Klicka på **Villkor** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="9da32-226">Välj alternativet **Kör alltid det här steget**.</span><span class="sxs-lookup"><span data-stu-id="9da32-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="9da32-227">Godkännandesteget krävs under vissa förhållanden</span><span class="sxs-lookup"><span data-stu-id="9da32-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="9da32-228">Godkännandesteget som du konfigurerar kanske endast krävs då specifika villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="9da32-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="9da32-229">Om du till exempel konfigurerar ett godkännandesteg för ett inköpsrekvisitionsarbetsflöde, kan du tillämpa att godkännandesteget endast inträffar om inköpsrekvisitionens belopp överstiger 10 000 dollar.</span><span class="sxs-lookup"><span data-stu-id="9da32-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="9da32-230">Följ dessa steg för att ange när godkännandesteget krävs.</span><span class="sxs-lookup"><span data-stu-id="9da32-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="9da32-231">Klicka på **Villkor** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="9da32-232">Välj alternativet **Kör bara det här steget när följande villkor uppfylls**.</span><span class="sxs-lookup"><span data-stu-id="9da32-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="9da32-233">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="9da32-233">Enter a condition.</span></span>
4. <span data-ttu-id="9da32-234">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="9da32-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="9da32-235">Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="9da32-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="9da32-236">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9da32-236">Click **Test**.</span></span>
    2. <span data-ttu-id="9da32-237">På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.</span><span class="sxs-lookup"><span data-stu-id="9da32-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="9da32-238">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9da32-238">Click **Test**.</span></span> <span data-ttu-id="9da32-239">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="9da32-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="9da32-240">När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="9da32-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="9da32-241">Ange vad som ska hända när dokumentet är försenat</span><span class="sxs-lookup"><span data-stu-id="9da32-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="9da32-242">Om en användare inte vidtar åtgärder för ett dokument inom den tilldelade tiden, är dokumentet försenat.</span><span class="sxs-lookup"><span data-stu-id="9da32-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="9da32-243">Ett dokument som är försenat kan eskaleras eller automatiskt tilldelas till en annan användare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9da32-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="9da32-244">Följ dessa steg för att eskalera dokumentet om det är försenat.</span><span class="sxs-lookup"><span data-stu-id="9da32-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="9da32-245">Klicka på **Eskalering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9da32-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="9da32-246">Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="9da32-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="9da32-247">Systemet tilldelar automatiskt dokumentet till de användare som listats i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="9da32-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="9da32-248">Till exempel representerar följande register en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="9da32-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="9da32-249">Sekvens</span><span class="sxs-lookup"><span data-stu-id="9da32-249">Sequence</span></span> | <span data-ttu-id="9da32-250">Eskaleringsväg</span><span class="sxs-lookup"><span data-stu-id="9da32-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="9da32-251">1</span><span class="sxs-lookup"><span data-stu-id="9da32-251">1</span></span>        | <span data-ttu-id="9da32-252">Tilldela till: Donna</span><span class="sxs-lookup"><span data-stu-id="9da32-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="9da32-253">2</span><span class="sxs-lookup"><span data-stu-id="9da32-253">2</span></span>        | <span data-ttu-id="9da32-254">Tilldela till: Erin</span><span class="sxs-lookup"><span data-stu-id="9da32-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="9da32-255">3</span><span class="sxs-lookup"><span data-stu-id="9da32-255">3</span></span>        | <span data-ttu-id="9da32-256">Slutlig åtgärd: Avvisa</span><span class="sxs-lookup"><span data-stu-id="9da32-256">Final action: Reject</span></span> |

    <span data-ttu-id="9da32-257">I detta scenario tilldelar systemet det försenade dokumentet till Donna.</span><span class="sxs-lookup"><span data-stu-id="9da32-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="9da32-258">Om Donna inte svarar inom angiven tidsperiod, tilldelar systemet dokumentet till Erin.</span><span class="sxs-lookup"><span data-stu-id="9da32-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="9da32-259">Om Erin inte svarar inom angiven tidsperiod, avslår systemet dokumentet.</span><span class="sxs-lookup"><span data-stu-id="9da32-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="9da32-260">Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="9da32-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="9da32-261">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.</span><span class="sxs-lookup"><span data-stu-id="9da32-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="9da32-262">Alternativ</span><span class="sxs-lookup"><span data-stu-id="9da32-262">Option</span></span></th>
    <th><span data-ttu-id="9da32-263">Användare som dokumentet eskaleras till</span><span class="sxs-lookup"><span data-stu-id="9da32-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="9da32-264">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="9da32-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="9da32-265">Hierarki</span><span class="sxs-lookup"><span data-stu-id="9da32-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="9da32-266">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="9da32-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9da32-267">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och därefter den hierarkityp som du vill eskalera dokumentet till.</span><span class="sxs-lookup"><span data-stu-id="9da32-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="9da32-268">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="9da32-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="9da32-269">Dessa namn representerar användare som dokumentet kan eskaleras till.</span><span class="sxs-lookup"><span data-stu-id="9da32-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="9da32-270">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="9da32-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="9da32-271">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="9da32-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="9da32-272">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="9da32-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="9da32-273">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="9da32-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="9da32-274">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som dokumentet ska eskaleras till:</span><span class="sxs-lookup"><span data-stu-id="9da32-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="9da32-275"><strong>Tilldela till samtliga hämtade användare</strong> – Dokumentet eskaleras till alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="9da32-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="9da32-276"><strong>Tilldela endast till senast hämtade användare</strong> – Dokumentet eskaleras endast till den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="9da32-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="9da32-277"><strong>Exkludera användare med följande villkor</strong> – Dokumentet har inte eskalerats till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="9da32-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="9da32-278">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="9da32-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9da32-279">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="9da32-279">Workflow user</span></span></td>
    <td><span data-ttu-id="9da32-280">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="9da32-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="9da32-281">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9da32-282">Användare</span><span class="sxs-lookup"><span data-stu-id="9da32-282">User</span></span></td>
    <td><span data-ttu-id="9da32-283">Specifika Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="9da32-283">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9da32-284">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="9da32-285">Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="9da32-285">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="9da32-286">Markera de användare som dokumentet ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da32-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="9da32-287">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget.</span><span class="sxs-lookup"><span data-stu-id="9da32-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="9da32-288">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="9da32-288">Select one of the following options:</span></span>

    - <span data-ttu-id="9da32-289">**Timmar** – Ange antalet timmar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="9da32-290">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="9da32-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9da32-291">**Dagar** – Ange antalet dagar som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="9da32-292">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="9da32-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9da32-293">**Veckor** – Ange antalet veckor som användaren har på sig att svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="9da32-294">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="9da32-295">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="9da32-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="9da32-296">**År** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="9da32-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="9da32-297">Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="9da32-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="9da32-298">Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="9da32-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="9da32-299">Du kan ändra alla användarnas ordningsföljd.</span><span class="sxs-lookup"><span data-stu-id="9da32-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="9da32-300">Om användarna i eskaleringsvägen inte svarar inom den tillåtna tidsperioden, kommer automatiska åtgärder att vidtas för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="9da32-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="9da32-301">Om du vill ange den åtgärd som systemet ska vidta, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="9da32-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
