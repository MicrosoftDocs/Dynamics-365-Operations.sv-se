---
title: Det går inte att ta bort en frisläppt produkt
description: Du kan bara ta bort en frisläppt produkt och alla dess varianter om den frisläppta produkten inte har några relaterade transaktioner.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477664"
---
# <a name="you-cant-delete-a-released-product"></a>Det går inte att ta bort en frisläppt produkt

## <a name="symptoms"></a>Symtom

Du kan bara ta bort en frisläppt produkt och alla dess varianter om den frisläppta produkten inte har några relaterade transaktioner.

## <a name="resolution"></a>Lösning

Följ dessa steg för att ta bort en frisläppt produkt eller produktmall.

1. Stäng alla öppna transaktioner för artiklarna.
1. Minska lagret till 0 (noll).
1. Utför lagerstängning.
1. Radera alla produktvarianter för den produktmall som du vill ta bort.
