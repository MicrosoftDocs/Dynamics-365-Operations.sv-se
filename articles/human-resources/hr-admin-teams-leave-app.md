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
# <a name="human-resources-app-in-teams"></a>Human Resources-app i Teams

[!include [banner](includes/preview-feature.md)]

Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan personalen snabbt begära ledighet och visa information om sitt ledighetssaldo i Microsoft Teams. Personalen kan interagera med en robot för att begära information. Fliken **Ledighet** visar mer detaljerad information.

![Human Resources Teams-approbot för tjänstledighet](./media/hr-admin-teams-leave-app-bot.png)

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Installera och konfigurera

Du hittar appen Human Resources i Teams-butiken. Mer information om hur du installerar Teams-appen finns i [Hantera tjänstledighetsansökningar i Teams](hr-teams-leave-app.md).

Information om hur du hanterar appbehörigheter i Teams finns i [Hantera policyer för appbehörigheter i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="known-issues"></a>Kända problem

| Utfärda | Status |
| --- | --- |
| Saldot är felaktigt när ledighet skickas in för ett framtida datum. | Prognosticering är ännu ej tillgänglig. Saldot visas för det aktuella datumet. |
| När du minskar antalet timmar som har ägnats i en befintlig begäran går **Återstående saldo** ner istället för upp. | Vi kommer att lösa detta välkända problem i framtiden. Visningen är felaktig, men de korrekta beloppen justeras vid överföringen. |
| Två **Kommande ledighet**-kort visas för samma datum. | Korten representerar enskilda inlämningar. Vi kommer även fortsatt att ta emot feedback och göra justeringar. |
| Det går inte att avbryta en **Granskas**-begäran. | Den här funktionen stöds för närvarande inte, men kommer att läggas till i en framtida version. |
| Information om saldo beräknas från och med idag. | Systemet visar för närvarande inte saldon per periodiseringsperioden, även om det har konfigurerats bland parametrarna för Tjänstledighet. |

## <a name="privacy-notice"></a>Sekretesspolicy

Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågan eller avsikten. Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service). Läs mer om LUIS [här](https://www.luis.ai/). LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso). Denna information överförs sedan till Microsofts [Azure-robotramverk](https://azure.microsoft.com/services/bot-service/) , som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan. 

Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure-robotramverket kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen. LUIS-tjänsten och Azure-robotramverket kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources. LUIS-tjänsten har endast åtkomst till användarfrågorna och är inte utformad för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, och en användare av Dynamics 365 Human Resources-roboten kan frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure-robotramverket. 

Innehållet i användarens frågor och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring. Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Se även 

[Ladda ned och installera Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams-hjälpcenter](https://support.office.com/teams)</br>
[Hantera ansökningar om ledighet i Teams](hr-teams-leave-app.md)

