---
title: Konfigurera manuella beslut i ett arbetsflöde
description: I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett manuellt beslut.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c9cecabb7923e86e8aa09eed7bd3b1ba5ee0bd8
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694871"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="d4acc-103">Konfigurera manuella beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d4acc-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4acc-104">I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett manuellt beslut.</span><span class="sxs-lookup"><span data-stu-id="d4acc-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="d4acc-105">Högerklicka det manuella beslutet och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera ett manuellt beslut i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="d4acc-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="d4acc-106">Använd sedan följande procedurer när du vill konfigurera egenskaperna för det manuella beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="d4acc-107">Namnge beslutet</span><span class="sxs-lookup"><span data-stu-id="d4acc-107">Name the decision</span></span>

<span data-ttu-id="d4acc-108">Följ dessa steg när du vill ange ett namn för det manuella beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="d4acc-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="d4acc-110">Ange ett unikt namn för det manuella beslutet i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="d4acc-111">Ange en ämnesrad och instruktioner</span><span class="sxs-lookup"><span data-stu-id="d4acc-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="d4acc-112">Du måste ange en ämnesrad och instruktioner för användare som är tilldelade det manuella beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="d4acc-113">Om du till exempel konfigurerar ett beslut för inköpsrekvisitioner kan användaren som tilldelats beslutet se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="d4acc-114">Ämnesraden visas i ett meddelandefält på sidan.</span><span class="sxs-lookup"><span data-stu-id="d4acc-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="d4acc-115">Användaren kan sedan klicka på ikonen i meddelandefältet för att visa instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="d4acc-116">Följ dessa steg när du vill ange en ämnesrad och instruktioner.</span><span class="sxs-lookup"><span data-stu-id="d4acc-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="d4acc-117">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="d4acc-118">Ange ämnesraden i fliken **Instruktioner**, i fältet **Arbetsuppgift**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="d4acc-119">Om du vill göra ämnesraden mer personlig kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="d4acc-120">Platshållare ersätts med lämpliga data när ämnesraden visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="d4acc-121">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="d4acc-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="d4acc-122">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="d4acc-123">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="d4acc-124">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="d4acc-125">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-125">Click **Insert**.</span></span>

4. <span data-ttu-id="d4acc-126">Om du vill lägga till översättningar av ämnesraden följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d4acc-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="d4acc-127">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="d4acc-128">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="d4acc-129">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="d4acc-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="d4acc-130">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="d4acc-131">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.</span><span class="sxs-lookup"><span data-stu-id="d4acc-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="d4acc-132">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-132">Click **Close**.</span></span>

5. <span data-ttu-id="d4acc-133">I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="d4acc-134">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="d4acc-135">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="d4acc-136">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="d4acc-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="d4acc-137">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="d4acc-138">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="d4acc-139">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="d4acc-140">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-140">Click **Insert**.</span></span>

7. <span data-ttu-id="d4acc-141">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d4acc-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="d4acc-142">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="d4acc-143">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="d4acc-144">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="d4acc-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="d4acc-145">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="d4acc-146">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.</span><span class="sxs-lookup"><span data-stu-id="d4acc-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="d4acc-147">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="d4acc-148">Ange möjliga resultat av ett beslut</span><span class="sxs-lookup"><span data-stu-id="d4acc-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="d4acc-149">Vanligtvis ställs en fråga till beslutsfattaren när ett dokument tilldelas till en beslutsfattare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="d4acc-150">Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="d4acc-151">Gör på följande sätt när du vill ange möjliga resultat av det manuella beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="d4acc-152">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="d4acc-153">Ange namnet på resultatet eller alternativet i fliken **Resultat**, i fältet **Resultat 1**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="d4acc-154">Följ dessa steg för att lägga till översättningar av resultaten:</span><span class="sxs-lookup"><span data-stu-id="d4acc-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="d4acc-155">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="d4acc-156">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="d4acc-157">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="d4acc-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="d4acc-158">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="d4acc-159">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-159">Click **Close**.</span></span>

