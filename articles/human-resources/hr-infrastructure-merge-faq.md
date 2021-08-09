---
title: Vanliga frågor om Dynamics 365 Human Resources infrastrukturkoppling
description: Det här avsnittet innehåller svar på vanliga frågor om den infrastruktur som har kopplats för Microsoft Dynamics 365 Human Resources och Finance and Operations-appar.
author: rachel-profitt
ms.date: 07/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fee4fea9b67ff8a0c8d813940a65cf882bd13abe
ms.sourcegitcommit: bf2daeccbe3f2826e734f409bfc823820144aa23
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2021
ms.locfileid: "6618001"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Vanliga frågor om Dynamics 365 Human Resources infrastrukturkoppling

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet innehåller svar på vanliga frågor om den infrastruktur som har kopplats för Microsoft Dynamics 365 Human Resources och Finance and Operations-appar.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Vad är Dynamics 365 Human Resources infrastrukturkoppling?

Dynamics 365 Human Resources är ett fristående program som använder olika infrastrukturer än andra Finance and Operations-appar, t.ex. Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Project Operations. Infrastrukturkopplingen kommer att föra in Dynamics 365 Human Resources i samma infrastruktur som andra Finance and Operations-program.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Värde och fördelar med infrastrukturkopplingen

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>Min organisation använder Dynamics 365 Human Resources för att hantera sina personaloperationer. Vilka fördelar får vi då dessa ändringar?

- Dessa ändringar eliminerar flera personaluppsättningar i Dynamics 365.
- De ger både Microsoft Power Platform utvidgningar och ett sätt att utöka affärslogik och funktionsalternativ.
- De ger konsistens mellan Dynamics 365 Human Resources och annars Finance and Operations-appar vad gäller program livscykelhantering (ALM), Microsoft Dynamics Lifecycle Services (LCS) geografisk tillgänglighet, utökningsbarhet och mer.
- Med hjälp av dessa kan du dra nytta av delade tjänster och verktyg och minska kostnaderna.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Min organisation använder Dynamics 365 Human Resources i Dynamics 365 Finance, Supply Chain Management, Commerce eller Project Operations. Vilka fördelar får vi då dessa ändringar?

Funktionerna och investeringar som har gjorts i kommer nu Dynamics 365 Human Resources att vara tillgängliga för kunder som använder personalmodulen i Dynamics 365 Finance. Vissa av funktionerna omfattar tjänstledighets- och frånvarohantering, förmånshantering och uppgiftshantering.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Förlorar jag några funktioner eller funktioner som jag för närvarande använder?

