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
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938555"
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
