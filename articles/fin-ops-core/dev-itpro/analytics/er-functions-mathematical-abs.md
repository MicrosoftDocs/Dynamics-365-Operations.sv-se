---
title: ABS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ABS elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 12165174806395b3c36a1dbb227ed7a86def77b1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565794"
---
# <a name="abs-er-function"></a><span data-ttu-id="15aba-103">ABS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="15aba-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15aba-104">`ABS`-funktionen returnerar absolutvärdet (modul) för det angivna talet som ett *verkligt* värde.</span><span class="sxs-lookup"><span data-stu-id="15aba-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="15aba-105">Med andra ord returnera tal utan tecken.</span><span class="sxs-lookup"><span data-stu-id="15aba-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="15aba-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="15aba-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="15aba-107">Argument</span><span class="sxs-lookup"><span data-stu-id="15aba-107">Arguments</span></span>

<span data-ttu-id="15aba-108">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="15aba-108">`number`: *Real*</span></span>

<span data-ttu-id="15aba-109">Ett numeriskt värde som du vill ha modul för.</span><span class="sxs-lookup"><span data-stu-id="15aba-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="15aba-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="15aba-110">Return values</span></span>

<span data-ttu-id="15aba-111">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="15aba-111">*Real*</span></span>

<span data-ttu-id="15aba-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="15aba-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="15aba-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="15aba-113">Example</span></span>

<span data-ttu-id="15aba-114">`ABS (-1)` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="15aba-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15aba-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="15aba-115">Additional resources</span></span>

[<span data-ttu-id="15aba-116">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="15aba-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]