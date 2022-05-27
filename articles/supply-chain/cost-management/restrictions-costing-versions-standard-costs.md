---
title: Begränsningar för kostnadsversioner av standardkostnader
description: Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11bf14b2926fd4ff053697bef8b7dad781948a2c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672218"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Begränsningar för kostnadsversioner av standardkostnader

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader. 

Följande restriktionerna ser till att standardkostnadsprinciperna efterlevs:

-  Avgifter måste inkluderas i en artikels kostnad. Avgifterna för en tillverkad artikel representerar de amorterade konstanta kostnaderna i strukturliste- och flödesinformationen. Avgifterna måste därför inkluderas i enhetskostnaden. Avgifterna för en inköpt artikel ska också inkluderas i artikelns enhetskostnad.

-  Beräkningen av standardkostnader för tillverkade artiklar måste baseras på kostnadsposterna i en kostnadsversion för standardkostnader. Alternativa källor till kostnadsdata kan bara användas med en kostnadsversion för planerade kostnader, till exempel handelsavtal för inköpspris för inköpta artiklar. Alternativa källor till kostnadsdata definieras av strukturlisteberäkningsgruppen.

-  Strukturlisteberäkningar måste utföras i ett läge med en enda nivå.

Artikelkostnadsdata för standardkostnader kan kopieras till en annan kostnadsversion som innehåller standardkostnader eller planerade kostnader. Artikelkostnadsdata för planerade kostnader kan emellertid inte kopieras till en kostnadsversion som innehåller standardkostnader, eftersom restriktionerna som beskrivits tidigare i det här avsnittet inte gäller för planerade kostnader.

## <a name="related-topics"></a>Relaterade ämnen

[Översikt över kostnadsversioner](costing-versions.md)

[Uppdatera standardkostnader i en icke-tillverkningsmiljö](update-standard-costs-non-manufacturing-environment.md)

[Förbereda underhåll av standardkostnader för tillverkade artiklar](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]