---
title: Det går inte att bearbeta korrigering av följesedel
description: Om du försöker korrigera en följesedel efter att den bokförts visas ett felmeddelande. På den här sidan förklaras hur du korrigerar bokförda följesedlar för artiklar som aktiverats för WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477658"
---
# <a name="delivery-note-correction-cant-be-processed"></a>Det går inte att bearbeta korrigering av följesedel

## <a name="symptoms"></a>Symtom

När du har bokfört en följesedel kan du inte annullera den eftersom knappen **Avbryt** inte är tillgänglig. Det går inte heller att korrigera följesedeln. Om du försöker följande felmeddelande kan komma att visas:

> Det går inte att bearbeta korrigering av följesedel. Följesedeln innehåller endast artiklar som är föremål för lagerstyrningsprocesser, eftersom dessa inte stöds av korrigering av följesedel.

## <a name="resolution"></a>Lösning

Om du vill korrigera bokförda följesedlar för artiklar som är aktiverade för WMS (avancerad lagerstyrning) måste du utföra bokföringen från lasten, inte direkt från ordern.
