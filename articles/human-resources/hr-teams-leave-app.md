---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 342106ad09db3a5d9c2dec8ab18e824d70e0f6bf
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128171"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="9016f-103">Hantera ansökningar om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="9016f-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9016f-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="9016f-105">Du kan använda en robot för att begära information och påbörja en begäran om att lämna en begäran.</span><span class="sxs-lookup"><span data-stu-id="9016f-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="9016f-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="9016f-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="9016f-107">Du kan dessutom skicka personuppgifter om din kommande ledighet i team och chattar utanför Personal-appen.</span><span class="sxs-lookup"><span data-stu-id="9016f-107">You can also send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="9016f-108">Installera appen</span><span class="sxs-lookup"><span data-stu-id="9016f-108">Install the app</span></span>

<span data-ttu-id="9016f-109">Du hittar appen Personal i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="9016f-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="9016f-110">I Microsoft Teams väljer du de tre punkterna (...).</span><span class="sxs-lookup"><span data-stu-id="9016f-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Punkter i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="9016f-112">Sök efter Dynamics 365 Human Resources och välj sedan panelen **Personal**.</span><span class="sxs-lookup"><span data-stu-id="9016f-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![HR-panel i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="9016f-114">Välj knappen **Lägg till** om du vill installera appen.</span><span class="sxs-lookup"><span data-stu-id="9016f-114">Select the **Add** button to install the app.</span></span>

   ![Instalaltion av Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="9016f-116">Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.</span><span class="sxs-lookup"><span data-stu-id="9016f-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Fliken Inställningar i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="9016f-118">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="9016f-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="9016f-119">Om du har till gång till mer än en instans av Personal kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9016f-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="9016f-120">Appen har nu stöd för säkerhetsrollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="9016f-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="9016f-121">Använd roboten</span><span class="sxs-lookup"><span data-stu-id="9016f-121">Use the bot</span></span>

<span data-ttu-id="9016f-122">När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.</span><span class="sxs-lookup"><span data-stu-id="9016f-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Robotvälkomstmeddelande i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="9016f-124">När du interagerar med roboten för första gången måste du kanske logga in.</span><span class="sxs-lookup"><span data-stu-id="9016f-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="9016f-125">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="9016f-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="9016f-126">Du kan be roboten att:</span><span class="sxs-lookup"><span data-stu-id="9016f-126">You can ask the bot to:</span></span>

- <span data-ttu-id="9016f-127">Visa saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till.</span><span class="sxs-lookup"><span data-stu-id="9016f-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Visa saldo i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="9016f-129">Visa ytterligare information om en viss tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="9016f-129">Show additional details about a specific leave type.</span></span>

   ![Visa information i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="9016f-131">Påbörja en ledighetsbegäran åt dig.</span><span class="sxs-lookup"><span data-stu-id="9016f-131">Start a leave request for you.</span></span>

   ![Begär tjänstledighet i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="9016f-133">När du har startat en ledighetsansökan kan du justera dagarna direkt på kortet.</span><span class="sxs-lookup"><span data-stu-id="9016f-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Redigera begäran i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="9016f-135">När du är klar med att mata in information väljer du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9016f-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="9016f-136">Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="9016f-136">You can also select **Save as draft** to come back to it later.</span></span>

![Skicka in begäran i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="9016f-138">Hantera din ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-138">Manage your leave in Teams</span></span>

<span data-ttu-id="9016f-139">På fliken **Ledighet** kan du visa:</span><span class="sxs-lookup"><span data-stu-id="9016f-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="9016f-140">Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till</span><span class="sxs-lookup"><span data-stu-id="9016f-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="9016f-141">Kommande ansökningar om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="9016f-141">Upcoming leave requests</span></span>

- <span data-ttu-id="9016f-142">Ansökningar om ledighet</span><span class="sxs-lookup"><span data-stu-id="9016f-142">Time-off requests</span></span>

- <span data-ttu-id="9016f-143">Utkast till ansökan om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="9016f-143">Draft leave requests</span></span>

![Fliken Ledighet i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="9016f-145">Skapa en ny ansökan</span><span class="sxs-lookup"><span data-stu-id="9016f-145">Create a new request</span></span>

1. <span data-ttu-id="9016f-146">Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.</span><span class="sxs-lookup"><span data-stu-id="9016f-146">To create a new leave request, select **New request**.</span></span>

   ![Ny ansökan i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="9016f-148">Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9016f-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Lägg till ledighet i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="9016f-150">Ange en orsakskod vid behov.</span><span class="sxs-lookup"><span data-stu-id="9016f-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="9016f-151">Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="9016f-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="9016f-152">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9016f-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="9016f-153">Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="9016f-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="9016f-154">Hantera ansökningsutkast</span><span class="sxs-lookup"><span data-stu-id="9016f-154">Manage draft requests</span></span>

1. <span data-ttu-id="9016f-155">Välj fliken **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="9016f-155">Select the **Drafts** tab.</span></span>

   ![Fliken Utkast i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="9016f-157">Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.</span><span class="sxs-lookup"><span data-stu-id="9016f-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="9016f-158">Utför erforderliga ändringar.</span><span class="sxs-lookup"><span data-stu-id="9016f-158">Make any necessary changes.</span></span> <span data-ttu-id="9016f-159">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9016f-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="9016f-160">Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="9016f-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Redigera utkast i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="9016f-162">Svara på Teams-meddelanden</span><span class="sxs-lookup"><span data-stu-id="9016f-162">Respond to Teams notifications</span></span>

<span data-ttu-id="9016f-163">När du eller en arbetare är godkännare för att skicka en begäran om ledighet får du ett meddelande i Personal-appen i Teams.</span><span class="sxs-lookup"><span data-stu-id="9016f-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="9016f-164">Du kan välja meddelandet om du vill visa det.</span><span class="sxs-lookup"><span data-stu-id="9016f-164">You can select the notification to view it.</span></span> <span data-ttu-id="9016f-165">Meddelanden visas också i området **Chatt** .</span><span class="sxs-lookup"><span data-stu-id="9016f-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="9016f-166">Om du är en godkännare kan du välja **Godkänn** eller **Neka** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9016f-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="9016f-167">Du kan också ange ett valfritt meddelande.</span><span class="sxs-lookup"><span data-stu-id="9016f-167">You can also provide an optional message.</span></span>

![Meddelande om ledighetsansökan i Personal Teams-appen](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="9016f-169">Skicka kommande ledighetsinformation till dina medarbetare</span><span class="sxs-lookup"><span data-stu-id="9016f-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="9016f-170">När du har installerat Personal-appen för Teams kan du enkelt skicka information om din kommande ledighet till dina medarbetare i grupper eller chattar.</span><span class="sxs-lookup"><span data-stu-id="9016f-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="9016f-171">I ett team eller chatt i Teams väljer du Personal-knappen under chattfönstret.</span><span class="sxs-lookup"><span data-stu-id="9016f-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Personal-knappen under chattfönstret](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="9016f-173">Välj den begäran som du vill dela.</span><span class="sxs-lookup"><span data-stu-id="9016f-173">Select the leave request you want to share.</span></span> <span data-ttu-id="9016f-174">Om du vill dela ett utkast till en ledighetsansökan väljer du **utkast** först.</span><span class="sxs-lookup"><span data-stu-id="9016f-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Välj en kommande ledighetsansökan att dela](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="9016f-176">Din ledighetsansökan visas i chatten.</span><span class="sxs-lookup"><span data-stu-id="9016f-176">Your leave request will display in the chat.</span></span>

![Kort för ledighetsansökan i Personal](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="9016f-178">Om du har delat en utkastbegäran visas det som ett utkast:</span><span class="sxs-lookup"><span data-stu-id="9016f-178">If you shared a draft request, it will display as a draft:</span></span>

![Utkast av kort för ledighetsansökan i Personal](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="9016f-180">Visa ditt teams ledighetskalender</span><span class="sxs-lookup"><span data-stu-id="9016f-180">View your team's leave calendar</span></span>

<span data-ttu-id="9016f-181">Om du är chef med underställda kan du visa teamets godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="9016f-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="9016f-182">I Personal-appen i Teams, välj **Ledighet**.</span><span class="sxs-lookup"><span data-stu-id="9016f-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="9016f-183">Välj **teamkalender** .</span><span class="sxs-lookup"><span data-stu-id="9016f-183">Select **Team calendar**.</span></span>

   ![Visa kalender i Personal Teams-app](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="9016f-185">Kalendern visar dina underställdas godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="9016f-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Ledighetskalender i Personal Teams-app](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="9016f-187">Felsökning</span><span class="sxs-lookup"><span data-stu-id="9016f-187">Troubleshooting</span></span>

<span data-ttu-id="9016f-188">Om du har problem med att logga in på eller använda appen Personal Teams kan du försöka följa dessa instruktioner för felsökning.</span><span class="sxs-lookup"><span data-stu-id="9016f-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="9016f-189">Om du fortfarande har problem efter felsökningen kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9016f-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="9016f-190">För mer information, se [Få support](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="9016f-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="9016f-191">Det går inte att logga in på Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="9016f-192">Om du inte kan logga in i appen är det möjligt att det konto du använder för att logga in i Microsoft Teams inte är associerat med en medarbetarpost i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9016f-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="9016f-193">Kontakta systemadministratören för att se till att din medarbetarpost är korrekt associerad.</span><span class="sxs-lookup"><span data-stu-id="9016f-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="9016f-194">Fel vid godkännande av tjänstledighetsbegäranden i Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="9016f-195">Om du får ett fel när du försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du testa följande åtgärder för felsökning:</span><span class="sxs-lookup"><span data-stu-id="9016f-195">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="9016f-196">Kontrollera att det konto som du använder för att logga in Microsoft Teams är det som du använder för att komma åt Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9016f-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="9016f-197">Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="9016f-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="9016f-198">Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9016f-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="9016f-199">Kända tillgänglighetsproblem</span><span class="sxs-lookup"><span data-stu-id="9016f-199">Known accessibility issues</span></span>

<span data-ttu-id="9016f-200">Appen Personal i Team har följande tillgänglighetsproblem som vi arbetar med att åtgärda i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="9016f-200">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="9016f-201">Utleverans</span><span class="sxs-lookup"><span data-stu-id="9016f-201">Issue</span></span> | <span data-ttu-id="9016f-202">Lösning eller förklaring</span><span class="sxs-lookup"><span data-stu-id="9016f-202">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="9016f-203">Om du zoomar till 400 % på skrivbordet döljs vissa av åtgärdsknapparna i vyn.</span><span class="sxs-lookup"><span data-stu-id="9016f-203">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="9016f-204">Vi rekommenderar att du använder en skärmförstorare istället för att använda den här zoomningsnivån.</span><span class="sxs-lookup"><span data-stu-id="9016f-204">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="9016f-205">Under fliken **Ledighet** tillkännager VoiceOver en knappåtgärd samtidigt som rubriken för ledighetsrutnätet läses upp.</span><span class="sxs-lookup"><span data-stu-id="9016f-205">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="9016f-206">Rubriken och elementen i rutnätet är grupperade efter år och de är döljbara.</span><span class="sxs-lookup"><span data-stu-id="9016f-206">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="9016f-207">Med VoiceOver tolkas detta som en åtgärdsbar artikel, men det är inte det.</span><span class="sxs-lookup"><span data-stu-id="9016f-207">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="9016f-208">Under fliken **Ledighet** finns en extra svepgest när du navigerar till **Orsakskod** i en ny begäran.</span><span class="sxs-lookup"><span data-stu-id="9016f-208">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="9016f-209">Det finns ingen dold kontroll som svepnavigeringen försöker nå.</span><span class="sxs-lookup"><span data-stu-id="9016f-209">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="9016f-210">Under fliken **Ledighet**, om du sveper när kalendern är öppen, hamnar du utanför kontrollen istället för längst upp i en ny begäran eller när du redigerar en begäran.</span><span class="sxs-lookup"><span data-stu-id="9016f-210">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="9016f-211">När du kommer till **Gå till idag**, se det som slutet på kontrollen och svep i motsatt riktning för att komma tillbaka till toppen.</span><span class="sxs-lookup"><span data-stu-id="9016f-211">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="9016f-212">VoiceOver läser inte etiketterna för datum.</span><span class="sxs-lookup"><span data-stu-id="9016f-212">Voiceover doesn't read the labels for dates.</span></span> | <span data-ttu-id="9016f-213">Datumen i par är alltid **startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="9016f-213">The dates encountered in pairs are always **Start date** and **End date**.</span></span> |
| <span data-ttu-id="9016f-214">Under fliken **Chatt** hoppar fokus tillbaka till toppen när du anger ett datum samtidigt som du använder hjälpverktyget eller tangentbordsnavigeringen.</span><span class="sxs-lookup"><span data-stu-id="9016f-214">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="9016f-215">TABB tills du kommer till inmatningsområdet igen.</span><span class="sxs-lookup"><span data-stu-id="9016f-215">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="9016f-216">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="9016f-216">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="9016f-217">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="9016f-217">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="9016f-218">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="9016f-218">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="9016f-219">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="9016f-219">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="9016f-220">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="9016f-220">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="9016f-221">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="9016f-221">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="9016f-222">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="9016f-222">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="9016f-223">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="9016f-223">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="9016f-224">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9016f-224">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="9016f-225">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="9016f-225">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="9016f-226">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="9016f-226">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="9016f-227">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="9016f-227">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="9016f-228">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9016f-228">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="9016f-229">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="9016f-229">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="9016f-230">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Personal har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="9016f-230">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="9016f-231">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="9016f-231">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="9016f-232">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="9016f-232">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="9016f-233">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9016f-233">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="9016f-234">Medan du samtalar med chattroboten i Personal-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9016f-234">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="9016f-235">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Personal har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="9016f-235">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="9016f-236">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9016f-236">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="9016f-237">Om du vill begränsa åtkomsten till Personal-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="9016f-237">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="9016f-238">Se även</span><span class="sxs-lookup"><span data-stu-id="9016f-238">See also</span></span>

[<span data-ttu-id="9016f-239">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-239">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="9016f-240">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="9016f-240">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="9016f-241">Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="9016f-241">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
