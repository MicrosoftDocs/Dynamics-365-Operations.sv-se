---
title: VALUEINLARGE ER-funktioner
description: Den här artikeln innehåller information om hur funktionen VALUEINLARGE elektronisk rapportering (ER) används.
author: kfend
ms.date: 08/17/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 425dbce8f229acbb9c8d721c8f1a554989e0533c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288103"
---
# <a name="valueinlarge-er-function"></a>VALUEINLARGE ER-funktioner

[!include [banner](../includes/banner.md)]

`VALUEINLARGE`-funktion bestämmer om specifik indata av typen *Int64* eller *heltal* matchar något värde för en angiven objekt i den angivna listan. Funktionen returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. Mer information om skillnaden med `VALUEIN`-funktionen finns i avsnittet om [användningsnotering](#usage_note) senare i den här artikeln.

## <a name="syntax"></a>Syntax

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Argument

`input`: *Fält*

Den giltiga sökvägen av en datakällaartikel för typen *Postlista*. Värdet för det här objektet kommer att matchas.

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`list item expression`: *Uttryck*

Ett giltigt villkorsuttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen.

## <a name="return-values"></a>Returvärden

*Booleskt*

Det resulterande *booleska* värdet.

## <a name=""></a><a name="usage_note">Användningsanteckningar</a>

När angiven inmatning representerar en *Int64* eller typen *heltal* för ett datakällaartikel, kommer den angivna listan att konverteras till ett temporärt SQL-register och matchas i databasen genom att en enda `EXISTS JOIN`-fråga körs. I annat fall fungerar funktionen som [`VALUEIN`](er-functions-logical-valuein.md)-funktion.

När angivet indata representerar ett datakällaartikel som är utformat som ett annat objekt än *Int64* och *integer* uppstår ett fel vid designtillfället som informerar dig om att `VALUEINLARGE`-funktionen inte kan användas för det konfigurerade ER-uttrycket.

När `VALUEINLARGE`-funktionsuttrycket körs och mer än en temporär tabell används i denna körnings omfång uppstår ett fel vid körning.

## <a name="example"></a>Exempel

Du definierar följande datakällor i din modellmappning:

- Datakällan **In** för typen *tabellposter*.
    - Den här datakällan refererar till tabellen **Intrastat**.
    - Alternativet **mellan företag** är inställt på **Nej**.
- **InMemory**-datakällan för typen *beräknade fält*.
    - Datakällan innehåller uttrycket `WHERE (In, In.Port <> "")`.
- **InFiltered**-datakällan för typen *beräknade fält*.
    - Datakällan innehåller uttrycket `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.

När datakällan **InFiltered** anropas under företagets **DEMF** skapas en ny temporär tabell i programdatabasen, som samlas in i minneslistan med post-ID-koder infogas i den här tabellen och följande SQL-sats skapas för att returnera filtrerade poster från **Intrastat**.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)

[VALUEIN-funktioner](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
