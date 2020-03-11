---
title: AND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen AND elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 1836d25ad07ad1ce735fda5e008a3315626b62bb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041839"
---
# <span data-ttu-id="6f3ef-103"><a name="AND">AND ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="6f3ef-103"><a name="AND">AND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f3ef-104">`AND`-funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="6f3ef-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f3ef-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f3ef-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="6f3ef-107">Argument</span><span class="sxs-lookup"><span data-stu-id="6f3ef-107">Arguments</span></span>

<span data-ttu-id="6f3ef-108">`condition 1`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="6f3ef-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="6f3ef-109">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="6f3ef-110">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-110">This argument is required.</span></span>

<span data-ttu-id="6f3ef-111">`condition N`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="6f3ef-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="6f3ef-112">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="6f3ef-113">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="6f3ef-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="6f3ef-114">Return values</span></span>

<span data-ttu-id="6f3ef-115">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="6f3ef-115">*Boolean*</span></span>

<span data-ttu-id="6f3ef-116">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6f3ef-117">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="6f3ef-117">Usage notes</span></span>

<span data-ttu-id="6f3ef-118">I argumenten för logiska funktioner kan du använda datakällans referenser, numeriska värden och text, booleska värden, jämförelseoperatorer och andra funktioner för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="6f3ef-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="6f3ef-119">Alla argument måste dock utvärderas till ett *booleskt* värde **SANT** eller **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="6f3ef-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="6f3ef-120">Example</span></span>

<span data-ttu-id="6f3ef-121">`AND (1=1, "a"="a")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="6f3ef-122">`AND (1=2, "a"="a")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="6f3ef-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f3ef-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6f3ef-123">Additional resources</span></span>

[<span data-ttu-id="6f3ef-124">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="6f3ef-124">Logical functions</span></span>](er-functions-category-logical.md)
