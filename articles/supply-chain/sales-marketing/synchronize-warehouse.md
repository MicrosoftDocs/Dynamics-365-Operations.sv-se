---
title: Synkronisera lagerställen från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 34cd18a18715d12d4002e6dbeee047467ed2a5ad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "340325"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Synkronisera lagerställen från Finance and Operations till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att köra synkronisering av lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

**Mall i dataintegrering**
- Lagerställen (Finance and Operations till Field Service)

**Uppgift i dataintegreringsprojektet**
- Lagerställe

## <a name="entity-set"></a>Ange entiteten
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Lagerställen                             |

## <a name="entity-flow"></a>Flöde för entitet
Lagerställen som har skapats och underhålls i Finance and Operations kan synkroniseras till Field Service via ett Common Data Service (CDS) dataintegreringsprojekt. De lagerställen som du vill synkronisera till Field Service kan kontrolleras med avancerad fråga och filtrering i projektet. Lagerställen som ska synkroniseras från Finance and Operations skapas i Field Service med fältet **Underhålls externt** anges till **Ja** och posten är skrivskyddad.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
För att stödja integrationen mellan Field Service och Finance and Operations krävs ytterligare funktioner från Field Service CRM-lösning. I lösningen har fältet **Hanteras externt** har lagts till i enheten **Lagerställe (msdyn_warehouses)**. Det här fältet hjälper till att identifiera om lagerstället ska hanteras från Finance and Operations eller om det bara finns i Field Service. Inställningarna för detta fält är:
- **Ja** – Lagerstället kommer från Finance and Operations och kan inte redigeras i Sales.
- **Nej** – Lagerstället angavs direkt i Field Service och underhålls här.

Fältet **Hanteras externt** hjälper till att styra synkroniseringen av lagernivåer, justeringar, överföring och användning av arbetsorder. Endast lagerställen med **Hanteras externt** som anges till **Ja** kan användas för att synkronisera direkt till samma lagerställe i det andra systemet. 

> [!NOTE]
> Det går att skapa flera lagerställen i Field Service (med **Hanteras externt** = Nej) och mappa dem till ett enda lager i Finance and Operations med avancerad fråga och filtreringsfunktioner Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Finance and Operations. I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Finance and Operations. För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar
### <a name="data-integration-project"></a>Dataintegreringsprojektet
Se till att uppdatera avancerad fråga och filtrering på projektet före synkroniseringen av lagerställen för att bara inkludera de lagerställen som du vill flytta från Finance and Operations till Field Service. Observera att du behöver lagerstället i Field Service för att använda det på arbetsorder, justeringar och överföringar.  

Kontrollera att **integreringsnyckel** finns i **msdyn_warehouses** genom att:
1. Gå till dataintegration.
2. Välj fliken **Anslutningsinställning**.
3. Välj anslutningsinställning som används för arbetsordersynkronisering.
4. Välj fliken **Integreringsnyckel**.
5. Sök efter msdyn_warehouses och bekräfta att nyckeln **msdyn_name (namn)** läggs till. Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Lagerställen (Finance and Operations till Field Service): lagerställe

[![Mallmappning i dataintegrering](./media/Warehouse1.png)](./media/Warehouse1.png)
