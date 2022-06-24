---
title: Systemkrav
description: Denna artikel anger systemkraven för Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b07d14dfe0e6b53c9489c284520a24b97d9887fa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879349"
---
# <a name="system-requirements"></a>Systemkrav

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Denna artikel anger systemkraven för Microsoft Dynamics 365 Human Resources. Det visar också de länder och regioner där personal finns tillgänglig, plus information om språk och lokalisering av personaldata.

## <a name="supported-web-browsers"></a>Webbläsare som stöds

Användare får åtkomst till Microsoft Dynamics 365 Human Resources via samtliga följande webbläsare som körs på angivna operativsystem: 

*   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
*   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
*   Google Chrome (den senaste tillgängliga versionen)
*   Apple Safari (den senaste tillgängliga versionen)

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

## <a name="special-considerations"></a>Särskilda beaktanden

* Du måste installera en förhandsversion av ett Chrome-tillägg för att göra det möjligt för Uppgiftsinspelaren för att ta skärmbilder och inkludera dem i genererade Microsoft Word-dokument
* Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
* Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.

## <a name="network-requirements"></a>Nätverkskrav

* Personal har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre. Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Personal. Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure fördröjningstest").
* Bandbreddskrav för personal beror på ditt scenario. Typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).
 
> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en testversion av Talent för kunder som är bekymrade över bandbreddskraven av personal.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

* För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om kraven på version finns i [felsökning av Office-integrering](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Felsöka Office-integrering").
* Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="regional-availability-languages-and-localization"></a>Lokal tillgänglighet, språk och lokalisering

Du kan hämta en PDF-fil för de länder, regioner och språk som personal stöder med [internationell tillgänglighet på Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> När användargränssnittet har lokaliserats till andra språk lagras alla användardata på det språk som det har angetts i. Du kan skapa e-postmeddelanden och mallar på andra språk, men data som t.ex. schemaläggningsinformation är bara tillgänglig på engelska för närvarande.

Om du är en utvecklare som vill skapa lands- eller regionsspecifika anpassningar eller skapa en lösning för ett land eller en region som inte stöds av Microsoft, se [globaliseringsfunktionen.](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
