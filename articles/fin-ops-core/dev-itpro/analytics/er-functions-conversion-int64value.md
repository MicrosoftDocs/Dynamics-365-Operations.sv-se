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
ms.openlocfilehash: 7fcb8a617507801d82d16175e9e86c9193091a12
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042698"
---
# <span data-ttu-id="bb2fc-103"><a name="INT64VALUE">INT64VALUE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="bb2fc-103"><a name="INT64VALUE">INT64VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb2fc-104">`INT64VALUE`-funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bb2fc-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="bb2fc-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="bb2fc-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="bb2fc-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="bb2fc-107">Argument</span><span class="sxs-lookup"><span data-stu-id="bb2fc-107">Arguments</span></span>

<span data-ttu-id="bb2fc-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="bb2fc-108">`text`: *String*</span></span>

<span data-ttu-id="bb2fc-109">Ett textvärde som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="bb2fc-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="bb2fc-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="bb2fc-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bb2fc-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="bb2fc-112">Return values</span></span>

<span data-ttu-id="bb2fc-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="bb2fc-113">*Int64*</span></span>

<span data-ttu-id="bb2fc-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bb2fc-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="bb2fc-115">Usage notes</span></span>

<span data-ttu-id="bb2fc-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="bb2fc-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="bb2fc-117">Example 1</span></span>

<span data-ttu-id="bb2fc-118">`INT64VALUE ("22565422744")`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bb2fc-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="bb2fc-119">Example 2</span></span>

<span data-ttu-id="bb2fc-120">`INT64VALUE ( VALUE("22565422744.77"))`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="bb2fc-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bb2fc-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bb2fc-121">Additional resources</span></span>

[<span data-ttu-id="bb2fc-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="bb2fc-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
