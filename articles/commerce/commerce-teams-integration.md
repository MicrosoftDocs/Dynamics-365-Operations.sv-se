---
title: Dynamics 365 Commerce och Microsoft Teams-integrering, översikt
description: Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 39de59d182fd6f4cb1616a47a09b44cd249f2187
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984205"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Dynamics 365 Commerce och Microsoft Teams-integrering, översikt

[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.

Dynamics 365 Commerce integrerar med Teams för att hjälpa kunder och deras medarbetare att förbättra produktiviteten genom att synkronisera uppgiftshantering mellan de två programmen. Den sömlösa uppgiftshantering som Commerce and Teams-integrationen tillhandahåller, gör att butikschefer och medarbetare kan skapa uppgiftslistor, tilldela uppgifter till flera butiker och spåra status för uppgifter mellan butiker, från antingen programmet eller program.

Commerce and Teams-integration är tillgänglig i Commerce version 10.0.18 som finns tillgänglig.

## <a name="key-features"></a>Nyckelfunktioner

Här är några av de nyckelfunktioner som finns i Commerce och Microsoft Teams-integration:

- Etablera Teams genom att dra nytta av väldefinierad information från Commerce, till exempel organisationsstrukturen och information om butiker, arbetare, behörigheter och affärssammanhang.
- Synkronisera enkelt pågående ändringar (till exempel tillägg av nya butiker eller anställning av nya medarbetare) mellan Commerce och Teams, men behåll Commerce som huvudkälla för organisationsstrukturdata.
- Integrera uppgiftshantering mellan Commerce och Teams om du vill hjälpa butiksarbetare, butikschefer, regionala chefer och kommunikationschefer att hantera uppgiftshantering från antingen program.

## <a name="prerequisites-for-using-integration-features"></a>Förutsättningar för användning av integrationsfunktioner

Följande förutsättningar måste uppfyllas innan du kan börja använda Microsoft Teams integrationsfunktionerna:

- Microsoft 365 Business Standard-licens (denna licens inkluderar Teams.)
- Azure Active Directory ( Azure AD) konton för alla butikschefer och medarbetare
- Kassasystem som är konfigurerade med Azure AD-autentisering

## <a name="conceptual-architecture"></a>Konceptuell arkitektur

följande bild visas den konceptuella arkitekturen för Dynamics 365 Commerce och Microsoft Teams-integration, med en San Francisco-butik som exempel. Både Teams och kassaprogrammet Commerce använder Microsoft Planner som en databas så att uppgifter som publiceras från Teams visas i kassaprogrammet och ad hoc-uppgifter som skapas av butikschefer i kassaprogrammet visas i Teams, vilket leder till en sömlös uppgiftshanteringserfarenhet mellan programmen.    

![Arkitektur för Commerce- och Teams-integrering.](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivera Dynamics 365 Commerce och Microsoft Teams-integration](enable-teams-integration.md)

[Provision Microsoft Teams från Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Mappa butiker och team om det finns befintliga team i Microsoft Teams](map-stores-existing-teams.md)

[Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration](teams-integration-faq.md)
