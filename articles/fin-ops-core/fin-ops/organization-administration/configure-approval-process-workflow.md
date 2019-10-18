---
title: Konfigurera godkännandeprocesser i ett arbetsflöde
description: Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b09d09464eae932bf9caf4f2ea38cbbb3b4f0162
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190222"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="75a29-103">Konfigurera godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="75a29-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75a29-104">Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="75a29-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="75a29-105">Högerklicka godkännandesteget i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper** om du vill godkänna en godkännandeprocess.</span><span class="sxs-lookup"><span data-stu-id="75a29-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="75a29-106">Namnge godkännandeprocessen</span><span class="sxs-lookup"><span data-stu-id="75a29-106">Name the approval process</span></span>

<span data-ttu-id="75a29-107">Följ dessa steg om du vill ange ett namn för godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="75a29-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="75a29-108">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="75a29-109">Ange ett unikt namn för godkännandeprocessen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="75a29-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="75a29-110">Ange när systemet ska agera automatiskt på dokumentet</span><span class="sxs-lookup"><span data-stu-id="75a29-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="75a29-111">Du kan konfigurera systemet att vidta automatiska åtgärder för dokumentet om vissa villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="75a29-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="75a29-112">Systemet kan till exempel godkänna utgiftsrapporter med totala belopp som understiger 1 000 kronor.</span><span class="sxs-lookup"><span data-stu-id="75a29-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="75a29-113">Följ dessa steg för att ange när systemet vidtar en åtgärd för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="75a29-114">Klicka på **Automatiska åtgärder** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="75a29-115">Markera kryssrutan **Aktivera automatiska åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="75a29-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="75a29-116">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="75a29-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="75a29-117">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="75a29-117">Enter a condition.</span></span>
5. <span data-ttu-id="75a29-118">Ange vid behov ytterligare villkor.</span><span class="sxs-lookup"><span data-stu-id="75a29-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="75a29-119">Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="75a29-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="75a29-120">Klicka på **Testa** för att öppna formuläret **Testa arbetsflödesvillkor**.</span><span class="sxs-lookup"><span data-stu-id="75a29-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="75a29-121">Markera en post i området **Validera villkor** i formuläret.</span><span class="sxs-lookup"><span data-stu-id="75a29-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="75a29-122">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="75a29-122">Click **Test**.</span></span> <span data-ttu-id="75a29-123">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="75a29-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="75a29-124">Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="75a29-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="75a29-125">I listan **Automatisk slutförandeåtgärd** väljer du den åtgärd som systemet ska vidta för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="75a29-126">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="75a29-126">Specify when notifications are sent</span></span>

<span data-ttu-id="75a29-127">Du kan skicka meddelanden till andra när ett dokument har godkänts, avvisats, delegerats eller eskalerats, eller när en ändring har begärts.</span><span class="sxs-lookup"><span data-stu-id="75a29-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="75a29-128">Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.</span><span class="sxs-lookup"><span data-stu-id="75a29-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="75a29-129">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="75a29-130">Markera kryssrutan bredvid händelserna för att skicka meddelanden för:</span><span class="sxs-lookup"><span data-stu-id="75a29-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="75a29-131">**Delegera** – När ett dokument har tilldelats till en annan användare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="75a29-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="75a29-132">**Eskalera** – När den tilldelade användaren inte har agerat på ett dokument vid angiven tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="75a29-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="75a29-133">**Godkänn** – När ett dokument har godkänts.</span><span class="sxs-lookup"><span data-stu-id="75a29-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="75a29-134">**Avvisa** – När ett dokument har avvisats.</span><span class="sxs-lookup"><span data-stu-id="75a29-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="75a29-135">**Begär ändring** – När den tilldelade användaren har begärt en ändring av ett dokument som skickats in.</span><span class="sxs-lookup"><span data-stu-id="75a29-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="75a29-136">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="75a29-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="75a29-137">Klicka på fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="75a29-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="75a29-138">Ange meddelandetexten i textrutan.</span><span class="sxs-lookup"><span data-stu-id="75a29-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="75a29-139">Om du vill göra texten mer personlig kan du även infoga platshållare som ersätts med lämplig information när de visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="75a29-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="75a29-140">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="75a29-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="75a29-141">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="75a29-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="75a29-142">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="75a29-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="75a29-143">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="75a29-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="75a29-144">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="75a29-144">Click **Insert**.</span></span>

