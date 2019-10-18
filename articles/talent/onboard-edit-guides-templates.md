---
title: Redigera integrationsguider och mallar i Dynamics 365 Talent - Onboard
description: I det här avsnittet beskrivs hur du lägger till aktiviteter och annan information i integrationsguider och mallar i Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7803c7cd2c58b8544d2c8dd711c295d6882f9fca
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010808"
---
# <a name="edit-onboarding-guides-and-templates"></a><span data-ttu-id="4c897-103">Redigera integrationsguider och mallar</span><span class="sxs-lookup"><span data-stu-id="4c897-103">Edit onboarding guides and templates</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4c897-104">När du har skapat en integrationsguide eller mall i Microsoft Dynamics 365 Talent: Onboard måste du lägga till en introduktion, aktiviteter, kontakter och resurser.</span><span class="sxs-lookup"><span data-stu-id="4c897-104">After you create an onboarding guide or template in Microsoft Dynamics 365 Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="4c897-105">Onboard gör att du kan lägga till omfattande innehåll i dina integrationsguider, t.ex.:</span><span class="sxs-lookup"><span data-stu-id="4c897-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="4c897-106">YouTube-videoklipp</span><span class="sxs-lookup"><span data-stu-id="4c897-106">YouTube videos</span></span>
- <span data-ttu-id="4c897-107">Microsoft Sway-presentationer</span><span class="sxs-lookup"><span data-stu-id="4c897-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="4c897-108">Microsoft PowerApps-appar</span><span class="sxs-lookup"><span data-stu-id="4c897-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="4c897-109">Microsoft Stream-videoklipp</span><span class="sxs-lookup"><span data-stu-id="4c897-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="4c897-110">Microsoft Forms-formulär</span><span class="sxs-lookup"><span data-stu-id="4c897-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="4c897-111">Iframes som innehåller webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="4c897-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="4c897-112">Redigera introduktioner eller aktiviteter som importerats från en mall</span><span class="sxs-lookup"><span data-stu-id="4c897-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="4c897-113">Om du skapar en integrationsguide från en mall, eller om du importerar aktiviteter från en mall till en annan, kommer du att märka en **lås**-knapp för de importerade aktiviteterna.</span><span class="sxs-lookup"><span data-stu-id="4c897-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="4c897-114">Dessa kallas *hanterade aktiviteter*.</span><span class="sxs-lookup"><span data-stu-id="4c897-114">These are called *managed activities*.</span></span>

