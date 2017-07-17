---
title: Systemkrav
description: "Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 724ee7ec29f8a9c4e8cc0b244193cd6c83c37f03
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Systemkrav
<a id="system-requirements" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Webbläsare som stöds
<a id="supported-web-browsers" class="xliff"></a>
----------------------

Webbprogrammet går att köra i följande webbläsare som körs på de angivna operativsystemen:

-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
-   Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

**Anteckningar:**

-   En förhandsversion av ett Chrome-tillägg måste installeras för att tillåta skärmbilder att hämtas av Uppgiftsinspelaren och inkluderas i genererade Microsoft Word-dokument. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
-   Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
-   Rapportdesignern för ekonomisk rapportering startar som ClickOnce-programmet. Kräver 64-bitars kompatibelt operativsystem. Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder Chrome med osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge.
-   Om du vill förhandsgranska PDF-filer bör du använda moderna webbläsare såsom Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.


### Webbläsare som stöds för molnbaserad kassa för butik
<a id="supported-web-browsers-for-retail-cloud-pos" class="xliff"></a>

Molnbaserad kassa för butik går att köra i följande webbläsare som körs på de angivna operativsystemen:

-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Chrome (senaste tillgängliga versionen) i Windows 7, 8.1 för Windows eller Windows 10

## Nätverkskrav
<a id="network-requirements" class="xliff"></a>
-   Dynamics 365 for Finance and Operations, Enterprise edition har utformats för nätverk med svarstider på maximalt 250-300 millisekunder. Detta är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Finance and Operations. Vi rekommenderar att du testar nätverksfördröjning vid <http://www.azurespeed.com>.
-   Bandbreddskrav beror på ditt scenario. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps). Scenarier som har höga nyttolastkrav, till exempel arbetsytor eller scenarier som involverar omfattande anpassning, rekommenderas större bandbredd.

I allmänhet är Finance and Operations optimerad för Internet. Antalet returresor från en webbläsarklient till Azure datacenter är mycket liten och hela nyttolasten komprimeras. 

**Varning:** Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en förhandsversion av Finance and Operations för kunder som är bekymrade över bandbreddskraven.

## Krav på .NET Framework
<a id="net-framework-requirements" class="xliff"></a>
.NET Framework version 4.6.2 krävs för alla ClickOnce-program, t.ex. dokumentflödesagent. Installationsinstruktioner finns i [installation av .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## Microsoft Office-program som stöds
<a id="supported-microsoft-office-applications" class="xliff"></a>
-   För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## Krav på Retail Modern POS
<a id="retail-modern-pos-requirements" class="xliff"></a>
### Operativsystem som stöds
<a id="supported-operating-systems" class="xliff"></a>

-   Retail Modern POS är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail Modern POS stöds bara på Windows 10 Pro, Enterprise och Enterprise Long Term Servicing Branch (LTSB).

### Minsta systemkrav
<a id="minimum-system-requirements" class="xliff"></a>

-   Den lägsta upplösningen som stöds är 1280 × 1024.
-   Den dator som Retail Modern POS körs på måste uppfylla följande villkor:
    -   Den måste har minst en processor med dubbla kärnor som kör med minst 2 GHz (gigahertz).
    -   Den måste ha minst 3 GB (Gigabyte) RAM.
    -   Den måste ha tillgång till Internet.

## Krav på Retail hardware station
<a id="retail-hardware-station-requirements" class="xliff"></a>
### Operativsystem som stöds
<a id="supported-operating-systems" class="xliff"></a>

-   Retail hardware station är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail hardware station stöds i följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate editions **Obs!:** Windows 7 stöds endast om Internet Explorer 11 är manuellt installerad i systemet.
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner

### Minsta systemkrav
<a id="minimum-system-requirements" class="xliff"></a>

Datorn måste uppfylla alla systemkrav för installation och användning av följande objekt:

-   Internet Information Services (IIS)
-   Maskinvara från tredje part

## Krav på Retail Store Scale Unit.
<a id="retail-store-scale-unit-requirements" class="xliff"></a>
### Operativsystem som stöds
<a id="supported-operating-systems" class="xliff"></a>

-   Retail Store Scale Unit är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail Store Scale Unit stöds i följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate-versioner
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner

### Minsta systemkrav
<a id="minimum-system-requirements" class="xliff"></a>

-   4 GB RAM
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

### Rekommenderade systemkrav
<a id="recommended-system-requirements" class="xliff"></a>

-   6 GB RAM
-   2,4 GHz i7 (eller motsvarande) högsta CPU-hastighet per kärna (fyra kärnor rekommenderas).
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

## Kopplingskrav
<a id="connector-requirements" class="xliff"></a>
### Operativsystem som stöds
<a id="supported-operating-systems" class="xliff"></a>

-   Koppling för Microsoft Dynamics AX har två separata installationsprogram **Async Server Connector service** och **Real-time service för Dynamics AX 2012 R3**.
-   Båda komponenterna 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Båda komponenterna kan användas på följande operativsystem:
    -   Windows 7 Professional, Enterprise, och Ultimate-versioner
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner
    -   Windows Server 2012 R2 Windows Server 2016

### Minsta systemkrav
<a id="minimum-system-requirements" class="xliff"></a>

-   2 GB RAM, 4 GB RAM-minne rekommenderas
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

## Krav för utveckling av lokala virtuella maskiner
<a id="requirements-for-development-on-local-vms" class="xliff"></a>
Information om kraven för utveckling av enskilda virtuella datorerna (VMs) finns i [VM körs lokalt](../dev-tools/access-instances.md).

Se även
<a id="see-also" class="xliff"></a>
--------

[Hämta en utvärderingskopia av Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)





