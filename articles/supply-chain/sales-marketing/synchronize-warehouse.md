---
title: Synkronisera lagerställen från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: bb365d1aae2ee6d6417f9a76f3a1716eb61c1f5b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572563"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Synkronisera lagerställen från Supply Chain Management till Field Service

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service.](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att köra synkronisering av lagerställen från Supply Chain Management till Field Service.

**Mall i dataintegrering**
- Lagerställen (Supply Chain Management till Field Service)

**Uppgift i dataintegreringsprojektet**
- Lagerställe

## <a name="table-set"></a>Registeruppsättning
| Field Service    | Hantering av underleverantörer                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Lagerställen                             |

## <a name="table-flow"></a>Registerflöde
Lagerställen som har skapats och underhålls i Supply Chain Management kan synkroniseras till Field Service via ett Microsoft Dataverse dataintegreringsprojekt. De lagerställen som du vill synkronisera till Field Service kan kontrolleras med avancerad fråga och filtrering i projektet. Lagerställen som ska synkroniseras från Supply Chain Management skapas i Field Service med kolumnen **Underhålls externt** anges till **Ja** och posten är skrivskyddad.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
För att stödja integrationen mellan Field Service och Supply Chain Management krävs ytterligare funktioner från Field Service CRM-lösning. I lösningen har kolumnen **Hanteras externt** har lagts till i tabellen **Lagerställe (msdyn_warehouses)**. Den här kolumnen hjälper till att identifiera om lagerstället ska hanteras från Supply Chain Management eller om det bara finns i Field Service. Inställningarna för denna kolumn är:
- **Ja** – Lagerstället kommer från Supply Chain Management och kan inte redigeras i Sales.
- **Nej** – Lagerstället angavs direkt i Field Service och underhålls här.

Kolumnen **Hanteras externt** hjälper till att styra synkroniseringen av lagernivåer, justeringar, överföring och användning av arbetsorder. Endast lagerställen med **Hanteras externt** som anges till **Ja** kan användas för att synkronisera direkt till samma lagerställe i det andra systemet. 

> [!NOTE]
> Det går att skapa flera lagerställen i Field Service (med **Hanteras externt** = Nej) och mappa dem till ett enda lager med avancerad fråga och filtreringsfunktioner Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Supply Chain Management. I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Supply Chain Management. För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar
### <a name="data-integration-project"></a>Dataintegreringsprojektet
Se till att uppdatera avancerad fråga och filtrering på projektet före synkroniseringen av lagerställen för att bara inkludera de lagerställen som du vill flytta från Supply Chain Management till Field Service. Observera att du behöver lagerstället i Field Service för att använda det på arbetsorder, justeringar och överföringar.  

Kontrollera att **integreringsnyckel** finns i **msdyn_warehouses** genom att:
1. Gå till dataintegration.
2. Välj fliken **Anslutningsinställning**.
3. Välj anslutningsinställning som används för arbetsordersynkronisering.
4. Välj fliken **Integreringsnyckel**.
5. Sök efter msdyn_warehouses och bekräfta att nyckeln **msdyn_name (namn)** läggs till. Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Lagerställen (Supply Chain Management till Field Service): lagerställe

[![Mallmappning i dataintegrering.](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]