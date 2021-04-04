---
title: Konfigurera arbetsflödesegenskaper
description: I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40118f329a676ffb30870eb882d127e3eb258599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566977"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="60197-103">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="60197-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60197-104">I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="60197-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="60197-105">Öppna arbetsflödet i arbetsflödesredigeraren för att konfigurera ett egenskaperna för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="60197-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="60197-106">Klicka på arbetsytan i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="60197-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="60197-107">Du kan sedan använda följande procedurer när du vill konfigurera olika egenskaper för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="60197-108">Ge arbetsflödet ett namn</span><span class="sxs-lookup"><span data-stu-id="60197-108">Name the workflow</span></span>

<span data-ttu-id="60197-109">Följ dessa steg när du vill ange ett namn för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="60197-110">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="60197-111">Ange ett unikt namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="60197-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="60197-112">Om du till exempel skapar ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, kan du namnge arbetsflödet för inköpsrekvisitioner **Inköpsrekvisitioner för Danmark** eller **Inköpsrekvisitioner för Spanien**.</span><span class="sxs-lookup"><span data-stu-id="60197-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="60197-113">Ange arbetsflödets ägare</span><span class="sxs-lookup"><span data-stu-id="60197-113">Specify the workflow owner</span></span>

<span data-ttu-id="60197-114">Ägaren till arbetsflödet är den person som administrerar och underhåller arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="60197-115">Följ dessa steg för att ange arbetsflödets ägare.</span><span class="sxs-lookup"><span data-stu-id="60197-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="60197-116">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="60197-117">I listan **Ägare** väljer du namnet på den person som ska hantera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="60197-118">Välj en e-postmall</span><span class="sxs-lookup"><span data-stu-id="60197-118">Select an email template</span></span>

<span data-ttu-id="60197-119">Följ dessa steg för att välja den e-postmall som används för att skapa meddelanden om arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="60197-120">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="60197-121">Välj mallen i listan **E-postmall för arbetsflödesmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="60197-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="60197-122">Ange instruktioner för användare</span><span class="sxs-lookup"><span data-stu-id="60197-122">Enter instructions for users</span></span>

<span data-ttu-id="60197-123">Du kan tillhandahålla instruktioner till de användare som skickar dokument för bearbetning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="60197-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="60197-124">Dessa användare kallas även för *upphovsmän*.</span><span class="sxs-lookup"><span data-stu-id="60197-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="60197-125">Anta att du skapar ett arbetsflöde för en inköpsrekvisition och anger instruktioner.</span><span class="sxs-lookup"><span data-stu-id="60197-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="60197-126">Dessa instruktioner kan sedan läsas av användare som anger inköpsrekvisitioner på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="60197-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="60197-127">För att visa instruktioner klickar upphovsmannen klickar på ikonen i meddelandefältet för arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="60197-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="60197-128">Följ dessa steg om du vill ange instruktioner för användare.</span><span class="sxs-lookup"><span data-stu-id="60197-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="60197-129">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="60197-130">Ange instruktionerna i fältet **Sändningsinstruktioner**.</span><span class="sxs-lookup"><span data-stu-id="60197-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="60197-131">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="60197-132">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="60197-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="60197-133">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="60197-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="60197-134">Klicka på fältet **Sändningsinstruktioner** för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="60197-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="60197-135">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="60197-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="60197-136">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="60197-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="60197-137">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="60197-137">Click **Insert**.</span></span>

4. <span data-ttu-id="60197-138">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="60197-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="60197-139">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="60197-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="60197-140">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="60197-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="60197-141">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="60197-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="60197-142">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="60197-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="60197-143">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="60197-144">Se steg 3 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="60197-145">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="60197-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="60197-146">Platshållare kan inte läggas till genom att kopiera och klistra in eftersom målinformationen inte klistras in på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="60197-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="60197-147">Använd gränssnittet för att lägga till platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="60197-148">Ange när det här arbetsflödet används med aktiveringsvillkor</span><span class="sxs-lookup"><span data-stu-id="60197-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="60197-149">Du kan skapa flera arbetsflöden utifrån samma arbetsflödestyp.</span><span class="sxs-lookup"><span data-stu-id="60197-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="60197-150">Om du har flera arbetsflöden som är baserade på samma typ, måste du ange när respektive arbetsflöde ska användas med aktiveringsvillkor.</span><span class="sxs-lookup"><span data-stu-id="60197-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="60197-151">Om aktiveringsvillkoren inte uppfylls används standardarbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="60197-152">Om det bara finns en definierad arbetsflödeskonfiguration för en arbetsflödestyp, kommer arbetsflödeskonfigurationen att användas oavsett aktiveringsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="60197-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="60197-153">Du kan till exempel skapa ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, exempelvis inköpsrekvisitioner för Danmark eller inköpsrekvisitioner för Spanien med följande villkor.</span><span class="sxs-lookup"><span data-stu-id="60197-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="60197-154">Inköpsrekvisitioner för Danmark används när: land/region = DK:</span><span class="sxs-lookup"><span data-stu-id="60197-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="60197-155">Inköpsrekvisitioner för Spanien används när: land/region = ES:</span><span class="sxs-lookup"><span data-stu-id="60197-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="60197-156">Följ dessa steg för att ange när arbetsflödet som du konfigurerar ska användas.</span><span class="sxs-lookup"><span data-stu-id="60197-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="60197-157">Klicka på **Aktivering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="60197-158">Markera kryssrutan **Ange villkor för att köra detta arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="60197-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="60197-159">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="60197-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="60197-160">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="60197-160">Enter a condition.</span></span>
5. <span data-ttu-id="60197-161">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="60197-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="60197-162">Kör genom arbetsflödet med några målposter för att verifiera att villkoret innehåller och exkluderar poster.</span><span class="sxs-lookup"><span data-stu-id="60197-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="60197-163">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="60197-163">Specify when notifications are sent</span></span>