4. <span data-ttu-id="d4acc-160">Ange namnet på resultatet eller alternativet i fältet **Resultat 2**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="d4acc-161">Följ dessa steg för att lägga till översättningar av resultaten:</span><span class="sxs-lookup"><span data-stu-id="d4acc-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="d4acc-162">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="d4acc-163">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="d4acc-164">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="d4acc-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="d4acc-165">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="d4acc-166">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="d4acc-167">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="d4acc-167">Specify when notifications are sent</span></span>

<span data-ttu-id="d4acc-168">Du kan skicka meddelanden till andra när ett beslut har fattats, delegerats eller eskalerats.</span><span class="sxs-lookup"><span data-stu-id="d4acc-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="d4acc-169">Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.</span><span class="sxs-lookup"><span data-stu-id="d4acc-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="d4acc-170">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="d4acc-171">Markera kryssrutan bredvid händelserna som meddelandena ska skickas för:</span><span class="sxs-lookup"><span data-stu-id="d4acc-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="d4acc-172">**\[Val 1\]** – Den tilldelade användaren har valt **\[Val 1\]**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="d4acc-173">**\[Val 2\]** – Den tilldelade användaren har valt **\[Val 2\]**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="d4acc-174">**Delegera** – Den tilldelade användaren har delegerat beslutet till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="d4acc-175">**Eskalera** – Den tilldelade användaren har inte fattat beslutet inom angiven tid.</span><span class="sxs-lookup"><span data-stu-id="d4acc-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="d4acc-176">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="d4acc-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="d4acc-177">Ange meddelandetexten i textrutan i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="d4acc-178">Om du vill anpassa meddelandet kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="d4acc-179">Platshållare ersätts med lämpliga data när meddelandet visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="d4acc-180">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="d4acc-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="d4acc-181">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="d4acc-182">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="d4acc-183">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="d4acc-184">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-184">Click **Insert**.</span></span>

6. <span data-ttu-id="d4acc-185">Om du vill lägga till översättningar av meddelandet följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d4acc-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="d4acc-186">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="d4acc-187">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="d4acc-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="d4acc-188">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="d4acc-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="d4acc-189">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="d4acc-190">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 5.</span><span class="sxs-lookup"><span data-stu-id="d4acc-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="d4acc-191">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-191">Click **Close**.</span></span>

7. <span data-ttu-id="d4acc-192">Ange vem meddelandena ska skickas till i fliken **Mottagare**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="d4acc-193">I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 8.</span><span class="sxs-lookup"><span data-stu-id="d4acc-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="d4acc-194">Alternativ</span><span class="sxs-lookup"><span data-stu-id="d4acc-194">Option</span></span></th>
    <th><span data-ttu-id="d4acc-195">Meddelandemottagare</span><span class="sxs-lookup"><span data-stu-id="d4acc-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="d4acc-196">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="d4acc-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="d4acc-197">Deltagare</span><span class="sxs-lookup"><span data-stu-id="d4acc-197">Participant</span></span></td>
    <td><span data-ttu-id="d4acc-198">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="d4acc-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-199">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="d4acc-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="d4acc-200">Välj den grupp som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-201">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d4acc-201">Workflow user</span></span></td>
    <td><span data-ttu-id="d4acc-202">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d4acc-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="d4acc-203">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-204">Användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-204">User</span></span></td>
    <td><span data-ttu-id="d4acc-205">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-206">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="d4acc-207">Listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="d4acc-208">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="d4acc-209">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="d4acc-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="d4acc-210">Tilldela ett beslut</span><span class="sxs-lookup"><span data-stu-id="d4acc-210">Assign a decision</span></span>

