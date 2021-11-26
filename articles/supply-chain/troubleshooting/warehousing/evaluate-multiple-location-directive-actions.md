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
ms.openlocfilehash: ea265166902f85c2c09cae08ee6de5cd7094e1b4
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778412"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Flera SKU-alternativ utvärderar inte flera platsdirektivåtgärder

## <a name="symptoms"></a>Symtom

Plats direktiv av typen arbetsorder *försäljningsorder* och arbetstypen *Placera* utvärderar inte flera lokaliseringsdirektivåtgärder när alternativet **Flera SKU-enheter** är valt. Endast den första åtgärden i platsdirektivets utvärderas.

## <a name="resolution"></a>Lösning

En ny funktion *Utvärdera alla åtgärder för platsdirektiv med flera SKU-enheter* har lagts till i version 10.0.15 (se [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Den här funktionen utvärderar alla åtgärder för platsdirektiv med flera SKU-enheter. Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan använda sidan [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera/inaktivera den vid behov.
