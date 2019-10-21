---
title: Översikt över Project Service Automation
description: Det här ämnet innehåller information om Dynamics 365 Project Service Automation till Dynamics 365 Finance integrationslösning.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250563"
---
# <a name="project-service-automation-overview"></a>Översikt över Project Service Automation

[!include[banner](../includes/banner.md)]

Project Service Automation till Finance integreringslösning använder funktionen för dataintegrering för att synkronisera data mellan instanser av Dynamics 365 Finance och Dynamics 365 Project Service Automation via Common Data Service. De integrationsmallar som medföljer dataintegrationsfunktionen gör et möjligt att aktiver flödet av projekt, projektkontrakt, projektkontraktsrader, projektkontraktraders milstolpar, projektaktiviteter, utgiftstransaktionskategorier, timuppskattningar och utgiftsuppskattningar från Project Service Automation till Finance.

> [!NOTE]
> - Om du använder version 7.3.0, måste du installera KB 4074835. Du kan sedan integrera fastprisprojekt.
> - Om du använder version 7.3.0 och överför avgiftstransaktioner från Project Service Automation måste du installera KB 4345320 för att inkludera dessa avgifter på projektfakturan.
> - Om du använder version 8.0, kommer du att kunna använda projektets uppgiftsintegration, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och funktionslåsning.
> - Om du använder version 8.0.1, eller senare kommer du att kunna synkronisera faktiska värden.

Innan du kan integrera Project Service Automation med Finance måste du konfigurera integrationsparametrar för Project Service Automation. Mer information finns i [Integreringsparametrar för Project Service Automation](PSA-parameters.md).

Den här integrationslösningen möjliggör direkt synkronisering i följande scenarion:

- Underhåll projektkontrakt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Skapa projekt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Underhåll projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Underhåll milstolpar för projektkontraktsrad i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Underhåll projektuppgifter i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Underhåll utgiftstransationskategorier i Finance och synkronisera dem direkt från Finance till Project Service Automation.
- Skapa timuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Skapa projektets utgiftsupppskattningar i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.
- Skapa tid, utgift och verkliga avgiftsvärden för projekt i Project Service Automation och skapa projekttransaktioner i integreringsjournalen för Project Service Automation så att de kan bokföras i Finance.

## <a name="data-synchronization"></a>Datasynkronisering

Följande bild visar hur data synkroniseras som en del av integreringen mellan Project Service Automation och Finance.

> [!NOTE]
> Alla mallar är för närvarande inte tillgängliga. Mallarna kommer att frisläppas när de slutförs.

[![Project Service Automation-integration med Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Systemkrav för Finance

Du måste installera, Enterprise edition 7.3 med plattformsuppdateringen 12 eller senare för att kunna använda integrationslösningen Project Service Automation till Finance.

## <a name="system-requirements-for-project-service-automation"></a>Systemkrav för Project Service Automation

Om du vill använda integrationslösningen för Project Service Automation till Finance måste du installera följande komponenter:

- Dynamics 365 Project Service Automation version 9.0.0.0 eller senare
- Lösningen Potentiell kund till kontanter för Dynamics 365 Sales, version 1.14.0.0 (v14) eller senare.
- Lösning för Project Service Automation till Finance för Dynamics 365 Project Service Automation version 1.0.0.0 or later

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Installera Project Service Automation till Finance i din Project Service Automation-instans

Hämta integreringslösningen Project Service Automation till Finance från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016) och följ de instruktioner som medföljer lösningen.
