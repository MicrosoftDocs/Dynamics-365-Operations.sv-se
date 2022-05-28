---
title: Dynamics 365 Finance, Supply Chain Management och Commerce i US Government Community Cloud (GCC)
description: Det här ämnet innehåller information om Microsoft Dynamics 365 US Government-produkter som är tillgängliga för kvalificerade myndigheter och privata enheter.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 204bf1886ff7f7393fba5713a54f305274f540d0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693320"
---
# <a name="dynamics-365-finance-supply-chain-management-and-commerce-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance, Supply Chain Management och Commerce i US Government Community Cloud (GCC)

[!include [banner](../includes/banner.md)]



Välj Microsoft Dynamics 365 US Government-produkter är tillgängliga för kvalificerade myndigheter och privata enheter. Dessa enheter är begränsade till följande typer:

- Amerikansk federal, delstat, lokala, urbefolknings- och regionala entiteter
- Privata enheter som använder Dynamics 365 US Government för att tillhandahålla lösningar till myndighetsenheter eller kvalificerade medlemmar i molnbaserade gruppen
- Privata enheter som har kunddata som omfattas av myndighetsregleringar och Dynamics 365 US Government är den lämpliga tjänsten för att uppfylla de lagstadgade kraven

Mer information finns i [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Registrering

För att slutföra den första introduktionen för ett implementeringsprojekt i Microsoft Dynamics Lifecycle Services (LCS), följ instruktionerna i [Integrera ett implementeringsprojekt](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Använd emellertid inte länken till offentlig LCS som finns i de här instruktionerna. Använd istället följande URL för att öppna LCS för US Government Community Cloud (GCC): <https://gov.lcs.microsoftdynamics.us>.

När den initiala introduktionen är slutförd följer du instruktionerna i [Projektregistrering](../lifecycle-services/project-onboarding.md). Använd återigen [LCS för GCC](https://gov.lcs.microsoftdynamics.us) istället för offentlig LCS.

## <a name="environment-deployment"></a>Distribuera miljö

När du har slutfört introduktionen till projekt kan du granska den ytterligare kapaciteten hos LCS som beskrivs i [Lifecycle Services (LCS) för Ekonomi och Drift-programkunder](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Gå sedan vidare till miljödistributionen.

- Om du vill distribuera Microsoft-hanterade miljöer via LCS följer du instruktionerna i [Lifecycle Services (LCS) för Ekonomi och Drift-programkunder](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- För molnstyrda miljöer , se [Distribuera och få tillgång till utvecklingsmiljöer](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). Du måste också slutföra resurshanterarens onboardingprocess för dina anslutningar, enligt beskrivningen i [Slutför Azure Resource Manager integreringsprocess för US government Lifecycle Services-projekt](arm-onbarding-us-goverment.md).

> [!NOTE]
> För US Government LCS projekt stöds endast Azure Government-specifika Azure-prenumerationer.

## <a name="features-that-arent-available"></a>Funktioner som inte är tillgängliga

Vissa funktioner är inte tillgängliga för distribution i GCC eller så är de inte tillgängliga med Dynamics 365 i GCC. Till exempel Azure DevOps-tjänster kommer inte vara tillgängliga i GCC. Du kan dock använda lokala Azure DevOps eller offentliga  Azure DevOps tjänster. För detaljerad information om funktionernas tillgänglighet, se [Affärsappar US Government funktionstillgänglighet](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Stöds Dynamics 365 Finance och Dynamics 365 Supply Chain Management i GCC-High?

Nej Dynamics 365 Finance och Dynamics 365 Supply Chain Management stöds bara i GCC.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Kan jag använda offentlig Azure DevOps med Ekonomi och Supply Chain Management i GCC?

Ja, du kan använda offentliga Azure DevOps-tjänster om du inte har några krav på en lösning som är certifierad av Federal Risk and Authorization Management Program (FEDRAMP). Du kan också använda Azure DevOps server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Kan jag distribuera en molnstyrd miljö för nivå-1-utvecklingsmiljö i ett kommersiellt Azure Commercial-abonnemang?

Nej I [LCS för GCC](https://gov.lcs.microsoftdynamics.us) måste du använda ett Azure Government-abonnemang på att distribuera en miljö med molnbaserad värd.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Vad kan jag göra om jag behöver ett paket från biblioteket gemensam tillgång, men det är inte tillgängligt i LCS för GCC?

Du kan hämta samma paket från biblioteket gemensamma tillgångar i [offentlig LCS](https://lcs.dynamics.com). Din partner kan också hjälpa dig att hämta paketet.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Är koduppgraderingsverktyget tillgängligt i GCC?

Nej, koduppgraderingsverktyget är för närvarande inte tillgängligt i GCC. Du kan dock skapa ett potentiellt projekt i [public LCS](https://lcs.dynamics.com) och använda verktyget för koduppgradering. Observera att du inte kan distribuera miljöer i potentiell kundprojekt.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Kan min partner öppna en supportbiljett åt mig?

Ja. Om din partner använder en icke GCC-identitet skickas supportbiljetten till den allmänna supportkön. Vi rekommenderar att du använder kundens GCC-berättigande i LCS för att öppna supportbiljetter.

## <a name="see-also"></a>Se även

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Tillgänglighet för affärsappar US Government funktioner](https://aka.ms/BAPFunctionalParity).
- [Användarhandbok för Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Molndistribution – översikt](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
