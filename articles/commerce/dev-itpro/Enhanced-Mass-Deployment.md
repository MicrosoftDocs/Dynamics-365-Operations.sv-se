---
title: Massdistribution av stängda Commerce-självbetjäningskomponenter
description: Denna artikel beskriver hur du använder ramverket för installationsprogram för självbetjäning för tyst installation och tjänstedistributioner.
author: jashanno
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: 66a711aff90221e594f4b2a0df3735eac93d0c9b
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387030"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Massdistribution av stängda Commerce-självbetjäningskomponenter

[!include [banner](../includes/banner.md)]

Denna artikel gäller komponentinstallationsprogram med stängt ramverk som frisläpps varje månad, med början med version 10.0.18, och som är tillgängliga i det delade tillgångsbiblioteket i Microsoft Dynamics Lifecycle Services (LCS). Observera att de flera av de första versionerna av dessa nya installationsprogram betecknas som **(Förhandsversion)**. Det enda syftet med denna beteckning är att skilja mellan de nya installationsprogrammen medan Microsoft fastställer om det finns ytterligare funktionella krav för att använda dem. Det betyder inte att installationsprogrammet inte är giltigt för produktion. Baserat på frisläppning av dessa nya installationsprogram planerar Microsoft att fasa ut de gamla (äldre) installationsprogrammen i eller runt oktober 2023. 

Denna artikel beskriver hur du använder de nya installationsprogrammen för att utföra tysta installations- och serviceuppdateringar via kommandoradsargument. Med dessa argument kan du använda massdistribution på flera olika sätt.

> [!NOTE]
> De nya stängda installationsprogrammen med självservicen kommer inte att göras tillgängliga i headquarters och kan bara laddas ned via LCS.

## <a name="delimiters-for-mass-deployment"></a>Avgränsare för massdistribution

I följande tabell visas avgränsarna som kan användas vid kommandoradskörningen.


