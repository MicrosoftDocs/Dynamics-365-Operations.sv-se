---
title: Uppgradera Dynamics AX 2012 till Dynamics 365 for Finance and Operations, Enterprise edition
description: "Det här avsnittet beskriver hur kunder som kör Microsoft Dynamics AX 2012 för närvarande kan flytta sina uppgifter och kod till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: sv-se
ms.lasthandoff: 06/15/2017

---

# Uppgradera Microsoft Dynamics AX 2012 till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition
<a id="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition" class="xliff"></a>

[!include[banner](../includes/banner.md)]

I plattformsuppdatering 8 ger Microsoft Dynamics 365 for Finance and Operations, Enterprise edition en uppgraderingsväg som kunder som för tillfället kör Microsoft Dynamics AX 2012 kan använda för att flytta sina data och kod till Finance and Operations. Uppgraderingsprocessen bygger på följande element:

- Verktyg som hjälper dig ta fram befintlig anpassad programkod från AX 2012.
- En datauppgraderingsprocess som du kan använda för att ta fram din databas. Därför kan du uppgradera din fullständiga transaktionshistorik.

## Översikt
<a id="overview" class="xliff"></a>

Den övergripande uppgraderingsprocessen kan vara visualiserad som tre övergripande faser: analysera, köra och validera.

Följande diagram visar uppgraderingsprocessens slutpunkt till slutpunkt och de aktiviteter som vi anser vara en del av varje fas. 

![Uppgraderingsprocess](./media/upgrade-process.png)

## Analysera
<a id="analyze" class="xliff"></a>

Aktiviteterna i analysfasen hjälper dig att uppskatta det arbete som krävs för uppgraderingen. De hjälpa dig också att förbereda en projektplan. Dessa aktiviteter kan utföras innan du köper Finance and Operations. De hjälper dig att fatta ett bra inköpsbeslut genom att tillhandahålla en datapunkt om det arbete och de resurser som krävs.

### Registrera dig för en förhandsgranskning i LCS
<a id="sign-up-for-a-public-preview-in-lcs" class="xliff"></a>

För att utföra analysaktiviteter innan du köper Finance and Operations måste du registrera dig för en förhandsgranskning. Förhandsgranskningen låter dig du distribuera egna Finance and Operations-miljöer. Dessutom får du tillgång till verktyg i Microsoft Dynamics Lifecycle Services (LCS) som används för att utvärdera din AX 2012-miljö och din befintliga anpassade kod.

Om du har ett befintligt LCS-projekt för AX 2012 måste du fortfarande registrera dig för ytterligare ett nytt projekt för att utvärdera Finance and Operations.

Gå till https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview om du vill veta hur du hämtar en förhandsgranskning för kunder.

Gå till https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview om du vill veta hur du hämtar en förhandsgranskning för partner.

