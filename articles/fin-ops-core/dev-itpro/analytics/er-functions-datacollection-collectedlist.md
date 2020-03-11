---
title: COLLECTEDLIST ER-funktion
description: Det här avsnittet innehåller information om hur funktionen COLLECTEDLIST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 8a66ba364a7d06cd5ac03b57f07e2c5d4eb7a46d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042606"
---
# <span data-ttu-id="ac271-103"><a name="COLLECTEDLIST">COLLECTEDLIST ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="ac271-103"><a name="COLLECTEDLIST">COLLECTEDLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac271-104">`COLLECTEDLIST`-funktionen ett *postlist*-värde som innehåller listan över värden som returnerades av egenskapen **Collected data key value** för formatelement och samlades in när format elementen användes för att generera utgående dokument under formatkörningen och som uppfyller de angivna villkoren.</span><span class="sxs-lookup"><span data-stu-id="ac271-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="ac271-105">Varje villkor består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="ac271-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac271-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac271-106">Syntax</span></span>

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="ac271-107">Argument</span><span class="sxs-lookup"><span data-stu-id="ac271-107">Arguments</span></span>

<span data-ttu-id="ac271-108">`condition 1 range`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ac271-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="ac271-109">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för elektronisk rapportering (ER)-format.</span><span class="sxs-lookup"><span data-stu-id="ac271-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="ac271-110">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="ac271-110">This argument is mandatory.</span></span>

<span data-ttu-id="ac271-111">`condition 1 value`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ac271-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="ac271-112">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="ac271-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ac271-113">Det här argumentet är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="ac271-113">This argument is mandatory.</span></span>

<span data-ttu-id="ac271-114">`condition N range`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ac271-114">`condition N range`: *String*</span></span>

<span data-ttu-id="ac271-115">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="ac271-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="ac271-116">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="ac271-116">These additional arguments are optional.</span></span>

<span data-ttu-id="ac271-117">`condition N value`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ac271-117">`condition N value`: *String*</span></span>

<span data-ttu-id="ac271-118">Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format.</span><span class="sxs-lookup"><span data-stu-id="ac271-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ac271-119">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="ac271-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="ac271-120">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ac271-120">Return values</span></span>

<span data-ttu-id="ac271-121">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="ac271-121">*Record list*</span></span>

<span data-ttu-id="ac271-122">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="ac271-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ac271-123">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="ac271-123">Usage notes</span></span>

<span data-ttu-id="ac271-124">Egenskaperna **Collected data key name** och **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponenten för ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output details** inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="ac271-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ac271-125">Denna funktion returnerar en tom lista när alternativet **Collect output details** på den aktuella komponenten **Allmänt\\Fil** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="ac271-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="ac271-126">I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="ac271-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="ac271-127">I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.</span><span class="sxs-lookup"><span data-stu-id="ac271-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="ac271-128">Exempel</span><span class="sxs-lookup"><span data-stu-id="ac271-128">Example</span></span>

<span data-ttu-id="ac271-129">För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="ac271-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac271-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ac271-130">Additional resources</span></span>

[<span data-ttu-id="ac271-131">Datainsamlingsfunktioner</span><span class="sxs-lookup"><span data-stu-id="ac271-131">Data collection functions</span></span>](er-functions-category-data-collection.md)
