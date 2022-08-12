---
title: Tillhandahålla Personal i infrastrukturen för Ekonomi och drift
description: Den här artikeln innehåller information om hur du tillhandahåller en ny produktionsmiljö för Microsoft Dynamics 365 Human Resources i infrastrukturen för ekonomi och drift.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15060d8bdd598476081c22d7280319da3db0cb31
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178425"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Tillhandahålla Personal i infrastrukturen för Ekonomi och drift

_**Gäller för:** Personal i infrastrukturen för appen för ekonomi och drift_ 

> [!NOTE]
> Från och med 2022 juli kan nya Personal-miljöer inte tilldelas för den fristående Personal-infrastrukturen, och nya Microsoft Dynamics Lifecycle Services-projekt (LCS) kan inte skapas i den. Kunder kan distribuera Personalmiljöer på infrastruktur för ekonomi och drift.

Den här artikeln innehåller information om hur du tillhandahåller en ny produktionsmiljö för Microsoft Dynamics 365 Human Resources i infrastrukturen för ekonomi och drift.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara på plats innan du kan tillhandahålla en ny miljö:

- Du har köpt Personal via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). Om du har en befintlig Dynamics 365-licens som redan innehåller tjänsteplanen for Personal och du inte kan utföra stegen i denna artikel, kontakta då supporten.
- Den globala administratören har loggat in på [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com) och skapat ett nytt projekt for ekonomi och drift.

## <a name="provision-a-human-resources-trial-environment"></a>Skapa en utvärderingsmiljö för Personal

