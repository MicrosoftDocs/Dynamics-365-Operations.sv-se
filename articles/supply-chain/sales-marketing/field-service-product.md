---
title: Synkronisera produkter från Finance and Operations till produkter i Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3f26240ec289f5ddcc2682e598bbf93f516b99af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "316336"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Synkronisera produkter i Finance and Operations till produkter i Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

Mallen **Fältserviceprodukter (Fin and Ops till Field Service)** som används baseras på mallen **Produkter (Field Service till Sales) – direkt** från potentiell kund till kontanter. Mer information finns i [Produkter (Fin and Ops till Sales) – direkt](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Det här ämnet beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Fin and Ops till Field Service)** och **Produkter (Field Service till Sales) – direkt**.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Fältserviceprodukter (Fin and Ops till Field Service)

**Namnen på uppgiften i dataintegreringsprojektet:**

- Produkter - produkter

Mallen **Fältserviceprodukter (Fin and Ops till Field Service)** som används inkluderar en mappning som inte inkluderades i mallen **Produkter (Field Service till Sales) – direkt**. Den här mappningen säkerställer att det fältservicespecifika fältet **Produkttyp för service** är korrekt inställt.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Följande värdemappning används.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

I Finance and Operations beräknas värdet för **Produkttyp för fältservice** på dataentiteten **Säljbara frisläppta produkter** på följande sätt:

- **Lager:** produkttyp = produkt- och modellgrupp, produkt i lager = True
- **Ej lagerartikel:** produkttyp = produkt- och modellgrupp, produkt i lager = False
- **Service:** Produkttyp = Service

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>Fältserviceprodukter (Fin and Ops till Field Service): Produkter - Produkter

[![Mallmappning i dataintegrering](./media/FSProduct.png)](./media/FSProduct.png)
