---
title: Utvärdera alla åtgärder för platsdirektiv för flera SKU:er
description: En ny funktion har lagts till för att utvärdera alla åtgärder för platsdirektiv med flera SKU:er. På den här sidan får du information om hur du aktiverar den.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477615"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Flera SKU-alternativ utvärderar inte flera platsdirektivåtgärder

## <a name="symptoms"></a>Symtom

Plats direktiv av typen arbetsorder *försäljningsorder* och arbetstypen *Placera* utvärderar inte flera lokaliseringsdirektivåtgärder när alternativet **Flera SKU-enheter** är valt. Endast den första åtgärden i platsdirektivets utvärderas.

## <a name="resolution"></a>Lösning

En ny funktion *Utvärdera alla åtgärder för platsdirektiv med flera SKU-enheter* har lagts till i version 10.0.15 (se [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Den här funktionen utvärderar alla åtgärder för platsdirektiv med flera SKU-enheter. Om du vill ha denna funktion använd [funktionshantering](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) för att aktivera den.
