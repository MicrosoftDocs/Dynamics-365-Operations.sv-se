---
title: SUMIF ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SUMIF elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 579b14c713bc5f9831c5e012d16bb3b6f97b1035
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916440"
---
# <span data-ttu-id="de0ac-103"><a name="SUMIF">SUMIF ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="de0ac-103"><a name="SUMIF">SUMIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de0ac-104">`SUMIF`-funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="de0ac-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="de0ac-105">Villkoret består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="de0ac-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="de0ac-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="de0ac-106">Syntax</span></span>

```
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="de0ac-107">Argument</span><span class="sxs-lookup"><span data-stu-id="de0ac-107">Arguments</span></span>

<span data-ttu-id="de0ac-108">`key name for summing`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="de0ac-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="de0ac-109">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för formatkomponenten elektronisk rapportering (ER) som värdet för bindningen måste användas för summeringsändamål.</span><span class="sxs-lookup"><span data-stu-id="de0ac-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="de0ac-110">Egenskapen **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="de0ac-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="de0ac-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="de0ac-111">Return values</span></span>

<span data-ttu-id="de0ac-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="de0ac-112">*Real*</span></span>

<span data-ttu-id="de0ac-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="de0ac-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="de0ac-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="de0ac-114">Usage notes</span></span>

<span data-ttu-id="de0ac-115">Denna funktion returnerar ett **0** (noll) värde när alternativet **Collect output details** för den aktuella komponenten **gemensam\\fil** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="de0ac-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="de0ac-116">I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="de0ac-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="de0ac-117">I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="de0ac-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="de0ac-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="de0ac-118">Example</span></span>

<span data-ttu-id="de0ac-119">För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="de0ac-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="de0ac-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="de0ac-120">Additional resources</span></span>

[<span data-ttu-id="de0ac-121">Datainsamlingsfunktioner</span><span class="sxs-lookup"><span data-stu-id="de0ac-121">Data collection functions</span></span>](er-functions-category-data-collection.md)