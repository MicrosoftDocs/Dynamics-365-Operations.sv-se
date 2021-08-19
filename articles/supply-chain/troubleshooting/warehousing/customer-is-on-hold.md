---
title: Du kan inte bekräfta en leverans eftersom kunden är spärrad
description: Du kan inte bekräfta en leverans eftersom kunden är spärrad.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 82b28e7cfd8c88e453cdd09398f5a92f605eab15a17d33defa0b9729a53c05b6
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012213"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Du kan inte bekräfta en leverans eftersom kunden är spärrad

Felkod: WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Leveransen %1 kan inte bekräftas eftersom kunden har spärrats för %2.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Kundkontot för lasten eller försändelsen är spärrat. Kundens status förhindrar därmed att leveransen bekräftas.

## <a name="resolution"></a>Lösning

Gör enligt följande för att ta bort spärren från kundkontot.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Öppna kundkontot som leveransen inte kan bekräftas för.
1. Ställ in fältet **Spärrad fakturering och leverans** på snabbfliken **Kredit och inkasso** som *Nej*.
1. Upprepa proceduren för alla spärrade kunder för lasten.
