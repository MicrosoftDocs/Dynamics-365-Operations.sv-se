---
title: INT64VALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INT64VALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 75df802b75454baeea75a8ceb32d5d045a77a3a0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916555"
---
# <span data-ttu-id="c3af4-103"><a name="INT64VALUE">INT64VALUE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="c3af4-103"><a name="INT64VALUE">INT64VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3af4-104">`INT64VALUE`-funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="c3af4-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="c3af4-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="c3af4-105">Syntax 1</span></span>

```
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="c3af4-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="c3af4-106">Syntax 2</span></span>

```
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="c3af4-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c3af4-107">Arguments</span></span>

<span data-ttu-id="c3af4-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="c3af4-108">`text`: *String*</span></span>

<span data-ttu-id="c3af4-109">Ett textvärde som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="c3af4-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="c3af4-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="c3af4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="c3af4-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="c3af4-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="c3af4-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c3af4-112">Return values</span></span>

<span data-ttu-id="c3af4-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="c3af4-113">*Int64*</span></span>

<span data-ttu-id="c3af4-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="c3af4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c3af4-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="c3af4-115">Usage notes</span></span>

<span data-ttu-id="c3af4-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="c3af4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="c3af4-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="c3af4-117">Example 1</span></span>

<span data-ttu-id="c3af4-118">`INT64VALUE ("22565422744")`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="c3af4-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c3af4-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="c3af4-119">Example 2</span></span>

<span data-ttu-id="c3af4-120">`INT64VALUE ( VALUE("22565422744.77"))`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="c3af4-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3af4-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c3af4-121">Additional resources</span></span>

[<span data-ttu-id="c3af4-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="c3af4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
