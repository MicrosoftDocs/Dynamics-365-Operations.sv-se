---
title: Systemkrav
description: "Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för moln- och lokala distributioner."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: sv-se
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Systemkrav

[!include[banner](../includes/banner.md)]


Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för moln- och lokala distributioner. Innan du installerar Finance and Operations, kontrollera vid behov om systemet du arbetar med uppfyller eller överskrider minimikraven för programvara, maskinvara och nätverk.


## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds
Följande Office-program stöds i molnet och i lokala distributioner av Finance and Operations.
-   För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Systemkrav som är specifika för molndistributioner
## <a name="network-requirements"></a>Nätverkskrav
-   Finance and Operations har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Detta är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Finance and Operations. Vi rekommenderar att du testar nätverksfördröjning vid <http://www.azurespeed.com>.
-   Bandbreddskrav för Finance and Operations är beroende av en viss situation. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps). Scenarier som har höga nyttolastkrav, till exempel arbetsytor eller scenarier som involverar omfattande anpassning, rekommenderas större bandbredd.

I allmänhet är Finance and Operations optimerad för Internet. Antalet returresor från en webbläsarklient till Azure datacenter är mycket liten och hela nyttolasten komprimeras. 

> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en förhandsversion av Finance and Operations för kunder som är bekymrade över bandbreddskraven.

