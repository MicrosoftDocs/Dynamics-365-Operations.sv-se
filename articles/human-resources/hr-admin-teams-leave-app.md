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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776318"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="b5ecc-103">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="b5ecc-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="b5ecc-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="b5ecc-105">Personalen kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="b5ecc-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-106">The **Time off** tab provides more detailed information.</span></span>

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="b5ecc-109">Installera och konfigurera</span><span class="sxs-lookup"><span data-stu-id="b5ecc-109">Install and setup</span></span>

<span data-ttu-id="b5ecc-110">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="b5ecc-111">Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="b5ecc-112">Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="b5ecc-113">Aktivera meddelanden för Human Resources-appen i Teams</span><span class="sxs-lookup"><span data-stu-id="b5ecc-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="b5ecc-114">Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="b5ecc-115">Endast användare som är inloggade i Teams och som använder Human Resources Teams-appen får meddelandena.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="b5ecc-116">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b5ecc-117">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="b5ecc-117">Select **Links**.</span></span>

3. <span data-ttu-id="b5ecc-118">Under **Inställningar**, välj **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="b5ecc-119">På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .</span><span class="sxs-lookup"><span data-stu-id="b5ecc-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="b5ecc-121">Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="b5ecc-123">Aktivera eller inaktivera Teams-meddelanden för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="b5ecc-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="b5ecc-124">När du har aktiverat meddelanden för Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="b5ecc-125">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b5ecc-126">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="b5ecc-126">Select **Links**.</span></span>

3. <span data-ttu-id="b5ecc-127">Under **Användare**, välj **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="b5ecc-128">Välj fliken **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="b5ecc-129">Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="b5ecc-131">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b5ecc-132">Kända problem</span><span class="sxs-lookup"><span data-stu-id="b5ecc-132">Known issues</span></span>

| <span data-ttu-id="b5ecc-133">Utleverans</span><span class="sxs-lookup"><span data-stu-id="b5ecc-133">Issue</span></span> | <span data-ttu-id="b5ecc-134">Status</span><span class="sxs-lookup"><span data-stu-id="b5ecc-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="b5ecc-135">Vågrät rullning fungerar inte på Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="b5ecc-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="b5ecc-136">Vågrät rullning är inte ett problem med iOS eller stationära enheter.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="b5ecc-137">Vi arbetar på en korrigering för Android.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="b5ecc-138">Fel: det finns ett problem med att hitta en miljö att ansluta till.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="b5ecc-139">Det här felet kan visas även om du har kontrollerat att användaren har åtkomst till en eller flera personalmiljöer.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="b5ecc-140">Dessutom kanske du inte ser alla miljöer som du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="b5ecc-141">Innan vi åtgärdar det här problemet ska du ta bort användaren och sedan importera dem igen för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="b5ecc-142">Saldot är felaktigt när ledighet skickas in för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="b5ecc-143">Prognosticering är ännu ej tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="b5ecc-144">Saldot visas för det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="b5ecc-145">Det går inte att avbryta en **Granskas**-begäran.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="b5ecc-146">Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="b5ecc-147">Information om saldo beräknas från och med idag.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="b5ecc-148">Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="b5ecc-149">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="b5ecc-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="b5ecc-150">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="b5ecc-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="b5ecc-151">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="b5ecc-152">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="b5ecc-153">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="b5ecc-154">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="b5ecc-155">Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="b5ecc-156">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="b5ecc-157">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b5ecc-158">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="b5ecc-159">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="b5ecc-160">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="b5ecc-161">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b5ecc-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="b5ecc-162">Microsoft Azure Event Grid och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5ecc-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="b5ecc-163">När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Teams, kommer vissa kunddata att flöda utanför det geografiska område där medarbetarens Human Resources har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="b5ecc-164">Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="b5ecc-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="b5ecc-165">Dessa data kan lagras i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ecc-166">Se även</span><span class="sxs-lookup"><span data-stu-id="b5ecc-166">See also</span></span> 

[<span data-ttu-id="b5ecc-167">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5ecc-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="b5ecc-168">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="b5ecc-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="b5ecc-169">Hantera begäranden om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="b5ecc-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

