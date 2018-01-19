---
title: Dynamics 365 for Talent, systemkrav och uppdateringspolicy
description: "Det här avsnittet beskriver kraven för Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-talent
ms.technology: 
ms.search.form: Talent, update policy, requirements, system requirements
audience: Application User, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7bcc8464d34c35423e86c963c6b493fc09db4472
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="microsoft-dynamics-365-for-talent-system-requirements-and-update-policy"></a>Microsoft Dynamics 365 for Talent, systemkrav och uppdateringspolicy

[!include[banner](includes/banner.md)]


Det här avsnittet beskriver kraven för Microsoft Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn.

## <a name="supported-web-browsers"></a>Webbläsare som stöds

Microsoft Dynamics 365 for Talent webbprogram går att köra i följande webbläsare som körs på de angivna operativsystemen: 

*   Microsoft Edge (den senaste tillgängliga versionen) på Windows 10
*   Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7
*   Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta
*   Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad

Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare. 

> [!NOTE]
> * Om du vill hämta bilder som har genererats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg. 
> * Arbetsflödesredigeraren startas som ett ClickOnce-program. Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program. Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.
> * Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.
Nätverkskrav
> * Dynamics 365 for Talent har utformats för nätverk med svarstider på maximalt 250-300 millisekunder. Detta är svarstiden från en webbläsarklient till datacentret Azure som är värd för Dynamics 365 for Talent. Vi rekommenderar att du testar nätverksfördröjning på [www.azurespeed.com] (http://www.azurespeed.com "Azure fördröjningstest").
> * Bandbreddskrav för Dynamics 365 for Talent är beroende av en viss situation. Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).

> [!WARNING]
> Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs. Det är mycket svårt att beräkna samtidiga användningen av en viss plats. Använd en testversion av Dynamics 365 for Talent för kunder som är bekymrade över bandbreddskraven.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

*   För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat. Mer information om versionskraven finns i [Felsökning av Office-integrering] (../dev-itpro/office-integration/office-integration-troubleshooting.md "Felsökning av Office-integrering").
*   Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.

## <a name="update-policy"></a>Uppdatera policy

Microsoft Dynamics 365 for Talent hanteras som ett molnbaserat erbjudande. Uppdateringar för Dynamics 365 for Talent är kontinuerlig och tillämpas automatiskt av Microsoft.

Uppdateringar släpps regelbundet, uppdateringar sker för alla nätverk.  Dynamics 365 for Talent stöds enligt [Microsoft Support Lifecycle-policyn] (https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle") som ger konsekventa och förutsägbara riktlinjer för produktsupport.

