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
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Synkronisera produkter i Supply Chain Management till produkter i Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

Mallen **Fältserviceprodukter (Supply Chain Management till Field Service)** som används baseras på mallen **Produkter (Supply Chain Management till Sales) – direkt** från potentiell kund till kontanter. Mer information finns i [Produkter (Supply Chain Management till Sales) – direkt](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Det här ämnet beskriver bara skillnaden mellan mallarna **Fältserviceprodukter (Supply Chain Management till Field Service)** och **Produkter (Supply Chain Management till Sales) – direkt**.

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

[![Mallmappning i dataintegrering](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]