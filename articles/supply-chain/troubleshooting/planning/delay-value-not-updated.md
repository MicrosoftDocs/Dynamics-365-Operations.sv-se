---
title: Fördröjningsvärdet uppdateras inte när du omplanerar en planerad order
description: Fördröjningsvärdet uppdateras inte när du omplanerar en planerad order
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 566702913774cf002ab38e367f690a479d968657
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477655"
---
# <a name="the-delay-value-isnt-updated-when-you-reschedule-a-planned-order"></a>Fördröjningsvärdet uppdateras inte när du omplanerar en planerad order

## <a name="symptoms"></a>Symtom

Fördröjningsvärdet uppdateras inte när du omplanerar en planerad order.

## <a name="resolution"></a>Lösning

Om du vill uppdatera fördröjningen för planerade order öppnar du dialogrutan **Omplanering** för den planerade ordern. På snabbfliken **Nedbrytning** ser du till att alternativet **Utför explosion efter omplanering** anges till *Ja*.
