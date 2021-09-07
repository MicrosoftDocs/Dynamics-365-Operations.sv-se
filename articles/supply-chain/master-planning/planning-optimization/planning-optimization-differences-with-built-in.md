---
title: Skillnader mellan inbyggd huvudplanering och Planeringsoptimering
description: Detta ämne innehåller en lista med funktioner som ännu inte stöds av Planeringsoptimering och som inte visas på analyssidan för Planeringsoptimering.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a102f1d77362f650c060ce5d0aee5b62d2102532
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344964"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Skillnader mellan inbyggd huvudplanering och Planeringsoptimering

[!include [banner](../../includes/banner.md)]

Resultatet från Planeringsoptimering kan skilja sig från resultaten från den inbyggda huvudplaneringsmotorn. Skillnaderna kan också orsakas av kommande funktioner. Detta ämne innehåller en lista med funktioner som ännu inte stöds av Planeringsoptimering och som inte visas på **[analyssidan för Planeringsoptimering](planning-optimization-fit-analysis.md)**].

| Funktion | Aktuellt beteende i Planeringsoptimering |
|---|---|
| Produkter med faktisk/nominell vikt | Produkter med faktisk/nominell vikt betraktas som vanliga produkter.|
| Utökningsbara dimensioner | Utökningsbara dimensioner är tomma på planerade order även om kryssrutan **Disponeringsplan efter dimension** har valts på sidan **Lagringsdimensionsgrupper** eller **Spårningsdimensionsgrupper**. |
| Filtrerade produktionskörningar | Mer information finns i [Produktionsplanering - Filter](production-planning.md#filters). |
| Prognosplanering | Prognosplanering stöds inte. Vi rekommenderar att du använder huvudplanering där en prognosmodell tilldelas huvudplanen. |
| Nummerserier för planerade order | Nummerserier för planerade order stöds inte. Planerade ordernummer genereras på tjänstesidan. |
| Plankopiering, borttagning av plan och rensning av planversion | <p>Följande artiklar inaktiveras under **Huvudplanering \> Huvudplanering \> Underhållsplaner** i navigeringfönstret:</p><ul><li>Plankopia</li><li>Radera plan</li><li>Planversionsrensning</li></ul> |
| Returorder | Returorder beaktas inte. |
| Tidsplaneringsrelaterade funktioner | Mer information finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md#limitations). |
| Transportkalendrar | Värdet i kolumnen **Transportkalender** på sidan **Leveranssätt** ignoreras. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Bristanalys för planeringsoptimering](planning-optimization-fit-analysis.md)
- [Parametrar som inte används i Planeringsoptimering](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
