---
title: Synkronisera lageröverföringar och justeringar från Field Service till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 75181661c41d238cdc06ffbb6969a2efd7d88d46
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/14/2019
ms.locfileid: "842425"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Synkronisera lagerjusteringar från Field Service till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera lagerjustering och överföringar från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.

**Mallar i dataintegrering**
- Lagerjustering (Field Service till Fin and Ops)
- Lageröverföring (Field Service till Fin and Ops)

**Uppgifter i dataintegreringsprojektet**
- Lagerjusteringar
- Lageröverföringar

## <a name="entity-set"></a>Ange entiteten
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS journalrubriker och journalrader för lagerjustering |
| msdyn_inventoryadjustmentproducts | CDS journalrubriker och journalrader för lageröverföring   |

## <a name="entity-flow"></a>Flöde för entitet
Lagerjusteringar och överföringar som görs i Field Service synkroniseras till Finance and Operations efter **Poststatus**-ändringar från **Skapad** till **Bokförd**. När detta inträffar kan justeringen överföringsordern låses och blir skrivskyddad. Detta innebär att justeringar och överföringar kan bokföras i Finance and Operations och kan inte ändras. I Finance and Operations kan du ställa in ett batchjobb för att automatiskt bokföra justeringarna och överföra lagerjournaler som genererats med integrationen. Se förutsättningen nedan för mer information om hur du aktiverar batch-jobbet.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service 
Fältet **Lagerenheten** har lagts till **produktentiteten**. Detta fält krävs eftersom försäljningen och lagerenheten är inte alltid samma Finance and Operations och lagerenheten behövs för lagerställe i Finance and Operations.
När du anger produkten för en lagerjusteringsprodukt för både lagerjusteringar och lageröverföringar ska enheten hämtas från lagerproduktvärde. Om det hittas ett värde kommer fältet **Enhet** att låsas på lagerjusteringsprodukt.

Fältet **Bokför status** har lagts till i både entiteten **Lagerjustering** och **Lageröverföring**. Det här fältet används som filter för när en justering eller överföring skickas till Finance and Operations. Standard för detta fält skapas (1), men det inte skickas till Finance and Operations. När ändringen är Bokförd (2) skickas den över till Finance and Operations, men efter detta kommer du inte längre kunna ändra något i justering eller överföring eller lägga till nya rader.

Fältet **nummerserie** har lagts till entiteten **lagerjusteringsprodukt**. Det här fältet ser till att integrationen har ett unikt nummer, så du kan skapa och uppdatera justeringen. När du skapar din första lagerjusteringsprodukt skapas en ny post i entiteten **P2C-autonummer** för att behålla nummerserien och det prefix som används.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="finance-and-operations"></a>Finance and Operations
Lagerjournaler från integreringning som genereras av integrationen kan automatiskt bokföras med ett batchjobb. Detta aktiveras från: **lagerhantering > periodiska uppgifter > CDS-integration > bokför integration av lagerjournaler**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a>Lagerjustering (Field Service till Fin and Ops): Lagerjustering

[![Mallmappning i dataintegrering](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a>Lageröverföring (Field Service till Fin and Ops): Lageröverföring

[![Mallmappning i dataintegrering](./media/FSTrans1.png)](./media/FSTrans1.png)
