---
title: Skillnader mellan planeringsoptimering och den inaktuella huvudplaneringsmotorn
description: Denna artikel innehåller en lista med funktioner som ännu inte stöds av Planeringsoptimering och som inte visas på analyssidan för Planeringsoptimering.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745372"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Skillnader mellan planeringsoptimering och den inaktuella huvudplaneringsmotorn

[!include [banner](../../includes/banner.md)]

Resultatet från Planeringsoptimering kan skilja sig från resultaten från den inaktuella huvudplaneringsmotorn. Skillnaderna kan också orsakas av kommande funktioner. Denna artikel innehåller en lista med funktioner som ännu inte stöds av Planeringsoptimering och som inte visas på sidan **[Passformanalys för Planeringsoptimering](planning-optimization-fit-analysis.md)**].

| Funktion | Aktuellt beteende i Planeringsoptimering |
|---|---|
| Produkter med faktisk/nominell vikt | Produkter med faktisk/nominell vikt betraktas som vanliga produkter.|
| Utökningsbara dimensioner | Utökningsbara dimensioner stöds inte av Planeringsoptimering. När du använder Planeringsoptimering är utökningsbara dimensioner är tomma på planerade order även om kryssrutan **Disponeringsplan efter dimension** har valts på sidan **Lagringsdimensionsgrupper** eller **Spårningsdimensionsgrupper**. |
| Filtrerade produktionskörningar | Mer information finns i [Produktionsplanering - Filter](production-planning.md#filters). |
| Prognosplanering | Prognosplanering stöds inte. Vi rekommenderar att du använder huvudplanering där en prognosmodell tilldelas huvudplanen. |
| Nummerserier för planerade order | Nummerserier för planerade order stöds inte. Planerade ordernummer genereras på tjänstesidan. Det planerade ordernumret visas normalt med 10 siffror, men serien bygger faktiskt på 20 tecken: 10 siffror fördelade för planeringskörningsräkningen och de övriga 10 siffrorna för den planerade orderräkningen. |
| Plankopiering, borttagning av plan och rensning av planversion | <p>Följande artiklar inaktiveras under **Huvudplanering \> Huvudplanering \> Underhållsplaner** i navigeringfönstret:</p><ul><li>Plankopia</li><li>Radera plan</li><li>Planversionsrensning</li></ul> |
| Returorder | Returorder beaktas inte. |
| Tidsplaneringsrelaterade funktioner | Mer information finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md#limitations). |
| Uppfyllelse av säkerhetslager | Vid Planeringsoptimering används alltid alternativet *Dagens datum + anskaffningstid* för fältet **Uppfyll minimum** på sidan **Artikeldisponering**. Detta hjälper till att förhindra oönskade planerade beställningar och andra problem, eftersom om upphandlingstiden inte ingår för säkerhetslager, planerade beställningar som skapas för lågt lagerbehållare alltid försenas på grund av ledtiden. |
| Pegging av säkerhetslager och nettobehov | Kravtypen *säkerhetslager* ingår inte och visas inte på sidan **Nettobehov**. Säkerhetslager representerar inte efterfrågan och har inget behovsdatum kopplat. I stället begränsar det hur mycket lager som alltid måste finnas i lager. Fältvärdet **Minimum** beaktas fortfarande vid beräkning av planerade order under masterplanering. Vi rekommenderar att du inspekterar kolumnen **Ackumulerad kvantitet** på sidan **Nettobehov** för att se att detta värde beaktades. Eftersom peggingen skiljer sig åt kan olika åtgärder föreslås. |
| Transportkalendrar | Värdet i kolumnen **Transportkalender** på sidan **Leveranssätt** ignoreras. |
| Minsta/högsta disponeringskod utan värden| Med den inaktuella huvudplaneringsmotorn behandlas disponeringskoden som ett behov när du använder en minsta/högsta disponeringskod där inga minimi- eller maximivärden anges, och en order skapas för respektive behov. Med Planeringsoptimering skapar systemet en order per dag för att täcka hela beloppet för den dagen.  |
| Nettobehov och manuellt skapade planerade order | Med den inaktuella huvudplaneringsmotorn visas manuellt skapade leveransorder för en artikel automatiskt bland nettobehoven för artikeln. När du till exempel skapar en inköpsorder från en försäljningsorder visas inköpsordern på sidan **Nettobehov** utan att föregående åtgärder krävs. Det beror på att den inaktuella huvudplaneringsmotorn loggar lagertransaktioner i `inventLogTTS` registret och visar ändringar på sidan **nettobehov** för dynamiska planer. Med Planeringsoptimering kommer emellertid manuellt skapade order inte att visas bland nettobehoven för en artikel förrän Planeringsoptimering körs (med hjälp av en plan som inkluderar artikeln), eller innan du väljer **Uppdatera \> Huvudplanering** i åtgärdsfönstret på sidan **Nettobehov**, som kommer att köra huvudplanering för objektet. Mer information om hur du arbetar med sidan finns på sidan **Nettobehov**, se [Nettobehov och pegging-information](net-requirements.md). |
| Resurstilldelning | När du arbetar med obegränsad kapacitet tilldelar den inaktuella huvudplaneringsmotorn alla planerade order till samma resurs för en given resursgrupp. Detta förbättrar planeringsoptimering genom att välja resurser vid slumpmässiga tidpunkter så att olika tillverkningsorder kan använda olika resurser. Om du vill använda samma resurs för alla planerade order måste du ange den resursen i flödet. |
| Utökade datatyper (EDT) | Planeringsoptimering stöder inte ändringar av EDT. Det betyder att den här processen inte stöds officiellt och att den inte fungerar. |
| Uppfyllelse av säkerhetslager | Planeringsoptimering använder alltid **Uppfyll minimum** av *Dagens datum + anskaffningstid*. Detta förbereder systemet att använda en förenklad planeringsinställning i framtiden och för att ge ett åtgärdbart resultat. Om anskaffningstiden inte finns med i säkerhetslagret försenas planerade order som skapas för lagerbehållning alltid på grund av ledtiden. Det här beteendet kan orsaka betydande brus och oönskade planerade order. Det bästa tillvägagångssättet är att ändra inställningen så att *dagens datum + anskaffningstid* används. Uppdatera huvuddata för att undvika varningar. |
| Kopiera statisk till dynamisk plan | Planeringsoptimering kopierar inte den statiska planen till den dynamiska planen, oavsett inställningen på sidan **Huvudplaneringsparametrar**. I allmänhet är denna åtgärd mindre relevant begrepp på grund av snabbheten och den fullständiga genereringen av Planeringsoptimeringen. Om två eller flera planer används ska huvudplaneringen utlösas för varje plan. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Bristanalys för Planeringsoptimering](planning-optimization-fit-analysis.md)
- [Parametrar som inte används i Planeringsoptimering](not-used-parameters.md)
- [Parametrar för datum och tid används i Planeringsoptimering](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
