---
title: Leverans för last har bekräftats men inga rader har bokförts
description: Försändelsebekräftelse påverkar inte bokföring. Den uppdaterar bara försändelsen och laststatus. Bokföring måste ske i en separat process.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e754f1461672c1e9f2d8dd1a7ceffc81f3809120
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477667"
---
# <a name="shipment-for-load-has-been-confirmed-but-no-lines-are-posted"></a>Leverans för last har bekräftats men inga rader har bokförts

## <a name="symptoms"></a>Symtom

När du arbetar med utgående lagerställeåtgärder kan följande meddelande visas:

> Leveransen för last 1% har bekräftats.

Ingen ytterligare bokföring inträffade.

## <a name="resolution"></a>Lösning

Detta är av design. Försändelsebekräftelse påverkar inte bokföring. Den uppdaterar bara försändelsen och laststatus. Bokföring måste ske i en separat process.