## <a name="net-framework-requirements"></a>Krav på .NET Framework
Finance and Operations kräver .NET Framework version 4.6.2 för alla enklicksprogram, t.ex. dokumentflödesagent. Installationsinstruktioner finns i [installation av .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Webbläsare som stöds
Webbprogrammet går att köra i följande webbläsare som körs på de angivna operativsystemen:


-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
-   Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

> [!NOTE]
> -   En förhandsversion av ett Chrome-tillägg måste installeras för att tillåta skärmbilder att hämtas av Uppgiftsinspelaren och inkluderas i genererade Microsoft Word-dokument. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
> -   Rapportdesignern för ekonomisk rapportering startar som ClickOnce-programmet. Kräver 64-bitars kompatibelt operativsystem. Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder Chrome med osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge.
> -   Om du vill förhandsgranska PDF-filer bör du använda moderna webbläsare såsom Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Webbläsare som stöds för molnbaserad kassa för butik

Molnbaserad kassa för butik går att köra i följande webbläsare som körs på de angivna operativsystemen:

-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Chrome (senaste tillgängliga versionen) i Windows 7, 8.1 för Windows eller Windows 10

## <a name="retail-modern-pos-requirements"></a>Krav på Retail Modern POS
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Retail Modern POS är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail Modern POS stöds bara på Windows 10 Pro, Enterprise och Enterprise Long Term Servicing Branch (LTSB).

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   Den lägsta upplösningen som stöds är 1280 × 1024.
-   Den dator som Retail Modern POS körs på måste uppfylla följande villkor:
    -   Den måste har minst en processor med dubbla kärnor som kör med minst 2 GHz (gigahertz).
    -   Den måste ha minst 3 GB (Gigabyte) RAM.
    -   Den måste ha tillgång till Internet.

## <a name="retail-hardware-station-requirements"></a>Krav på Retail hardware station
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Retail hardware station är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail hardware station stöds i följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate-versioner 
    
    > [!NOTE]
    > Windows 7 stöds endast om Internet Explorer 11 har installerats manuellt i systemet.

    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner

### <a name="minimum-system-requirements"></a>Minsta systemkrav

Datorn måste uppfylla alla systemkrav för installation och användning av följande objekt:

-   Internet Information Services (IIS)
-   Maskinvara från tredje part

## <a name="retail-store-scale-unit-requirements"></a>Krav på Retail Store Scale Unit.
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Retail Store Scale Unit är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail Store Scale Unit stöds i följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate-versioner
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   4 GB RAM
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

### <a name="recommended-system-requirements"></a>Rekommenderade systemkrav

-   6 GB RAM
-   2,4 GHz i7 (eller motsvarande) högsta CPU-hastighet per kärna (fyra kärnor rekommenderas).
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

## <a name="connector-requirements"></a>Kopplingskrav
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Koppling för Microsoft Dynamics AX har två separata installationsprogram **Async Server Connector service** och **Real-time service för Dynamics AX 2012 R3**.
-   Båda komponenterna 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Båda komponenterna kan användas på följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate-versioner
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner
    -   Windows Server 2012 R2 Windows Server 2016

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   2 GB RAM, 4 GB RAM-minne rekommenderas
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

## <a name="requirements-for-development-on-local-vms"></a>Krav för utveckling av lokala virtuella maskiner
Information om kraven för utveckling av enskilda virtuella datorerna (VMs) finns i [VM körs lokalt](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Systemkrav för lokala distributioner

## <a name="network-requirements"></a>Nätverkskrav
Finance and Operations (lokalt) kan fungera med nätverk som använder Internet Protocol Version 4 (IPv4) eller Internet Protocol Version 6 (IPv6). Överväg nätverksmiljön när du planerar ditt system och följ riktlinjerna nedan.

### <a name="network-response-time"></a>Svarstid för nätverk
Nedan beskrivs minimikraven för nätverk för anslutningen mellan webbläsaren och Application Object Server (AOS) och anslutningen mellan AOS och databasen i ett lokalt system.

| Värde     | Webbläsare till AOS | AOS till databas                                            |
|-----------|--------------------|------------------------------------------------------------|
| Bandbredd | 50 kB/s per användare   | 100 Mbit/s                                                   |
| Svarstid   | < 250-300 ms       | < 1 ms (endast LAN). AOS och databasen måste finnas samtidigt. |

- Finance and Operations (lokal) har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till det datacenter som är värd för Finance and Operations.
- Bandbreddskrav för Finance and Operations (lokal) är beroende av en viss situation. Typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (kB/s) mellan webbläsaren och Finance and Operations-servern. Scenarier som har höga nyttolastkrav, till exempel arbetsytor eller scenarier som involverar omfattande anpassning, rekommenderas större bandbredd och beror på användning.
Distribution där AOS och SQL Server-databasen finns i olika företagsdatacenter stöds inte. AOS och SQL Server-databasen måste vara på samma plats. I allmänhet är Finance and Operations optimerat för att reducera returresor från webbläsare till server. Antalet returresor från en webbläsarklient till datacentret är antingen noll eller ett för varje användarinteraktion.

> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Vi rekommenderar att du använder en verklig simulering mot en miljö för icke-produktion i Finance and Operations som bästa prestandamätare för ditt specifika fall. 

### <a name="lan-environments"></a>LAN-miljöer
I lokala nätverksmiljöer (LAN) krävs inte Microsoft fjärrskrivbord i Microsoft Windows Server för att ansluta till Finance and Operations. Däremot kan det krävas för underhållsåtgärder på virtuella maskiner som utgör serverinstallationer.

### <a name="wan-environments"></a>WAN-miljöer
I WAN-nätverk (Wide Area Network) krävs inte fjärrskrivbord i Windows Server för att ansluta till inance and Operations.

### <a name="internet-connectivity-requirements"></a>Krav för Internetanslutning
Finance and Operations (lokalt) kräver inte Internetanslutning från slutanvändarens arbetsplatser. Dock är vissa funktioner inte tillgängliga utan Internetanslutning.

| Webbläsarklient | Ett intranätscenario utan Internetanslutning är en designpunkt för alternativet för lokal distribution. Vissa funktioner som kräver molnbaserade tjänster inte är tillgängliga, som till exempel Hjälp- och uppgiftsguidebibliotek i LCS. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Server         | AOS eller Service Fabric måste kunna kommunicera med LCS. Lokal webbläsarbaserad klient kräver inte tillgång till Internet.                                                                                |
| Telemetri      | Telemetridata kan gå förlorade om det är långa avbrott i anslutningen. Avbrott i anslutningen till LCS påverkar inte lokala programfunktioner.                                                |
| LCS            | Anslutning till LCS krävs för distribution, kodinstallation och underhållsåtgärder.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Överföring av telemetridata till molnet
De flesta telemetri lagras lokalt och kan nås med hjälp av loggboken i Microsoft Windows. En liten del av telemetrihändelsen överförs till Microsoft telemetriförloppet i molnet för diagnostik. Kunddata och identifierbar data av slutanvändaren tillhör inte telemetrin som skickas till Microsoft. Namn på VM skickas till Microsoft för att underlätta hantering av miljö och diagnostik från LCS-portalen.

## <a name="domain-requirements"></a>Domänkrav
Tänk på följande domänkrav när du installerar Finance and Operations (lokal):

- Virtuella maskiner som är värdar för Finance and Operations (lokal) komponenter måste tillhöra en Active Directory-domän. Active Directory Domain Services (AD DS) måste konfigureras i enhetligt läge.
- Virtuella maskiner som kör Finance and Operations (lokal) komponenter måste ha tillgång till varandra som konfigureras i Active Directory Domain Services. 
- Domänkontrollanten måste köra Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Maskinvarukrav
Det här avsnittet beskriver den maskinvara som behövs för att köra Finance and Operations (lokalt).
Baserat på systemkonfigurationen, datasammansättning och de program och funktioner som du bestämmer dig för att använda kommer kraven på maskinvara att variera. Här följer några av de faktorer som kan påverka valet av lämplig maskinvara för Finance and Operations (lokalt):

- Antal transaktioner per timme.
- Antal samtidiga användare.

## <a name="minimum-infrastructure-requirements"></a>Minsta infrastrukturkrav
Finance and Operations (lokalt) använder Microsoft Azure Service Fabric som värd för AOS, batchn, datahantering, Management reporter och Environment orchestrator-tjänster. Microsoft SQL Server Reporting Services (SSRS) finns inte i Service Fabric-grupperingen.
SQL Server måste ställas in i en HADRON inställning med hög tillgänglighet som har minst två noder för produktionsanvändning.
Bilden nedan visar det minsta rekommenderade antalet noder i din Service Fabric-gruppering.

[![rekommenderat antal noder för Service Fabric-gruppering](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Processor och RAM-krav
Följande tabell visar antalet processorer och mängden direktminne (RAM) som krävs för de olika rollerna som krävs för att köra det här distributionsalternativet. För mer information släs rekommendationen om minimikrav för Service Fabric-grupperingar [Planera och förbereda distributionen av fristående Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Om andra Microsoft-program är installerade på samma dator, måste systemet även uppfylla maskinvarukraven för programvaran. Vi rekommenderar att du begränsar andra serverprogram på samma dator som t.ex. AOS till 1 gigabyte (GB) av RAM.

**Storlekssortering efter roll och topologityp**

| Topologi   | Roll (nodtyp)              | Rekommenderade processorkärnor | Rekommenderat minne (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Produktion | AOS, datahantering, batch   | 8                           | 24                      |
|            | Styrningsrapportering           | 4                           | 16                      |
|            | SQL Server Reporting Services  | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |
| Begränsat fel    | AOS, datahantering, batch   | 4                           | 24                      |
|            | Styrningsrapportering           | 4                           | 16                      |
|            | SQL Server Reporting Services  | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |

**Minsta storleksuppskattningar för produktion och distributioner med begränsat fel**\*

| Topologi                                  | Roll                          | Antal instanser |
|-------------------------------------------|-------------------------------|---------------------|
| Produktion                                | AOS (datahantering, batch)  | 3                   |
|                                           | Styrningsrapportering           | 2                   |
|                                           | SQL Server Reporting Services  | 1                   |
|                                           | Orchestrator\*\*                | 3                   |
| Begränsat fel                                   | AOS, datahantering, batch   | 2                   |
|                                           | Styrningsrapportering           | 1                   |
|                                           | SQL Server Reporting Services  | 1                   |
|                                           | Orchestrator                  | 3                   |
| *Sammanfattningsproduktion och topologier med begränsat fel* |                               | 16                  |

\*Dessa siffror verifieras av våra förhandsgranskningskunder och kan anpassas vid behov utifrån den återkopplingen.

\*\*Orchestrator anges som den primära nodtypen och används för att köra Service Fabric-tjänsten också.

**Intern SQL Server och AD initiala uppskattningar**

[![Intern SQL Server och AD initiala uppskattningar](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*SQL Server-storlekar kan variera mycket beroende på arbetsbelastning. Mer information finns i avsnittet [Maskinvarustorlek för lokala miljöer](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Lagring

- **AOS** - Finance and Operations (lokalt) använder en Server Message Block (SMB) 3.0-resurs för att lagra ostrukturerade data. Mer information finns i [Lagringsplatser direkt i Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – aktuella alternativ:
    - En lättillgänglig SSD-inställning (solid state drive)
    - Ett lagringsnätverk (SAN) optimerad för OLTP-genomflöden.
    - Högpresterande direktansluten lagring (DAS) 
- **SQL och datahantering IOPS** – Lagring för både datahantering och SQL Server ska ha minst 2 000 ingångs-/utgångsåtgärder per sekund (IOPS). Produktions-IOPS beror på flera faktorer. Mer information finns i avsnittet "Maskinvarustorlek för lokala miljöer". 
- **Virtuell dator-IOPS** – varje virtuell dator måste ha minst 100 skriv-IOPS.

## <a name="virtual-host-requirements"></a>Krav för virtuell värd
När du ställer in virtuella värdar för en Finance and Operations-miljö (lokalt) gäller följande riktlinjer: [planera och förbereda din Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) och [Beskriva en Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Varje virtuell värd bör ha tillräckligt med kärnor för den infrastruktur som dimensioneras. Flera avancerade konfigurationer är möjliga om SQL Server finns på fysisk maskinvara men allt annat är virtualiserat. Om SQL Server är virtualiserat ska diskundersystemet vara en snabb SAN eller motsvarande. Kontrollera alltid att grundläggande inställningar för virtuell server är hög tillgängliga och redundanta. I samtliga fall, om virtualisering används, ska ingen VM-ögonblicksbild tas.

## <a name="software-requirements-for-all-server-computers"></a>Programvarukrav för alla serverdatorer
Följande programvara måste finnas på datorn innan några Finance and Operations (lokal)-komponenter kan installeras:

- Microsoft .NET Framework 4.5.1 eller högre
- Service Fabric, för mer information, se [planera och förbereda ditt kluster med Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Serveroperativsystem som stöds
Följande tabell innehåller serveroperativsystem som stöds för Finance and Operations-komponenter.

| Operativsystem                                     | Anteckningar                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter eller Standard | Dessa krav gäller för databasen och Service Fabric-klustret som är värd för AOS. |

## <a name="software-requirements-for-database-servers"></a>Programvarukrav för alla databasservrar

- Endast 64-bitars version av SQL Server 2016 stöds.
- I en produktionsmiljö rekommenderar vi att du installerar den senaste kumulativa uppdateringen (CU) för versionen av SQL Server som du använder.
- Finance and Operations (lokalt) stödjer Unicode-sorteringar som är skiftlägeskänsliga, accentkänsliga, kana-känslig och breddkänsliga. Sorteringen måste matcha de nationella inställningarna på de datorer som kör AOS-instanser. Om du sätter upp en ny installation rekommenderar vi att du väljer en Windows-sortering istället för en SQL Server-sortering. Mer information om hur du väljer en sortering för en SQL Server-databas finns på [dokumentationen till SQL Server](/sql/sql-server/sql-server-technical-documentation).
Följande tabell innehåller de SQL Server-versioner som stöds för Finance and Operations-databaser. Mer information finns i maskinvarukraven för [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Behov                                                      | Anteckningar                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition eller Enterprise Edition | Maskinvarukrav för SQL Server 2016 finns i [Maskin- och programvarukrav för installation av SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Programvarukrav för alla klientdatorer
Webbprogrammet Finance and Operations kan köras på alla enheter med en HTML5.0-kompatibel webbläsare. Specifika enhets-/webbläsarkombinationer som Microsoft har bekräftat omfattar:

- Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
- Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
- Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
- Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Programvarukrav för Active Directory Federation Services 
Active Directory Federation Services (AD FS) i Windows Server 2016

Domänkontrollanten måste vara Windows Server 2012 R2 eller senare med domänfunktionsnivån 2012 R2 eller större

Mer information om domänfunktionsnivåer finns i: 
- [Vad är funktionsnivåer i Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Förstå funktionsnivåer i Active Directory domäntjänster](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Maskin- och programvarukrav för Retail-komponenter
Finance and Operations (lokalt) innehåller inte Retail-komponenter just nu.

<a name="see-also"></a>Se även
--------

[Hämta en utvärderingskopia av Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

