---
title: Fel vid kostnadskalkylering med automatisk lageravräkning under lagerstängning
description: I tidigare versioner kan du ha fått en kostnadskalkylering med automatisk lageravräkning under lagerstängningen. Det här problemet har åtgärdats.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477617"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Fel vid kostnadskalkylering med automatisk lageravräkning under lagerstängning

## <a name="symptoms"></a>Symtom

I versioner före release 10.0.13 får du följande felaktiga varningsmeddelande under lagerstängning om du inte använder det lean produktionskostnadsflödet:

> Du utför en lagerstängning med ett datum %1. Ingen kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut har registrerats. Kom ihåg att utföra en kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut. Värderingen av lager, sålda varor och avvikelser kanske inte är korrekt i delredovisning eller redovisning förrän denna har utförts.

## <a name="resolution"></a>Lösning

Det här problemet har korrigerats i version 10.0.13 och senare. Mer information finns i [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
