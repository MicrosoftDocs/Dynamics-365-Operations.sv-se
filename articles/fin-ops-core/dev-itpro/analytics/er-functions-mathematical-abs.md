---
title: ABS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ABS elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 2a3613483d53fb265741b5d6a34a91da443dcef7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753154"
---
# <a name="abs-er-function"></a><span data-ttu-id="c19e3-103">ABS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="c19e3-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c19e3-104">`ABS`-funktionen returnerar absolutvärdet (modul) för det angivna talet som ett *verkligt* värde.</span><span class="sxs-lookup"><span data-stu-id="c19e3-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="c19e3-105">Med andra ord returnera tal utan tecken.</span><span class="sxs-lookup"><span data-stu-id="c19e3-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="c19e3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c19e3-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="c19e3-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c19e3-107">Arguments</span></span>

<span data-ttu-id="c19e3-108">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="c19e3-108">`number`: *Real*</span></span>

<span data-ttu-id="c19e3-109">Ett numeriskt värde som du vill ha modul för.</span><span class="sxs-lookup"><span data-stu-id="c19e3-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="c19e3-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c19e3-110">Return values</span></span>

<span data-ttu-id="c19e3-111">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="c19e3-111">*Real*</span></span>

<span data-ttu-id="c19e3-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="c19e3-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="c19e3-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="c19e3-113">Example</span></span>

<span data-ttu-id="c19e3-114">`ABS (-1)` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="c19e3-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c19e3-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c19e3-115">Additional resources</span></span>

[<span data-ttu-id="c19e3-116">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="c19e3-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]