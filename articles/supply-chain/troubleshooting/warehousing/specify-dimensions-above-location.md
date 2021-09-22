---
title: Det går inte att frisläppa en last för delkvantitet med en batch ovan-hierarki
description: När du använder en artikel med batch ovan-reservationshierarkin måste lastrader ange dimensioner ovanför platsen för att lager ska allokeras.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477607"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Det går inte att frisläppa en last för delkvantitet med en batch ovan-reservationshierarki

## <a name="symptoms"></a>Symtom

När du använder ett objekt som har en *batch ovan* bokningshierarki, kommer kommandot **Släppa till distributionslager** på sidan **Workbench för lastplanering** inte att fungera om du försäker släppa en last för en delkvantitet. Följande felmeddelande visas:

> För att tilldelas en påfyllnad måste lastrader ange dimensionerna ovanför platsen. För att tilldela dessa dimensioner, reservera och återskapa lastraden.

Men när du använder ett objekt som har ett *batch under* bokningshierarki, kan du frisläppa en last för en delkvantitet från sidan **Workbench för lastplanering**.

## <a name="cause"></a>Orsak

När en dimension ovanför dimensionen **Plats** i reservationshierarkin måste den anges innan den kan frisläppas till lagerstället. Lagret kan bara allokeras om det inte finns några luckor i dimensionerna ovanför platsen.

## <a name="resolution"></a>Lösning

Kontrollera att alla dimensioner ovanför **Plats** har tilldelats genom att reserveras och återskapa lastraden.
