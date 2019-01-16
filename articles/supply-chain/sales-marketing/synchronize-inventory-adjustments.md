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

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="77dd5-103">Synkronisera lagerjusteringar från Field Service till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="77dd5-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="77dd5-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="77dd5-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="77dd5-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="77dd5-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="77dd5-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="77dd5-106">Templates and tasks</span></span>
<span data-ttu-id="77dd5-107">Följande mall och underliggande uppgifter används för att synkronisera lagerjusteringar och överföringar från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="77dd5-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="77dd5-108">**Namnet på mallarna i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="77dd5-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="77dd5-109">Lagerjustering (Field Service till Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="77dd5-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="77dd5-110">Lageröverföringar (Field Service till Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="77dd5-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="77dd5-111">**Namnen på uppgifterna i dataintegreringsprojekt:**</span><span class="sxs-lookup"><span data-stu-id="77dd5-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="77dd5-112">Lagerjusteringar</span><span class="sxs-lookup"><span data-stu-id="77dd5-112">Inventory Adjustments</span></span>
- <span data-ttu-id="77dd5-113">Lageröverföringar</span><span class="sxs-lookup"><span data-stu-id="77dd5-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="77dd5-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="77dd5-114">Entity set</span></span>
| <span data-ttu-id="77dd5-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="77dd5-115">Field Service</span></span>                     | <span data-ttu-id="77dd5-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="77dd5-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="77dd5-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="77dd5-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="77dd5-118">CDS journalrubriker och journalrader för lagerjustering</span><span class="sxs-lookup"><span data-stu-id="77dd5-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="77dd5-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="77dd5-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="77dd5-120">CDS journalrubriker och journalrader för lageröverföring</span><span class="sxs-lookup"><span data-stu-id="77dd5-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="77dd5-121">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="77dd5-121">Entity flow</span></span>
<span data-ttu-id="77dd5-122">Lagerjusteringar och överföringar som görs i Field Service synkroniseras till Finance and Operations när **Bokför status** ändras från Skapad till Bokförd.</span><span class="sxs-lookup"><span data-stu-id="77dd5-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="77dd5-123">När detta händer blir justerings- eller överföringsordern låst och skrivskyddad, när justeringar och överföringar kan bokföras i Finance and Operations och kan därför inte ändras.</span><span class="sxs-lookup"><span data-stu-id="77dd5-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="77dd5-124">I Finance and Operations kan du ställa in ett batchjobb för att automatiskt bokföra justeringarna och överföra lagerjournaler som genererats med integrationen.</span><span class="sxs-lookup"><span data-stu-id="77dd5-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="77dd5-125">Se förutsättningen nedan för mer information om hur du aktiverar batch-jobbet.</span><span class="sxs-lookup"><span data-stu-id="77dd5-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="77dd5-126">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="77dd5-126">Field Service CRM solution</span></span> 
<span data-ttu-id="77dd5-127">Fältet Lagerenheten har lagts till produktentiteten.</span><span class="sxs-lookup"><span data-stu-id="77dd5-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="77dd5-128">Detta fält krävs eftersom försäljningen och lagerenheten är inte alltid samma Operations och för lagerställe i Operations behöver vi lagerenheten.</span><span class="sxs-lookup"><span data-stu-id="77dd5-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="77dd5-129">När du anger produkten för en lagerjusteringsprodukt för både lagerjusteringar och lageröverföringar ska enheten hämtas från produktens lagerproduktvärde.</span><span class="sxs-lookup"><span data-stu-id="77dd5-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="77dd5-130">Om det hittas ett värde kommer fältet Enhet att låsas på lagerjusteringsprodukt</span><span class="sxs-lookup"><span data-stu-id="77dd5-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="77dd5-131">Fältet Bokför status har lagts till i både entiteten Jagerjustering och Lageröverföring.</span><span class="sxs-lookup"><span data-stu-id="77dd5-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="77dd5-132">Det här fältet används som filter för när en justering eller överföring skickas till Operations.</span><span class="sxs-lookup"><span data-stu-id="77dd5-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="77dd5-133">Fältet är standard för Skapad (1) och det skickas inte sedan över till Operations.</span><span class="sxs-lookup"><span data-stu-id="77dd5-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="77dd5-134">När ändringen är Bokförd (2) skickas den över till Operations, med du kommer sedan inte längre att kunna ändra något i justering eller överföring eller lägga till nya rader.</span><span class="sxs-lookup"><span data-stu-id="77dd5-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="77dd5-135">Fältet nummerserie har lagts till entiteten lagerjusteringsprodukt.</span><span class="sxs-lookup"><span data-stu-id="77dd5-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="77dd5-136">Det här fältet hjälper integreringen att ha ett unikt nummer så att integrationen vet när den ska skapa och när den ska uppdatera.</span><span class="sxs-lookup"><span data-stu-id="77dd5-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="77dd5-137">När du skapar din första lagerjusteringsprodukt skapas en ny post i entiteten P2C-autonummer för att behålla numemrserien och det prefix som används.</span><span class="sxs-lookup"><span data-stu-id="77dd5-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="77dd5-138">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="77dd5-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="77dd5-139">I Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="77dd5-139">In Finance and Operations</span></span>
<span data-ttu-id="77dd5-140">Lagerjournaler från integreringning som genereras av integrationen kan automatiskt bokföras med ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="77dd5-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="77dd5-141">Detta aktiveras från: lagerhantering > periodiska uppgifter > CDS-integration > bokför integration av lagerjournaler</span><span class="sxs-lookup"><span data-stu-id="77dd5-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="77dd5-142">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="77dd5-142">Template mapping in Data integration</span></span>

<span data-ttu-id="77dd5-143">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="77dd5-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="77dd5-144">Lagerjustering (Field Service till Finance and Operations): Lagerjustering</span><span class="sxs-lookup"><span data-stu-id="77dd5-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="77dd5-145">[![Mallmappning i dataintegrering](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="77dd5-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="77dd5-146">Lageröverföring (Field Service till Finance and Operations): Lageröverföring</span><span class="sxs-lookup"><span data-stu-id="77dd5-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="77dd5-147">[![Mallmappning i dataintegrering](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="77dd5-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