| Avgränsare                 | Beskrivning |
|---------------------------|-------------|
| -AadTokenIssuerPrefix | Prefixet för Microsoft Azure Active Directory (Azure AD) tokenutfärdare. |
| -AsyncClientAadClientId | Det Azure AD klient-ID som Async Client ska använda under kommunikationen med headquarters. |
| -AsyncClientAppInsightsInstrumentationKey | Instrumentationsnyckel för Async Client AppInsights. |
| -AsyncClientCertFullPath | Den helt formaterade URN-sökvägen som använder tumavtryck som sökmått för Async Client-identitetscertifikatsplatsen som ska användas för autentisera med Azure AD vid kommunikation med headquarters. Till exempel är `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` en korrekt formaterad URN. Värdet **\<MyThumbprint\>** ersätts med det certifikattumavtryck som ska användas. Använd inte den här parametern tillsammans med parametern **-AsyncClientCertThumbprint**. |
| -AsyncClientCertThumbprint | Tumavtrycket för Async Client-identitetscertifikatet som ska användas för att autentisera med Azure AD för kommunikation med headquarters. Det här tumavtrycket används för att söka efter plats och namn för **LocalMachine/Min lagringsplats** för att hitta rätt certifikat att använda. Använd inte den här parametern tillsammans med parametern **-AsyncClientCertFullPath**. |
| -ClientAppInsightsInstrumentationKey | Klientens AppInsights-instrumentationsnyckel. |
| -CloudPosAppInsightsInstrumentationKey | Cloud POS AppInsights-instrumentationsnyckel. |
| -Config | Konfigurationsfilen som ska användas under installationen. Ett exempel på ett filnamn är **Contoso.CommerceScaleUnit.xml**. |
| -CposAadClientId | Det Azure AD-klient-ID som Cloud Pos ska använda under enhetsaktivering. Den här parametern behövs inte för lokal distribution. |
| -Device | Enhets-ID som visas på sidan **Enheter** i headquarters. |
| -EnvironmentId | Miljö-ID. |
| -HardwareStationAppInsightsInstrumentationKey | Maskinvarustationens AppInsights-instrumentationsnyckel. |
| Installera | En parameter som anger om den komponent som det här installationsprogrammet tillhandahåller ska installeras. Den här parametern behövs för att en installation ska kunna utföras och den har inte något inledande bindestrecktecken. |
| -InstallOffline | För Modern POS anger den här parametern att offlinedatabasen också ska vara installerad och konfigurerad. Använd även parametern **-SQLServerName**. I annat fall försöker installationsprogrammet att hitta en standardinstans som uppfyller kraven. |
| -Port | Den port som ska associeras med och användas av den virtuella Retail Server-katalogen. Om ingen port anges används standardporten 443. |
| -Register | Register-ID som visas på sidan **Register** i headquarters. |
| -RetailServerAadClientId | Det Azure AD klient-ID som Retail Server ska använda under kommunikationen med headquarters. |
| -RetailServerAadResourceId | Resurs-ID:t för Retail Server Azure AD-appen som ska användas när enheten aktiveras. Den här parametern behövs inte för lokal distribution. |
| -RetailServerCertFullPath | Den helt formaterade URN-sökvägen som använder tumavtryck som sökmått för Retail Server-identitetscertifikatet som ska användas för autentisera med Azure AD vid kommunikation med headquarters. Till exempel är `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` ett korrekt formaterat URN där värdet **\<MyThumbprint\>** ersätts med certifikattumavtrycket som ska användas. Använd inte den här parametern tillsammans med parametern **-RetailServerCertThumbprint**. |
| -RetailServerCertThumbprint | Tumavtrycket för Retail Server-identitetscertifikatet som ska användas för att autentisera med Azure AD för kommunikation med headquarters. Det här tumavtrycket används för att söka efter plats och namn för **LocalMachine/Min lagringsplats** för att hitta rätt certifikat att använda. Använd inte den här parametern tillsammans med parametern **-RetailServerCertFullPath**. |
| -RetailServerURL | URL-adressen till Retail Server som installationsprogrammet ska använda. (Den här URL:en är även känd som Commerce Scale Unit-URL:en \[CSU\].) För Modern POS används det här värdet under enhetsaktivering. |
| -SkipAadCredentialsCheck| En switch som anger om förutsättningskontrolleran för Azure AD-autentisering ska hoppas över. Standardvärdet är **falskt**. |
| -SkipCertCheck | En switch som anger om förutsättningskontrolleran för certifikat ska hoppas över. Standardvärdet är **falskt**. |
| -SkipIisCheck | En switch som anger om förutsättningskontrollerna för Internet Information Services (IIS) ska hoppas över. Standardvärdet är **falskt**. |
| -SkipNetFrameworkCheck | En switch som anger om förutsättningskontrolleran för .NET Framework ska hoppas över. Standardvärdet är **falskt**. |
| -SkipScaleUnitHealthcheck | En switch som anger om hälsokontrollen av installerade komponenter ska hoppas över. Standardvärdet är **falskt**. |
| -SkipSChannelCheck | En switch som anger om förutsättningskontrolleran för säker kanal ska hoppas över. Standardvärdet är **falskt**. |
| -SkipSqlFullTextCheck | En switch som anger om validering av SQL Server-förutsättningen som kräver fulltextsökning ska hoppas över. Standardvärdet är **falskt**. |
| -SkipSqlServerCheck | En switch som anger om förutsättningskontrollerna för SQL Server ska hoppas över. Standardvärdet är **falskt**. |
| -SqlServerName | SQL Server-namnet. Om namnet inte angetts försöker installationsprogrammet hitta standardinstansen. |
| -SslcertFullPath | Den helt formaterade URN-sökvägen som använder tumavtryck som sökmått för certifikatplatsen som ska användas för att kryptera HTTP-trafik till skalningsenheten. Till exempel är `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` ett korrekt formaterat URN där värdet **\<MyThumbprint\>** ersätts med certifikattumavtrycket som ska användas. Använd inte den här parametern tillsammans med parametern **-SslCertThumbprint**. |
| -SslCertThumbprint | Tumavtrycket för certifikatet som ska användas för att kryptera HTTP-trafik till skalningsenheten. Det här tumavtrycket används för att söka efter plats och namn för **LocalMachine/Min lagringsplats** för att hitta rätt certifikat att använda. Använd inte den här parametern tillsammans med parametern **-SslCertFullPath**. |
| -StoreSystemAosUrl | URL för headquarters (AOS). |
| -StoreSystemChannelDatabaseId | Kanaldatabasens ID (namn). |
| -TenantId | Azure AD-klientorganisationens ID. |
| -TransactionServiceAzureAuthority | Transaction Service Azure AD-utfärdaren. |
| -TransactionServiceAzureResource | Transaction Service Azure AD-resursen. |
| -TrustSqlServerCertificate | En switch som anger om servercertifikatet ska vara betrott medan en anslutning till SQL Server upprättas. För att undvika säkerhetsrisker ska produktionsdistributioner aldrig leverera ett **sant** värde här. Standardvärdet är **falskt**. |
| -Verbosity | Den loggningsnivå som begärs under installationen. Normalt bör värdet inte användas. |
| -WindowsPhoneAppInsightsInstrumentationKey | Maskinvarustationens AppInsights-instrumentationsnyckel. |

