---
title: Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: f7ea5036682ad5b61fe56acd20a591cccc01f2cb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838329"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> - Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Microsoft Dynamics 365 for Finance and Operations version 8.0.
> - Om du använder Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.
> - Integrering av faktiska uppgifter finns i Microsoft Dynamics 365 for Finance and Operations version 8.0.1 eller senare.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Dataflöde för Project Service Automation till Finance and Operations

Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektuppgifter från Project Service Automation till Finance and Operations.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Mall och uppgift

För att få åtkomst till mallen väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektuppgifter från Project Service Automation till Finance and Operations:

- **Namn på mallen i dataintegrering:** Projektuppgifter ("PSA till Fin och Ops")
- **Namn på uppgiften i projektet:** Projektuppgifter

Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation | Finance and Operations              |
|----------------------------|-------------------------------------|
| Projektuppgifter              | Integrationsenhet för projektuppgift |

## <a name="entity-flow"></a>Flöde för entitet

Projektuppgifter hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projektaktiviteter.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för Excel för att filtrera data om följande villkor uppfylls:

- Du har resursspecifika poster i en projektuppgift.

Om du måste använda Power Query, följ då dessa riktlinjer:

- Mallen för projektuppgifter ("PSA till Fin och Ops") har ett standardfilter som exkluderar resursspecifika poster från en projektuppgift genom att ange filtret i **IsLineTask** som **False**. Om du skapar en egen mall måste du lägga till filtret.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
