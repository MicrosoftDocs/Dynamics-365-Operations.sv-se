---
title: Human Resources-app i Teams
description: Detta avsnitt introducerar Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388126"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="2a8b7-103">Human Resources-app i Teams</span><span class="sxs-lookup"><span data-stu-id="2a8b7-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2a8b7-104">Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="2a8b7-105">Personalen kan interagera med en robot för att begära information.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="2a8b7-106">Fliken **Ledighet** visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-106">The **Time off** tab provides more detailed information.</span></span>

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="2a8b7-109">Installera och konfigurera</span><span class="sxs-lookup"><span data-stu-id="2a8b7-109">Install and setup</span></span>

<span data-ttu-id="2a8b7-110">Du hittar appen Human Resources i Teams-butiken.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="2a8b7-111">Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="2a8b7-112">Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="2a8b7-113">Kända problem</span><span class="sxs-lookup"><span data-stu-id="2a8b7-113">Known issues</span></span>

| <span data-ttu-id="2a8b7-114">Utfärda</span><span class="sxs-lookup"><span data-stu-id="2a8b7-114">Issue</span></span> | <span data-ttu-id="2a8b7-115">Status</span><span class="sxs-lookup"><span data-stu-id="2a8b7-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="2a8b7-116">Saldot är felaktigt när ledighet skickas in för ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="2a8b7-117">Prognosticering är ännu ej tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="2a8b7-118">Saldot visas för det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="2a8b7-119">När du minskar antalet timmar som har ägnats i en befintlig begäran går **Återstående saldo** ner istället för upp.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="2a8b7-120">Vi kommer att lösa detta välkända problem i framtiden.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="2a8b7-121">Visningen är felaktig, men de korrekta beloppen justeras vid överföringen.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="2a8b7-122">Två **Kommande ledighet**-kort visas för samma datum.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="2a8b7-123">Korten representerar enskilda inlämningar.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-123">The cards represent individual submissions.</span></span> <span data-ttu-id="2a8b7-124">Vi kommer även fortsatt att ta emot feedback och göra justeringar.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="2a8b7-125">Det går inte att avbryta en **Granskas**-begäran.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="2a8b7-126">Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="2a8b7-127">Information om saldo beräknas från och med idag.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="2a8b7-128">Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="2a8b7-129">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="2a8b7-129">Privacy notice</span></span>

<span data-ttu-id="2a8b7-130">Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="2a8b7-131">Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="2a8b7-132">Läs mer om LUIS [här](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="2a8b7-133">LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="2a8b7-134">Denna information överförs sedan till Microsofts [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/) , som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="2a8b7-135">Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="2a8b7-136">LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2a8b7-137">LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="2a8b7-138">Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="2a8b7-139">Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="2a8b7-140">Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="2a8b7-141">Se även</span><span class="sxs-lookup"><span data-stu-id="2a8b7-141">See also</span></span> 

[<span data-ttu-id="2a8b7-142">Ladda ned och installera Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a8b7-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="2a8b7-143">Microsoft Teams-hjälpcenter</span><span class="sxs-lookup"><span data-stu-id="2a8b7-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="2a8b7-144">Hantera ansökningar om ledighet i Teams</span><span class="sxs-lookup"><span data-stu-id="2a8b7-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

