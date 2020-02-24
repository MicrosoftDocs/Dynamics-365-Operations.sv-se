---
title: Integrerat leverantörshuvud
description: I det här avsnittet beskriver integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2442a6869daac22a435c1a7504b93ea4b5c14747
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020014"
---
# <a name="integrated-vendor-master"></a>Integrerat leverantörshuvud

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Termen *leverantör* hänvisar till en leverantörsorganisation eller en enskild firma som är en del av leveranskedjeprocessen och som levererar varor för verksamheten. Även om *leverantören* är ett etablerat koncept i Finance and Operations-appar finns inget leverantörskoncept i andra Dynamics 365-appar. I stället överbelastar vissa företag kontoentiteten för att lagra både kundinformation och leverantörsinformation. Andra företag använder ett anpassat leverantörskoncept. Common Data Service-integrationen stöder båda dessa konstruktioner. Därför kan du aktivera någon av konstruktionerna, beroende på ditt affärsscenario.

Integrering av leverantörsdata mellan Finance and Operations-appar och andra Dynamics 365-appar gör att du kan hantera flera data. Oavsett var leverantörsdata har sitt ursprung integreras den bakom kulisserna i programgränser och infrastrukturskillnader. 

### <a name="vendor-data-flow"></a>Leveranstörsdataflöde

Om du vill använda Dynamics 365-appar för leverantörshantering och vill isolera leverantörsinformation från kundinformationen kan du använda den nya leverantörsdesignen.

![Leveranstörsdataflöde](media/dual-write-vendor-data-flow.png)

Om du vill använda andra Dynamics 365-appar för leverantörshantering och vill fortsätta använda kontoentiteten för att lagra leverantörsinformationen kan du använda den nya utökade leverantörsdesignen. I den här designen lagras utökad leverantörsinformation, till exempel leverantörsgrupp och leverantörsbokföringsprofil, i leverantörsdetaljerna.

![Utökat leveranstörsdataflöde](media/dual-write-vendor-detail.jpg)

Leverantörens kontaktinformation liknar kundens kontaktinformation. Bakom kulisserna lagras kontaktpersonens information och hämtas från samma entiteter.

## <a name="templates"></a>Mallar

Leverantörsdata innehåller all information om leverantören, till exempel leverantörsgruppen, adresser, kontaktinformation, betalningsprofil och fakturaprofil. En samling entitetsmappningar fungerar tillsammans under leverantörsdatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar         | Beskrivning
----------------------------|---------------------------------|------------
Leverantör V2               | Konto | Företag som använder kontoentiteten för att lagra leverantörsinformation kan fortsätta att använda den på samma sätt. De kan också dra nytta av de explicita leverantörsfunktioner som kommer på grund av Finance and Operations-appintegrering.
Leverantör V2               | Msdyn\_vendors | Företag som använder en anpassad lösning för leverantörer kan dra nytta av det färdiga leverantörskoncept som introduceras i Common Data Service på grund av Finance and Operations-appintegrering. 
Leverantörsgrupper | msdyn_vendorgroups | Den här mallen synkroniserar leverantörsgruppinformation.
Betalningsmetod för leverantör | msdyn_vendorpaymentmethods | Den här mallen synkroniserar information om leverantörsbetalningsmetod.
CDS-kontakter V2             | kontakter                        | Mallen [Kontakter](customer-mapping.md#cds-contacts-v2-to-contacts) synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
Betalningsplanrader      | msdyn_paymentschedulelines      | Mallen [betalningsplanrader](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synkroniserar referensdata för kunder och leverantörer.
Betalningsplan            | msdyn_paymentschedules          | Mallen [betalningsplaner](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synkroniserar referensdata för betalningsplaner för både kunder och leverantörer.
Betalningsdagsrader – CDS V2    | msdyn_paymentdaylines           | Mallen [betalningsdagsrader](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synkroniserar referensdata för betalningsdagsrader för kunder och leverantörer.
Betalningsdagar – CDS            | msdyn_paymentdays               | Mallen [betalningsdagar](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
Betalningsvillkor            | msdyn_paymentterms              | Mallen [betalningsvillkor](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.
Namnaffix                | msdyn_nameaffixes               | Mallen [namnaffix](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synkroniserar referensdata för namnaffix för både kunder och leverantörer.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
