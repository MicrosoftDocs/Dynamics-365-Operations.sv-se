---
title: Använda filter på en plan
description: I det här avsnittet beskrivs hur använder filter på en plan när funktionerna för planeringsoptimering används.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 7b605f9826d2116f6f52a4b880f4fb5bd24cfdd0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813061"
---
# <a name="apply-filters-to-a-plan"></a>Använda filter på en plan

[!include [banner](../../includes/banner.md)]

När funktionen för planeringsoptimering används kan du använda ett filter på en plan. **Planfiltret** används alltid vid en huvudplaneringskörning. Ett **planfilter** är användbart när du vill begränsa en plan till en viss grupp av artiklar och se till att inga andra artiklar ingår i den resulterande huvudplaneringen.

Om ett **planfilter** används och ett körningsfilter också används under huvudplaneringskörningen, inkluderas bara skärningen mellan de två filtren i planeringskörningen.

**Planfiltret** kan nås från **huvudplaner** när planeringsoptimering används.

## <a name="example-scenario"></a>Exempelscenario

Ett planfilter är en inställning som omfattar artiklarna A, B och C. Huvudplaneringskörningarna körs sedan för samma plan, men olika körningsfilter tillämpas:

- **Körningsfilter som innehåller artikel D:** inga artiklar planeras eftersom det inte finns någon överlappning mellan planfiltret och körningsfiltret.
- **Körningsfilter som innehåller artikel A och D:** endast artikel A ingår i planeringskörningen, eftersom artikel D inte ingår i planfiltret.
- **Körningsfilter som innehåller artikel B:** endast artikel B ingår i planeringskörningen och det tidigare planeringsresultatet för artikel A behålls.
- **Körningsfilter som innehåller alla poster (tomt filter)** : artiklarna A, B och C inkluderas i planeringskörningen och föregående planeringsresultat för artiklarna A och B skrivs över.

> [!NOTE]
> Du bör inte ange ett planfilter för planen som har valts som **Aktuell dynamisk huvudplan** på sidan för **huvudplaneringsparametrar**. Annars kommer funktionen för dynamisk huvudplan att begränsas till de filtrerade artiklarna. Om till exempel nettobehoven uppdateras för en artikel som inte ingår i planfiltret, genereras inget resultat.

## <a name="related-resources"></a>Relaterade resurser

[Rådgivning om optimering – översikt](planning-optimization-overview.md)

[Kom igång med planeringsoptimering](get-started.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]