Det kommer att finnas funktionell paritet Dynamics 365 Human Resources mellan och personal modulen i Finance and Operations-app. Dynamics 365 Human Resources gäller för liknande funktioner. Mer information finns i [Översikt för funktionshantering](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>Kommer erfarenhetsändringen för mina användare?

De nya personalfunktionerna hanteras med funktionshantering. Kunderna bestämmer om de vill öppna om de vill öppna en ny kund eller inte. I vissa fall kan funktionerna ändras. I så fall ges dokumentation.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Hur påverkar denna förändring mig om jag är en befintlig kund och jag använder både HR-modulen på Finance and Operations infrastruktur och Dynamics 365 Human Resources genom anpassade integrationer?

Anpassade integreringar mellan Dynamics 365 Human Resources och personalmodulen i Dynamics 365 Finance behöver inte längre göras. Alla personaldata finns i samma databas som andra Finance and Operations-appar.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migrera från Dynamics 365 Human Resources till Finance and Operations-appar

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Min organisation använder Dynamics 365 Human Resources för att hantera sina personaloperationer. Vad har vi att planera för att flytta till den nya erfarenheten?

Om din organisation använder Dynamics 365 Human Resources men använder ingen annan Finance and Operations appar, kommer din HR -miljö att migreras till den nya infrastrukturen. Större delen av migreringsprocessen kommer att vara automatiserad. Processer används för att flytta databasen och synkronisera den med den nya infrastruktur.

Dessutom finns verktyget på plats så att du kan testa migreringsprocessen och validera dina data och erfarenheter innan du migrerar produktionsmiljön.

Om din organisation använder båda Dynamics 365 Human Resources och Finance and Operations-appar, bör du planera mer tid för validering för att säkerställa att dina data migreras korrekt till den nya miljön. Under migreringen till den nya infrastruktur sammanfogas data från din Personal-miljö med Finance and Operations-miljö. Verktyg finns på plats för att automatisera så mycket som möjligt i kopplade dataprocesser. Om data står i konflikt måste dock användarindata anges för att definiera hur konflikterna ska lösas. Användare och administratörer måste hantera datamappningarna där det finns konflikter och testa migreringen i arbetsmiljöer innan produktionsmiljön migreras.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Min organisation använder Dynamics 365 Human Resources i Dynamics 365 Finance, Supply Chain Management, Commerce eller Project Operations. Vad har vi att planera för att flytta till den nya erfarenheten?

För organisationer som använder HR -modulen i Finance and Operations-appar, den nya funktionaliteten från Dynamics 365 Human Resources kommer att tillämpas på din miljö genom standardprocessen för en version. Du kan förvänta dig att de nya funktionerna i din miljö blir tillgängliga i varje uppdatering. Du kan använda funktionshantering för att aktivera nya funktioner. Du bör dock planera att validera dessa funktioner. Följ de processer du har på plats för att validera andra uppdateringar av din miljö. För mer information om hur uppdateringar tillämpas på Finance and Operations-appar, se [One Version översikt](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>När kommer min organisation att migreras?

Migreringen för respektive organisation beror på dess aktuella konfiguration och beredskap att flytta till den nya infrastruktur. Dessa datum kan ändras.

- Organisationer som för närvarande använder HR -modulen i Finance and Operations appar får HR-funktionen för Dynamics 365 Human Resources som en del av den vanliga uppdateringsprocessen för en One Version. Nya funktioner planeras bli allmänt tillgängliga från och med oktober 2021.
- Organisationer som för närvarande bara använder Dynamics 365 Human Resources kommer att ha tillgång till migrationsverktyg så att de kan börja testa och starta migrationen som börjar i mitten av 2022. Datumet då migreringen till den nya infrastrukturen måste ha slutförts har ännu inte bestämts. Den kommer dock att vara minst ett år efter det datum då verktyget för migrering blir tillgängligt.
- Organisationer som för närvarande bara använder Dynamics 365 Human Resources och andra Finance and Operations-appar kommer att ha tillgång till migrationsverktyg så att de kan börja testa och starta migrationen som börjar sent år 2022. Datumet då migreringen till den nya infrastrukturen måste ha slutförts har ännu inte bestämts. Den kommer dock att vara minst ett år efter det datum då verktyget för migrering blir tillgängligt.

Mer information om de nya funktionerna för Dynamics 365 Human Resources finns i [Vad är nytt eller ändrat i Personal](./hr-admin-whats-new.md).

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Jag använder nya funktioner som bara är tillgängliga i Dynamics 365 Human Resources (t.ex. **Tjänstledighet och frånvaro** och **Hantering av förmåner**). Kommer dessa funktioner nu att vara tillgängliga även i modulen Personal i Finance and Operations infrastruktur?

Ja, alla moduler Dynamics 365 Human Resources kommer i befintligt skick Finance and Operations-appar det kommer att finnas 100 procent funktionsparitet. Som en del av den övergripande migreringsstrategin för kunder som för närvarande använder dessa kapaciteter i personal, migreras kunddata så att de fortsätter att arbeta med Finance and Operations infrastruktur.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>Jag använder de nya Dynamics 365 Human Resources funktionerna för hantering av förmåner. Jag har byggt anpassade integrationer med HR-modulen på Finance and Operations infrastruktur så att jag kan dra nytta av lönefunktionerna genom att använda förmånsdata. Kommer dessa anpassade integrationer att krävas framåt?

Som en del av infrastrukturkopplingen förs personaldata in i samma databas som andra Finance and Operations-appar. Integrationen mellan moduler i Finance and Operations-appar behöver inte längre göras.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>Min organisation använder en eller flera ISV-lösningar med Dynamics 365 Human Resources. Kommer våra ISV-lösningar att migreras automatiskt?

Migreringserfarenheterna för varje oberoende lösning för programvaruleverantör (ISV) varierar beroende på hur lösningen integreras. Microsoft kommer att arbeta nära ISV för att säkerställa en smidig övergång till den nya infrastruktur.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>Min organisation använder LinkedIn Talent Hub-integration med Dynamics 365 Human Resources. Kommer denna integration att fortsätta arbeta efter det att infrastrukturändringen är klar?

Ja, LinkedIn Talent Hub Integration kommer att fortsätta arbeta efter migreringen till den nya infrastruktur.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Min organisation använder programmet Personal för Teams. Kommer appen att fortsätta arbeta efter det att infrastrukturändringen är klar?

Ja, Human Resources-app för Teams kommer att fortsätta arbeta efter migreringen till den nya infrastruktur.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Min organisation har konfigurerat anpassad säkerhet i Dynamics 365 Human Resources. Kommer vår anpassade säkerhet fortfarande att tillämpas efter att infrastrukturändringen är klar?

Ja, anpassade säkerhetskonfigurationer inkluderas i dataöverflyttningen till den nya infrastruktur.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Vi använder dataintegratorn för att flytta data mellan Dynamics 365 Human Resources och Finance and Operations-program. Hur påverkas de data som för tillfället integreras?

Personaldata som för närvarande hanteras i Dynamics 365 Human Resources är synkroniseras med Dataverse. Dataintegrerare kan sedan användas för envägssynkronisering med Finance and Operations-program. När du har migrerat till den nya infrastrukturerna kommer personaldata att finnas med i Finance and Operations-appar. Dataintegratorn behöver inte längre synkronisera data mellan Finance and Operations-appar och personal.

De aktuella inbyggda Dataverse dataregistren för Personal fortsätter att synkronisera data från miljön på den nya infrastrukturen. Enheterna konverteras för att stödja nedskrivning. Alla andra dataintegrationer som konfigureras via Dataintegrator mot dessa register för andra Dynamics 365-program fortsätter att fungera som de är konfigurerade.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Vi använder webbskrivning för att flytta personaldata mellan Dataverse och andra Finance and Operations-program. Hur påverkas de data som för närvarande integreras av migreringen till den nya infrastrukturen?

HR -data kommer att vara infödda till Finance and Operations-appar i miljön på den nya infrastrukturen. Dubbelriktad skrivning här informationen används sedan för att flytta personaldata mellan den nya miljön och Dataverse-miljön.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Vi har skapat anpassade integrationer från Dynamics 365 Human Resources till ett eller flera externa system. Måste vi utveckla nya integreringar efter att infrastrukturändringen är klar?

Det beror på integrationsslutpunkten. För mer information om integrationstekniker som finns tillgängliga i Finance and Operations-appar och hur man väljer den bästa integrationstekniken, se [Översikt över Integration](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Vi har utökat Dataverse för Dynamics 365 Human Resources. Kommer dessa lösningar att migreras automatiskt?

Om Dynamics 365 Human Resources och Finance and Operations-miljöer som kommer att förenas i miljön på den nya infrastrukturen är anslutna till sammaDataverse-miljö, kommer de två apparna att fortsätta att vara anslutna till samma Dataverse-miljö efter migreringen. Därför krävs ingen migrering för Dataverse-tillägg.

Om Dynamics 365 Human Resources och Finance and Operations-miljöer är för närvarande anslutna till separata Dataverse-miljöer måste de två Dataverse miljöerna kombineras så att de är anslutna till en enda miljö på den nya infrastrukturen. För denna Dataverse migrering kan Dataverse tabellerna som är standard för personallösningar kan vara anslutna synkroniseras med den nya Dataverse-miljön. Alla utökningar av Dataverse-miljön migreras emellertid inte automatiskt, utan måste omdistribueras i den nya miljön. Vi rekommenderar att du använder hanterade lösningar för hantering av Dataverse-tillägg. Mer information finns i [Introduktion till lösningar](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Vi har konfigurerat Microsoft Power Automate flöden och/eller Microsoft Power Apps att arbeta Dynamics 365 Human Resources. Kommer dessa Microsoft Power Platform-komponenter att migreras och arbeta automatiskt när infrastrukturändringen är klar?

Power Apps, Power Automate-flöden och andra Microsoft Power Platform-anpassningar liknar Dataverse-utvidgningar. Om de fungerar automatiskt efter migreringen till den nya infrastrukturen beror på om Human Resources-appen och Finance and Operations-apparna ansluts till samma Power Apps miljö före migreringen.

Om apparna för närvarande är anslutna till samma Power Apps-miljö, kommer de att fortsätta vara anslutna till den Power Apps-miljön efter migreringen till den nya infrastrukturen. I så fall fortsätter Power Apps, Power Automate-flöden och andra Microsoft Power Platform anpassningar att fungera utan ytterligare konfiguration. Vi rekommenderar att du använder hanterade lösningar för hantering av apptillägg i Dataverse. Mer information finns i [Introduktion till lösningar](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

Om emellertid Human Resources-appen och Finance and Operations-apparna är anslutna till separata Power Apps-miljöer måste de kombineras som en del av migreringen. Den här uppgiften kräver att Power Apps och andra anpassningar omdistribueras i den nya miljön.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Vi har aktiverat Dataverse virtuella register för Dynamics 365 Human Resources. Vad händer med dessa register under migreringen?

Efter migrationen, om miljön på den nya infrastrukturen förblir ansluten till Dataverse miljö som för närvarande är ansluten till Dynamics 365 Human Resources, kommer Dataverse virtuella tabeller som har genererats i den miljön fortsätter att fungera utan ytterligare konfiguration.

Men om miljön på den nya infrastrukturen är ansluten till en annan Dataverse miljö efter migrationen måste de virtuella tabellerna återskapas i det nya Dataverse-miljö.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Vi har utvecklat en integration genom att använda ATS-API (Applicant Tracking System), Payroll API, Dataverse virtuella register för Dynamics 365 Human Resources eller andra enheter i Dataverse webb-API:t. Kommer denna integration att fortsätta arbeta efter det att infrastrukturändringen är klar?

Efter migrationen, om miljön på den nya infrastrukturen förblir ansluten till Dataverse miljö som för närvarande är ansluten till Dynamics 365 Human Resources, kommer Dataverse alla integrationer som har utvecklats mot Dataverse Web API fortsätter att fungera när migreringen är klar.

Efter migrationen, om miljön på den nya infrastrukturen förblir ansluten till Dataverse-miljön efter migreringen måste alla efter migrationen, alla integrationer som har utvecklats mot Dataverse Webb-API måste omkonfigureras så att de ansluter till det nya Dataverse-miljön.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>Påverkas Azure-regionen när min miljö migreras?

Personalmiljön förväntas vanligtvis ligga kvar i samma Azure-region under migreringen. Det enda undantaget inträffar om Human Resources-miljön kopplas till en Finance and Operations-miljö i en annan region. I det här fallet flyttas Human Resources-miljön till Azure-regionen i Finance and Operations-miljön.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>Min organisation är beroende av arbetsflöden i Dynamics 365 Human Resources för en eller flera affärsprocesser. Kommer dessa arbetsflöden att migreras automatiskt?

Ja, arbetsflödeskonfigurationer, arbetsflödeshistorik och aktuella pågående arbetsflöden migreras.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Vilka utbildningar och resurser finns tillgängliga för att hjälpa till med migreringsprocessen?

Detaljerad dokumentation finns med där du ingående kan beskriva varje steg i migreringsprocessen. Ytterligare utbildningsresurser, som till exempel arbetscenter och andra, kan också vara tillgängliga, beroende på vilka behov som finns.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>Min organisation har skapat sparade vyer i Dynamics 365 Human Resources för att förbättra användarvänliga gränssnittet. Kommer Sparade vyer migreras automatiskt?

Ja, sparade vyer migreras till den nya infrastruktur.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Vi använder Ceridian med Dynamics 365 Human Resources. Kommer Ceridian-integration att vara tillgänglig efter det att infrastrukturändringen är klar? 

Integrationen med Ceridian migreras till Löne-API-baserad integration. Den filbaserade integrationen som för närvarande finns i Dynamics 365 Human Resources migreras inte till Finance and Operations infrastruktur. Mer information finns i [Löne-API-introduktion](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Hur kommer migreringen att påverka serviceuppdateringsprocessen?

Efter migreringen kommer kunderna att ha mycket mer flexibilitet när det gäller ALM och serviceuppdateringar. Serviceuppdateringar används inte längre automatiskt i Personal-miljöer. I stället följer tjänsten One Version av uppdateringsprocesserna och -funktionen. Därför är konfigurationsalternativ för uppdateringar tillgängliga via LCS. Mer information finns i [Översikt över One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Hur kommer migreringen att påverka mitt LCS-projekt för Dynamics 365 Human Resources?

Migreringen till den nya infrastruktur kommer att flytta hanteringen av dina Dynamics 365 Human Resources-miljöer till ett LCS-implementeringsprojekt. Om migreringen kopplar Dynamics 365 Human Resources till en befintlig Finance and Operations- miljö kopplas ditt Personal LCS-projekt till LCS-implementeringsprojekt för Finance and Operations-appen. Om du för närvarande bara använder Dynamics 365 Human Resources kommer ett nytt LCS implementation LCS-implementeringsprojekt skapas och ditt befintliga Personal LCS-projekt kommer att migreras till nästa projekt.

Det nya projektet kommer att vara av samma typ som Finance and Operations-appar använder. Den kommer att ha samma funktioner och funktionalitet för miljöhantering. Mer information finns i [Lifecycle Services, resurser](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Vi har kopplat vår uppgiftsregistrering till Affärsprocessmodellerare i Personal. Hur migrerar och sammanfogas Affärsprocessmodelleraren till LCS?

Affärsprocessbibliotek för LCS-projektet flyttas till det nya LCS-projektet för Personal.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>Min organisation använder för närvarande bara Dynamics 365 Human Resources. Vilka resurser är tillgängliga så att vi kan lära oss mer om utvecklingskapaciteterna när infrastrukturändringen har slutförts?

Både Microsoft Power Platform utvidgningsalternativ och Finance and Operations utvidgningsalternativ är tillgängliga och kan användas för utveckling. Mer information finns i [Utveckla och anpassa startsidan](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Vi har aktiverat funktioner i Dynamics 365 Human Resources. Aktiveras de här funktionerna automatiskt under migreringen?

Om en funktion aktiveras automatiskt i den nya infrastruktur avgörs individuellt för varje funktion. Den här informationen inkluderas i funktionsdokumentationen.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Vad händer med min BYOD-databas under migreringen?

Import- och exportkonfigurationer för att ta med din egen databas (BYOD) migreras till den nya infrastruktur.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Vad händer med min Azure Data Lake under migreringen?

Alla exporter som för närvarande är konfigurerade för Azure Data Lake Storage i Finance and Operations-appar underhåller samma konfiguration efter migreringen.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Vi använder just nu Dynamics AX 2012. Kommer de uppgraderingsverktyg som för närvarande är tillgängliga att användas för att uppgradera HR -modulen AX 2012 till Dynamics 365 Human Resources?

Ja. Dynamics 365 Human Resources inkluderas i den sammanslagna kodbasen och i infrastruktur för Finance and Operations-appar. Vid en uppgradering från Dynamics AX 2012 till Dynamics 365 Human Resources används samma uppgraderingssökväg och verktyg som används vid uppgradering till den senaste versionen av Finance and Operations-appar.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Vi använder dokumenthantering med Dynamics 365 Human Resources. Vad händer med dokumenten under migreringen?

Dokumenten ligger kvar i den befintliga dokumentlagringen. De mappas om till miljön i den nya infrastrukturen.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Vad händer med de batchjobb som vi har konfigurerat efter Dynamics 365 Human Resources efter migreringen?

Tillämpliga batchjobb migreras automatiskt till den nya infrastruktur.

## <a name="licensing-impact"></a>Licenseringsinverkan

Den här dokumentationen ersätter eller ersätter inte någon av de juridiska dokument som täcker användningsrättigheter.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>Min organisation använder Dynamics 365 Human Resources för att hantera sina personaloperationer. Ändras våra licenser eller kostnader?

Kunder som har köpt Dynamics 365 Human Resources-licenser påverkas inte. Det finns ingen licensieringsmigrering för den här kunden. Den extra lagerhållningsenheten (SKU) som är specifik för Personal kan inte längre användas. I stället kan kunderna välja att köpa en Finance and Operations-appar nivå 2 sandbox-miljö till en något lägre kostnad. Befintliga kunder som har köpt en sandbox-miljö för Personal kommer att migreras till en Finance and Operations-app nivå 2 utan extra kostnad.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Min organisation använder Dynamics 365 Human Resources i Dynamics 365 Finance, Supply Chain Management, Commerce eller Project Operations. Ändras mina licenser eller kostnader?

Befintliga användare av Dynamics 365-appar och användare av fristående Dynamics 365 Finance, Supply Chain Management, Commerce, och Project Operations kan få åtkomst till Personal som en del av dessa licenser till februari 2025 eller tills det nuvarande licensavtalet löper ut, beroende på vilket som inträffar tidigare. Du kan välja att flytta till Personal-licenser tidigare om det hjälper dig att få bättre kostnadsbesparande. Från och med februari 2025 måste alla befintliga CSP- och personalkunder ta bort modulen HR och köpa Personal-licenser för att kunna dra nytta av den nya kapaciteten som tas med i Finance and Operations-programmen.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Min organisation använder med Dynamics 365 Finance, Supply Chain Management, Commerce eller Project Operations. Måste vi köpa in ytterligare en miljö för att kunna stödja infrastrukturkopplingen?

Ytterligare miljöer behövs inte för att stödja infrastrukturändringen.

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>Vart ska jag gå om jag har fler frågor om produktlicensen?

Om du har licensfrågor hittar du mer information om [Biz-appar Biz Biz – D365 Prissättning och licensiering](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering). Om informationen inte hjälper dig med ditt problem öppnar du en begäran med LicenseQ.