---
title: Plockningsarbete spärrat på grund av oavslutat lagerpåfyllnadsarbete
description: Plockningsarbetet kan spärras på grund av beroende lagerpåfyllnadsarbete. Slutför lagerpåfyllnadsarbetet och bearbeta sedan plockningsarbetet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477678"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>Plockningsarbetet kan frisättas på grund av oavslutat lagerpåfyllnadsarbete.

## <a name="symptoms"></a>Symtom

När du använder begäranspåfyllning kan plockningsarbete spärras på grund av beroende lagerpåfyllnadsarbete. Om en plockplats måste fyllas på skapar systemet både påfyllningsarbetet och plockningsarbetet för att uppfylla källorderns behov. Det spärrar dock plockningsarbetet tills lagerpåfyllnadsarbetet är slutfört och du får följande felmeddelande:

> Det går inte att ta bort spärren från arbetsuppgiften %1 eftersom den innehåller icke avslutat lagerpåfyllnadsarbete.

## <a name="resolution"></a>Lösning

Det här beteendet är avsiktligt eftersom plockplatsen inte har tillräckligt med lager om inte lagerpåfyllnadsarbetet har slutförts. Slutför lagerpåfyllnadsarbetet och bearbeta sedan plockningsarbetet.
