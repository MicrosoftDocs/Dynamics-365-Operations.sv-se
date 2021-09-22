---
title: Det gick inte att frisläppa försäljningsorder med utgående lageråtgärder
description: Det finns flera orsaker till att du får ett felmeddelande om att en försäljningsorder inte kunde frisläppas. På den här sidan beskrivs varför och hur du begränsar problemet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477647"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>Det gick inte att frisläppa försäljningsorder med utgående lageråtgärder

## <a name="symptoms"></a>Symtom

När du arbetar med utgående lagerställeåtgärder kan följande felmeddelande visas:

> Det gick inte att släppa försäljningsordern

## <a name="cause"></a>Orsak

Det här problemet kan uppstå av flera orsaker. Till exempel är ordern i kredithanteringsspärr och inga försändelser kan skapas förrän en giltig postadress anges för alla försäljningsrader som är kopplade till en order. Alternativt finns det ett orderspärr som måste åtgärdas innan ordern kan frisläppas till lagerstället. Det här undantaget kan vara kundspecifikt, eller så kan det finnas på kundkontot.

## <a name="resolution"></a>Lösning

Lägg till eller uppdatera adressen på försäljningsordern och orderraderna och släpp sedan ordern på lagerstället. Order kan bara frisläppas till lagerstället om de har en giltig leveransadress (per adressformats inställningar i modulen **organisationsadministration**).

Undersök orderspärren och åtgärda problemen. Ta sedan bort spärren från ordern eller kunden och släpp ordern på lagerstället.
