---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
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
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428838"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="88663-103">Hantera ansökningar om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="88663-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="88663-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="88663-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="88663-105">Du kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="88663-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="88663-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="88663-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="88663-107">Installera appen</span><span class="sxs-lookup"><span data-stu-id="88663-107">Install the app</span></span>

<span data-ttu-id="88663-108">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="88663-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="88663-109">I Microsoft Teams väljer du de tre punkterna (...).</span><span class="sxs-lookup"><span data-stu-id="88663-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Punkter i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="88663-111">Sök efter Dynamics 365 Human Resources och välj sedan panelen **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="88663-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![HR-panel i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="88663-113">Välj knappen **Lägg till** om du vill installera appen.</span><span class="sxs-lookup"><span data-stu-id="88663-113">Select the **Add** button to install the app.</span></span>

   ![Instalaltion av Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="88663-115">Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.</span><span class="sxs-lookup"><span data-stu-id="88663-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Fliken Inställningar i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="88663-117">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="88663-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="88663-118">Om du har till gång till mer än en instans av Human Resources kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="88663-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="88663-119">Appen stöder för närvarande inte säkerhetsrollen Systemadministratör, och ett felmeddelande visas om du loggar in med ett systemadministratörskonto.</span><span class="sxs-lookup"><span data-stu-id="88663-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="88663-120">Om du vill logga in med ett annat konto väljer du fliken **Inställningar**, knappen **Byt konto** och loggar sedan in med ett användarkonto som inte har systemadministratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="88663-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="88663-121">Använd roboten</span><span class="sxs-lookup"><span data-stu-id="88663-121">Use the bot</span></span>

<span data-ttu-id="88663-122">När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.</span><span class="sxs-lookup"><span data-stu-id="88663-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Robotvälkomstmeddelande i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="88663-124">När du interagerar med roboten för första gången måste du kanske logga in.</span><span class="sxs-lookup"><span data-stu-id="88663-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="88663-125">Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="88663-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="88663-126">Du kan be roboten att:</span><span class="sxs-lookup"><span data-stu-id="88663-126">You can ask the bot to:</span></span>

- <span data-ttu-id="88663-127">Visa saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till.</span><span class="sxs-lookup"><span data-stu-id="88663-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Visa saldo i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="88663-129">Visa ytterligare information om en viss tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="88663-129">Show additional details about a specific leave type.</span></span>

   ![Visa information i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="88663-131">Påbörja en ledighetsbegäran åt dig.</span><span class="sxs-lookup"><span data-stu-id="88663-131">Start a leave request for you.</span></span>

   ![Begär tjänstledighet i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="88663-133">När du har startat en begäran om tjänstledighet kan du justera dagarna direkt på kortet, eller också kan du välja **Redigera information** för att lägga till ytterligare information i din begäran.</span><span class="sxs-lookup"><span data-stu-id="88663-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![Redigera begäran i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="88663-135">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="88663-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="88663-136">Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="88663-136">You can also type **Save as draft** to come back to it later.</span></span>

![Skicka in begäran i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="88663-138">Hantera din ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="88663-138">Manage your leave in Teams</span></span>

<span data-ttu-id="88663-139">På fliken **Ledighet** kan du visa:</span><span class="sxs-lookup"><span data-stu-id="88663-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="88663-140">Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till</span><span class="sxs-lookup"><span data-stu-id="88663-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="88663-141">Kommande ansökningar om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="88663-141">Upcoming leave requests</span></span>

- <span data-ttu-id="88663-142">Ansökningar om ledighet</span><span class="sxs-lookup"><span data-stu-id="88663-142">Time-off requests</span></span>

- <span data-ttu-id="88663-143">Utkast till ansökan om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="88663-143">Draft leave requests</span></span>

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="88663-145">Skapa en ny ansökan</span><span class="sxs-lookup"><span data-stu-id="88663-145">Create a new request</span></span>

1. <span data-ttu-id="88663-146">Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.</span><span class="sxs-lookup"><span data-stu-id="88663-146">To create a new leave request, select **New request**.</span></span>

   ![Ny ansökan i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="88663-148">Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="88663-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Lägg till ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="88663-150">Ange en orsakskod vid behov.</span><span class="sxs-lookup"><span data-stu-id="88663-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="88663-151">Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="88663-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="88663-152">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="88663-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="88663-153">Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="88663-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="88663-154">Hantera ansökningsutkast</span><span class="sxs-lookup"><span data-stu-id="88663-154">Manage draft requests</span></span>

1. <span data-ttu-id="88663-155">Välj fliken **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="88663-155">Select the **Drafts** tab.</span></span>

   ![Fliken Utkast i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="88663-157">Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.</span><span class="sxs-lookup"><span data-stu-id="88663-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="88663-158">Utför erforderliga ändringar.</span><span class="sxs-lookup"><span data-stu-id="88663-158">Make any necessary changes.</span></span> <span data-ttu-id="88663-159">När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="88663-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="88663-160">Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.</span><span class="sxs-lookup"><span data-stu-id="88663-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Redigera utkast i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="88663-162">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="88663-162">Privacy notice</span></span>

<span data-ttu-id="88663-163">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="88663-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="88663-164">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="88663-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="88663-165">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="88663-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="88663-166">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="88663-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="88663-167">Denna information överförs sedan till Microsofts [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/) , som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="88663-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="88663-168">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="88663-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="88663-169">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88663-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="88663-170">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="88663-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="88663-171">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="88663-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="88663-172">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="88663-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="88663-173">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="88663-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="88663-174">Se även</span><span class="sxs-lookup"><span data-stu-id="88663-174">See also</span></span>

[<span data-ttu-id="88663-175">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88663-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="88663-176">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="88663-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="88663-177">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="88663-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
