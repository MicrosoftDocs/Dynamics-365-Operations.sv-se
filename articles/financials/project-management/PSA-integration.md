---
title: Project Service Automation
description: "Den här lösningen använder funktionen Dataintegrering för att synkronisera data över instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a>Project Service Automation

Integrationslösningen Project Service Automation till Finance and Operations använder funktionen Dataintegrering för att synkronisera data över instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS). Aktivera integrationsmallarna som medföljer dataintegrationsfunktionen för att tillåta flöde av projekt, projektkontrakt, projektkontraktsrader, projektkontraktraders milstolpar, projektaktiviteter, utgiftstransaktionskategorier, timuppskattningar, och utgiftsuppskattningar från Project Service Automation till Finance and Operations.

> [!NOTE] 
> Om du använder Dynamics 365 for Finance and Operations, Enterprise Edition, 7.3.0, måste du installera KB 4074835. Detta gör att du kan integrera fastprisprojekt.
>
> Om du använder Dynamics 365 for Finance and Operations version 8.0 kommer du att kunna använda projektets uppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattningar av utgift och funktionslåsning.
>
> Om du använder Dynamics 365 for Finance and Operations version 8.0.1 kan du synkronisera verkliga värden.
>
> Om du använder Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.

Innan du kan integrera Project Service Automation med Finance and Operations måste du konfigurera integrationsparametrar för Project Service Automation. Mer information finns i integrationsparametrar för Project Service Automation.

Den här integrationslösningen möjliggör direkt synkronisering i följande scenarion:

- Underhåll projektkontrakt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Skapa projekt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll milstolpar för projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll projektuppgifter i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Underhåll utgiftstransationskategorier i Finance and Operations och synkronisera dem direkt från Finance and Operations till Project Service Automation.
- Skapa timuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.
- Skapa utgiftsuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.

## <a name="data-synchronization"></a>Datasynkronisering
Följande bild visar hur data synkroniseras som en del av integreringen mellan Project Service Automation och Finance and Operations.

> [!NOTE]
> Alla mallar är för närvarande inte tillgängliga. Mallarna kommer att frisläppas när de slutförs.

[![Project Service Automation med Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations

Du måste installera Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 med plattformsuppdateringen 12 eller senare för att kunna använda integrationslösningen Project Service Automation till Finance and Operations.

## <a name="system-requirements-for-project-service-automation"></a>Systemkrav för Project Service Automation

Om du vill använda integrationslösningen för Project Service Automation till Finance and Operations måste du installera följande komponenter:

- Microsoft Dynamics 365 för Project Service Automation version 9.0.0.0 eller senare.
- Lösningen Potentiell kund till kontanter för Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.
- Lösningen Project Service Automation till Operations för Dynamics 365 for Project Service Automation version 1.0.0.0 eller senare.

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Installera Project Service Automation till Finance and Operations i din Project Service Automation-instans



