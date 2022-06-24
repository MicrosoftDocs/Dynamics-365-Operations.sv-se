---
title: Använda filter på en plan
description: I denna artikel beskrivs hur använder filter på en plan när funktionen Planeringsoptimering används.
author: t-benebo
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2df379be0876225bc7b0301d21f4e6660b04eb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875316"
---
# <a name="apply-filters-to-a-plan"></a>Använda filter på en plan

[!include [banner](../../includes/banner.md)]

När funktionen för Planeringsoptimering används kan du använda ett filter på en plan. **Planfiltret** används alltid vid en huvudplaneringskörning. Ett **planfilter** är användbart när du vill begränsa en plan till en viss grupp av artiklar och se till att inga andra artiklar ingår i den resulterande huvudplaneringen.

Om ett **planfilter** används och ett körningsfilter också används under huvudplaneringskörningen, inkluderas bara skärningen mellan de två filtren i planeringskörningen.

**Planfiltret** kan nås från **huvudplaner** när Planeringsoptimering används.

## <a name="example-scenario"></a>Exempelscenario

Ett planfilter är en inställning som omfattar artiklarna A, B och C. Huvudplaneringskörningarna körs sedan för samma plan, men olika körningsfilter tillämpas:

- **Körningsfilter som innehåller artikel D:** inga artiklar planeras eftersom det inte finns någon överlappning mellan planfiltret och körningsfiltret.
- **Körningsfilter som innehåller artikel A och D:** endast artikel A ingår i planeringskörningen, eftersom artikel D inte ingår i planfiltret.
- **Körningsfilter som innehåller artikel B:** endast artikel B ingår i planeringskörningen och det tidigare planeringsresultatet för artikel A behålls.
- **Körningsfilter som innehåller alla poster (tomt filter)** : artiklarna A, B och C inkluderas i planeringskörningen och föregående planeringsresultat för artiklarna A och B skrivs över.

> [!NOTE]
> Om du anger ett planfilter för den plan som är vald som **aktuell dynamisk huvudplan** på **parametersidan för huvudplanering** begränsas den dynamiska huvudplansfunktionen till filtrerade artiklarna. Om till exempel nettobehoven uppdateras för en artikel som inte ingår i planfiltret, genereras inget resultat.

## <a name="related-resources"></a>Relaterade resurser

[Rådgivning om optimering – översikt](planning-optimization-overview.md)

[Kom igång med Planeringsoptimering](get-started.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
