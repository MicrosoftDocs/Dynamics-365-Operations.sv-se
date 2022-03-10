---
title: Hantera ansökningar om ledighet i Teams
description: I det här avsnittet beskrivs hur du begär ledighet i Dynamics 365 Human Resources-appen i Microsoft Teams.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d004e33d01dbd171626d7e23f93df081bc0210a9
ms.sourcegitcommit: 70ac76be31bab7ed5e93f92f4683e65031fbdf85
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2021
ms.locfileid: "7924757"
---
# <a name="manage-leave-requests-in-teams"></a>Hantera begäranden om ledighet i Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Med hjälp av Dynamics 365 Human Resources-appen i Microsoft Teams kan du snabbt begära ledighet och visa information om ditt ledighetssaldo direkt i Microsoft Teams. Du kan använda en robot för att begära information och påbörja en begäran om att lämna en begäran. Fliken **Ledighet** visar mer detaljerad information. Du kan dessutom skicka personuppgifter om din kommande ledighet i Teams och chattar utanför Personal-appen.

## <a name="install-the-app"></a>Installera appen

Du hittar appen Dynamics 365 Human Resources i Teams-butiken.

1. I Microsoft Teams, navigera till listan med appar.
 
2. Sök efter Dynamics 365 Human Resources och välj sedan panelen **Personal**.

