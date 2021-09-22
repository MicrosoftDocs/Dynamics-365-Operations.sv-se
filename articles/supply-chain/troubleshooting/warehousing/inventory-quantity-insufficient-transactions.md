---
title: Lagerkvantitet inte uppdaterad på grund av otillräckliga transaktioner
description: Lagerkvantitet -1% kan inte uppdateras eftersom det inte finns tillräckligt många lagertransaktioner för artikel %2 med de angivna dimensionerna.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477583"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>Systemet kan inte uppdatera lagerkvantitet på grund av otillräckligt antal transaktioner

## <a name="symptoms"></a>Symtom

Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna. Följande felmeddelande visas:

> Lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikeln %2 med dimensioner Storlek=%3, Färg=%4, Tillägg=%5, Webbplats=%6, Lagerställe=%7, Plats=%8, Lagerstatus=tillgänglig, ID-nummer=%9, Batchnummer=%10 för referens-ID %11 på parti-Lot ID %12.

## <a name="resolution"></a>Lösning

Se till att inga lagertransaktioner fysiskt reserverar kvantiteten. Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.
