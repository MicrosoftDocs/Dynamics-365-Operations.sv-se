---
title: Commerce-analyser (förhandsversion)
description: Det här avsnittet innehåller information om hur du installerar och använder analysfunktionerna i Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/24/2022
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 7e3721421e15bc3e5937691cdbaee51e4d3cdd17
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349753"
---
# <a name="commerce-analytics-preview"></a>Commerce-analyser (förhandsversion)

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du installerar Commerce-analyser (förhandsversion), den funktionella analyskapacitet som finns i Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Commerce-analyser (förhandsversion) livedemo

Du kan testa en [live-demo av Commerce-analyser (förhandsversion)](https://aka.ms/CommerceAnalyticsDemo).

![Commerce-analyser (förhandsversion) sammanfattning](media/CommerceAnalytics_Summary.png)
![Commerce-analyser (förhandsversion) betalningar](media/CommerceAnalytics_Payments.png)
![Commerce-analyser (förhandsversion) webbaktivitet](media/CommerceAnalytics_WebActivity.png)

## <a name="commerce-analytics-preview-system-architecture"></a>Commerce-analyser (förhandsversion) systemarkitektur

### <a name="key-components"></a>Nyckelkomponenter

Commerce-analyser (förhandsversion) består av följande nyckelkomponenter:

- Interaktiva Power BI rapporter som är klara att användas
- SQL-vyer i Azure Synapse Analytics
- Enhetsdata och ontologi-data i Azure Data Lake
- Rådata i Data Lake

![Nyckelkomponenter i systemarkitekturen för Commerce-analys](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Dataflöde

#### <a name="step-1-data-generation"></a>Steg 1: Datagenerering

Data har antingen sitt ursprung i transaktionsdata eller som beteendedata från någon av följande källor:

- En kundtjänstassistent använder Commerce HQ-klienten för att bearbeta försäljningsorder.
- En kassör vid kassan bearbetar försäljningstransaktioner.
- Försäljning skapas i anpassade program med hjälp av fjärradministrerad Commerce (Commerce Scale Unit).
- En näthandlare bläddrar på din näthandelswebbplats.
- En näthandlare gör en beställning på din näthandelswebbplats.
- Data produceras av andra system, till exempel Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Steg 2: påfyllning och förbearbetning

Transaktionsdata går till Commerce HQ antingen direkt (vid order som fångas in direkt i Commerce HQ-klienten) eller via Commerce Scale Unit (när det gäller order som fångas i kassan, i näthandel eller i anpassade klienter som använder fjärradministrerad Commerce).

Funktionen Exportera till Data Lake används sedan för att kopiera transaktionsdata till din datasjö som rådata. I data den här mappen lagras rådata i mappen Register.

Data för webbaktiviteten för näthandel skickas direkt till datasjön. Data som producerats av andra system, t.ex. Dynamics 365 Connected Spaces skickas direkt till datasjön av dessa system.

#### <a name="step-3-transformation-and-aggregation"></a>Steg 3: omvandling och aggregering

När rådata finns i din datasjö, läser Commerce-analystjänsten den, transformerar den, aggregerar den och skriver den tillbaka till datasjön i form av logiska enheter (i mappen Enheter) och aggregerade mått (i mappen Ontologier).

#### <a name="step-4-querying"></a>Steg 4: Fråga

Azure Synapse Analytics används för att efterfråga data i din datasjö via ett Transact-SQL-gränssnitt (T-SQL). Det här gränssnittet omfattar SQL-vyer. SQL-vyer gör det möjligt att söka efter data i data via en T-SQL-klient (för ad hoc-analys) eller via ett visualiseringsverktyg som t.ex.Power BI.

#### <a name="step-5-modeling-and-serving"></a>Steg 5: Modellera och servera

Data som efterfrågas av Azure Synapse Analytics går till den semantiska Power BI-modellen. Beroende på vilken typ av data det är, kommer det antingen att importeras regelbundet i minnet Power BI eller direkt tillfrågas vid körning.

Informationen återges slutligen i visuella Power BI objekt, så att användarna kan visa och interagera med dem.

## <a name="commerce-analytics-preview-functional-overview"></a>Funktionell översikt över Commerce-analys (förhandsversion)

### <a name="summary"></a>Sammanfattning

Mallprogrammet Commerce-analys innehåller följande huvudrapportsidor:

1. [Filter på högsta nivå](#TopLevelFilters)
2. [Produkter](#ProductsPage)
3. [Kunder](#CustomersPage)
4. [Kanaler](#ChannelsPage)
5. [Försäljning](#SalesPage)
6. [Marginaler](#MarginsPage)
7. [Returer](#ReturnsPage)
8. [Rabatter](#DiscountsPage)
9. [Betalningar](#PaymentsPage)
10. [Kunder](#CustomersPage)
11. [Jämförelse](#ComparisonPage)
12. [Webbaktivitet](#WebActivityPage)
13. [Webbaktivitet – filter på toppnivå](#WebActivityTopLevelFilters)

#### <a name="top-level-filters"></a><a name="TopLevelFilters"></a>Filter på högsta nivå

- Datuminställningar

    - År
    - Kvartal
    - Månad
    - Vecka
    - Dag

- Kanalinställningar

    - Juridisk person
    - Kanaltyp
    - Kundtyp
    - Försäljningstyp
    - Kanal
    - Organisationshierarki

- Produktinställningar

    - Kategorihierarki
    - Kategori

#### <a name="products"></a><a name="ProductsPage"></a> Produkter

- Försäljning
- Marginal
- Returer

#### <a name="customers"></a><a name="CustomersPage"></a> Kunder

- Försäljning
- Marginal
- Returer

#### <a name="channels"></a><a name="ChannelsPage"></a> Kanaler

- Försäljning
- Marginal
- Returer

### <a name="sales"></a>Försäljning <a name="SalesPage"></a>

- Efter leveransplats
- Efter kanal/butik/terminal
- Per anställd
- Efter datum
- Efter timme
- Efter produktkategori

### <a name="margins"></a><a name="MarginsPage"></a> Marginaler

- Efter leveransplats
- Biprodukt
- Efter datum

### <a name="returns"></a><a name="ReturnsPage"></a> Returer

- Retur efter belopp

    - Per butik
    - Biprodukt
    - Efter datum

- Retur efter transaktion

    - Per butik
    - Biprodukt
    - Efter datum

### <a name="discounts"></a><a name="DiscountsPage"></a> Rabatter

- Per butik
- Biprodukt
- Efter datum
- Uppdelning

    - Juridisk person
    - Butik
    - Rabattyp
    - Rabattnamn
    - Produkt

### <a name="payments"></a><a name="PaymentsPage"></a> Betalningar

- Efter kanal/terminal
- Efter betalningsmetod/typ
- Efter datum
- Uppdelning

    - Juridisk person
    - Kanaltyp
    - Butik
    - Terminal
    - Betalningsmetod

### <a name="customers"></a><a name="CustomersPage"></a> Kunder

- Livstidsvärde (LTV)

    LTV beräknas baserat på det totala belopp som en kund lägger ut i alla Dynamics 365 Commerce försäljningskanaler (inklusive kassa, näthandel och kundtjänst).

- Recency

    Senaste beräknas baserat på antalet dagar sedan en kunds senaste transaktionella åtagande med organisationen. För närvarande tar senaste inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom näthandel.

- Frekvens

    Frekvens beräknas baserat på en kunds transaktionella åtagande med organisationen. För närvarande tar frekvens inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom näthandel.

- Relationslängd

    Relationslängden beräknas baserat på antalet dagar sedan kundposten skapades i systemet.

- Transaktionsantal

### <a name="comparison"></a><a name="ComparisonPage"></a> Jämförelse

- Produktjämförelse per tidsperiod

    - Försäljning och försäljningsdifferens
    - Marginal- och marginaldifferens

- Kund efter tidsperiod

    - Försäljning och försäljningsdifferens
    - Marginal- och marginaldifferens

### <a name="web-activity"></a><a name="WebActivityPage"></a> Webbaktivitet

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filter på högsta nivå

- Datumintervall
- Kanaltyp
- Kanal
- Kategorihierarki

#### <a name="acquisitions"></a>Anskaffningar

- Sidvyer

    - Efter land eller region
    - Biprodukt
    - Efter status för inloggad användare
    - Efter datum

- Order för näthandel
- Konverteringsgrad

    - Efter datum

- Konverteringstratt

    - Sidvy efter sidtyp (startsida, kategorisida eller produktinformationssida)
    - Lägg till i shoppingvagnen
    - Kassa
    - Inköp

#### <a name="sessions"></a>Sessioner

En session är ett avsnitt av en användares besök på din näthandelswebbplats. En session anses avslutad efter 30 minutes inaktivitet eller 24 timmars aktiv användning.

- Efter land eller region
- Efter ursprung (extern referensman)
- Efter status för inloggad användare
- Sessionsräkning

    - Efter datum
    - Efter inmatningssida

- Order per session

    - Efter datum

- Sessionens avhoppningsgrad

    En sessions avhoppning är en session som användaren lämnar omedelbart efter att han eller hon har besökt näthandelswebbplatsen. Mer information finns i [avhoppningsgrad](https://en.wikipedia.org/wiki/Bounce_rate).

- Klick per session

#### <a name="visitors"></a>Besökare

En anonym gäst på din näthandelswebbplats identifieras unikt baserat på den specifika webbläsare och specifika enhet som användaren använder. Commerce-analys spårar inte anonyma besökare i olika webbläsare eller enheter. En anonym besökare som använder samma webbläsare på samma enhet identifieras unikt för flera användarsessioner tills webbläsarens cachelagrade data rensas eller så passerar en period (vanligtvis 12 månader) vilket som inträffar först.

Om du är inloggad på din näthandelsplats kan Commerce-analys ge ytterligare information om dem. Denna information baseras på den befintliga relationen mellan din organisation och företaget till följd av deras tidigare inköp i alla försäljningskanaler Dynamics 365 Commerce (inklusive kassa, näthandel och kundtjänst). Den ytterligare informationen omfattar senaste, relationslängd, livstidsvärde och frekvensdata.

- Besöksmarginal
- Genomsnittsorder för besökare
- Genomsnittsförsäljning för besökare
- Antal näthandelsbesökare

    - Efter datum
    - Efter plats

        Commerce-analys kan för närvarande endast ge information om platser på land-/regionnivå för insikter i näthandelsbesökare.

    - Efter senaste

        Senaste beräknas baserat på antalet dagar sedan en kunds senaste transaktionella åtagande med organisationen. För närvarande tar senaste inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom näthandel.

    - Efter relationslängd

        Relationslängden beräknas baserat på antalet dagar sedan kundposten skapades i systemet.

    - Efter livstidsvärde (LTV)

        LTV beräknas baserat på det totala belopp som en kund lägger ut i alla Dynamics 365 Commerce försäljningskanaler (inklusive kassa, näthandel och kundtjänst).

    - Efter frekvens

        Frekvens beräknas baserat på en kunds transaktionella åtagande med organisationen. För närvarande tar frekvens inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom näthandel.

#### <a name="impressions"></a>Visningar

En visning är en enda vy av en visuell produkt av en näthandelsbesökare. Till exempel går en näthandelsbesökare till hemsidan för din näthandelswebbplats och tittar på en yogamatta i en listmodul för **bästsäljande**. Besökaren ser sedan samma yogamatta i listmodulen **Val för dig**. I det här fallet finns det två produktvisning.

För närvarande spåras dessa visningar under följande områden:

- Listor (till exempel **Rekommenderad**, **Bästsäljande**, **Val för dig** och **Populära**)
- Kundvagnsmodul
- Behållare för sökresultat
- Behållare för kategorisökningsresultat

För närvarande räknas produkter som återges i en modul eller i anpassade visuella värden inte i mätvärden som är visningsrelaterade.

Sidan **visningsrapport** omfattar följande mätvärden:

- Visningsräkning

    - Efter sidtyp och modul

        Sidtyp är den allmänna typ av sida som definieras för varje sida på din näthandelswebbplats. Modultyp är den typ av visuell modul för näthandel som produkten visas i.

        Om du vill visa information om moduler måste du kanske gå nedåt till visuella elementen på sidan och modulerna.

    - Biprodukt
    - Efter status för inloggad användare
    - Efter datum

- Visningsklickräkning

    En visningsklickning uppstår när en näthandelsbesökare väljer en visuell produkt. Vanligtvis tas denna information till produktinformationssidan för produkten.

- Genomklickningsfrekvens för visning (CTR)

    CTR beräknas som det totala antalet visningsklick dividerat med det totala antalet visningar.

## <a name="commerce-analytics-preview-installation"></a>Installation av Commerce-analyser (förhandsversion)

> [!NOTE]
> Commerce-analys (förhandsversion) är i förhandsversion i regioner i USA, Kanada, Storbritannien, Europa, Sydostasien, Östasien, Australien och Japan. Om din miljö för ekonomi och drift finns i någon av dessa regioner kan du aktivera denna funktion i din miljö med hjälp av Microsoft Dynamics Lifecycle Services (LCS). Innan du kan använda den här funktionen, se [Konfigurera export till Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Aktivera och konfigurera Commerce-analys (förhandsversion)

Om du vill installera Commerce-analys (förhandsversion) måste du ha behörighet att skapa resurser i ett Azure-abonnemang. Du måste också ha behörighet att installera tillägg i LCS. 

Följ dessa steg för att aktivera och konfigurera tillägget för Commerce-analys (förhandsversion).

1. [Aktivera och konfigurera tillägget Exportera till Data Lake](#enableExportToDataLake).
1. [Installera och konfigurera en Azure Synapse Workspace](#configureAzureSynapse).
1. [Lägg till hemligheter i nyckelvalvet](#addSecrets).
1. [Aktivera och konfigurera tillägget Commerce-analys (förhandsversion)](#enableCommerceAnalyticsAddin).
1. [Installera Power BI mallappen](#powerbi).

### <a name="enable-and-configure-the-export-to-data-lake-add-in"></a><a name="enableExportToDataLake"></a>Aktivera och konfigurera tillägget Exportera till Data Lake

> [!IMPORTANT]
> När du konfigurerar tillägget Exportera till Data Lake avmarkerar du kryssrutan **Ändringar av realtidsdata** på inställningssidan för Exportera till Data Lake för att se till att ändringar av realtidsdata inte aktiveras. Funktionen **Dataändringar i realtid** befinner sig i förhandsgranskningsversion och stöds för närvarande inte av Commerce Analytics. Om du aktiverar funktionen kommer Commerce Analytics inte att kunna bearbeta dina data i datasjön, och de flesta Power BI-rapporter kommer inte att uppvisa några data.

Commerce-analys (förhandsversion) använder sig av funktionen Exportera till Data Lake för att exportera Commerce-administrationsdata till Data Lake och hålla datan aktuell. Innan du konfigurerar Commerce-analys (förhandsversion), aktivera och konfigurera Exportera till Data Lake genom att följa stegen i [konfigurera export till Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

När du konfigurerar tillägget Exportera till Data Lake, se till att notera följande information eftersom du måste registrera den senare:

- <a name="keyVault"></a>DNS-namnet på det nyckelvalv du tillhandahållit.
- De hemliga namn som du tillhandahållit och som innehåller program-ID och programhemlighet. Mer information om mått finns i [Lägg till hemligheter till nyckelvalvet](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Installera och konfigurera en Azure Synapse Workspace.

Commerce Analytics (förhandsversion) kräver att Synapse SQL on-demand används i Azure Synapse Workspace. Följ de här stegen om du vill installera och konfigurera en Azure Synapse Workspace.

1. Installera en Azure Synapse Workspace i ditt Azure-abonnemang. Mer information finns i [Snabbstart: Skapa en Synapse-arbetsyta](/azure/synapse-analytics/quickstart-create-workspace).
1. <a name="serverlessep"></a>När arbetsytan tillhandahålles öppnar du resursöversiktssidan och noterar värdet för **Serverlös SQL-slutpunkt**. Du måste lagra detta värde i nyckelvalvet i nästa avsnitt.
1. På översiktssidan väljer du länken **Öppna Synapse Studio** för att öppna Azure Synapse Studio för din arbetsyta.
1. Välj **Hantera** i menyn till vänster. Om du vill visa menynamnen måste du eventuellt välja den expanderade länken i den vänstra menyn.
1. Under **Säkerhetsgrupp** väljer du **Åtkomstkontroll**. 
1. Markera **Lägg till**.
1. I fönstret **Lägg till rolltilldelning** ställer du in alternativen enligt beskrivet i följande tabell.

    | Alternativ | Värde |
    |--------|-------|
    | Omfattning | Välj **Arbetsyta**. |
    | Roll | Välj **Synapse SQL-administratör**.|
    | Välj användare | Sök efter namnet på det program som du [skapade under installationen av tillägget Exportera till Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createapplication). När programmet visas i sökresultatet väljer du det. Programmet visas nu i avsnittet **Markerad(e) användare, grupp(er) eller huvudnamn för tjänster**. |

1. Välj **Verkställ** för att slutföra rolltilldelningen. Programmet beviljas behörigheten Synapse SQL-administratör. Därför kan det skapa nödvändiga vyer under konfigurationen av tillägget Commerce Analytics (Preview) LCS.

### <a name="add-secrets-to-the-key-vault"></a><a name="addSecrets"></a>Lägg till hemligheter i nyckelvalvet

I samma [nyckelvalv](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createkeyvault) som du använde när du konfigurerade tillägget Exportera till Data Lake måste du lägga till de hemligheter som anges i följande tabell. För varje hemlighet måste du ange ett hemligt namn och ett angivet värde.

| Föreslaget hemligt namn | Hemligt värde | Exempel på hemligt värde |
|---------|---------|---------|
| synapse-sql-server | Det serverlösa SQL-slutpunktsvärde som du noterade när du [konfigurerade Azure Synapse Workspace](#serverlessep). | `test-ondemand.sql.azuresynapse.net` |
| <a name="roUser"></a>readonly-sql-pwd | Lösenordet som ska anges för SQL-skrivskyddade användare. Power BI-rapporten använder detta lösenord för att ansluta till serverlösa SQL. Du anger lösenordet genom att följa organisationens lösenordspolicy. | |

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Aktivera och konfigurera tillägget Commerce-analys (förhandsversion).

Om du vill installera tillägget Commerce-analys (förhandsversion) i LCS måste du vara miljöadministratör i LCS för den miljö som du planerar att använda.

Följ dessa steg för att installera och konfigurera tillägget Commerce-analys (förhandsversion).

1. Logga in på [LCS](https://lcs.dynamics.com/) och gå till miljön.
2. På sidan **Miljö** på fliken **Miljötillägg**, välj **Installera ett nytt tillägg**.
3. I dialogrutan, välj **Commerce-analys (förhandsversion)**.
4. Ange följande information i dialogrutan **Konfigurera tillägg**.

    | Information | Källa | Exempelvärde |
    |---|---|---|
    | Klientorganisations-ID för Azure Active Directory (Azure AD) | Logga in på [Azure-portal](https://portal.azure.com/) och öppna **Azure Active Directory**-tjänsten. Öppna sedan sidan **Egenskaper** och kopiera värdet i fältet **Klientorganisations-ID**. | `72f988bf-0000-0000-00000-2d7cd011db47` |
    | DNS-namnet på ditt Azure-nyckelvalv | Ange DNS-namnet på ditt nyckelvalv. Du bör ha observerat det här värdet medan du [konfigurerade tillägget Exportera till Data Lake](#keyVault). | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Hemligt namn som innehåller program-ID:t | Ange namn hemligt namn som lagrar program-ID:t. Du bör ha observerat det här värdet medan du [konfigurerade tillägget Exportera till Data Lake](#keyVault). | `app-id` |
    | Hemligt namn innehåller programhemlighet | Ange namn hemligt namn som lagrar program-hemlighet. Du bör ha observerat det här värdet medan du [konfigurerade tillägget Exportera till Data Lake](#keyVault). | `app-secret` |
    | Hemligt namn som innehåller den serverlösa SQL-slutpunkten för Azure Synapse | Ange det hemliga namn som lagrar serverlös SQL-slutpunkt. Du bör ha skapat hemligheten när du [lade till henligheter i nyckelvärdet](#addSecrets). | `synapse-sql-server` |
    | Hemligt namn som innehåller lösenordet som ska anges för skrivskyddade SQL-användare i Azure Synapse | Ange det hemliga namn som lagrar lösenordet som ska anges för serverlös skrivskyddad SQL-användare. Denna användare skapas åt dig och bör användas i Power BI-rapporten för att ansluta till den serverlösa SQL-servern. Du bör ha skapat hemligheten när du [lade till hemligheter i nyckelvärdet](#addSecrets). | `readonly-sql-pwd` |

1. Acceptera villkoren för erbjudandet genom att markera kryssrutan och sedan välja **Installera**.

    Systemet installerar och konfigurerar tillägget Commerce-analys (förhandsversion) för miljön. Den här processen kan ta några minuter. När den är klar visas **Commerce-analys (förhandsversion)** på sidan **Miljö** och statusvärdet bör vara **Installerat**.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Installera Power BI mallappen

För att installera Power BI mallappen för Commerce-analys (förhandsversion), följ stegen nedan.

1. Logga in på [Power BI portalen](https://powerbi.microsoft.com/) med ditt organisations-ID.
1. Installera mallappen för Commerce-analys (förhandsversion) Power BI genom att gå till [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Du kan också gå till [AppSource-sidan för Dynamics 365 Commerce-analys](https://appsource.microsoft.com/product/power-bi/dynamics-365-commerce.dydnamics-365-commerce-analytics) och välja **Hämta nu**.
1. Om du installerar om programmet för första gången går du vidare till steg 5. Om du har installerat detta tidigare gäller följande alternativ för uppdatering av programmet:

    - **Uppdatera arbetsytan och programmet** – Uppdatera den befintliga mallappen och skriv över dina befintliga appinställningar, som appinstansens namn och behörighetskonfigurationer.
    - **Uppdatera endast innehållet i arbetsytan utan att uppdatera programmet** – Uppdatera det befintliga mallprogrammet, men behåll de befintliga appinställningarna. *Det här alternativet är det rekommenderade alternativet för appuppdateringar.*
    - **Installera en annan kopia av programmet i en ny arbetsyta** – Skapa en ny arbetsyta och skapa sedan en kopia av det befintliga mallprogrammet i det. Den befintliga arbetsytan lämnas intakt.

1. Välj ett av uppdateringsalternativen och välj sedan **Installera**.
1. Öppna det installerade programmet genom att välja **Appar** i det vänstra fönstret och sedan välja programmet.
1. Anslut programmet till din datakälla genom att välja **Anslut**. Om du har installerat programmet tidigare väljer du länken **Anslut dina data** i det gula meddelandefältet.
1. Ange följande fält.

    | Fält | Värde |
    |---|---|
    | Server | Ange den serverlösa SQL-slutpunkt som du gjorde en anteckning om när du [skapade Azure Synapse Workspace](#serverlessep). |
    | Databas | Ange **CommerceAnalytics**. |
    | Språk | Välj ett värde i listan. Detta fält används för lokaliserade produkt- och kategorinamn. Värdet är skiftlägeskänsligt. |
    | Datumintervall | Välj ett värde i listan. Data för valt antal månader kommer att importeras till Power BI datauppsättningen. Värdet du väljer påverkar storleken på datauppsättningen och den tid som krävs för synkronisering. |

1. Välj **Nästa**. När du uppmanas att ange autentiseringsuppgifterna för att ansluta till Azure Synapse SQL-databasen ska du ställa in fältvärdena så som visas i följande tabell.

    | Fält | Värde |
    |---|---|
    | Autentiseringsmetod | Välj **Grundläggande**. |
    | Användarnamn | Ange **reportreadonlyuser**. |
    | Lösenord | Ange lösenordet som du [lagrade för den skrivskyddade SQL-användaren i nyckelvalvet](#roUser). |

1. Välj **logga in och anslut**.
1. Vänta tills datauppsättningen har uppdaterats. Välj sedan knappen **Redigera app** för att öppna programarbetsytan, där du kan visa uppdateringsstatusen för datauppsättningen. I app-arbetsytan kan du även ställa in automatiska uppdateringsscheman för din datauppsättning, hantera behörigheter och byta namn på appinstansen.

### <a name="privacy"></a><a name="privacy"></a>Tillgänglighet

Din sekretess är viktig för oss. Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
