---
title: ROUND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUND elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 6751c1321fc71419fa8b153145a057371e0f7af5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041617"
---
# <span data-ttu-id="b2efe-103"><a name="ROUND">ROUND ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="b2efe-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2efe-104">`ROUND`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b2efe-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2efe-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2efe-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="b2efe-106">Argument</span><span class="sxs-lookup"><span data-stu-id="b2efe-106">Arguments</span></span>

<span data-ttu-id="b2efe-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="b2efe-107">`number`: *Real*</span></span>

<span data-ttu-id="b2efe-108">Ett numeriskt värde som måste avrundas.</span><span class="sxs-lookup"><span data-stu-id="b2efe-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="b2efe-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="b2efe-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="b2efe-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b2efe-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2efe-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b2efe-111">Return values</span></span>

<span data-ttu-id="b2efe-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="b2efe-112">*Real*</span></span>

<span data-ttu-id="b2efe-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="b2efe-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b2efe-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b2efe-114">Usage notes</span></span>

<span data-ttu-id="b2efe-115">Om värdet för `decimals`-argument är större än 0 (noll) avrundas det specificerade numret till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b2efe-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="b2efe-116">Om värdet för argumentet `decimals` är **0** (noll) avrundas det specificerade numret till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="b2efe-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="b2efe-117">Om värdet för argumentet `decimals` är mindre än 0 (noll) avrundas det specificerade numret till vänster om decimaltecknet.</span><span class="sxs-lookup"><span data-stu-id="b2efe-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="b2efe-118">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b2efe-118">Example 1</span></span>

<span data-ttu-id="b2efe-119">`ROUND (1200.767, 2)` avrundar till två decimaler och returnerar **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="b2efe-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b2efe-120">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b2efe-120">Example 2</span></span>

<span data-ttu-id="b2efe-121">`ROUND (1200.767, -3)` avrundar till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="b2efe-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2efe-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b2efe-122">Additional resources</span></span>

[<span data-ttu-id="b2efe-123">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="b2efe-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
