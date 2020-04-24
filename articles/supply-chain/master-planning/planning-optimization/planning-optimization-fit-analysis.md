---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 17114d4c0ef2c74ab1bb56d41e4a008150c21f36
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208764"
---
# <a name="planning-optimization-fit-analysis"></a>Planera analys av optimeringsanpassning

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Om du vill se hur kompatibla aktuella inställningar och data är med funktionen för planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Planera analys av optimeringsanpassning** och väljer sedan **Kör analys**. Om analysen hittar eventuella inkonsekvenser visas de på samma sida. (Det kan ta några minuter att köra analysen.)

> [!NOTE]
> Om inkonsekvenser hittas kan du fortfarande använda planeringsoptimering. Resultaten av anpassningsanalysen visar bara platser där planeringstjänsten inte ska svara på den aktuella inställningen. Med andra ord visar de platser där vissa processer kan ignoreras eller kanske inte stöds.

## <a name="analysis-results-example-1"></a>Analysresultat: exempel 1

- **Funktion:** produktion
- **Problem:** artiklar med strukturlistenivåer större än noll: 56
- **Förklaring:** anpassningsanalysen hittade 56 artiklar som har en inställning för strukturlista (BOM) för produktion. Eftersom den aktuella versionen av planeringsoptimering inte stöder produktionen genererar planeringsoptimering planerade inköpsorder istället för planerade tillverkningsorder. Dessutom visas en varning med en lista över de objekt som påverkas.

### <a name="analysis-results-example-2"></a>Analysresultat: exempel 2

- **Funktion:** åtgärder
- **Problem:** Disponeringsgrupper med aktiverad åtgärdsberäkning: 6
- **Förklaring:** anpassningsanalysen hittade sex disponeringsgrupper där åtgärdsberäkning är aktiverad. Eftersom den aktuella versionen av planeringsoptimering inte stöder åtgärder kommer inga åtgärder att genereras under huvudplaneringen.

## <a name="related-resources"></a>Relaterade resurser

[Rådgivning om optimering – översikt](planning-optimization-overview.md)

[Kom igång med planeringsoptimering](get-started.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)
