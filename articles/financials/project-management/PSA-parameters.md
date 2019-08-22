---
title: Integrationsparametrarna Project Service Automation
description: Det här avsnittet beskriver hur du konfigurerar hur standarddata anges när du integrerar Microsoft Dynamics 365 for Project Service Automation med Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
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
ms.openlocfilehash: b58d2de323395db97d1f8ea146da55bba4e0f9c6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839001"
---
# <a name="project-service-automation-integration-parameters"></a>Parametrar för Project Service Automation-integration

[!include[banner](../includes/banner.md)]

På **Parametrar för Project Service Automation-integration** på sidan kan du konfigurera hur skrivs standarddata när du integrerar Microsoft Dynamics 365 for Project Service Automation med Microsoft Dynamics 365 for Finance and Operations. Följande fält måste konfigureras för att projekt ska kunna synkroniseras från Project Service Automation till Finance and Operations.

> [!NOTE]
> - Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Microsoft Dynamics 365 for Finance and Operations version 8.0.
> - Integrering av faktiska uppgifter finns i Microsoft Dynamics 365 for Finance and Operations version 8.0.1 eller senare.
> - Om du använder Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.

| Flik                    | Fält                | beskrivning |
|------------------------|----------------------|-------------|
| Allmänt                | Standardprojekttyp | Välj förvald projekttyp. När projekt synkroniseras med Project Service Automation används detta värde om du inte angett ett standardvärde i integreringsmallen. I samband med synkroniseringen anges fältet **Projekttyp** som detta värde för nya projekt. Värdet kan dock uppdateras när projektets kontraktrader synkroniseras från Project Service Automation |
|                        | Tidskategori        | Välj standardtidkategori. Detta värde används när timuppskattningar synkroniseras från Project Service Automation. När timuppskattningar och faktiskt timantal synkroniseras med Project Service Automation anges fältet **Kategori** till detta värde för nya prognoser för projekttimme i Finance and Operations. |
|                        | Avgiftskategori         | Välj standardavgiftskategori. Detta värde används när verkliga avgifter synkroniseras från Project Service Automation. När de verkliga avgifterna synkroniseras från Project Service Automation anges fältet **Kategori** för nya transaktioner till detta värde i Finance and Operations. |
| Standardvärden för projektgrupp | Projekttyp         | Klicka på **Ny** för att lägga till en rad där du kan välja den projekttyp som standardprojektgrupp ska anges för. En viss projekttyp kan bara väljas en gång under konfigurationen. |
|                        | Projektgrupp        | Välj standardprojektgrupp för den valda projekttypen. När nya projekt synkroniseras från Project Service Automation kommer fältet **Projektgrupp** att anges som standardvärdet för projekttypen om du inte har angett ett standardvärde i integrationsmallen. |
| Standardvärden för typ av fakturering  | Faktureringstyp         | Klicka på **Ny** för att lägga till en rad där du kan välja den faktureringstyp som standardradegenskap ska anges för. En viss faktureringstyp kan bara väljas en gång under konfigurationen. |
|                        | Radegenskap        | Välj standardradegenskap för vald faktureringstyp. Då nya timuppskattningar, nya utgiftsuppskattningar eller nya verkliga värden synkroniseras från Project Service Automation kommer fältet **Radegenskap** att anges som standardvärdet för faktureringstypen. |
| Funktionslåsning  | Inte tillämpligt       | Välj funktionen som ska inaktiveras i Finance and Operations för projekt och kontrakt som härrör från Project Service Automation. Exempelvis kan du välja att inaktivera möjligheten att redigera kontrakt och projekt, skapa uppdelade arbetsstrukturer samt ange tidrapporter i Finance and Operations. Redovisningsrelaterade fält fortsätter att vara aktiverade, även om de inte blir tillgängliga genom parameterinställningen. Alla funktioner aktiveras som standard. |
