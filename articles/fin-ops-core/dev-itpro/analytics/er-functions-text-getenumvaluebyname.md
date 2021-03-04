---
title: Funktionen GETENUMVALUEBYNAME ER
description: Det här avsnittet innehåller information om hur funktionen GETENUMVALUEBYNAME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29d7ec6498090ea47259303237c5a64a26e4926b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685942"
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

## <a name="example-1"></a>Exempel 1

I följande illustration introduceras uppräkningen **ReportDirection** i en datamodell. Observera att etiketter definieras för uppräkningsvärden.

![Tillgängliga värden för en uppräkningen för datamodell](./media/ER-data-model-enumeration-values.PNG)

Illustrationen som följer visar dessa detaljer:

- **$Direction** datakällan har konfigurerats i en ER-rapport. Den här datakällan konfigureras baserat på den **ReportDirection** modelluppräkning.
- `$IsArrivals`-uttrycket är utformat för att använda modelluppräkningsbaserad **$Direction** datakälla som en parameter för denna funktion.
- Värdet för detta jämförelseuttryck är **SANT**.

![Exempel på uppräkning av en datamodell](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Exempel 2

Med funktionerna `GETENUMVALUEBYNAME` och [`LISTOFFIELDS`](er-functions-list-listoffields.md) kan du hämta värden och etiketter för uppräkningar som stöds som textvärden. (De uppräkningar som stöds är programuppräkningar, uppräkningar av datamodeller och formatuppräkningar.)

I följande illustration introduceras datakällan **TransType** i en modellmappning. Den här datakällan refererar till uppräkningen **LedgerTransType** för program.

![Datakälla för en modellmappning som refererar till ett programuppräkning](./media/er-functions-text-getenumvaluebyname-example2-1.png)

Följande bild visar datakällan **TransTypeList** som konfigureras i en modellmappning. Den här datakällan konfigureras baserat på den **TransType** programuppräkning. Funktionen `LISTOFFIELDS` används för att returnera alla uppräkningsvärden som en lista med poster som innehåller fält. På så sätt visas information om varje uppräkningsvärde.

> [!NOTE]
> Fälteet **EnumValue** konfigureras för datakällan **TransTypeList** med hjälp av `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`-uttrycket. Det här fältet returnerar ett uppräkningsvärde för varje post i den här listan.

![Datakälla för en modellmappning som returnerar alla uppräkningsvärden för en markerad uppräkning som en lista med poster](./media/er-functions-text-getenumvaluebyname-example2-2.png)

Följande bild visar datakällan **VendTrans** som konfigureras i en modellmappning. Den här datakällan returnerar transaktionsposter för leverantörer från programregistret **VendTrans**. Redovisningstypen för varje transaktion definieras av värdet i fältet **TransType**.

> [!NOTE]
> Fälteet **TransTypeTitle** konfigureras för datakällan **VendTrans** med hjälp av `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`-uttrycket. Det här fältet returnerar etiketten för ett uppräkningsvärde för den aktuella transaktionen som text, om detta uppräkningsvärde är tillgängligt. Annars returneras ett tomt strängvärde.
>
> Fältet **TransTypeTitle** är bundet till **LedgerType** för en datamodell som gör att informationen kan användas i alla ER-format där datamodellen används som datakälla.

![Datakälla för en modellmappning som returnerar leverantörstransaktioner](./media/er-functions-text-getenumvaluebyname-example2-3.png)

Följande bild visar hur du kan använda [datakällans felsökare](er-debug-data-sources.md) för att testa den konfigurerade modellmappningen.

![Använda datakällans felsökare för att testa den konfigurerade modellmappningen](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

Fältet **LedgerType** i en datamodell visar etiketter för de transaktionstyper som förväntas.

Om du planerar att använda den här metoden för en stor mängd transaktionsdata måste du överväga att köra prestanda. För mer information, se [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)

[Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md)

[LISTOFFIELDS ER-funktion](er-functions-list-listoffields.md)

[FIRSTORNULL ER-funktion](er-functions-list-firstornull.md)

[WHERE ER-funktionen](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]