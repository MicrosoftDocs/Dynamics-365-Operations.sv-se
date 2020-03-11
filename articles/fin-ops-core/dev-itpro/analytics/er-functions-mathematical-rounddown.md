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
ms.openlocfilehash: 92150bb23e76f82907e0f3e8f0738b25801958bf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041578"
---
# <span data-ttu-id="fd0b0-103"><a name="ROUNDDOWN">ROUNDDOWN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="fd0b0-103"><a name="ROUNDDOWN">ROUNDDOWN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd0b0-104">`ROUNDDOWN`-funktionen returnerar det specificerade numret som *verkligt* värde efter det avrundats ned till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd0b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd0b0-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="fd0b0-106">Argument</span><span class="sxs-lookup"><span data-stu-id="fd0b0-106">Arguments</span></span>

<span data-ttu-id="fd0b0-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="fd0b0-107">`number`: *Real*</span></span>

<span data-ttu-id="fd0b0-108">Ett numeriskt värde som måste avrundas nedåt.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="fd0b0-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="fd0b0-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="fd0b0-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="fd0b0-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="fd0b0-111">Return values</span></span>

<span data-ttu-id="fd0b0-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="fd0b0-112">*Real*</span></span>

<span data-ttu-id="fd0b0-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fd0b0-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="fd0b0-114">Usage notes</span></span>

<span data-ttu-id="fd0b0-115">Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret nedåt (mot noll).</span><span class="sxs-lookup"><span data-stu-id="fd0b0-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="fd0b0-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="fd0b0-116">Example 1</span></span>

<span data-ttu-id="fd0b0-117">`ROUNDDOWN (1200.767, 2)` avrundar nedåt till två decimaler och returnerar **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="fd0b0-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="fd0b0-118">Example 2</span></span>

<span data-ttu-id="fd0b0-119">`ROUNDDOWN (1700.767, -3)` avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="fd0b0-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd0b0-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fd0b0-120">Additional resources</span></span>

[<span data-ttu-id="fd0b0-121">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="fd0b0-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
