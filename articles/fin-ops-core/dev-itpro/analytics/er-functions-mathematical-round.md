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
ms.openlocfilehash: 12af71a024a76fca98fc2e876da9b59e5762cf07
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744561"
---
# <a name="round-er-function"></a><span data-ttu-id="0f59a-103">ROUND ER-funktion</span><span class="sxs-lookup"><span data-stu-id="0f59a-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f59a-104">`ROUND`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="0f59a-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f59a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f59a-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="0f59a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="0f59a-106">Arguments</span></span>

<span data-ttu-id="0f59a-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="0f59a-107">`number`: *Real*</span></span>

<span data-ttu-id="0f59a-108">Ett numeriskt värde som måste avrundas.</span><span class="sxs-lookup"><span data-stu-id="0f59a-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="0f59a-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="0f59a-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="0f59a-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="0f59a-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="0f59a-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0f59a-111">Return values</span></span>

<span data-ttu-id="0f59a-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="0f59a-112">*Real*</span></span>

<span data-ttu-id="0f59a-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="0f59a-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0f59a-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="0f59a-114">Usage notes</span></span>

<span data-ttu-id="0f59a-115">Om värdet för `decimals`-argument är större än 0 (noll) avrundas det specificerade numret till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="0f59a-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="0f59a-116">Om värdet för argumentet `decimals` är **0** (noll) avrundas det specificerade numret till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="0f59a-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="0f59a-117">Om värdet för argumentet `decimals` är mindre än 0 (noll) avrundas det specificerade numret till vänster om decimaltecknet.</span><span class="sxs-lookup"><span data-stu-id="0f59a-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="0f59a-118">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="0f59a-118">Example 1</span></span>

<span data-ttu-id="0f59a-119">`ROUND (1200.767, 2)` avrundar till två decimaler och returnerar **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="0f59a-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0f59a-120">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="0f59a-120">Example 2</span></span>

<span data-ttu-id="0f59a-121">`ROUND (1200.767, -3)` avrundar till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="0f59a-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f59a-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0f59a-122">Additional resources</span></span>

[<span data-ttu-id="0f59a-123">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="0f59a-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
