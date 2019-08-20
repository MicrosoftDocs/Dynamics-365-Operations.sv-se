---
title: Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service
description: Det här avsnittet anger ordningen för synkroniseringen som du måste följa för att skapa de ursprungliga data.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797308"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service

Innan du använder dataintegrering måste du skapa de ursprungliga data som krävs för kunder, leverantörer och kontakter. Om du till exempel vill skapa en ny artikel för **leverantörsgrupp** och ange dess **betalningsvillkor** som **Net30**, innan du försöker skapa artikeln **leverantörsgrupp** se till att **Net30** finns i både Finance and Operations och Common Data Service. (I framtiden kommer vi att släppa en funktion för dubbel skrivplattform som kallas **initial synkronisering**. Den kommer att göra en engångsdatasynkronisering mellan Finance and Operations och Common Data Service som en del av dubbel skriv-installationen.)

Tips: vi släpper en dubbel-skriv-karta för alla referensdata inklusive **betalningsvillkor** (betalningsvillkor). Om du redan har de ursprungliga data i ett system kan en liten uppdateringsåtgärd på en post utlösa dubbel-skriv på posten. 

Du måste följa följande prioritetsordning och kontrollera att de ursprungliga data är tillgängliga på både Finance and Operations och Common Data Service.   

## <a name="vendor"></a>Leverantör

Orderutförande för leverantör är:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Kund (organisation)

Orderutförande för kund är:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Kontakt (person)

Orderutförande för kontakt är:

```
Customer
Vendor               
```
