---
title: SUMIFS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SUMIFS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ff5ad3371a6e18ca1a3ee855e3b35f51f7513ef0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564769"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="006c4-103">SUMIFS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="006c4-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="006c4-104">`SUMIFS`-funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="006c4-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="006c4-105">Varje villkor består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="006c4-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="006c4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="006c4-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="006c4-107">Argument</span><span class="sxs-lookup"><span data-stu-id="006c4-107">Arguments</span></span>

<span data-ttu-id="006c4-108">`key name for summing`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="006c4-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="006c4-109">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för formatkomponenten elektronisk rapportering (ER) som värdet för bindningen måste användas för summeringsändamål.</span><span class="sxs-lookup"><span data-stu-id="006c4-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="006c4-110">Egenskapen **Collected data key name** kan konfigureras för antingen en **Numerisk**-komponent eller en **Sträng**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="006c4-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="006c4-111">`condition 1 range`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="006c4-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="006c4-112">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="006c4-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="006c4-113">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="006c4-113">This argument is mandatory.</span></span>

<span data-ttu-id="006c4-114">Egenskapen **Collected data key name** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="006c4-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="006c4-115">`condition 1 value`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="006c4-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="006c4-116">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="006c4-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="006c4-117">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="006c4-117">This argument is mandatory.</span></span>

<span data-ttu-id="006c4-118">Egenskapen **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="006c4-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="006c4-119">`condition N range`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="006c4-119">`condition N range`: *String*</span></span>

<span data-ttu-id="006c4-120">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="006c4-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="006c4-121">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="006c4-121">These additional arguments are optional.</span></span>

<span data-ttu-id="006c4-122">Egenskapen **Collected data key name** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="006c4-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="006c4-123">`condition N value`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="006c4-123">`condition N value`: *String*</span></span>

<span data-ttu-id="006c4-124">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="006c4-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="006c4-125">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="006c4-125">These additional arguments are optional.</span></span>

<span data-ttu-id="006c4-126">Egenskapen **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="006c4-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="006c4-127">Returvärden</span><span class="sxs-lookup"><span data-stu-id="006c4-127">Return values</span></span>

<span data-ttu-id="006c4-128">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="006c4-128">*Real*</span></span>

<span data-ttu-id="006c4-129">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="006c4-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="006c4-130">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="006c4-130">Usage notes</span></span>

<span data-ttu-id="006c4-131">Denna funktion returnerar ett **0** (noll) värde när alternativet **Collect output details** för den aktuella komponenten **gemensam\\fil** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="006c4-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="006c4-132">I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="006c4-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="006c4-133">I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="006c4-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="006c4-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="006c4-134">Example</span></span>

<span data-ttu-id="006c4-135">För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="006c4-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="006c4-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="006c4-136">Additional resources</span></span>

[<span data-ttu-id="006c4-137">Datainsamlingsfunktioner</span><span class="sxs-lookup"><span data-stu-id="006c4-137">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]