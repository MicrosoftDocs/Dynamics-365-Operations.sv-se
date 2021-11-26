---
title: Tjänstbeskrivning för Finance and Operations-appar
description: Det här ämnet innehåller tjänstbeskrivning för Finance and Operations-appar.
author: tomhig
ms.date: 09/29/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: a1547f0cc6c6f705cd0e2ff6e5be751cb97b946a
ms.sourcegitcommit: 79d19924ed736c9210fa9ae4e0d4c41c53c27eb5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2021
ms.locfileid: "7581826"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Tjänstbeskrivning för Finance and Operations-appar

[!include[banner](../includes/banner.md)]

Finance and Operations-program är ERP(Enterprise Resource Planning) SaaS-produkter som bygger på och för [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/). Finance and Operations-tjänsten ger organisationer ERP-funktioner som stöder deras unika behov och gör det lättare för dem att ändra företagsmiljöer utan att behöva hantera infrastruktur. Finance and Operations-appar kan omfatta ett eller flera av följande lösningsområden:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Tillsammans med [Business Intelligence](/power-bi/fundamentals/power-bi-service-overview), [infrastruktur](https://azure.microsoft.com/global-infrastructure/), [beräkning](/azure/service-fabric/service-fabric-overview) och [databastjänster](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/) gör apparna att organisationer kan köra branschspecifika och operationella affärsprocesser. Med stöd av sin implementeringspartner bestämmer kunderna konfigurationen av affärsprogramlogiken som passar deras unika affärsprocesser bäst. Funktionalitet och affärsprocesser kan utökas eller förlängas via en eller en kombination av följande lösningar:

- Inbyggd [personanpassningsupplevelse](personalize-user-experience.md)
- [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)-verktyg
- [Visual Studio](https://visualstudio.microsoft.com)-baserat [Finance and Operations SDK (software development kit)](../../dev-itpro/dev-tools/developer-home-page.md) och [Azure DevOps automatiserat bygge](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Oberoende programvaruleverantör (ISV) från [AppSource](https://appsource.microsoft.com/partners)

Utifrån kraven väljer kunderna en lösningsmetod. De arbetar med sin implementeringspartner för att definiera, utveckla och testa sin lösning genom att använda de verktyg och regelverk som finns i [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md). Det finns fyra vanliga scenarier:

- Färdig standardkonfiguration av Finance and Operations-appar (inga tillägg)
- Finance and Operations-appkonfiguration som omfattar en eller flera ISV-lösningar
- Finance and Operations-appkonfiguration som omfattar ett eller flera kundspecifika tillägg
- Finance and Operations-appkonfiguration som omfattar en kombination av kundspecifika tillägg och en eller flera ISV-lösningar

En organisation kan matcha sin affärsutveckling genom att enkelt lägga till användare och affärsprocesser via en enkel, transparent prenumerationsmodell. Mer information finns i [Licensguide för Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Driftmodell

I driftmodellen för Finance and Operations-appar definieras specifika roller och ansvarsområden för kunden, implementeringspartnern och Microsoft under tjänstens livscykel. Mer information finns i [Molnåtgärder och underhåll](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Kundaktiviteter

Kunderna arbetar tillsammans med sin partner och [Microsoft FastTrack](/dynamics365/fasttrack/) enligt ramverket [Success by Design](/dynamics365/fasttrack/success-by-design-overview) och använder verktyg och regelverksmallar som finns i [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) för att implementera sin lösning. Vanliga aktiviteter är:

- Användaridentitet och säkerhetshantering
- Definiera, utveckla och använda affärsprocesser
- Definiera, utveckla, testa och använda tillägg
- Övervaka och hantera icke-produktionsdistributioner
- Hantera programuppdateringar och validera tillägg
- Hantera ISV-lösningar och tredjepartsintegration

### <a name="microsoft-responsibilities"></a>Microsofts ansvar

Microsoft hanterar Finance and Operations-tjänsten genom att distribuera, övervaka och underhålla kunder och produktionsmiljöer i Microsoft SaaS-prenumerationen. Den här hanteringen omfattar att allokera den systeminfrastruktur som krävs för att köra tjänsten och i förebyggande syfte kommunicera med kunder om tjänstens hälsa. Ansvarsområdena omfattar:

**Infrastrukturhantering**
- Säkerhet och isolering
- Operativsystem och virtualisering
- Servrar, lagring och nätverk
- Datacenterkraft, nätverk, kylning

**Hantering av programplattform**
- 24/7-programövervakning och -meddelanden
- Diagnostik, plattformsuppdateringar, programuppdateringar, tjänstuppdateringar
- Programflöde, belastningsutjämning, webbplatsreplikering
- Etablering och hantering av miljön
- Databashantering, hög tillgänglighet (HA)/haveriberedskap (DR), skala, åtgärder
- Beräkningsdistribution, uppskalning, nedskalning

## <a name="system-configuration"></a>Systemkonfiguration

Finance and Operations-appar skalas enligt transaktionsvolymen och användarbelastningen. Varje kundimplementering skapar en unik lösning som består av följande element:

- **Datasammansättning** – En unik uppsättning parametrar som styr beteende, layout för organisationen, strukturen på huvuddata (t.ex. ekonomiska dimensioner och lagerdimensioner) och granularitet i transaktionsspårningen.
- **Tillägg och konfiguration** – Tilläggsmekanismer som använder kodtillägg, ISV-lösningar och unika konfigurationer som omfattar arbetsflöden, integrationer och rapportkonfigurationer.
- **Användningsmönster** – En unik kombination av online- och batchanvändning, tillsammans med möjligheten att integrera med nedströms och uppströms system för integration av data och möjligheten att skilja mellan olika informationsvyer som kunderna använder i sina affärsprocesser.

Microsoft konfigurerar kundproduktionsmiljöer som storleksanpassas för hantering av transaktionsvolym och användarsamtidighet. Microsoft ansvarar för följande uppgifter:

- Korrekt allokering av resurser i produktionsmiljöer, baserat på kundens profilinformation i [LCS-prenumerationsberäkningen](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Kontinuerlig övervakning och diagnos av produktionsmiljöers tjänsttillgänglighet
- Analysera och felsöka problem med systemprestanda med Finance and Operations-appar

För att säkerställa att en implementering är konfigurerad för hög prestanda måste kunderna utföra följande uppgifter:

- Ange korrekt användningsinformation om Finance and Operations-implementeringen i [LCS-prenumerationsberäkningen](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Bygga och testa tillägg avseende prestanda och skala.
- Testa datakonfigurationer för prestanda på rätt sätt.
- Säkerställa skalbarhet genom att utföra [prestandatest](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) innan de går live.

## <a name="onboarding-and-implementation"></a>Registrering och implementering

I följande tabell visas typiska händelser för registrering och implementering.

| Begäran | Förväntad Microsoft-åtgärd | Förväntad åtgärd för kund-/implementeringspartner |
|---|---|---|
| Ursprungligt erbjudandeinköp | Ett LCS-projekt skapas efter köpet av erbjudandet, baserat på en händelse som initieras av kunden. | Gå igenom [handelsprocessen](before-you-buy.md) Enterprise-avtal (EA) eller Molnlösningsleverantör (CSP) . Partnern skapar en klientorganisation för kunden, om det är tillämpligt. |
| Tilläggsköp | Bevilja kundåtkomst till det tillägg som väljs under implementeringen. | Inte aktuellt |
| Planering och analys av implementering | Ange relevanta verktyg i LCS, t.ex. [Affärsprocessmodellerare (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) och [interoperabilitet med Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md) | Planera projekt, konfigurera Azure DevOps, slutför systemets registrering och konfigurera administratörskonton. |

Mer information finns i [Registrera ett implementeringsprojekt](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalisering

Finance and Operations-appar finns i flera Azure-regioner över hela världen. Finance and Operations-appar innehåller funktioner som stöder olika länder/regioner och modersmål. Mer information finns i [Lokaliserings- och regelfunktioner](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Lands-/regionspecifika beaktanden

- Kunder inom reglerad bransch eller handelsorganisationer som gör affärer med enheter i Frankrike som kräver lokal datahemvist ska granska [Finance and Operations i Frankrike](../../dev-itpro/deployment/france-local-deployment.md).
- Kunder som har verksamhet i Kina ska granska [Finance and Operations – drivs av 21Vianet i Kina](../../dev-itpro/deployment/china-local-deployment.md).
- Kunder som har verksamhet i Ryssland ska granska [Rysk lokaliseringslag för personuppgifter](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia)

### <a name="general-data-protection-regulation-gdpr"></a>Allmänna dataskyddsförordningen (GDPR)

För Finance and Operations-appar fungerar Microsoft som personuppgiftsbiträde. Som personuppgiftsbiträde har Finance and Operations processer och funktioner som hjälper kunder att följa GDPR-krav som personuppgiftsbiträde. Mer information finns i [GDPR – översikt](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Miljö- och datahantering

Det här avsnittet beskriver några typiska miljö- och datahanteringshändelser som inträffar i tjänsten.

### <a name="environment-and-data-management-events-for-production-instances"></a>Miljö- och datahanteringshändelser för produktionsinstanser

LCS tillhandahåller [självbetjäningsverktyg](../../dev-itpro/deployment/infrastructure-stack.md) och [databasflyttåtgärder](../../dev-itpro/database/dbmovement-operations.md) som används för att utföra miljö- och datahanteringsuppgifter. Nedan följer några exempel:

**Händelse:** [Begära en produktionsinstans](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Fyll i [checklistan för publicering](../imp-lifecycle/prepare-go-live.md) och skicka den till [Microsoft FastTrack](/dynamics365/fasttrack/)-teamet.
- Fyll i [LCS-prenumerationsberäkningen](../../dev-itpro/lifecycle-services/subscription-estimator.md) innan du begär en produktionsinstans.
- Slutför alla implementeringsuppgifter som angetts i [LCS-metoden](../../dev-itpro/lifecycle-services/create-methodology.md).

**Händelse:** [kopiera en sandbox-databas till en produktionsinstans](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Utförs för en testpublicering eller en faktisk övergång till publicering.

**Händelse:** [Underhållsläge](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Aktivera underhållsläge i LCS.
2. Utför det underhåll som behövs.
3. Inaktivera underhållsläge i LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Miljö- och datahanteringshändelser för icke-produktionsinstanser

LCS tillhandahåller [självbetjäningetablering](../../dev-itpro/deployment/infrastructure-stack.md) och [databasflyttåtgärder](../../dev-itpro/database/dbmovement-operations.md) som används för att utföra miljö- och datahanteringsuppgifter. Nedan följer några exempel:

**Händelse:** [Distribuera en ny sandbox-instans](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Kontrollera att alla obligatoriska instanser har [planerats](../imp-lifecycle/environment-planning.md) och att tillämpliga tilläggserbjudanden har köpts in.
- Kör distributionsprocessen i LCS.
- Slutför alla uppgifter som angetts i LCS-checklistorna.
    
>[!NOTE]
>En utvecklings-sandbox-miljö är en virtuell dator (VM) som [distribueras till kundens Azure-prenumeration](../../dev-itpro/dev-tools/access-instances.md) och hanteras av kunden.

**Händelse:** [Kopiera en golden-konfigurationsdatabas från sandbox till produktion](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Utförs för en testpublicering eller en faktisk övergång till publicering.

**Händelse:** [Återställa en säkerhetskopia av en produktionspunkt till en instans som inte är produktion](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Kör alternativet [Uppdatera databas](../../dev-itpro/database/database-refresh.md) i LCS.
- Publiceringskopia: Radera eller dölj känsliga data via skript, justera miljöspecifika programkonfigurationer (t.ex. integrationsslutpunkter) och aktivera eller lägga till användare. Observera att dessa ändringar görs genom att du tillämpar ett [datapaket](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Händelse:** [Återställning av icke-produktionsinstansdatabas till tidpunkt](../../dev-itpro/database/database-point-in-time-restore.md)

- Acceptera att processen inte kan ångras.
- Kör åtgärden för tidpunktsåterställning i LCS.

**Händelse:** Kopiera en Nivå 2-databas till en utvecklings-sandbox för [felsökning](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Kör databasexportåtgärden i LCS för Nivå 2-sandbox-miljön.
- Importera och uppdatera databasen i utvecklingsmiljön.

## <a name="data-backup-and-retention"></a>Säkerhetskopiering och kvarhållning av data

Databaser för Finance and Operations-miljöer i SaaS-prenumerationen skyddas av automatiska säkerhetskopieringar. För produktionsmiljöer sparas automatiska säkerhetskopieringar i 28 dagar om inte Microsoft gör en återtagning. För sandbox-miljöer (Tier 2+) finns de kvar i sju dagar. Ett återtag av produktionsmiljön kan utföras om ett fel inträffar under en planerad underhållsuppdatering.

Mer information om automatiska säkerhetskopieringar finns i [Automatiserad säkerhetskopiering - Azure SQL-databas & SQL Managed Instance](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Ansvarsområden för tjänstaktivitet

I tabellen nedan beskrivs några typiska scenarier och aktiviteter för tjänsten. Det anger också om Microsoft, kunden eller både Microsoft och kunden ansvarar för aktiviteterna.

| Aktivitet | Microsofts ansvar | Kundens ansvar |
|---|---|---|
| **Etablera initiala klientorganisationer** | | |
| Uppskatta storleken på den projekterade belastningen i LCS med hjälp av verktyget för prenumerationsberäkning, och begär att specifika miljöer ska etableras. | | X |
| Etablera alla produktionsinstanser och icke-produktionsinstanser. | X | |
| Validera distribuerade produktionsinstanser och icke-produktionsinstanser. | | X |
| **Tjänstuppdateringar** | |
| Tillämpa tjänstuppdateringar på angivna icke-produktions- och produktionsinstanser. | X | |
| Använd tjänstuppdateringar manuellt från LCS på instansen. Definiera, utveckla, testa uppdateringen och för tillbaka koduppdateringspaketet till LCS. | | X |
| Begär och schemalägg tilläggsuppdateringar tillämpas på produktionsinstansen. | | X |
| Skapa en kod och säkerhetskopiering av data för produktionsinstansen innan några uppdateringar tillämpas. | X | |
| Om fel uppstår, återta produktionsinstansen till kod- och datasäkerhetskopian. | X | |
| **Datahantering (säkerhetskopiering, återställning och uppdatering)** | | |
| Säkerhetskopiera databasen. | X | |
| Fastställ hög tillgänglighet och en haveriberedskapsplan. | X | |
| Övervaka prestanda i produktionsinstansdatabasen. | X | |
| Justera prestanda i produktionsinstansdatabasen. | X | |
| Uppdatera produktionsinstansdatabasen i tidpunktsuppdatering till en instans som inte är produktion. | | X |
| **Uppdatera infrastruktur** | | |
| Planera regelbundna uppdateringar av infrastruktur. | X | |
| **Skalning upp och ned (användare, lagring och instanser)** | | |
| Köpa in ytterligare tillägg för användare och icke-produktion. | | X |
| Uppdatera användarändringar i verktyget LCS-prenumerationsberäkning. | | X |
| Rapportera alla prestandaproblem som påverkar användningen av tjänsten. | | X |
| Förebyggande hantering av resurser som krävs för tillämpliga tjänster. | X | |
| Undersöka och felsöka problem. | X | |
| **Säkerhet (användaråtkomst)** | | |
| Ge användaråtkomst till tjänsten. | | X |
| Ge LCS-projektåtkomst till hanteringen och driften av instanser som har distribuerats via LCS. | | X |
| **Övervaka produktionsinstanser** | | |
| Övervaka produktionsinstanser 24/7. | X | |
| Proaktivt meddela kunden om incidenter som berör produktionsinstansen. | X | |
| **Hantera och övervaka icke-produktionsinstanser** | | |
| Hantera icke-produktionsinstanser med hjälp av LCS. | | X |
| Övervaka icke-produktionsinstanser. | | X |

## <a name="service-update-strategy"></a>Strategi för tjänstuppdatering

I enlighet med [livscykelpolicyn för programvara](../../dev-itpro/migration-upgrade/versions-update-policy.md) följer Finance and Operations-appar Microsofts [Modern Lifecycle Policy](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) som omfattar produkter som kontinuerligt servas och stöds. 

Microsoft släpper åtta tjänstuppdateringar för Finance and Operations-appar varje år under följande månader:

- Januari
- Februari
- April
- maj
- Juli
- Augusti
- Oktober
- November

>[!NOTE]
>April och oktober är de huvudsakliga utgivningscyklerna. Kunderna kan göra en paus i en enskild tjänstuppdatering i upp till tre på varandra följande uppdateringscykler.

Mer information finns i följande ämnen:

- [Översikt över Tjänstuppdateringar för One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Konfigurera tjänstuppdateringar via LCS](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Pausa tjänstuppdateringar via LCS](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Få meddelanden om tjänstuppdateringar via LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Regressionstestverktyg för validering av serviceuppdateringar](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Dynamics 365-översikt och utgivningscykler](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Säkerhet och administrativ åtkomst

Administrativ åtkomst till en Finance and Operations-produktionsmiljö kontrolleras och loggas strikt. Kunddata hanteras i enlighet med [villkoren för Microsofts onlinetjänster](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Kunds administrativa åtkomst

Kundens klientorganisationsadministratör kan komma åt produktionsinstanser eller ickeproduktionsinstanser, enligt beskrivningen i följande tabell:

| Miljötyp | Syfte | Åtkomstnivå för kunder |
|---|---|---|
| **Icke-produktion**<br>Nivå 1 sandbox-miljö | En miljö som inte är produktionsmiljö som kunder distribuerar för utveckling, demonstration eller utbildning. | En Nivå 1 sandbox-miljö (kallas även molnbaserad miljö) är en kundhanterad VM som distribueras till kundens Azure-prenumeration från LCS. Eftersom det är en virtuell dator i kundens Azure-prenumeration har kunden fullständig administrativ åtkomst till miljön via Remote Desktop. |
| **Icke-produktion**<br>Nivå 2 (eller högre) sandbox-miljö | En miljö som inte är produktionsmiljö där kunder distribuerar för testning av användargodkännande, integrationstester, utbildning, mellanlagring eller andra scenarion som gäller för förproduktion. | Nivå 2 och högre sandbox-miljöer distribueras till Finance and Operations SaaS-prenumerationen. Åtkomst till Azure SQL-databaser som är associerade med den icke-produktionsmiljön beviljas via [just-in-time-åtkomst](../../dev-itpro/database/database-just-in-time-jit-access.md). Remote Desktop-åtkomst är inte tillgänglig. |
| **Produktion** | En produktionsmiljö distribueras när projektet är [klart för initial publicering](/imp-lifecycle/environment-planning.md#production-system-readiness). | Produktionsmiljöer distribueras till SaaS-prenumerationen. All åtkomst går via webbläsaren, tjänsteslutpunkter eller LCS. |

### <a name="microsoft-administrative-access"></a>Microsofts administrativa åtkomst

Följande tabell visar olika åtkomstnivåer för olika Microsoft-administratörer:

| Administratör | Kunddata |
|---|---|
| Svarsteam för verksamhet<br>(Begränsat till endast nyckelpersonal) | Åtkomsten beviljas via en supportbegäran. Åtkomsten granskas och begränsas till varaktigheten för supportaktiviteten. |
| Microsoft Customer Support Services (CSS) | Ingen direkt åtkomst. Kunden kan använda skärmdelning för att arbeta med supportpersonal för felsökning av problem. |
| Konstruktion | Ingen direkt åtkomst. Svarsteamet för verksamhet kan felsöka problem tillsammans med teknikavdelningen med hjälp av skärmdelning. |
| Andra i Microsoft | Ingen åtkomst. |

## <a name="monitoring"></a>Övervakning

Microsoft har investerat i en omfattande verktygsuppsättning för att övervaka och diagnosticera kundernas produktionsinstanser. Microsoft övervakar kunders produktionsmiljöer 24 timmar om dagen, 7 dagar i veckan. Mer information finns i [Produktionssupport och övervakning](../imp-lifecycle/production-support-monitoring.md).

| Microsofts ansvar | Kundens ansvar |
|---|---|
| <ul><li>Övervaka tillgängligheten på tjänsten.</li><li>Övervaka och avisera kontinuerligt via hälsomått och säkerhetskomponenter för viktiga komponenter som Application Object Server (AOS), Batch, Dataimport/export-ramverk (DIXF), Commerce och Management Reporter.</li><li>Övervaka prestandaförsämring som orsakas av infrastrukturtjänster (till exempel Azure Active Directory \[Azure AD\] och Azure SQL).</li><li>Om Microsoft fastställer att en enskild process eller ett batchjobb orsakar avvikelser, kommer den processen eller jobbet att avslutas efter kommunikation med kunden.</li></ul> | <ul><li>Övervaka ändringar av programkonfigurationer och tillägg som kan orsaka funktionsproblem och prestandaproblem.</li><li>Programfel måste diagnosticeras genom att använda övervakningsverktygen. Använd dessa verktyg diagnosticera användarrapporterade prestandaförsämringar.</li><li>Informera Microsoft om det finns förväntad belastning på systemet utöver projekterad toppanvändning.</li><li>Om den tillämpliga tjänsten inte är tillgänglig i produktionsinstansen kan kunden använda LCS för att rapportera ett [produktionsavbrott](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Genom att skicka supportförfrågningar online, via LCS, kan Microsoft leverera snabb och djupgående teknisk kompetens på det mest effektiva sättet. Även om det finns ett telefonnummeralternativ bör det endast användas om onlinealternativet inte är tillgängligt. Mer information finns i [Alternativ för telefonsupport](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Incidenthantering

Microsoft hanterar och åtgärdar incidenter efter allvarlighetsgrad. Microsofts incidentallvarlighetsgrader kan ändras under den första bedömningen av incidenten, och när mer information om inverkan och omfattning blir tillgänglig. Om incidenten åtgärdas förändras inte incidentens allvarlighetsgrad.

Mer information om allvarlighetsnivåer finns i [den här allvarlighetstabellen](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Verksamhetskontinuitet genom hög tillgänglighet och haveriberedskap 

Microsoft tillhandahåller affärskontinuitet och haveriberedskap för produktionsinstanser av Finance and Operations-appar i händelse av Azure-regionomfattande avbrott. Mer information finns i [Affärskontinuitet och haveriberedskap](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Hög tillgänglighet** – HA-funktionaliteten innehåller sätt att förhindra avbrott som orsakas av att en enstaka nod i en Azure-resurs misslyckas. Varje tjänsts molnarkitektur använder Azure-tillgänglighetsuppsättningar för beräkningsskiktet för att förhindra händelser med fel vid enstaka punkter. HA för databaser tillhandahålls via [Azure SQL HA-funktioner](/azure/azure-sql/database/high-availability-sla).
- **Haveriberedskap** – [Funktioner för Azure-haveriberedskap](/azure/best-practices-availability-paired-regions) skyddar varje tjänst mot avbrott som påverkar ett hel Azure-datacenter. Här följer några av dessa funktioner:

    - Azure SQL aktiv georeplikering för den primära databasen (affärsdatabasen).
    - Georedundanta kopior av Azure Blob Storage (som innehåller dokumentbilagor) i andra Azure-regioner.
    - Sekundär region för Azure SQL- och Azure Blob Storage-replikeringar.

Primära datalager stöds för replikering. Därför används transformerade data från den primära databasen för komponenter för varje tjänst, t.ex. Management Reporter och enhetsarkiv. Dessa data måste genereras efter att återställningsplatsen har konfigurerats och tjänsten har startats. Kundkodsartefakter och återställda datalager används för att omdistribuera platsen. Med omdistribueringen går det att använda tillståndsreplikering av beräkningsnoderna, tillsammans med nätverk och andra komponenter, för att använda återställda datalager för att konfigurera den sekundära platsen. Om haveriberedskap används för att återställa kundens produktionsinstans, kommer Microsoft och kunden att uppfylla sina ansvarsområden [för incidenthantering](service-description.md#incident-management).

Microsofts haveriberedskapsplaner och procedurer undersöks regelbundet genom SOC-granskningar (System and Organization Controls). Dessa efterlevnadskontroller granskar den tekniska och procedurmässiga processen för Microsofts DR, inklusive Dynamics 365 Finance and Operations-appar. [SOC-efterlevnad](/compliance/regulatory/offering-soc-2) granskningsrapporter och alla andra efterlevnadsrapporter finns tillgängliga i [efterföljandeerbjudanden för Microsoft Trust Center](/compliance/regulatory/offering-home).

| Microsofts ansvar | Kundens ansvar |
|---|---|
| Microsoft tillhandahåller en sekundär miljö i Azure-kopplade datacenter när den primära produktionsinstansen distribueras. Mer information finns i [Affärskontinuitet och haveriberedskap (BCDR): Azure-kopplade regioner](/azure/best-practices-availability-paired-regions). | None |
| Microsoft aktiverar georedundans av Azure SQL och Azure Blob Storage när den primära produktionsinstansen distribueras. | None |
| Microsoft aktiverar automatisk säkerhetskopiering av Azure SQL-databaser. | None |
| <p>När ett avbrott inträffar bestämmer Microsoft om en redundans måste utföras för kunden och om data går förlorade. Dataförlust kan vara upp till fem sekunder. Mer information finns i [Geoåterställning av Azure SQL-databas](https://azure.microsoft.com/blog/azure-sql-database-geo-restore).</p><p>I händelse av dataförlust begär Microsoft kundens godkännande för en redundans.</p> | I händelse av dataförlust måste kunden eventuellt tillhandahålla skriftligt godkännande för att utlösa redundansen. |
| När en redundans inträffar fungerar tjänsten i begränsat läge. Uppdateringsunderhåll kan inte utlösas i redundansläge. | Kunden kan inte begära paketdistributioner eller andra regelbundna underhållsbegäranden i redundansläge. |
| När datacentret tas i drift Microsoft återställer tillbaka till produktionsinstansen i den primära Azure-regionen. Normal verksamhet återupptas. | Kunden kanske måste godkänna återställning till produktionsinstansen i den primära Azure-regionen. |

## <a name="finance-and-operations-support-offerings"></a>Finance and Operations-supporterbjudanden

Teknisk support finns på marknader där Finance and Operations-tjänster erbjuds. [Supportupplevelser](../../dev-itpro/lifecycle-services/lcs-support.md) tillhandahålls i LCS och Finance and Operations-appar. Nedan följer några exempel:

- [Problemsökning](../../dev-itpro/lifecycle-services/issue-search-lcs.md) i LCS
- [Integrerad teknisk support](../../dev-itpro/lifecycle-services/support-experience.md) i Finance and Operations-appar
- [Molnbaserad support](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) i LCS

Microsoft erbjuder Finance and Operations-kunderna tre supportplaner: Premier, Professional Direct och det support som ingår i prenumerationen. Supportnivån varierar per plan. Följande tabell visar en jämförelse av de tre planerna.

| Supportfunktion | Premier | Professional Direct | Abonnemang |
|---|---|---|---|
| Obegränsad sändning av avbrott/korrigera incident | Ja | Ja | Ja |
| 24/7 åtkomst via LCS | Ja | Ja | Ja |
| Incidentsvarstid | Mindre än en timme | Mindre än en timme | Nästa arbetsdag |
| Rådgivningstimmar | Pooler anskaffas per avtal. | Nej | Nej |
| Dedikerad supportkontohanterare | Ja | Nej | Nej |
| Dedikerad supporttekniker | Engageras enligt separat avtal | Nej | Nej |

Mer information finns i [Supportöversikt](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Process för att engagera support

I händelse av incidenter som involverar Finance and Operations-appar skickar kunderna supportärenden till Microsoft via LCS. CSS hanterar incidenterna utifrån kundens supportplan och hur allvarliga incidenten är enligt CSS

### <a name="service-level-agreement"></a>Servicenivåavtal

Microsoft är engagerade i en tillgänglighetsgrad på 99,9 procent per månad för tjänsten. Om Microsoft inte uppnår och underhåller servicenivån för den tillämpliga tjänsten på det sätt som beskrivs i servicenivåavtalet (SLA) kan kunden få kredit mot en del av sina månatliga serviceavgifter för tjänsten. Information om hur du initierar en servicekredit finns i avsnittet "Anspråk" i [servicenivåavtalet](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Viktiga resurser

- **[Trust Center](https://www.microsoft.com/trust-center)** – Hämta information om var dina Finance and Operations-data lagras, plus ytterligare information om sekretess, efterlevnad och säkerhetsprocedurer.
- **[Licensvillkor och -dokumentation](https://www.microsoftvolumelicensing.com/)** – Snabbt få åtkomst till licensvillkor, villkor och ytterligare information som är relevant för användningen av produkter och tjänster som licensieras via Microsofts volymlicensprogram.
- **[Licensvillkor](https://www.microsoft.com/licensing/product-licensing/)** – Resurserna på den här sidan definierar villkoren för programvaran och onlinetjänsternas produkter som du köper via Microsofts kommersiella licensieringsprogram.
- **[Microsofts livscykelpolicy](/lifecycle/)** – På den här sidan finns enhetliga och förutsägbara riktlinjer för support under en produkts livscykel.
- **[Licensguide](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – Med den här guiden kan du lära dig mer om hur du licensierar Dynamics 365.
- **[Kundtjänst](https://dynamics.microsoft.com/support/)** – Få branschledande support för dina Dynamics 365-appar.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** – Hantera din livscykel för program och gå mot förutsägbara, upprepningsbara implementeringar av hög kvalitet.

## <a name="definitions"></a>Definitioner

### <a name="azure-region"></a>[Azure-region](/azure/availability-zones/az-overview#regions)

En geografisk region där det finns ett eller flera Azure-datacenter. Exempel på detta är USA och Europa.

### <a name="business-process-modeler-bpm"></a>[Affärsprocessmodelleraren (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Ett verktyg i LCS som gör det lättare att göra en bristanalys för en given implementering med hjälp av affärsprocessdefinitioner från amerikansk produktivitet och kvalitetscenter (APQC) som stöds i Finance and Operations-appar.

### <a name="cloud-solution-provider"></a>Leverantör av molnbaserad lösning

En partner som ingår i CSP-programmet (Microsoft molnbaserad lösningsleverantör) och som ger kunder molnbaserade tjänster med mervärde, support, en faktura och kundhantering i skala.

### <a name="customer"></a>Kund

En företagsenhet som använder Finance and Operations-appar och representeras av en klientorganisation i Office 365.

### <a name="development-environment"></a>Utvecklingsmiljö

En miljö för icke-produktions sandbox-miljö som används för att utveckla tillägg. Kunder distribuerar den här miljön till sitt eget Azure-abonnemang från LCS. Den här miljön kan även användas för demonstration, utbildning eller andra testuppgifter. Det kallas också för [Nivå 1 sandbox](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Driftstopp

En period när användare inte kan logga in eller få åtkomst till sin aktiva klientorganisation på grund av ett fel i den ej utgångna plattform eller tjänsteinfrastrukturen, vilket Microsoft fastställer från automatiserad hälsoövervakning och systemloggar. Avbrott omfattar inte schemalagda avbrott, otillgängliga funktioner för tjänsttillägg, att till tjänsten inte kan användas på grund av ändringar av som du gjort i tjänsten, eller perioder där skalningsenhetens kapacitet överskrids.

### <a name="implementation-partner"></a>Implementeringspartner

Den partner som kunden väljer för att anpassa, konfigurera, implementera och hantera sina Finance and Operations-lösningar.

### <a name="incident"></a>Incident

Ett problem som kunderna stöter på när de använder Finance and Operations-tjänsten och som de skickar in en ärende för via LCS.

### <a name="microsoft-customer-support-services-css"></a>Microsoft Customer Support Services (CSS)

Microsofts globala supportteam som arbetar med kvalitetsservice för Finance and Operations-appar.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

Den administrativa portal för livscykelhantering av Finance and Operations-appar från utvärdering, till implementering, hantering av och support efter produktion. Mer information finns i [Lifecycle Services-resurser](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Icke-produktionsinstans

Någon av följande instanser av en tjänst som kunden använder för att validera tillägg och utföra andra utvecklingsuppgifter:

- **Sandbox nivå 1** – Utvecklarinstans (med kund som värd)
- **Sandbox nivå 2** – Instans för standardgodkännandetest
- **Sandbox nivå 3–5** – Tilläggssandbox-miljöer

Mer information om Nivå 2 till 5 finns i [Välja korrekt nivå-2 eller högre miljö](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Produktionsinstans

En Finance and Operations-miljö som kunden använder för att hantera "live" dagliga transaktioner och affärsprocesser.

### <a name="sandbox-environment"></a>Sandbox-miljö

En icke-produktionsmiljö som kunden använder för demonstration, utbildning, användaracceptanstest, validering av tillägg och andra testuppgifter.

### <a name="service"></a>Service

Alla kärntjänster som ingår i Finance and Operations-apparna.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Servicenivåavtal (SLA) för Microsofts onlinetjänster

Serviceavtalet gäller för Microsofts onlinetjänster. Mer information finns i [Serviceavtal](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Tjänsteuppdatering

Microsoft-tjänsters Finance and Operations-miljöer på enhetlig bas med hjälp av serviceuppdateringar. Kunder ställer in sin egen serviceuppdateringskalender utifrån verksamhetens behov. Mer information i [Tjänstuppdateringar för en version](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="user"></a>Användare

En person som använder Finance and Operations-miljöer och som är associerad med en kunds klientorganisation.
