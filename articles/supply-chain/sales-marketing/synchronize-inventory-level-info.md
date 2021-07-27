---
title: Synkronisera information om lagerjusteringar från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 05/07/2019
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
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ce5ddf863988475550584384f4cf26f1302768aa
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355911"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Synkronisera information om lagerjusteringar från Supply Chain Management till Field Service 

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service.](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera lagerhållningsnivåer från Supply Chain Management till Field Service.

**Mall i dataintegrering**
- Produktlager (Supply Chain Management till Field Service)
  
**Uppgift i dataintegreringsprojektet**
- Produktlager

Följande synkroniseringsuppgifter krävs före synkronisering av lagernivåer kan uppstå:
- Lagerställen (Supply Chain Management till Field Service) 
- Field Service produkter med lagerenhet (Supply Chain Management till Sales) 

## <a name="entity-set"></a>Ange entiteten

| Field Service                      | Hantering av underleverantörer                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Dataverse lagerbehållning enligt lagerställe     |

## <a name="entity-flow"></a>Flöde för entitet
Information om lagernivåer från Finance and Operations till Field Service för utvalda produkter Information om lagernivåer inkluderar: 
- Lagerbehållning (aktuell införd fysisk kvantiteten i lagret)
- Kvantitet har beställts (total registrerad kvantitet som beställts - dvs försäljningsorder)
- Beställd kvantitet beställts (total registrerad beställd kvantitet - dvs försäljningsorder)

Informationen registreras per frisläppt produkt för varje lagerställe och synkroniseras utifrån ändringsspårning när lagernivån ändras.

I Field Service skapar integreringslösningen lagerjournaler för delta, för att få nivåer i Field Service att matcha nivåer i Supply Chain Management.

Supply Chain Management kommer att fungera som mall för lagernivåer. Därför är det viktigt att ställa in integration för arbetsorder, överföringar och justeringar från Field Service till Supply Chain Management om den funktionen används i Field Service samt synkronisering av lagernivåerna från Supply Chain Management.

Produkter och lagerställen där lagernivåer hanteras från Supply Chain Management kan styras med avancerad fråga och filtrering (Power Query).

> [!NOTE]
> Det går att skapa flera lagerställen i Field Service (med **Hanteras externt = Nej**) och mappa dem till ett enda lager i Supply Chain Management med avancerad fråga och filtreringsfunktioner Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Supply Chain Management. I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Supply Chain Management. För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Entiteten **Externt produktlager** är en ny entitet som endast används för stöd i integrationen. Den här entiteten tar emot värdena för lagernivåer från Supply Chain Management i integrationen och omvandlar sedan dessa värden till manuella lagerjournaler, som sedan ändrar lagerprodukterna på lagret.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="data-integration"></a>Dataintegration
För att projektet ska fungera måste du se till att integrationsnyckeln uppdateras för msdynce_externalproductinventories.
1.  Gå till **Dataintegration > anslutningsuppsättningar**.
2.  Välj den använda anslutningsuppsättningen.
3.  På fliken **Integrationsnyckeln**, se till att följande nyckel läggs till msdynce_externalproductinventories:
      - msdynce_productnumber (produktnummer)
      - msdynce_warehouseid (dist.lager-ID)
      
### <a name="data-integration-project"></a>Dataintegreringsprojektet
Du kan tillämpa filter med avancerad fråga och filtrering för att kontrollera att bara önskade produkter och lagerställen skickar information om lagernivåer från Supply Chain Management till Field Service.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Produktlager (Supply Chain Management till Field Service): Produktlager

[![Mallmappning i dataintegrering.](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]