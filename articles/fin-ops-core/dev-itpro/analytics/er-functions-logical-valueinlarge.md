---
title: VALUEINLARGE ER-funktioner
description: Det här avsnittet innehåller information om hur funktionen VALUEINLARGE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686916"
---
# <a name="valueinlarge-er-function"></a>VALUEINLARGE ER-funktioner

[!include [banner](../includes/banner.md)]

`VALUEINLARGE`-funktion bestämmer om specifik indata av typen *Int64* eller *heltal* matchar något värde för en angiven objekt i den angivna listan. Funktionen returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. Mer information om skillnaden med `VALUEIN`-funktionen finns i avsnittet om [användningsnotering](#usage_note) senare i det här avsnittet.

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
