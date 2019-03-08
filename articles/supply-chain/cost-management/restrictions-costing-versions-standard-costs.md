---
title: Begränsningar för kostnadsversioner av standardkostnader
description: Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0383f78ea5cfa42183e0bfe8a96d7d3866766e7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "309804"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Begränsningar för kostnadsversioner av standardkostnader

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader. 

Följande restriktionerna ser till att standardkostnadsprinciperna efterlevs:

-  Avgifter måste inkluderas i en artikels kostnad. Avgifterna för en tillverkad artikel representerar de amorterade konstanta kostnaderna i strukturliste- och flödesinformationen. Avgifterna måste därför inkluderas i enhetskostnaden. Avgifterna för en inköpt artikel ska också inkluderas i artikelns enhetskostnad.

-  Beräkningen av standardkostnader för tillverkade artiklar måste baseras på kostnadsposterna i en kostnadsversion för standardkostnader. Alternativa källor till kostnadsdata kan bara användas med en kostnadsversion för planerade kostnader, till exempel handelsavtal för inköpspris för inköpta artiklar. Alternativa källor till kostnadsdata definieras av strukturlisteberäkningsgruppen.

-  Strukturlisteberäkningar måste utföras i ett läge med en enda nivå.

Artikelkostnadsdata för standardkostnader kan kopieras till en annan kostnadsversion som innehåller standardkostnader eller planerade kostnader. Artikelkostnadsdata för planerade kostnader kan emellertid inte kopieras till en kostnadsversion som innehåller standardkostnader, eftersom restriktionerna som beskrivits tidigare i det här avsnittet inte gäller för planerade kostnader.

<a name="related-topics"></a>Relaterade ämnen
--------

[Kostnadsversioner](costing-versions.md)

[Uppdatering av standardkostnader i en icke-tillverkningsmiljö](update-standard-costs-non-manufacturing-environment.md)

[Förbereda underhåll av standardkostnader för tillverkade artiklar](update-standard-costs-manufacturing-environment.md)

