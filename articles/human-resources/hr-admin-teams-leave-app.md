---
title: Human Resources-app i Teams
description: Detta avsnitt introducerar Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51f04e553da822c4e09d31bcd72c71b674ad1f1b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930027"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="e6fea-103">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e6fea-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e6fea-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="e6fea-105">Personalen kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="e6fea-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="e6fea-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="e6fea-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="e6fea-107">Dessutom kan de skicka personuppgifter om kommande ledighet i team och chattar utanför Human Resources-appen.</span><span class="sxs-lookup"><span data-stu-id="e6fea-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

![Kort för ledighetsansökan i Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="e6fea-111">Installera och konfigurera</span><span class="sxs-lookup"><span data-stu-id="e6fea-111">Install and setup</span></span>

<span data-ttu-id="e6fea-112">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="e6fea-112">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="e6fea-113">Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="e6fea-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="e6fea-114">Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="e6fea-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="e6fea-115">Aktivera meddelanden för Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-115">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="e6fea-116">Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e6fea-116">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="e6fea-117">Endast användare som är inloggade i Teams och som använder Human Resources Teams-appen får meddelandena.</span><span class="sxs-lookup"><span data-stu-id="e6fea-117">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="e6fea-118">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-118">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="e6fea-119">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="e6fea-119">Select **Links**.</span></span>

3. <span data-ttu-id="e6fea-120">Under **Inställningar**, välj **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-120">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="e6fea-121">På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .</span><span class="sxs-lookup"><span data-stu-id="e6fea-121">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="e6fea-123">Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.</span><span class="sxs-lookup"><span data-stu-id="e6fea-123">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="e6fea-125">Aktivera eller inaktivera Teams-meddelanden för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="e6fea-125">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="e6fea-126">När du har aktiverat meddelanden för Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="e6fea-126">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="e6fea-127">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="e6fea-128">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="e6fea-128">Select **Links**.</span></span>

3. <span data-ttu-id="e6fea-129">Under **Användare**, välj **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-129">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="e6fea-130">Välj fliken **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-130">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="e6fea-131">Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.</span><span class="sxs-lookup"><span data-stu-id="e6fea-131">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="e6fea-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e6fea-133">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e6fea-134">Kända problem</span><span class="sxs-lookup"><span data-stu-id="e6fea-134">Known issues</span></span>

| <span data-ttu-id="e6fea-135">Utleverans</span><span class="sxs-lookup"><span data-stu-id="e6fea-135">Issue</span></span> | <span data-ttu-id="e6fea-136">Status</span><span class="sxs-lookup"><span data-stu-id="e6fea-136">Status</span></span> |
| --- | --- |
| <span data-ttu-id="e6fea-137">Vågrät rullning fungerar inte på Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="e6fea-137">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="e6fea-138">Vågrät rullning är inte ett problem med iOS eller stationära enheter.</span><span class="sxs-lookup"><span data-stu-id="e6fea-138">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="e6fea-139">Vi arbetar på en korrigering för Android.</span><span class="sxs-lookup"><span data-stu-id="e6fea-139">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="e6fea-140">Saldot är felaktigt när ledighet skickas in för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="e6fea-140">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="e6fea-141">Prognosticering är ännu ej tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e6fea-141">Forecasting isn't yet available.</span></span> <span data-ttu-id="e6fea-142">Saldot visas för det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="e6fea-142">The balance displays for the current date.</span></span> |
| <span data-ttu-id="e6fea-143">Det går inte att avbryta en **Granskas**-begäran.</span><span class="sxs-lookup"><span data-stu-id="e6fea-143">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="e6fea-144">Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version.</span><span class="sxs-lookup"><span data-stu-id="e6fea-144">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="e6fea-145">Information om saldo beräknas från och med idag.</span><span class="sxs-lookup"><span data-stu-id="e6fea-145">Balance information is calculated as of today.</span></span> | <span data-ttu-id="e6fea-146">Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="e6fea-146">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="e6fea-147">Felsökning</span><span class="sxs-lookup"><span data-stu-id="e6fea-147">Troubleshooting</span></span>

<span data-ttu-id="e6fea-148">Om en användare har problem med att logga in på eller använda appen Human Resources Teams kan du försöka följa dessa instruktioner för felsökning.</span><span class="sxs-lookup"><span data-stu-id="e6fea-148">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="e6fea-149">Om du fortfarande har problem efter felsökningen kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e6fea-149">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="e6fea-150">För mer information, se [Få support](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="e6fea-150">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="e6fea-151">Det går inte att logga in på Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-151">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="e6fea-152">Om en användare kontaktar dig eftersom de inte kan logga in i appen, kontrollerar du att användaren har en associerad medarbetarpost i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e6fea-152">If a user contacts you because they can't sign into the app, verify that the user has an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="e6fea-153">Fel vid godkännande av tjänstledighetsbegäranden i Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-153">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="e6fea-154">Om en användare får ett fel när han eller hon försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du utföra följande åtgärder för felsökning:</span><span class="sxs-lookup"><span data-stu-id="e6fea-154">If a user receives an error while trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="e6fea-155">Kontrollera att deras Teams-konton är samma som de använder för att få tillgång till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e6fea-155">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="e6fea-156">Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="e6fea-156">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="e6fea-157">Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="e6fea-157">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="e6fea-158">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="e6fea-158">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="e6fea-159">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="e6fea-159">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="e6fea-160">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="e6fea-160">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="e6fea-161">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="e6fea-161">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="e6fea-162">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="e6fea-162">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="e6fea-163">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="e6fea-163">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="e6fea-164">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="e6fea-164">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="e6fea-165">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="e6fea-165">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="e6fea-166">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e6fea-166">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e6fea-167">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="e6fea-167">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="e6fea-168">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="e6fea-168">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="e6fea-169">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="e6fea-169">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="e6fea-170">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e6fea-170">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="e6fea-171">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="e6fea-171">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="e6fea-172">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Human Resources har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="e6fea-172">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="e6fea-173">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="e6fea-173">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="e6fea-174">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="e6fea-174">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="e6fea-175">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="e6fea-175">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="e6fea-176">Medan du samtalar med chattroboten i Human Resources-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e6fea-176">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="e6fea-177">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Human Resources har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="e6fea-177">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="e6fea-178">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="e6fea-178">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="e6fea-179">Om du vill begränsa åtkomsten till Human Resources-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="e6fea-179">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6fea-180">Se även</span><span class="sxs-lookup"><span data-stu-id="e6fea-180">See also</span></span> 

[<span data-ttu-id="e6fea-181">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-181">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="e6fea-182">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="e6fea-182">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="e6fea-183">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="e6fea-183">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

