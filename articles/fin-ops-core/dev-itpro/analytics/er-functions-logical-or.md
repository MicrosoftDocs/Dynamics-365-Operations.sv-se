---
title: OR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen OR elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686988"
---
# <a name="or-er-function"></a><span data-ttu-id="1af64-103">OR ER-funktion</span><span class="sxs-lookup"><span data-stu-id="1af64-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1af64-104">`OR`-funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk.</span><span class="sxs-lookup"><span data-stu-id="1af64-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="1af64-105">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="1af64-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1af64-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1af64-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="1af64-107">Argument</span><span class="sxs-lookup"><span data-stu-id="1af64-107">Arguments</span></span>

<span data-ttu-id="1af64-108">`condition 1`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="1af64-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="1af64-109">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="1af64-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="1af64-110">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="1af64-110">This argument is required.</span></span>

<span data-ttu-id="1af64-111">`condition N`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="1af64-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="1af64-112">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="1af64-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="1af64-113">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="1af64-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="1af64-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="1af64-114">Return values</span></span>

<span data-ttu-id="1af64-115">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="1af64-115">*Boolean*</span></span>

<span data-ttu-id="1af64-116">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="1af64-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="1af64-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="1af64-117">Example</span></span>

<span data-ttu-id="1af64-118">`OR (1=2, "a"="a")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="1af64-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1af64-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1af64-119">Additional resources</span></span>

[<span data-ttu-id="1af64-120">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="1af64-120">Logical functions</span></span>](er-functions-category-logical.md)
