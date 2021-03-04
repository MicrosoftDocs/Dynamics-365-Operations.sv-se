---
title: Talent systemkrav
description: Det här avsnittet beskrivs kraven för Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462574"
---
# <a name="talent-system-requirements"></a>Talent systemkrav

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs kraven för Microsoft Dynamics 365 Talent, inklusive Attract och Onboard. Det visar också de länder och regioner där Talent finns tillgänglig, plus information om språk och lokalisering av Talent data. Dessutom ger det här här avsnittet uppdateringsprincipen för Talent.

## <a name="supported-web-browsers"></a>Webbläsare som stöds

Microsoft Dynamics 365 Talent går att köra i följande webbläsare som körs på de angivna operativsystemen: 

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
> * Dynamics 365 Talent har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Talent. Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure fördröjningstest").
> * Bandbreddskrav för Talent beror på ditt scenario. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).
> 
> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en testversion av Talent för kunder som är bekymrade över bandbreddskraven.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

* För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "Felsöka Office-integrering").
* Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="regional-availability-languages-and-localization"></a>Lokal tillgänglighet, språk och lokalisering

Du kan hämta en PDF-fil för de länder, regioner och språk som Talent stöder med [internationell tillgänglighet på Microsoft Dynamics 365.](https://docs.microsoft.com/dynamics365/get-started/availability) 

> [!NOTE]
> När användargränssnittet har lokaliserats till andra språk lagras alla användardata på det språk som det har angetts i. Du kan skapa e-postmeddelanden och mallar på andra språk, men data som t.ex. schemaläggningsinformation är bara tillgänglig på engelska för närvarande.

Om du är en utvecklare som vill skapa lands- eller regionsspecifika anpassningar eller skapa en lösning för ett land eller en region som inte stöds av Microsoft, se [globaliseringsfunktionen.](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)



[!INCLUDE[footer-include](../includes/footer-banner.md)]