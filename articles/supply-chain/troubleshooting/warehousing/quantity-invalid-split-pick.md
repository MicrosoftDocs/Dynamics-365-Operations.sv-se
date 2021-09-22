---
title: Kvantitet inte giltig för enheten %1 när delad plockning utförs
description: När du utför en uppdelad plockning över flera batcher kan ett felmeddelande visas om att kvantiteten inte gäller för %1 enhet. Den här sidan hjälper till att lösa problemet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4627db7400d6ccd81f25f100de4696058ce35c42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477589"
---
# <a name="quantity-is-not-valid-when-performing-a-split-pick-across-multiple-batches"></a>Kvantitet inte giltig när delad plockning mellan flera batchar utförs

## <a name="symptoms"></a>Symtom

Det här felmeddelandet visas när du försöker göra en *delad plockning* i flera batchar.

> Kvantiteten är ogiltig för enheten %1.

## <a name="resolution"></a>Lösning

Lagerarbetaren måste använda en process *kort plockning* i Warehouse Management-mobilappen. Om du försöker att plocka flera batchar från samma plats kan du även använda alternativet **fullständig** i appen.
