---
title: Synkronisera lageröverföringar och justeringar från Field Service till Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ff64f28af570b792f73b51aa9caf06dd2445b2ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437553"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Synkronisera lageröverföringar och justeringar från Field Service till Supply Chain Management

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera lagerjusteringar och överföringar från Field Service till Supply Chain Management.

**Mallar i dataintegrering**
- Lagerjustering (Field Service till Supply Chain Management)
- Lageröverföringar (Field Service till Supply Chain Management)

**Uppgifter i dataintegreringsprojektet**
- Lagerjusteringar
- Lageröverföringar

## <a name="entity-set"></a>Ange entiteten
| Field Service                     | Hantering av underleverantörer                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS journalrubriker och journalrader för lagerjustering |
| msdyn_inventoryadjustmentproducts | CDS journalrubriker och journalrader för lageröverföring   |

## <a name="entity-flow"></a>Flöde för entitet
Lagerjusteringar och överföringar som görs i Field Service synkroniseras till Supply Chain Management efter **Poststatus**-ändringar från **Skapad** till **Bokförd**. När detta inträffar kan justeringen överföringsordern låses och blir skrivskyddad. Detta innebär att justeringar och överföringar kan bokföras i Supply Chain Management och kan inte ändras. I Supply Chain Management kan du ställa in ett batchjobb för att automatiskt bokföra justeringarna och överföra lagerjournaler som genererats med integrationen. Se förutsättningen nedan för mer information om hur du aktiverar batch-jobbet.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service 
Fältet **Lagerenheten** har lagts till **produktentiteten**. Detta fält krävs eftersom försäljningen och lagerenheten är inte alltid samma Supply Chain Management och lagerenheten behövs för lagerställe i Supply Chain Management.
När du anger produkten för en lagerjusteringsprodukt för både lagerjusteringar och lageröverföringar ska enheten hämtas från lagerproduktvärde. Om det hittas ett värde kommer fältet **Enhet** att låsas på lagerjusteringsprodukt.

Fältet **Bokför status** har lagts till i både entiteten **Lagerjustering** och **Lageröverföring**. Det här fältet används som filter för när en justering eller överföring skickas till Supply Chain Management. Standard för detta fält skapas (1), men det inte skickas till Supply Chain Management. När ändringen är Bokförd (2) skickas den över till Supply Chain Management, men efter detta kommer du inte längre kunna ändra något i justering eller överföring eller lägga till nya rader.

Fältet **nummerserie** har lagts till entiteten **lagerjusteringsprodukt**. Det här fältet ser till att integrationen har ett unikt nummer, så du kan skapa och uppdatera justeringen. När du skapar din första lagerjusteringsprodukt skapas en ny post i entiteten **P2C-autonummer** för att behålla nummerserien och det prefix som används.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="supply-chain-management"></a>Hantering av underleverantörer
Lagerjournaler från integreringning som genereras av integrationen kan automatiskt bokföras med ett batchjobb. Detta aktiveras från: **lagerhantering > periodiska uppgifter > CDS-integration > bokför integration av lagerjournaler**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Lagerjustering (Field Service till Supply Chain Management): Lagerjustering

[![Mallmappning i dataintegrering](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Lageröverföring (Field Service till Supply Chain Management): Lageröverföring

[![Mallmappning i dataintegrering](./media/FSTrans1.png)](./media/FSTrans1.png)
