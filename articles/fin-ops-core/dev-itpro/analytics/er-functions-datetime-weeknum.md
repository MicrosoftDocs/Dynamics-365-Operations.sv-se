---
title: WEEKNUM ER-funktion
description: Den här artikeln innehåller information om hur funktionen WEEKNUM elektronisk rapportering (ER) används.
author: kfend
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 4658f88b7e353e651177fad0c8636c5403be1256
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268159"
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
