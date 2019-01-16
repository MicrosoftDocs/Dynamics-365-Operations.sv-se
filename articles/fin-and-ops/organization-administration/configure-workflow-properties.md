---
title: "Konfigurera arbetsflödesegenskaper"
description: "I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde."
author: sericks007
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 576ce368b2a8672aa39116eb0cc6e3d3f2a06bb3
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2018

---

# <a name="configure-workflow-properties"></a><span data-ttu-id="87d86-103">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="87d86-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87d86-104">I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="87d86-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="87d86-105">Öppna arbetsflödet i arbetsflödesredigeraren för att konfigurera ett egenskaperna för ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="87d86-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="87d86-106">Klicka på arbetsytan i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="87d86-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="87d86-107">Du kan sedan använda följande procedurer när du vill konfigurera olika egenskaper för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="87d86-108">Ge arbetsflödet ett namn</span><span class="sxs-lookup"><span data-stu-id="87d86-108">Name the workflow</span></span>

<span data-ttu-id="87d86-109">Följ dessa steg när du vill ange ett namn för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="87d86-110">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="87d86-111">Ange ett unikt namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="87d86-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="87d86-112">Om du till exempel skapar ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, kan du namnge arbetsflödet för inköpsrekvisitioner **Inköpsrekvisitioner för Danmark** eller **Inköpsrekvisitioner för Spanien**.</span><span class="sxs-lookup"><span data-stu-id="87d86-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="87d86-113">Ange arbetsflödets ägare</span><span class="sxs-lookup"><span data-stu-id="87d86-113">Specify the workflow owner</span></span>

<span data-ttu-id="87d86-114">Ägaren till arbetsflödet är den person som administrerar och underhåller arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="87d86-115">Följ dessa steg för att ange arbetsflödets ägare.</span><span class="sxs-lookup"><span data-stu-id="87d86-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="87d86-116">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="87d86-117">I listan **Ägare** väljer du namnet på den person som ska hantera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="87d86-118">Välj en e-postmall</span><span class="sxs-lookup"><span data-stu-id="87d86-118">Select an email template</span></span>

<span data-ttu-id="87d86-119">Följ dessa steg för att välja den e-postmall som används för att skapa meddelanden om arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="87d86-120">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="87d86-121">Välj mallen i listan **E-postmall för arbetsflödesmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="87d86-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="87d86-122">Ange instruktioner för användare</span><span class="sxs-lookup"><span data-stu-id="87d86-122">Enter instructions for users</span></span>

<span data-ttu-id="87d86-123">Du kan tillhandahålla instruktioner till de användare som skickar dokument för bearbetning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="87d86-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="87d86-124">Dessa användare kallas även för *upphovsmän*.</span><span class="sxs-lookup"><span data-stu-id="87d86-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="87d86-125">Anta att du skapar ett arbetsflöde för en inköpsrekvisition och anger instruktioner.</span><span class="sxs-lookup"><span data-stu-id="87d86-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="87d86-126">Dessa instruktioner kan sedan läsas av användare som anger inköpsrekvisitioner på sidan **Inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="87d86-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="87d86-127">För att visa instruktioner klickar upphovsmannen klickar på ikonen i meddelandefältet för arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="87d86-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="87d86-128">Följ dessa steg om du vill ange instruktioner för användare.</span><span class="sxs-lookup"><span data-stu-id="87d86-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="87d86-129">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="87d86-130">Ange instruktionerna i fältet **Sändningsinstruktioner**.</span><span class="sxs-lookup"><span data-stu-id="87d86-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="87d86-131">Om du vill anpassa instruktionerna kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="87d86-132">Platshållare ersätts med lämpliga data när instruktionerna visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="87d86-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="87d86-133">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="87d86-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="87d86-134">Klicka på fältet **Sändningsinstruktioner** för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="87d86-135">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="87d86-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="87d86-136">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="87d86-137">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="87d86-137">Click **Insert**.</span></span>

4. <span data-ttu-id="87d86-138">Om du vill lägga till översättningar av instruktionerna följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="87d86-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="87d86-139">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="87d86-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="87d86-140">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="87d86-141">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="87d86-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="87d86-142">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="87d86-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="87d86-143">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="87d86-144">Se steg 3 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="87d86-145">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="87d86-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="87d86-146">Ange när detta arbetsflöde ska användas</span><span class="sxs-lookup"><span data-stu-id="87d86-146">Specify when this workflow is used</span></span>

