---
title: Kvantitet på en startad karantänorder uppdateras inte när ordern delas upp
description: När du skapar en karantänorder och försöker dela den uppdateras inte orderkvantiteten till den uppdelade resterande kvantiteten.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026928"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>Kvantitet på en startad karantänorder uppdateras inte när ordern delas upp

KB-nummer: 4613113

## <a name="symptoms"></a>Symtom

När du skapar en karantänorder och försöker dela den uppdateras inte orderkvantiteten till den resterande kvantiteten efter uppdelningen.

## <a name="resolution"></a>Upplösning

Systemet ändrar inte den ursprungliga kvantiteten från en karantänorder för att säkerställa att du kan spåra den ursprungliga kvantiteten som skapades för karantänordern. Systemet spårar dock den kvantitet som delas upp från en karantänorder. För att spåra använder den ett databasfält med namnet `QuantityThatHasSplitIntoOtherQuarantineOrders`. Det här fältet visas dock inte i användargränssnittet (UI).
