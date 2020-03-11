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
ms.openlocfilehash: 214fb2808f024487795f27de45de1d4de8cead2d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041663"
---
# <span data-ttu-id="051db-103"><a name="ABS">ABS ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="051db-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="051db-104">`ABS`-funktionen returnerar absolutvärdet (modul) för det angivna talet som ett *verkligt* värde.</span><span class="sxs-lookup"><span data-stu-id="051db-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="051db-105">Med andra ord returnera tal utan tecken.</span><span class="sxs-lookup"><span data-stu-id="051db-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="051db-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="051db-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="051db-107">Argument</span><span class="sxs-lookup"><span data-stu-id="051db-107">Arguments</span></span>

<span data-ttu-id="051db-108">`number`: *Realtaltal*</span><span class="sxs-lookup"><span data-stu-id="051db-108">`number`: *Real*</span></span>

<span data-ttu-id="051db-109">Ett numeriskt värde som du vill ha modul för.</span><span class="sxs-lookup"><span data-stu-id="051db-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="051db-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="051db-110">Return values</span></span>

<span data-ttu-id="051db-111">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="051db-111">*Real*</span></span>

<span data-ttu-id="051db-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="051db-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="051db-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="051db-113">Example</span></span>

<span data-ttu-id="051db-114">`ABS (-1)` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="051db-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="051db-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="051db-115">Additional resources</span></span>

[<span data-ttu-id="051db-116">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="051db-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
