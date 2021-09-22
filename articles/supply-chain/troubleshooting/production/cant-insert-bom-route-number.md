---
title: Det går inte att infoga aktiv version av strukturliste- och flödesnummer
description: Om standardplatsen och standardlagerstället redan har definierats för en vald produkt kommer du inte att uppmanas att infoga den aktiva versionen av strukturliste- och flödesnummer.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477585"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Det går inte att infoga strukturlista och flöde när du skapar en ny produktionsorder

## <a name="symptoms"></a>Symtom

När du skapar en ny produktionsorder, efter att du har angett artikelnumret, kommer **Webbplats** och **Distributionslager** ställs automatiskt in till standardwebbplatsen och lagret som definieras på sidan **Standardorderinställningar** för färdig varuartikel. Dessutom anges det aktiva strukturlistenumret och flödesnumret automatiskt, så du får inte följande meddelande som frågar dig om dessa värden:

> Vill du infoga aktiv version för strukturlista och flöde?

## <a name="resolution"></a>Lösning

Du uppmanas inte att infoga strukturliste- och flödesnummer om du väljer en produkt som en webbplats och ett lagerställe har definierats för på sidan **Standardorderinställningar**. Du får bara en fråga om dessa värden inte har definierats för den valda produkten.