<span data-ttu-id="d4acc-211">Följ dessa steg för att ange vem som ska tilldelas ett manuellt beslut.</span><span class="sxs-lookup"><span data-stu-id="d4acc-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="d4acc-212">Klicka på **Tilldelning** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="d4acc-213">I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.</span><span class="sxs-lookup"><span data-stu-id="d4acc-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="d4acc-214">Alternativ</span><span class="sxs-lookup"><span data-stu-id="d4acc-214">Option</span></span></th>
    <th><span data-ttu-id="d4acc-215">Användare som tilldelats beslutet</span><span class="sxs-lookup"><span data-stu-id="d4acc-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="d4acc-216">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="d4acc-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="d4acc-217">Deltagare</span><span class="sxs-lookup"><span data-stu-id="d4acc-217">Participant</span></span></td>
    <td><span data-ttu-id="d4acc-218">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="d4acc-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-219">Välj <strong>Deltagare</strong> och sedan fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> för att välja den typ av grupp eller roll som du vill tilldela beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="d4acc-220">Välj den grupp eller roll som du vill tilldela beslutet i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-221">Hierarki</span><span class="sxs-lookup"><span data-stu-id="d4acc-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="d4acc-222">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="d4acc-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-223">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong>, och sedan väljer den hierarkityp som du vill tilldela beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="d4acc-224">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="d4acc-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="d4acc-225">Dessa namn representerar användare som kan tilldelas beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="d4acc-226">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="d4acc-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="d4acc-227">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="d4acc-228">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="d4acc-229">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="d4acc-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="d4acc-230">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas steget:</span><span class="sxs-lookup"><span data-stu-id="d4acc-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="d4acc-231"><strong>Tilldela samtliga hämtade användare</strong> – Beslutet tilldelas alla användare i spannet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="d4acc-232"><strong>Tilldela endast till senast hämtade användare</strong> – Beslutet tilldelas endast den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="d4acc-233"><strong>Exkludera användare med följande villkor</strong> – Beslutet har inte tilldelats någon användare i spannet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="d4acc-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="d4acc-234">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-235">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d4acc-235">Workflow user</span></span></td>
    <td><span data-ttu-id="d4acc-236">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d4acc-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="d4acc-237">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-238">Användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-238">User</span></span></td>
    <td><span data-ttu-id="d4acc-239">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-240">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="d4acc-241">Listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="d4acc-242">Markera de användare som ska tilldelas beslutet och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="d4acc-243">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="d4acc-244">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d4acc-244">Select one of the following options:</span></span>

    - <span data-ttu-id="d4acc-245">**Timmar** – Ange antalet timmar som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="d4acc-246">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-247">**Dagar** – Ange antalet dagar som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="d4acc-248">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-249">**Veckor** – Ange antalet veckor som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="d4acc-250">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="d4acc-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="d4acc-251">Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="d4acc-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="d4acc-252">**År –** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="d4acc-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="d4acc-253">Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="d4acc-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="d4acc-254">Om användaren inte fattar beslutet inom den tilldelade tiden, är beslutet försenat.</span><span class="sxs-lookup"><span data-stu-id="d4acc-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="d4acc-255">Ett beslut som är försenat eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="d4acc-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="d4acc-256">Ange vad som ska hända när ett beslut är försenat</span><span class="sxs-lookup"><span data-stu-id="d4acc-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="d4acc-257">Om en användare inte fattar beslutet inom den tilldelade tiden, är beslutet försenat.</span><span class="sxs-lookup"><span data-stu-id="d4acc-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="d4acc-258">Ett beslut som är försenat kan eskaleras eller automatiskt tilldelas en annan användare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="d4acc-259">Följ dessa steg för att eskalera beslutet om det är försenat.</span><span class="sxs-lookup"><span data-stu-id="d4acc-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="d4acc-260">Klicka på **Eskalering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="d4acc-261">Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="d4acc-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="d4acc-262">Systemet tilldelar automatiskt beslutet till de användare som listats i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="d4acc-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="d4acc-263">Till exempel representerar följande register en eskaleringsväg.</span><span class="sxs-lookup"><span data-stu-id="d4acc-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="d4acc-264">Sekvens</span><span class="sxs-lookup"><span data-stu-id="d4acc-264">Sequence</span></span> | <span data-ttu-id="d4acc-265">Eskaleringsväg</span><span class="sxs-lookup"><span data-stu-id="d4acc-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="d4acc-266">1</span><span class="sxs-lookup"><span data-stu-id="d4acc-266">1</span></span>        | <span data-ttu-id="d4acc-267">Tilldela till: Donna</span><span class="sxs-lookup"><span data-stu-id="d4acc-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="d4acc-268">2</span><span class="sxs-lookup"><span data-stu-id="d4acc-268">2</span></span>        | <span data-ttu-id="d4acc-269">Tilldela till: Erin</span><span class="sxs-lookup"><span data-stu-id="d4acc-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="d4acc-270">3</span><span class="sxs-lookup"><span data-stu-id="d4acc-270">3</span></span>        | <span data-ttu-id="d4acc-271">Slutgiltig åtgärd; \[Val 1\]</span><span class="sxs-lookup"><span data-stu-id="d4acc-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="d4acc-272">I detta scenario tilldelar systemet det försenade beslutet till Donna.</span><span class="sxs-lookup"><span data-stu-id="d4acc-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="d4acc-273">Om Donna inte fattar beslutet inom angiven tidsperiod, tilldelar systemet beslutet till Erin.</span><span class="sxs-lookup"><span data-stu-id="d4acc-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="d4acc-274">Om Erin inte fattar beslutet inom angiven tidsperiod, väljer systemet **\[Val 1\]** som beslut.</span><span class="sxs-lookup"><span data-stu-id="d4acc-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="d4acc-275">Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="d4acc-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="d4acc-276">I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.</span><span class="sxs-lookup"><span data-stu-id="d4acc-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="d4acc-277">Alternativ</span><span class="sxs-lookup"><span data-stu-id="d4acc-277">Option</span></span></th>
    <th><span data-ttu-id="d4acc-278">Användare som beslutet eskaleras till</span><span class="sxs-lookup"><span data-stu-id="d4acc-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="d4acc-279">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="d4acc-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="d4acc-280">Hierarki</span><span class="sxs-lookup"><span data-stu-id="d4acc-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="d4acc-281">Användare i en specifik organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="d4acc-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-282">Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> och, i listan <strong>Hierarkityp</strong>, den hierarkityp som du vill eskalera beslutet till.</span><span class="sxs-lookup"><span data-stu-id="d4acc-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="d4acc-283">Systemet måste hämta ett intervall med användarnamn i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="d4acc-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="d4acc-284">Dessa namn representerar användare som beslutet kan eskaleras till.</span><span class="sxs-lookup"><span data-stu-id="d4acc-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="d4acc-285">Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar:</span><span class="sxs-lookup"><span data-stu-id="d4acc-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="d4acc-286">Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="d4acc-287">Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="d4acc-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="d4acc-288">Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</span><span class="sxs-lookup"><span data-stu-id="d4acc-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="d4acc-289">I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas beslutet:</span><span class="sxs-lookup"><span data-stu-id="d4acc-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="d4acc-290"><strong>Tilldela till samtliga hämtade användare</strong> – Beslutet eskaleras till alla användare i intervallet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="d4acc-291"><strong>Tilldela endast till senast hämtade användare</strong> – Beslutet eskaleras endast till den senaste användaren i intervallet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="d4acc-292"><strong>Exkludera användare med följande villkor:</strong> – Beslutet eskaleras inte till någon användare i intervallet som uppfyller ett visst villkor.</span><span class="sxs-lookup"><span data-stu-id="d4acc-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="d4acc-293">Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-294">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d4acc-294">Workflow user</span></span></td>
    <td><span data-ttu-id="d4acc-295">Användarna i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d4acc-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="d4acc-296">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="d4acc-297">Användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-297">User</span></span></td>
    <td><span data-ttu-id="d4acc-298">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="d4acc-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="d4acc-299">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="d4acc-300">Listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="d4acc-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="d4acc-301">Markera de användare som beslutet ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4acc-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="d4acc-302">I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="d4acc-303">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d4acc-303">Select one of the following options:</span></span>

    - <span data-ttu-id="d4acc-304">**Timmar** – Ange antalet timmar som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="d4acc-305">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-306">**Dagar** – Ange antalet dagar som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="d4acc-307">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-308">**Veckor** – Ange antalet veckor som användaren har på sig att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="d4acc-309">**Månader –** – Välj dag och vecka då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="d4acc-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="d4acc-310">Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="d4acc-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="d4acc-311">**År –** – Välj dag, vecka och månad då användaren senast måste svara.</span><span class="sxs-lookup"><span data-stu-id="d4acc-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="d4acc-312">Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="d4acc-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="d4acc-313">Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen.</span><span class="sxs-lookup"><span data-stu-id="d4acc-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="d4acc-314">Du kan ändra alla användarnas ordningsföljd.</span><span class="sxs-lookup"><span data-stu-id="d4acc-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="d4acc-315">Om användarna i eskaleringsvägen inte fattar beslutet inom den tillåtna tidsperioden, kommer systemet att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="d4acc-316">Om du vill ange vilket alternativ som systemet väljer, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="d4acc-317">Ange en tidsgräns</span><span class="sxs-lookup"><span data-stu-id="d4acc-317">Set a time limit</span></span>

