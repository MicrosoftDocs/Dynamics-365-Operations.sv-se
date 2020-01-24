---
title: COUNTIF ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen COUNTIF elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: ca7c0f449aff75527e5052ba01e6fc0e29bb0fd7
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917705"
---
# <span data-ttu-id="619fd-103"><a name="COUNTIF">COUNTIF ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="619fd-103"><a name="COUNTIF">COUNTIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="619fd-104">`COUNTIF`-funktionen returnerar ett *heltalsvärde* som representerar antalet formatelement som samlades in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="619fd-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="619fd-105">Villkoret består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="619fd-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="619fd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="619fd-106">Syntax</span></span>

```
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="619fd-107">Argument</span><span class="sxs-lookup"><span data-stu-id="619fd-107">Arguments</span></span>

<span data-ttu-id="619fd-108">`condition range`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="619fd-108">`condition range`: *String*</span></span>

<span data-ttu-id="619fd-109">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för elektronisk rapportering (ER)-format.</span><span class="sxs-lookup"><span data-stu-id="619fd-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="619fd-110">`condition value`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="619fd-110">`condition value`: *String*</span></span>

<span data-ttu-id="619fd-111">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="619fd-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="619fd-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="619fd-112">Return values</span></span>

<span data-ttu-id="619fd-113">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="619fd-113">*Integer*</span></span>

<span data-ttu-id="619fd-114">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="619fd-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="619fd-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="619fd-115">Usage notes</span></span>

<span data-ttu-id="619fd-116">Egenskaperna **Collected data key name** och **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponenten för ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output details** inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="619fd-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="619fd-117">Denna funktion returnerar ett **0** (noll) värde när alternativet **Collect output details** för den aktuella komponenten **gemensam\\fil** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="619fd-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="619fd-118">I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="619fd-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="619fd-119">I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="619fd-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="619fd-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="619fd-120">Example</span></span>

<span data-ttu-id="619fd-121">För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="619fd-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="619fd-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="619fd-122">Additional resources</span></span>

[<span data-ttu-id="619fd-123">Datainsamlingsfunktioner</span><span class="sxs-lookup"><span data-stu-id="619fd-123">Data collection functions</span></span>](er-functions-category-data-collection.md)