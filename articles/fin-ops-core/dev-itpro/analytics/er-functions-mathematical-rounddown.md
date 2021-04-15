---
title: ROUNDDOWN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDDOWN elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 89fc134ec11a47506211ce68ec3aaf966d9a308b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744473"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="11de5-103">ROUNDDOWN ER-funktion</span><span class="sxs-lookup"><span data-stu-id="11de5-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11de5-104">`ROUNDDOWN`-funktionen returnerar det specificerade numret som *verkligt* värde efter det avrundats ned till det angivna antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="11de5-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="11de5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="11de5-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="11de5-106">Argument</span><span class="sxs-lookup"><span data-stu-id="11de5-106">Arguments</span></span>

<span data-ttu-id="11de5-107">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="11de5-107">`number`: *Real*</span></span>

<span data-ttu-id="11de5-108">Ett numeriskt värde som måste avrundas nedåt.</span><span class="sxs-lookup"><span data-stu-id="11de5-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="11de5-109">`decimals`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="11de5-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="11de5-110">Ett numeriskt värde som representerar antalet decimaler.</span><span class="sxs-lookup"><span data-stu-id="11de5-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="11de5-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="11de5-111">Return values</span></span>

<span data-ttu-id="11de5-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="11de5-112">*Real*</span></span>

<span data-ttu-id="11de5-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="11de5-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="11de5-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="11de5-114">Usage notes</span></span>

<span data-ttu-id="11de5-115">Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret nedåt (mot noll).</span><span class="sxs-lookup"><span data-stu-id="11de5-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="11de5-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="11de5-116">Example 1</span></span>

<span data-ttu-id="11de5-117">`ROUNDDOWN (1200.767, 2)` avrundar nedåt till två decimaler och returnerar **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="11de5-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="11de5-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="11de5-118">Example 2</span></span>

<span data-ttu-id="11de5-119">`ROUNDDOWN (1700.767, -3)` avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**.</span><span class="sxs-lookup"><span data-stu-id="11de5-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11de5-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="11de5-120">Additional resources</span></span>

[<span data-ttu-id="11de5-121">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="11de5-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]