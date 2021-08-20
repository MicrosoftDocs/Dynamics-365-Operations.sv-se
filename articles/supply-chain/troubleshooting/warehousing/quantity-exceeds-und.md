---
title: Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för underleverans
description: Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för underleverans
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a6a5b1140d1bc5d09a1bc582fb1d2ac9446fae0920cbb9957797dbdea4c684e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760332"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för underleverans

Felkod: WAX1686

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Försändelsen för beläggning %1 har inte bekräftats eftersom kvantiteten för artikeln %2 överskrider procenttalet som har definierats för underleverans.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Kvantiteten för beläggningen eller leveransen har bara delvis plockats. Kvantiteten underskrider för närvarande den plockade kvantiteten med en procentsats som ligger utanför den tillåtna underleveransprocenten.

## <a name="resolution"></a>Upplösning

Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Ställ in kvantiteten för beläggningsrad.
- Ange procentsats för underleverans.

### <a name="set-the-load-line-quantity"></a>Ställ in kvantiteten för beläggningsrad

Gör på följande sätt om du vill ställa in kvantitet för beläggningsrad:

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** markerar du beläggningsraden för den artikel som överskrider underleveransprocenten.
1. På snabbfliken **Radinformation** väljer du **Order**.
1. I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att försändelsebekräftelse kan ske.

### <a name="set-the-underdelivery-percentage"></a>Ange procentsats för underleverans

Gör på följande sätt om du vill ställa in procentsats för underleverans:

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** markerar du beläggningsraden för den artikel som överskrider underleveransprocenten.
1. På snabbfliken **Radinformation** väljer du **Allmänt**.
1. I fältet **Underleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot beläggningskvantiteten, detta så att leveransbekräftelse kan ske.
