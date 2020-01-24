---
title: ABS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ABS elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 9b32c5e8a413be3583177f565e2d4909330ad1e0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917107"
---
# <span data-ttu-id="02a0f-103"><a name="ABS">ABS ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="02a0f-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02a0f-104">`ABS`-funktionen returnerar absolutvärdet (modul) för det angivna talet som ett *verkligt* värde.</span><span class="sxs-lookup"><span data-stu-id="02a0f-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="02a0f-105">Med andra ord returnera tal utan tecken.</span><span class="sxs-lookup"><span data-stu-id="02a0f-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="02a0f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="02a0f-106">Syntax</span></span>

```
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="02a0f-107">Argument</span><span class="sxs-lookup"><span data-stu-id="02a0f-107">Arguments</span></span>

<span data-ttu-id="02a0f-108">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="02a0f-108">`number`: *Real*</span></span>

<span data-ttu-id="02a0f-109">Ett numeriskt värde som du vill ha modul för.</span><span class="sxs-lookup"><span data-stu-id="02a0f-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="02a0f-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="02a0f-110">Return values</span></span>

<span data-ttu-id="02a0f-111">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="02a0f-111">*Real*</span></span>

<span data-ttu-id="02a0f-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="02a0f-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="02a0f-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="02a0f-113">Example</span></span>

<span data-ttu-id="02a0f-114">`ABS (-1)` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="02a0f-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02a0f-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="02a0f-115">Additional resources</span></span>

[<span data-ttu-id="02a0f-116">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="02a0f-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
