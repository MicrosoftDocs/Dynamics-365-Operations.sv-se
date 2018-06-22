---
title: "Synkronisera projektuppgiftskategorier från Project Service Automation"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Dynamics 365 for Project Service Automation."
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Dynamics 365 for Project Service Automation.

> [!NOTE]
> Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Dataflöde för Project Service Automation och Finance and Operations

Automatisering av integrationslösningen Project Service Automation och Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om transaktionskategorier för projektutgifter mellan Finance and Operations och Project Service Automation.

Om projektets utgiftskategorier hanteras i Finance and Operations, är integrationsflödet först från Finance and Operations till Project Service Automation och sedan uppdateras integrations-ID för projektets utgiftskategorier genom att synkronisera från Project Service Automation till Finance and Operations.

Om projektets utgiftskategorier hanteras i Project Service Automation, är integrationsflödet först från Project Service Automation till Finance and Operations. Projektkategorier måste också vara konfigurerade i Finance and Operations före synkronisering från Project Service Automation. Synkronisera sedan från Finance and Operations tillbaka till Project Service Automation och sedan från Project Service Automation till Finance and Operations igen. Detta säkerställer att kategorier länkas och dubbletter skapas inte.

> [!NOTE]
> Vanligtvis kommer projektets utgiftskategorier att hanteras i Finance and Operations. Om detta inte är din situation och du redan har utgiftskategorier skapade i Project Service Automation måste du först synkronisera med projektets utgiftstransaktionskategorier (PSA till Fin and Ops) och sedan synkronisera med projektets utgiftstransaktionskategorier (Fin and Ops till PSA). Du bör sedan köra synkroniseringen från PSA till Fin and Ops en gång.

> Om du först synkroniseras från Project Service Automation måste projektkategorier redan ställas in i Finance and Operations och eventuella projektkategorier måste vara synkroniserade med transaktionskategorier i Project Service Automation som måste vara inställda på **Aktiva i journaler**.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Project Service Automation:

-  **Namnet på mallen i dataintegrering:**  projektets utgiftstransaktionskategorier (Fin and Ops till PSA)
-  **Namnet på uppgiften i projektet:** synkronisera kategorier till PSA

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Integrationsenhet för kategorier    | Transaktionskategorier        |

## <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för att ställa in faktureringstypen på transaktionskategorin när du synkroniserar till Project Service Automation. Mallen för projektets utgiftstransaktionskategorier (Fin and Ops till PSA) har en standardkolumn och mappning finns redan. Om du skapar en egen mall måste du lägga till en villkorlig kolumn i Power Query.
- Öppna Advance Query och filtreringsformulär inifrån mappningen av projektets utgiftskategoriuppgifter.
- Välj **lägga till villkorlig kolumn**.
- Namnge den nya kolumnen, till exempel BillingType.
- Ange följande villkor: om **CATEGORYID inte är lika med noll sedan 19235001, annars noll**.
- Klicka **OK** på kolumnen.
- Måste du mappa den här nya kolumnen på mappningssidan.

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.

[![Mallmappning](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Finance and Operations:

-**Namnet på mallen för dataintegrering:** projektets utgiftstransaktionskategorier (PSA till Fin and Ops) -**namnet på uppgiften i projektet:** synkronisera kategorier till Fin Ops

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Transaktionskategorier          | Integrationsenhet för kategorier  | 

## <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier. Synkroniseringen tillbaka till Finance and Operations uppdaterar integrations-ID från Project Service Automation i projektkategorin för Finance and Operations.

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