## <a name="general-overview"></a>Allmän översikt

Det nya ramverket för installationsprogram för självbetjäning har olika funktioner och förbättringar. Det nya ramverket genererar installationsprogrammet enbart för Modern POS, maskinvarustation och CSU (egen värd). Det är viktigt att du förstår den grundläggande kommandoradsanvändningen för stängda installationsprogram, som bör se ut ungefär som i följande exempel. 
 
```Console
<Component Installer Name>.exe install -<Parameter Name> "<Parameter Information>"
```

Installationsprogrammet kräver parametern **install** (eller **uninstall** för att ta bort installationen) och alla parametrar som är specifika för den installationen. **Parameternamn** bör innehålla de parametrar som behövs, t.ex. registrering, CSU-URL eller certifikatinformation. **Parameterinformationen** bör innehålla eventuell ytterligare information om parametrarna.

Det stängda ramverket har skapats för att det ska vara möjligt att göra följande ändringar:
- **Stängd** – Det nya ramverket för installationsprogram separerar Microsoft-distribuerade installationsprogram för baskomponenter från de utökningsbara anpassningarna. Anpassningarna installeras efteråt men tas sedan bort när det gäller uppdateringar (så att uppdateringar endast kan tillåtas för Microsofts baskomponent, endast för anpassningar eller för båda).
- **Utan GUI** – Det finns inte längre ett användargränssnitt (UI). I stället finns det en helt kommandoradsstyrd körbar fil för varje komponentinstallationsprogram. Den här ändringen är en av flera viktiga ändringar eller funktioner som används för att fokusera det nya ramverket för installationsprogram på användning för massdistribution.
- **Djupare loggning** – Förbättrade installationsprogramsloggar gör det möjligt att validera installationens slutförande eller fel, vilka steg som har utförts och eventuella varningar och fel som genererats.
- **Rensning** – Inom det nya ramverket arbetar komponentinstallationsprogrammen hårdare för att underhålla installationskatalogerna, genom att rensa hela innehållet i komponentmappen innan de installerar de nyare komponenterna. Denna rensning säkerställer att det inte finns några över kvarlämnade filer som kan orsaka problem och förhindra en lyckad installation.

Tre komponenter har inte migrerats till det nya ramverket: den virtuella kringutrustningssimulatorn, Async Server Connector service (används för Dynamics AX 2012 R3 support) och Real-time Service Replacement (används för Dynamics AX 2012 R3 support).

> [!NOTE]
> Installationsprogram lagras lokalt och sparas.  Det är viktigt att med tiden hantera eller ta bort de sparade installationsprogrammen så att de inte upptar diskutrymme. Det rekommenderas att behålla det aktuella installationsprogrammet för baskomponenterna och eventuella tilläggsinstallationsprogram för de senaste versionerna för återställning från extrema situationer.

## <a name="migration"></a>Migrering

Migrering från de gamla självbetjäningsramverkets komponentinstallationsprogrammen till de nya ramverkets komponentinstallationsprogram kräver avinstallation av de gamla komponenterna.

