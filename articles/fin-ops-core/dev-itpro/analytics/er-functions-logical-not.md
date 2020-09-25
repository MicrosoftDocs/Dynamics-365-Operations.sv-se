---
title: NOT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: af588c3714069040fa339d3121e6eb404b9be979
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744657"
---
# <a name="not-er-function"></a><span data-ttu-id="f5164-103">NOT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="f5164-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5164-104">`NOT`-funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.</span><span class="sxs-lookup"><span data-stu-id="f5164-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5164-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5164-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="f5164-106">Argument</span><span class="sxs-lookup"><span data-stu-id="f5164-106">Arguments</span></span>

<span data-ttu-id="f5164-107">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="f5164-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="f5164-108">Ett giltigt villkorsuttryck som måste återförd.</span><span class="sxs-lookup"><span data-stu-id="f5164-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="f5164-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="f5164-109">Return values</span></span>

<span data-ttu-id="f5164-110">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="f5164-110">*Boolean*</span></span>

<span data-ttu-id="f5164-111">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="f5164-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="f5164-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="f5164-112">Example</span></span>

<span data-ttu-id="f5164-113">`NOT (TRUE)` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="f5164-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5164-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f5164-114">Additional resources</span></span>

[<span data-ttu-id="f5164-115">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="f5164-115">Logical functions</span></span>](er-functions-category-logical.md)
