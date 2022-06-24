---
title: Provision Microsoft Teams från Dynamics 365 Commerce
description: I denna artikel beskrivs hur du etablerar Microsoft Teams med hjälp av organisationsdata från Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3dc9d0f20ec251f0908dda0017adaaeac1b43856
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868945"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Provision Microsoft Teams från Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du etablerar Microsoft Teams med hjälp av organisationsdata från Dynamics 365 Commerce.

Dynamics 365 Commerce erbjuder ett enkelt sätt att tillhandahålla Teams om du ännu inte har ställt in team för dina detaljhandelsbutiker där. Genom att dra nytta av väldefinierad information från Commerce som du vill använda i Teams kan du hjälpa butiksanställda att komma igång i Teams. Den här informationen omfattar organisationshierarkin, butiksnamn, medarbetarinformation Azure Active Directory och (Azure AD) konton. 

Processen för reservering av Teams har två huvudsteg:

1. I Teams skapar du ett team för varje butik och lägger till butiksarbetare som medlemmar i rätt team. Om en anställd är associerad med mer än en butik kommer teammedlemskapet att återspegla detta faktum. Ett kommunikationsteam med regionala chefer som medlemmar skapas för att publicera uppgifter från Teams.
1. Överför organisationshierarkin från Commerce till Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Provision Teams i Commerce headquarters

Innan du provision Microsoft Teams måste du utföra följande uppgifter:

- Bekräfta att alla regionchefer har kommunikationschefer.
- Bekräfta att Azure-kontot för alla butikschefer och den anställda har associerats med chefens eller arbetarens arbetarpost i Commerce headquarters.

Följ de här stegen om du vill etablera Teams i Commerce headquarters.

1. Öppna **Butik och handel \> Kanalinställningar \> Microsoft Teams integreringskonfiguration**.
1. Klicka på **Provision Teams** i åtgärdsfönstret. Ett batchjobb som kallas **Teams Provision** skapas.
1. Gå till **Systemadministration \> Förfrågningar \> Batch-jobb** och hitta det senaste jobbet som har beskrivningen **Teams-etablering**. Vänta tills körningen är klar för det här jobbet.

> [!TIP]
> Om ingen av dina regionchefer, butikschefer och butiksarbetare har associerats med en Teams-licens kan du få följande felmeddelande: "Det gick inte att hämta tillämpliga SKU-kategorier för användaren." Välj för att rätta till problemet **Synkronisera team och medlemmar** i åtgärdsfönstret.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Validera Teams-etablering i administratörscentret för Teams

Om du validera Microsoft Teams etablering i Microsoft Teams administrationscentret gör du på följande sätt.
    
1. Gå till [Teams administratörscenter](https://admin.teams.microsoft.com/) och logga in som administratör för din näthandelsklient.
1. I det vänstra navigeringsfönstret väljer du **Teams** för att öppna och sedan **Hantera team**.
1. Bekräfta att ett team har skapats för varje Commerce butik.
1. Markera ett team och bekräfta att butiksarbetare har lagts till som medlemmar i gruppen.
1. I vänstra navigeringsfönstret, välj **Användare** och bekräfta att alla butiksanställda i alla butiker har lagts till som användare.

I följande illustration visas ett exempel på sidan **Hantera team** i Teams administratörscenter.

![Exempel på sidan Hantera team i administrationscentret för Teams.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Överför en Commerce organisationshierarki till Teams
    
Commerce organisationshierarki kan användas för Microsoft Teams för att publicera uppgifter i alla eller valda butiker som använder samma hierarkistruktur.

Så här överför du en Commerce organisationshierarki till Teams.
    
1. I Commerce headquarters, gå till **Butik och handel \> Kanalinställning \> Microsoft Teams integreringskonfiguration**.
1. Välj **Hämta målhierarki** och välj sedan **Retail Stores by Region** om du vill hämta filen med kommaavgränsade värden (CSV) i organisationshierarkin.
1. Installera modulen Microsoft TeamsPowerShell genom att följa stegen i [Installera Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).
1. När du uppmanas i Teams PowerShell-fönster, logga in med administratörskontot för din Azure AD klientorganisation.
1. Följ stegen i [Ställ in din teaminriktningshierarki](/microsoftteams/set-up-your-team-hierarchy) om du vill överföra CSV-filen för målhierarkin.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Kontrollera att organisationshierarkin har överförts till Teams

Kontrollera att organisationshierarkin har överförts till Microsoft Teams med följande steg.

1. Logga in i Teams som kommunikationschef.
1. I det navigeringsfönstret, välj **Uppgifter av Planner**.
1. På fliken **Publicerade listor** skapar du en ny lista som har en dummy-uppgift.
1. Markera **Publicera**. Organisationshierarkin bör visas i dialogrutan **Välj vem som ska publicera till** som visas i exemplet i illustrationen nedan.

![Exempel på en organisationshierarki i dialogrutan Välj vem som ska publiceras till.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce och Microsoft Teams-integrering, översikt](commerce-teams-integration.md)

[Aktivera Dynamics 365 Commerce och Microsoft Teams-integrering](enable-teams-integration.md)

[Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Mappa butiker och team om det finns befintliga team i Microsoft Teams](map-stores-existing-teams.md)

[Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integrering](teams-integration-faq.md)