- **Modern POS** – Det nya ramverket för installationsprogram gör att programmet får ett nytt programsignatur-ID. Därför krävs en fullständig avinstallation av gamla komponenter innan det nya ramverkets Modern POS-komponent installeras. På grund av kravet på fullständig avinstallation måste enhetsaktiveringen göras igen. (Återaktiveringen av enheten är ett engångskrav, förutsatt att avinstallationen inte sker igen.)
- **Maskinvarustation** – Som IIS-webbplats kräver det nya ramverket för installationsprogram att basmappstrukturen omarbetas. Därför krävs en fullständig avinstallation av gamla komponenter innan det nya ramverkets maskinvarustationskomponent installeras.
- **Commerce Scale Unit (CSU, självvärdbaserad)** – Som en serie IIS-webbplatser kräver det nya ramverket för installationsprogram att basmappstrukturen omarbetas.  Därför krävs en fullständig avinstallation av gamla komponenter innan det nya ramverkets CSU-komponent (självvärdbaserad) installeras.

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Innan du börjar

Det är mycket viktigt att du tar bort den gamla Modern POS-komponenten med självbetjäning. Mer information finns i migreringsstegen tidigare i denna artikel.

> [!NOTE]
> På ett endatorsystem som en utvecklartopologi eller en demomiljö, eller när Commerce Scale Unit och Modern POS är installerade på samma dator, är det möjligt för Store Commerce att inte kunna slutföra enhetsaktiveringen. Det här problemet beror på att Store Commerce inte kan ringa nätverkssamtal till samma dator (det vill säga till sig själv). Även om detta aldrig ska vara ett scenario i en produktionsinställning kan problemet minskas genom att ett Loopback-undantag för AppContainer inaktiveras så att kommunikation kan ske till samma dator. Olika program är allmänt tillgängliga för att aktivera denna loopback. För mer information om loopback, se [Hur du aktiverar loopback och felsöker nätverksisolering](/previous-versions/windows/apps/hh780593(v=win.10)). Det är viktigt att du känner till att en loopback kan vara en säkerhetsrisk, så du rekommenderas inte att använda en loopback om du inte är säker på att det behövs.

### <a name="examples-of-silent-deployment"></a>Exempel på tyst distribution

Det här avsnittet innehåller exempel på kommandon som används för installation av Modern POS.

#### <a name="silently-install-modern-pos"></a>Installera Modern POS tyst

Följande kommando installerar (eller uppdaterar) Modern POS tyst. Det har standardkommandostrukturen som används för tyst service av komponenter som för närvarande är installerade. Strukturen använder de grundläggande värdena i **&lt;InstallerName&gt;.exe**.

Följande grundläggande kommando visar vilka tillgängliga alternativ som finns tillgängliga om en installation begärs. Du rekommenderas att använda det här kommandot när du först testar eller använder installationsprogrammet.

```Console
CommerceModernPOS.exe -help install
```

> [!NOTE]
> En konfigurationsfil behövs inte för Modern POS. Installationsprogrammet har nu parametrar (visas tidigare i denna artikel) för de olika värden som används under enhetsaktivering.

Följande kommando specificerar alla parametrar som ska användas under enhetsaktiveringen när Modern POS-programmet har installerats. I det här exemplet används **Houston-3**, som är ett vanligt värde i Dynamics 365 Commerce-demodata.

