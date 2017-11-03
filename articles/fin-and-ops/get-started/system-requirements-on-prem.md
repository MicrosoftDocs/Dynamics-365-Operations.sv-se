---
title: "Systemkrav för lokala distributioner"
description: "Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och lokala distributioner."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 25a6f326c57e84d6a7c356ac5407be7ed3095f83
ms.openlocfilehash: 5edc6f0b2240e9dd2d3b72a13f35e96f016aa013
ms.contentlocale: sv-se
ms.lasthandoff: 10/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Systemkrav för lokala distributioner

[!include[banner](../includes/banner.md)]

Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och lokala distributioner. Innan du installerar Finance and Operations, kontrollera vid behov om systemet du arbetar med uppfyller eller överskrider minimikraven för programvara, maskinvara och nätverk.

## <a name="network-requirements"></a>Nätverkskrav
Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (lokal) fungerar över nätverk som använder Internet Protocol Version 4 (IPv4) eller Internet Protocol Version 6 (IPv6). Överväg nätverksmiljön när du planerar ditt system och följ riktlinjerna nedan.

### <a name="network-response-time"></a>Svarstid för nätverk
Nedan beskrivs minimikraven för nätverk för anslutningen mellan webbläsaren och Application Object Server (AOS) och anslutningen mellan AOS och databasen i ett lokalt system.

| Värde     | Webbläsare till AOS                      | AOS till databas |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Bandbredd | 50 KB per sekund per användare | 100 MB per sekund (MBps) |
| Svarstid   | Mindre än 250 – 300 millisekunder (ms)     | Mindre än 1 ms (endast lokalt nätverk LAN]). AOS och databasen måste finnas samtidigt. |

- Finance and Operations (lokal) har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till det datacenter som är värd för Finance and Operations.
- Bandbreddskrav för Finance and Operations (lokal) är beroende av en viss situation. Typiska scenarier kräver en bandbredd på mer än 50 kB per sekund mellan webbläsaren och Finance and Operations-servern. Scenarier som har höga nyttolastkrav, till exempel scenarier som involverar arbetsytor eller omfattande anpassning, rekommenderas större bandbredd. Den specifika mängden bandbredd beror på användning.

Distribution där AOS och Microsoft SQL Server-databasen finns i olika datacenter stöds inte. AOS och SQL Server-databasen måste finnas samtidigt. 

I allmänhet är Finance and Operations optimerat för att reducera returresor från webbläsare till server. Antalet returresor från en webbläsarklient till datacentret är antingen noll eller ett för varje användarinteraktion.

> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Vi rekommenderar att du använder en verklig simulering mot en miljö för icke-produktion i Finance and Operations som bästa prestandamätare för ditt specifika fall. 

### <a name="lan-environments"></a>LAN-miljöer
I lokala nätverksmiljöer (LAN) krävs inte Microsoft fjärrskrivbord i Microsoft Windows Server för att ansluta till Finance and Operations. Däremot kan Fjärrskrivbord krävas för underhållsåtgärder på virtuella maskiner (VM) som utgör serverinstallationer.

### <a name="wan-environments"></a>WAN-miljöer
I WAN-nätverk (Wide Area Network) krävs inte fjärrskrivbord i Windows Server för att ansluta till inance and Operations.

### <a name="internet-connectivity-requirements"></a>Krav för Internetanslutning
Finance and Operations (lokalt) kräver inte Internetanslutning från användarens arbetsplatser. Dock är vissa funktioner inte tillgängliga utan Internetanslutning.

|                    |   |
|--------------------|---|
| **Webbläsarklient** | Ett intranätscenario utan Internetanslutning är en designpunkt för alternativet för lokal distribution. Vissa funktioner som kräver molnbaserade tjänster inte är tillgängliga, som till exempel Hjälp- och uppgiftsguidebibliotek i Microsoft Dynamics Lifecycle Services (LCS). |
| **Server**         | AOS eller Microsoft Azure Service Fabric måste kunna kommunicera med LCS. Lokal webbläsarbaserad klient kräver inte tillgång till Internet. |
| **Telemetri**      | Telemetridata kan gå förlorade om det är långa avbrott i anslutningen. Avbrott i anslutningen till LCS påverkar inte lokala programfunktioner. |
| **LCS**            | Anslutning till LCS krävs för distribution, kodinstallation och underhållsåtgärder. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Överföring av telemetridata till molnet
De flesta telemetridata lagras lokalt och kan nås med hjälp av loggboken i Microsoft Windows. En liten del av telemetrihändelsen överförs till Microsoft telemetriförloppet i molnet för diagnostik. Kunddata och identifierbar data av slutanvändaren tillhör inte telemetridata som skickas till Microsoft. Namn på VM skickas till Microsoft för att underlätta hantering av miljö och diagnostik från LCS-portalen.