> [!NOTE]
> Från och med 20 december 2021 kommer Personal-app för robottjänster (version 1.1.4) som finns i Microsofts innehavare att inaktiveras. Det senaste filnamnstillägget (version 1.1.5) är tillgängligt för installation. Mer information finns i [Hantera ansökan om tjänstledighet i Teams](hr-admin-teams-leave-app.md#update-app).

3. Välj knappen **Lägg till** om du vill installera appen.

Om appen inte logga in dig automatiskt väljer du fliken **Inställningar** för att logga in.

> [!NOTE]
> Om du inte ser någon dialogruta för inloggning uppdaterar du dina webbläsarinställningar så att dessa tillåter popup-fönster. 

Om du har till gång till mer än en instans av Personal kan du välja vilken miljö du vill ansluta till på fliken **Inställningar**.

> [!NOTE]
> Appen har nu stöd för säkerhetsrollen systemadministratör.
 
## <a name="use-the-bot"></a>Använd roboten

När appen har installerats visas ett välkomstmeddelande som anger vilka typer av åtgärder roboten kan vidta för din räkning.

> [!NOTE]
> När du först interagerar med roboten måste du kanske logga in. Om du inte ser någon dialogruta för inloggning uppdaterar du dina webbläsarinställningar så att dessa tillåter popup-fönster.

Du kan be roboten att:

- Visa aktuella tjänstledighetssaldon. Skicka till exempel ett meddelande där det står "Visa tjänstledighetssaldon".

- Påbörja en ledighetsbegäran åt dig. Skicka till exempel ett meddelande där det står "Ta ledigt" eller "Jag vill ta semester nästa torsdag och fredag" för att vara mer specifik när du begär tjänstledighet av semestertyp. 

  ![Starta en tjänstledighetsbegäran i Teams-chatten.](./media/hr-teams-leave-app-initiate.png)

- Chattroboten fyller i en tjänstledighetsbegäran för dig. Välj **Begär ledig tid** och redigera informationen för din förfrågan.

   Om du vill skicka tjänstledighetsansökningar för flera tjänstledighetstyper för samma datum väljer du alternativet **Dela dag med** från menyn **Fler alternativ**. 

   Om du väljer en halvdagsledighet när tjänstledighetsenheten är i dagar, kan du ange om du vill begära ledighet från den första halvan av dagen eller den andra halvan av dagen genom att välja alternativet **Halvdagsdefinition** på menyn **Fler alternativ**.
   
   ![Halvdagsdefinitioner.](./media/HalfDayDefinitions.png)

- När du har redigerat informationen om din tjänstledighet väljer du **Skicka** för att skicka den för godkännande.

  ![Skicka ledighetsbegäran.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Hantera din ledighet i Teams

På fliken **Ledighet** kan du visa: 

- Saldoinformation om ledighet för varje tjänstledighetstyp som du är anmäld till

- Kommande ansökningar om tjänstledighet

- Ansökningar om ledig tid

- Utkast till ansökan om tjänstledighet
 
### <a name="create-a-new-request"></a>Skapa en ny ansökan

1. Skapa en ny ledighetsansökan genom att välja **Ny ansökan**.

2. Ange den dag eller de dagar som du vill ta ledigt och välj sedan **Lägg till**.

   ![Lägg till ledighet i Personal Teams-appen för tjänstledighet.](./media/TimeOffHours.png)

3. Ange en orsakskod vid behov. Skriv även eventuella kommentarer och lägg till eventuella bifogade filer.

4. Välj alternativ **Dela dag med** från menyn **Fler alternativ** om du vill skicka flera ledighetsförfrågningar för samma datum för olika ledighetstyper.

5. Välj alternativet **Halvdagsdefinition** om du vill ange om du vill begära ledigt den första halvan av dagen eller den andra arbetsdagen. Det här alternativet är tillgängligt när enheten för ledighetsförfrågan är i dagar och beloppet som begärts är 0,5 dagar.

6. När du är klar med att mata in information väljer du **Skicka in** för att skicka in den för godkännande. Du kan också skriva **Spara som utkast** om du vill komma tillbaka till den senare.

### <a name="manage-draft-requests"></a>Hantera ansökningsutkast

1. Välj fliken **Utkast**.

2. Välj blyertspennan om du vill redigera ansökan, eller välj papperskorgen om du vill ta bort ansökan.

3. Utför erforderliga ändringar. När du är klar med att mata in information skriver du **Skicka in** för att skicka in den för godkännande. Du kan också välja **Spara som utkast** om du vill komma tillbaka till den senare.
   
### <a name="respond-to-teams-notifications"></a>Svara på Teams-meddelanden

När du eller en medarbetare som du är godkännare för skickar in en begäran om ledighet får du ett meddelande i Personal-appen i Teams. Du kan välja meddelandet om du vill visa begäran om ledighet. Meddelanden visas också i området **Chatt** .

Om du är en godkännare kan du välja **Godkänn** eller **Neka** i meddelandet. Du kan också ange ett valfritt meddelande.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Skicka kommande ledighetsinformation till dina medarbetare

När du har installerat Personal-appen för Teams kan du enkelt skicka information om din kommande ledighet till dina medarbetare i grupper eller chattar.

1. I ett team eller chatt i Teams väljer du Personal-knappen under chattfönstret.

   ![Personal-knappen under chattfönstret.](./media/hr-teams-leave-app-chat-button.png)

2. Välj den begäran som du vill dela. Om du vill dela ett utkast till en ledighetsansökan väljer du **utkast** först.

Din ledighetsansökan visas i chatten.

Om du har delat en utkastbegäran visas det som ett utkast.

## <a name="view-your-teams-leave-calendar"></a>Visa ditt teams ledighetskalender

Om du är chef med underställda kan du visa teamets godkända och väntande ledighet.

1. I Personal-appen i Teams, välj **Ledighet**.

2. Välj **teamkalender** . Kalendern visar dina underställdas godkända och väntande ledighet.

   > [!NOTE]
   > Om du inte kan se teamkalendern ber du administratören att aktivera den. För mer information, se [Installera och konfigurera](hr-admin-teams-leave-app.md#install-and-setup).

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

## <a name="troubleshooting"></a>Felsökning

Om du har problem med att logga in på eller använda Teams-appen Dynamics 365 Human Resources kan du försöka följa dessa instruktioner för felsökning. Om du fortfarande har problem efter felsökningen kontaktar du supporten. För mer information, se [Få support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Det går inte att logga in på Personal-appen i Teams

Om du inte kan logga in i appen är det möjligt att det konto du använder för att logga in i Microsoft Teams inte är associerat med en medarbetarpost i Dynamics 365 Human Resources. Kontakta systemadministratören för att se till att din medarbetarpost är korrekt associerad.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>Det går inte att hitta Dynamics 365 Human Resources-miljön bland inställningarna

Om du inte kan välja korrekt Dynamics 365-miljö kanske användarposten inte har synkroniserats korrekt. Kontakta systemadministratören om du vill skapa användarposten på nytt och koppla den till användarreferenserna. Försök sedan att logga in på Personal-programmet Microsoft Teams under några minuter.

### <a name="translations-dont-display-correctly"></a>Översättningarna visas inte korrekt

Om översättningarna inte visas som förväntat ser du till att det språk du väljer i Teams matchar det språk som valts i personal **Användaralternativ**.

I Teams, titta på **Appspråket** i **Inställningar**.

![Teams-inställningar.](./media/hr-teams-leave-app-settings.png)

I personal, välj **Inställningar** och sedan **Användaralternativ**. Kontrollera att fältet **Språk** matchar fältet i fältet **Appspråk** i Teams.

![Användaralternativ för personal.](./media/hr-teams-leave-app-user-options.png)

Hör av dig om du fortfarande upplever översättningsproblem. Mer information finns i [Få support för Finance and Operations-appar eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Fel vid godkännande av tjänstledighetsbegäranden i Personal-appen i Teams

Om du får ett fel när du försöker godkänna tjänstledighetsbegäranden i Teams-appen ska du testa följande åtgärder för felsökning:

1. Kontrollera att det konto som du använder för att logga in Microsoft Teams är det som du använder för att komma åt Dynamics 365 Human Resources.

2. Kontrollera att de är giltiga godkännare för begäran genom att kontrollera arbetsflödesinställningarna för att godkännande av tjänstledighet. Mer information om att lämna arbetsflöden för förfrågningar finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Låt godkännare inte ta emot Teams-chattmeddelanden med syfte att godkänna tjänstledighetsansökningar

1. Kontrollera att meddelanden har aktiverats för miljön och användaren. Mer information finns i [Aktivera meddelanden för appen Personal i Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) och [Slå på/stäng av aviseringar för Teams för enskilda användare](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Se till att användarna är inloggade på fliken **Chattar** med samma autentiseringsuppgifter som när de godkänner tjänstledighetsansökningar. Använd meddelandena "logga ut" och sedan "logga in" för att logga in med rätt autentiseringsuppgifter.

3. Om problemet kvarstår kontrollerar du statusen för batchjobbet i **Business Events-systemet** som systemadministratör. Om denna befinner sig i **Väntande** eller **Utförande** fas ber vi dig att återkomma om några minuter. Om statusen inte ändras skapar du en supportbegäran så att vårt team kan hjälpa till att lösa problemet.

## <a name="known-accessibility-issues"></a>Kända tillgänglighetsproblem

Appen Personal i Team har följande tillgänglighetsproblem som vi arbetar med att åtgärda i framtida versioner.

| Utleverans | Lösning eller förklaring |
| --- | --- |
| Om du zoomar till 400 % på skrivbordet döljs vissa av åtgärdsknapparna i vyn. | Vi rekommenderar att du använder en skärmförstorare istället för att använda den här zoomningsnivån. |
| På fliken **Ledighet** tillkännager VoiceOver en knappåtgärd samtidigt som den avläser sidhuvudet för ledighetsrutnätet. | Sidhuvudet och elementen i rutnätet är grupperade efter år och kan döljas. VoiceOver tolkar denna presentation som en åtgärdsbar artikel, men det är den inte. |
| Under fliken **Ledighet** finns en extra svepgest när du navigerar till **Orsakskod** i en ny begäran. | Det finns ingen dold kontroll som svepnavigeringen försöker nå. |
| Under fliken **Ledighet**, om du sveper när kalendern är öppen, hamnar du utanför kontrollen istället för längst upp i en ny begäran eller när du redigerar en begäran. | När du kommer till **Gå till idag**, se det som slutet på kontrollen och svep i motsatt riktning för att komma tillbaka till toppen. |
| Under fliken **Chatt** hoppar fokus tillbaka till toppen när du anger ett datum samtidigt som du använder hjälpverktyget eller tangentbordsnavigeringen. | TABB tills du kommer till inmatningsområdet igen. |

## <a name="privacy-notice"></a>Sekretesspolicy

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Med Dynamics 365 Human Resources-roboten i Microsoft Teams analyseras användarens textinmatningar i syfte att förstå den underliggande frågeställningen eller avsikten. Användarens indata, t.ex. "Sök konto Contoso", vidarebefordras till en av Microsofts kognitiva tjänster som kallas LUIS (Language Understanding Intelligent Service). Läs mer om LUIS [här](https://www.luis.ai/). LUIS-tjänsten disambiguerar eller förstår syftet med användarindata (i det här fallet är avsikten att hitta information) och målentiteten (i det här fallet är den avsedda entiteten ett konto med namnet Contoso). Denna information överförs sedan till Microsofts [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/)  som samverkar med data från Dynamics 365 Human Resources och hämtar den önskade informationen för användarfrågan. 

Genom att installera och tillåta åtkomst till robotprogrammet godkänner du att LUIS-tjänsten och Azure Bot Framework kan bearbeta avsikten bakom inmatningen, vilket leder till en förbättrad användarupplevelse i konversationen. LUIS-tjänsten och Azure Bot Framework kan ha varierande nivåer av kompatibilitet jämfört med Dynamics 365 Human Resources. Även om LUIS-tjänsten endast har åtkomst till användarfrågorna och inte utformats för att vara ansluten till användarens Dynamics 365 Human Resources-data eller -konto, kan en en användare av Dynamics 365 Human Resources-roboten frivilligt ange en fråga som innehåller kunddata, personliga data eller andra data, och detta frågeinnehåll kan komma att skickas till LUIS-tjänsten och Azure Bot Framework. 

Innehållet i användarens frågeställningar och meddelanden behålls i LUIS-systemet under högst 30 dagar, är krypterat i vila och används inte för utbildning eller serviceförbättring. Läs mer om kognitiva tjänster [här](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Om du vill hantera administrationsinställningar för appar i Microsoft Teams går du till administratörscentret för [Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid och Azure Cosmos DB

När du använder Dynamics 365 Human Resources-appen i Microsoft Teams  kan vissa kunddata komma flöda utanför det geografiska område där din klientorganisations personaltjänst har distribuerats.

Dynamics 365 Human Resources överför medarbetarens begäran om tjänstledighet och arbetsflödesuppgifter till Microsoft Azure Event Grid och Microsoft Teams . Dessa data kan lagras i Microsoft Azure Event Grid i upp till 24 timmar och bearbetas i USA, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar. Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Medan du samtalar med chattroboten i Personal-appen kan konversationsinnehållet lagras i Azure Cosmos DB och skickas till Microsoft Teams. Denna data kan lagras i Azure i Cosmos DB i upp till 24 timmar och kan bearbetas utanför det geografiska område där klientorganisationens Personal har distribuerats, krypteras i transit och vila och används inte av Microsoft eller dess under processer för utbildning eller serviceförbättringar. Mer information om var dina data lagras i Teams finns i: [plats för data i Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Om du vill begränsa åtkomsten till Personal-appen personal i Microsoft Teams för din organisation eller dina användare inom organisationen läser du [Hantera principer för programbehörigheter i Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Se även

[Ladda ned och installera Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams-hjälpcenter](https://support.office.com/teams)</br>
[Personal-app i Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
