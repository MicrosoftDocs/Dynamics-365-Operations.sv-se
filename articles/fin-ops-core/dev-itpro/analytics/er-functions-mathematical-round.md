---
title: ROUND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUND elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 716ac0bbc9fec992ec1bbfc99bfc86434bf97984
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570408"
---
# <a name="round-er-function"></a><span data-ttu-id="b5b5d-103">ROUND ER-funktion</span><span class="sxs-lookup"><span data-stu-id="b5b5d-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5b5d-104">`ROUND`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5b5d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5b5d-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="b5b5d-106">Argument</span><span class="sxs-lookup"><span data-stu-id="b5b5d-106">Arguments</span></span>

<span data-ttu-id="b5b5d-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="b5b5d-107">`number`: *Real*</span></span>

<span data-ttu-id="b5b5d-108">Ett numeriskt värde som måste avrundas.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="b5b5d-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="b5b5d-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="b5b5d-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="b5b5d-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b5b5d-111">Return values</span></span>

<span data-ttu-id="b5b5d-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="b5b5d-112">*Real*</span></span>

<span data-ttu-id="b5b5d-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b5b5d-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b5b5d-114">Usage notes</span></span>

<span data-ttu-id="b5b5d-115">Om värdet för `decimals`-argument är större än 0 (noll) avrundas det specificerade numret till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="b5b5d-116">Om värdet för argumentet `decimals` är **0** (noll) avrundas det specificerade numret till närmast jämna heltal.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="b5b5d-117">Om värdet för argumentet `decimals` är mindre än 0 (noll) avrundas det specificerade numret till vänster om decimaltecknet.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="b5b5d-118">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b5b5d-118">Example 1</span></span>

<span data-ttu-id="b5b5d-119">`ROUND (1200.767, 2)` avrundar till två decimaler och returnerar **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b5b5d-120">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b5b5d-120">Example 2</span></span>

<span data-ttu-id="b5b5d-121">`ROUND (1200.767, -3)` avrundar till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="b5b5d-122">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="b5b5d-122">Example 3</span></span>

<span data-ttu-id="b5b5d-123">`ROUND (1200.5, 0)` avrundar till närmaste jämna heltal och returnerar **1200**, men `ROUND (1201.5, 0)` returnerar sedan **1202**.</span><span class="sxs-lookup"><span data-stu-id="b5b5d-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5b5d-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b5b5d-124">Additional resources</span></span>

[<span data-ttu-id="b5b5d-125">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="b5b5d-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]