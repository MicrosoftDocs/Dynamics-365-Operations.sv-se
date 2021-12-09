---
title: Commerce-analyser (förhandsversion)
description: Det här avsnittet innehåller information om hur du installerar och använder analysfunktionerna i Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862783"
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
- SQL-vyer i Azure Synapse analys
- Enhetsdata och ontologi-data i Azure Data Lake
- Rådata i Data Lake

![Nyckelkomponenter i systemarkitekturen för Commerce-analys](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Dataflöde

#### <a name="step-1-data-generation"></a>Steg 1: Datagenerering

Data har antingen sitt ursprung i transaktionsdata eller som beteendedata från någon av följande källor:

- En kundtjänstassistent använder Commerce HQ-klienten för att bearbeta försäljningsorder.
- En kassör vid kassan bearbetar försäljningstransaktioner.
- Försäljning skapas i anpassade program med hjälp av fjärradministrerad Commerce (Commerce Scale Unit).
- En e-handlare bläddrar på din näthandelswebbplats.
- En e-handlare gör en beställning på din näthandelswebbplats.
- Data produceras av andra system, till exempel Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Steg 2: påfyllning och förbearbetning

Transaktionsdata går till Commerce HQ antingen direkt (vid order som fångas in direkt i Commerce HQ-klienten) eller via Commerce Scale Unit (när det gäller order som fångas i kassan, i e-handel eller i anpassade klienter som använder fjärradministrerad Commerce).

Funktionen Exportera till Data Lake används sedan för att kopiera transaktionsdata till din datasjö som rådata. I data den här mappen lagras rådata i mappen Register.

Data för webbaktiviteten för e-handel skickas direkt till datasjön. Data som producerats av andra system, t.ex. Dynamics 365 Connected Spaces skickas direkt till datasjön av dessa system.

#### <a name="step-3-transformation-and-aggregation"></a>Steg 3: omvandling och aggregering

När rådata finns i din datasjö, läser Commerce-analystjänsten den, transformerar den, aggregerar den och skriver den tillbaka till datasjön i form av logiska enheter (i mappen Enheter) och aggregerade mått (i mappen Ontologier).

#### <a name="step-4-querying"></a>Steg 4: Fråga

Azure Synapse analys används för att fråga efter data i din datasjö via ett Transact-SQL-gränssnitt (T-SQL). Det här gränssnittet omfattar SQL-vyer. SQL-vyer gör det möjligt att söka efter data i data via en T-SQL-klient (för ad hoc-analys) eller via ett visualiseringsverktyg som t.ex.Power BI.

#### <a name="step-5-modeling-and-serving"></a>Steg 5: Modellera och servera

Data som söks i Azure Synapse analys går till Power BI semantiska modell. Beroende på vilken typ av data det är, kommer det antingen att importeras regelbundet i minnet Power BI eller direkt tillfrågas vid körning.

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

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a>Filter på högsta nivå

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

####  <a name="products"></a><a name="ProductsPage"></a> Produkter

- Försäljning
- Marginal
- Returer

####  <a name="customers"></a><a name="CustomersPage"></a> Kunder

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

    LTV beräknas baserat på det totala belopp som en kund lägger ut i alla Dynamics 365 Commerce försäljningskanaler (inklusive kassa, e-handel och kundtjänst).

- Recency

    Senaste beräknas baserat på antalet dagar sedan en kunds senaste transaktionella åtagande med organisationen. För närvarande tar senaste inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom e-handel.

- Frekvens

    Frekvens beräknas baserat på en kunds transaktionella åtagande med organisationen. För närvarande tar frekvens inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom e-handel.

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

En session är ett avsnitt av en användares besök på din e-handelswebbplats. En session anses avslutad efter 30 minutes inaktivitet eller 24 timmars aktiv användning.

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

Om du är inloggad på din näthandelsplats kan Commerce-analys ge ytterligare information om dem. Denna information baseras på den befintliga relationen mellan din organisation och företaget till följd av deras tidigare inköp i alla försäljningskanaler Dynamics 365 Commerce (inklusive kassa, e-handel och kundtjänst). Den ytterligare informationen omfattar senaste, relationslängd, livstidsvärde och frekvensdata.

- Besöksmarginal
- Genomsnittsorder för besökare
- Genomsnittsförsäljning för besökare
- Antal e-handelsbesökare

    - Efter datum
    - Efter plats

        Commerce-analys kan för närvarande endast ge information om platser på land-/regionnivå för insikter i e-handelsbesökare.

    - Efter senaste

        Senaste beräknas baserat på antalet dagar sedan en kunds senaste transaktionella åtagande med organisationen. För närvarande tar senaste inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom e-handel.

    - Efter relationslängd

        Relationslängden beräknas baserat på antalet dagar sedan kundposten skapades i systemet.

    - Efter livstidsvärde (LTV)

        LTV beräknas baserat på det totala belopp som en kund lägger ut i alla Dynamics 365 Commerce försäljningskanaler (inklusive kassa, e-handel och kundtjänst).

    - Efter frekvens

        Frekvens beräknas baserat på en kunds transaktionella åtagande med organisationen. För närvarande tar frekvens inte hänsyn till icke-transaktionella signaler, till exempel webbaktivitet inom e-handel.

#### <a name="impressions"></a>Visningar

En visning är en enda vy av en visuell produkt av en e-handelsbesökare. Till exempel går en e-handelsbesökare till hemsidan för din näthandelswebbplats och tittar på en yogamatta i en listmodul för **bästsäljande**. Besökaren ser sedan samma yogamatta i listmodulen **Val för dig**. I det här fallet finns det två produktvisning. 

För närvarande spåras dessa visningar under följande områden:

- Listor (till exempel **Rekommenderad**, **Bästsäljande**, **Val för dig** och **Populära**)
- Kundvagnsmodul
- Behållare för sökresultat
- Behållare för kategorisökningsresultat

För närvarande räknas produkter som återges i en modul eller i anpassade visuella värden inte i mätvärden som är visningsrelaterade.

Sidan **visningsrapport** omfattar följande mätvärden:

- Visningsräkning

    - Efter sidtyp och modul

        Sidtyp är den allmänna typ av sida som definieras för varje sida på din näthandelswebbplats. Modultyp är den typ av visuell modul för e-handel som produkten visas i.

        Om du vill visa information om moduler måste du kanske gå nedåt till visuella elementen på sidan och modulerna.

    - Biprodukt
    - Efter status för inloggad användare
    - Efter datum

- Visningsklickräkning

    En visningsklickning uppstår när en e-handelsbesökare väljer en visuell produkt. Vanligtvis tas denna information till produktinformationssidan för produkten.

- Genomklickningsfrekvens för visning (CTR)

    CTR beräknas som det totala antalet visningsklick dividerat med det totala antalet visningar.

## <a name="commerce-analytics-preview-installation"></a>Installation av Commerce-analyser (förhandsversion)

> [!NOTE]
> Commerce-analys (förhandsversion) är i förhandsversion i regioner i USA, Kanada, Storbritannien, Europa, Sydostasien, Östasien, Australien och Japan. Om din Finance and Operations miljö finns i någon av dessa regioner kan du aktivera den funktionen i din miljö med Microsoft Dynamics Lifecycle Services (LCS). Innan du kan använda den här funktionen, se [Konfigurera export till Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Aktivera och konfigurera Commerce-analys (förhandsversion)

Om du vill installera Commerce-analys (förhandsversion) måste du ha behörighet att skapa resurser i ett Azure-abonnemang. Du måste också ha behörighet att installera tillägg i LCS. Här finns en översikt av stegen.

1. [Skicka in förhandsgranskningsformuläret för Commerce-analys (förhandsversion)](#joinPreview).
2. [Aktivera och konfigurera export till Data Lake](#enableExportToDataLake).
3. [Aktivera och konfigurera tillägget Commerce-analys (förhandsversion)](#enableCommerceAnalyticsAddin).
4. [Generera en signatur för delad åtkomst (SAS) för ditt lagringskonto](#getSASToken).
5. [Hämta distribueringsskripten för Azure Synapse vyer](#downloadSynapseDeploymentScripts).
6. [Installera och konfigurera en Azure Synapse workspace](#configureAzureSynapse).
7. [Installera Power BI mallappen](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Skicka in förhandsgranskningsformuläret för Commerce-analys (förhandsversion).

Skicka in [förhandsgranskningsformuläret för Commerce-analys (förhandsversion)](https://forms.office.com/r/vW5VLJGXZ2). Upp till tre affärsdagar för att formuläret ska kunna bearbetas. När det har bearbetats skickas ett bekräftelsemeddelande via e-post till den e-postadress som du angett i formuläret.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>Aktivera och konfigurera export till Data Lake.

Commerce-analys (förhandsversion) använder sig av funktionen Exportera till Data Lake för att exportera Commerce HQ-data till Data Lake och se till att data är aktuell. Innan du konfigurerar Commerce-analys (förhandsversion), aktivera och konfigurera Exportera till Data Lake genom att följa stegen i [konfigurera export till Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

När du konfigurerar Exportera till Data Lake, noterar du följande information, eftersom du måste registrera den senare:

- <a name="keyVault"></a>DNS-namnet (Domain Name System) namnet på nyckelvalvet och de hemliga namnen där du lagrar app-ID och apphemlighet. Mer information om mått finns i [Lägg till hemligheter till nyckelvalvet](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>Namnet på lagringskontot för Data Lake-instansen. För mer information, se [Skapa ett konto för Data Lake Storage (Gen2) i abonnemanget](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Aktivera och konfigurera tillägget Commerce-analys (förhandsversion).

Om du vill installera tillägget Commerce-analys (förhandsversion) i LCS måste du vara miljöadministratör i LCS för den miljö som du planerar att använda.

Följ dessa steg för att installera och konfigurera tillägget Commerce-analys (förhandsversion).

1. Logga in på [LCS](https://lcs.dynamics.com/) och gå till miljön.
2. På sidan **Miljö** på fliken **Miljötillägg**, välj **Installera ett nytt tillägg**.
3. I dialogrutan, välj **Commerce-analys (förhandsversion)**.

    Om **Commerce-analys (förhandsversion)** inte finns med i listan, se till att du har gått med i Insider Program. 

4. Ange följande information i dialogrutan **Konfigurera tillägg**.

    | Information | Källa | Exempelvärde |
    |---|---|---|
    | Azure AD Innehavar-ID för din miljö | Logga in på [Azure-portal](https://portal.azure.com/) och öppna **Azure Active Directory**-tjänsten. Öppna sedan sidan **Egenskaper** och kopiera värdet i fältet **Katalog-ID**.  | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | DNS-namnet på ditt nyckelvalv | Ange [DNS-namnet](#keyVault) på ditt nyckelvalv. Du bör ha observerat det här värdet i föregående avsnitt. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Hemlighet som innehåller program-ID:t | Ange namn [hemligt namn som lagrar program-ID:t](#keyVault). Du bör ha observerat det här värdet i föregående avsnitt. | program-ID |
    | Hemlighet innehåller program-hemlighet | Ange namn [hemligt namn som lagrar program-hemlighet](#keyVault). Du bör ha observerat det här värdet i föregående avsnitt. | programhemlighet |

5. Acceptera villkoren för erbjudandet genom att markera kryssrutan och sedan välja **Installera**.

    Systemet installerar och konfigurerar tillägget Commerce-analys (förhandsversion) för miljön. Den här processen kan ta några minuter. När den är klar visas **Commerce-analys (förhandsversion)** på sidan **Miljö** och statusvärdet bör vara **Installerat**.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>Generera en SAS-token för ditt lagringskonto

Med en SAS-token kan externa enheter komma åt ditt lagringskonto och ha specifika behörigheter för en begränsad tid. Azure Synapse använder SAS-token för åtkomst till underliggande data i Data Lake.

> [!NOTE]
> På grund av en känd begränsning av Commerce-analys (förhandsversion) förlorar Azure Synapse-instansen åtkomsten till datasjön den när SAS-token upphör att gälla. När du genererar en SAS-token bör du därför ange det maximala utgångsdatum som tillåts av organisationens säkerhetspolicy.

Gör på följande sätt om du vill generera SAS-token.

1. I Azure-portalen, gå till det [lagringskonto](#storageAccount) du skapade när du konfigurerade Exportera till Data Lake.
2. I den vänstra rutan, under lagringskontot, välj **Delad åtkomstsignatur**.
3. På sidan **SAS-alternativ** anger du följande fält.

    | Fält | Värde |
    |---|---|
    | Tillåtna tjänster | Välj **Blobb**. |
    | Tillåtna resurstyper | Välj **tjänst**, **behållare** och **objekt**. |
    | Tillåtna behörigheter | Välj **Läs**, **Skriv**, **Radera**, **Lista**, **Lägg till** och **Skapa**. |
    | Behörigheter för blobb-versionering | Välj **Aktivera borttagning av versioner**. |
    | Start- och utgångsdatum/tid | Ange start- och slutdatum samt start- och sluttid för SAS-token efter behov. |
    | Tillåtna IP-adresser | Lämna det här fältet tomt. |
    | Tillåtna protokoll | Välj **Endast HTTPS**. |
    | Prioriterad flödesnivå | Välj **Grundläggande (standard)**. |
    | Signeringsnyckel | Välj **nyckel1** eller **nyckel2**, enligt behov. |

4. Välj **Generera SAS och anslutningssträng**.
5. Kopiera värdet i **SAS-token** och klistra in det i en textredigerare som Anteckningar.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>Hämta distribueringsskripten för Azure Synapse vyer

Om du vill skapa och publicera nödvändiga vyer i en Azure Synapse workspace måste du köra en uppsättning skript. Följ dessa steg för att ladda ner skripten.

1. I GitHub, gå till [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) databas.
2. Ladda ner skripten till din lokala dator genom att klona lagringsplats eller ladda ner det som en zip-fil.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Installera och konfigurera en Azure Synapse workspace.

Följ de här stegen om du vill installera och konfigurera en Azure Synapse workspace.

1. Installera en Azure Synapse workspace i ditt Azure-abonnemang. Mer information finns i [Snabbstart: Skapa en Synapse-arbetsyta](/azure/synapse-analytics/quickstart-create-workspace).
2. I Anteckningar eller någon annan textredigerare öppnar du skriptfilen **SetupSynapse.sql** från mappen på din lokala dator som du klonade eller laddade ner Dynamics365Commerce.Solutions lagringsplatsen till i föregående avsnitt. Skriptfilen visas under mappen /Pipeline/CommerceAnalysynapse/. Ersätt platshållartexten i skriptet med värden som visas i följande tabell.

    | Platshållartext | Ersättningsvärde |
    |---|---|
    | placeholder_storageaccount | Namnet på [lagringskonto](#storageAccount) du skapade när du konfigurerade Exportera till Data Lake. |
    | <a name="phContainer"></a>placeholder_container | Namnet på lagringsbehållaren som skapades i din Data Lake-instans efter att du lyckades installera tillägget Exportera till Data Lake i LCS. Om du vill hämta behållarnamnet måste du använda Storage Explorer i Azure-portalen för att bläddra i ditt lagringskonto. |
    | placeholder_sastoken | Det [SAS-token](#getSASToken) som du genererade. Se till att ta bort frågetecken (**?**) från början av SAS-tokenvärdet. |
    | <a name="phUserPwd"></a>placeholder_password | Ett lösenord som du väljer starkt. Gör en notering av detta lösenord. Det kommer att anges som lösenord för det nya konto i **reportreadonlyuser** som skriptet skapar. Ange **inte** lösenordet för kontot **sqladminuser**. |

3. Kopiera det uppdaterade innehållet i skriptfilen.
4. I Azure-portalen, gå till den nya Azure Synapse workspace. På sidan **Översikt**, välj **Öppna Synapse Studio**.
5. I Synapse Studio, välj **Ny \> SQL script** och klistra in innehållet i skriptfilen i SQL-skriptredigeraren.
6. Kontrollera att fältet **Använd databas** är inställt på **huvud**.
7. Välj **Kör** och vänta tills skriptet har körts. Lyckad körning av skriptet skapar databasen för handelsanalys, autentiseringsuppgifter för åtkomst till datasjön och ett skrivskyddat användarkonto som Power BI används för att ansluta till Azure Synapse-instansen.
8. Öppna Windows PowerShell i administratörsläge på din lokala dator och gå till mappen /Pipeline/CommerceAnalycommerceSynapse/ under den mapp som du har öppnat eller hämtat Dynamics365Commerce.Solutions lagringsplats till.
9. Ställ in körningspolicyn för Windows PowerShell genom att köra följande kommando.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Om modulen SQL Server PowerShell inte redan är installerad, ska du installera den genom att köra följande kommando.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > Under installationen av modulen kan du tillfrågas om att installera NuGet providern. I det här fallet väljer du **Y** för installation av NuGet provider. Du kanske också uppmanas att bekräfta att du installerar om moduler från en ej betrodd lagringsplats. I det här fallet väljer du **Y** för att fortsätta med installationen. Du kan också köra cmdleten **Set-PSRepository** för att förtroende för **PSGallery**-databasen. 

11. Publicera Azure Synapse vyerna genom att köra följande kommando.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    När du kör det här kommandot, byt ut platshållarvärdena som visas i följande tabell.

    | Platshållarens värde | Ersättningsvärde |
    |---|---|
    | SERVER_NAME | Namnet på Azure Synapse serverlös SQL-slutpunkt. Du får det här värdet från sidan **översikt** för Azure Synapse workspace i Azure-portal. |
    | PASSWORD | Lösenordet för kontot **sqladminuser**. |
    | STORAGE_ACCOUNT | Namnet på lagringskontot för Data Lake. |
    | CONTAINER_NAME | Namnet på behållaren som skapades av funktionen Exportera till Data Lake. Den här behållaren är samma behållare som du angav som värde för [placeholder_container](#phContainer) i steg 2. |
    | DATA_ROOT_PATH | Mappnamnet under behållaren som innehåller alla data. |

    > [!NOTE]
    > Du kan hitta namnet på lagringskontot, behållarnamnet och datarotsökvägen genom att använda Azure Storage-webbläsare och Data Lake Storage-kontot i Azure-portal.

12. Vänta tills skriptet körs. En lyckad körning av skriptet skapar SQL-vyer i den Azure Synapse serverlösa SQL-instansen.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Installera Power BI mallappen

För att installera Power BI mallappen för Commerce-analys (förhandsversion), följ stegen nedan.

1. Logga in på [Power BI portalen](https://powerbi.microsoft.com/) med ditt organisations-ID.
2. Installera mallappen för Commerce-analys (förhandsversion) Power BI genom att gå till [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Du kanske får en varning om att programmet inte finns med i AppSource-listan. Välj **Installera**.
3. Om du installerar om programmet för första gången går du vidare till steg 5. Om du har installerat det här programmet tidigare visas följande alternativ för uppdatering av programmet:

    - **Uppdatera arbetsytan och programmet** – Uppdatera den befintliga mallappen och skriv över dina befintliga appinställningar, som appinstansens namn och behörighetskonfigurationer.
    - **Uppdatera endast innehållet i arbetsytan utan att uppdatera programmet** – Uppdatera det befintliga mallprogrammet, men behåll de befintliga appinställningarna. *Det här alternativet är det rekommenderade alternativet för appuppdateringar.*
    - **Installera en annan kopia av programmet i en ny arbetsyta** – Skapa en ny arbetsyta och skapa sedan en kopia av det befintliga mallprogrammet i det. Den befintliga arbetsytan lämnas intakt.

4. Välj ett av uppdateringsalternativen och välj sedan **Installera**.
5. Öppna det installerade programmet genom att välja **Appar** i det vänstra fönstret och sedan välja programmet.
6. Anslut programmet till din datakälla genom att välja **Anslut**. Om du har installerat programmet tidigare väljer du länken **Anslut dina data** i det gula meddelandefältet.
7. Ange följande fält.

    | Fält | Värde |
    |---|---|
    | Server | Ange namnet på den Azure Synapse serverlösa SQL-slutpunkt som du skapade i det föregående avsnittet. Du får det här värdet från sidan **översikt** för Azure Synapse workspace i Azure-portal. |
    | Databas | Ange **CommerceAnalytics**. |
    | Språk | Välj ett värde i listan. Detta fält används för lokaliserade produkt- och kategorinamn. Värdet är skiftlägeskänsligt. |
    | Datumintervall | Välj ett värde i listan. Data för valt antal månader kommer att importeras till Power BI datauppsättningen. Värdet du väljer påverkar storleken på datauppsättningen och den tid som krävs för synkronisering. |

8. Välj **Nästa**. Du uppmanas ange autentiseringsuppgifterna för att ansluta till Azure Synapse SQL-databasen. Ställ in fälten enligt beskrivningen i följande tabell.

    | Fält | Värde |
    |---|---|
    | Autentiseringsmetod | Välj **Grundläggande**. |
    | Användarnamn | Ange **reportreadonlyuser**. |
    | Lösenord | Ange värdet som du bytte ut [placeholder_password](#phUserPwd) platshållaren i skriptet SetupSynapse.sql. Lösenordet är lösenordet för kontot **reportreadonlyuser**. |

9. Välj **logga in och anslut**.
10. Vänta tills datauppsättningen har uppdaterats. Markera sedan knappen **Redigera app** för att öppna app-arbetsytan, där du kan visa uppdateringsstatus för datauppsättningen. I app-arbetsytan kan du även ställa in automatiska uppdateringsscheman för din datauppsättning, hantera behörigheter och byta namn på appinstansen.

### <a name="privacy"></a><a name="privacy"></a>Tillgänglighet

Din sekretess är viktig för oss. Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
