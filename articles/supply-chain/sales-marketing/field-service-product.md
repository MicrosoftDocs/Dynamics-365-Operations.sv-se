---
title: Synkronisera produkter i Supply Chain Management till produkter i Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ffa0616d51127a024bea526c5926a182c0449971
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996748"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="d714e-103">Synkronisera produkter i Supply Chain Management till produkter i Field Service</span><span class="sxs-lookup"><span data-stu-id="d714e-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d714e-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="d714e-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="d714e-105">Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** som används baseras på mallen **Produkter (Supply Chain Management till Sales) – direkt** från potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="d714e-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="d714e-106">Mer information finns i [Produkter (Supply Chain Management till Sales) – direkt](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="d714e-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="d714e-107">Det här ämnet beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Supply Chain Management till Field Service)** och **Produkter (Supply Chain Management till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="d714e-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d714e-108">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="d714e-108">Templates and tasks</span></span>

<span data-ttu-id="d714e-109">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="d714e-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="d714e-110">Field Service-produkter (Supply Chain Management till Field Service).</span><span class="sxs-lookup"><span data-stu-id="d714e-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="d714e-111">**Namnen på uppgiften i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="d714e-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="d714e-112">Produkter - produkter</span><span class="sxs-lookup"><span data-stu-id="d714e-112">Products - Products</span></span>

<span data-ttu-id="d714e-113">Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** inkluderar en mappning som inte inkluderas i mallen **Produkter (Supply Chain Management till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="d714e-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="d714e-114">Den här mappningen säkerställer att det fältservicespecifika fältet **Produkttyp för service** är korrekt inställt.</span><span class="sxs-lookup"><span data-stu-id="d714e-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="d714e-115">Följande värdemappning används.</span><span class="sxs-lookup"><span data-stu-id="d714e-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="d714e-116">I Supply Chain Management beräknas värdet för **Produkttyp för fältservice** på dataentiteten **Säljbara frisläppta produkter** på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d714e-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="d714e-117">**Lager:** produkttyp = produkt- och modellgrupp, produkt i lager = True</span><span class="sxs-lookup"><span data-stu-id="d714e-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="d714e-118">**Ej lagerartikel:** produkttyp = produkt- och modellgrupp, produkt i lager = False</span><span class="sxs-lookup"><span data-stu-id="d714e-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="d714e-119">**Service:** Produkttyp = Service</span><span class="sxs-lookup"><span data-stu-id="d714e-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d714e-120">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="d714e-120">Template mapping in Data integration</span></span>

<span data-ttu-id="d714e-121">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="d714e-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="d714e-122">Field Service-produkter (Supply Chain Management till Field Service): produkter - produkter.</span><span class="sxs-lookup"><span data-stu-id="d714e-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="d714e-123">[![Mallmappning i dataintegrering](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="d714e-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
