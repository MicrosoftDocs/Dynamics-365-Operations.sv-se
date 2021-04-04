---
title: INT64VALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INT64VALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 9db2e9abcac36a8331a494c886218bbfc82e93aa
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561504"
---
# <a name="int64value-er-function"></a><span data-ttu-id="e1c7f-103">INT64VALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="e1c7f-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1c7f-104">`INT64VALUE`-funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e1c7f-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="e1c7f-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="e1c7f-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="e1c7f-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="e1c7f-107">Argument</span><span class="sxs-lookup"><span data-stu-id="e1c7f-107">Arguments</span></span>

<span data-ttu-id="e1c7f-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e1c7f-108">`text`: *String*</span></span>

<span data-ttu-id="e1c7f-109">Ett textvärde som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="e1c7f-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="e1c7f-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="e1c7f-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int64*-nummer.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="e1c7f-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e1c7f-112">Return values</span></span>

<span data-ttu-id="e1c7f-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="e1c7f-113">*Int64*</span></span>

<span data-ttu-id="e1c7f-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e1c7f-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="e1c7f-115">Usage notes</span></span>

<span data-ttu-id="e1c7f-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="e1c7f-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e1c7f-117">Example 1</span></span>

<span data-ttu-id="e1c7f-118">`INT64VALUE ("22565422744")`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e1c7f-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e1c7f-119">Example 2</span></span>

<span data-ttu-id="e1c7f-120">`INT64VALUE ( VALUE("22565422744.77"))`-returnerar *Int64*-värdet **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="e1c7f-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1c7f-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e1c7f-121">Additional resources</span></span>

[<span data-ttu-id="e1c7f-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="e1c7f-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]