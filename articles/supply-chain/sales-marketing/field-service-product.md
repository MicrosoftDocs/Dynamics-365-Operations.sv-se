---
title: Synkronisera produkter i Supply Chain Management till produkter i Field Service
description: Denna artikel avhandlar de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: Henrikan
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
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 114550f01f3aed197480fb6830fe913dbfa7b570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860563"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Synkronisera produkter i Supply Chain Management till produkter i Field Service

[!include[banner](../includes/banner.md)]

Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** som används baseras på mallen **Produkter (Supply Chain Management till Sales) – direkt** från potentiell kund till kontanter. Mer information finns i [Produkter (Supply Chain Management till Sales) – direkt](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Denna artikel beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Supply Chain Management till Field Service)** och **Produkter (Supply Chain Management till Sales) – direkt**.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Field Service-produkter (Supply Chain Management till Field Service).

**Namnen på uppgiften i dataintegreringsprojektet**

- Produkter - produkter

Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** inkluderar en mappning som inte inkluderas i mallen **Produkter (Supply Chain Management till Sales) – direkt**. Den här mappningen säkerställer att det fältservicespecifika fältet **Produkttyp för service** är korrekt inställt.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Följande värdemappning används.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

I Supply Chain Management beräknas värdet för **Produkttyp för fältservice** på dataentiteten **Säljbara frisläppta produkter** på följande sätt:

- **Lager:** produkttyp = produkt- och modellgrupp, produkt i lager = True
- **Ej lagerartikel:** produkttyp = produkt- och modellgrupp, produkt i lager = False
- **Service:** Produkttyp = Service

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Field Service-produkter (Supply Chain Management till Field Service): produkter - produkter.

[![Mallmappning i dataintegrering.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]