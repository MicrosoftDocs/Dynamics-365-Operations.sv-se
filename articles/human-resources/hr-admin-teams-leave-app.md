---
title: Human Resources-app i Teams
description: Detta avsnitt introducerar Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
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
ms.openlocfilehash: 33322b9b553076125695f257b201463e9d8275c6
ms.sourcegitcommit: e27510ba52623c801353eed4853f8c0aeea3bb2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3828924"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="6e776-103">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="6e776-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6e776-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e776-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="6e776-105">Personalen kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="6e776-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="6e776-106">Fliken **Ledighet** ger detaljerade information. Dessutom kan de skicka människor information om kommande ledigheter i Teams och chatta utanför Human Resources-appen.</span><span class="sxs-lookup"><span data-stu-id="6e776-106">The **Time off** tab provides more detailed information.In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

![Kort för ledighetsansökan i Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="6e776-110">Installera och konfigurera</span><span class="sxs-lookup"><span data-stu-id="6e776-110">Install and setup</span></span>

<span data-ttu-id="6e776-111">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="6e776-111">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="6e776-112">Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="6e776-112">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="6e776-113">Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="6e776-113">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="6e776-114">Aktivera meddelanden för Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="6e776-114">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="6e776-115">Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6e776-115">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="6e776-116">Endast användare som är inloggade i Teams och som använder Human Resources Teams-appen får meddelandena.</span><span class="sxs-lookup"><span data-stu-id="6e776-116">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="6e776-117">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="6e776-117">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="6e776-118">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="6e776-118">Select **Links**.</span></span>

3. <span data-ttu-id="6e776-119">Under **Inställningar**, välj **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="6e776-119">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="6e776-120">På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .</span><span class="sxs-lookup"><span data-stu-id="6e776-120">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="6e776-122">Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.</span><span class="sxs-lookup"><span data-stu-id="6e776-122">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="6e776-124">Aktivera eller inaktivera Teams-meddelanden för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="6e776-124">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="6e776-125">När du har aktiverat meddelanden för Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="6e776-125">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="6e776-126">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="6e776-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="6e776-127">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="6e776-127">Select **Links**.</span></span>

3. <span data-ttu-id="6e776-128">Under **Användare**, välj **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="6e776-128">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="6e776-129">Välj fliken **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="6e776-129">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="6e776-130">Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.</span><span class="sxs-lookup"><span data-stu-id="6e776-130">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="6e776-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6e776-132">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6e776-133">Kända problem</span><span class="sxs-lookup"><span data-stu-id="6e776-133">Known issues</span></span>

| <span data-ttu-id="6e776-134">Utleverans</span><span class="sxs-lookup"><span data-stu-id="6e776-134">Issue</span></span> | <span data-ttu-id="6e776-135">Status</span><span class="sxs-lookup"><span data-stu-id="6e776-135">Status</span></span> |
| --- | --- |
| <span data-ttu-id="6e776-136">Vågrät rullning fungerar inte på Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="6e776-136">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="6e776-137">Vågrät rullning är inte ett problem med iOS eller stationära enheter.</span><span class="sxs-lookup"><span data-stu-id="6e776-137">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="6e776-138">Vi arbetar på en korrigering för Android.</span><span class="sxs-lookup"><span data-stu-id="6e776-138">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="6e776-139">Saldot är felaktigt när ledighet skickas in för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="6e776-139">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="6e776-140">Prognosticering är ännu ej tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6e776-140">Forecasting isn't yet available.</span></span> <span data-ttu-id="6e776-141">Saldot visas för det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="6e776-141">The balance displays for the current date.</span></span> |
| <span data-ttu-id="6e776-142">Det går inte att avbryta en **Granskas**-begäran.</span><span class="sxs-lookup"><span data-stu-id="6e776-142">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="6e776-143">Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version.</span><span class="sxs-lookup"><span data-stu-id="6e776-143">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="6e776-144">Information om saldo beräknas från och med idag.</span><span class="sxs-lookup"><span data-stu-id="6e776-144">Balance information is calculated as of today.</span></span> | <span data-ttu-id="6e776-145">Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="6e776-145">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="6e776-146">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6e776-146">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="6e776-147">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="6e776-147">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="6e776-148">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="6e776-148">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="6e776-149">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="6e776-149">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="6e776-150">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="6e776-150">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="6e776-151">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="6e776-151">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="6e776-152">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="6e776-152">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="6e776-153">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="6e776-153">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="6e776-154">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6e776-154">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6e776-155">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="6e776-155">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="6e776-156">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="6e776-156">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="6e776-157">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="6e776-157">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="6e776-158">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6e776-158">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="6e776-159">Microsoft Teams, Azure Event Grid och Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="6e776-159">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="6e776-160">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Human Resources har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="6e776-160">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="6e776-161">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="6e776-161">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="6e776-162">Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="6e776-162">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="6e776-163">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="6e776-163">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="6e776-164">Medan du samtalar med chattroboten i Human Resources-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e776-164">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="6e776-165">Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Human Resources har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="6e776-165">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="6e776-166">Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="6e776-166">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="6e776-167">Om du vill begränsa åtkomsten till Human Resources-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="6e776-167">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e776-168">Se även</span><span class="sxs-lookup"><span data-stu-id="6e776-168">See also</span></span> 

[<span data-ttu-id="6e776-169">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e776-169">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="6e776-170">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="6e776-170">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="6e776-171">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="6e776-171">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

