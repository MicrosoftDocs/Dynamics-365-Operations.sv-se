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
ms.openlocfilehash: e714be06984f399235f0799ef077a92deae64d9e
ms.sourcegitcommit: b0aa724a18ab1fbb5a62925f048c54b2c676ebf4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "4476087"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="cf91f-103">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="cf91f-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cf91f-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="cf91f-105">Personalen kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="cf91f-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="cf91f-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="cf91f-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="cf91f-107">Dessutom kan de skicka personuppgifter om kommande ledighet i team och chattar utanför Human Resources-appen.</span><span class="sxs-lookup"><span data-stu-id="cf91f-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

![Kort för ledighetsansökan i Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="cf91f-111">Installera och konfigurera</span><span class="sxs-lookup"><span data-stu-id="cf91f-111">Install and setup</span></span>

<span data-ttu-id="cf91f-112">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="cf91f-112">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="cf91f-113">Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="cf91f-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="cf91f-114">Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="cf91f-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="cf91f-115">Aktivera meddelanden för Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-115">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="cf91f-116">Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cf91f-116">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="cf91f-117">Endast användare som är inloggade i Teams och som använder Human Resources Teams-appen får meddelandena.</span><span class="sxs-lookup"><span data-stu-id="cf91f-117">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="cf91f-118">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-118">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="cf91f-119">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="cf91f-119">Select **Links**.</span></span>

3. <span data-ttu-id="cf91f-120">Under **Inställningar**, välj **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-120">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="cf91f-121">På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .</span><span class="sxs-lookup"><span data-stu-id="cf91f-121">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="cf91f-123">Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.</span><span class="sxs-lookup"><span data-stu-id="cf91f-123">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="cf91f-125">Aktivera eller inaktivera Teams-meddelanden för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="cf91f-125">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="cf91f-126">När du har aktiverat meddelanden för Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="cf91f-126">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="cf91f-127">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="cf91f-128">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="cf91f-128">Select **Links**.</span></span>

3. <span data-ttu-id="cf91f-129">Under **Användare**, välj **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-129">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="cf91f-130">Välj fliken **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-130">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="cf91f-131">Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.</span><span class="sxs-lookup"><span data-stu-id="cf91f-131">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="cf91f-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-133">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cf91f-134">Kända problem</span><span class="sxs-lookup"><span data-stu-id="cf91f-134">Known issues</span></span>

| <span data-ttu-id="cf91f-135">Utleverans</span><span class="sxs-lookup"><span data-stu-id="cf91f-135">Issue</span></span> | <span data-ttu-id="cf91f-136">Status</span><span class="sxs-lookup"><span data-stu-id="cf91f-136">Status</span></span> |
| --- | --- |
| <span data-ttu-id="cf91f-137">Saldot är felaktigt när ledighet skickas in för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="cf91f-137">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="cf91f-138">Prognosticering är ännu ej tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="cf91f-138">Forecasting isn't yet available.</span></span> <span data-ttu-id="cf91f-139">Saldot visas för det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="cf91f-139">The balance displays for the current date.</span></span> |
| <span data-ttu-id="cf91f-140">Det går inte att avbryta en **Granskas**-begäran.</span><span class="sxs-lookup"><span data-stu-id="cf91f-140">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="cf91f-141">Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version.</span><span class="sxs-lookup"><span data-stu-id="cf91f-141">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="cf91f-142">Information om saldo beräknas från och med idag.</span><span class="sxs-lookup"><span data-stu-id="cf91f-142">Balance information is calculated as of today.</span></span> | <span data-ttu-id="cf91f-143">Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="cf91f-143">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="cf91f-144">Felsökning</span><span class="sxs-lookup"><span data-stu-id="cf91f-144">Troubleshooting</span></span>

<span data-ttu-id="cf91f-145">Om en användare har problem med att logga in på eller använda appen Human Resources Teams kan du försöka följa dessa instruktioner för felsökning.</span><span class="sxs-lookup"><span data-stu-id="cf91f-145">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="cf91f-146">Om du fortfarande har problem efter felsökningen kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="cf91f-146">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="cf91f-147">För mer information, se [Få support](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="cf91f-147">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="cf91f-148">Det går inte att logga in på Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-148">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="cf91f-149">Om en användare kontaktar dig eftersom de inte kan logga in i appen, kontrollerar du att användaren har en associerad medarbetarpost i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cf91f-149">If a user contacts you because they can't sign into the app, verify that the user has an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="cf91f-150">Fel vid godkännande av tjänstledighetsbegäranden i Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-150">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="cf91f-151">Om en användare får ett fel när han eller hon försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du utföra följande åtgärder för felsökning:</span><span class="sxs-lookup"><span data-stu-id="cf91f-151">If a user receives an error while trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="cf91f-152">Kontrollera att deras Teams-konton är samma som de använder för att få tillgång till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cf91f-152">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="cf91f-153">Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="cf91f-153">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="cf91f-154">Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cf91f-154">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="cf91f-155">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="cf91f-155">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="cf91f-156">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="cf91f-156">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="cf91f-157">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="cf91f-157">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="cf91f-158">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="cf91f-158">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="cf91f-159">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="cf91f-159">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="cf91f-160">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="cf91f-160">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="cf91f-161">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="cf91f-161">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="cf91f-162">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="cf91f-162">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="cf91f-163">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cf91f-163">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="cf91f-164">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="cf91f-164">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="cf91f-165">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="cf91f-165">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="cf91f-166">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="cf91f-166">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="cf91f-167">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cf91f-167">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="cf91f-168">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="cf91f-168">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="cf91f-169">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Human Resources har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="cf91f-169">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="cf91f-170">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="cf91f-170">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="cf91f-171">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="cf91f-171">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="cf91f-172">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="cf91f-172">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="cf91f-173">Medan du samtalar med chattroboten i Human Resources-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cf91f-173">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="cf91f-174">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Human Resources har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="cf91f-174">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="cf91f-175">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="cf91f-175">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="cf91f-176">Om du vill begränsa åtkomsten till Human Resources-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="cf91f-176">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf91f-177">Se även</span><span class="sxs-lookup"><span data-stu-id="cf91f-177">See also</span></span> 

[<span data-ttu-id="cf91f-178">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-178">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="cf91f-179">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="cf91f-179">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="cf91f-180">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="cf91f-180">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