7. <span data-ttu-id="75a29-145">Klicka på **Översättningar** för att lägga till översättningar av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="75a29-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="75a29-146">Följ dessa steg i formuläret som visas:</span><span class="sxs-lookup"><span data-stu-id="75a29-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="75a29-147">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="75a29-147">Click **Add**.</span></span>
    2. <span data-ttu-id="75a29-148">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="75a29-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="75a29-149">I textrutan **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="75a29-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="75a29-150">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="75a29-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="75a29-151">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="75a29-151">Click **Close**.</span></span>

8. <span data-ttu-id="75a29-152">Klicka på fliken **Recipient**.</span><span class="sxs-lookup"><span data-stu-id="75a29-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="75a29-153">Ange till vem som meddelandena ska skickas.</span><span class="sxs-lookup"><span data-stu-id="75a29-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="75a29-154">I följande register väljer du ett av alternativen, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 10.</span><span class="sxs-lookup"><span data-stu-id="75a29-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="75a29-155">Alternativ</span><span class="sxs-lookup"><span data-stu-id="75a29-155">Option</span></span></th>
    <th><span data-ttu-id="75a29-156">Meddelandemottagare</span><span class="sxs-lookup"><span data-stu-id="75a29-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="75a29-157">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="75a29-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="75a29-158"><strong>Deltagare</strong></span><span class="sxs-lookup"><span data-stu-id="75a29-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="75a29-159">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="75a29-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="75a29-160">Klicka på fliken <strong>Role based</strong>när du har markerat <strong>Participant</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="75a29-161">Välj den grupp- eller rolltyp som du vill skicka meddelanden till i listan <strong>Typ of participant</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="75a29-162">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="75a29-163"><strong>Användare av arbetsflöde</strong></span><span class="sxs-lookup"><span data-stu-id="75a29-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="75a29-164">Användare som deltar i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="75a29-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="75a29-165">Klicka på fliken <strong>Arbetsflödesanvändar</strong> när du har valt <strong>Arbetsflödesanvändar</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="75a29-166">Välj en användare som deltar i arbetsflödet i listan <strong>Arbetsflödesanvändar</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="75a29-167"><strong>Användare</strong></span><span class="sxs-lookup"><span data-stu-id="75a29-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="75a29-168">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="75a29-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="75a29-169">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="75a29-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="75a29-170">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>:.</span><span class="sxs-lookup"><span data-stu-id="75a29-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="75a29-171">Upprepa stegen 3 till och med 9 för varje enskild händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="75a29-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="75a29-172">Ange den slutliga godkännaren</span><span class="sxs-lookup"><span data-stu-id="75a29-172">Specify a final approver</span></span>

<span data-ttu-id="75a29-173">Du kan eventuellt tilldela en slutlig godkännare för situationer där godkännaren är den person, som skickade in dokumentet för godkännande.</span><span class="sxs-lookup"><span data-stu-id="75a29-173">You may want to designate a final approver for scenarios where the approver is the person who submitted the document for approval.</span></span> <span data-ttu-id="75a29-174">Följ dessa steg för att ange en slutlig godkännare.</span><span class="sxs-lookup"><span data-stu-id="75a29-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="75a29-175">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-175">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="75a29-176">Markera rutan **Använd slutlig godkännare**.</span><span class="sxs-lookup"><span data-stu-id="75a29-176">Select the **Use final approver** check box.</span></span>
3. <span data-ttu-id="75a29-177">I listan ska du välja en användare som slutlig godkännare.</span><span class="sxs-lookup"><span data-stu-id="75a29-177">In the list, select the user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="75a29-178">Ange en tidsgräns</span><span class="sxs-lookup"><span data-stu-id="75a29-178">Set a time limit</span></span>

