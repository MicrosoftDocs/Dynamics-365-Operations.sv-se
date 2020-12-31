---
title: ROUNDDOWN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDDOWN elektronisk rapportering (ER) används.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686892"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="4d4dc-103">ROUNDDOWN ER-funktion</span><span class="sxs-lookup"><span data-stu-id="4d4dc-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d4dc-104">`ROUNDDOWN`-funktionen returnerar det specificerade numret som *verkligt* värde efter det avrundats ned till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d4dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d4dc-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="4d4dc-106">Argument</span><span class="sxs-lookup"><span data-stu-id="4d4dc-106">Arguments</span></span>

<span data-ttu-id="4d4dc-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="4d4dc-107">`number`: *Real*</span></span>

<span data-ttu-id="4d4dc-108">Ett numeriskt värde som måste avrundas nedåt.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="4d4dc-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="4d4dc-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="4d4dc-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="4d4dc-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4d4dc-111">Return values</span></span>

<span data-ttu-id="4d4dc-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="4d4dc-112">*Real*</span></span>

<span data-ttu-id="4d4dc-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4d4dc-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="4d4dc-114">Usage notes</span></span>

<span data-ttu-id="4d4dc-115">Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret nedåt (mot noll).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="4d4dc-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="4d4dc-116">Example 1</span></span>

<span data-ttu-id="4d4dc-117">`ROUNDDOWN (1200.767, 2)` avrundar nedåt till två decimaler och returnerar **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="4d4dc-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="4d4dc-118">Example 2</span></span>

<span data-ttu-id="4d4dc-119">`ROUNDDOWN (1700.767, -3)` avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d4dc-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4d4dc-120">Additional resources</span></span>

[<span data-ttu-id="4d4dc-121">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="4d4dc-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
