---
title: Vanliga frågor och svar om kundmigrering för Personal
description: Den här artikeln innehåller svar på vanliga frågor om migrering av Microsoft Dynamics 365 Human Resources till den sammanslagna infrastrukturen för ekonomi och drift.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a6f883da07bd1d3a6b0379f1582dc8556e166ff
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151091"
---
# <a name="human-resources-customer-migration"></a>Kundmigrering för Personal

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>Hur ska Dynamics 365 Human Resources-kunderna planera flytten till infrastrukturen för ekonomi och drift?

Två kategorier av Microsoft Dynamics 365 Human Resources-kunder kommer att påverkas och måste göra ändringar i syfte att säkerställa att de finns med i den senaste infrastrukturen för ekonomi och drift:

- Kunder som använder Dynamics 365 Human Resources och inte har några andra driftappar från Dynamics 365
- Kunder som använder både Dynamics 365 Human Resources och Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce eller Dynamics 365 Project Operations

Oavsett vilken kategori de tillhör måste kunderna flytta data till en nyligen skapad miljö i infrastrukturen för ekonomi och drift, samt validera att sammanslagningen har slutförts.

Hädanefter kommer Dynamics 365 Human Resources-programmet att ha en egen miljö för ekonomi och drift som är separat från andra driftappar. På det här sättet kan kunderna dra nytta av expansionsalternativen utan att behöva sammanfoga aktuella data. Microsoft kommer att tillhandahålla verktyg och en sandbox-miljö som kunderna kan använda för att testa och validera datamigrering innan de tar steget över till en produktionsmiljö. Verktyget möjliggör en närapå automatiserad process och är tillgänglig mellan augusti och november 2022.

Kunder som använder andra program för infrastrukturen för ekonomi och drift har då möjlighet att sammanfoga sina personaldata med en befintlig miljö. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>När kommer kunderna att flyttas infrastrukturen för ekonomi och drift?

Övergången för respektive företag beror på företagets aktuella konfiguration och beredskap att flytta över till infrastrukturen för ekonomi och drift. Vi rekommenderar att kunderna samarbetar med sin respektive Microsoft-partner för att avgöra en optimal väg framåt.

- Organisationer som använder modulen **Personal** i Dynamics 365 Finance kommer att kunna aktivera nya funktioner i Dynamics 365 Human Resources som ett led i den sedvanliga uppdateringsprocessen för One Version. Nya funktioner planeras bli allmänt tillgängliga från och med januari 2022.
- Organisationer som använder Dynamics 365 Human Resources kommer att ha åtkomst till verktyg som de kan använda när de slutför infrastruktursammanslagningen. Microsoft kommer att arbeta tillsammans med kunderna gällande övergång för att förhindra störningar i tjänsten. Kunderna har 12 till 18 månader på sig att genomföra övergången från det att migreringsverktyget blir tillgängligt.
- Organisationer som använder både Dynamics 365 Human Resources och modulen **Personalresurser** kan flytta sin fristående Personal-infrastruktur till infrastrukturen för ekonomi och drift. Ett annat alternativ är att använda verktygen för sammanslagning för att föra in miljöerna i en enda miljö. Det finns inga krav eller tidsramar för att sammanfoga de två miljöerna.

