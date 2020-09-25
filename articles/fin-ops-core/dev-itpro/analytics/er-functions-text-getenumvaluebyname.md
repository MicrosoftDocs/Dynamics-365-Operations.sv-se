---
title: Funktionen GETENUMVALUEBYNAME ER
description: Det här avsnittet innehåller information om hur funktionen GETENUMVALUEBYNAME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743865"
---
# <a name="getenumvaluebyname-er-function"></a>Funktionen GETENUMVALUEBYNAME ER

[!include [banner](../includes/banner.md)]

`GETENUMVALUEBYNAME`-funktionen söker efter ett specifikt värde för *uppräkning* i angiven uppräkningsdatakälla med hjälp av det uppräkningsnamn som anges som ett *sträng*-värde. Om *Enum*-värdet hittas returnerar funktionen den. Annars returnerar funktionen **null**-uppräkningsvärdet.

## <a name="syntax"></a>Syntax

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argument

`enumeration data source path`: *Uppräkning*

Den giltiga sökvägen till en datakälla för någon av följande uppräkningstyper:

- Elektronisk rapportering (ER) modelluppräkning
- ER-formatuppräkning
- Microsoft Dynamics 365 Finance uppräkning

`enumeration value text`: *Sträng*

Ett strängvärde som representerar namnet på ett enda uppräkningsvärde.

## <a name="return-values"></a>Returvärden

Kan ha värdet null *Enum*

Det resulterande fasttextvärde.

## <a name="usage-notes"></a>Användningsanteckningar

Inget undantag genereras om *fasttextvärde* inte hittas med hjälp av namnet på uppräkningsvärdet som anges som ett *sträng*-värde.

## <a name="example"></a>Exempel

I följande illustration introduceras uppräkningen **ReportDirection** i en datamodell. Observera att etiketter definieras för uppräkningsvärden.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Illustrationen som följer visar dessa detaljer:

- **$Direction** datakällan har konfigurerats i en ER-rapport. Den här datakällan konfigureras baserat på den **ReportDirection** modelluppräkning.
- `$IsArrivals`-uttrycket är utformat för att använda modelluppräkningsbaserad **$Direction** datakälla som en parameter för denna funktion.
- Värdet för detta jämförelseuttryck är **SANT**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