## <a name="domain-requirements"></a>Domänkrav
Tänk på följande domänkrav när du installerar Finance and Operations (lokal):

- Virtuella maskiner som är värdar för Finance and Operations (lokal) komponenter måste tillhöra en Active Directory-domän. Active Directory Domain Services (AD DS) måste konfigureras i enhetligt läge.
- Virtuella maskiner som kör Finance and Operations (lokal) måste ha åtkomst till varandra. Den här behörigheten är konfigurerad i AD DS. 
- Domänkontrollanten måste vara Microsoft Windows Server 2012 R2 eller senare och domänfunktionsnivån måste vara 2012 R2 eller större

## <a name="hardware-requirements"></a>Maskinvarukrav
Det här avsnittet beskriver den maskinvara som behövs för att köra Finance and Operations (lokalt).

Kraven på maskinvara varierar baserat på systemkonfigurationen, datasammansättning och de program och funktioner som du bestämmer dig för att använda. Här följer några av de faktorer som kan påverka valet av lämplig maskinvara för Finance and Operations (lokalt):

- Antal transaktioner per timme.
- Antal samtidiga användare.

## <a name="minimum-infrastructure-requirements"></a>Minsta infrastrukturkrav
Finance and Operations (lokalt) använder Service Fabric som värd för AOS, batch, datahantering, Management reporter och Environment orchestrator-tjänster. 

SQL Server måste ha en HADRON inställning med hög tillgänglighet som har minst två noder för produktionsanvändning.

Bilden nedan visar det minsta rekommenderade antalet noder i din Service Fabric-gruppering.

