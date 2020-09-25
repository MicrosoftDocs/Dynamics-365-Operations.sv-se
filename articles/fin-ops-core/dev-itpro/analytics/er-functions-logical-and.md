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
ms.openlocfilehash: 4a246496eca0d5a8538ac7f1577957e6b9eae4e3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743482"
---
# <a name="and-er-function"></a><span data-ttu-id="efa5e-103">AND ER-funktion</span><span class="sxs-lookup"><span data-stu-id="efa5e-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efa5e-104">`AND`-funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="efa5e-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="efa5e-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="efa5e-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="efa5e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="efa5e-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="efa5e-107">Argument</span><span class="sxs-lookup"><span data-stu-id="efa5e-107">Arguments</span></span>

<span data-ttu-id="efa5e-108">`condition 1`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="efa5e-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="efa5e-109">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="efa5e-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="efa5e-110">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="efa5e-110">This argument is required.</span></span>

<span data-ttu-id="efa5e-111">`condition N`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="efa5e-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="efa5e-112">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="efa5e-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="efa5e-113">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="efa5e-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="efa5e-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="efa5e-114">Return values</span></span>

<span data-ttu-id="efa5e-115">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="efa5e-115">*Boolean*</span></span>

<span data-ttu-id="efa5e-116">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="efa5e-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="efa5e-117">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="efa5e-117">Usage notes</span></span>

<span data-ttu-id="efa5e-118">I argumenten för logiska funktioner kan du använda datakällans referenser, numeriska värden och text, booleska värden, jämförelseoperatorer och andra funktioner för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="efa5e-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="efa5e-119">Alla argument måste dock utvärderas till ett *booleskt* värde **SANT** eller **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="efa5e-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="efa5e-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="efa5e-120">Example</span></span>

<span data-ttu-id="efa5e-121">`AND (1=1, "a"="a")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="efa5e-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="efa5e-122">`AND (1=2, "a"="a")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="efa5e-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="efa5e-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="efa5e-123">Additional resources</span></span>

[<span data-ttu-id="efa5e-124">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="efa5e-124">Logical functions</span></span>](er-functions-category-logical.md)
