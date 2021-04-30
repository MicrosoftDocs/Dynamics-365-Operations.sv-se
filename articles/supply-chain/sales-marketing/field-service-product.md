---
title: Synkronisera produkter i Supply Chain Management till produkter i Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 45a989604d829db715756b6cd206a5675a18acf2
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910001"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="95f92-103">Synkronisera produkter i Supply Chain Management till produkter i Field Service</span><span class="sxs-lookup"><span data-stu-id="95f92-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="95f92-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="95f92-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="95f92-105">Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** som används baseras på mallen **Produkter (Supply Chain Management till Sales) – direkt** från potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="95f92-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="95f92-106">Mer information finns i [Produkter (Supply Chain Management till Sales) – direkt](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="95f92-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="95f92-107">Det här ämnet beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Supply Chain Management till Field Service)** och **Produkter (Supply Chain Management till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="95f92-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="95f92-108">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="95f92-108">Templates and tasks</span></span>

<span data-ttu-id="95f92-109">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="95f92-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="95f92-110">Field Service-produkter (Supply Chain Management till Field Service).</span><span class="sxs-lookup"><span data-stu-id="95f92-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="95f92-111">**Namnen på uppgiften i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="95f92-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="95f92-112">Produkter - produkter</span><span class="sxs-lookup"><span data-stu-id="95f92-112">Products - Products</span></span>

<span data-ttu-id="95f92-113">Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** inkluderar en mappning som inte inkluderas i mallen **Produkter (Supply Chain Management till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="95f92-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="95f92-114">Den här mappningen säkerställer att det fältservicespecifika fältet **Produkttyp för service** är korrekt inställt.</span><span class="sxs-lookup"><span data-stu-id="95f92-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="95f92-115">Följande värdemappning används.</span><span class="sxs-lookup"><span data-stu-id="95f92-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="95f92-116">I Supply Chain Management beräknas värdet för **Produkttyp för fältservice** på dataentiteten **Säljbara frisläppta produkter** på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="95f92-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="95f92-117">**Lager:** produkttyp = produkt- och modellgrupp, produkt i lager = True</span><span class="sxs-lookup"><span data-stu-id="95f92-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="95f92-118">**Ej lagerartikel:** produkttyp = produkt- och modellgrupp, produkt i lager = False</span><span class="sxs-lookup"><span data-stu-id="95f92-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="95f92-119">**Service:** Produkttyp = Service</span><span class="sxs-lookup"><span data-stu-id="95f92-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="95f92-120">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="95f92-120">Template mapping in Data integration</span></span>

<span data-ttu-id="95f92-121">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="95f92-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="95f92-122">Field Service-produkter (Supply Chain Management till Field Service): produkter - produkter.</span><span class="sxs-lookup"><span data-stu-id="95f92-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="95f92-123">[![Mallmappning i dataintegrering](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="95f92-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]