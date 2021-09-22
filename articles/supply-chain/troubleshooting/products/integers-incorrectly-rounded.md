---
title: Heltal avrundas felaktigt i beräkningar av produktkonfigurationsmodeller
description: Heltalsresultat avrundas felaktigt ibland när produktkonfigurationsmodeller beräknas. Korrigera problemet med ett tillagt decimalattribut och en beräkning.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477651"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Heltal avrundas felaktigt när produktkonfigurationsmodeller beräknas

## <a name="symptoms"></a>Symtom

Det här problemet kan uppstå när du utför följande serie åtgärder:

1. Ställ in dessa attribut i en produktionskonfigurationsmodell:

    - Indata (heltal)
    - Procent (decimal)
    - Resultat (heltal)

2. Skapa en beräkning som har följande uttryck:

    *Resultat* = *indata* × *procent* ÷ 100

I det här fallet har heltalsresultatet inte alltid avrundats korrekt. Om indata till exempel är 1 000 och procentandelen är 2,40 väntar du dig att heltalsresultatet blir 24 eftersom 2,40 procent av 1 000 är 24 (eller 24,00 i decimalform). I stället visas resultatet 23. När procentsatsen är 2,39 avrundas dock beräkningen till 24 i stället för 23. När procentsatsen är 2,50 avrundas beräkningen till 25, som förväntat.

## <a name="cause"></a>Orsak

Det här problemet beror på det sätt som Microsoft Solver Foundation internt representerar tal genom att använda bråktal. I föregående exempel representeras resultatet av beräkningen där procentsatsen är 2,40 som 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375. När .NET skickar det här värdet som ett heltal returneras 23.

## <a name="resolution"></a>Lösning

Det här beteendet ändras inte eftersom andra scenarier är beroende av det. I föregående exempel kan du åtgärda problemet genom att införa ytterligare ett decimalattribut och beräkningar.

Konfigurera till exempel följande attribut i en produktionskonfigurationsmodell:

- Indata (heltal)
- Procent (decimal)
- ResultDecimal (decimal)
- ResultInteger (heltal)

Du kan sedan lägga till följande beräkningar:

- *ResultDecimal* = *Indata* × *Procent* ÷ 100
- *ResultInteger* = *ResultDecimal*
