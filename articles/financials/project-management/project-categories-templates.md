---
title: Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektutgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "347846"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektutgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> - Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Microsoft Dynamics 365 for Finance and Operations version 8.0.
> - Integrering av faktiska uppgifter finns i Microsoft Dynamics 365 for Finance and Operations version 8.0.1 eller senare.
> - Om du använder Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Dataflöde för Project Service Automation och Finance and Operations

Automatisering av integrationslösningen Project Service Automation och Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om transaktionskategorier för projektutgifter mellan Finance and Operations och Project Service Automation.

Om projektets utgiftskategorier hanteras i Finance and Operations sker integrationsflödet först från Project Service Automation till Project Service Automation. Integrations-ID för kategorier för projektutgifter uppdateras sedan genom synkronisering från Project Service Automation till Finance and Operations.

Om projektets utgiftskategorier hanteras i Project Service Automation, är integrationsflödet först från Project Service Automation till Finance and Operations. Projektkategorierna måste också vara konfigurerade i Finance and Operations före synkronisering från Project Service Automation. Synkronisera sedan från Finance and Operations och tillbaka till Project Service Automation, och sedan från Project Service Automation till Finance and Operations igen. På så sätt kan du garantera att kategorierna sammankopplas och att inga dubbletter skapas.

> [!NOTE]
> Vanligtvis hanteras projektets utgiftskategorier i Finance and Operations. Om de inte hanteras i Finance and Operations, eller om utgiftskategorier redan har skapats i Project Service Automation, måste du dock först synkronisera genom att använda mallen för transaktionskategorier för projektutgifter ("PSA till Fin och Ops"). Synkronisera sedan genom att använda mallen för transaktionskategorier för projektutgifter ("Fin och Ops till PSA"). Du bör sedan köra synkroniseringen från Project Service Automation till Finance and Operations en gång till.
>
> Om du synkroniserar från Project Service Automation först måste följande krav uppfyllas i Finance and Operations innan synkroniseringen körs:
>
> - Den delade kategori som matchar den projektkategori som skapas i Project Service Automation måste existera, samt måste aktiveras för såväl **Projekt** och **Utgift**.
> - Följande projektkategorier måste finnas för respektive juridisk Finance and Operations-person med vilken integrering ska ske.
>
>     - **Projekt/kategori** finns. 
>     - **Använd i Utgift** har aktiverats.
>     - **Aktiv i journalen** har aktiverats.
>     - **Transaktionstyp** anges som **Utgift**.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>Synkronisering av projektutgiftskategori från Finance and Operations till Project Service Automation

### <a name="template-and-task"></a>Mall och uppgift

För att få åtkomst till mallen väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Project Service Automation:

- **Namnet på mallen i dataintegrering:**  projektets utgiftstransaktionskategorier (Fin and Ops till PSA)
- **Namnet på uppgiften i projektet:** synkronisera kategorier till PSA

### <a name="entity-set"></a>Ange entiteten

| Finance and Operations            | Project Service Automation |
|-----------------------------------|----------------------------|
| Integrationsenhet för kategorier | Transaktionskategorier     |

### <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.

### <a name="power-query"></a>Power Query

När du synkroniserar med Project Service Automation måste du använda Microsoft Power Query för Excel för att ange faktureringstyp för transaktionskategorin. Mallen för projektets utgiftstransaktionskategorier ("Fin och Ops till PSA") tillhandahåller en standardkolumn och mappning. Om du skapar en egen mall måste du lägga till en villkorlig kolumn i Power Query. Följ dessa steg.

1. Klicka på pilen för att öppna mappningen av projektets utgiftskategoriuppgift i mallen för projektets utgiftstransaktionskategorier ("Fin och Ops till PSA").
2. Klicka på länken **Avancerade frågor och filter** för att öppna Power Query.
2. Välj **lägga till villkorlig kolumn**.
3. Ange ett namn för den nya kolumnen, till exempel **Faktureringstyp**.
4. Ange följande villkor: **om CATEGORYID ej noll så 19235001, annars noll**.
5. Klicka **OK** på kolumnen.
6. Se till att mappa denna nya kolumn på mappningssidan.

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.

[![Mallmappning](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>Synkronisering av projektutgiftskategori från Project Service Automation till Finance and Operations

### <a name="template-and-task"></a>Mall och uppgift

Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Project Service Automation till Finance and Operations:

- **Namn på mallen i dataintegreringen:** Projektets utgiftstransaktionskategorier ("PSA till Fin och Ops")
- **Namnet på uppgiften i projektet:** Synkronisera kategorier till Fin Ops

### <a name="entity-set"></a>Ange entiteten

| Project Service Automation | Finance and Operations            |
|----------------------------|-----------------------------------|
| Transaktionskategorier     | Integrationsenhet för kategorier |

### <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier. Synkroniseringen tillbaka till Finance and Operations uppdaterar projektkategorin i Finance and Operations med integrations-ID från Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)