För senaste information, kontrollera regelbundet [utgivningsplanen](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>Behöver kunderna fortfarande anpassade integrationer mellan Dynamics 365 Human Resources och modulen Personal?

- Kunder som har både och Dynamics 365 Human Resources andra infrastrukturmiljöer för ekonomi och drift som för närvarande är integrerade måste fortsätta integrera de två miljöerna efter sammanslagningen.
- Kunder som väljer att hålla sin Dynamics 365 Human Resources-miljö åtskild från sin befintliga ekonomi- och driftprogrammiljö måste fortsätta integrera miljöerna för att göra datan tillgänglig i båda miljöer.
- Kunder kan fortsätta använda dataintegreraren för att kopiera data mellan de två miljöerna. Kunder som sammanfogar data i en enkel miljö efter migreringen måste inte längre integrera datan, detta eftersom alla data finns i en enkel databas.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>Kommer kundernas ISV-lösningar att migreras automatiskt?

Migreringserfarenheterna för varje oberoende lösning för programvaruleverantör (ISV) varierar beroende på hur lösningen integreras. Microsoft kommer att arbeta nära ISV i syfte att säkerställa en smidig övergång till infrastrukturen för ekonomi och drift. Många ISV-lösningar bygger på Dataverse med användning av funktionerna i Microsoft Power Platform. Dessa lösningar vilar på Dataverse-integreringen mellan Dynamics 365 Human Resources-miljön och Dataverse-miljön. Dataverse-integreringen håller på att göras inaktuell som en del av infrastruktursammanslagningen. I infrastrukturen för ekonomi och drift planeras nya mappningar med dubbel skrivning som ska ersätta funktionerna i Dataverse-integreringen.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>Hur påverkas dataintegreraren som flyttar data mellan Dynamics 365 Human Resources och andra Dynamics 365-program?

När kunderna har flyttat över till infrastrukturen för ekonomi och drift måste de fortsätta integrera data mellan de två miljöerna. Kunderna kan fortsätta använda daataintegreraren för att utföra dessa datamigreringsuppgifter. Kunder som tänker hålla sin Dynamics 365 Human Resources-miljö åtskild från sin befintliga ekonomi- och driftprogrammiljö måste fortsätta integrera datan mellan de två miljöerna. För kunder som sammanfogar de två miljöerna i en och samma miljö behövs inte längre någon integregrering mellan de två miljöerna.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>Hur kommer data att flyttas mellan Dynamics 365 Human Resources i infrastrukturen för ekonomi och drift och Dataverse efter migreringen?

Den aktuella Dataverse-integreringen mellan Dynamics 365 Human Resources och Dataverse kommer att bli inaktuell som en del av infrastrukturen för ekonomi och drift. Det finns planer på att införa mappningar med dubbel skrivning för att mappa ekonomi- och driftsentiteter till Dataverse-tabeller. Kunderna måste bestämma vilka mappningar med dubbel skrivning som krävs för implementeringen. Vi rekommenderar att virtuella tabeller används för integrering och ISV-lösningar, detta såvida det inte finns ett särskilt affärsbehov av att duplicera data i Dataverse i syfte att köra affärslogik.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>Hur påverkar migreringen Dataverse-tillägg för Dynamics 365 Human Resources?

Kunder måste migrera till en sandbox-miljö innan de migrerar sin produktionsmiljö. När kunderna migrerar sin sandbox-miljö måste de skapa en kopia av sin Dataverse-miljö för att kunna ansluta till den nya migrerade miljön för ekonom i och drift. Vi rekommenderar att kunden kopierar både data och lösningar för miljön, detta så att de matchar kundens aktuella produktionsmiljö.

När kunderna är redo att migrera sin Dynamics 365 Human Resources-produktionsmiljö migrerar Microsoft automatiskt databasen och Azure Blob-lagring. Migrerad databas och lagring kommer att rikta den nya miljön i infrastrukturen för ekonom i och drift till samma Dataverse-produktionsmiljö. Innan data kan fortsätta kopieras till Dataverse måste kunderna aktivera eventuella mappningar med dubbel skrivning som behövs för integrering, tillägg och ISV-lösningar som bygger på Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>Kommer Microsoft Power Platform-komponents som byggts för Dynamics 365 Human Resources att fungera automatiskt efter att infrastrukturmigreringen har slutförts?

Program som skapas i Power Apps, flöden som skapas i Power Automate och andra Microsoft Power Platform-anpassningar liknar Dataverse-tillägg. Under migreringen av kundproduktionsmiljöer påverkas inte Dataverse-miljöer, och inte heller eventuella tillägg. Program, flöden och andra anpassningar av Power Microsoft-plattformar bör fortsätta fungera utan att ytterligare konfiguration krävs.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>Vad händer med virtuella Dataverse-tabellentiteter för Dynamics 365 Human Resources i samband med migrering?

När kunderna migrerar sin Dynamics 365 Human Resources-miljö till infrastrukturen för ekonomi och drift förblir miljön ansluten till den Dataverse-miljö som för närvarande är ansluten till Dynamics 365 Human Resources. De virtuella Dataverse-tabeller som har genererats i miljön fortsätter fungera utan att ytterligare konfiguration krävs. De virtuella registren måste kanske genereras om i den Dataverse-miljö som är ansluten till en kunds befintliga ekonomi- och driftmiljö.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>Hur kommer en integrering som använder ATS-API:t (Sökandespårningssystem), Löne-API, virtuella tabeller för Dataverse för Dynamics 365 Human Resources eller andra entiteter i webb-API:t för Dataverse att fungera när infrastruktursammanslagningen har slutförts?

När kunderna migrerar sin Dynamics 365 Human Resources-miljö till infrastrukturen för ekonomi och drift förblir miljön ansluten till den Dataverse-miljö som för närvarande är ansluten till Dynamics 365 Human Resources. Alla integreringar som utvecklats mot webb-API:t för Dataverse kommer att fortsätta fungera när migreringen är slutförd.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Vår organisation har konfigurerat anpassad säkerhet i Dynamics 365 Human Resources. Kommer denna fortfarande att tillämpas efter att infrastrukturmigreringen är slutförd?

Ja, anpassade säkerhetskonfigurationer inkluderas i datamigreringen.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>Kommer arbetsflöden i Dynamics 365 Human Resources att migreras automatiskt?

Ja, arbetsflödeskonfigurationer, arbetsflödeshistorik och aktuella pågående arbetsflöden kommer att migreras till den sammanfogade infrastrukturen.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>Kommer sparade vyer i Dynamics 365 Human Resources att migreras automatiskt?

Ja, sparade vyer migreras till den sammanfogade infrastrukturen.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Kommer funktioner som aktiveras i Dynamics 365 Human Resources att vara automatiskt tillgängliga när infrastrukturerna har sammanfogats?

- För kunder som använder modulen **Personal** han funktioner som bara finns i Dynamics 365 Human Resources via Funktionshanteringen. Dessa funktioner aktiveras vanligtvis inte som standard. Alla funktioner som måste aktiveras som standard dokumenteras.
- För kunder som använder Dynamics 365 Human Resources kommer funktioner att vara tillgängliga i infrastrukturen. Alla funktioner som inte är tillgängliga dokumenteras. Alla funktionshanteringsnycklar som aktiveras i den aktuella Dynamics 365 Human Resources-miljön aktiveras i den sammanslagna infrastrukturen. Mer information finns i [Översikt för funktionshantering](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>Vad händer med egna (BYOD-) databaser under migreringen?

Import- och exportkonfigurationer för att ta med sin egen databas (BYOD) migreras till infrastrukturen för ekonomi och drift.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>Påverkas Azure-regionen när kundmiljön migreras?

Dynamics 365 Human Resources-miljön kommer att ligga kvar i samma Azure-region för migreringen. Om det finns ett krav på att flytta en miljö till en annan Azure-region måste kunderna följa standardstegen för att migrera till en ny region efter att migreringen är slutförd.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>Vad händer med mina Azure-datasjöar under migreringen?

Alla exporter som för närvarande är konfigurerade för Azure Data Lake i appar för ekonomi och drift bibehåller samma konfiguration efter migreringen.

> [!NOTE]
> Mappningar med dubbelriktad skrivning måste ha aktiverats för att det ska gå att fortsätta skriva data från Personal-miljön till Dataverse.

Kunder som vill exportera personaldata till datasjön kan aktivera funktionen efter att migreringen till infrastrukturen för ekonomi och drift har slutförts. Mer information finns i [Datasjöar – Azure Architecture Center](/azure/architecture/data-guide/scenarios/data-lake).

Kunderna kan koppla flera ekonomi- och driftmiljöer till samma datasjö. Varje miljö pekar emellertid till olika mapp och behållare. Kunder som planerar att sammanfoga miljöer senare bör noggrant planera sin metod.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Vilken migrering krävs om en kund för närvarande använder modulen Personal?

Kunder som använder modulen **Personal** kommer att få de nya Dynamics 365 Human Resources-funktionerna tillämpade på sin miljö via standarduppdateringsprocessen för One Version. Kunderna kan förvänta sig att de nya funktionerna blir tillgängliga i deras miljö i takt med att de blir tillgängliga i respektive uppdatering. Kunder kan använda Funktionshantering för att aktivera funktionerna. Kunder bör planera att validera dessa nya funktioner med hjälp av de processer de redan har på plats och använda för att validera andra uppdateringar av sin miljö.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>Vad händer med anpassade integreringar med externa system?

Kunderna måste migrera sina integreringar till ekonomi- och driftmiljön. Eftersom slutpunkten för den här miljön är olika måste kunderna eventuellt uppdatera eller ändra integreringarna så att dessa pekar på den nya miljön. Den här uppgiften är främst en manuell process, och vilka ändringar som behövs beror på integreringens arkitektur. Kunderna bör arbeta tillsammans med sina Microsoft-partner för att ta reda på hur integrationer kan flyttas.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>Vad händer med Microsoft Power Platform (Dataverse)-tillägg om kunder sammanfogar en Dynamics 365 Human Resources-miljö med en befintlig miljö för ekonomi och drift?

Om kunderna väljer att slå ihop en Dynamics 365 Human Resources-miljö och en befintlig miljö för ekonomi och drift till en enda Dataverse-instans efter migrering, måste deras Dataverse-miljöer kombineras som en del av sammanslagningsprocessen. Den här uppgiften kräver att samtliga program som skapas genom användning av Power Apps och alla andra anpassningar omdistribueras i den nya miljön.

## <a name="what-will-happen-to-documents-during-the-migration"></a>Vad händer med dokument under migreringen?

När kunderna migrerar sin Dynamics 365 Human Resources-miljö till infrastrukturen för ekonomi och drift finns dokumenten kvar i den befintliga dokumentlagringen och mappas automatiskt till den nya miljön i infrastrukturen för ekonomi och drift.

I en framtida version kommer nya dataentiteter att tillhandahållas. När ändringen har gjorts kan kunder som väljer att slå ihop sin Dynamics 365 Human Resources-miljö med en befintlig miljö för ekonomi och drift att kunna exportera dokument och flytta dem till den befintliga miljön.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Efter migreringen, vad händer med de batchjobb som konfigurerats i Dynamics 365 Human Resources?

Batchjobb måste omkonfigureras i miljön för ekonomi och drift. Kunderna måste utvärdera varje batchjobb och jämföra det med aktuell lista över batchjobb i ekonomi- och driftsmiljön. Kunderna bör också analysera den övergripande batchplanen när de slår ihop de två uppsättningarna med batchjobb, detta för att ta reda på om ändringar ska göras i batchplanen, prioriteringarna eller batchgrupperna.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>Hur kommer migreringen att påverka LCS-projektet för Dynamics 365 Human Resources?

Kunderna måste skapa ett nytt Microsoft Dynamics Lifecycle Service-projekt (LCS), och de måste välja appar för ekonomi och drift som produkt och **Implementering** som projekttyp. Ett nytt fält för delprojekttypen är dessutom tillgängligt när ett LCS-projekt skapas. Kunderna måste välja alternativet för Dynamics 365 Human Resources-migrering om de vill flytta ett befintligt LCS-projekt för Personal till den infrastruktur som används för ekonomi och drift.

Funktionerna för LCS-projekt för ekonomi och drift skiljer sig från funktionerna för LCS-projekt av typen Personal.

För att kunna publicera måste nya kunder utföra följande uppgifter:

- Slutföra projektregistreringen.
- Slutföra metoden.
- Fylla i en prenumerationsberäknare.
- Slutföra beredskapsprocessen för publicering.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>Hur kommer Affärsprocessmodelleraren att migreras?

Kunderna måste exportera sitt bibliotek för Affärsprocessmodelleraren från LCS-projektet för Personal och importera det till LCS-projektet för ekonomi och drift. Dessutom måste kunderna uppdatera hjälpinställningarna i programmet så att dessa pekar på det nya LCS-projektet.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>Hur kommer tjänsteuppdateringsprocessen att påverkas av migreringen?

Efter migreringen kommer kunderna att ha mycket större flexibilitet när det gäller hanteringen av programmens livscykel (ALM) samt tjänsteuppdateringar. Tjänsteuppdateringar tillämpas inte längre automatiskt i Personal-miljöer. Istället följer tjänsten uppdateringsprocesserna och -funktionen för One Version, och konfigurationsalternativen för uppdateringar via LCS kommer att aktiveras.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>Är kunderna berättigade till FastTrack-hjälp i samband med infrastruktursammanslagningen?

Microsoft definierar fortfarande vilka verktyg och resurser som ska vara tillgängliga från Fasttrack som hjälp med sammanslagningen.

## <a name="licensing-impact"></a>Licenseringsinverkan

Mer information om hur licensieringen påverkas finns i [Vanliga frågor och svar om infrastruktursammanslagningen för Dynamics 365 Human Resources](hr-infrastructure-merge-faq.md#licensing-impact).
