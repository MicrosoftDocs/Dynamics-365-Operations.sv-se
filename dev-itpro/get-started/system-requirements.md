---
title: Systemkrav
description: "Det här avsnittet beskrivs systemkraven för den aktuella versionen av Microsoft Dynamics 365 för operationer."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Systemkrav

Det här avsnittet beskrivs systemkraven för den aktuella versionen av Microsoft Dynamics 365 för operationer.

<a name="supported-web-browsers"></a>Webbläsare som stöds
----------------------

Microsoft Dynamics 365 för webbprogrammet operationer kan köras i något av följande webbläsare som körs på de angivna operativsystem:

-   Microsoft Edge (senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Google Chrome (senaste tillgängliga versionen) på Windows 10, 8.1 för Windows, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC
-   Apple Safari (senaste tillgängliga versionen) i Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra) eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. **Anteckningar:**

-   Om du vill hämta bilder som har genererats från Uppgiftsinspelning och inkludera dem i Microsoft Word-dokument måste du ha installerat tillägget krom. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   Arbetsflödesredigeraren startas som en ClickOnce-program. Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
-   Report Designer för ekonomisk rapportering startar som ClickOnce-programmet. Kräver 64-bitars kompatibelt operativsystem. Om du använder krom, måste du installera tillägget ClickOnce för att hämta report designer-klienten. Du använder krom incognito läge, ifall ClickOnce-tillägget aktiveras även för incognito.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Webbläsare som stöds för molnbaserad kassa för butik

Molnet Retail POS till Dynamics 365 för operationer kan köras i något av följande webbläsare som körs på de angivna operativsystem:

-   Microsoft Edge (senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Krom (senaste tillgängliga versionen) i Windows 7, 8.1 för Windows eller Windows 10

## <a name="network-requirements"></a>Nätverkskrav
-   Dynamics 365 för åtgärder som har utformats för nätverk med svarstid på mindre än 150 millisekunder. Detta är svarstiden från en webbläsare klient till datacentret Azure Microsoft Dynamics 365 för operationer där. Vi rekommenderar att du testar nätverksfördröjning vid <http://www.azurespeed.com>.
-   Bandbreddskrav för Dynamics 365 för operationer är beroende av en viss situation. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps). Scenarier som har hög nyttolast krav, till exempel arbetsytor eller omfattande anpassning kanske du behöver rekommenderas större bandbredd dock.

I allmänhet är Dynamics 365 för operationer optimerad för Internet. Hela nyttolast komprimeras antalet kontakter från en webbläsare klient Azure Datacenter är mycket liten. **Varning:** inte beräkna bandbreddskrav från en klient plats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använda en förhandsversion av Dynamics 365 för kunder som inte vill bandbreddskraven för operationer.

## <a name="net-framework-requirements"></a>.NET framework-krav
Dynamics 365 för åtgärder som kräver .NET Framework version 4.6.2 för klickar du på alla-en gång programmen, t ex routing agenten dokument. Installationsinstruktioner finns i [installationen av .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds
-   Om du vill köra Microsoft Excel och Word-tillägg, måste du ha Microsoft Office 2016 för Windows eller Macintosh installerat. Mer information om kraven på version finns [felsökning av Office-integrering](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Om du vill visa dokument som har genererats vid Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare.

## <a name="retail-modern-pos-requirements"></a>Retail POS Modern krav
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Modern Retail POS är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Modern Retail POS stöds bara på Windows 10 Pro, Enterprise och Enterprise lång sikt Underhåll grenen (LTSB).

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   Den lägsta upplösningen stöds är 1280 × 1024.
-   Modern Retail POS körs på datorn måste uppfylla följande villkor:
    -   Den måste har minst en processor med dubbla kärnor som kör med minst 2 GHz (gigahertz).
    -   Måste, minst 3 GB (Gigabyte) RAM.
    -   Den måste ha tillgång till Internet.

## <a name="retail-hardware-station-requirements"></a>Krav för Retail station
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Retail maskinvara station är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Station för Retail-maskinvara stöds i följande operativsystem:
    -   Versioner av Windows 7 Professional, Enterprise och Ultimate **Obs!:** Windows 7 stöds endast om Internet Explorer 11 manuellt är installerat på datorn.
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och inbäddad
    -   Windows 10 Pro, Enterprise och LTSB för Enterprise-versioner

### <a name="minimum-system-requirements"></a>Minsta systemkrav

Datorn måste uppfylla alla systemkrav för installation och användning av följande objekt:

-   Internet Information Services (IIS)
-   Maskinvara från tredje part

## <a name="retail-store-scale-unit-requirements"></a>Krav för Retail Store skala enhet
### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Butik skala är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Butik skala enhet har stöd för följande operativsystem:
    -   Windows 7 Professional, Enterprise- och Ultimate-utgåvor
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och inbäddad
    -   Windows 10 Pro, Enterprise och LTSB för Enterprise-versioner

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   4 GB RAM
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minst.)
-   Minst 10 GB ledigt utrymme (kanal databasen kan kräva stora mängder diskutrymme.)

### <a name="recommended-system-requirements"></a>Rekommenderade systemkrav

-   6 GB RAM
-   2,4 GHz i7 (eller motsvarande) högsta CPU-hastighet per kärna (fyra kärnor rekommenderas).
-   Minst 10 GB ledigt utrymme (kanal databasen kan kräva stora mängder diskutrymme.)

## <a name="requirements-for-development-on-local-vms"></a>Krav för utveckling av lokala virtuella maskiner
Information om kraven för utveckling av enskilda virtuella datorerna (VMs) finns i [VM körs lokalt](/dynamics365/operations/dev-itpro/dev-tools/access-instances#vm-that-is-running-in-premises).

<a name="see-also"></a>Se även
--------

[Hämta en utvärderingsversion av Dynamics 365 för operationer](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


