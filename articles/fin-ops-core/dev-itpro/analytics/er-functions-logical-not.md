---
title: NOT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751739"
---
# <a name="not-er-function"></a><span data-ttu-id="64982-103">NOT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="64982-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64982-104">`NOT`-funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.</span><span class="sxs-lookup"><span data-stu-id="64982-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="64982-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="64982-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="64982-106">Argument</span><span class="sxs-lookup"><span data-stu-id="64982-106">Arguments</span></span>

<span data-ttu-id="64982-107">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="64982-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="64982-108">Ett giltigt villkorsuttryck som måste återförd.</span><span class="sxs-lookup"><span data-stu-id="64982-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="64982-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="64982-109">Return values</span></span>

<span data-ttu-id="64982-110">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="64982-110">*Boolean*</span></span>

<span data-ttu-id="64982-111">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="64982-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="64982-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="64982-112">Example</span></span>

<span data-ttu-id="64982-113">`NOT (TRUE)` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="64982-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64982-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="64982-114">Additional resources</span></span>

[<span data-ttu-id="64982-115">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="64982-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]