[![Rekommenderat antal noder för Service Fabric-gruppering](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Processor och RAM-krav
Följande tabell visar antalet processorer och mängden direktminne (RAM) som krävs för de olika rollerna som krävs för att köra det här distributionsalternativet. För mer information läs rekommendationen om minimikrav för Service Fabric-grupperingar i [Planera och förbereda distributionen av fristående Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Om andra Microsoft-program är installerade på samma dator, måste systemet även uppfylla maskinvarukraven för programvaran. Om andra serverprogram är installerade på samma dator som AOS, rekommenderar vi att du begränsar dessa serverprogram till 1 gigabyte (GB) av RAM.

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

**Minsta storleksuppskattningar för produktion och distributioner med begränsat fel\***

| Topologi                                        | Roll                          | Antal instanser |
|-------------------------------------------------|-------------------------------|---------------------|
| Produktion                                      | AOS (datahantering, batch)  | 3                   |
|                                                 | Styrningsrapportering           | 2                   |
|                                                 | SQL Server Reporting Services  | 1                   |
|                                                 | Orchestrator\*\*              | 3                   |
| Begränsat fel                                         | AOS, datahantering, batch   | 2                   |
|                                                 | Styrningsrapportering           | 1                   |
|                                                 | SQL Server Reporting Services  | 1                   |
|                                                 | Orchestrator                  | 3                   |
| *Sammanfattningsproduktion och topologier med begränsat fel* |                               | *16*                |

\* Siffrorna i tabellen verifieras av våra förhandsgranskningskunder och kan justeras utifrån feedback från dessa kunder.

\*\* Orchestrator anges som den primära nodtypen och används för att köra Service Fabric-tjänsten också.

**Initiala uppskattningar för intern SQL Server och AD DS**

<table>
<thead>
<tr>
<th></th>
<th>Roll</th>
<th>VM/förekomster</th>
<th>Kärnor</th>
<th>Totala kärnor</th>
<th>Minne per instans (GB)</th>
<th>Totalt minne (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Delad infrastruktur</strong></td>
<td>SQL Server*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Filserver/lagringsnätverk/högtillgänglig lagring</td>
<td colspan="5"><p>Intern lagring måste baseras på SSD (solid-state drives) i ett körningslagringsnätverk (SAN).</p>
<p>Genomflödet storlek och ingångs-/utgångsåtgärder per sekund (IOPS) baseras på arbetsbelastningens storlek.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Sammanfattning för en delad infrastruktur</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\*SQL Server-storlekar kan variera mycket beroende på arbetsbelastning. Mer information finns i [Maskinvarustorlek för lokala miljöer](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Lagring

- **AOS** - Finance and Operations (lokalt) använder en Server Message Block (SMB) 3.0-resurs för att lagra ostrukturerade data. Mer information finns i [Lagringsplatser direkt i Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – Följande alternativ är gångbara:

    - En lättillgänglig SSD-inställning
    - En SAN som är optimerad för OLTP-genomflöden (online transaction processing)
    - Högpresterande direktansluten lagring (DAS) 

- **SQL Server och datahantering IOPS** – Lagring för både datahantering och SQL Server ska ha minst 2 000 IOPS. Produktions-IOPS beror på flera faktorer. Mer information finns i [Maskinvarustorlek för lokala miljöer](hardware-sizing-on-premises-environments.md).
- **VM IOPS** – varje VM bör ha minst 100 skriv-IOPS.

## <a name="virtual-host-requirements"></a>Krav för virtuell värd
När du ställer in virtuella värdar för en Finance and Operations-miljö (lokalt) gäller följande riktlinjer: [planera och förbereda din Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) och [Beskriva en Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Varje virtuell värd bör ha tillräckligt med kärnor för den infrastruktur som dimensioneras. Flera avancerade konfigurationer är möjliga om SQL Server finns på fysisk maskinvara men allt annat är virtualiserat. Om SQL Server är virtualiserat ska diskundersystemet vara en snabb SAN eller motsvarande. Kontrollera alltid att grundläggande inställningar för virtuell server är hög tillgängliga och redundanta. I samtliga fall, om virtualisering används, ska ingen VM-ögonblicksbild tas.

## <a name="software-requirements-for-all-server-computers"></a>Programvarukrav för alla serverdatorer
Följande programvara måste finnas på datorn innan några Finance and Operations (lokal)-komponenter kan installeras:

- Microsoft .NET Framework version 4.5.1 eller senare
- Service Fabric

För mer information, se [planera och förbereda ditt kluster med Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Serveroperativsystem som stöds
Följande tabell innehåller serveroperativsystem som stöds för Finance and Operations-komponenter.

| Operativsystem                                     | Anteckningar |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter eller Standard | Dessa krav gäller för databasen och Service Fabric-klustret som är värd för AOS. |

## <a name="software-requirements-for-database-servers"></a>Programvarukrav för alla databasservrar

- Endast 64-bitars version av SQL Server 2016 stöds.
- I en produktionsmiljö rekommenderar vi att du installerar den senaste kumulativa uppdateringen (CU) för versionen av SQL Server som du använder.
- Finance and Operations (lokalt) stödjer Unicode-sorteringar som är skiftlägeskänsliga, accentkänsliga, kana-känslig och breddkänsliga. Sorteringen måste matcha de nationella inställningarna på de datorer som kör AOS-instanser. Om du sätter upp en ny installation rekommenderar vi att du väljer en Windows-sortering istället för en SQL Server-sortering. Mer information om hur du väljer en sortering för en SQL Server-databas finns på [dokumentationen till SQL Server](/sql/sql-server/sql-server-technical-documentation).

Följande tabell innehåller de SQL Server-versioner som stöds för Finance and Operations-databaser. Mer information finns i maskinvarukraven för [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Behov                                                      | Anteckningar |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition eller Enterprise Edition | Maskinvarukrav för SQL Server 2016 finns i [Maskin- och programvarukrav för installation av SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-application-object-server-aos"></a>Programvarukrav för programobjektserver (Application Object Server, eller AOS) 
- SQL Server-integreringstjänster (SSIS)

## <a name="software-requirements-for-reporting-server-bi"></a>Programvarukrav för rapporterignsserver (BI)
- SQL-serverrapporteringstjänster (SSRS)

## <a name="software-requirements-for-client-computers"></a>Programvarukrav för alla klientdatorer
Webbprogrammet Finance and Operations kan köras på alla enheter med en HTML 5.0-kompatibel webbläsare. Här är några specifika enhets-/webbläsarkombinationer som Microsoft har bekräftat:

- Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
- Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
- Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
- Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Programvarukrav för Active Directory Federation Services 
Active Directory Federation Services (AD FS) i Windows Server 2016 krävs

Domänkontrollanten måste vara Windows Server 2012 R2 eller senare och domänfunktionsnivån måste vara 2012 R2 eller större Mer information om domänfunktionsnivåer finns på följande sidor:

- [Vad är funktionsnivåer i Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Förstå funktionsnivåer i Active Directory domäntjänster](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds
Följande Microsoft Office-program stöds i molnet och i lokala distributioner av Finance and Operations.

-   För att kunna köra Microsoft Excel och Microsoft Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Maskin- och programvarukrav för Retail-komponenter
Finance and Operations (lokalt) innehåller för närvarande inte Retail-komponenter.