<span data-ttu-id="87d86-147">Du kan skapa flera arbetsflöden utifrån samma typ.</span><span class="sxs-lookup"><span data-stu-id="87d86-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="87d86-148">Du kan till exempel skapa ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, exempelvis inköpsrekvisitioner för Danmark eller inköpsrekvisitioner för Spanien.</span><span class="sxs-lookup"><span data-stu-id="87d86-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="87d86-149">Om du har flera arbetsflöden som är baserade på samma typ, måste du ange när respektive arbetsflöde ska användas.</span><span class="sxs-lookup"><span data-stu-id="87d86-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="87d86-150">För föregående exempel anger du följande villkor:</span><span class="sxs-lookup"><span data-stu-id="87d86-150">For the preceding example, you specify the following conditions:</span></span>

- <span data-ttu-id="87d86-151">Inköpsrekvisitioner för Danmark används när: land/region = DK:</span><span class="sxs-lookup"><span data-stu-id="87d86-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="87d86-152">Inköpsrekvisitioner för Spanien används när: land/region = ES:</span><span class="sxs-lookup"><span data-stu-id="87d86-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="87d86-153">Följ dessa steg för att ange när arbetsflödet som du konfigurerar ska användas.</span><span class="sxs-lookup"><span data-stu-id="87d86-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="87d86-154">Klicka på **Aktivering** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-154">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="87d86-155">Markera kryssrutan **Ange villkor för att köra detta arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="87d86-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="87d86-156">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="87d86-156">Click **Add condition**.</span></span>
4. <span data-ttu-id="87d86-157">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="87d86-157">Enter a condition.</span></span>
5. <span data-ttu-id="87d86-158">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="87d86-158">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="87d86-159">Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="87d86-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>

    1. <span data-ttu-id="87d86-160">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="87d86-160">Click **Test**.</span></span>
    2. <span data-ttu-id="87d86-161">På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.</span><span class="sxs-lookup"><span data-stu-id="87d86-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="87d86-162">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="87d86-162">Click **Test**.</span></span> <span data-ttu-id="87d86-163">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du har angett.</span><span class="sxs-lookup"><span data-stu-id="87d86-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="87d86-164">Om du till exempel skapar ett arbetsflöde för inköpsrekvisition för Spanien, visar området **Validera villkor** på sidan en lista över inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="87d86-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="87d86-165">När du klickar på **Testa** utför systemet en utvärdering av vald inköpsrekvisition för att kontrollera om land/region är ES.</span><span class="sxs-lookup"><span data-stu-id="87d86-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4. <span data-ttu-id="87d86-166">När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="87d86-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="87d86-167">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="87d86-167">Specify when notifications are sent</span></span>

<span data-ttu-id="87d86-168">När ett dokument skickas in för bearbetning skapas en arbetsflödesinstans.</span><span class="sxs-lookup"><span data-stu-id="87d86-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="87d86-169">Du kan skicka meddelanden till användarna när arbetsflödesinstanser som baseras på arbetsflödet har startats, slutförts, annullerats eller stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="87d86-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="87d86-170">Följ dessa steg för att ange när meddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="87d86-170">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="87d86-171">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-171">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="87d86-172">Markera kryssrutan för varje händelse som ska utlösa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="87d86-172">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="87d86-173">**Startat** – Skicka meddelanden när en arbetsflödesinstans har startats.</span><span class="sxs-lookup"><span data-stu-id="87d86-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="87d86-174">**Stoppat** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett fel.</span><span class="sxs-lookup"><span data-stu-id="87d86-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="87d86-175">**Slutfört** – Skicka meddelanden när en arbetsflödesinstans har slutförts.</span><span class="sxs-lookup"><span data-stu-id="87d86-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="87d86-176">**Oåterkalleligt** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett oåterkalleligt fel.</span><span class="sxs-lookup"><span data-stu-id="87d86-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="87d86-177">**Avslutat** – Skicka meddelanden när en arbetsflödesinstans har avslutats.</span><span class="sxs-lookup"><span data-stu-id="87d86-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="87d86-178">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="87d86-178">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="87d86-179">Ange meddelandetexten i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="87d86-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="87d86-180">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="87d86-181">Platshållare ersätts med lämpliga data när texten visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="87d86-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="87d86-182">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="87d86-182">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="87d86-183">Klicka i fältet för att ange var platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-183">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="87d86-184">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="87d86-184">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="87d86-185">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-185">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="87d86-186">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="87d86-186">Click **Insert**.</span></span>
    5. <span data-ttu-id="87d86-187">En gemensam platshållare med **Meddelandetext** som ska inkluderas är "Senaste anteckningar: %Workflow.Last note%”, som visar alla kommentarer från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="87d86-187">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="87d86-188">Följ dessa steg för att lägga till översättningar av texten:</span><span class="sxs-lookup"><span data-stu-id="87d86-188">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="87d86-189">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="87d86-189">Click **Translations**.</span></span>
    2. <span data-ttu-id="87d86-190">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="87d86-190">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="87d86-191">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="87d86-191">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="87d86-192">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="87d86-192">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="87d86-193">Om du vill anpassa texten kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-193">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="87d86-194">Se steg 5 för instruktioner om hur du anger en platshållare.</span><span class="sxs-lookup"><span data-stu-id="87d86-194">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="87d86-195">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="87d86-195">Click **Close**.</span></span>