<span data-ttu-id="75a29-179">Följ dessa steg om den manuella processen måste slutföras inom en viss tid.</span><span class="sxs-lookup"><span data-stu-id="75a29-179">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="75a29-180">De alternativ som du väljer i dessa steg åsidosätter alternativen som du valde i områdena **Assignment** och **Escalation** för respektive godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="75a29-180">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="75a29-181">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-181">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="75a29-182">Markera kryssrutan för **elementet** **Ställ in en tidsgräns för arbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="75a29-182">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="75a29-183">Ange när godkännandeprocessen måste vara slutförd i fältet **Duration**.</span><span class="sxs-lookup"><span data-stu-id="75a29-183">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="75a29-184">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="75a29-184">Select one of the following options:</span></span>

    - <span data-ttu-id="75a29-185">**Timmar** – Ange det antal timmar inom vilket godkännandeprocessen senast måste ha slutförts.</span><span class="sxs-lookup"><span data-stu-id="75a29-185">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="75a29-186">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="75a29-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="75a29-187">**Dagar** – Ange det antal dagar inom vilket godkännandeprocessen senast måste ha slutförts.</span><span class="sxs-lookup"><span data-stu-id="75a29-187">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="75a29-188">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="75a29-188">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="75a29-189">**Weeks** – Ange det antal veckor inom vilket godkännandeprocessen senast måste ha slutförts.</span><span class="sxs-lookup"><span data-stu-id="75a29-189">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="75a29-190">**Months –** – Välj dag och vecka då godkännandeprocessen senast måste vara slutförd.</span><span class="sxs-lookup"><span data-stu-id="75a29-190">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="75a29-191">Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="75a29-191">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="75a29-192">**År** – Välj dag, vecka och månad då godkännandeprocessen senast måste vara slutförd.</span><span class="sxs-lookup"><span data-stu-id="75a29-192">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="75a29-193">Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="75a29-193">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="75a29-194">Om tidsgränsen överskrids, utför systemet åtgärden i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-194">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="75a29-195">I listan **Åtgärd** väljer du den åtgärd som ska vidtas i systemet.</span><span class="sxs-lookup"><span data-stu-id="75a29-195">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="75a29-196">Ange vilka åtgärder som är tillgängliga för användaren</span><span class="sxs-lookup"><span data-stu-id="75a29-196">Specify which actions are available to the user</span></span>

<span data-ttu-id="75a29-197">När ett dokument tilldelas en användare för godkännande, måste användaren vidta åtgärder för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-197">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="75a29-198">Följ dessa steg för att ange vilka åtgärder som användaren kan vidta för det inskickade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-198">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="75a29-199">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="75a29-199">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="75a29-200">Markera kryssrutan **Godkänn** om du vill att användaren ska kunna godkänna dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-200">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="75a29-201">Markera kryssrutan **Avvisa** om du vill att användaren ska kunna avvisa dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-201">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="75a29-202">Markerakrysstura **Begär ändring** om du vill att användaren ska kunna begära ändringar i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="75a29-202">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="75a29-203">Markera kryssrutan **Delegera** om du vill att användaren ska kunna tilldela dokument till andra användare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="75a29-203">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="75a29-204">**Kryssrutan Aktivera åtgärder från arbetslistan i Enterprise Portal** stöds inte längre.</span><span class="sxs-lookup"><span data-stu-id="75a29-204">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="75a29-205">Konfigurera godkännandestegen</span><span class="sxs-lookup"><span data-stu-id="75a29-205">Configure the approval steps</span></span>

<span data-ttu-id="75a29-206">En godkännandeprocess består av godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="75a29-206">An approval process consists of approval steps.</span></span> <span data-ttu-id="75a29-207">Slutför följande procedur för att lägga till steg i godkännandeprocessen och konfigurera stegen.</span><span class="sxs-lookup"><span data-stu-id="75a29-207">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="75a29-208">Dubbelklicka på godkännandeprocessen i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="75a29-208">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="75a29-209">Arbetsflödesredigeraren visar stegen för godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="75a29-209">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="75a29-210">Dra steget från området **Arbetsflödeselement** till arbetsytan för att lägga till ett godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="75a29-210">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="75a29-211">Se [Konfigurera ett godkännandesteg](configure-approval-step-workflow.md) för att konfigurera ett godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="75a29-211">To configure an approval step, see [Configure an approval step](configure-approval-step-workflow.md).</span></span>