```Console
CommerceModernPOS.exe install -Register "Houston-3" -Device "Houston-3" -RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

Följande kommando anger de parametrar som ska användas för att installera och konfigurera offlinedatabasen. SQL Server specificeras tillsammans med den konfigurationsfil som ska användas.

```Console
CommerceModernPOS.exe install -InstallOffline -SQLServerName "SQLExpress" -Config "ModernPOS.Houston-3.xml"
```

Du kan blanda och matcha dessa koncept för att uppnå de installationsresultat du vill ha.

## <a name="hardware-station"></a>Maskinvarustation

### <a name="before-you-begin"></a>Innan du börjar

Det är mycket viktigt att du tar bort den gamla maskinvarustationskomponenten med självbetjäning. Mer information finns i migreringsstegen tidigare i denna artikel. Det finns inte längre ett informationsverktyg för handlarkonto. I stället installeras information om handlares konto när en kassaterminal kopplas ihop med maskinvarustationen. När du testar installationsprogrammet för första gången rekommenderar vi att du kör följande kommando:

```Console
CommerceHardwareStation.exe -help install
```

### <a name="examples-of-silent-deployment"></a>Exempel på tyst distribution

Det här avsnittet innehåller exempel på kommandon som används för installation av maskinvarustation.

#### <a name="silently-install-hardware-station"></a>Installera maskinvarustation tyst

Följande kommando installerar (eller uppdaterar) maskinvarustationen tyst. Det har standardkommandostrukturen som används för att serva komponenter som för närvarande är installerade. Strukturen använder de grundläggande värdena i **&lt;InstallerName&gt;.exe**.

Följande grundläggande kommando kör det körbara filinstallationsprogrammet.

```Console
HardwareStation.exe install -Port 443 -StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" -StoreSystemChannelDatabaseID "Houston" -SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> En konfigurationsfil behövs inte för maskinvarustation. Installationsprogrammet har nu parametrar (visas tidigare i denna artikel) för de olika värden som krävs.

Följande kommando anger alla parametrar som krävs för att hoppa över förutsättningskontroller under en standardinstallation. 

> [!NOTE]
> Att hoppa över kontroller rekommenderas inte utan noggrann testning i förväg eller i utvecklingssituationer.

```Console
HardwareStation.exe install -SkipFirewallUpdate -SkipOPOSCheck -SkipVersionCheck -SkipURLCheck -Config "HardwareStation.Houston.xml"
```

Det är vanligt att blanda och matcha dessa koncept för att uppnå de installationsresultat du vill ha.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (självvärdbaserad)

När du testar installationsprogrammet för första gången rekommenderar vi att du kör följande kommando:

```Console
CommerceStoreScaleUnitSetup.exe -help install
```

### <a name="before-you-begin"></a>Innan du börjar

Det är mycket viktigt att du tar bort den gamla CSU-komponenten (självvärdbaserad) med självbetjäning. Mer information finns i migreringsstegen tidigare i denna artikel.

### <a name="examples-of-silent-deployment"></a>Exempel på tyst distribution

Det här avsnittet innehåller exempel på kommandon som används för installation av CSU (självvärdbaserad).

#### <a name="silently-install-csu-self-hosted"></a>Installera CSU-komponent (självvärdbaserad) tyst

Följande kommando installerar (eller uppdaterar) CSU (självvärdbaserad). Det har standardkommandostrukturen som används för tyst service av komponenter som för närvarande är installerade. Strukturen använder de grundläggande värdena i **&lt;InstallerName&gt;.exe**.

Jämfört med andra självbetjäningsinstallationsprogram är Commerce Scale Unit (CSU) mer komplicerat och kräver en ganska stor mängd ytterligare information. Följande kommando är det minimikommando (med parametrar) som krävs för att köra det körbara filinstallationsprogrammet när det inte finns någon konfigurationsfil.

```Console
CommerceScaleUnit.exe install -port 446 -SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate -Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> En konfigurationsfil krävs fortfarande för CSU (självvärdbaserad).

Följande kommando är ett mer ingående kommando som kör det körbara filinstallationsprogrammet med några alternativa parametrar.

```Console
CommerceScaleUnit.exe install -Port 446 -SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate -Verbosity 0 -Config "Contoso.StoreSystemSetup.xml"
```

Följande kommando anger parametrar som krävs för att hoppa över förutsättningskontroller under en standardinstallation. 

> [!NOTE]
> Att hoppa över kontroller rekommenderas inte utan noggrann testning i förväg eller i utvecklingssituationer.


```Console
CommerceScaleUnit.exe installer -skipscaleunithealthcheck -skipcertcheck -skipaadcredentialscheck -skipschannelcheck -skipiischeck -skipnetcorebundlecheck -skipsqlservercheck -skipnetframeworkcheck -skipversioncheck -skipurlcheck -Config "Contoso.StoreSystemSetup.xml" -SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate
```

Du kan blanda och matcha dessa koncept för att uppnå de installationsresultat du vill ha.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