<span data-ttu-id="60197-164">När ett dokument skickas in för bearbetning skapas en arbetsflödesinstans.</span><span class="sxs-lookup"><span data-stu-id="60197-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="60197-165">Du kan skicka meddelanden till användarna när arbetsflödesinstanser som baseras på arbetsflödet har startats, slutförts, annullerats eller stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="60197-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="60197-166">Följ dessa steg för att ange när meddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="60197-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="60197-167">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="60197-168">Markera kryssrutan för varje händelse som ska utlösa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="60197-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="60197-169">**Startat** – Skicka meddelanden när en arbetsflödesinstans har startats.</span><span class="sxs-lookup"><span data-stu-id="60197-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="60197-170">**Stoppat** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="60197-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="60197-171">**Slutfört** – Skicka meddelanden när en arbetsflödesinstans har slutförts.</span><span class="sxs-lookup"><span data-stu-id="60197-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="60197-172">**Oåterkalleligt** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett oåterkalleligt fel.</span><span class="sxs-lookup"><span data-stu-id="60197-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="60197-173">**Avslutat** – Skicka meddelanden när en arbetsflödesinstans har avslutats.</span><span class="sxs-lookup"><span data-stu-id="60197-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="60197-174">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="60197-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="60197-175">Ange meddelandetexten i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="60197-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="60197-176">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="60197-177">Platshållare ersätts med lämpliga data när texten visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="60197-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="60197-178">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="60197-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="60197-179">Klicka i fältet för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="60197-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="60197-180">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="60197-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="60197-181">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="60197-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="60197-182">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="60197-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="60197-183">En gemensam platshållare med **Meddelandetext** som ska inkluderas är "Senaste anteckningar: %Workflow.Last note%”, som visar alla kommentarer från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="60197-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="60197-184">Följ dessa steg för att lägga till översättningar av texten:</span><span class="sxs-lookup"><span data-stu-id="60197-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="60197-185">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="60197-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="60197-186">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="60197-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="60197-187">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="60197-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="60197-188">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="60197-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="60197-189">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="60197-190">Se steg 5 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="60197-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="60197-191">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="60197-191">Click **Close**.</span></span>

7. <span data-ttu-id="60197-192">Använd följande alternativ för att, i fliken **Mottagare**, ange vem som ska få meddelandena.</span><span class="sxs-lookup"><span data-stu-id="60197-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="60197-193">Alternativ</span><span class="sxs-lookup"><span data-stu-id="60197-193">Option</span></span></th>
    <th><span data-ttu-id="60197-194">Meddelandena skickas till dessa användare</span><span class="sxs-lookup"><span data-stu-id="60197-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="60197-195">Följ dessa steg om du vill skicka meddelanden</span><span class="sxs-lookup"><span data-stu-id="60197-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="60197-196">Deltagare</span><span class="sxs-lookup"><span data-stu-id="60197-196">Participant</span></span></td>
    <td><span data-ttu-id="60197-197">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="60197-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="60197-198">Klicka på <strong>Deltagare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="60197-199">Välj den typ av grupp eller roll som du vill skicka meddelanden till i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="60197-200">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="60197-201">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="60197-201">Workflow user</span></span></td>
    <td><span data-ttu-id="60197-202">Användare som är deltagare i detta arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="60197-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="60197-203">Klicka på <strong>Användare av arbetsflöde</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="60197-204">Välj en deltagare i detta arbetsflöde i fliken <strong>Användare av arbetsflöde</strong> i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="60197-205">Användare</span><span class="sxs-lookup"><span data-stu-id="60197-205">User</span></span></td>
    <td><span data-ttu-id="60197-206">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="60197-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="60197-207">Klicka på <strong>Användare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="60197-208">Fliken <strong>Användare</strong> i listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="60197-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="60197-209">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="60197-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="60197-210">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="60197-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="60197-211">Kommentera de ändringar som du har gjorts i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="60197-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="60197-212">Gör på följande sätt om du vill kommentera de ändringar som du har utfört i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="60197-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="60197-213">Klicka på **Noteringar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60197-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="60197-214">Skriv dina kommentarer i fältet **Ange kommentarer om arbetsflödet**.</span><span class="sxs-lookup"><span data-stu-id="60197-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="60197-215">Granska dina kommentarer.</span><span class="sxs-lookup"><span data-stu-id="60197-215">Review your comments.</span></span> <span data-ttu-id="60197-216">När du har lagt till kommentarer kan du inte ändra dem.</span><span class="sxs-lookup"><span data-stu-id="60197-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="60197-217">Klicka på **Lägg till** för att lägga till dina kommentarer i området **Kommentarshistorik**.</span><span class="sxs-lookup"><span data-stu-id="60197-217">Click **Add** to add your comments to the **Comment history** area.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]