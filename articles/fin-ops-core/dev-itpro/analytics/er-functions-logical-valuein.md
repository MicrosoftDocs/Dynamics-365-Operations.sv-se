---
title: VALUEIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen VALUEIN elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 909aef5e52817a67e400f3132cb5d6ecc8a18906
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751760"
---
# <a name="valuein-er-function"></a><span data-ttu-id="f5f3b-103">VALUEIN ER-funktion</span><span class="sxs-lookup"><span data-stu-id="f5f3b-103">VALUEIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5f3b-104">`VALUEIN`-funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="f5f3b-105">Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="f5f3b-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5f3b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5f3b-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="f5f3b-108">Argument</span><span class="sxs-lookup"><span data-stu-id="f5f3b-108">Arguments</span></span>

<span data-ttu-id="f5f3b-109">`input`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="f5f3b-109">`input`: *Field*</span></span>

<span data-ttu-id="f5f3b-110">Den giltiga sökvägen för ett objekt av en datakälla för typen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="f5f3b-111">Värdet för det här objektet kommer att matchas.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-111">The value of this item will be matched.</span></span>

<span data-ttu-id="f5f3b-112">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="f5f3b-112">`list`: *Record list*</span></span>

<span data-ttu-id="f5f3b-113">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="f5f3b-114">`list item expression`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="f5f3b-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="f5f3b-115">Ett giltigt villkorsuttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="f5f3b-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="f5f3b-116">Return values</span></span>

<span data-ttu-id="f5f3b-117">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="f5f3b-117">*Boolean*</span></span>

<span data-ttu-id="f5f3b-118">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f5f3b-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="f5f3b-119">Usage notes</span></span>

<span data-ttu-id="f5f3b-120">I allmänhet översätts funktionen `VALUEIN` till en uppsättning **ELLER**-villkor.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span> <span data-ttu-id="f5f3b-121">Om listan med villkor **ELLER** är stor och den maximala totala längden för en SQL-sats kan överskridas, kan du överväga att använda [`VALUEINLARGE`](er-functions-logical-valueinlarge.md)-funktionen.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-121">If the list of **OR** conditions is large and the maximum total length of an SQL statement might be exceeded, consider using the [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) function.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="f5f3b-122">I vissa fall kan den översättas till en SQL-databassats med hjälp av `EXISTS JOIN`-operatorn.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-122">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="f5f3b-123">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="f5f3b-123">Example 1</span></span>

<span data-ttu-id="f5f3b-124">Du kan definiera följande datakälla i din modellmappning **lista** för typen *beräknat fält*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-124">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="f5f3b-125">Datakällan innehåller uttrycket `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-125">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="f5f3b-126">När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, List.Value)`-uttryck, returneras **SANT**.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-126">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="f5f3b-127">I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `(("B" = "a") or ("B" = "b") or ("B" = "c"))` där `("B" = "b")` är lika med **SANT**</span><span class="sxs-lookup"><span data-stu-id="f5f3b-127">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="f5f3b-128">När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, LEFT(List.Value, 0))`-uttryck, returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-128">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="f5f3b-129">I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `("B" = "")` som inte är lika med **SANT**.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-129">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="f5f3b-130">Den övre gränsen för antalet tecken i texten i sådant tillstånd är 32 768 tecken.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-130">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="f5f3b-131">Därför bör du inte skapa datakällor som eventuellt överskrider begränsningen vid körning.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-131">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="f5f3b-132">Programmet ska sluta köras om gränsen överskrids och ett undantag genereras.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-132">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="f5f3b-133">Till exempel kan detta inträffa om datakällan har konfigurerats som `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` och listorna **List1** och **List2** innehåller en stor mängd poster.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-133">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="f5f3b-134">I vissa fall kan funktionen `VALUEIN` översätts till en databas med hjälp av operatören `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-134">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="f5f3b-135">Det här problemet uppstår när funktionen [`FILTER`](er-functions-list-filter.md) används och följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="f5f3b-135">This behavior occurs when the [`FILTER`](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="f5f3b-136">Alternativet **FRÅGA EFTER FRÅGA** är inte markerat för datakällan för funktionen `VALUEIN` som refererar till listan över poster.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-136">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="f5f3b-137">Inga ytterligare villkor ska kopplas till den här datakällan vid körning.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-137">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="f5f3b-138">Inga kapslade uttryck är konfigurerade för funktionen `VALUEIN` som refererar till listan över poster.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-138">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="f5f3b-139">Ett listobjekt för funktionen `VALUEIN` refererar till ett fält i den angivna datakällan, inte ett uttryck eller en metod.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-139">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="f5f3b-140">Överväg att använda det här alternativet i stället för funktionen [`WHERE`](er-functions-list-where.md) som beskrivs tidigare i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-140">Consider using this option instead of the [`WHERE`](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="f5f3b-141">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="f5f3b-141">Example 2</span></span>

<span data-ttu-id="f5f3b-142">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="f5f3b-142">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="f5f3b-143">Datakällan **In** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-143">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="f5f3b-144">Den här datakällan refererar till tabellen Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-144">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="f5f3b-145">Datakällan **Port** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-145">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="f5f3b-146">Den här datakällan refererar till tabellen IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-146">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="f5f3b-147">När en datakälla anropas som konfigurerats som uttrycket `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` genereras följande SQL-sats för att returnera filtrerade poster i Intrastat-registret:</span><span class="sxs-lookup"><span data-stu-id="f5f3b-147">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="f5f3b-148">För fälten **dataAreaId** genereras den slutliga SQL-satsen utifrån operatör `IN`.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-148">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="f5f3b-149">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="f5f3b-149">Example 3</span></span>

<span data-ttu-id="f5f3b-150">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="f5f3b-150">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="f5f3b-151">**Le**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-151">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="f5f3b-152">Datakällan innehåller uttrycket `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-152">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="f5f3b-153">Datakällan **In** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-153">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="f5f3b-154">Den här datakällan refererar till Intrastattabellen och alternativet **korsföretag** aktiveras för den.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-154">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="f5f3b-155">När en datakälla anropas som konfigurerats som den `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, slutgiltiga SQL-satsen innehåller följande villkor.</span><span class="sxs-lookup"><span data-stu-id="f5f3b-155">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="f5f3b-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f5f3b-156">Additional resources</span></span>

[<span data-ttu-id="f5f3b-157">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="f5f3b-157">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="f5f3b-158">VALUEINLARGE funktioner</span><span class="sxs-lookup"><span data-stu-id="f5f3b-158">VALUEINLARGE functions</span></span>](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]