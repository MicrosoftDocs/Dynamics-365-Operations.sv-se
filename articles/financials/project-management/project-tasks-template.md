---
title: "Synkronisera projektuppgifter från Project Service Automation"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: sv-se
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Synkronisera projektuppgifter från Project Service Automation direkt till projektaktiviteter i Finance and Operations

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.

> [!NOTE]
> Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Dataflöde för Project Service Automation till Finance and Operations

Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektuppgifter från Project Service Automation till Finance and Operations.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Mall och uppgift

För att få åtkomst till mallen, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektuppgifter från Project Service Automation till Finance and Operations:

-**Namnet på mallen för dataintegrering:** projektuppgifter (PSA till Fin and Ops) -**namnet på uppgiften i projektet:** projektuppgifter

Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.

## <a name="entity-set"></a>Ange entiteten

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Projektuppgifter                           | Integrationsenhet för projektuppgift.   |

## <a name="entity-flow"></a>Flöde för entitet

Projektuppgifter hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projektaktiviteter.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.

## <a name="power-query"></a>Power Query

Du måste använda  Microsoft Power Query för att filtrera data om följande villkor uppfylls:

- Du har specifika resursposter inom en projektuppgift.

Om du måste använda Power Query enligt riktlinjerna nedan:

- Mallen för projektuppgifter (PSA till Fin and Ops) har standardfilter för att utesluta specifika resursposter från inom en projektuppfigt genom att ange filtret i **IsLineTask** till **falsk**. Om du skapar en egen mall måste du lägga till filtret.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


