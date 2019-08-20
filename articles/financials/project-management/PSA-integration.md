---
title: Project Service Automation
description: Det här avsnittet innehåller information om Project Service Automation till integreringslösningen för Finance and Operations. Den här integreringslösningen använder dataintegrering för att synkronisera data mellan instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation med Common Data Service.
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1d6d0b219666bb31cf08da580c701f93d08389a
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741232"
---
# <a name="project-service-automation"></a>Project Service Automation

[!include[banner](../includes/banner.md)]

Project Service Automation till Finance and Operations integreringslösning använder funktionen för dataintegrering för att synkronisera data mellan instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation via Common Data Service. De integrationsmallar som medföljer dataintegrationsfunktionen gör et möjligt att aktiver flödet av projekt, projektkontrakt, projektkontraktsrader, projektkontraktraders milstolpar, projektaktiviteter, utgiftstransaktionskategorier, timuppskattningar och utgiftsuppskattningar från Project Service Automation till Finance and Operations.

> [!NOTE]
> - Om du använder Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.
> - Om du använder Finance and Operations 7.3.0 måste du installera KB 4074835. Du kan sedan integrera fastprisprojekt.
> - Om du använder Finance and Operations 7.3.0 och överför avgiftstransaktioner från Project Service Automation måste du installera KB 4345320 för att inkludera dessa avgifter på projektfakturan.
> - Om du använder Microsoft Dynamics 365 for Finance and Operations version 8.0, kommer du att kunna använda projektets uppgiftsintegration, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och funktionslåsning.
> - Om du använder Microsoft Dynamics 365 for Finance and Operations version 8.0.1, eller senare kommer du att kunna synkronisera faktiska värden.

Innan du kan integrera Project Service Automation med Finance and Operations måste du konfigurera integrationsparametrar för Project Service Automation. Mer information finns i [Integreringsparametrar för Project Service Automation](PSA-parameters.md).

Den här integrationslösningen möjliggör direkt synkronisering i följande scenarion:

- Underhåll projektkontrakt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Skapa projekt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll milstolpar för projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll projektuppgifter i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll utgiftstransationskategorier i Finance and Operations och synkronisera dem direkt från Finance and Operations till Project Service Automation.
- Skapa timuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Skapa utgiftsuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Skapa tid, utgift och verkliga avgiftsvärden för projekt i Project Service Automation och skapa projekttransaktioner i integreringsjournalen för Project Service Automation så att de kan bokföras i Finance and Operations.

## <a name="data-synchronization"></a>Datasynkronisering

Följande bild visar hur data synkroniseras som en del av integreringen mellan Project Service Automation och Finance and Operations.

> [!NOTE]
> Alla mallar är för närvarande inte tillgängliga. Mallarna kommer att frisläppas när de slutförs.

[![Project Service Automation med Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations

Du måste installera Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 med plattformsuppdateringen 12 eller senare för att kunna använda integrationslösningen Project Service Automation till Finance and Operations.

## <a name="system-requirements-for-project-service-automation"></a>Systemkrav för Project Service Automation

Om du vill använda integrationslösningen för Project Service Automation till Finance and Operations måste du installera följande komponenter:

- Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 eller senare
- Lösningen Potentiell kund till kontanter för Microsoft Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.
- Integegrationslösning för Project Service Automation till Finance and Operations för Microsoft Dynamics 365 for Project Service Automation version 1.0.0.0 or later

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Installera Project Service Automation till Finance and Operations i din Project Service Automation-instans

Hämta integreringslösningen Project Service Automation till Finance and Operations från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016) och följ de instruktioner som medföljer lösningen.
