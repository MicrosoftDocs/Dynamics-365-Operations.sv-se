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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743649"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="cc8f4-103">INTVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="cc8f4-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc8f4-104">`INTVALUE`-funktionen returnerar ett *Int*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="cc8f4-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="cc8f4-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="cc8f4-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="cc8f4-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="cc8f4-107">Argument</span><span class="sxs-lookup"><span data-stu-id="cc8f4-107">Arguments</span></span>

<span data-ttu-id="cc8f4-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cc8f4-108">`text`: *String*</span></span>

<span data-ttu-id="cc8f4-109">Ett textvärde som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="cc8f4-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="cc8f4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="cc8f4-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="cc8f4-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="cc8f4-112">Return values</span></span>

<span data-ttu-id="cc8f4-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="cc8f4-113">*Int*</span></span>

<span data-ttu-id="cc8f4-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cc8f4-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="cc8f4-115">Usage notes</span></span>

<span data-ttu-id="cc8f4-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="cc8f4-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="cc8f4-117">Example 1</span></span>

<span data-ttu-id="cc8f4-118">`INTVALUE ("100.77")`-returnerar *Int*-värdet **100**.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="cc8f4-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="cc8f4-119">Example 2</span></span>

<span data-ttu-id="cc8f4-120">`INTVALUE (-100.77)`-returnerar *Int*-värdet **-100**.</span><span class="sxs-lookup"><span data-stu-id="cc8f4-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cc8f4-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cc8f4-121">Additional resources</span></span>

[<span data-ttu-id="cc8f4-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="cc8f4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
