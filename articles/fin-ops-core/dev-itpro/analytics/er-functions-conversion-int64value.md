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
ms.openlocfilehash: 78b69b5280fb8c7ed99d73568097cd0c080a807a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744849"
---
# <a name="int64value-er-function"></a><span data-ttu-id="1a483-103">INT64VALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="1a483-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a483-104">`INT64VALUE`-funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="1a483-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="1a483-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="1a483-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="1a483-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="1a483-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="1a483-107">Argument</span><span class="sxs-lookup"><span data-stu-id="1a483-107">Arguments</span></span>

<span data-ttu-id="1a483-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="1a483-108">`text`: *String*</span></span>

<span data-ttu-id="1a483-109">Ett textvärde som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="1a483-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="1a483-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="1a483-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="1a483-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="1a483-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="1a483-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="1a483-112">Return values</span></span>

<span data-ttu-id="1a483-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="1a483-113">*Int64*</span></span>

<span data-ttu-id="1a483-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="1a483-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1a483-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="1a483-115">Usage notes</span></span>

<span data-ttu-id="1a483-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="1a483-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="1a483-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="1a483-117">Example 1</span></span>

<span data-ttu-id="1a483-118">`INT64VALUE ("22565422744")`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="1a483-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1a483-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="1a483-119">Example 2</span></span>

<span data-ttu-id="1a483-120">`INT64VALUE ( VALUE("22565422744.77"))`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="1a483-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a483-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1a483-121">Additional resources</span></span>

[<span data-ttu-id="1a483-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="1a483-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
