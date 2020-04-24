---
title: LISTJOIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTJOIN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249045"
---
# <a name=""></a><span data-ttu-id="053fd-103"><a name="LISTJOIN">LISTJOIN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="053fd-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="053fd-104">`LISTJOIN`-funktionen returnerar ett *postlist*-värde som representerar av en ny sammanslagen lista med poster som skapas från de angivna argumenten.</span><span class="sxs-lookup"><span data-stu-id="053fd-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="053fd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="053fd-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="053fd-106">Argument</span><span class="sxs-lookup"><span data-stu-id="053fd-106">Arguments</span></span>

<span data-ttu-id="053fd-107">`list 1`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="053fd-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="053fd-108">En referens till en datakälla av datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="053fd-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="053fd-109">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="053fd-109">This argument is mandatory.</span></span>

<span data-ttu-id="053fd-110">`list N`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="053fd-110">`list N`: *Record list*</span></span>

<span data-ttu-id="053fd-111">En referens till en datakälla av datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="053fd-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="053fd-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="053fd-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="053fd-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="053fd-113">Return values</span></span>

<span data-ttu-id="053fd-114">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="053fd-114">*Record list*</span></span>

<span data-ttu-id="053fd-115">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="053fd-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="053fd-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="053fd-116">Usage notes</span></span>

<span data-ttu-id="053fd-117">Strukturen för listan som skapas innehåller endast de fält som presenteras i strukturen för varje postlista som nämns i argumenten.</span><span class="sxs-lookup"><span data-stu-id="053fd-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="053fd-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="053fd-118">Example</span></span>

<span data-ttu-id="053fd-119">Du anger datakälla **post 1** av typen `Container`.</span><span class="sxs-lookup"><span data-stu-id="053fd-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="053fd-120">Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="053fd-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="053fd-121">**Kod**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `String`.</span><span class="sxs-lookup"><span data-stu-id="053fd-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="053fd-122">**Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.</span><span class="sxs-lookup"><span data-stu-id="053fd-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="053fd-123">Du anger datakälla **post 2** av typen `Container`.</span><span class="sxs-lookup"><span data-stu-id="053fd-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="053fd-124">Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="053fd-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="053fd-125">**Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.</span><span class="sxs-lookup"><span data-stu-id="053fd-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="053fd-126">**IsValid**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="053fd-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

<span data-ttu-id="053fd-127">I det här fallet returnerar uttrycket `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` en ny lista som innehåller två poster.</span><span class="sxs-lookup"><span data-stu-id="053fd-127">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span> <span data-ttu-id="053fd-128">Strukturen för den här listan består av ett enda fält **belopp** av typen `Real`, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="053fd-128">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="053fd-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="053fd-129">Additional resources</span></span>

[<span data-ttu-id="053fd-130">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="053fd-130">List functions</span></span>](er-functions-category-list.md)
