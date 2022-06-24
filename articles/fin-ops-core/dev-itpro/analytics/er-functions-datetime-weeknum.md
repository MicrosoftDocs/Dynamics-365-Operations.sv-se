---
title: WEEKNUM ER-funktion
description: Den här artikeln innehåller information om hur funktionen WEEKNUM elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 2c6eef0d6e1f90a3f8d382591edad3d568da84ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858782"
---
# <a name="weeknum-er-function"></a>WEEKNUM ER-funktion

[!include [banner](../includes/banner.md)]

Funktionen `WEEKNUM` returnerar värdet *[Heltal](er-formula-supported-data-types-primitive.md#integer)* representerar veckan av året som inkluderar ett specificerat *[Datum](er-formula-supported-data-types-primitive.md#date)*. Beräkningen baseras på de konstnadsberoende regler som definierar en kalendervecka och den första dagen i veckan.

## <a name="syntax"></a>Syntax

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argument</a>

`date`: *Datum*

Ett datumvärde som representerar det datum som ska användas för att beräkna veckan på året.

`culture`: *[Sträng](er-formula-supported-data-types-primitive.md#string)*

Kulturen som ska användas för beräkning. Du kan använda språkkoder som stöds i enlighet med .NET [standarder](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0).

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Veckan under året beräknas baserat på [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-standarden, om denna standard har godkänts av ett land eller en region som språk anges under körning. Annars baseras beräkningen på lands-/regionspecifika nationella standarder.

Om en kod som inte stöds [kultur](#arguments) ges som argument för funktionen `WEEKNUM` vid körning genereras ett undantag. Om den tomma strängen anges som en språkkod används den engelska landsneutrala kalendern för att beräkna veckonumret.

## <a name="examples"></a>Exempel

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` returnerar **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` returnerar **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` returnerar **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` returnerar **21**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
