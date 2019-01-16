---
title: "Synkronisera lageröverföringar och justeringar från Field Service till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Synkronisera lagerjusteringar från Field Service till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.

**Namnet på mallarna i dataintegreringen**
- Lagerjustering (Field Service till Finance and Operations)
- Lageröverföringar (Field Service till Finance and Operations)

**Namnen på uppgifterna i dataintegreringsprojekt:**
- Lagerjusteringar
- Lageröverföringar

## <a name="entity-set"></a>Ange entiteten
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS journalrubriker och journalrader för lagerjustering |
| msdyn_inventoryadjustmentproducts | CDS journalrubriker och journalrader för lageröverföring   |

## <a name="entity-flow"></a>Flöde för entitet
Lagerjusteringar och överföringar som görs i Field Service synkroniseras till Finance and Operations när **Bokför status** ändras från Skapad till Bokförd. När detta händer blir justerings- eller överföringsordern låst och skrivskyddad, när justeringar och överföringar kan bokföras i Finance and Operations och kan därför inte ändras.
I Finance and Operations kan du ställa in ett batchjobb för att automatiskt bokföra justeringarna och överföra lagerjournaler som genererats med integrationen. Se förutsättningen nedan för mer information om hur du aktiverar batch-jobbet.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service 
Fältet Lagerenheten har lagts till produktentiteten. Detta fält krävs eftersom försäljningen och lagerenheten är inte alltid samma Operations och för lagerställe i Operations behöver vi lagerenheten.
När du anger produkten för en lagerjusteringsprodukt för både lagerjusteringar och lageröverföringar ska enheten hämtas från produktens lagerproduktvärde. Om det hittas ett värde kommer fältet Enhet att låsas på lagerjusteringsprodukt

Fältet Bokför status har lagts till i både entiteten Jagerjustering och Lageröverföring. Det här fältet används som filter för när en justering eller överföring skickas till Operations. Fältet är standard för Skapad (1) och det skickas inte sedan över till Operations. När ändringen är Bokförd (2) skickas den över till Operations, med du kommer sedan inte längre att kunna ändra något i justering eller överföring eller lägga till nya rader.
Fältet nummerserie har lagts till entiteten lagerjusteringsprodukt. Det här fältet hjälper integreringen att ha ett unikt nummer så att integrationen vet när den ska skapa och när den ska uppdatera. När du skapar din första lagerjusteringsprodukt skapas en ny post i entiteten P2C-autonummer för att behålla numemrserien och det prefix som används.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="in-finance-and-operations"></a>I Finance and Operations
Lagerjournaler från integreringning som genereras av integrationen kan automatiskt bokföras med ett batchjobb. Detta aktiveras från: lagerhantering > periodiska uppgifter > CDS-integration > bokför integration av lagerjournaler

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Lagerjustering (Field Service till Finance and Operations): Lagerjustering

[![Mallmappning i dataintegrering](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Lageröverföring (Field Service till Finance and Operations): Lageröverföring

[![Mallmappning i dataintegrering](./media/FSTrans1.png)](./media/FSTrans1.png)

