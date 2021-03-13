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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a598f0356034a22ee7fc0902360b8862a1944558
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010982"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="a87b3-103">Synkronisera lageröverföringar och justeringar från Field Service till Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a87b3-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a87b3-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerjusteringar och överföringar från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="a87b3-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="a87b3-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="a87b3-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a87b3-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="a87b3-106">Templates and tasks</span></span>
<span data-ttu-id="a87b3-107">Följande mall och underliggande uppgifter används för att synkronisera lagerjusteringar och överföringar från Field Service till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a87b3-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="a87b3-108">**Mallar i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="a87b3-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="a87b3-109">Lagerjustering (Field Service till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="a87b3-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="a87b3-110">Lageröverföringar (Field Service till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="a87b3-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="a87b3-111">**Uppgifter i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="a87b3-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="a87b3-112">Lagerjusteringar</span><span class="sxs-lookup"><span data-stu-id="a87b3-112">Inventory Adjustments</span></span>
- <span data-ttu-id="a87b3-113">Lageröverföringar</span><span class="sxs-lookup"><span data-stu-id="a87b3-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="a87b3-114">Registeruppsättning</span><span class="sxs-lookup"><span data-stu-id="a87b3-114">Table set</span></span>
| <span data-ttu-id="a87b3-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="a87b3-115">Field Service</span></span>                     | <span data-ttu-id="a87b3-116">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="a87b3-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="a87b3-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="a87b3-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="a87b3-118">Dataverse journalrubriker och journalrader för lagerjustering</span><span class="sxs-lookup"><span data-stu-id="a87b3-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="a87b3-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="a87b3-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="a87b3-120">Dataverse journalrubriker och journalrader för lageröverföring</span><span class="sxs-lookup"><span data-stu-id="a87b3-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="a87b3-121">Registerflöde</span><span class="sxs-lookup"><span data-stu-id="a87b3-121">Table flow</span></span>
<span data-ttu-id="a87b3-122">Lagerjusteringar och överföringar som görs i Field Service synkroniseras till Supply Chain Management efter **Poststatus**-ändringar från **Skapad** till **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="a87b3-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="a87b3-123">När detta inträffar kan justeringen överföringsordern låses och blir skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="a87b3-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="a87b3-124">Detta innebär att justeringar och överföringar kan bokföras i Supply Chain Management och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="a87b3-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="a87b3-125">I Supply Chain Management kan du ställa in ett batchjobb för att automatiskt bokföra justeringarna och överföra lagerjournaler som genererats med integrationen.</span><span class="sxs-lookup"><span data-stu-id="a87b3-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="a87b3-126">Se förutsättningen nedan för mer information om hur du aktiverar batch-jobbet.</span><span class="sxs-lookup"><span data-stu-id="a87b3-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="a87b3-127">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="a87b3-127">Field Service CRM solution</span></span> 
<span data-ttu-id="a87b3-128">Kolumnen **Lagerenheten** har lagts till i tabellen **produkt**.</span><span class="sxs-lookup"><span data-stu-id="a87b3-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="a87b3-129">Denna kolumn krävs eftersom försäljningen och lagerenheten är inte alltid samma Supply Chain Management och lagerenheten behövs för lagerställe i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a87b3-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="a87b3-130">När du anger produkten för en lagerjusteringsprodukt för både lagerjusteringar och lageröverföringar ska enheten hämtas från lagerproduktvärde.</span><span class="sxs-lookup"><span data-stu-id="a87b3-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="a87b3-131">Om det hittas ett värde kommer kolumnen **Enhet** att låsas på lagerjusteringsprodukt.</span><span class="sxs-lookup"><span data-stu-id="a87b3-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="a87b3-132">Kolumnen **Bokför status** har lagts till i både tabellen **Lagerjustering** och **Lageröverföring**.</span><span class="sxs-lookup"><span data-stu-id="a87b3-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="a87b3-133">Den här kolumnen används som filter för när en justering eller överföring skickas till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a87b3-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="a87b3-134">Standard för denna kolumn skapas (1), men det inte skickas till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a87b3-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="a87b3-135">När ändringen är Bokförd (2) skickas den över till Supply Chain Management, men efter detta kommer du inte längre kunna ändra något i justering eller överföring eller lägga till nya rader.</span><span class="sxs-lookup"><span data-stu-id="a87b3-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="a87b3-136">Kolumnen **nummerserie** har lagts till tabellen **lagerjusteringsprodukt**.</span><span class="sxs-lookup"><span data-stu-id="a87b3-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="a87b3-137">Den här kolumnen ser till att integrationen har ett unikt nummer, så du kan skapa och uppdatera justeringen.</span><span class="sxs-lookup"><span data-stu-id="a87b3-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="a87b3-138">När du skapar din första lagerjusteringsprodukt skapas en ny post i tabellen **P2C-autonummer** för att behålla nummerserien och det prefix som används.</span><span class="sxs-lookup"><span data-stu-id="a87b3-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="a87b3-139">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a87b3-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="a87b3-140">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="a87b3-140">Supply Chain Management</span></span>
<span data-ttu-id="a87b3-141">Lagerjournaler från integreringning som genereras av integrationen kan automatiskt bokföras med ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="a87b3-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="a87b3-142">Detta aktiveras från **lagerhantering > periodiska uppgifter > Dataverse-integration > bokför integration av lagerjournaler**.</span><span class="sxs-lookup"><span data-stu-id="a87b3-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a87b3-143">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="a87b3-143">Template mapping in Data integration</span></span>

<span data-ttu-id="a87b3-144">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="a87b3-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="a87b3-145">Lagerjustering (Field Service till Supply Chain Management): Lagerjustering</span><span class="sxs-lookup"><span data-stu-id="a87b3-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="a87b3-146">[![Mallmappning i dataintegrering](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="a87b3-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="a87b3-147">Lageröverföring (Field Service till Supply Chain Management): Lageröverföring</span><span class="sxs-lookup"><span data-stu-id="a87b3-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="a87b3-148">[![Mallmappning i dataintegrering](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="a87b3-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