7. <span data-ttu-id="87d86-196">Använd följande alternativ för att, i fliken **Mottagare**, ange vem som ska få meddelandena.</span><span class="sxs-lookup"><span data-stu-id="87d86-196">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="87d86-197">Alternativ</span><span class="sxs-lookup"><span data-stu-id="87d86-197">Option</span></span></th>
    <th><span data-ttu-id="87d86-198">Meddelandena skickas till dessa användare</span><span class="sxs-lookup"><span data-stu-id="87d86-198">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="87d86-199">Följ dessa steg om du vill skicka meddelanden</span><span class="sxs-lookup"><span data-stu-id="87d86-199">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="87d86-200">Deltagare</span><span class="sxs-lookup"><span data-stu-id="87d86-200">Participant</span></span></td>
    <td><span data-ttu-id="87d86-201">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="87d86-201">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="87d86-202">Klicka på <strong>Deltagare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-202">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="87d86-203">Välj den typ av grupp eller roll som du vill skicka meddelanden till i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-203">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="87d86-204">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-204">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="87d86-205">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="87d86-205">Workflow user</span></span></td>
    <td><span data-ttu-id="87d86-206">Användare som är deltagare i detta arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="87d86-206">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="87d86-207">Klicka på <strong>Användare av arbetsflöde</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-207">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="87d86-208">Välj en deltagare i detta arbetsflöde i fliken <strong>Användare av arbetsflöde</strong> i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-208">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="87d86-209">Användare</span><span class="sxs-lookup"><span data-stu-id="87d86-209">User</span></span></td>
    <td><span data-ttu-id="87d86-210">Specifika Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="87d86-210">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="87d86-211">Klicka på <strong>Användare</strong> i fliken <strong>Mottagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-211">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="87d86-212">Listan <strong>Tillgängliga användare</strong> i fliken <strong>Användare</strong> innehåller alla Finance and Operations-användare.</span><span class="sxs-lookup"><span data-stu-id="87d86-212">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="87d86-213">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="87d86-213">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="87d86-214">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="87d86-214">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="87d86-215">Kommentera de ändringar som du har gjorts i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="87d86-215">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="87d86-216">Gör på följande sätt om du vill kommentera de ändringar som du har utfört i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="87d86-216">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="87d86-217">Klicka på **Noteringar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="87d86-217">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="87d86-218">Skriv dina kommentarer i fältet **Ange kommentarer om arbetsflödet**.</span><span class="sxs-lookup"><span data-stu-id="87d86-218">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="87d86-219">Granska dina kommentarer.</span><span class="sxs-lookup"><span data-stu-id="87d86-219">Review your comments.</span></span> <span data-ttu-id="87d86-220">När du har lagt till kommentarer kan du inte ändra dem.</span><span class="sxs-lookup"><span data-stu-id="87d86-220">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="87d86-221">Klicka på **Lägg till** för att lägga till dina kommentarer i området **Kommentarshistorik**.</span><span class="sxs-lookup"><span data-stu-id="87d86-221">Click **Add** to add your comments to the **Comment history** area.</span></span>

