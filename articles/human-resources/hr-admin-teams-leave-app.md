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
# <a name="human-resources-app-in-teams"></a>Human Resources-app i Teams

[!include [banner](includes/preview-feature.md)]

Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams. Personalen kan interagera med en robot för att begära information. Fliken **Ledighet** visar mer detaljerad information.

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Installera och konfigurera

Du hittar appen Human Resources i Teams-butiken. Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).

Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Aktivera meddelanden för Human Resources-appen i Teams

Om du vill att användarna ska få lämna meddelanden i appen Teams måste du aktivera meddelanden i Human Resources.

>[!NOTE]
>Endast användare som är inloggade i Teams och som använder Human Resources Teams-appen får meddelandena.

1. I Personal, välj **Systemadministration**.

2. Markera **länkar**

3. Under **Inställningar**, välj **Systemparametrar**.

4. På fliken **Allmänt** anger du **Aktivera meddelanden för Teams-appen** till **Ja** .

   ![Aktivera Teams-appmeddelanden i systemparametrar](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Om du vill aktivera Teams-meddelanden för alla användare väljer du **Ja** vid prompten.

   ![Aktivera Teams-meddelanden för alla användare](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Aktivera eller inaktivera Teams-meddelanden för enskilda användare

När du har aktiverat meddelanden för Human Resources Teams-appen kan du aktivera eller inaktivera meddelanden för enskilda användare.

1. I Personal, välj **Systemadministration**.

2. Markera **länkar**

3. Under **Användare**, välj **Användaralternativ**.

4. Välj fliken **Arbetsflöde**.

5. Ange **Aktivera meddelanden för Teams-app** till **Ja** för att aktivera aviseringar för användaren eller **Nej** för att inaktivera meddelanden för användaren.

   ![Aktivera Teams-appmeddelanden på fliken arbetsflöde i användaralternativ](./media/hr-admin-teams-leave-app-notifications.png)

6. Välj **Spara**.

## <a name="known-issues"></a>Kända problem

| Utleverans | Status |
| --- | --- |
| Vågrät rullning fungerar inte på Android-telefoner | Vågrät rullning är inte ett problem med iOS eller stationära enheter. Vi arbetar på en korrigering för Android. |
| Fel: det finns ett problem med att hitta en miljö att ansluta till. | Det här felet kan visas även om du har kontrollerat att användaren har åtkomst till en eller flera personalmiljöer. Dessutom kanske du inte ser alla miljöer som du förväntar dig. Innan vi åtgärdar det här problemet ska du ta bort användaren och sedan importera dem igen för att lösa problemet. |
| Saldot är felaktigt när ledighet skickas in för ett framtida datum. | Prognosticering är ännu ej tillgänglig. Saldot visas för det aktuella datumet. |
| Det går inte att avbryta en **Granskas**-begäran. | Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version. |
| Information om saldo beräknas från och med idag. | Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet. |

## <a name="privacy-notice"></a>Sekretesspolicy

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten. Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service). Läs mer om LUIS [här](https://www.luis.ai/). LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso). Denna information överförs sedan till [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan. 

Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen. LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources. LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket. 

Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring. Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a>Microsoft Azure Event Grid och Microsoft Teams

När du använder meddelandefunktionen för Dynamics 365 Human Resources-appen i Teams, kommer vissa kunddata att flöda utanför det geografiska område där medarbetarens Human Resources har distribuerats. Dynamics 365 Human Resources överför medarbetarens information om tjänstledighet och arbetsflödes uppgifter till Microsoft Azure Event Grid och Microsoft Teams . Dessa data kan lagras i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar.

## <a name="see-also"></a>Se även 

[Ladda ned och installera Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams-hjälpcenter](https://support.office.com/teams)</br>
[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md)

