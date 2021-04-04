---
title: LISTJOIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTJOIN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6713823d8d089a677c39bc2a8b5cfe1d1b23b459
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563790"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="07b97-103">LISTJOIN ER-funktion</span><span class="sxs-lookup"><span data-stu-id="07b97-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07b97-104">`LISTJOIN`-funktionen returnerar ett *postlist*-värde som representerar av en ny sammanslagen lista med poster som skapas från de angivna argumenten.</span><span class="sxs-lookup"><span data-stu-id="07b97-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="07b97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07b97-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="07b97-106">Argument</span><span class="sxs-lookup"><span data-stu-id="07b97-106">Arguments</span></span>

<span data-ttu-id="07b97-107">`list 1`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="07b97-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="07b97-108">En referens till en datakälla av datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="07b97-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="07b97-109">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="07b97-109">This argument is mandatory.</span></span>

<span data-ttu-id="07b97-110">`list N`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="07b97-110">`list N`: *Record list*</span></span>

<span data-ttu-id="07b97-111">En referens till en datakälla av datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="07b97-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="07b97-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="07b97-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="07b97-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="07b97-113">Return values</span></span>

<span data-ttu-id="07b97-114">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="07b97-114">*Record list*</span></span>

<span data-ttu-id="07b97-115">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="07b97-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="07b97-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="07b97-116">Usage notes</span></span>

<span data-ttu-id="07b97-117">Strukturen för listan som skapas innehåller endast de fält som presenteras i strukturen för varje postlista som nämns i argumenten.</span><span class="sxs-lookup"><span data-stu-id="07b97-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="07b97-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="07b97-118">Example</span></span>

<span data-ttu-id="07b97-119">Du anger datakälla **post 1** av typen `Container`.</span><span class="sxs-lookup"><span data-stu-id="07b97-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="07b97-120">Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="07b97-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="07b97-121">**Kod**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `String`.</span><span class="sxs-lookup"><span data-stu-id="07b97-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="07b97-122">**Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.</span><span class="sxs-lookup"><span data-stu-id="07b97-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="07b97-123">Du anger datakälla **post 2** av typen `Container`.</span><span class="sxs-lookup"><span data-stu-id="07b97-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="07b97-124">Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="07b97-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="07b97-125">**Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.</span><span class="sxs-lookup"><span data-stu-id="07b97-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="07b97-126">**IsValid**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="07b97-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Sidan ER-modellmappningsdesigner](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="07b97-128">I det här fallet returnerar uttrycket `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` en ny lista som innehåller två poster.</span><span class="sxs-lookup"><span data-stu-id="07b97-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Sidan ER-modell mappning i designer med två poster](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="07b97-130">Strukturen för den här listan består av ett enda fält **belopp** av typen `Real`, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="07b97-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Beloppsfält på sidan ER-modellmappningsdesigner](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="07b97-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="07b97-132">Additional resources</span></span>

[<span data-ttu-id="07b97-133">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="07b97-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="07b97-134">Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling</span><span class="sxs-lookup"><span data-stu-id="07b97-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]