---
title: Det går inte att skapa lastrad på grund av ogiltiga lagerdimensioner
description: När du försöker frisläppa en returförsäljningsorder till lagerstället kan det visas ett felmeddelande om ogiltiga lagerdimensioner. Ta bort dessa från orderraden.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119222"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Det går inte att skapa lastrad för returförsäljningsorder på grund av ogiltiga lagerdimensioner

## <a name="symptoms"></a>Symtom

Följande felmeddelande visas när du försöker frisläppa en returförsäljningsorder till lagerstället:

> Du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga. Du kan inte referera lagerdimensioner som finns under platsdimensionen i den här reservationshierarkin. Ta bort de ogiltiga dimensionerna från orderraden.

## <a name="resolution"></a>Lösning

Tyvärr har produkten inte stöd för lastbearbetning för en försäljningsreturprocess. Därför kan du inte frisläppa returförsäljningsordern till lagerstället.

På försäljningsordertransaktioner kan du inte referera till lagerdimensioner som ligger under dimensionen **Plats** i reservationshierarkin. Upplösningen är att ta bort ogiltiga dimensioner från orderraden.
