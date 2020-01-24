---
title: VALUEIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen VALUEIN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: cb9a387c8b68d0da4dd485116089f1cf4c5ab72c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915980"
---
# <a name="VALUEIN">VALUEIN ER-funktion</a>

[!include [banner](../includes/banner.md)]

`VALUEIN`-funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan. Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argument

`input`: *Fält*

Den giltiga sökvägen för ett objekt av en datakälla för typen *Postlista*. Värdet för det här objektet kommer att matchas.

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`list item expression`: *Boolesk*

Ett giltigt villkorsuttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="usage-notes"></a>Användningsanteckningar

I allmänhet översätts funktionen `VALUEIN` till en uppsättning **ELLER**-villkor.

```
(input = list.item1.value) OR (input = list.item2.value) OR …
```

I vissa fall kan den översättas till en SQL-databassats med hjälp av `EXISTS JOIN`-operatorn.

## <a name="example-1"></a>Exempel 1

Du kan definiera följande datakälla i din modellmappning **lista** för typen *beräknat fält*. Datakällan innehåller uttrycket `SPLIT ("a,b,c", ",")`.

När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, List.Value)`-uttryck, returneras **SANT**. I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `(("B" = "a") or ("B" = "b") or ("B" = "c"))` där `("B" = "b")` är lika med **SANT**

När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, LEFT(List.Value, 0))`-uttryck, returneras **FALSKT**. I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `("B" = "")` som inte är lika med **SANT**.

Den övre gränsen för antalet tecken i texten i sådant tillstånd är 32 768 tecken. Därför bör du inte skapa datakällor som eventuellt överskrider begränsningen vid körning. Programmet ska sluta köras om gränsen överskrids och ett undantag genereras. Till exempel kan detta inträffa om datakällan har konfigurerats som `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` och listorna **List1** och **List2** innehåller en stor mängd poster.

I vissa fall kan funktionen `VALUEIN` översätts till en databas med hjälp av operatören `EXISTS JOIN`. Det här problemet uppstår när funktionen [FILTER](er-functions-list-filter.md) används och följande villkor uppfylls:

- Alternativet **FRÅGA EFTER FRÅGA** är inte markerat för datakällan för funktionen `VALUEIN` som refererar till listan över poster. Inga ytterligare villkor ska kopplas till den här datakällan vid körning.
- Inga kapslade uttryck är konfigurerade för funktionen `VALUEIN` som refererar till listan över poster.
- Ett listobjekt för funktionen `VALUEIN` refererar till ett fält i den angivna datakällan, inte ett uttryck eller en metod.

Överväg att använda det här alternativet i stället för funktionen [WHERE](er-functions-list-where.md) som beskrivs tidigare i det här exemplet.

## <a name="example-2"></a>Exempel 2

Du definierar följande datakällor i din modellmappning:

- Datakällan **In** för typen *tabellposter*. Den här datakällan refererar till tabellen Intrastat.
- Datakällan **Port** för typen *tabellposter*. Den här datakällan refererar till tabellen IntrastatPort.

När en datakälla anropas som konfigurerats som uttrycket `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` genereras följande SQL-sats för att returnera filtrerade poster i Intrastat-registret:

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

För fälten **dataAreaId** genereras den slutliga SQL-satsen utifrån operatör `IN`.

## <a name="example-3"></a>Exempel 3

Du definierar följande datakällor i din modellmappning:

- **Le**-datakällan för typen *beräknade fält*. Datakällan innehåller uttrycket `SPLIT ("DEMF,GBSI,USMF", ",")`.
- Datakällan **In** för typen *tabellposter*. Den här datakällan refererar till Intrastattabellen och alternativet **korsföretag** aktiveras för den.

När en datakälla anropas som konfigurerats som den `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, slutgiltiga SQL-satsen innehåller följande villkor.

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)
