---
title: VALUEINLARGE ER-funktioner
description: Det här avsnittet innehåller information om hur funktionen VALUEINLARGE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 74d6856a0598293d87f79baabed4773d617164d0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743762"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="42ac1-103">VALUEINLARGE ER-funktioner</span><span class="sxs-lookup"><span data-stu-id="42ac1-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42ac1-104">`VALUEINLARGE`-funktion bestämmer om specifik indata av typen *Int64* eller *heltal* matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="42ac1-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="42ac1-105">Funktionen returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="42ac1-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="42ac1-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="42ac1-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="42ac1-107">Mer information om skillnaden med `VALUEIN`-funktionen finns i avsnittet om [användningsnotering](#usage_note) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="42ac1-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="42ac1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="42ac1-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="42ac1-109">Argument</span><span class="sxs-lookup"><span data-stu-id="42ac1-109">Arguments</span></span>

<span data-ttu-id="42ac1-110">`input`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="42ac1-110">`input`: *Field*</span></span>

<span data-ttu-id="42ac1-111">Den giltiga sökvägen av en datakällaartikel för typen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="42ac1-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="42ac1-112">Värdet för det här objektet kommer att matchas.</span><span class="sxs-lookup"><span data-stu-id="42ac1-112">The value of this item will be matched.</span></span>

<span data-ttu-id="42ac1-113">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="42ac1-113">`list`: *Record list*</span></span>

<span data-ttu-id="42ac1-114">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="42ac1-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="42ac1-115">`list item expression`: *Uttryck*</span><span class="sxs-lookup"><span data-stu-id="42ac1-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="42ac1-116">Ett giltigt villkorsuttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen.</span><span class="sxs-lookup"><span data-stu-id="42ac1-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="42ac1-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="42ac1-117">Return values</span></span>

<span data-ttu-id="42ac1-118">*Booleskt*</span><span class="sxs-lookup"><span data-stu-id="42ac1-118">*Boolean*</span></span>

<span data-ttu-id="42ac1-119">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="42ac1-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="42ac1-120"><a name="usage_note">Användningsanteckningar</a></span><span class="sxs-lookup"><span data-stu-id="42ac1-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="42ac1-121">När angiven inmatning representerar en *Int64* eller typen *heltal* för ett datakällaartikel, kommer den angivna listan att konverteras till ett temporärt SQL-register och matchas i databasen genom att en enda `EXISTS JOIN`-fråga körs.</span><span class="sxs-lookup"><span data-stu-id="42ac1-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="42ac1-122">I annat fall fungerar funktionen som [`VALUEIN`](er-functions-logical-valuein.md)-funktion.</span><span class="sxs-lookup"><span data-stu-id="42ac1-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="42ac1-123">När angivet indata representerar ett datakällaartikel som är utformat som ett annat objekt än *Int64* och *integer* uppstår ett fel vid designtillfället som informerar dig om att `VALUEINLARGE`-funktionen inte kan användas för det konfigurerade ER-uttrycket.</span><span class="sxs-lookup"><span data-stu-id="42ac1-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="42ac1-124">När `VALUEINLARGE`-funktionsuttrycket körs och mer än en temporär tabell används i denna körnings omfång uppstår ett fel vid körning.</span><span class="sxs-lookup"><span data-stu-id="42ac1-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="42ac1-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="42ac1-125">Example</span></span>

<span data-ttu-id="42ac1-126">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="42ac1-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="42ac1-127">Datakällan **In** för typen *tabellposter*.</span><span class="sxs-lookup"><span data-stu-id="42ac1-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="42ac1-128">Den här datakällan refererar till tabellen **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="42ac1-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="42ac1-129">Alternativet **mellan företag** är inställt på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="42ac1-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="42ac1-130">**InMemory**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="42ac1-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="42ac1-131">Datakällan innehåller uttrycket `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="42ac1-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="42ac1-132">**InFiltered**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="42ac1-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="42ac1-133">Datakällan innehåller uttrycket `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="42ac1-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="42ac1-134">När datakällan **InFiltered** anropas under företagets **DEMF** skapas en ny temporär tabell i programdatabasen, som samlas in i minneslistan med post-ID-koder infogas i den här tabellen och följande SQL-sats skapas för att returnera filtrerade poster från **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="42ac1-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="42ac1-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="42ac1-135">Additional resources</span></span>

[<span data-ttu-id="42ac1-136">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="42ac1-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="42ac1-137">VALUEIN-funktioner</span><span class="sxs-lookup"><span data-stu-id="42ac1-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]