> [!NOTE]
> Från och med april 2022 finns inte utvärderingsmiljöerna för Personal tillgängliga i det fristående programmet. Potentiella kunder som är intresserade av att utvärdera Personalfunktionerna i apparna för ekonomi och drift kan använda gratisversionen på 30 dagar tillsammans med demodatan. Dynamics 365 Finance omfattar de Personalfunktioner som inkluderas i Ekonomiinfrastrukturen via sammanslagningen med det fristående programmet. Mer information finns i [Sammanslagning av Personalerbjudanden för samman funktioner för kunder](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Mer information om Dynamics 365 Finance-provversioner finns i [steg-för-steg-guiden](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>Planera Personal-miljöer

Innan du skapar din första Personal-miljö bör du noggrant planera miljöbehoven för ditt projekt. Ett basabonnemang på Personal innehåller två miljöer: en produktionsmiljö och en godkännandetestmiljö (sandbox-miljö) i standardutförande. Beroende på hur komplext ditt projekt är har du möjlighet att köpa in ytterligare miljöer för att kunna stödja projektaktiviteter.

Här följer några beaktanden vid ytterligare tillvalsmiljöer:

- **Datamigrering** – Datamigreringsaktiviteter gör att din sandbox-miljö kan användas i testsyfte under hela projektets gång. Om du har ytterligare en miljö kan datamigreringsaktiviteter fortsätta samtidigt som tester och konfigurationsaktiviteter sker i en annan miljö.
- **Integrering** – Konfigurera och testa integreringar som kan komma att omfatta inbyggda integreringar eller anpassade integreringar som exempelvis för lönesystem, sökandespårningssystem eller förmånssystem och leverantörer.
- **Utbildning** – Du kan komma att behöva en separat miljö som är konfigurerad med en uppsättning utbildningsdata, detta för att utbilda dina medarbetare i användningen av det nya systemet. 
- **Flerfasprojekt** – Du kan komma att behöva ytterligare en miljö för att stödja konfiguration, datamigrering, testning eller andra aktiviteter i en projektfas som planeras efter projektets ursprungliga publicering.
- **Utveckling** – I infrastrukturerna för ekonomi och drift kan du nu utöka lösningen och utveckla dina egna anpassningar. Alla utvecklare måste använda sin egen utvecklingsmiljö. För mer information, se [Distribuera och få tillgång till utvecklingsmiljöer](/fin-ops-core/dev-itpro/dev-tools/access-instances).
- **GOLD** – För nya distributioner är en gemensam metod att använda en separat GOLD-miljö som hålls orörd för konfiguration och datamigrering. Den här miljön kan användas i hela implementeringen för att uppdatera andra miljöer. Den används för att skapa den nya produktionsmiljön som har baskonfigurationen och datamigreringen. Du kan inte distribuera en produktionsmiljö på ekonomi- och driftinfrastrukturen förrän du har slutfört beredskapsprocessen för publicering. Mer information finns i [Förbered publicering](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> När det gäller dina miljöer rekommenderar vi följande metod:
>
> - Använd din standardmiljö för standardgodkännande (f.d. sandbox-miljö) eller någon annan miljö för att göra en fejkad övergång innan du kör publiceringen.
> - Upprätta en detaljerad övergångschecklista som inkluderar varje datapaket som krävs för att migrera den slutgiltiga datan till produktionsmiljön i samband med publiceringsövergången. Denna rekommendation är särskilt viktig om du inte har någon separat GULD-miljö för att lagra dina konfigurationer.
> - Använd din standardmiljö för godkännande av standardgodkännande (f.d. "sandbox"-miljö) eller någon annan Nivå 2-miljö eller högre som din TEST-miljö i hela projektet. Om du behöver fler miljöer kan din organisation köpa dem till en extra kostnad.

## <a name="create-an-lcs-project"></a>Skapa ett LCS-projekt

För att hantera dina Personal-miljöer med LCS måste först skapa ett LCS-projekt. Om du migrerar din Personalmiljö till infrastrukturen för ekonomi och drift måste du skapa ett nytt LCS-projekt för appar för ekonomi och drift. Mer information finns [Migrera din Personalmiljö](hr-admin-migrate-overview). Om du redan har ett LCS-projekt för andra appar för ekonomi och drift kan du aktivera personalfunktionerna i arbetsytan **Funktionshantering**. Mer information finns i [Översikt för funktionshantering](/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

När en ny kund registrerar sig för Personal omfattar abonnemanget en arbetsyta för Implementering av projekt. När kunden har aktiverat tjänsten måste klientorganisationens administratör logga in på <https://lcs.dynamics.com> med hjälp av klientorganisationskontot. Projektarbetsytan skapas automatiskt för organisationen. Mer information finns i [Lifecycle Services (LCS) för app-kunder för Ekonomi och drift](/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs).

> [!NOTE]
> För att säkerställa ett lyckat tillhandahållande måste det konto som du använder för att tillhandahålla Personal-miljön tilldelas antingen rollen **Systemadministratör** eller rollen **Systemanpassare** i den Power Apps-miljö som är kopplad till Personal-miljön. Mer information om hur du tilldelar säkerhetsroller till användare i Microsoft Power Platform finns i [Konfigurera användarsäkerhet för resurser](/power-platform/admin/database-security).

Du måste slutföra processen för registrering av LCS-projekt innan du kan börja distribuera miljöer. Mer information finns i [Projektregistrering](/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding). Mer information om hur du använder LCS finns i [användarhandboken för Lifecycle Services (LCS](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide)).

## <a name="deploy-human-resources-environments"></a>Distribuera Personal-miljöer

Distribution av appar för ekonomi och drift, inklusive Personal, i molnet kräver att du förstår vilken miljö och vilket abonnemang du distribuerar till, vem som kan utföra vilka uppgifter samt vilka data och anpassningar som du måste hantera. Vi rekommenderar att du använder ett tjänstekonto istället för en namngiven användare när du distribuerar nya miljöer. Mer information om hur du distribuerar miljöer i infrastrukturen för ekonomi och drift finns i [Översikt över molnbaserad distribution](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Om du vill distribuera en produktionsmiljö för Personal på infrastrukturen för ekonomi och drift måste du först slutföra beredskapsprocessen för publicering. Mer information finns i [Förbered publicering](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live). Denna process omfattar abonnemangsuppskattningen i LCS. Mer information finns i [Abonnemangsuppskattning](/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integrera Microsoft Power Platform med Personal

Microsoft Power Platform tillhandahåller en serie funktioner för Dynamics 365-program via administrationscentret för Power Platform. Du kan integrera och utöka användningen av Personaldata med hjälp av Microsoft Power Platform. Information om hur du integrerar Personal med Microsoft Power Platform finns i [Microsoft Power Platform-integrering med appar för ekonomi och drift](/fin-ops-core/dev-itpro/power-platform/overview).

## <a name="supported-geographies"></a>Områden som stöds

Information om språk och geografi som stöds för Personal finns i [Design på global nivå: Lära dig mer om vilka länder och språk som stöds](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Bevilja åtkomst till miljön.

Som standard har den globala administratör som skapade miljön åtkomst till den. Du måste uttryckligen bevilja åtkomst till ytterligare appanvändare. Du måste lägga till användare och tilldela dem lämpliga roller i Personal-miljön. Mer information finns i [skapa nya användare](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) och [tilldela användare till säkerhetsroller](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Ytterligare resurser
Du kan lära dig mer om hur du använder och hanterar projekt i LCS i appinfrastrukturen för ekonomi och drift med hjälp av följande resurser:

- [Resurser för Lifecycle Services](/fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Användarhandbok för Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Självbetjäning för distribution – översikt](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Startsida för åtgärder för databasflytt](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
