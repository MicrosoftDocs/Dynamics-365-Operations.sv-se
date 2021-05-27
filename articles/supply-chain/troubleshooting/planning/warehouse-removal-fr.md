---
title: Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader
description: Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026918"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader

KB-nummer: 4614408

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när dimensionen **Lagerställe** inte har tilldelats under fliken **Prognosticeringsdimension** på sidan **Parameter för efterfrågeprognos**. Ändå visas kolumnen **Lagerställe** på sidan **Efterfrågeprognos** (**Huvudplanering \> Prognos \> Manuell prognos \> Efterfrågeprognosrader**).

## <a name="resolution"></a>Upplösning

Inställningarna under fliken **Prognosticeringsdimensioner** på sidan **Parameter för efterfrågeprognos** påverkar inte sidan **Efterfrågeprognos**. De styr baslinjeprognosen som skapas och visas i den justerade efterfrågeprognosen. De kontrollerar emellertid inte de dimensioner som krävs för den "verkliga" efterfrågeprognosen. Genom att auktorisera posterna som visas på sidan **Justerad efterfrågeprognos** kan du konvertera dem till "verkliga" prognosposter för en prognosmodell. Den modellen kan sedan användas för huvudplanering.

På sidan **Efterfrågeprognos** är dimensionerna för den "verkliga" prognosen som visas på efterfrågeprognosraderna del av lagerdimensionerna. (Detta beteende liknar beteendet för försäljningsorderrader.) Om ditt system inte är inställt på att använda **Lagerställe** som obligatorisk lagerdimension kan du anpassa sidan så att kolumnen döljs.
