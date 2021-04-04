---
title: AND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen AND elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 068b9a3b2cf2e5bffe895bc4e8a7cbb2d8025ad7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560095"
---
# <a name="and-er-function"></a><span data-ttu-id="20090-103">AND ER-funktion</span><span class="sxs-lookup"><span data-stu-id="20090-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20090-104">`AND`-funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="20090-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="20090-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="20090-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="20090-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="20090-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="20090-107">Argument</span><span class="sxs-lookup"><span data-stu-id="20090-107">Arguments</span></span>

<span data-ttu-id="20090-108">`condition 1`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="20090-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="20090-109">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="20090-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="20090-110">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="20090-110">This argument is required.</span></span>

<span data-ttu-id="20090-111">`condition N`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="20090-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="20090-112">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="20090-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="20090-113">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="20090-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="20090-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="20090-114">Return values</span></span>

<span data-ttu-id="20090-115">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="20090-115">*Boolean*</span></span>

<span data-ttu-id="20090-116">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="20090-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="20090-117">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="20090-117">Usage notes</span></span>

<span data-ttu-id="20090-118">I argumenten för logiska funktioner kan du använda datakällans referenser, numeriska värden och text, booleska värden, jämförelseoperatorer och andra funktioner för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="20090-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="20090-119">Alla argument måste dock utvärderas till ett *booleskt* värde **SANT** eller **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="20090-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="20090-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="20090-120">Example</span></span>

<span data-ttu-id="20090-121">`AND (1=1, "a"="a")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="20090-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="20090-122">`AND (1=2, "a"="a")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="20090-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="20090-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="20090-123">Additional resources</span></span>

[<span data-ttu-id="20090-124">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="20090-124">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]