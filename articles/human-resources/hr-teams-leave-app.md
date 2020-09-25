---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
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
ms.openlocfilehash: 0fbf44fe35af3147fd5fb478b6cbfc5a5d0b109d
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766770"
---
# <a name="manage-leave-requests-in-teams"></a>Hantera ansökningar om ledighet i Teams

[!include [banner](includes/preview-feature.md)]

Med hjälp av Microsoft Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams. Du kan interagera med en robot för att begära information. Fliken **Ledighet** visar mer detaljerad information.

## <a name="install-the-app"></a>Installera appen

Du hittar appen Human Resources i Teams-butiken.

1. I Microsoft Teams väljer du de tre punkterna (...).

   ![Punkter i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-ellipses.png)
 
2. Sök efter Dynamics 365 Human Resources och välj sedan panelen **Human Resources**.

   ![HR-panel i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-human-resources-tile.png)

3. Välj knappen **Lägg till** om du vill installera appen.

   ![Instalaltion av Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-in-store.png)

Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.

![Fliken Inställningar i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster. 

Om du har till gång till mer än en instans av Human Resources kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.

> [!WARNING]
> Appen stöder för närvarande inte säkerhetsrollen Systemadministratör, och ett felmeddelande visas om du loggar in med ett systemadministratörskonto. Om du vill logga in med ett annat konto väljer du fliken **Inställningar**, knappen **Byt konto** och loggar sedan in med ett användarkonto som inte har systemadministratörsbehörighet.
 
## <a name="use-the-bot"></a>Använd roboten

När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.

![Robotvälkomstmeddelande i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> När du interagerar med roboten för första gången måste du kanske logga in. Om du inte ser någon dialogruta för inloggning kontrollerar du att webbläsarinställningarna tillåter popup-fönster.

Du kan be roboten att:

- Visa saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till.

   ![Visa saldo i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-balances.png)
 
- Visa ytterligare information om en viss tjänstledighetstyp.

   ![Visa information i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-details.png)

- Påbörja en ledighetsbegäran åt dig.

   ![Begär tjänstledighet i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-request.png)
 
När du har startat en ledighetsansökan kan du justera dagarna direkt på kortet.

![Redigera begäran i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-edit.png)
 
När du är klar med att mata in information väljer du **Skicka in** för att skicka in den för godkännande. Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.

![Skicka in begäran i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Hantera din ledighet i Teams

På fliken **Ledighet** kan du visa:

- Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till

- Kommande ansökningar om tjänstledighet

- Ansökningar om ledighet

- Utkast till ansökan om tjänstledighet

![Fliken Ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Skapa en ny ansökan

1. Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.

   ![Ny ansökan i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.

   ![Lägg till ledighet i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Ange en orsakskod vid behov. Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.

4. När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande. Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.

### <a name="manage-draft-requests"></a>Hantera ansökningsutkast

1. Välj fliken **Utkast**.

   ![Fliken Utkast i Human Resources Teams-appen för ledighet](./media/hr-teams-leave-app-drafts-tab.png)

2. Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.

3. Utför erforderliga ändringar. När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande. Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.

   ![Redigera utkast i Human Resources Teams-appen för tjänstledighet](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="teams-notifications"></a>Teams-meddelanden

När du eller en arbetare är godkännare för att skicka en begäran om ledighet får du ett meddelande i Human Resources-appen i Teams. Du kan välja meddelandet om du vill visa det. Meddelanden visas också i området **Chatt** .

Om du är en godkännare kan du välja **Godkänn** eller **Neka** i meddelandet. Du kan också ange ett valfritt meddelande.

![Meddelande om ledighetsansökan i Human Resources Teams-appen](./media/hr-teams-leave-app-notification.png)

## <a name="view-your-teams-leave-calendar"></a>Visa ditt teams ledighetskalender

Om du är chef med underställda kan du visa teamets godkända och väntande ledighet.

1. I Human Resources-appen i Teams, välj **Ledighet**.

2. Välj **teamkalender** .

   ![Visa kalender i Human Resources Teams-app](./media/hr-teams-leave-app-view-calendar.png)

Kalendern visar dina underställdas godkända och väntande ledighet.

![Ledighetskalender i Human Resources Teams-app](./media/hr-teams-leave-app-calendar.png)

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
[Human Resources-app i Teams](hr-admin-teams-leave-app.md)
