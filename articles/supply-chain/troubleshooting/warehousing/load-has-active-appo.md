---
title: Du kan inte bekräfta en leverans på grund av ett problem med kalendern.
description: Du kan inte bekräfta en leverans på grund av ett problem med kalendern.
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8aae45beeef1934760d620874897f46a1cf901995e2b83e148a1d56898d9c717
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735954"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Du kan inte bekräfta en leverans på grund av ett problem med kalendern.

Felkod: TRX2716

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Kalendertypen %1 kräver att mötet %2 checkas in och ut.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Aktiva möten för beläggningen finns. Det finns till exempel en regel som säger att förarna måste checka in. Därför befinner sig beläggningen i ett skick där leveransbekräftelsen misslyckas.

## <a name="resolution"></a>Upplösning

Du måste undersöka och åtgärda eventuella problem med de aktiva möten som är kopplade till beläggningen.

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. I åtgärdsfönstret, på fliken **Transport**, i gruppen **Möten**, väljer du **Transportplanering**.
1. Gör något av följande:

    - Kontrollera att förarens in-/utcheckning slutförs för det här mötet.
    - Fyll i eller annullera mötet.
    - Inaktivera alternativet **Förarincheckning krävs** för den relaterade mötesregeln.
