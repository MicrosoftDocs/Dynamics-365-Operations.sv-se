---
title: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
description: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938553"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Du kan inte bekräfta en leverans eftersom inga artiklar har plockats

Felkod: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Vissa av de artiklar som behövs för lasten %1 har ännu inte plockats och förflyttats till den slutliga leveransplatsen.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Beläggningen eller leveransen kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:

- Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.
- Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.

## <a name="resolution"></a>Upplösning

Kontrollera relaterade försäljningsorder eller överföringsorder för beläggningen eller leveransen. Se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.
