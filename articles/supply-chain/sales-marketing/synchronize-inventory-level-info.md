---
title: Synkronisera information om lagernivåer från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: c7dce4427810b93e0ee4f1a27881c2b1b04fb125
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535708"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Synkronisera information om lagernivåer från Finance and Operations till Field Service 

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera lagerhållningsnivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

**Mall i dataintegrering**
- Produktlager (Fin and Ops till Field Service)
  
**Uppgift i dataintegreringsprojektet**
- Produktlager

Följande synkroniseringsuppgifter krävs före synkronisering av lagernivåer kan uppstå:
- Lagerställen (Fin and Ops till Field Service) 
- Field Service-produkter med lagerenhet (Fin and Ops till Sales) 

## <a name="entity-set"></a>Ange entiteten

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | CDS lagerbehållning enligt lagerställe     |

## <a name="entity-flow"></a>Flöde för entitet
Information om lagernivåer från Finance and Operations till Field Service för utvalda produkter Information om lagernivåer inkluderar: 
- Lagerbehållning (aktuell införd fysisk kvantiteten i lagret)
- Kvantitet har beställts (total registrerad kvantitet som beställts - dvs försäljningsorder)
- Beställd kvantitet beställts (total registrerad beställd kvantitet - dvs försäljningsorder)

Informationen registreras per frisläppt produkt för varje lagerställe och synkroniseras utifrån ändringsspårning när lagernivån ändras.

I Field Service skapar integreringslösningen lagerjournaler för delta, för att få nivåer i Field Service att matcha nivåer i Finance and Operations.

Finance and Operations kommer att fungera som mall för lagernivåer. Därför är det viktigt att ställa in integration för arbetsorder, överföringar och justeringar från Field Service till Finance and Operations om den funktionen används i Field Service samt synkronisering av lagernivåerna från Finance and Operations.

Produkter och lagerställen där lagernivåer hanteras från Finance and Operations kan styras med avancerad fråga och filtrering (Power Query).

> [!NOTE]
> Det går att skapa flera lagerställen i Field Service (med **Hanteras externt = Nej**) och mappa dem till ett enda lager i Finance and Operations med avancerad fråga och filtreringsfunktioner Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Finance and Operations. I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Finance and Operations. För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Entiteten **Externt produktlager** är en ny entitet som endast används för stöd i integrationen. Den här entiteten tar emot värdena för lagernivåer från Finance and Operations i integrationen och omvandlar sedan dessa värden till manuella lagerjournaler, som sedan ändrar lagerprodukterna på lagret.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="data-integration"></a>Dataintegration
För att projektet ska fungera måste du se till att integrationsnyckeln uppdateras för msdynce_externalproductinventories.
1.  Gå till **Dataintegration > anslutningsuppsättningar**.
2.  Välj den använda anslutningsuppsättningen.
3.  På fliken **Integrationsnyckeln**, se till att följande nyckel läggs till msdynce_externalproductinventories:
      - msdynce_productnumber (produktnummer)
      - msdynce_warehouseid (dist.lager-ID)
      
### <a name="data-integration-project"></a>Dataintegreringsprojektet
Du kan tillämpa filter med avancerad fråga och filtrering för att kontrollera att bara önskade produkter och lagerställen skickar information om lagernivåer från Finance and Operations till Field Service.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a>Produktlager (Fin and Ops till Field Service): Produktlager

[![Mallmappning i dataintegrering](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
