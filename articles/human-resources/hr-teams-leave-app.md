---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 661bb8369fe4dbe6cdf6ee0fb05d16f4350ecf5a
ms.sourcegitcommit: c5c8f19a696ad4a3d68dffd63bfe7b484b999d2b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6097269"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="6c23f-103">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6c23f-104">Med hjälp av Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c23f-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="6c23f-105">Du kan använda en robot för att begära information och påbörja en begäran om att lämna en begäran.</span><span class="sxs-lookup"><span data-stu-id="6c23f-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="6c23f-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="6c23f-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="6c23f-107">Du kan dessutom skicka personuppgifter om din kommande ledighet i Teams och chattar utanför Personal-appen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="6c23f-108">Installera appen</span><span class="sxs-lookup"><span data-stu-id="6c23f-108">Install the app</span></span>

<span data-ttu-id="6c23f-109">Du hittar appen Dynamics 365 Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="6c23f-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="6c23f-110">I Microsoft Teams, navigera till listan med appar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-110">In Microsoft Teams, navigate to the list of apps.</span></span>
 
2. <span data-ttu-id="6c23f-111">Sök efter Dynamics 365 Human Resources och välj sedan panelen **Personal**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

3. <span data-ttu-id="6c23f-112">Välj knappen **Lägg till** om du vill installera appen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-112">Select the **Add** button to install the app.</span></span>

<span data-ttu-id="6c23f-113">Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.</span><span class="sxs-lookup"><span data-stu-id="6c23f-113">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

> [!NOTE]
> <span data-ttu-id="6c23f-114">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="6c23f-114">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="6c23f-115">Om du har till gång till mer än en instans av Personal kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-115">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="6c23f-116">Appen har nu stöd för säkerhetsrollen systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="6c23f-116">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="6c23f-117">Använd roboten</span><span class="sxs-lookup"><span data-stu-id="6c23f-117">Use the bot</span></span>

<span data-ttu-id="6c23f-118">När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.</span><span class="sxs-lookup"><span data-stu-id="6c23f-118">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

> [!NOTE]
> <span data-ttu-id="6c23f-119">När du interagerar med roboten för första gången måste du kanske logga in.</span><span class="sxs-lookup"><span data-stu-id="6c23f-119">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="6c23f-120">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="6c23f-120">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="6c23f-121">Du kan be roboten att:</span><span class="sxs-lookup"><span data-stu-id="6c23f-121">You can ask the bot to:</span></span>

- <span data-ttu-id="6c23f-122">Visa aktuella tjänstledighetssaldon.</span><span class="sxs-lookup"><span data-stu-id="6c23f-122">View your current leave balances.</span></span> <span data-ttu-id="6c23f-123">Skicka till exempel ett meddelande där det står "Visa tjänstledighetssaldon".</span><span class="sxs-lookup"><span data-stu-id="6c23f-123">For example, send a message that says, "View leave balances."</span></span>

