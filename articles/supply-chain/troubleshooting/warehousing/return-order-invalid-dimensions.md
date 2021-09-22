---
title: Det går inte att skapa lastrad på grund av ogiltiga lagerdimensioner
description: När du försöker frisläppa en returförsäljningsorder till lagerstället kan det visas ett felmeddelande om ogiltiga lagerdimensioner. Ta bort dessa från orderraden.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac58
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cb728f6a989cdac63c91d49baaea094bace59e4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477648"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Det går inte att skapa lastrad för returförsäljningsorder på grund av ogiltiga lagerdimensioner

## <a name="symptoms"></a>Symtom

Följande felmeddelande visas när du försöker frisläppa en returförsäljningsorder till lagerstället:

> Du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga. Du kan inte referera lagerdimensioner som finns under platsdimensionen i den här reservationshierarkin. Ta bort de ogiltiga dimensionerna från orderraden.

## <a name="resolution"></a>Lösning

Tyvärr har produkten inte stöd för lastbearbetning för en försäljningsreturprocess. Därför kan du inte frisläppa returförsäljningsordern till lagerstället.

På försäljningsordertransaktioner kan du inte referera till lagerdimensioner som ligger under dimensionen **Plats** i reservationshierarkin. Upplösningen är att ta bort ogiltiga dimensioner från orderraden.
