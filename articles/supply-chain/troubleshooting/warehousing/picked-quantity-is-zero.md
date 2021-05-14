---
title: Du kan inte bekräfta en leverans eftersom kvantiteten är noll
description: Du kan inte bekräfta en leverans eftersom kvantiteten är noll
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938552"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Du kan inte bekräfta en leverans eftersom kvantiteten är noll

Felkod: LoadLineArbetsbelastningningUpdatedToZero

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Beläggningsraden för artikel %1 och leveransen %2 har uppdaterats till noll kvantitet på grund av underleveranskonfigurationen som inte tillåter leverans av någon kvantitet för den här artikeln.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Systemet utvärderar om den plockade kvantiteten ligger inom de förväntade gränserna, baserat på plockad kvantitet, beläggningsradkvantitet och underleveransprocent. Om systemet finner att den plockade kvantiteten på beläggningsraden är 0 (noll) kan du inte bekräfta försändelsen. Detta problem kan till exempel uppstå om arbete har avbrutits och procentsatsen för underleverans på beläggningsraden är 100 procent.

## <a name="resolution"></a>Upplösning

Kontrollera beläggningsraderna för att se till att procentsatsen och kvantiteterna för underleverans stämmer överens med det plockade arbetet.

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** markerar du beläggningsraden för den artikel som överskrider underleveransprocenten.
1. Justera värdet i fältet **Underleverans** **Kvantitet** efter behov.

> [!TIP]
> Om problemet består måste du kanske slutföra mer plockningsarbete för relaterade försäljningsorder eller överföringsorder tills den tillgängliga kvantiteten stämmer överens med beläggningen eller försändelsen.
