---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 48bf6f7997d6159077419bcd05d27fd711c8fb4b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891040"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="922a8-103">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="922a8-104">Med hjälp av Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="922a8-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="922a8-105">Du kan använda en robot för att begära information och påbörja en begäran om att lämna en begäran.</span><span class="sxs-lookup"><span data-stu-id="922a8-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="922a8-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="922a8-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="922a8-107">Du kan dessutom skicka personuppgifter om din kommande ledighet i Teams och chattar utanför Personal-appen.</span><span class="sxs-lookup"><span data-stu-id="922a8-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="922a8-108">Installera appen</span><span class="sxs-lookup"><span data-stu-id="922a8-108">Install the app</span></span>

<span data-ttu-id="922a8-109">Du hittar appen Dynamics 365 Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="922a8-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="922a8-110">I Microsoft Teams väljer du de tre punkterna (...).</span><span class="sxs-lookup"><span data-stu-id="922a8-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Punkter i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="922a8-112">Sök efter Dynamics 365 Human Resources och välj sedan panelen **Personal**.</span><span class="sxs-lookup"><span data-stu-id="922a8-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![HR-panel i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="922a8-114">Välj knappen **Lägg till** om du vill installera appen.</span><span class="sxs-lookup"><span data-stu-id="922a8-114">Select the **Add** button to install the app.</span></span>

   ![Instalaltion av Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="922a8-116">Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.</span><span class="sxs-lookup"><span data-stu-id="922a8-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Fliken Inställningar i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="922a8-118">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="922a8-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="922a8-119">Om du har till gång till mer än en instans av Personal kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="922a8-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="922a8-120">Appen har nu stöd för säkerhetsrollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="922a8-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="922a8-121">Använd roboten</span><span class="sxs-lookup"><span data-stu-id="922a8-121">Use the bot</span></span>

<span data-ttu-id="922a8-122">När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.</span><span class="sxs-lookup"><span data-stu-id="922a8-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Robotvälkomstmeddelande i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="922a8-124">När du interagerar med roboten för första gången måste du kanske logga in.</span><span class="sxs-lookup"><span data-stu-id="922a8-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="922a8-125">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="922a8-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="922a8-126">Du kan be roboten att:</span><span class="sxs-lookup"><span data-stu-id="922a8-126">You can ask the bot to:</span></span>

- <span data-ttu-id="922a8-127">Påbörja en ledighetsbegäran åt dig.</span><span class="sxs-lookup"><span data-stu-id="922a8-127">Start a leave request for you.</span></span>

  ![Starta en tjänstledighetsbegäran i Teams-chatt](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="922a8-129">Chattroboten fyller i en tjänstledighetsbegäran för dig.</span><span class="sxs-lookup"><span data-stu-id="922a8-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="922a8-130">Välj **Begär ledig tid** och redigera informationen för din förfrågan.</span><span class="sxs-lookup"><span data-stu-id="922a8-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Redigera information om ledighetsansökan](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="922a8-132">När du har redigerat informationen om din tjänstledighet väljer du **Skicka** för att skicka den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="922a8-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Skicka ledighetsbegäran](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="922a8-134">Hantera din ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-134">Manage your leave in Teams</span></span>

<span data-ttu-id="922a8-135">På fliken **Ledighet** kan du visa:</span><span class="sxs-lookup"><span data-stu-id="922a8-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="922a8-136">Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till</span><span class="sxs-lookup"><span data-stu-id="922a8-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="922a8-137">Kommande ansökningar om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="922a8-137">Upcoming leave requests</span></span>

- <span data-ttu-id="922a8-138">Ansökningar om ledighet</span><span class="sxs-lookup"><span data-stu-id="922a8-138">Time-off requests</span></span>

- <span data-ttu-id="922a8-139">Utkast till ansökan om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="922a8-139">Draft leave requests</span></span>

![Fliken Ledighet i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="922a8-141">Skapa en ny ansökan</span><span class="sxs-lookup"><span data-stu-id="922a8-141">Create a new request</span></span>

1. <span data-ttu-id="922a8-142">Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.</span><span class="sxs-lookup"><span data-stu-id="922a8-142">To create a new leave request, select **New request**.</span></span>

   ![Ny ansökan i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="922a8-144">Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="922a8-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Lägg till ledighet i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="922a8-146">Ange en orsakskod vid behov.</span><span class="sxs-lookup"><span data-stu-id="922a8-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="922a8-147">Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="922a8-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="922a8-148">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="922a8-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="922a8-149">Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="922a8-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="922a8-150">Hantera ansökningsutkast</span><span class="sxs-lookup"><span data-stu-id="922a8-150">Manage draft requests</span></span>

1. <span data-ttu-id="922a8-151">Välj fliken **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="922a8-151">Select the **Drafts** tab.</span></span>

   ![Fliken Utkast i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="922a8-153">Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.</span><span class="sxs-lookup"><span data-stu-id="922a8-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="922a8-154">Utför erforderliga ändringar.</span><span class="sxs-lookup"><span data-stu-id="922a8-154">Make any necessary changes.</span></span> <span data-ttu-id="922a8-155">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="922a8-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="922a8-156">Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="922a8-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![Redigera utkast i Personal Teams-appen för tjänstledighet](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="922a8-158">Svara på Teams-meddelanden</span><span class="sxs-lookup"><span data-stu-id="922a8-158">Respond to Teams notifications</span></span>

<span data-ttu-id="922a8-159">När du eller en arbetare är godkännare för att skicka en begäran om ledighet får du ett meddelande i Personal-appen i Teams.</span><span class="sxs-lookup"><span data-stu-id="922a8-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="922a8-160">Du kan välja meddelandet om du vill visa det.</span><span class="sxs-lookup"><span data-stu-id="922a8-160">You can select the notification to view it.</span></span> <span data-ttu-id="922a8-161">Meddelanden visas också i området **Chatt** .</span><span class="sxs-lookup"><span data-stu-id="922a8-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="922a8-162">Om du är en godkännare kan du välja **Godkänn** eller **Neka** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="922a8-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="922a8-163">Du kan också ange ett valfritt meddelande.</span><span class="sxs-lookup"><span data-stu-id="922a8-163">You can also provide an optional message.</span></span>

![Meddelande om ledighetsansökan i Personal Teams-appen](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="922a8-165">Skicka kommande ledighetsinformation till dina medarbetare</span><span class="sxs-lookup"><span data-stu-id="922a8-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="922a8-166">När du har installerat Personal-appen för Teams kan du enkelt skicka information om din kommande ledighet till dina medarbetare i grupper eller chattar.</span><span class="sxs-lookup"><span data-stu-id="922a8-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="922a8-167">I ett team eller chatt i Teams väljer du Personal-knappen under chattfönstret.</span><span class="sxs-lookup"><span data-stu-id="922a8-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Personal-knappen under chattfönstret](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="922a8-169">Välj den begäran som du vill dela.</span><span class="sxs-lookup"><span data-stu-id="922a8-169">Select the leave request you want to share.</span></span> <span data-ttu-id="922a8-170">Om du vill dela ett utkast till en ledighetsansökan väljer du **utkast** först.</span><span class="sxs-lookup"><span data-stu-id="922a8-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Välj en kommande ledighetsansökan att dela](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="922a8-172">Din ledighetsansökan visas i chatten.</span><span class="sxs-lookup"><span data-stu-id="922a8-172">Your leave request will display in the chat.</span></span>

![Kort för ledighetsansökan i Personal](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="922a8-174">Om du har delat en utkastbegäran visas det som ett utkast:</span><span class="sxs-lookup"><span data-stu-id="922a8-174">If you shared a draft request, it will display as a draft:</span></span>

![Utkast av kort för ledighetsansökan i Personal](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="922a8-176">Visa ditt teams ledighetskalender</span><span class="sxs-lookup"><span data-stu-id="922a8-176">View your team's leave calendar</span></span>

<span data-ttu-id="922a8-177">Om du är chef med underställda kan du visa teamets godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="922a8-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="922a8-178">I Personal-appen i Teams, välj **Ledighet**.</span><span class="sxs-lookup"><span data-stu-id="922a8-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="922a8-179">Välj **teamkalender** .</span><span class="sxs-lookup"><span data-stu-id="922a8-179">Select **Team calendar**.</span></span> <span data-ttu-id="922a8-180">Kalendern visar dina underställdas godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="922a8-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Visa kalender i Personal Teams-app](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="922a8-182">Om du inte kan se teamkalendern ber du administratören att aktivera den.</span><span class="sxs-lookup"><span data-stu-id="922a8-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="922a8-183">För mer information, se [Installera och konfigurera](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="922a8-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="922a8-184">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="922a8-184">Supported languages</span></span>

<span data-ttu-id="922a8-185">Dynamics 365 Human Resources-appen i Teams har stöd för följande språk:</span><span class="sxs-lookup"><span data-stu-id="922a8-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="922a8-186">Språk-ID</span><span class="sxs-lookup"><span data-stu-id="922a8-186">Locale ID</span></span> | <span data-ttu-id="922a8-187">Språk</span><span class="sxs-lookup"><span data-stu-id="922a8-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="922a8-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="922a8-188">de-DE</span></span> | <span data-ttu-id="922a8-189">Tyska (Tyskland)</span><span class="sxs-lookup"><span data-stu-id="922a8-189">German (Germany)</span></span> |
| <span data-ttu-id="922a8-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="922a8-190">es-ES</span></span> | <span data-ttu-id="922a8-191">Spanska (Spanien)</span><span class="sxs-lookup"><span data-stu-id="922a8-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="922a8-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="922a8-192">es-MX</span></span> | <span data-ttu-id="922a8-193">Spanska (Mexiko)</span><span class="sxs-lookup"><span data-stu-id="922a8-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="922a8-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="922a8-194">fr-CA</span></span> | <span data-ttu-id="922a8-195">Franska (Kanada)</span><span class="sxs-lookup"><span data-stu-id="922a8-195">French (Canada)</span></span> |
| <span data-ttu-id="922a8-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="922a8-196">fr-FR</span></span> | <span data-ttu-id="922a8-197">Franska (Frankrike)</span><span class="sxs-lookup"><span data-stu-id="922a8-197">French (France)</span></span> |
| <span data-ttu-id="922a8-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="922a8-198">it-IT</span></span> | <span data-ttu-id="922a8-199">Italienska (Italien)</span><span class="sxs-lookup"><span data-stu-id="922a8-199">Italian (Italy)</span></span> |
| <span data-ttu-id="922a8-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="922a8-200">nl-NL</span></span> | <span data-ttu-id="922a8-201">Nederländska (Nederländerna)</span><span class="sxs-lookup"><span data-stu-id="922a8-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="922a8-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="922a8-202">pt-BR</span></span> | <span data-ttu-id="922a8-203">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="922a8-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="922a8-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="922a8-204">tr-TR</span></span> | <span data-ttu-id="922a8-205">Turkiska (Turkiet)</span><span class="sxs-lookup"><span data-stu-id="922a8-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="922a8-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="922a8-206">zh-CN</span></span> | <span data-ttu-id="922a8-207">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="922a8-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="922a8-208">Felsökning</span><span class="sxs-lookup"><span data-stu-id="922a8-208">Troubleshooting</span></span>

<span data-ttu-id="922a8-209">Om du har problem med att logga in på eller använda Teams-appen Dynamics 365 Human Resources kan du försöka följa dessa instruktioner för felsökning.</span><span class="sxs-lookup"><span data-stu-id="922a8-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="922a8-210">Om du fortfarande har problem efter felsökningen kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="922a8-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="922a8-211">För mer information, se [Få support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="922a8-211">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="922a8-212">Det går inte att logga in på Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="922a8-213">Om du inte kan logga in i appen är det möjligt att det konto du använder för att logga in i Microsoft Teams inte är associerat med en medarbetarpost i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="922a8-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="922a8-214">Kontakta systemadministratören för att se till att din medarbetarpost är korrekt associerad.</span><span class="sxs-lookup"><span data-stu-id="922a8-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="922a8-215">Översättningarna visas inte korrekt</span><span class="sxs-lookup"><span data-stu-id="922a8-215">Translations don't display correctly</span></span>

<span data-ttu-id="922a8-216">Om översättningarna inte visas som förväntat ser du till att det språk du väljer i Teams matchar det språk som valts i personal **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="922a8-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="922a8-217">I Teams, titta på **Appspråket** i **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="922a8-217">In Teams, look at **App language** in **Settings**.</span></span>

![Teams-inställningar](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="922a8-219">I personal, välj **Inställningar** och sedan **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="922a8-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="922a8-220">Kontrollera att fältet **Språk** matchar fältet i fältet **Appspråk** i Teams.</span><span class="sxs-lookup"><span data-stu-id="922a8-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Användaralternativ för personal](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="922a8-222">Hör av dig om du fortfarande upplever översättningsproblem.</span><span class="sxs-lookup"><span data-stu-id="922a8-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="922a8-223">Mer information finns i [Få support för Finance and Operations-appar eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="922a8-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="922a8-224">Fel vid godkännande av tjänstledighetsbegäranden i Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="922a8-225">Om du får ett fel när du försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du testa följande åtgärder för felsökning:</span><span class="sxs-lookup"><span data-stu-id="922a8-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="922a8-226">Kontrollera att det konto som du använder för att logga in Microsoft Teams är det som du använder för att komma åt Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="922a8-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="922a8-227">Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="922a8-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="922a8-228">Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="922a8-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="922a8-229">Kända tillgänglighetsproblem</span><span class="sxs-lookup"><span data-stu-id="922a8-229">Known accessibility issues</span></span>

<span data-ttu-id="922a8-230">Appen Personal i Team har följande tillgänglighetsproblem som vi arbetar med att åtgärda i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="922a8-230">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="922a8-231">Utleverans</span><span class="sxs-lookup"><span data-stu-id="922a8-231">Issue</span></span> | <span data-ttu-id="922a8-232">Lösning eller förklaring</span><span class="sxs-lookup"><span data-stu-id="922a8-232">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="922a8-233">Om du zoomar till 400 % på skrivbordet döljs vissa av åtgärdsknapparna i vyn.</span><span class="sxs-lookup"><span data-stu-id="922a8-233">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="922a8-234">Vi rekommenderar att du använder en skärmförstorare istället för att använda den här zoomningsnivån.</span><span class="sxs-lookup"><span data-stu-id="922a8-234">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="922a8-235">Under fliken **Ledighet** tillkännager VoiceOver en knappåtgärd samtidigt som rubriken för ledighetsrutnätet läses upp.</span><span class="sxs-lookup"><span data-stu-id="922a8-235">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="922a8-236">Rubriken och elementen i rutnätet är grupperade efter år och de är döljbara.</span><span class="sxs-lookup"><span data-stu-id="922a8-236">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="922a8-237">Med VoiceOver tolkas detta som en åtgärdsbar artikel, men det är inte det.</span><span class="sxs-lookup"><span data-stu-id="922a8-237">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="922a8-238">Under fliken **Ledighet** finns en extra svepgest när du navigerar till **Orsakskod** i en ny begäran.</span><span class="sxs-lookup"><span data-stu-id="922a8-238">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="922a8-239">Det finns ingen dold kontroll som svepnavigeringen försöker nå.</span><span class="sxs-lookup"><span data-stu-id="922a8-239">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="922a8-240">Under fliken **Ledighet**, om du sveper när kalendern är öppen, hamnar du utanför kontrollen istället för längst upp i en ny begäran eller när du redigerar en begäran.</span><span class="sxs-lookup"><span data-stu-id="922a8-240">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="922a8-241">När du kommer till **Gå till idag**, se det som slutet på kontrollen och svep i motsatt riktning för att komma tillbaka till toppen.</span><span class="sxs-lookup"><span data-stu-id="922a8-241">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="922a8-242">Under fliken **Chatt** hoppar fokus tillbaka till toppen när du anger ett datum samtidigt som du använder hjälpverktyget eller tangentbordsnavigeringen.</span><span class="sxs-lookup"><span data-stu-id="922a8-242">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="922a8-243">TABB tills du kommer till inmatningsområdet igen.</span><span class="sxs-lookup"><span data-stu-id="922a8-243">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="922a8-244">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="922a8-244">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="922a8-245">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="922a8-245">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="922a8-246">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågeställningen eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="922a8-246">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="922a8-247">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="922a8-247">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="922a8-248">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="922a8-248">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="922a8-249">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet, avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="922a8-249">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="922a8-250">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="922a8-250">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="922a8-251">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="922a8-251">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="922a8-252">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="922a8-252">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="922a8-253">LUIS-tjänsten har endast åtkomst till användarfrågeställningarna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en frågeställning som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="922a8-253">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="922a8-254">Innehållet i användarens frågeställningar och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="922a8-254">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="922a8-255">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="922a8-255">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="922a8-256">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="922a8-256">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="922a8-257">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="922a8-257">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="922a8-258">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Personal har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="922a8-258">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="922a8-259">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="922a8-259">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="922a8-260">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="922a8-260">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="922a8-261">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="922a8-261">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="922a8-262">Medan du samtalar med chattroboten i Personal-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="922a8-262">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="922a8-263">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Personal har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="922a8-263">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="922a8-264">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="922a8-264">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="922a8-265">Om du vill begränsa åtkomsten till Personal-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="922a8-265">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="922a8-266">Se även</span><span class="sxs-lookup"><span data-stu-id="922a8-266">See also</span></span>

[<span data-ttu-id="922a8-267">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-267">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="922a8-268">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="922a8-268">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="922a8-269">Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="922a8-269">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]