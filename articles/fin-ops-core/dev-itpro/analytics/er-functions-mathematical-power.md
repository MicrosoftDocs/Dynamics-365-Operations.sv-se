---
title: POWER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen POWER elektronisk rapportering (ER) används.
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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915911"
---
# <span data-ttu-id="2a772-103"><a name="POWER">POWER ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="2a772-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a772-104">`POWER`-funktionen returnerar ett *verkligt* värde som representerar resultatet av att höja det angivna positiva talet till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="2a772-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a772-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a772-105">Syntax</span></span>

```
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="2a772-106">Argument</span><span class="sxs-lookup"><span data-stu-id="2a772-106">Arguments</span></span>

<span data-ttu-id="2a772-107">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="2a772-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="2a772-108">Ett numeriskt värde som måste höjas till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="2a772-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="2a772-109">`power`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="2a772-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="2a772-110">Ett numeriskt värde som representerar den specifika effekten.</span><span class="sxs-lookup"><span data-stu-id="2a772-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="2a772-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="2a772-111">Return values</span></span>

<span data-ttu-id="2a772-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="2a772-112">*Real*</span></span>

<span data-ttu-id="2a772-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="2a772-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2a772-114">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="2a772-114">Example 1</span></span>

<span data-ttu-id="2a772-115">`POWER (10, 2)` returnerar **100**.</span><span class="sxs-lookup"><span data-stu-id="2a772-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2a772-116">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="2a772-116">Example 2</span></span>

<span data-ttu-id="2a772-117">`POWER (4, 0.5)` returnerar **2**.</span><span class="sxs-lookup"><span data-stu-id="2a772-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a772-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2a772-118">Additional resources</span></span>

[<span data-ttu-id="2a772-119">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="2a772-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
