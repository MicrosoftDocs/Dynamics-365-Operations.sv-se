---
title: ROUNDAMOUNT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDAMOUNT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 15a84b086b324ec390d88e8b2617022ad4773977
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683073"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="ee0c2-103">ROUNDAMOUNT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="ee0c2-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee0c2-104">`ROUNDAMOUNT`-funktionen returnerar ett *verkligt* värde som resultat av avrundning av det angivna numret till närmaste multipel av ett annat tal enligt den angivna avrundningsregeln.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee0c2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee0c2-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="ee0c2-106">Argument</span><span class="sxs-lookup"><span data-stu-id="ee0c2-106">Arguments</span></span>

<span data-ttu-id="ee0c2-107">`number`: *Int* eller *Real*</span><span class="sxs-lookup"><span data-stu-id="ee0c2-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="ee0c2-108">Ett numeriskt värde som måste avrundas.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="ee0c2-109">`decimals`: *Int* eller *Real*</span><span class="sxs-lookup"><span data-stu-id="ee0c2-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="ee0c2-110">Det tal som `number`-parameterns värde måste avrundas till en multipel av.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="ee0c2-111">`round rule`: *Uppräknat värde*</span><span class="sxs-lookup"><span data-stu-id="ee0c2-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="ee0c2-112">Ett uppräkningsvärde för den **RoundOffType**-uppräkning som definierar avrundningsregeln.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="ee0c2-113">Den här uppräkningen erbjuder följande värden:</span><span class="sxs-lookup"><span data-stu-id="ee0c2-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="ee0c2-114">Normal (ordinarie)</span><span class="sxs-lookup"><span data-stu-id="ee0c2-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="ee0c2-115">Nedåt (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="ee0c2-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="ee0c2-116">Avrundningsmetod (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="ee0c2-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="ee0c2-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ee0c2-117">Return values</span></span>

<span data-ttu-id="ee0c2-118">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="ee0c2-118">*Real*</span></span>

<span data-ttu-id="ee0c2-119">Det resulterande numeriska värdet är en multipel av värdet som anges av `decimals`-parametern och är närmast det värde som anges av `number`-parametern.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ee0c2-120">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="ee0c2-120">Usage notes</span></span>

<span data-ttu-id="ee0c2-121">När `number`-parametern är noll, returnerar den här funktionen alltid noll.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="ee0c2-122">När `decimals`-parametern är noll avrundar den här funktionen till standardvärdet för avrundningsvärden.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="ee0c2-123">När `round rule`-parameter är inställd på **RoundOffType.Ordinary** är standardavrundningsvärdet **0.01**.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="ee0c2-124">Annars är standardavrundningsvärdet **1.0**.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="ee0c2-125">När `round rule`-parametern är inställd på **RoundOffType.Ordinary** avrundar denna funktion till närmaste avrundningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="ee0c2-126">När `round rule`-parametern är inställd på **RoundOffType.RoundDown** avrundar denna funktion mot noll till närmaste avrundningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="ee0c2-127">När `round rule`-parametern är inställd på **RoundOffType.RoundUp** avrundar denna funktion bort från noll till närmaste avrundningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="ee0c2-128">När `round rule`-parameter är inställd på **RoundOffType.Ordinary**, dden här funktionen uppför sig som [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel-funktion och [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ -funktion.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee0c2-129">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ee0c2-129">Remarks</span></span>

<span data-ttu-id="ee0c2-130">Om du vill avrunda ett numeriskt värde till ett angivet antal decimaler använder du funktionen [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="ee0c2-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ee0c2-131">Exempel</span><span class="sxs-lookup"><span data-stu-id="ee0c2-131">Example</span></span>

<span data-ttu-id="ee0c2-132">Om parametern **model.RoundOff** är inställd på **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 7.35.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="ee0c2-133">Om parametern **model.RoundOff** är inställd på **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 7.35.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="ee0c2-134">Om parametern **model.RoundOff** är inställd på **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 8.4.</span><span class="sxs-lookup"><span data-stu-id="ee0c2-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee0c2-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ee0c2-135">Additional resources</span></span>

[<span data-ttu-id="ee0c2-136">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="ee0c2-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="ee0c2-137">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="ee0c2-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)
