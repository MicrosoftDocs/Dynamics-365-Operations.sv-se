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
ms.openlocfilehash: 96af593d2e8a738258fe614f0f252620cb48c5f19eeb4425c9659ee6f9cd8c0c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741223"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader

KB-nummer: 4614408

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när dimensionen **Lagerställe** inte har tilldelats under fliken **Prognosticeringsdimension** på sidan **Parameter för efterfrågeprognos**. Ändå visas kolumnen **Lagerställe** på sidan **Efterfrågeprognos** (**Huvudplanering \> Prognos \> Manuell prognos \> Efterfrågeprognosrader**).

## <a name="resolution"></a>Upplösning

Inställningarna under fliken **Prognosticeringsdimensioner** på sidan **Parameter för efterfrågeprognos** påverkar inte sidan **Efterfrågeprognos**. De styr baslinjeprognosen som skapas och visas i den justerade efterfrågeprognosen. De kontrollerar emellertid inte de dimensioner som krävs för den "verkliga" efterfrågeprognosen. Genom att auktorisera posterna som visas på sidan **Justerad efterfrågeprognos** kan du konvertera dem till "verkliga" prognosposter för en prognosmodell. Den modellen kan sedan användas för huvudplanering.

På sidan **Efterfrågeprognos** är dimensionerna för den "verkliga" prognosen som visas på efterfrågeprognosraderna del av lagerdimensionerna. (Detta beteende liknar beteendet för försäljningsorderrader.) Om ditt system inte är inställt på att använda **Lagerställe** som obligatorisk lagerdimension kan du anpassa sidan så att kolumnen döljs.
