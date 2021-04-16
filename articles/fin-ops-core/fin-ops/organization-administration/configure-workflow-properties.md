---
title: Konfigurera arbetsflödesegenskaper
description: I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.
author: ChrisGarty
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
ms.openlocfilehash: 8d55665df9efdc87f8a7c42a132bad11b4c4426e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747793"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="1a062-103">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="1a062-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a062-104">I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="1a062-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="1a062-105">Öppna arbetsflödet i arbetsflödesredigeraren för att konfigurera ett egenskaperna för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="1a062-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="1a062-106">Klicka på arbetsytan i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="1a062-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="1a062-107">Du kan sedan använda följande procedurer när du vill konfigurera olika egenskaper för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="1a062-108">Ge arbetsflödet ett namn</span><span class="sxs-lookup"><span data-stu-id="1a062-108">Name the workflow</span></span>

<span data-ttu-id="1a062-109">Följ dessa steg när du vill ange ett namn för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="1a062-110">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1a062-111">Ange ett unikt namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1a062-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="1a062-112">Om du till exempel skapar ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, kan du namnge arbetsflödet för inköpsrekvisitioner **Inköpsrekvisitioner för Danmark** eller **Inköpsrekvisitioner för Spanien**.</span><span class="sxs-lookup"><span data-stu-id="1a062-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="1a062-113">Ange arbetsflödets ägare</span><span class="sxs-lookup"><span data-stu-id="1a062-113">Specify the workflow owner</span></span>

<span data-ttu-id="1a062-114">Ägaren till arbetsflödet är den person som administrerar och underhåller arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="1a062-115">Följ dessa steg för att ange arbetsflödets ägare.</span><span class="sxs-lookup"><span data-stu-id="1a062-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="1a062-116">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1a062-117">I listan **Ägare** väljer du namnet på den person som ska hantera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="1a062-118">Välj en e-postmall</span><span class="sxs-lookup"><span data-stu-id="1a062-118">Select an email template</span></span>

<span data-ttu-id="1a062-119">Följ dessa steg för att välja den e-postmall som används för att skapa meddelanden om arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="1a062-120">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1a062-121">Välj mallen i listan **E-postmall för arbetsflödesmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="1a062-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="1a062-122">Ange instruktioner för användare</span><span class="sxs-lookup"><span data-stu-id="1a062-122">Enter instructions for users</span></span>

<span data-ttu-id="1a062-123">Du kan tillhandahålla instruktioner till de användare som skickar dokument för bearbetning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="1a062-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="1a062-124">Dessa användare kallas även för *upphovsmän*.</span><span class="sxs-lookup"><span data-stu-id="1a062-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="1a062-125">Anta att du skapar ett arbetsflöde för en inköpsrekvisition och anger instruktioner.</span><span class="sxs-lookup"><span data-stu-id="1a062-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="1a062-126">Dessa instruktioner kan sedan läsas av användare som anger inköpsrekvisitioner på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="1a062-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="1a062-127">För att visa instruktioner klickar upphovsmannen klickar på ikonen i meddelandefältet för arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="1a062-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="1a062-128">Följ dessa steg om du vill ange instruktioner för användare.</span><span class="sxs-lookup"><span data-stu-id="1a062-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="1a062-129">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1a062-130">Ange instruktionerna i fältet **Sändningsinstruktioner**.</span><span class="sxs-lookup"><span data-stu-id="1a062-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="1a062-131">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="1a062-132">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="1a062-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="1a062-133">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="1a062-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="1a062-134">Klicka på fältet **Sändningsinstruktioner** för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="1a062-135">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="1a062-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="1a062-136">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="1a062-137">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="1a062-137">Click **Insert**.</span></span>

4. <span data-ttu-id="1a062-138">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="1a062-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="1a062-139">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="1a062-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="1a062-140">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="1a062-141">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="1a062-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="1a062-142">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="1a062-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="1a062-143">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1a062-144">Se steg 3 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="1a062-145">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="1a062-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a062-146">Platshållare kan inte läggas till genom att kopiera och klistra in eftersom målinformationen inte klistras in på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="1a062-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="1a062-147">Använd gränssnittet för att lägga till platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="1a062-148">Ange när det här arbetsflödet används med aktiveringsvillkor</span><span class="sxs-lookup"><span data-stu-id="1a062-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="1a062-149">Du kan skapa flera arbetsflöden utifrån samma arbetsflödestyp.</span><span class="sxs-lookup"><span data-stu-id="1a062-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="1a062-150">Om du har flera arbetsflöden som är baserade på samma typ, måste du ange när respektive arbetsflöde ska användas med aktiveringsvillkor.</span><span class="sxs-lookup"><span data-stu-id="1a062-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="1a062-151">Om aktiveringsvillkoren inte uppfylls används standardarbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="1a062-152">Om det bara finns en definierad arbetsflödeskonfiguration för en arbetsflödestyp, kommer arbetsflödeskonfigurationen att användas oavsett aktiveringsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="1a062-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="1a062-153">Du kan till exempel skapa ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, exempelvis inköpsrekvisitioner för Danmark eller inköpsrekvisitioner för Spanien med följande villkor.</span><span class="sxs-lookup"><span data-stu-id="1a062-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="1a062-154">Inköpsrekvisitioner för Danmark används när: land/region = DK:</span><span class="sxs-lookup"><span data-stu-id="1a062-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="1a062-155">Inköpsrekvisitioner för Spanien används när: land/region = ES:</span><span class="sxs-lookup"><span data-stu-id="1a062-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="1a062-156">Följ dessa steg för att ange när arbetsflödet som du konfigurerar ska användas.</span><span class="sxs-lookup"><span data-stu-id="1a062-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="1a062-157">Klicka på **Aktivering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="1a062-158">Markera kryssrutan **Ange villkor för att köra detta arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="1a062-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="1a062-159">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="1a062-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="1a062-160">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="1a062-160">Enter a condition.</span></span>
5. <span data-ttu-id="1a062-161">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="1a062-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="1a062-162">Kör genom arbetsflödet med några målposter för att verifiera att villkoret innehåller och exkluderar poster.</span><span class="sxs-lookup"><span data-stu-id="1a062-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="1a062-163">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="1a062-163">Specify when notifications are sent</span></span>

