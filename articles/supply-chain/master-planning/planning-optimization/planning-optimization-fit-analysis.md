---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774054"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a>Planera analys av optimeringsanpassning

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
