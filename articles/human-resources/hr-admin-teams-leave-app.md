---
title: Personal-app i Teams
description: Detta avsnitt introducerar Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c1cceb15d64215cb8d5c996df792e863d466f87d
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053573"
---
# <a name="human-resources-app-in-teams"></a>Personal-app i Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams. Personalen kan interagera med en robot för att begära information. Fliken **Ledighet** visar mer detaljerad information. Dessutom kan de skicka personuppgifter om kommande ledighet i team och chattar utanför Personal-appen.

![Personal Teams-approbot för tjänstledighet](./media/hr-teams-leave-app-bot.png)

![Fliken Ledighet i Personal Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

![Kort för ledighetsansökan i Personal](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Installera och konfigurera

Du hittar appen Dynamics 365 Human Resources i Teams-butiken. Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).

Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

Om du vill att användarna ska visa tjänstledighets- och frånvarokalendern i programmet måste du aktivera **tjänstledighets- och frånvarokalendern i Teams** i funktionshanteringen. Mer information om hur du aktiverar funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Aktivera meddelanden för Personal-appen i Teams

Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Dynamics 365 Human Resources.

>[!NOTE]
>Endast användare som är inloggade i Teams och som använder Dynamics 365 Human Resources Teams-appen får meddelandena.

1. I Personal, välj **Systemadministration**.

2. Markera **länkar**

3. Under **Inställningar**, välj **Systemparametrar**.

4. På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Aktivera eller inaktivera Teams-meddelanden för enskilda användare

När du har aktiverat meddelanden för Dynamics 365 Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.

1. I Personal, välj **Systemadministration**.

2. Markera **länkar**

3. Under **Användare**, välj **Användaralternativ**.

4. Välj fliken **Arbetsflöde**.

5. Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. Välj **Spara**.

## <a name="supported-languages"></a>Språk som stöds

Dynamics 365 Human Resources-appen i Teams har stöd för följande språk:

| Språk-ID | Språk |
| --- | --- |
| de-DE | Tyska (Tyskland) |
| es-ES | Spanska (Spanien) |
| es-MX | Spanska (Mexiko) |
| fr-CA | Franska (Kanada) |
| fr-FR | Franska (Frankrike) |
| it-IT | Italienska (Italien) |
| nl-NL | Nederländska (Nederländerna) |
| pt-BR | Portugisiska (Brasilien) |
| tr-TR | Turkiska (Turkiet) |
| zh-CN | Kinesiska (förenklad) |

## <a name="notes"></a>Anteckningar

Följande arbetsobjekt planeras för kommande versioner:

| Arbetsuppgift | Status |
| --- | --- |
| Saldot är felaktigt när ledighet skickas in för ett framtida datum. | Prognosticering är ännu ej tillgänglig. Saldot visas för det aktuella datumet. |
| Det går inte att avbryta en **Granskas**-begäran. | Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version. |
| Information om saldo beräknas från och med idag. | Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet. |

## <a name="troubleshooting"></a>Felsökning

Om en användare har problem med att logga in på eller använda appen Personal Teams kan du försöka följa dessa instruktioner för felsökning. Om du fortfarande har problem efter felsökningen kontaktar du supporten. För mer information, se [Få support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Det går inte att logga in på Personal-appen i Teams

Om en användare kontaktar dig eftersom de inte kan logga in i appen, kontrollerar du att de har en associerad medarbetarpost i Personal.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Fel vid godkännande av tjänstledighetsbegäranden i Personal-appen i Teams

Om en användare får ett fel när han eller hon försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du utföra följande åtgärder för felsökning:

1. Kontrollera att deras Teams-konton är samma som de använder för att få tillgång till Personal.

2. Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet. Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Låt godkännare inte ta emot Teams-chattmeddelanden med syfte att godkänna tjänstledighetsansökningar

1. Kontrollera att meddelanden har aktiverats för miljön och användaren. Mer information finns i [Aktivera meddelanden för appen Personal i Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) och [Slå på/stäng av aviseringar för Teams för enskilda användare](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Se till att användarna är inloggade på fliken **Chattar** med samma autentiseringsuppgifter som när de godkänner tjänstledighetsansökningar. Använd meddelandena "logga ut" och sedan "logga in" för att logga in med rätt autentiseringsuppgifter.

3. Om problemet kvarstår kontrollerar du statusen för batchjobbet i Business Events-systemet som systemadministratör. Om denna befinner sig i en väntande eller en utförande fast försöker du igen om några minuter. Om statusen inte ändras skapar du en supportbegäran så att vårt team kan hjälpa till att lösa problemet.

## <a name="privacy-notice"></a>Sekretesspolicy

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågeställningen eller avsikten. Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service). Läs mer om LUIS [här](https://www.luis.ai/). LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet, avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso). Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan.

Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen. LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources. LUIS-tjänsten har endast åtkomst till användarfrågeställningarna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en frågeställning som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket. 

Innehållet i användarens frågeställningar och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring. Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid och Azure Cosmos DB

När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Microsoft Teams kan vissa kunddata flöda utanför det geografiska område där medarbetarens Personal har distribuerats.

Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams . Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar. Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Medan du samtalar med chattroboten i Personal-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams. Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Personal har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar. Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Om du vill begränsa åtkomsten till Personal-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Se även 

[Ladda ned och installera Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams-hjälpcenter](https://support.office.com/teams)</br>
[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]