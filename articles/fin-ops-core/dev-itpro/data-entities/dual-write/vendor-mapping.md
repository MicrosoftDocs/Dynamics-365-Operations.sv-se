---
title: Integrerat leverantörshuvud
description: I den här artikeln beskrivs integreringen av leverantörsdata mellan appar för ekonomi och drift och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a2c32ef546a5bc74e090591c0ac9d51529299041
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112215"
---
# <a name="integrated-vendor-master"></a>Integrerat leverantörshuvud

[!include [banner](../../includes/banner.md)]



Termen *leverantör* avser en leverantörs organisation, eller en enskild person som levererar varor eller tjänster till ett företag. Även om *leverantören* är ett etablerat koncept i Microsoft Dynamics 365 Supply Chain Management inget leverantörskoncept finns i kundengagemangsappar. Du kan dock överlagra tabellen **konto/kontakt** för att lagra leverantörsinformation. Den integrerade leverantörsmästaren introducerar ett uttryckligt leverantörskoncept i kundengagemangsappar. Du kan antingen använda den nya leverantörsdesignen eller lagra leverantörsdata i tabellen **konto/kontakt**. Båda metoderna stöds av dubbelriktad skrivning.

I båda metoderna är leverantörsdata integrerad mellan Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service och Power Apps-portaler. I Supply Chain Management är data tillgängliga för arbetsflöden som inköpsrekvisitioner och inköpsorder.

## <a name="vendor-data-flow"></a>Leveranstörsdataflöde

Om du inte vill lagra leverantörsdata i tabellen **konto/kontakt** i Dataverse, kan du använda den nya leverantörsdesignen.

![Leveranstörsdataflöde.](media/dual-write-vendor-data-flow.png)

Om du vill fortsätta lagra leverantörsdata i tabellen **konto/kontakt** kan du använda den utökade leverantörsdesignen. Om du vill använda den utökade leverantörsdesignen måste du konfigurera leverantörsarbetsflödena i lösningspaketet för dubbelriktad skrivning. Mer information finns i [Växla mellan leverantörsdesigner](vendor-switch.md).

![Utökat leveranstörsdataflöde.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Om du använder Power Apps-portaler för självbetjäningsleverantörer kan leverantörsinformationen flöda direkt till appar för ekonomi och drift.

## <a name="templates"></a>Mallar

Leverantörsdata innehåller all information om leverantören, till exempel leverantörsgruppen, adresser, kontaktinformation, betalningsprofil och fakturaprofil. En samling tabellmappningar fungerar tillsammans under leverantörsdatainteraktion, som visas i följande tabell.

Appar för ekonomi och drift | Kundengagemangsappar     | beskrivning
----------------------------|-----------------------------|------------
[CDS-kontakter V2](mapping-reference.md#115) | kontakter | Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
[Namnaffix](mapping-reference.md#155) | msdyn_nameaffixes | Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.
[Betalningsdagsrader – CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.
[Betalningsdagar – CDS](mapping-reference.md#158) | msdyn_paymentdays | Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
[Betalningsplanrader](mapping-reference.md#159) | msdyn_paymentschedulelines | Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.
[Betalningsplan](mapping-reference.md#160) | msdyn_paymentschedules | Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.
[Betalningsvillkor](mapping-reference.md#161) | msdyn_paymentterms | Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.
[Leverantörer V2](mapping-reference.md#202) | msdyn_vendors | Företag som använder en anpassad lösning för leverantörer kan dra nytta av det färdiga leverantörskoncept som introduceras i Dataverse på grund av integreringen av appar för Ekonomi och drift.
[Leverantörsgrupper](mapping-reference.md#200) | msdyn_vendorgroups | Den här mallen synkroniserar leverantörsgruppinformation.
[Betalningsmetod för leverantör](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Den här mallen synkroniserar information om leverantörsbetalningsmetod.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