Tänk på att denna förhandsgranskning skiljer sig från en [30-dagars testversion](https://aka.ms/D365OperationTrials). 30-dagars testversioner innehåller en distribuerade instans av Finance and Operations som du kan använda för att undersöka och utvärdera programmet. Analysaktiviteter kan dock kräva full LCS-erfarenhet och verktyg.

### Välj uppgraderingsmetod
<a id="select-the-upgrade-methodology" class="xliff"></a>
I ditt nya LCS-projekt tilldelats projektet metoden för att **uppgradera AX 2012 till Dynamics 365 for Operations**. Denna metod är speciellt till för AX 2012-kunder som uppgraderar. Den beskriver de tre faserna i detalj och tillhandahåller länkar till stöddokumentation om processen.

![Uppgradera methodology(./media/methodology.png)
 
### Kör verktyget uppgraderingsanalys
<a id="run-the-upgrade-analyzer" class="xliff"></a>
Det uppgraderade analysverktyget körs mot AX 2012-miljön och identifierar aktiviteter som du bör utföra för att förbereda AX 2012-miljön, så att uppgraderingsupplevelsen blir smidigare och mindre kostsam:

- **Datarensning** – processen hjälper dig att identifiera data som du kan ta bort utan att orsaka funktionsförlust. Verktyget identifierar olika typer av data som du kan minska genom att köra en rensning. För varje typ av data ges en förklaring om vilken effekt rensningen får. Du bestämmer sedan om du vill köra rensningen. En del av kostnaden för prenumerationen på Finance and Operations baseras på databasens storlek. Genom att minska storleken kan du därför minska den delen av abonnemangskostnaden och även minska den tid som krävs för att utföra uppgraderingen. En mindre databas bidrar till att garantera en snabbare uppgradering.
- **Konfigurera SQL** – processen granskar SQL-konfigurationen och rekommenderar optimeringar. Genom att se till att SQL fungerar optimalt kan den här processen minska den tid som krävs för att publicera uppgraderingen.
- **Gamla funktioner** – den här processen identifierar de funktioner som du använder för närvarande, men som inte är tillgängliga i Finance and Operations. Därför hjälper processen dig att tidigt upptäcka luckor i funktionen. Den ger även förslag på alternativ.

Dessutom, som en del av det här steget, måste du installera KBXXXXXXX i AX 2012-miljön. Denna snabbkorrigering innehåller en checklista för föruppgradering. Du kan använda checklistan i AX 2012-miljön för att ange data som krävs för uppgraderingsprocessen. I en checklista för föruppgraderingaktivitet kan du till exempel ange Microsoft Azure Active Directory (Azure AD)-inloggningsuppgifter för varje aktuell AX 2012-användare så att varje användare kan logga in på Finance and Operations.

Resultatet av det här steget blir arbetsflödet i projektplanen för uppgraderingen för dina AX 2012-systemadministratörer.

Mer information finns i [Analys: använda verktyget uppgraderingsanalys för att planera migreringsarbetet](upgrade-analyzer-tool.md).

### Köra uppskattningsverktygen för uppgradering av kod
<a id="run-the-code-upgrade-estimation-tools" class="xliff"></a>
Detta steg tar koden från AX 2012, konverterar den till det nya formatet och ger information om konflikter som en utvecklare måste lösa senare. Åtgärden ligger till grund för att beräkna kostnaden för din koduppgradering.

För att slutföra den här åtgärden måste du exportera koden från AX 2012 som en export av en modellagringsplats och överföra den till LCS-koduppgraderingsverktyget. Koduppgraderingsverktyget skapar en uppgraderingsversion av koden och en rapport om de återstående konflikter som måste åtgärdas. Utvecklaren kan sedan granska både uppgraderad kod och rapporten för att avgöra vilken insats som krävs för att uppgradera din kodbas.

Resultatet av det här steget blir arbetsflödet i projektplanen för uppgraderingen för dina Microsoft Dynamics AX-utvecklare.

Mer information finns i [Analys: beräkna insatsen för att uppgradera kod](analyze-code-upgrade.md).

### Distribuera en demomiljö
<a id="deploy-a-demo-environment" class="xliff"></a>
Demo-miljöer är standardmiljöer som innehåller demonstrationsdata (inte dina egna data) och standardkoden (inga anpassningar). Vi rekommenderar att du distribuerar en demo-miljö för att granska de nya funktionerna och för att utföra en grundläggande GAP-analys av standardprocesser som används i AX 2012, men som kan ha ändrats i Finance and Operations. Du kan antingen distribuera dessa demo-miljöer i Azure eller hämta dem som en VM (virtual machine) som körs på din egen maskinvara. Om du distribuerar dem i Azure måste du tillhandahålla din Azure-prenumeration, eftersom du fortfarande använder ett förhandsgranskningsprojekt och ännu inte har köpt en Finance and Operation-prenumeration.

Resultatet av det här steget blir arbetsflödet i projektplanen för uppgraderingen för dina funktionella användare eller affärsanvändare.

Mer information finns i [analys: distribuera ett begränsat läge](analysis-sandbox.md)

### Skapa en projektplan
<a id="create-a-project-plan" class="xliff"></a>
En mall för en projektplan finns i uppgraderingsmetodiken. I det här steget används utdata från föregående steg i analysfasen för att fylla projektplanen för uppgraderingsprojektet. Projektplanen innehåller också all testinformation: datauppgraderingstestning, övergångstestning, funktionstestets passupprepningar och information om de olika resurstilldelningarna för aktiviteterna.

I den här steget ger projektplanen en datapunkt som kan hjälpa dig att förstå tiden och kostnaden för en uppgradering till Finance and Operations.

## Kör
<a id="execute" class="xliff"></a>
Under utförandefasen arbetar du med uppgifter som du har planerat under analysfasen. Om du vill gå till utförandefasen måste du köpa Finance and Operations och du måste ha tillgängliga resurser som kan fungera med uppgraderingen.

### Växla till LCS-implementeringsprojektet
<a id="switch-to-the-lcs-implementation-project" class="xliff"></a>
Förhandsgranskningen av projektet som du använde för att analysfasen har tjänat sitt syfte. Nu kan du kasta den. I de återsående stegen behöver du bara projektplanen som du skapade i det sista steget i analysfasen.

När du köper en Finance and Operations-prenumeration får du information om hur du registrerar dig för ett nytt LCS-projekt. Projektet kallas för ett implementeringsprojekt och blir det nya permanenta LCS-projektet för din prenumeration så länge du har denna prenumeration. Det här projektet skiljer sig från förhandsgranskningen av projektet på så sätt att det hanteras av Microsoft. Därför har projektet följande egenskaper:

- Alla miljöer i projektet har en värd i Azure.
- Azure-abonnemanget som är kopplat till projektet hanteras av Microsoft. Därför sker ingen separat fakturering för Azure-kostnader. Kostnaderna omfattas av din Finance and Operations-prenumeration.
- Produktionsmiljön i projektet underhålls av Microsoft. Därför körs koddistributioner, uppgraderingar och underhåll av infrastruktur direkt av Microsoft, inte av personalen. 

### Utföra förberedelseåtgärderna för AX 2012
<a id="perform-the-ax-2012-preparation-tasks" class="xliff"></a>
Utför uppgifterna som identifieras av verktyget för uppgraderingsanalys och som är dokumenterade i projektplanens uppgradering. Din systemadministratör för Microsoft Dynamics AX och databasadministratör (DBA) måste utföra de här uppgifterna.

[Datauppgradering från AX 2012 till Dynamics 365 for Operations – checklista för föruppgradering i AX 2012](prepare-data-upgrade.md)

### Utföra koduppgraderingen
<a id="perform-code-upgrade" class="xliff"></a>
Utför åtgärderna som planerades under steget för uppskattning av koduppgraderingen i analysfasen. Utvecklarna måste köra dessa uppgifter.

Härifrån och framåt ska kodändringarna i AX 2012 frysas. Endast nödkodsändringar ska tillåtas i AX 2012. Om en ändring görs måste den porteras manuellt till den nya kodbasen.

### Utveckla ny kod
<a id="develop-new-code" class="xliff"></a>
Slutför uppgifterna från GAP-analysen som utfördes under steget ”Distribuera en demomiljö” i analysfasen. Åtgärderna kommer troligen att vara en blandning av funktionella åtgärder som definierar konfigurations- och utvecklingsåtgärderna för anpassningar som är relaterade till nya funktioner som tas upp.

### Datauppgradering (utvecklingsmiljö)
<a id="data-upgrade-development-environment" class="xliff"></a>
När dina koduppgraderingsuppgifter har slutförts kan du uppgradera AX 2012-databasen till Finance and Operations för första gången. Första uppgraderingen sker i en utvecklingsmiljö, så att du lättare kan reparera eller felsöka eventuella problem som identifierats i detta steg. Problemet kan felsökas direkt i en utvecklingsmiljö, koden kan justeras och uppgraderingen kan köras om inom ett par minuter. Större begränsade lägen har inte den här flexibiliteten och det tar minst flera timmar att felsöka och åtgärda problem, uppdatera kod, distribuera uppdaterad kod och köra om uppgraderingen.

På bilden nedan visas processen. Säkerhetskopiera bara AX 2012-databasen, ladda upp den till Azure, återställ Finance and Operations-miljön och kör sedan datauppgraderingen.

![Datauppgradering i en utvecklingsmiljö](./media/data-upgrade-dev.png)
 
Datauppgraderingen sker via en speciell typ av distribuerbara paket. Samma mekanism används för att distribuera ny Finance and Operations-kod från en miljö till en annan.

Det underliggande ramverket som används för att konvertera data i databasen under processen är i stort sett samma som uppgraderingsramverket i AX 2012 som baseras på X++-batchjobb som kör **ReleaseUpdatexxx**-klasser.

Mer information finns i [Datauppgradering från AX 2012 till Dynamics 365 för operationer i en utvecklingsmiljö](data-upgrade-2012.md).

### Datauppgradering (begränsade miljöer)
<a id="data-upgrade-sandbox-environments" class="xliff"></a>
När datauppgradering i en utvecklingsmiljö är slutförd, kan samma process köras i en avgränsad miljö. Begränsat läge är en miljö där företagsanvändare och funktionella gruppmedlemmar kan testa affärsprocesser med hjälp av uppgraderade AX 2012-data och -kod.

Följande bild visar hur processen för datauppgradering körs i begränsat läge. Skillnaden här är att bacpac-verktyget används i stället för en traditionell SQL-säkerhetskopia. Det här verktyget behövs för att konvertera mellan Microsoft SQL Server och Azure SQL-databasen. Det är ett SQL-verktyg av standardtyp och är inte specifik för Finance and Operations.

![Datauppgradering i begränsat läge](./media/data-upgrade-sandbox.png)

Mer information finns i [Datauppgradering från AX 2012 till Dynamics 365 för operationer i en avgränsad miljö](upgrade-data-sandbox.md).
 
## Validera
<a id="validate" class="xliff"></a>
När du går in i valideringsfasen har du tillgängliga miljöer som inkluderar din uppgraderade anpassade kod och dina uppgraderingsdata. Det här steget beskriver processen för validering och testning av att den uppgraderade miljön fungerar som den ska. Här beskrivs processen för hur du förbereder publicering.

### Utföra övergångstest och skapa en övergångsplan
<a id="perform-cutover-testing-and-create-a-cutover-plan" class="xliff"></a>
Termen _övergång_ används här för att beskriva den slutliga processen för att publicera det nya systemet. Processen består av de uppgifter som inträffar efter att AX 2012 stängs av och innan Finance and Operations aktiveras. 

Syftet med testet är att öva på övergångsprocessen. På så sätt kan du garantera att alla som är inblandade i den faktiska övergången till publiceringen får en smidig upplevelse.

Det finns två huvudsakliga arbetsflöden:

- **Tekniskt arbetsflöde** – den här arbetsflödet innebär att köra datauppgraderingen. Din affärsverksamhet kommer att tvinga fram en gräns för hur långt driftstopp som kan tillåtas. Under driftstoppet kommer varken AX 2012 eller Finance and Operations att vara tillgängliga. Det tekniska arbetsflödet behöver kanske justera prestandan i datauppgraderingsprocessen så att den uppfyller företagets driftstoppsgräns. 
- **Funktionellt arbetsflöde** – efter att data har uppgraderats kan flera konfigureringsaktiviteter krävas i Finance and Operations-miljön. Dessa uppgifter skall dokumenteras och kvantifieras och en resurs måste tilldelas dem, eftersom de måste passa ihop med de tekniska uppgifterna inom företagets driftstoppsgräns.

Mer information finns i 
- [Validera: övergångstestning](upgrade-cutover-testing.md)
- [Validera: appvalideringsprocess](app-validation-process.md)

### Funktionstestpass
<a id="functional-test-pass" class="xliff"></a>
Slutför ett fullständigt funktionstestpass för alla affärsprocesser. Det här testpasset blir en omfattande omtestning av alla affärsprocesser som rör Finance and Operations. Dessa affärsprocesser inkluderar både gamla processer som togs fram från AX 2012 och nya processer som inbegriper nya funktioner som togs upp för första gången i Finance and Operations. 

Beroende på kodens kvalitet krävs problemlösning och omtestning kan kräva åtskilliga iterationer av funktionstestningspasset. När ett problem har korrigerats måste alla berörda processer testas på nytt, för att garantera att nedströms- eller uppströmsprocessen inte påverkas av ändringen.

Mer information finns i [Validera: funktionstestning](upgrade-functional-validation.md).

### Checklista för publicering
<a id="pre-go-live-checklist" class="xliff"></a>
Checklistan för förpublicering är en rekommenderad procedur som kan hjälpa dig att minska risken för fel under den sista övergången till publicering. En vecka före publicering, stoppa konfigurationsändringar i AX 2012 (det vill säga, under \<modulen\>\Setup). Den här begränsningen av konfigurationsändringar är enbart procedurmässig. Microsoft Dynamics AX-systemadministratören accepterar bara att spärra den här typen ändringar i det här läget.

Vi rekommenderar att du även spärrar kodändringar i kodbasen för Finance and Operations. Inga ytterligare ändringar ska tillåtas om de inte har utvärderats och har visat sig inte hindra publiceringen.  

När konfigurationsbegränsningen och koden har spärrats bör datauppgraderingen köras för sista gången innan övergången. På så sätt kan se du till att allting fortfarande fungerar som förväntat. 

Mer information finns i [Validera: förbereda publicering](upgrade-go-live-prep.md).



### Uppgraderingsvägar som stöds
<a id="supported-upgrade-paths" class="xliff"></a>
Från och med juni 2017 stöds uppgradering till Microsoft Dynamics 365 för Finance and Operations, Enterprise edition, version 0617 från Microsoft Dynamics AX 2012 R3. Alla samlade uppdateringar (CUs) i AX 2012 R3 stöds.

Microsoft Dynamics AX 2012 R2 och Microsoft Dynamics AX 2012 RTM stöds inte för närvarande. Support läggs till senare under 2017.

Endast uppgradering till den molndistribuerade versionen av Finance and Operations stöds. Uppgraderingen till den lokala versionen stöds inte. Stöd för uppgradering till den lokala versionen läggs till senare under 2017.