<span data-ttu-id="d4acc-318">Följ dessa steg om beslutet måste fattas inom en viss tid.</span><span class="sxs-lookup"><span data-stu-id="d4acc-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="d4acc-319">De alternativ som du väljer i denna procedur åsidosätter alternativen som du valde i avsnitten **Tilldelning** och **Eskalering** på sidan.</span><span class="sxs-lookup"><span data-stu-id="d4acc-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="d4acc-320">Klicka på **Avancerade inställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4acc-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="d4acc-321">Markera kryssrutan **Ange en tidsgräns för arbetsflödeselement**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="d4acc-322">Ange när beslutet måste fattas i fältet **Tidslängd**.</span><span class="sxs-lookup"><span data-stu-id="d4acc-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="d4acc-323">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d4acc-323">Select one of the following options:</span></span>

    - <span data-ttu-id="d4acc-324">**Timmar** – Ange antalet timmar.</span><span class="sxs-lookup"><span data-stu-id="d4acc-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="d4acc-325">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-326">**Dagar** – Ange antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="d4acc-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="d4acc-327">Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.</span><span class="sxs-lookup"><span data-stu-id="d4acc-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="d4acc-328">**Veckor** – Ange antalet veckor.</span><span class="sxs-lookup"><span data-stu-id="d4acc-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="d4acc-329">**Månader –** – Välj dag och vecka då beslutet senast måste vara fattat.</span><span class="sxs-lookup"><span data-stu-id="d4acc-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="d4acc-330">Du kanske till exempel vill att beslutet ska vara fattat senast på fredagen i den tredje veckan i månaden.</span><span class="sxs-lookup"><span data-stu-id="d4acc-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="d4acc-331">**År –** – Välj dag, vecka och månad då beslutet senast måste vara fattat.</span><span class="sxs-lookup"><span data-stu-id="d4acc-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="d4acc-332">Du kanske till exempel vill att beslutet ska vara fattat senast på fredagen i den tredje veckan i december.</span><span class="sxs-lookup"><span data-stu-id="d4acc-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="d4acc-333">Om tidsgränsen överskrids kommer systemet att fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="d4acc-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="d4acc-334">I listan **Åtgärd** väljer du det alternativ som systemet ska vidta.</span><span class="sxs-lookup"><span data-stu-id="d4acc-334">In the **Action** list, select the option that the system should select.</span></span>
