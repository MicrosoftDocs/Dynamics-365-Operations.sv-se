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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a850b1cbe7224ab1a7b2bd39ac4667304781cbb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041686"
---
# <span data-ttu-id="99030-103"><a name="OR">OR ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="99030-103"><a name="OR">OR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99030-104">`OR`-funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk.</span><span class="sxs-lookup"><span data-stu-id="99030-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="99030-105">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="99030-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="99030-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="99030-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="99030-107">Argument</span><span class="sxs-lookup"><span data-stu-id="99030-107">Arguments</span></span>

<span data-ttu-id="99030-108">`condition 1`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="99030-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="99030-109">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="99030-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="99030-110">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="99030-110">This argument is required.</span></span>

<span data-ttu-id="99030-111">`condition N`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="99030-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="99030-112">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="99030-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="99030-113">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="99030-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="99030-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="99030-114">Return values</span></span>

<span data-ttu-id="99030-115">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="99030-115">*Boolean*</span></span>

<span data-ttu-id="99030-116">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="99030-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="99030-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="99030-117">Example</span></span>

<span data-ttu-id="99030-118">`OR (1=2, "a"="a")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="99030-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99030-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="99030-119">Additional resources</span></span>

[<span data-ttu-id="99030-120">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="99030-120">Logical functions</span></span>](er-functions-category-logical.md)
