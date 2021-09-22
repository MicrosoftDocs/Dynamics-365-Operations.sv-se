---
title: Tillverkningsorder visas inte på sidan Markering
description: Vissa tillverkningsorder visas inte på markeringssidan. I det här ämnet beskrivs de tre produktkonfigurationerna som inte är tillgängliga för markering.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477578"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>Tillverkningsorder visas inte på sidan Markering

## <a name="symptoms"></a>Symtom

När du arbetar med diskret tillverkning visas inte vissa produktionsorder på sidan **Markering**.

## <a name="resolution"></a>Lösning

Produkter som har följande konfigurationer är inte tillgängliga för markering. Därför visas de inte på **markeringssidan**:

- Produkterna definieras som produkter av typen *faktisk/nominell vikt*.
- De aktiveras för de avancerade lagerprocesserna.
- De konfigureras för kontroll med principen för *standardkostnad*.
