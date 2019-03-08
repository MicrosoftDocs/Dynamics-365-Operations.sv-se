---
title: Systemkrav och uppdateringspolicy för Talent
description: Det här avsnittet beskrivs kraven för Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn.
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0fa2b7c2dc5b88349cb4012b6b0ba9009a361fa0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306189"
---
# <a name="talent-system-requirements-and-update-policy"></a>Systemkrav och uppdateringspolicy för Talent

[!include [banner](includes/banner.md)]

Det här avsnittet beskrivs kraven för Microsoft Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn.

## <a name="supported-web-browsers"></a>Webbläsare som stöds

Webbprogrammet Microsoft Dynamics 365 for Talent går att köra i följande webbläsare som körs på de angivna operativsystemen: 

*   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
*   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
*   Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
*   Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

> [!NOTE]
> * Om du vill hämta bilder som har skapats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg. 
> * Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
> * Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.
>   Nätverkskrav
> * Dynamics 365 for Talent har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Dynamics 365 for Talent. Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").
> * Bandbreddskrav för Dynamics 365 for Talent beror på ditt scenario. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).
> 
> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en testversion av Dynamics 365 for Talent för kunder som är bekymrade över bandbreddskraven.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

* För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. För mer information om versionskrav läs [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "felsökning av Office-integrering+").
* Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="update-policy"></a>Uppdatera policy

Microsoft Dynamics 365 for Talent hanteras som ett molnbaserad erbjudande. Uppdateringar för Dynamics 365 for Talent är kontinuerlig och tillämpas automatiskt av Microsoft.

Uppdateringar släpps regelbundet, uppdateringar sker för alla nätverk.  Dynamics 365 for Talent stöds enligt [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av produktsupport.
