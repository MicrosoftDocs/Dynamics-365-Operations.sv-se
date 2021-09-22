---
title: En inleverans för inköpsorder inkluderar inte alla avgifter
description: En inleverans för inköpsorder inkluderar inte alla avgifter
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477590"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>En inleverans för inköpsorder inkluderar inte alla avgifter

## <a name="symptoms"></a>Symtom

När du får en inköpsorder inkluderas inte alla kostnader i inleveransen.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. På sidan **Anskaffnings- och källparametrar** på fliken **Leverans** se till att alternativet **Skapa ändringar i produktinleverans** anges till *Ja*.
1. Skapa en inköpsorder som inkluderar avgifter.
1. Bekräfta inköpsordern.
1. Få en inköpsorder.
1. Granska den totala inleveransen och jämför den med den förväntade totala summan.
1. Lägg märke till att inte alla avgifter tas med i inleveransen för inköpsordern.

## <a name="resolution"></a>Lösning

Lösningen beror på hur tilläggen har ställts in. Information om hur du ställer in tillägg för att uppfylla dina krav finns i följande blogginlägg: [Bokför tillägg vid tiden för produktinleveransen](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
