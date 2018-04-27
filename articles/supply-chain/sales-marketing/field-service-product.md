---
title: "Synkronisera produkter från Finance and Operations till produkter i Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 699830ce6cd993f3dd3fd4ff744ce5a8b9645c32
ms.contentlocale: sv-se
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="f4bf7-103">Synkronisera produkter från Finance and Operations till produkter i Field Service</span><span class="sxs-lookup"><span data-stu-id="f4bf7-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f4bf7-104">Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="f4bf7-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f4bf7-105">Mallen **Fältserviceprodukter (Fin and Ops till Field Service)** som används baseras på mallen **Produkter (Field Service till Sales) – direkt** från potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="f4bf7-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="f4bf7-106">Mer information finns i [Produkter (Fin and Ops till Sales) – direkt](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="f4bf7-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="f4bf7-107">Det här ämnet beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Fin and Ops till Field Service)** och **Produkter (Field Service till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="f4bf7-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f4bf7-108">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="f4bf7-108">Templates and tasks</span></span>

<span data-ttu-id="f4bf7-109">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="f4bf7-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="f4bf7-110">Fältserviceprodukter (Fin and Ops till Field Service)</span><span class="sxs-lookup"><span data-stu-id="f4bf7-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="f4bf7-111">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="f4bf7-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="f4bf7-112">Produkter - produkter</span><span class="sxs-lookup"><span data-stu-id="f4bf7-112">Products - Products</span></span>

<span data-ttu-id="f4bf7-113">Mallen **Fältserviceprodukter (Fin and Ops till Field Service)** som används inkluderar en mappning som inte inkluderades i mallen **Produkter (Field Service till Sales) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="f4bf7-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="f4bf7-114">Den här mappningen säkerställer att det fältservicespecifika fältet **Produkttyp för service** är korrekt inställt.</span><span class="sxs-lookup"><span data-stu-id="f4bf7-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="f4bf7-115">Följande värdemappning används.</span><span class="sxs-lookup"><span data-stu-id="f4bf7-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="f4bf7-116">I Finance and Operations beräknas värdet för **Produkttyp för fältservice** på dataentiteten **Säljbara frisläppta produkter** på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="f4bf7-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="f4bf7-117">**Lager:** produkttyp = produkt- och modellgrupp, produkt i lager = True</span><span class="sxs-lookup"><span data-stu-id="f4bf7-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="f4bf7-118">**Ej lagerartikel:** produkttyp = produkt- och modellgrupp, produkt i lager = False</span><span class="sxs-lookup"><span data-stu-id="f4bf7-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="f4bf7-119">**Service:** Produkttyp = Service</span><span class="sxs-lookup"><span data-stu-id="f4bf7-119">**Service:** Product type = Service</span></span>

