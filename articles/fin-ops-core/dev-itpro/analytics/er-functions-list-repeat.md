---
title: REPEAT ER-funktion
description: Den här artikeln innehåller information om hur REPEAT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220700"
---
# <a name="repeat-er-function"></a>REPEAT ER-funktion

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Funktionen `REPEAT` bygger på en post som innehåller fältet som har ett värde som matchar den angivna indata. Den returnerar sedan en ny *postlista* över en post som upprepas ett angivet antal gånger.

## <a name="syntax"></a>Syntax

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argument

`item`: Alla [primitiva](er-formula-supported-data-types-primitive.md) eller [sammansatta](er-formula-supported-data-types-composite.md) datatyper som stöds

Värdet som ska upprepas.

`number`: *Heltal*

Antal upprepningar.

## <a name="return-values"></a>Returvärden

*Postlista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Listan över upprepade poster som returneras exponerar följande fält:

- Det angivna värdet (`Item` fältet)
- Den aktuella postens index (`Number` fält)

> [!NOTE]
> Eftersom en-baserad numrering används för denna funktion har fältet `Number` värdet **1** för den första posten i den resulterande listan.

Du kan använda den här funktionen för att multiplicera befintliga data så att du kan göra prestanda- och volymtestning av [Elektronisk rapportering (ER)](general-electronic-reporting.md) lösningar med [Regression Suite Automation Tool (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Exempel

Du vill skapa ett dokument i XML-format som måste innehålla lika många `Party` XML-element som du anger i ett datainmatningsfält i dialogrutan vid körning, innan exekveringen av ett ER-format börjar.

På bilden nedan visas ER [format](er-overview-components.md#format-component). I det här formatet läggs ett enskilt `Party` XML-element till för att exponera egenskaperna för en enskild part.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

I nästa bild visas följande konfigurerade datakällor:

- `Party` datakälla som representerar en enskild part. Fältet `Party.Value` används för att exponera ett enda textvärde.
- `NumberOfRepeats` [Datakällan](er-user-input-parameter-data-sources.md) som används för att erbjuda ett datainmatningsfält i dialogrutan vid körning, så att du kan ange antalet parter som ska anges i det genererade dokumentet.
- Datakällan `Party2` som upprepar `Party` posten antalet gånger som du har angett i `NumberOfRepeats` datakällan.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

I nästa bild visas data bindande för det redigerbara ER-format som skapas för att generera utdata i XML-format. Dessa utdata visar enskilda parter som fasta noder.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

Följande bild visar resultatet när det utformat formatet körs och värdet för `NumberOfRepeats` datakällan anges som **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