<span data-ttu-id="1a062-164">När ett dokument skickas in för bearbetning skapas en arbetsflödesinstans.</span><span class="sxs-lookup"><span data-stu-id="1a062-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="1a062-165">Du kan skicka meddelanden till användarna när arbetsflödesinstanser som baseras på arbetsflödet har startats, slutförts, annullerats eller stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="1a062-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="1a062-166">Följ dessa steg för att ange när meddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="1a062-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="1a062-167">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="1a062-168">Markera kryssrutan för varje händelse som ska utlösa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="1a062-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="1a062-169">**Startat** – Skicka meddelanden när en arbetsflödesinstans har startats.</span><span class="sxs-lookup"><span data-stu-id="1a062-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="1a062-170">**Stoppat** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="1a062-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="1a062-171">**Slutfört** – Skicka meddelanden när en arbetsflödesinstans har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1a062-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="1a062-172">**Oåterkalleligt** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett oåterkalleligt fel.</span><span class="sxs-lookup"><span data-stu-id="1a062-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="1a062-173">**Avslutat** – Skicka meddelanden när en arbetsflödesinstans har avslutats.</span><span class="sxs-lookup"><span data-stu-id="1a062-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="1a062-174">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="1a062-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="1a062-175">Ange meddelandetexten i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="1a062-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="1a062-176">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1a062-177">Platshållare ersätts med lämpliga data när texten visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="1a062-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="1a062-178">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="1a062-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="1a062-179">Klicka i fältet för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="1a062-180">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="1a062-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="1a062-181">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="1a062-182">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="1a062-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="1a062-183">En gemensam platshållare med **Meddelandetext** som ska inkluderas är "Senaste anteckningar: %Workflow.Last note%”, som visar alla kommentarer från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="1a062-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="1a062-184">Följ dessa steg för att lägga till översättningar av texten:</span><span class="sxs-lookup"><span data-stu-id="1a062-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="1a062-185">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="1a062-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="1a062-186">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="1a062-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="1a062-187">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="1a062-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="1a062-188">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="1a062-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="1a062-189">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1a062-190">Se steg 5 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="1a062-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="1a062-191">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="1a062-191">Click **Close**.</span></span>

7. <span data-ttu-id="1a062-192">Använd följande alternativ för att, i fliken **Mottagare**, ange vem som ska få meddelandena.</span><span class="sxs-lookup"><span data-stu-id="1a062-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="1a062-193">Alternativ</span><span class="sxs-lookup"><span data-stu-id="1a062-193">Option</span></span></th>
    <th><span data-ttu-id="1a062-194">Meddelandena skickas till dessa användare</span><span class="sxs-lookup"><span data-stu-id="1a062-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="1a062-195">Följ dessa steg om du vill skicka meddelanden</span><span class="sxs-lookup"><span data-stu-id="1a062-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="1a062-196">Deltagare</span><span class="sxs-lookup"><span data-stu-id="1a062-196">Participant</span></span></td>
    <td><span data-ttu-id="1a062-197">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="1a062-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1a062-198">Klicka på <strong>Deltagare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="1a062-199">Välj den typ av grupp eller roll som du vill skicka meddelanden till i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="1a062-200">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="1a062-201">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="1a062-201">Workflow user</span></span></td>
    <td><span data-ttu-id="1a062-202">Användare som är deltagare i detta arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="1a062-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1a062-203">Klicka på <strong>Användare av arbetsflöde</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="1a062-204">Välj en deltagare i detta arbetsflöde i fliken <strong>Användare av arbetsflöde</strong> i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="1a062-205">Användare</span><span class="sxs-lookup"><span data-stu-id="1a062-205">User</span></span></td>
    <td><span data-ttu-id="1a062-206">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="1a062-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1a062-207">Klicka på <strong>Användare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="1a062-208">Fliken <strong>Användare</strong> i listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="1a062-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="1a062-209">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a062-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="1a062-210">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="1a062-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="1a062-211">Kommentera de ändringar som du har gjorts i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="1a062-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="1a062-212">Gör på följande sätt om du vill kommentera de ändringar som du har utfört i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1a062-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="1a062-213">Klicka på **Noteringar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1a062-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="1a062-214">Skriv dina kommentarer i fältet **Ange kommentarer om arbetsflödet**.</span><span class="sxs-lookup"><span data-stu-id="1a062-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="1a062-215">Granska dina kommentarer.</span><span class="sxs-lookup"><span data-stu-id="1a062-215">Review your comments.</span></span> <span data-ttu-id="1a062-216">När du har lagt till kommentarer kan du inte ändra dem.</span><span class="sxs-lookup"><span data-stu-id="1a062-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="1a062-217">Klicka på **Lägg till** för att lägga till dina kommentarer i området **Kommentarshistorik**.</span><span class="sxs-lookup"><span data-stu-id="1a062-217">Click **Add** to add your comments to the **Comment history** area.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]