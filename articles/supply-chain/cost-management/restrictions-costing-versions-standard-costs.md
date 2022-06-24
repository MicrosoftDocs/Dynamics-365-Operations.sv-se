---
title: Begränsningar för kostnadsversioner av standardkostnader
description: Denna artikel beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader.
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
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867997"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Begränsningar för kostnadsversioner av standardkostnader

[!include [banner](../includes/banner.md)]

Denna artikel beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader. 

Följande restriktionerna ser till att standardkostnadsprinciperna efterlevs:

-  Avgifter måste inkluderas i en artikels kostnad. Avgifterna för en tillverkad artikel representerar de amorterade konstanta kostnaderna i strukturliste- och flödesinformationen. Avgifterna måste därför inkluderas i enhetskostnaden. Avgifterna för en inköpt artikel ska också inkluderas i artikelns enhetskostnad.

-  Beräkningen av standardkostnader för tillverkade artiklar måste baseras på kostnadsposterna i en kostnadsversion för standardkostnader. Alternativa källor till kostnadsdata kan bara användas med en kostnadsversion för planerade kostnader, till exempel handelsavtal för inköpspris för inköpta artiklar. Alternativa källor till kostnadsdata definieras av strukturlisteberäkningsgruppen.

-  Strukturlisteberäkningar måste utföras i ett läge med en enda nivå.

Artikelkostnadsdata för standardkostnader kan kopieras till en annan kostnadsversion som innehåller standardkostnader eller planerade kostnader. Artikelkostnadsdata för planerade kostnader kan emellertid inte kopieras till en kostnadsversion som innehåller standardkostnader, detta eftersom restriktionerna som beskrivits tidigare i denna artikel inte gäller för planerade kostnader.

## <a name="related-articles"></a>Relaterade artiklar

[Översikt över kostnadsversioner](costing-versions.md)

[Uppdatera standardkostnader i en icke-tillverkningsmiljö](update-standard-costs-non-manufacturing-environment.md)

[Förbereda underhåll av standardkostnader för tillverkade artiklar](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]