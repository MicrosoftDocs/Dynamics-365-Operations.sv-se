---
title: ROUNDUP ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDUP elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 1784ab3587a090c8e5535509a1ba52fc85111daa
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041594"
---
# <span data-ttu-id="1ef42-103"><a name="ROUNDUP">ROUNDUP ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="1ef42-103"><a name="ROUNDUP">ROUNDUP ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ef42-104">`ROUNDUP`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats upp till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="1ef42-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ef42-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ef42-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="1ef42-106">Argument</span><span class="sxs-lookup"><span data-stu-id="1ef42-106">Arguments</span></span>

<span data-ttu-id="1ef42-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="1ef42-107">`number`: *Real*</span></span>

<span data-ttu-id="1ef42-108">Ett numeriskt värde som måste avrundas uppåt.</span><span class="sxs-lookup"><span data-stu-id="1ef42-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="1ef42-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="1ef42-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="1ef42-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="1ef42-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="1ef42-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="1ef42-111">Return values</span></span>

<span data-ttu-id="1ef42-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="1ef42-112">*Real*</span></span>

<span data-ttu-id="1ef42-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="1ef42-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1ef42-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="1ef42-114">Usage notes</span></span>

<span data-ttu-id="1ef42-115">Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret uppåt (från noll).</span><span class="sxs-lookup"><span data-stu-id="1ef42-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="1ef42-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="1ef42-116">Example 1</span></span>

<span data-ttu-id="1ef42-117">`ROUNDUP (1200.763, 2)` avrundar uppåt till två decimaler och returnerar **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="1ef42-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1ef42-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="1ef42-118">Example 2</span></span>

<span data-ttu-id="1ef42-119">`ROUNDUP (1200.767, -3)` avrundar uppåt till närmaste multipel av 1 000 och returnerar **2000**.</span><span class="sxs-lookup"><span data-stu-id="1ef42-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ef42-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1ef42-120">Additional resources</span></span>

[<span data-ttu-id="1ef42-121">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="1ef42-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
