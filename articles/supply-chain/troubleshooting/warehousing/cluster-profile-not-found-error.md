---
title: Det gick inte att hitta klusterprofil
description: När du arbetar med inkommande lagerställeåtgärder kan du få ett felmeddelande om att klusterprofilen inte kan hittas. Kontrollera att klusterprofilerna är korrekt inställda.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477676"
---
# <a name="cluster-profile-cant-be-found"></a>Det går inte att hitta klusterprofil

## <a name="symptoms"></a>Symtom

När du arbetar med inkommande lagerställeåtgärder kan följande felmeddelande visas:

> "Kvalitetsordern %1 har genererats. Det gick inte att hitta klusterprofil. Kontrollera konfigurationen."

Det här felmeddelandet är relaterat till en mottagningsprocess där kvalitetshantering (QMS) aktiveras. Beroende på konfigurationerna i din miljö kan ytterligare information om transaktionen som genererar felmeddelandet hjälpa till att åtgärda problemet.

## <a name="resolution"></a>Lösning

Granska först inställningar för klusterplockning och kontrollera att dina klusterprofiler är korrekt inställda. Du kan inte använda en menyartikel för mobila enheter för klusterplockning om inte klusterprofiler har ställts in. Beroende på din miljö kan du också behöva granska andra relaterade konfigurationer.
