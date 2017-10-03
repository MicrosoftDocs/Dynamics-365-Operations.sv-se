---
title: "Systemkrav för molndistributioner"
description: "Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och molndistributioner."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 46eacb2a01c3bfcc7144c7d8c39ee0189fd72e16
ms.contentlocale: sv-se
ms.lasthandoff: 08/04/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Systemkrav för molndistributioner

[!include[banner](../includes/banner.md)]

Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och molndistributioner. Innan du installerar Finance and Operations, kontrollera vid behov om systemet du arbetar med uppfyller eller överskrider minimikraven för programvara, maskinvara och nätverk.

## <a name="supported-web-browsers"></a>Webbläsare som stöds
Webbprogrammet går att köra i följande webbläsare som körs på de angivna operativsystemen:

-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
-   Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

> [!NOTE]
> -   Du måste installera en förhandsversion av ett Chrome-tillägg för att aktivera Uppgiftsinspelare för att ta skärmbilder och inkludera dem i genererade Microsoft Word-dokument. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
> -   Rapportdesignern för ekonomisk rapportering startar som ClickOnce-programmet. Kräver 64-bitars kompatibelt operativsystem. Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder Chrome med osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge.
> -   Om du vill förhandsgranska PDF-filer bör du använda moderna webbläsare såsom Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Webbläsare som stöds för molnbaserad kassa för butik

Molnbaserad kassa för butik går att köra i följande webbläsare som körs på de angivna operativsystemen:

-   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
-   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
-   Chrome (senaste tillgängliga versionen) i Windows 7, 8.1 för Windows eller Windows 10

## <a name="network-requirements"></a>Nätverkskrav
-   Finance and Operations har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna tidsfördröjning är tidsfördröjning från en webbläsarklient till Microsoft Azure datacenter som är värd för Finance and Operations. Vi rekommenderar att du testar nätverksfördröjning vid <http://www.azurespeed.com>.
-   Bandbreddskrav för Finance and Operations är beroende av en viss situation. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps). Scenarier som har höga nyttolastkrav, till exempel scenarier som involverar arbetsytor eller omfattande anpassning, rekommenderas större bandbredd.

I allmänhet är Finance and Operations optimerad för Internet. Antalet returresor från en webbläsarklient till Azure datacenter är mycket liten och hela nyttolasten komprimeras. 

> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Kunder som är bekymrade över bandbreddskraven bör förhandsversion av Finance and Operations.

## <a name="net-framework-requirements"></a>Krav på .NET Framework
Finance and Operations kräver Microsoft .NET Framework version 4.6.2 för alla enklicksprogram, t.ex. dokumentflödesagent. Installationsinstruktioner finns i [installation av .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds
Följande Microsoft Office-program stöds i molnet och i lokala distributioner av Finance and Operations.

-   För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="retail-modern-pos-requirements"></a>Krav på Retail Modern POS

> [!NOTE]
> Om Modern Retail POS kommer att använda offline-databasen, måste datorn uppfylla alla systemkrav för Microsoft SQL Server. En Modern Retail POS offlinedatabasen fungerar på Microsoft SQL Server 2012 med Service Pack 3 eller senare, Microsoft SQL Server 2014 med Service Pack 2 eller senare och Microsoft SQL Server 2016. Vi rekommenderar att du alltid använder den senaste versionen som finns och att du installerar de senaste uppdateringarna.

### <a name="supported-operating-systems"></a>Operativsystem som stöds

-   Retail Modern POS är ett 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Retail Modern POS stöds bara på Windows 10 Pro, Enterprise och Enterprise Long Term Servicing Branch (LTSB).

### <a name="minimum-system-requirements"></a>Minsta systemkrav

-   Den lägsta upplösningen som stöds är 1280 × 1024.
-   Den dator som Retail Modern POS körs på måste uppfylla följande villkor:

    -   Den måste har minst en processor med dubbla kärnor som kör med minst 2 GHz (gigahertz).
    -   Den måste ha minst 3 GB direktminne (RAM).
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

-   Koppling för Microsoft Dynamics AX har två separata installationsprogram Async Server Connector service och Real-time service för Dynamics AX 2012 R3.
-   Båda komponenterna 32-bitars program, men körs på både x86 och x64-arkitektur.
-   Båda komponenterna kan användas på följande operativsystem:

    -   Windows 7 Professional, Enterprise, och Ultimate-versioner
    -   Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded
    -   Windows 10 Pro, Enterprise och Enterprise LTSB-versioner
    -   Microsoft Windows Server 2012 R2 och Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Minsta systemkrav
-   2 GB RAM (4 GB RAM-minne rekommenderas.)
-   1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)
-   Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)

## <a name="requirements-for-development-on-local-vms"></a>Krav för utveckling av lokala virtuella maskiner
Information om kraven för utveckling av enskilda virtuella datorerna (VMs) finns i [VM körs lokalt](../dev-tools/access-instances.md).


## <a name="see-also"></a>Se även

[Hämta en utvärderingskopia av Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

