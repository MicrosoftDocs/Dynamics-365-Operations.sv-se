---
title: NOT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 9b55b3d8930ece7e2f2925579821ca88749801f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565890"
---
# <a name="not-er-function"></a><span data-ttu-id="531c9-103">NOT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="531c9-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="531c9-104">`NOT`-funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.</span><span class="sxs-lookup"><span data-stu-id="531c9-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="531c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="531c9-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="531c9-106">Argument</span><span class="sxs-lookup"><span data-stu-id="531c9-106">Arguments</span></span>

<span data-ttu-id="531c9-107">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="531c9-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="531c9-108">Ett giltigt villkorsuttryck som måste återförd.</span><span class="sxs-lookup"><span data-stu-id="531c9-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="531c9-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="531c9-109">Return values</span></span>

<span data-ttu-id="531c9-110">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="531c9-110">*Boolean*</span></span>

<span data-ttu-id="531c9-111">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="531c9-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="531c9-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="531c9-112">Example</span></span>

<span data-ttu-id="531c9-113">`NOT (TRUE)` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="531c9-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="531c9-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="531c9-114">Additional resources</span></span>

[<span data-ttu-id="531c9-115">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="531c9-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]