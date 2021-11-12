---
title: Skillnader mellan inbyggd huvudplanering och Planeringsoptimering
description: Detta ämne innehåller en lista med funktioner som ännu inte stöds av Planeringsoptimering och som inte visas på analyssidan för Planeringsoptimering.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e271ddd3331d7b5de78f00a02b60a0479879c172
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700015"
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
| Nummerserier för planerade order | Nummerserier för planerade order stöds inte. Planerade ordernummer genereras på tjänstesidan. Det planerade ordernumret visas normalt med 10 siffror, men serien bygger faktiskt på 20 tecken: 10 siffror fördelade för planeringskörningsräkningen och de övriga 10 siffrorna för den planerade orderräkningen. |
| Plankopiering, borttagning av plan och rensning av planversion | <p>Följande artiklar inaktiveras under **Huvudplanering \> Huvudplanering \> Underhållsplaner** i navigeringfönstret:</p><ul><li>Plankopia</li><li>Radera plan</li><li>Planversionsrensning</li></ul> |
| Returorder | Returorder beaktas inte. |
| Tidsplaneringsrelaterade funktioner | Mer information finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md#limitations). |
| Uppfyllelse av säkerhetslager | Vid planeringsoptimering används alltid alternativet *Dagens datum + anskaffningstid* för fältet **Uppfyll minimum** på sidan **Artikeldisponering**. Detta hjälper till att förhindra oönskade planerade beställningar och andra problem, eftersom om upphandlingstiden inte ingår för säkerhetslager, planerade beställningar som skapas för lågt lagerbehållare alltid försenas på grund av ledtiden. |
| Pegging av säkerhetslager och nettobehov | Kravtypen *säkerhetslager* ingår inte och visas inte på sidan **Nettobehov**. Säkerhetslager representerar inte efterfrågan och har inget behovsdatum kopplat. I stället begränsar det hur mycket lager som alltid måste finnas i lager. Fältvärdet **Minimum** beaktas fortfarande vid beräkning av planerade order under masterplanering. Vi rekommenderar att du inspekterar kolumnen **Ackumulerad kvantitet** på sidan **Nettobehov** för att se att detta värde beaktades. |
| Transportkalendrar | Värdet i kolumnen **Transportkalender** på sidan **Leveranssätt** ignoreras. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Bristanalys för planeringsoptimering](planning-optimization-fit-analysis.md)
- [Parametrar som inte används i Planeringsoptimering](not-used-parameters.md)
- [Parametrar för datum och tid används i Planeringsoptimering](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
