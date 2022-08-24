---
title: JSONVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen JSONVALUE elektronisk rapportering (ER) används.
author: kfend
ms.date: 10/25/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267993"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`JSONVALUE`-funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID. Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde.

## <a name="syntax"></a>Syntax

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng* som innehåller JSON-data.

`path`: *Sträng*

Identifierare för ett skalärvärde av JSON-data. Använd ett snedstreck (/) om du vill åtskilj namnen på relaterade JSON-noder. Använd parentesen (\[\]) notering för att ange index för ett visst värde i en JSON-matris. Observera att nollbaserad numrering används för detta index.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example-1"></a>Exempel 1

**JsonField** datakälla innehåller följande data JSON-format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. I det här fallet returnerar uttrycket `JSONVALUE (JsonField, "BuildNumber")` följande värde av datatypen *Sträng*: **"7.3.1234.1"**.

## <a name="example-2"></a>Exempel 2

Datakällan **JsonField** av typen *beräknat fält* som innehåller följande uttryck: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

Det här uttrycket är konfigurerat för att returnera ett värde för [*Sträng*](er-formula-supported-data-types-primitive.md#string) som representerar följande data i JSON-format.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

I det här fallet returnerar uttrycket `JSONVALUE(json, "workers/[1]/emails/[0]")` följande värde av datatypen *Sträng*: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
