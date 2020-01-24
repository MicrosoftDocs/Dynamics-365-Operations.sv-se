---
title: INTVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INTVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917728"
---
# <span data-ttu-id="0b843-103"><a name="INTVALUE">INTVALUE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="0b843-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b843-104">`INTVALUE`-funktionen returnerar ett *Int*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="0b843-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="0b843-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="0b843-105">Syntax 1</span></span>

```
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="0b843-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="0b843-106">Syntax 2</span></span>

```
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="0b843-107">Argument</span><span class="sxs-lookup"><span data-stu-id="0b843-107">Arguments</span></span>

<span data-ttu-id="0b843-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0b843-108">`text`: *String*</span></span>

<span data-ttu-id="0b843-109">Ett textvärde som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="0b843-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="0b843-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="0b843-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="0b843-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="0b843-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="0b843-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0b843-112">Return values</span></span>

<span data-ttu-id="0b843-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="0b843-113">*Int*</span></span>

<span data-ttu-id="0b843-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="0b843-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0b843-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="0b843-115">Usage notes</span></span>

<span data-ttu-id="0b843-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="0b843-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="0b843-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="0b843-117">Example 1</span></span>

<span data-ttu-id="0b843-118">`INTVALUE ("100.77")`-returnerar *Int*-värdet **100**.</span><span class="sxs-lookup"><span data-stu-id="0b843-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0b843-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="0b843-119">Example 2</span></span>

<span data-ttu-id="0b843-120">`INTVALUE (-100.77)`-returnerar *Int*-värdet **-100**.</span><span class="sxs-lookup"><span data-stu-id="0b843-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b843-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0b843-121">Additional resources</span></span>

[<span data-ttu-id="0b843-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="0b843-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