<span data-ttu-id="4c897-115">[![Hanterade aktiviteter](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="4c897-116">När du väljer en hanterad aktivitet kan du se källmallen överst i aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="4c897-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="4c897-117">[![Källa för hanterad aktivitet](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="4c897-118">Om du redigerar en aktivitet i en mall, skickar Onboard ändringarna till alla mallar och ej skickade guider som baseras på mallen.</span><span class="sxs-lookup"><span data-stu-id="4c897-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="4c897-119">Om du väljer en guide som inte har skickats och som är baserad på en mall som du har redigerat och sedan väljer fliken **aktiviteter** i guiden visas ett meddelande om att din guide har ändrats.</span><span class="sxs-lookup"><span data-stu-id="4c897-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="4c897-120">Klicka på **OK**om du vill stänga meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4c897-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="4c897-121">[![Ändra meddelande](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="4c897-122">En svart prick visas bredvid de uppdaterade aktiviteterna.</span><span class="sxs-lookup"><span data-stu-id="4c897-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="4c897-123">[![Ändrad aktivitet](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="4c897-124">Du kan inte redigera hanterade aktiviteter utanför den ursprungliga mallen, förutom att lägga till en tilldelad, förfallodatum eller annan information i det högra avsnittet av aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="4c897-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="4c897-125">Om du vill redigera en hanterad aktivitet, eller om du inte vill att en aktivitet ska ta emot uppdateringar från mallen den kommer från, väljer du **lås**-knappen för den aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="4c897-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="4c897-126">**Lås**-knappen döljs.</span><span class="sxs-lookup"><span data-stu-id="4c897-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="4c897-127">Aktiviteten kommer inte längre att hanteras av den ursprungliga mallen och kommer inte längre att ta emot uppdateringar från den mallen.</span><span class="sxs-lookup"><span data-stu-id="4c897-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="4c897-128">De uppdateringar du gör av en aktivitet påverkar inte den ursprungliga mallen.</span><span class="sxs-lookup"><span data-stu-id="4c897-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="4c897-129">Om du tar bort en aktivitet från en guide och skickar ändringarna från den guidens mall fortsätter aktiviteten att vara borttagen i guiden.</span><span class="sxs-lookup"><span data-stu-id="4c897-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="4c897-130">Kontakter och resurser hanteras inte av mallar.</span><span class="sxs-lookup"><span data-stu-id="4c897-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="4c897-131">Utöver detta hanteras inte avsnitt, så om du lägger till eller redigerar ett avsnitt i en mall flyttas inte ändringarna till några guider eller mallar som använder den mallen.</span><span class="sxs-lookup"><span data-stu-id="4c897-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="4c897-132">Om du lägger till nya aktiviteter i en mall, flyttas de nya aktiviteterna till guider och mallar baserade på den mallen och de nya aktiviteterna visas högst upp.</span><span class="sxs-lookup"><span data-stu-id="4c897-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="4c897-133">Importera aktiviteter från en annan mall</span><span class="sxs-lookup"><span data-stu-id="4c897-133">Import activities from another template</span></span>

<span data-ttu-id="4c897-134">Du kan importera aktiviteter från en eller flera mallar till en guide eller en mall.</span><span class="sxs-lookup"><span data-stu-id="4c897-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="4c897-135">Välj den guide eller mall du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="4c897-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="4c897-136">Välj fliken **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="4c897-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="4c897-137">Välj fliken **import** i avsnittet till höger.</span><span class="sxs-lookup"><span data-stu-id="4c897-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="4c897-138">[![Importera aktiviteter](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="4c897-139">Om du vill förhandsgranska uppgifterna i en ny flik i webbläsaren, markerar du knappen **Öppna i ny flik** på en mall.</span><span class="sxs-lookup"><span data-stu-id="4c897-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="4c897-140">[![Importera aktiviteter](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="4c897-141">Dra och släpp den önskade mallen till den plats i programguidens mall där du vill att aktiviteterna ska visas.</span><span class="sxs-lookup"><span data-stu-id="4c897-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="4c897-142">Fortsätt redigera din guide eller mall.</span><span class="sxs-lookup"><span data-stu-id="4c897-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="4c897-143">De importerade aktiviteterna innehåller en **lås**-knapp, som anger att dessa aktiviteter hanteras av mallen som du importerade från.</span><span class="sxs-lookup"><span data-stu-id="4c897-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="4c897-144">När du gör ändringar i den importerade mallen kommer dessa aktiviteter att uppdateras i mallen du importerade dem till.</span><span class="sxs-lookup"><span data-stu-id="4c897-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="4c897-145">Ändringarna flyttas dock inte automatiskt till guider som skapats från mallen du importerade till.</span><span class="sxs-lookup"><span data-stu-id="4c897-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="4c897-146">Skicka ändringar från en mall till andra mallar eller guider</span><span class="sxs-lookup"><span data-stu-id="4c897-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="4c897-147">Om du redigerar en mall som innehåller aktiviteter som används i andra mallar eller guider måste du utföra ändringarna om du vill att de ska visas i de andra mallarna eller guiderna.</span><span class="sxs-lookup"><span data-stu-id="4c897-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="4c897-148">Om du inte är säker på om din malls aktiviteter används i andra mallar eller guiderna väljer du fliken **Används i** för att visa var dessa aktiviteter förekommer.</span><span class="sxs-lookup"><span data-stu-id="4c897-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="4c897-149">[![Visa guider och mallar som aktiviteter används i](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="4c897-150">Så här flyttar du dina ändringar:</span><span class="sxs-lookup"><span data-stu-id="4c897-150">To push your changes:</span></span>

1. <span data-ttu-id="4c897-151">Spara ändringarna genom att välja knappen **spara**.</span><span class="sxs-lookup"><span data-stu-id="4c897-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="4c897-152">Om du inte gör det uppmanas du att spara ändringarna i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="4c897-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="4c897-153">Välj **Skicka dessa ändringar**.</span><span class="sxs-lookup"><span data-stu-id="4c897-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="4c897-154">Lägga till eller redigera en inledning</span><span class="sxs-lookup"><span data-stu-id="4c897-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="4c897-155">Ange en flik för **Introduktion**, ange en rubrik för guiden och ett öppningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="4c897-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="4c897-156">Om du vill använda exempeltexten väljer du **Använd detta meddelande**.</span><span class="sxs-lookup"><span data-stu-id="4c897-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="4c897-157">[![Fliken Introduktion i en Onboard-mall](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="4c897-158">Använd formateringsknappar om du vill skriva ut text som du behöver eller om du vill lägga till bilder eller länkar.</span><span class="sxs-lookup"><span data-stu-id="4c897-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="4c897-159">Spara arbetet genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4c897-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="4c897-160">Lägga till eller redigera aktiviteter</span><span class="sxs-lookup"><span data-stu-id="4c897-160">Add or edit activities</span></span>

1. <span data-ttu-id="4c897-161">På fliken **aktiviteter** drar du objekt från höger till redigeringsområdet.</span><span class="sxs-lookup"><span data-stu-id="4c897-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="4c897-162">Om du vill organisera guiden i avsnitt drar du objektet **Nya avsnitt** till redigeringsområdet och anger ett namn och en valfri beskrivning av avsnittet.</span><span class="sxs-lookup"><span data-stu-id="4c897-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="4c897-163">Lägga till ett nytt avsnitt i en integrationsguide eller mall</span><span class="sxs-lookup"><span data-stu-id="4c897-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="4c897-164">Om du vill lägga till aktiviteter för den nya anställningen drar du objektet **Ny aktivitet** till redigeringsområdet och anger ett namn och en beskrivning för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="4c897-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="4c897-165">Lägga till en ny aktivitet i en integrationsguide eller mall</span><span class="sxs-lookup"><span data-stu-id="4c897-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="4c897-166">Lägga till omfattande innehåll i din integrationsguide:</span><span class="sxs-lookup"><span data-stu-id="4c897-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="4c897-167">Lägg till en YouTube-video genom att dra **YouTube**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och ange URL för YouTube-videon.</span><span class="sxs-lookup"><span data-stu-id="4c897-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="4c897-168">Om du vill lägga till en Sway-presentation eller ett nyhetsbrev drar du **Sway**-objektet till redigeringsområdet, anger ett namn och en beskrivning för aktiviteten och anger den inbäddade webbadressen för Sway-presentationen eller nyhetsbrevet.</span><span class="sxs-lookup"><span data-stu-id="4c897-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="4c897-169">Om du vill lägga till en PowerApps-app, dra **PowerApps**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och välj antingen PowerApps-appen eller ange PowerApps app-ID.</span><span class="sxs-lookup"><span data-stu-id="4c897-169">To add a PowerApps app, drag the **PowerApps** item to the editing area, enter a name and description for the activity, and either select the PowerApps app or enter the PowerApps app ID.</span></span>
    - <span data-ttu-id="4c897-170">Lägg till en Microsoft Stream-video genom att dra **Microsoft Stream**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och ange URL för Microsoft Stream-videon.</span><span class="sxs-lookup"><span data-stu-id="4c897-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="4c897-171">Om du vill lägga till ett Microsoft Forms-formulär, dra **Microsoft Forms**-objektet till redigeringsområdet, ange ett namn och beskrivning för aktiviteten, ange URL-adressen för Microsoft Forms-formuläret och ange storleken på skärmområdet.</span><span class="sxs-lookup"><span data-stu-id="4c897-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="4c897-172">Om du vill lägga till en iframe som innehåller webbinnehåll, dra **Webbinnehåll (iframe)**-objektet till redigeringsområdet, ange ett namn och beskrivning för aktiviteten, ange URL-adressen för webbinnehållet och ange storleken på skärmområdet.</span><span class="sxs-lookup"><span data-stu-id="4c897-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="4c897-173">Lägga till omfattande innehåll i en integrationsguide eller mall</span><span class="sxs-lookup"><span data-stu-id="4c897-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="4c897-174">Valfritt: tilldela aktiviteten till en specifik person eller roll i området till höger om varje aktivitet, Lägg till ett förfallodatum och en kontaktperson och tilldela en kategorifärg.</span><span class="sxs-lookup"><span data-stu-id="4c897-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="4c897-175">När du tilldelar en aktivitet till en person eller roll skapas en uppgift för varje enskild person.</span><span class="sxs-lookup"><span data-stu-id="4c897-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="4c897-176">Den här uppgiften visas på menyn **aktiviteter** i Onboard.</span><span class="sxs-lookup"><span data-stu-id="4c897-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="4c897-177">[![Tilldela en aktivitet i en integrationsguide eller mall](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="4c897-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="4c897-178">Spara arbetet genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4c897-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="4c897-179">Om du vill ta bort en aktivitet eller ett avsnitt väljer du knappen **Ta bort** (papperskorgsymbolen) i det övre högra hörnet av aktiviteten eller avsnittet.</span><span class="sxs-lookup"><span data-stu-id="4c897-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="4c897-180">Om du vill ordna om aktiviteter och avsnitt drar du dem till en ny plats.</span><span class="sxs-lookup"><span data-stu-id="4c897-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="4c897-181">Lägga till eller redigera</span><span class="sxs-lookup"><span data-stu-id="4c897-181">Add or edit contacts</span></span>

<span data-ttu-id="4c897-182">Du kan lägga till kontaktpersoner som kan hjälpa din nya anställning att lyckas från dag ett.</span><span class="sxs-lookup"><span data-stu-id="4c897-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="4c897-183">Dessa kontakter kan vara rekryterare, medarbetare, integrationskompisar, mentorer, administratörer och supportpersonal.</span><span class="sxs-lookup"><span data-stu-id="4c897-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="4c897-184">På fliken **Kontakter**, välj **Ny kontakt**.</span><span class="sxs-lookup"><span data-stu-id="4c897-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="4c897-185">I dialogrutan **Lägg till teammedlemmar**, ange kontaktpersonens namn eller e-postadress, ange en kort beskrivning som förklarar hur kontaktpersonen kan hjälpa den nya anställningen och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4c897-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="4c897-186">Lägga till kontakter i en integrationsguide eller mall</span><span class="sxs-lookup"><span data-stu-id="4c897-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="4c897-187">Du kan också välja en eller flera kontakter under **förslag**.</span><span class="sxs-lookup"><span data-stu-id="4c897-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="4c897-188">Spara arbetet genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4c897-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="4c897-189">Om du vill ta bort en kontakt väljer du knappen **Ta bort** (papperskorgsymbolen) till höger om kontakten.</span><span class="sxs-lookup"><span data-stu-id="4c897-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="4c897-190">Om du vill redigera en kontakt väljer du knappen **Redigera** (pennsymbolen) till höger om kontakten.</span><span class="sxs-lookup"><span data-stu-id="4c897-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="4c897-191">Lägga till eller redigera resurser</span><span class="sxs-lookup"><span data-stu-id="4c897-191">Add or edit resources</span></span>

<span data-ttu-id="4c897-192">Du kan lägga till användbara filer, kartor och länkar till avsnittet **resurser** i din integrationsguide.</span><span class="sxs-lookup"><span data-stu-id="4c897-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="4c897-193">På fliken **Resurser**, välj **Ny resurs**.</span><span class="sxs-lookup"><span data-stu-id="4c897-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="4c897-194">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="4c897-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="4c897-195">Om du vill lägga till en fil väljer du fliken **Fil** och drar filen till det angivna området.</span><span class="sxs-lookup"><span data-stu-id="4c897-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="4c897-196">(Du kan också klicka någonstans i området för att bläddra efter filen på din dator eller välja **bläddra i OneDrive**.) Ange ett namn på filen och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4c897-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="4c897-197">Om du vill lägga till en länk väljer väljer du fliken**Länk** och anger ett namn och en adress för länken och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4c897-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="4c897-198">Om du vill lägga till en karta väljer väljer du fliken **karta** och anger ett namn och en adress för kartan och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4c897-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="4c897-199">Onboard kommer att innehålla en karta över den adress som du anger.</span><span class="sxs-lookup"><span data-stu-id="4c897-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="4c897-200">Lägga till en resurs i en integrationsguide eller mall</span><span class="sxs-lookup"><span data-stu-id="4c897-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="4c897-201">Spara arbetet genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4c897-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="4c897-202">Om du vill ta bort en resurs väljer du knappen **Ta bort** (papperskorgsymbolen) till höger om resursen.</span><span class="sxs-lookup"><span data-stu-id="4c897-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="4c897-203">Om du vill redigera en kontakt väljer du knappen **Redigera** (pennsymbolen) till höger om resursen.</span><span class="sxs-lookup"><span data-stu-id="4c897-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c897-204">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4c897-204">Next steps</span></span>

- [<span data-ttu-id="4c897-205">Dela innehåll med andra deltagare</span><span class="sxs-lookup"><span data-stu-id="4c897-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="4c897-206">Visa status för uppgifter och integration av medarbetare</span><span class="sxs-lookup"><span data-stu-id="4c897-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="4c897-207">Skapa anställningsteam i Onboard</span><span class="sxs-lookup"><span data-stu-id="4c897-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="4c897-208">Se även</span><span class="sxs-lookup"><span data-stu-id="4c897-208">See also</span></span>

- [<span data-ttu-id="4c897-209">Prova eller köp appen Onboard</span><span class="sxs-lookup"><span data-stu-id="4c897-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="4c897-210">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4c897-210">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="4c897-211">Viktig information</span><span class="sxs-lookup"><span data-stu-id="4c897-211">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="4c897-212">Få support</span><span class="sxs-lookup"><span data-stu-id="4c897-212">Get support</span></span>](./talent-support.md)
