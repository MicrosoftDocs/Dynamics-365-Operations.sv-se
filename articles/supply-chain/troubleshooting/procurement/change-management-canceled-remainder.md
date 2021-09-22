---
title: Annullerad leveransrest flyttar inköpsordern till ett bekräftat tillstånd
description: Om en leveransrest annulleras på en inköpsorder där ändringshantering har aktiverats, skickas inköpsordern till ett bekräftat tillstånd.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477644"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>Annullerad leveransrest flyttar inköpsordern till ett bekräftat tillstånd

## <a name="symptoms"></a>Symtom

För en inköpsorder som är föremål för ändringshantering, om den enda ändringen som begärs är annulleringen av en leverans som rest på en eller flera av raderna, skickas inköpsordern direkt till ett tillstånd *bekräftat* när den godkänns och ingen journal skapas.

## <a name="resolution"></a>Lösning

Annullering av en leveranspåminnelse påverkar inte innehållet i bekräftelsejournalen. Den här funktionen ska användas när raden har inlevererats delvis och den resterande kvaliteten ska annulleras i processteg efter det att inköpsordern har bekräftats med leverantören.

Om detta ska avspeglas på inköpsorderbekräftelsen ska kvantiteten justeras på inköpsorderraden så att bekräftelsen blir nödvändig. Om inget har mottagits på raden kan du ta bort kvantiteten. I det här fallet krävs en ombekräftelse.
