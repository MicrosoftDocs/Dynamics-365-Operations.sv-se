---
title: Integrationsparametrarna Project Service Automation
description: Det här avsnittet beskriver hur du konfigurerar hur standarddata anges när du integrerar Microsoft Dynamics 365 for Project Service Automation med Microsoft Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: cd09dad15112fd71bfd386e0072a77a4121c96e0
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096261"
---
# <a name="project-service-automation-integration-parameters"></a>Parametrar för Project Service Automation-integration

[!include[banner](../includes/banner.md)]

På **Parametrar för Project Service Automation-integration** på sidan kan du konfigurera hur skrivs standarddata när du integrerar Dynamics 365 Project Service Automation med Dynamics 365 Finance. Följande fält måste konfigureras för att projekt ska kunna synkroniseras från Project Service Automation till Finance.

Om du vill öppna sidan **Parametrar för Project Service Automation-integration** gå till **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för Dynamics 365 for Project Service Automation-integration**. 

> [!NOTE]
> - Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i version 8.0.
> - Integrering av faktiska uppgifter finns i version 8.0.1 eller senare.


| Flik                    | Fält                | Beskrivning |
|------------------------|----------------------|-------------|
| Allmänt                | Standardprojekttyp | Välj förvald projekttyp. När projekt synkroniseras med Project Service Automation används detta värde om du inte angett ett standardvärde i integreringsmallen. I samband med synkroniseringen anges fältet **Projekttyp** som detta värde för nya projekt. Värdet kan dock uppdateras när projektets kontraktrader synkroniseras från Project Service Automation |
|                        | Tidskategori        | Välj standardtidkategori. Detta värde används när timuppskattningar synkroniseras från Project Service Automation. När timuppskattningar och faktiskt timantal synkroniseras med Project Service Automation anges fältet **Kategori** till detta värde för nya prognoser för projekttimme i Finance. |
|                        | Avgiftskategori         | Välj standardavgiftskategori. Detta värde används när verkliga avgifter synkroniseras från Project Service Automation. När de verkliga avgifterna synkroniseras från Project Service Automation anges fältet **Kategori** för nya transaktioner till detta värde i Finance. |
| Standardvärden för projektgrupp | Projekttyp         | Klicka på **Ny** för att lägga till en rad där du kan välja den projekttyp som standardprojektgrupp ska anges för. En viss projekttyp kan bara väljas en gång under konfigurationen. |
|                        | Projektgrupp        | Välj standardprojektgrupp för den valda projekttypen. När nya projekt synkroniseras från Project Service Automation kommer fältet **Projektgrupp** att anges som standardvärdet för projekttypen om du inte har angett ett standardvärde i integrationsmallen. |
| Standardvärden för typ av fakturering  | Faktureringstyp         | Klicka på **Ny** för att lägga till en rad där du kan välja den faktureringstyp som standardradegenskap ska anges för. En viss faktureringstyp kan bara väljas en gång under konfigurationen. |
|                        | Radegenskap        | Välj standardradegenskap för vald faktureringstyp. Då nya timuppskattningar, nya utgiftsuppskattningar eller nya verkliga värden synkroniseras från Project Service Automation kommer fältet **Radegenskap** att anges som standardvärdet för faktureringstypen. |
| Funktionslåsning  | Inte aktuellt       | Välj funktionen som ska inaktiveras i Finance för projekt och kontrakt som härrör från Project Service Automation. Exempelvis kan du välja att inaktivera möjligheten att redigera kontrakt och projekt, skapa uppdelade arbetsstrukturer samt ange tidrapporter i Finance. Redovisningsrelaterade fält fortsätter att vara aktiverade, även om de inte blir tillgängliga genom parameterinställningen. Alla funktioner aktiveras som standard. |
