---
title: INTVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INTVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 64f43ad29d59ade1e124b6800734b003f6ca07df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561480"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="75336-103">INTVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="75336-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75336-104">`INTVALUE`-funktionen returnerar ett *Int*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="75336-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="75336-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="75336-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="75336-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="75336-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="75336-107">Argument</span><span class="sxs-lookup"><span data-stu-id="75336-107">Arguments</span></span>

<span data-ttu-id="75336-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="75336-108">`text`: *String*</span></span>

<span data-ttu-id="75336-109">Ett textvärde som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="75336-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="75336-110">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="75336-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="75336-111">Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int*-nummer.</span><span class="sxs-lookup"><span data-stu-id="75336-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="75336-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="75336-112">Return values</span></span>

<span data-ttu-id="75336-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="75336-113">*Int*</span></span>

<span data-ttu-id="75336-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="75336-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="75336-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="75336-115">Usage notes</span></span>

<span data-ttu-id="75336-116">Eventuella decimaler trunkeras.</span><span class="sxs-lookup"><span data-stu-id="75336-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="75336-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="75336-117">Example 1</span></span>

<span data-ttu-id="75336-118">`INTVALUE ("100.77")`-returnerar *Int*-värdet **100**.</span><span class="sxs-lookup"><span data-stu-id="75336-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="75336-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="75336-119">Example 2</span></span>

<span data-ttu-id="75336-120">`INTVALUE (-100.77)`-returnerar *Int*-värdet **-100**.</span><span class="sxs-lookup"><span data-stu-id="75336-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75336-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="75336-121">Additional resources</span></span>

[<span data-ttu-id="75336-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="75336-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]