- <span data-ttu-id="6c23f-124">Påbörja en ledighetsbegäran åt dig.</span><span class="sxs-lookup"><span data-stu-id="6c23f-124">Start a leave request for you.</span></span> <span data-ttu-id="6c23f-125">Skicka till exempel ett meddelande där det står: "Ta ledigt" eller "Jag vill ta semester nästa torsdag och fredag" som är mer specifik för att begära tjänstledighet för semestertypen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-125">For example, send a message that says, “Take time off” or “I want to take vacation time off next Thursday and Friday” to be more specific for requesting leave for the vacation leave type.</span></span> 

  ![Starta en tjänstledighetsbegäran i Teams-chatt](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="6c23f-127">Chattroboten fyller i en tjänstledighetsbegäran för dig.</span><span class="sxs-lookup"><span data-stu-id="6c23f-127">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="6c23f-128">Välj **Begär ledig tid** och redigera informationen för din förfrågan.</span><span class="sxs-lookup"><span data-stu-id="6c23f-128">Select **Request time off** and edit the details for your request.</span></span>

   <span data-ttu-id="6c23f-129">Om du vill skicka tjänstledighetsansökningar för flera tjänstledighetstyper för samma datum väljer du alternativet **Dela dag med** från menyn **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-129">If you want to submit leave requests for multiple leave types for the same date, select the **Split day with** option from the **More options** menu.</span></span> 

   <span data-ttu-id="6c23f-130">Om du väljer en halvdagsledighet när tjänstledighetsenheten är i dagar, kan du ange om du vill begära ledighet från den första halvan av dagen eller den andra halvan av dagen genom att välja alternativet **Halvdagsdefinition** på menyn **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-130">If you select a half day leave when the leave request unit is in days, you can specify whether you want to request time off the first half day or the second half day by selecting the **Half day definition** option from the **More options** menu.</span></span>
   
   ![Halvdagsdefinitioner](./media/HalfDayDefinitions.png)

- <span data-ttu-id="6c23f-132">När du har redigerat informationen om din tjänstledighet väljer du **Skicka** för att skicka den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="6c23f-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Skicka ledighetsbegäran](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="6c23f-134">Hantera din ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-134">Manage your leave in Teams</span></span>

<span data-ttu-id="6c23f-135">På fliken **Ledighet** kan du visa:</span><span class="sxs-lookup"><span data-stu-id="6c23f-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="6c23f-136">Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till</span><span class="sxs-lookup"><span data-stu-id="6c23f-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="6c23f-137">Kommande ansökningar om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="6c23f-137">Upcoming leave requests</span></span>

- <span data-ttu-id="6c23f-138">Ansökningar om ledighet</span><span class="sxs-lookup"><span data-stu-id="6c23f-138">Time-off requests</span></span>

- <span data-ttu-id="6c23f-139">Utkast till ansökan om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="6c23f-139">Draft leave requests</span></span>
 
### <a name="create-a-new-request"></a><span data-ttu-id="6c23f-140">Skapa en ny ansökan</span><span class="sxs-lookup"><span data-stu-id="6c23f-140">Create a new request</span></span>

1. <span data-ttu-id="6c23f-141">Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-141">To create a new leave request, select **New request**.</span></span>

2. <span data-ttu-id="6c23f-142">Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-142">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Lägg till ledighet i Personal Teams-appen för ledighet](./media/TimeOffHours.png)

3. <span data-ttu-id="6c23f-144">Ange en orsakskod vid behov.</span><span class="sxs-lookup"><span data-stu-id="6c23f-144">If applicable, enter a reason code.</span></span> <span data-ttu-id="6c23f-145">Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="6c23f-145">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="6c23f-146">Välj alternativ **Dela dag med** från menyn **Fler alternativ** om du vill skicka flera ledighetsförfrågningar för samma datum för olika ledighetstyper.</span><span class="sxs-lookup"><span data-stu-id="6c23f-146">Select the **Split day with** option from the **More options** menu if you want to submit multiple leave request entries for the same date for different leave types.</span></span>

5. <span data-ttu-id="6c23f-147">Välj alternativet **Halvdagsdefinition** om du vill ange om du vill begära ledigt den första halvan av dagen eller den andra arbetsdagen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-147">Select the **Half day definition** option to specify if you want to request the first half day off or the second half day off.</span></span> <span data-ttu-id="6c23f-148">Det här alternativet är tillgängligt när enheten för ledighetsförfrågan är i dagar och beloppet som begärts är 0,5 dagar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-148">This option is available when the leave request unit is in days and the amount requested is 0.5 days.</span></span>

6. <span data-ttu-id="6c23f-149">När du är klar med att mata in information väljer du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="6c23f-149">When you're done entering information, enter **Submit** to submit it for approval.</span></span> <span data-ttu-id="6c23f-150">Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="6c23f-150">You can also enter **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="6c23f-151">Hantera ansökningsutkast</span><span class="sxs-lookup"><span data-stu-id="6c23f-151">Manage draft requests</span></span>

1. <span data-ttu-id="6c23f-152">Välj fliken **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-152">Select the **Drafts** tab.</span></span>

2. <span data-ttu-id="6c23f-153">Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.</span><span class="sxs-lookup"><span data-stu-id="6c23f-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="6c23f-154">Utför erforderliga ändringar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-154">Make any necessary changes.</span></span> <span data-ttu-id="6c23f-155">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="6c23f-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="6c23f-156">Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="6c23f-156">You can also select **Save as draft** to come back to it later.</span></span>
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="6c23f-157">Svara på Teams-meddelanden</span><span class="sxs-lookup"><span data-stu-id="6c23f-157">Respond to Teams notifications</span></span>

<span data-ttu-id="6c23f-158">När du eller en arbetare är godkännare för att skicka en begäran om ledighet får du ett meddelande i Personal-appen i Teams.</span><span class="sxs-lookup"><span data-stu-id="6c23f-158">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="6c23f-159">Du kan välja meddelandet om du vill visa det.</span><span class="sxs-lookup"><span data-stu-id="6c23f-159">You can select the notification to view it.</span></span> <span data-ttu-id="6c23f-160">Meddelanden visas också i området **Chatt** .</span><span class="sxs-lookup"><span data-stu-id="6c23f-160">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="6c23f-161">Om du är en godkännare kan du välja **Godkänn** eller **Neka** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6c23f-161">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="6c23f-162">Du kan också ange ett valfritt meddelande.</span><span class="sxs-lookup"><span data-stu-id="6c23f-162">You can also provide an optional message.</span></span>

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="6c23f-163">Skicka kommande ledighetsinformation till dina medarbetare</span><span class="sxs-lookup"><span data-stu-id="6c23f-163">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="6c23f-164">När du har installerat Personal-appen för Teams kan du enkelt skicka information om din kommande ledighet till dina medarbetare i grupper eller chattar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-164">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="6c23f-165">I ett team eller chatt i Teams väljer du Personal-knappen under chattfönstret.</span><span class="sxs-lookup"><span data-stu-id="6c23f-165">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Personal-knappen under chattfönstret](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="6c23f-167">Välj den begäran som du vill dela.</span><span class="sxs-lookup"><span data-stu-id="6c23f-167">Select the leave request you want to share.</span></span> <span data-ttu-id="6c23f-168">Om du vill dela ett utkast till en ledighetsansökan väljer du **utkast** först.</span><span class="sxs-lookup"><span data-stu-id="6c23f-168">If you want to share a draft leave request, select **Drafts** first.</span></span>

<span data-ttu-id="6c23f-169">Din ledighetsansökan visas i chatten.</span><span class="sxs-lookup"><span data-stu-id="6c23f-169">Your leave request will display in the chat.</span></span>

<span data-ttu-id="6c23f-170">Om du har delat en utkastbegäran visas det som ett utkast.</span><span class="sxs-lookup"><span data-stu-id="6c23f-170">If you shared a draft request, it will display as a draft.</span></span>

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="6c23f-171">Visa ditt teams ledighetskalender</span><span class="sxs-lookup"><span data-stu-id="6c23f-171">View your team's leave calendar</span></span>

<span data-ttu-id="6c23f-172">Om du är chef med underställda kan du visa teamets godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="6c23f-172">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="6c23f-173">I Personal-appen i Teams, välj **Ledighet**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-173">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="6c23f-174">Välj **teamkalender** .</span><span class="sxs-lookup"><span data-stu-id="6c23f-174">Select **Team calendar**.</span></span> <span data-ttu-id="6c23f-175">Kalendern visar dina underställdas godkända och väntande ledighet.</span><span class="sxs-lookup"><span data-stu-id="6c23f-175">The calendar displays your direct reports' approved and pending time off.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c23f-176">Om du inte kan se teamkalendern ber du administratören att aktivera den.</span><span class="sxs-lookup"><span data-stu-id="6c23f-176">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="6c23f-177">För mer information, se [Installera och konfigurera](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="6c23f-177">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="6c23f-178">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="6c23f-178">Supported languages</span></span>

<span data-ttu-id="6c23f-179">Dynamics 365 Human Resources-appen i Teams har stöd för följande språk:</span><span class="sxs-lookup"><span data-stu-id="6c23f-179">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="6c23f-180">Språk-ID</span><span class="sxs-lookup"><span data-stu-id="6c23f-180">Locale ID</span></span> | <span data-ttu-id="6c23f-181">Språk</span><span class="sxs-lookup"><span data-stu-id="6c23f-181">Language</span></span> |
| --- | --- |
| <span data-ttu-id="6c23f-182">de-DE</span><span class="sxs-lookup"><span data-stu-id="6c23f-182">de-DE</span></span> | <span data-ttu-id="6c23f-183">Tyska (Tyskland)</span><span class="sxs-lookup"><span data-stu-id="6c23f-183">German (Germany)</span></span> |
| <span data-ttu-id="6c23f-184">es-ES</span><span class="sxs-lookup"><span data-stu-id="6c23f-184">es-ES</span></span> | <span data-ttu-id="6c23f-185">Spanska (Spanien)</span><span class="sxs-lookup"><span data-stu-id="6c23f-185">Spanish (Spain)</span></span> |
| <span data-ttu-id="6c23f-186">es-MX</span><span class="sxs-lookup"><span data-stu-id="6c23f-186">es-MX</span></span> | <span data-ttu-id="6c23f-187">Spanska (Mexiko)</span><span class="sxs-lookup"><span data-stu-id="6c23f-187">Spanish (Mexico)</span></span> |
| <span data-ttu-id="6c23f-188">fr-CA</span><span class="sxs-lookup"><span data-stu-id="6c23f-188">fr-CA</span></span> | <span data-ttu-id="6c23f-189">Franska (Kanada)</span><span class="sxs-lookup"><span data-stu-id="6c23f-189">French (Canada)</span></span> |
| <span data-ttu-id="6c23f-190">fr-FR</span><span class="sxs-lookup"><span data-stu-id="6c23f-190">fr-FR</span></span> | <span data-ttu-id="6c23f-191">Franska (Frankrike)</span><span class="sxs-lookup"><span data-stu-id="6c23f-191">French (France)</span></span> |
| <span data-ttu-id="6c23f-192">it-IT</span><span class="sxs-lookup"><span data-stu-id="6c23f-192">it-IT</span></span> | <span data-ttu-id="6c23f-193">Italienska (Italien)</span><span class="sxs-lookup"><span data-stu-id="6c23f-193">Italian (Italy)</span></span> |
| <span data-ttu-id="6c23f-194">nl-NL</span><span class="sxs-lookup"><span data-stu-id="6c23f-194">nl-NL</span></span> | <span data-ttu-id="6c23f-195">Nederländska (Nederländerna)</span><span class="sxs-lookup"><span data-stu-id="6c23f-195">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="6c23f-196">pt-BR</span><span class="sxs-lookup"><span data-stu-id="6c23f-196">pt-BR</span></span> | <span data-ttu-id="6c23f-197">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="6c23f-197">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="6c23f-198">tr-TR</span><span class="sxs-lookup"><span data-stu-id="6c23f-198">tr-TR</span></span> | <span data-ttu-id="6c23f-199">Turkiska (Turkiet)</span><span class="sxs-lookup"><span data-stu-id="6c23f-199">Turkish (Turkey)</span></span> |
| <span data-ttu-id="6c23f-200">zh-CN</span><span class="sxs-lookup"><span data-stu-id="6c23f-200">zh-CN</span></span> | <span data-ttu-id="6c23f-201">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="6c23f-201">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="6c23f-202">Felsökning</span><span class="sxs-lookup"><span data-stu-id="6c23f-202">Troubleshooting</span></span>

<span data-ttu-id="6c23f-203">Om du har problem med att logga in på eller använda Teams-appen Dynamics 365 Human Resources kan du försöka följa dessa instruktioner för felsökning.</span><span class="sxs-lookup"><span data-stu-id="6c23f-203">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="6c23f-204">Om du fortfarande har problem efter felsökningen kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="6c23f-204">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="6c23f-205">För mer information, se [Få support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="6c23f-205">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="6c23f-206">Det går inte att logga in på Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-206">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="6c23f-207">Om du inte kan logga in i appen är det möjligt att det konto du använder för att logga in i Microsoft Teams inte är associerat med en medarbetarpost i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6c23f-207">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6c23f-208">Kontakta systemadministratören för att se till att din medarbetarpost är korrekt associerad.</span><span class="sxs-lookup"><span data-stu-id="6c23f-208">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="6c23f-209">Översättningarna visas inte korrekt</span><span class="sxs-lookup"><span data-stu-id="6c23f-209">Translations don't display correctly</span></span>

<span data-ttu-id="6c23f-210">Om översättningarna inte visas som förväntat ser du till att det språk du väljer i Teams matchar det språk som valts i personal **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-210">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="6c23f-211">I Teams, titta på **Appspråket** i **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-211">In Teams, look at **App language** in **Settings**.</span></span>

![Teams-inställningar](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="6c23f-213">I personal, välj **Inställningar** och sedan **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="6c23f-213">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="6c23f-214">Kontrollera att fältet **Språk** matchar fältet i fältet **Appspråk** i Teams.</span><span class="sxs-lookup"><span data-stu-id="6c23f-214">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Användaralternativ för personal](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="6c23f-216">Hör av dig om du fortfarande upplever översättningsproblem.</span><span class="sxs-lookup"><span data-stu-id="6c23f-216">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="6c23f-217">Mer information finns i [Få support för Finance and Operations-appar eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="6c23f-217">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="6c23f-218">Fel vid godkännande av tjänstledighetsbegäranden i Personal-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-218">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="6c23f-219">Om du får ett fel när du försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du testa följande åtgärder för felsökning:</span><span class="sxs-lookup"><span data-stu-id="6c23f-219">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="6c23f-220">Kontrollera att det konto som du använder för att logga in Microsoft Teams är det som du använder för att komma åt Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6c23f-220">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="6c23f-221">Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="6c23f-221">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="6c23f-222">Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="6c23f-222">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a><span data-ttu-id="6c23f-223">Låt godkännare inte ta emot Teams-chattmeddelanden med syfte att godkänna tjänstledighetsansökningar</span><span class="sxs-lookup"><span data-stu-id="6c23f-223">Leave approvers don't receive Teams chat messages to approve leave requests</span></span>

1. <span data-ttu-id="6c23f-224">Kontrollera att meddelanden har aktiverats för miljön och användaren.</span><span class="sxs-lookup"><span data-stu-id="6c23f-224">Ensure notifications are enabled for the environment and the user.</span></span> <span data-ttu-id="6c23f-225">Mer information finns i [Aktivera meddelanden för appen Personal i Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) och [Slå på/stäng av aviseringar för Teams för enskilda användare](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span><span class="sxs-lookup"><span data-stu-id="6c23f-225">For more information, see [Enable notifications for the Human Resources app in Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) and [Turn Teams notifications on or off for individual users](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span></span>

2. <span data-ttu-id="6c23f-226">Se till att användarna är inloggade på fliken **Chattar** med samma autentiseringsuppgifter som när de godkänner tjänstledighetsansökningar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-226">Ensure users are signed into the **Chats** tab with the same credentials they use for approving leave requests.</span></span> <span data-ttu-id="6c23f-227">Använd meddelandena "logga ut" och sedan "logga in" för att logga in med rätt autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="6c23f-227">Use the messages "sign out" and then "sign in" to sign in with the correct credentials.</span></span>

3. <span data-ttu-id="6c23f-228">Om problemet kvarstår kontrollerar du statusen för batchjobbet i Business Events-systemet som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="6c23f-228">If the issue persists, check the status of the Business Events system batch job as a system administrator.</span></span> <span data-ttu-id="6c23f-229">Om denna befinner sig i en väntande eller en utförande fast försöker du igen om några minuter.</span><span class="sxs-lookup"><span data-stu-id="6c23f-229">If it's in a waiting or executing stage, check back in a few minutes.</span></span> <span data-ttu-id="6c23f-230">Om statusen inte ändras skapar du en supportbegäran så att vårt team kan hjälpa till att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="6c23f-230">If the status remains unchanged, log a support ticket so our team can help resolve the issue.</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="6c23f-231">Kända tillgänglighetsproblem</span><span class="sxs-lookup"><span data-stu-id="6c23f-231">Known accessibility issues</span></span>

<span data-ttu-id="6c23f-232">Appen Personal i Team har följande tillgänglighetsproblem som vi arbetar med att åtgärda i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="6c23f-232">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="6c23f-233">Utleverans</span><span class="sxs-lookup"><span data-stu-id="6c23f-233">Issue</span></span> | <span data-ttu-id="6c23f-234">Lösning eller förklaring</span><span class="sxs-lookup"><span data-stu-id="6c23f-234">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="6c23f-235">Om du zoomar till 400 % på skrivbordet döljs vissa av åtgärdsknapparna i vyn.</span><span class="sxs-lookup"><span data-stu-id="6c23f-235">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="6c23f-236">Vi rekommenderar att du använder en skärmförstorare istället för att använda den här zoomningsnivån.</span><span class="sxs-lookup"><span data-stu-id="6c23f-236">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="6c23f-237">Under fliken **Ledighet** tillkännager VoiceOver en knappåtgärd samtidigt som rubriken för ledighetsrutnätet läses upp.</span><span class="sxs-lookup"><span data-stu-id="6c23f-237">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="6c23f-238">Rubriken och elementen i rutnätet är grupperade efter år och de är döljbara.</span><span class="sxs-lookup"><span data-stu-id="6c23f-238">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="6c23f-239">Med VoiceOver tolkas detta som en åtgärdsbar artikel, men det är inte det.</span><span class="sxs-lookup"><span data-stu-id="6c23f-239">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="6c23f-240">Under fliken **Ledighet** finns en extra svepgest när du navigerar till **Orsakskod** i en ny begäran.</span><span class="sxs-lookup"><span data-stu-id="6c23f-240">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="6c23f-241">Det finns ingen dold kontroll som svepnavigeringen försöker nå.</span><span class="sxs-lookup"><span data-stu-id="6c23f-241">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="6c23f-242">Under fliken **Ledighet**, om du sveper när kalendern är öppen, hamnar du utanför kontrollen istället för längst upp i en ny begäran eller när du redigerar en begäran.</span><span class="sxs-lookup"><span data-stu-id="6c23f-242">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="6c23f-243">När du kommer till **Gå till idag**, se det som slutet på kontrollen och svep i motsatt riktning för att komma tillbaka till toppen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-243">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="6c23f-244">Under fliken **Chatt** hoppar fokus tillbaka till toppen när du anger ett datum samtidigt som du använder hjälpverktyget eller tangentbordsnavigeringen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-244">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="6c23f-245">TABB tills du kommer till inmatningsområdet igen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-245">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="6c23f-246">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6c23f-246">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="6c23f-247">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="6c23f-247">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="6c23f-248">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågeställningen eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="6c23f-248">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="6c23f-249">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="6c23f-249">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="6c23f-250">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="6c23f-250">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="6c23f-251">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet, avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="6c23f-251">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="6c23f-252">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="6c23f-252">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="6c23f-253">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="6c23f-253">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="6c23f-254">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6c23f-254">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6c23f-255">LUIS-tjänsten har endast åtkomst till användarfrågeställningarna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en frågeställning som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="6c23f-255">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="6c23f-256">Innehållet i användarens frågeställningar och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="6c23f-256">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="6c23f-257">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="6c23f-257">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="6c23f-258">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6c23f-258">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="6c23f-259">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="6c23f-259">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="6c23f-260">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Personal har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="6c23f-260">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="6c23f-261">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="6c23f-261">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="6c23f-262">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-262">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="6c23f-263">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="6c23f-263">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="6c23f-264">Medan du samtalar med chattroboten i Personal-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c23f-264">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="6c23f-265">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Personal har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="6c23f-265">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="6c23f-266">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="6c23f-266">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="6c23f-267">Om du vill begränsa åtkomsten till Personal-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="6c23f-267">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c23f-268">Se även</span><span class="sxs-lookup"><span data-stu-id="6c23f-268">See also</span></span>

[<span data-ttu-id="6c23f-269">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-269">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="6c23f-270">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="6c23f-270">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="6c23f-271">Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="6c23f-271">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
