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
# <span data-ttu-id="4c80b-103"><a name="VALUEIN">VALUEIN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="4c80b-103"><a name="VALUEIN">VALUEIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c80b-104">`VALUEIN`-funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="4c80b-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="4c80b-105">Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="4c80b-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="4c80b-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="4c80b-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c80b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c80b-107">Syntax</span></span>

```
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="4c80b-108">Argument</span><span class="sxs-lookup"><span data-stu-id="4c80b-108">Arguments</span></span>

<span data-ttu-id="4c80b-109">`input`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="4c80b-109">`input`: *Field*</span></span>

<span data-ttu-id="4c80b-110">Den giltiga sökvägen för ett objekt av en datakälla för typen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="4c80b-111">Värdet för det här objektet kommer att matchas.</span><span class="sxs-lookup"><span data-stu-id="4c80b-111">The value of this item will be matched.</span></span>

<span data-ttu-id="4c80b-112">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="4c80b-112">`list`: *Record list*</span></span>

<span data-ttu-id="4c80b-113">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="4c80b-114">`list item expression`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="4c80b-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="4c80b-115">Ett giltigt villkorsuttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen.</span><span class="sxs-lookup"><span data-stu-id="4c80b-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="4c80b-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4c80b-116">Return values</span></span>

<span data-ttu-id="4c80b-117">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="4c80b-117">*Boolean*</span></span>

<span data-ttu-id="4c80b-118">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="4c80b-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4c80b-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="4c80b-119">Usage notes</span></span>

<span data-ttu-id="4c80b-120">I allmänhet översätts funktionen `VALUEIN` till en uppsättning **ELLER**-villkor.</span><span class="sxs-lookup"><span data-stu-id="4c80b-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span>

```
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="4c80b-121">I vissa fall kan den översättas till en SQL-databassats med hjälp av `EXISTS JOIN`-operatorn.</span><span class="sxs-lookup"><span data-stu-id="4c80b-121">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="4c80b-122">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="4c80b-122">Example 1</span></span>

<span data-ttu-id="4c80b-123">Du kan definiera följande datakälla i din modellmappning **lista** för typen *beräknat fält*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-123">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="4c80b-124">Datakällan innehåller uttrycket `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="4c80b-124">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="4c80b-125">När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, List.Value)`-uttryck, returneras **SANT**.</span><span class="sxs-lookup"><span data-stu-id="4c80b-125">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="4c80b-126">I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `(("B" = "a") or ("B" = "b") or ("B" = "c"))` där `("B" = "b")` är lika med **SANT**</span><span class="sxs-lookup"><span data-stu-id="4c80b-126">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="4c80b-127">När en datakälla anropas, om den har konfigurerats som `VALUEIN ("B", List, LEFT(List.Value, 0))`-uttryck, returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="4c80b-127">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="4c80b-128">I det här fallet översätts funktionen `VALUEIN` till följande uppsättning villkor: `("B" = "")` som inte är lika med **SANT**.</span><span class="sxs-lookup"><span data-stu-id="4c80b-128">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="4c80b-129">Den övre gränsen för antalet tecken i texten i sådant tillstånd är 32 768 tecken.</span><span class="sxs-lookup"><span data-stu-id="4c80b-129">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="4c80b-130">Därför bör du inte skapa datakällor som eventuellt överskrider begränsningen vid körning.</span><span class="sxs-lookup"><span data-stu-id="4c80b-130">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="4c80b-131">Programmet ska sluta köras om gränsen överskrids och ett undantag genereras.</span><span class="sxs-lookup"><span data-stu-id="4c80b-131">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="4c80b-132">Till exempel kan detta inträffa om datakällan har konfigurerats som `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` och listorna **List1** och **List2** innehåller en stor mängd poster.</span><span class="sxs-lookup"><span data-stu-id="4c80b-132">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="4c80b-133">I vissa fall kan funktionen `VALUEIN` översätts till en databas med hjälp av operatören `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="4c80b-133">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="4c80b-134">Det här problemet uppstår när funktionen [FILTER](er-functions-list-filter.md) används och följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="4c80b-134">This behavior occurs when the [FILTER](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="4c80b-135">Alternativet **FRÅGA EFTER FRÅGA** är inte markerat för datakällan för funktionen `VALUEIN` som refererar till listan över poster.</span><span class="sxs-lookup"><span data-stu-id="4c80b-135">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="4c80b-136">Inga ytterligare villkor ska kopplas till den här datakällan vid körning.</span><span class="sxs-lookup"><span data-stu-id="4c80b-136">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="4c80b-137">Inga kapslade uttryck är konfigurerade för funktionen `VALUEIN` som refererar till listan över poster.</span><span class="sxs-lookup"><span data-stu-id="4c80b-137">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="4c80b-138">Ett listobjekt för funktionen `VALUEIN` refererar till ett fält i den angivna datakällan, inte ett uttryck eller en metod.</span><span class="sxs-lookup"><span data-stu-id="4c80b-138">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="4c80b-139">Överväg att använda det här alternativet i stället för funktionen [WHERE](er-functions-list-where.md) som beskrivs tidigare i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="4c80b-139">Consider using this option instead of the [WHERE](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="4c80b-140">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="4c80b-140">Example 2</span></span>

<span data-ttu-id="4c80b-141">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="4c80b-141">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="4c80b-142">Datakällan **In** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-142">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="4c80b-143">Den här datakällan refererar till tabellen Intrastat.</span><span class="sxs-lookup"><span data-stu-id="4c80b-143">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="4c80b-144">Datakällan **Port** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-144">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="4c80b-145">Den här datakällan refererar till tabellen IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="4c80b-145">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="4c80b-146">När en datakälla anropas som konfigurerats som uttrycket `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` genereras följande SQL-sats för att returnera filtrerade poster i Intrastat-registret:</span><span class="sxs-lookup"><span data-stu-id="4c80b-146">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="4c80b-147">För fälten **dataAreaId** genereras den slutliga SQL-satsen utifrån operatör `IN`.</span><span class="sxs-lookup"><span data-stu-id="4c80b-147">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="4c80b-148">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="4c80b-148">Example 3</span></span>

<span data-ttu-id="4c80b-149">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="4c80b-149">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="4c80b-150">**Le**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-150">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="4c80b-151">Datakällan innehåller uttrycket `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="4c80b-151">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="4c80b-152">Datakällan **In** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="4c80b-152">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="4c80b-153">Den här datakällan refererar till Intrastattabellen och alternativet **korsföretag** aktiveras för den.</span><span class="sxs-lookup"><span data-stu-id="4c80b-153">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="4c80b-154">När en datakälla anropas som konfigurerats som den `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, slutgiltiga SQL-satsen innehåller följande villkor.</span><span class="sxs-lookup"><span data-stu-id="4c80b-154">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="4c80b-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4c80b-155">Additional resources</span></span>

[<span data-ttu-id="4c80b-156">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="4c80b-156">Logical functions</span></span>](er-functions-category-logical.md)
