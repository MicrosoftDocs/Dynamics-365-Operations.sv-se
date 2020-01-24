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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef7d81852a0bbb84fd8f37cd89555766cc47f5f8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915865"
---
# <span data-ttu-id="20697-103"><a name="ROUNDDOWN">ROUNDDOWN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="20697-103"><a name="ROUNDDOWN">ROUNDDOWN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20697-104">`ROUNDDOWN`-funktionen returnerar det specificerade numret som *verkligt* värde efter det avrundats ned till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="20697-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="20697-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="20697-105">Syntax</span></span>

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="20697-106">Argument</span><span class="sxs-lookup"><span data-stu-id="20697-106">Arguments</span></span>

<span data-ttu-id="20697-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="20697-107">`number`: *Real*</span></span>

<span data-ttu-id="20697-108">Ett numeriskt värde som måste avrundas nedåt.</span><span class="sxs-lookup"><span data-stu-id="20697-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="20697-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="20697-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="20697-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="20697-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="20697-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="20697-111">Return values</span></span>

<span data-ttu-id="20697-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="20697-112">*Real*</span></span>

<span data-ttu-id="20697-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="20697-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="20697-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="20697-114">Usage notes</span></span>

<span data-ttu-id="20697-115">Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret nedåt (mot noll).</span><span class="sxs-lookup"><span data-stu-id="20697-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="20697-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="20697-116">Example 1</span></span>

<span data-ttu-id="20697-117">`ROUNDDOWN (1200.767, 2)` avrundar nedåt till två decimaler och returnerar **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="20697-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="20697-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="20697-118">Example 2</span></span>

<span data-ttu-id="20697-119">`ROUNDDOWN (1700.767, -3)` avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="20697-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="20697-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="20697-120">Additional resources</span></span>

[<span data-ttu-id="20697-121">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="20697-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
