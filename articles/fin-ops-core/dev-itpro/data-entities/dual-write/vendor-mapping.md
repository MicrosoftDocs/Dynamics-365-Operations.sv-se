---
title: Integrerat leverantörshuvud
description: I det här avsnittet beskriver integreringen av leverantörsdata mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f2fc88ed0c0f4dbec55f8ca251cca3d071760b55
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744525"
---
# <a name="integrated-vendor-master"></a>Integrerat leverantörshuvud

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Termen *leverantör* avser en leverantörs organisation, eller en enskild person som levererar varor eller tjänster till ett företag. Även om *leverantören* är ett etablerat koncept i Microsoft Dynamics 365 Supply Chain Management inget leverantörskoncept finns i modellstyrda appar i Dynamics 365. Du kan dock överlagra tabellen **konto/kontakt** för att lagra leverantörsinformation. Den integrerade leverantörsmästaren introducerar ett uttryckligt leverantörskoncept i modellstyrda appar i Dynamics 365. Du kan antingen använda den nya leverantörsdesignen eller lagra leverantörsdata i tabellen **konto/kontakt**. Båda metoderna stöds av dubbelriktad skrivning.

I båda metoderna är leverantörsdata integrerad mellan Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service och Power Apps-portaler. I Supply Chain Management är data tillgängliga för arbetsflöden som inköpsrekvisitioner och inköpsorder.

## <a name="vendor-data-flow"></a>Leveranstörsdataflöde

Om du inte vill lagra leverantörsdata i tabellen **konto/kontakt** i Dataverse, kan du använda den nya leverantörsdesignen.

![Leveranstörsdataflöde](media/dual-write-vendor-data-flow.png)

Om du vill fortsätta att lagra leverantörsdata i tabellen **konto/kontakt** kan du använda den utökade leverantörsdesignen. Om du vill använda den utökade leverantörsdesignen måste du konfigurera leverantörsarbetsflödena i lösningspaketet för dubbelriktad skrivning. Mer information finns i [Växla mellan leverantörsdesigner](vendor-switch.md).

![Utökat leveranstörsdataflöde](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Om du använder Power Apps-portaler för självbetjäningsleverantörer kan leverantörsinformationen flöda direkt till Finance and Operations-appar.

## <a name="templates"></a>Mallar

Leverantörsdata innehåller all information om leverantören, till exempel leverantörsgruppen, adresser, kontaktinformation, betalningsprofil och fakturaprofil. En samling tabellmappningar fungerar tillsammans under leverantörsdatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar     | beskrivning
----------------------------|-----------------------------|------------
Leverantör V2                   | Konto                     | Företag som använder kontotabellen för att lagra leverantörsinformation kan fortsätta att använda den på samma sätt. De kan också dra nytta av de explicita leverantörsfunktioner som kommer på grund av Finance and Operations-appintegrering.
Leverantör V2                   | Msdyn\_vendors              | Företag som använder en anpassad lösning för leverantörer kan dra nytta av det färdiga leverantörskoncept som introduceras i Dataverse på grund av Finance and Operations-appintegrering. 
Leverantörsgrupper               | msdyn\_vendorgroups         | Den här mallen synkroniserar leverantörsgruppinformation.
Betalningsmetod för leverantör       | msdyn\_vendorpaymentmethods | Den här mallen synkroniserar information om leverantörsbetalningsmetod.
CDS-kontakter V2             | kontakter                    | Mallen [Kontakter](customer-mapping.md#cds-contacts-v2-to-contacts) synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
Betalningsplanrader      | msdyn\_paymentschedulelines | Mallen [betalningsplanrader](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synkroniserar referensdata för kunder och leverantörer.
Betalningsplan            | msdyn\_paymentschedules     | Mallen [betalningsplaner](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synkroniserar referensdata för betalningsplaner för både kunder och leverantörer.
Betalningsdagsrader – CDS V2    | msdyn\_paymentdaylines      | Mallen [betalningsdagsrader](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synkroniserar referensdata för betalningsdagsrader för kunder och leverantörer.
Betalningsdagar – CDS            | msdyn\_paymentdays          | Mallen [betalningsdagar](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
Betalningsvillkor            | msdyn\_paymentterms         | Mallen [betalningsvillkor](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.
Namnaffix                | msdyn\_nameaffixes          | Mallen [namnaffix](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synkroniserar referensdata för namnaffix för både kunder och leverantörer.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
