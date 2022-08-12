---
title: Vanliga frågor om Dynamics 365 Human Resources infrastrukturkoppling
description: Den här artikeln innehåller svar på vanliga frågor om infrastruktursammanslagningen för Microsoft Dynamics 365 Human Resources och appar för ekonomi och drift.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd71d728f9c97dc9e2c44a7e7a0e773be891b818
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203212"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Vanliga frågor om Dynamics 365 Human Resources infrastrukturkoppling

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>Vad är Dynamics 365 Human Resources?

Microsoft Dynamics 365 Human Resources tillhandahåller verktyg som hjälper personalteam att öka organisationens flexibilitet, transformera medarbetarnas erfarenheter och optimera personalprogram för att skapa en arbetsplats där människor och företaget kan frodas. För mer information om Dynamics 365 Human Resources, se [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transformera medarbetarerfarenheter.** Behåll de främsta medarbetarna genom att ge chefer och medarbetare erfarenheter av uppkopplad självbetjäning som driver engagemang och tillväxt.
- **Optimera personalprogram.** Minska driftkostnaderna och skapa personcentrerade tjänstledighets- och frånvaroprogram samt tids-, förmåns- och kompensationshanteringsprogram.
- **Öka organisationens flexibilitet.** Gör det möjligt för personalavdelningen att använda den rörlighet som verksamheten kräver genom att använda Dataverse och Microsoft Power Platform för att centralisera personers data och enkelt utöka Dynamics 365 Human Resources.
- **Upptäcka personalinsikter.** Fatta datadrivna beslut genom att analysera och visualisera personers data på omfattande instrumentpaneler som är tillgängliga på alla enheter.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Värde och fördelar med infrastrukturkopplingen

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Vad är Dynamics 365 Human Resources infrastrukturkoppling?

Det finns för närvarande två separata uppsättningar med personalfunktioner i två olika infrastrukturer i Dynamics 365:

- **Dynamics 365 Human Resources** – Ett fristående program som körs på en oberoende infrastruktur. När detta program lanserades separerades infrastrukturen från andra program för Dynamics 365-drift. Våra kunder använder detta program för att öka organisationens flexibilitet, optimera personalprogram, transformera medarbetarerfarenheter och få insikter om personalen.
- **Personalmodul** – En äldre uppsättning funktioner som tidigare ingick i lagerhållningsenheten (SKU) för Unified Operations-licens. Personalmodulen kör på ekonomi- och driftinfrastrukturen, som är densamma för alla åtgärdsappar. Dessa program inkluderar Dynamics 365 Finance, Dynamics 365 Project Operations och Dynamics 365 Supply Chain Management. Kunderna tog emot personalfunktionerna som en del av Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.

Under de senaste tre åren har Microsoft inte lagt till några nya funktioner eller förbättringar i personalmodulen. Istället har våra övergripande investeringar fokuserat på Dynamics 365 Human Resources-appen.

Genom att ta med dessa två uppsättningar funktioner i samma infrastruktur hjälper vi kunderna att få följande fördelar:

- Förbättringar som har lagts till i Dynamics 365 Human Resources under de senaste tre åren, inklusive förbättrad tjänstledighet och frånvaro, förmånshantering och rapportering.
- Förbättrad utbyggbarhet genom Microsoft Power Platform och möjlighet att utöka affärslogik för att personanpassa sidor.
- Förbättrad distribution, förbättrade uppdateringar och förbättrat underhåll som är konsekventa i fråga om livscykelhantering för program (ALM), Lifecycle Services, geografisk tillgänglighet med mera.
- Fler tekniska innovationer i takt med att vårt tekniska team använder delade tjänster, verktyg och reducerade plattformskostnader.

Den här övergången kommer att påverka kunder som för närvarande använder antingen Dynamics 365 Human Resources eller den äldre personalmodulen.

## <a name="glossary-of-terms-used-in-this-faq"></a>Ordlista med termer som används i dessa Vanliga frågor och svar

- **Dynamics 365 Human Resources** – Vår aktuella och framtida produkt som erbjuder personalfunktioner på marknaden.
- **Personalmodul** – En uppsättning äldre funktioner som tidigare licensierades med Unified Operations-erbjudandet. Funktionerna aktiveras när en kund äger Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.
- **Infrastruktur för ekonomi och drift** – Den utvecklingsarkitektur som används av driftportföljen, inklusive Dynamics 365 Finance, Dynamics 365 Supply Chain Management och Dynamics 365 Project Operations. Denna infrastruktur är den som kommer att användas framöver. I dessa Vanliga frågor och svar avser termen *sammanslagen infrastruktur* miljön för ekonomi och drift.
- **Personalinfrastruktur** – Utvecklingsarkitekturen som historiskt använts för programmet Dynamics 365 Human Resources. Sammanslagningsprojektet för infrastruktur för in Dynamics 365 Human Resources i samma infrastruktur som Ekonomi och Drift. Den fristående infrastrukturen kommer att upphöra.

## <a name="general-questions-about-the-infrastructure-merge"></a>Allmänna frågor om den infrastruktursammanslagningen

### <a name="will-customers-lose-any-features-or-capabilities"></a>Förlorar kunderna funktioner eller kapacitet?

Vårt mål är att minimera den inverkan den här övergången har på kunderna. Inga funktioner eller funktioner tas bort. Det kommer att finnas funktionell paritet mellan Dynamics 365 Human Resources personalmodulen. Om det finns en funktion i båda infrastrukturerna används Dynamics 365 Human Resources-funktionen.

### <a name="will-the-user-experience-change"></a>Kommer användarupplevelsen att förändras?

Användarupplevelsen kommer att stämma överens med standardupplevelsen för Dynamics 365-plattformen. Fastän den allmänna upplevelsen för instrumentpanelen och menyerna förblir oförändrad, kommer den att stämma överens med standardupplevelsen av Dynamics 365 Finance. Navigeringen omfattar både moduler och arbetsytor, gör att det går att använda favoriter, med mera. Arbetsytorna Dynamics 365 Human Resources, till exempel **Personalhantering** och **Personer**, sammanfogas till infrastrukturen för ekonomi och drift. I framtiden kommer nya funktioner att levereras via Funktionshantering, som innebär att kunderna kan visa nya funktioner och bestämma vilka funktioner de vill använda. Mer information finns i [översikten för Funktionshantering](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och [dokumentationen för Användargränssnitt](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>När kan infrastruktursammanslagningen för Dynamics 365 Human Resources vara klar?

Infrastruktursammanslagningen lanseras fasvis i syfte att ge kunderna tid att planera och genomföra de steg som behövs. Vi påbörjade publiceringen av funktioner i utgivningscykel 2 år 2021 för Dynamics. Vi planerar att slutföra allt produktutvecklingsarbete för det här projektet vid slutet av 2022 års utgivningscykel 2. Observera att tidsangivelserna kan komma att ändras. För den senaste informationen, se [utgivningsplanerna](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Vilka utbildningar och resurser finns tillgängliga för att hjälpa till med infrastruktursammanslagningen?

Vi kommer att tillhandahålla dokumentation som beskriver varje enskilt steg av sammanslagningsprocessen för infrastruktur i detalj. Vi kommer att tillhandahålla ytterligare utbildningsresurser, till exempel videor och workshops, som behövs för att hjälpa kunder och partner med en smidig övergång.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Kommer det att ske förändringar i utvecklingskapaciteterna när infrastruktursammanslagningen har slutförts?

Mer information om utvecklingskapaciteter finns på [Startsidan för utveckling och anpassning](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Frågor om funktionstillgänglighet

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>Kommer LinkedIn Talent Hub-integreringen att fungera i infrastrukturen för ekonomi och drift?

Nej, LinkedIn Talent Hub-integreringen kommer inte att ingå i den sammanslagna infrastrukturen. Public application programming interfaces (API:er) är tillgängliga för att bygga integreringar med spårningslösningar för rekrytering och sökande. Kunder som planerar att använda LinkedIn Talent Hub bör arbeta tillsammans med sin Microsoft-partner och integrera med de API:er som tillhandahålls. Mer information om API:er för ATS (Applicant Tracking System, sökandespårningssystem) finns i [Introduktion till integrerings-API för sökandespårningssystem](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Kommer funktionerna som för närvarande bara finns tillgängliga i Dynamics 365 Human Resources (till exempel tjänstledighetshantering och förmånshantering) att vara tillgängliga när sammanslagningen har slutförts?

Ja. Alla Dynamics 365 Human Resources programfunktioner förs över till infrastrukturen för ekonomi och drift. Funktionerna blir tillgängliga i faser. Om du vill ha aktuell information om tillgänglighet för funktioner för den sammanslagna infrastrukturen bör du regelbundet granska [utgivningsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>Kommer Ceridian-integrering med Dynamics 365 Human Resources att vara tillgänglig efter det att infrastruktursammanslagningen har slutförts?

Ceridian håller på att skapa en V2-integration med Dynamics 365 Human Resources som utnyttjar löne-API:erna. Den filbaserade integreringen som för närvarande finns i Dynamics 365 Human Resources migreras inte till infrastrukturen för ekonomi och drift. Mer information finns i [Löne-API-introduktion](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>Ska sökandens spårning eller registrering/avregistrering av medarbetarens funktioner inkluderas?

I tidigare versioner skapade vi integrations-API:t för ATS i syfte att göra det möjligt för partner och kunder att skapa ATS-integreringar med Personal. Ytterligare ATS-relaterade funktioner blev tillgängliga 2022 cykel 1. Vi kommer att fortsätta förbättra dessa API:er i kommande versioner.

Den personalfunktion som för närvarande finns i infrastrukturen för ekonomi och drift innehåller vissa funktioner för rekryteringshantering som inte finns i Dynamics 365 Human Resources. Denna funktion kommer att vara tillgänglig för samtliga Personal-kunder när sammanslagningen av infrastrukturen har slutförts. Den här funktionen tillhandahåller en lätt ATS-funktion. Vi planerar emellertid inte att utöka den här funktionen i framtiden. Kunder som behöver mer avancerade funktioner kan dra nytta av ATS-partnerintegrationer. Mer information om API:er för ATS (Applicant Tracking System, sökandespårningssystem) finns i [Introduktion till integrerings-API för sökandespårningssystem](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>Kommer uppgraderingsverktygen för Dynamics AX 2012 att användas för att uppgradera Personalmodulen i AX 2012 till Dynamics 365 Human Resources-appen?

Ja. En uppgradering från Dynamics AX 2012 till Dynamics 365 Human Resources kommer att följa samma uppgraderingsväg och verktyg som används för att uppgradera till den senaste versionen av andra Dynamics 365 Operations-appar, till exempel Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.

Mer information om migrering till infrastrukturen för ekonomi och drift finns i [Vanliga frågor och svar om kundintegrering för Personal](./customer-migration.md).
