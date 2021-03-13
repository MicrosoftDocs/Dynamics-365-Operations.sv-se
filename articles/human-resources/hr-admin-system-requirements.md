---
title: Systemkrav
description: I den här artikeln beskrivs kraven för Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e7d7389c1bcf0f6024464e37b36d39efae5b832
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114270"
---
# <a name="system-requirements"></a>Systemkrav

I den här artikeln beskrivs kraven för Microsoft Dynamics 365 Human Resources. Det visar också de länder och regioner där personal finns tillgänglig, plus information om språk och lokalisering av personaldata.

## <a name="supported-web-browsers"></a>Webbläsare som stöds

Personal går att köra i följande webbläsare som körs på de angivna operativsystemen: 

*   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
*   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
*   Google Chrome (den senaste tillgängliga versionen)
*   Apple Safari (den senaste tillgängliga versionen)

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

> [!NOTE]
> * Om du vill hämta bilder som har skapats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg. 
> * Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
> * Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.
>   Nätverkskrav
> * Personal har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Personal. Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure fördröjningstest").
> * Bandbreddskrav för personal beror på ditt scenario. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).
> 
> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en testversion av Talent för kunder som är bekymrade över bandbreddskraven av personal.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

* För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "Felsöka Office-integrering").
* Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="regional-availability-languages-and-localization"></a>Lokal tillgänglighet, språk och lokalisering

Du kan hämta en PDF-fil för de länder, regioner och språk som personal stöder med [internationell tillgänglighet på Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> När användargränssnittet har lokaliserats till andra språk lagras alla användardata på det språk som det har angetts i. Du kan skapa e-postmeddelanden och mallar på andra språk, men data som t.ex. schemaläggningsinformation är bara tillgänglig på engelska för närvarande.

Om du är en utvecklare som vill skapa lands- eller regionsspecifika anpassningar eller skapa en lösning för ett land eller en region som inte stöds av Microsoft, se [globaliseringsfunktionen.](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)
