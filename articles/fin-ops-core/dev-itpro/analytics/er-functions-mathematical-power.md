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
ms.openlocfilehash: c57222d7fcc133faa679bab43431272c984c9d8b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041640"
---
# <span data-ttu-id="58f07-103"><a name="POWER">POWER ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="58f07-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58f07-104">`POWER`-funktionen returnerar ett *verkligt* värde som representerar resultatet av att höja det angivna positiva talet till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="58f07-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="58f07-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58f07-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="58f07-106">Argument</span><span class="sxs-lookup"><span data-stu-id="58f07-106">Arguments</span></span>

<span data-ttu-id="58f07-107">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="58f07-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="58f07-108">Ett numeriskt värde som måste höjas till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="58f07-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="58f07-109">`power`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="58f07-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="58f07-110">Ett numeriskt värde som representerar den specifika effekten.</span><span class="sxs-lookup"><span data-stu-id="58f07-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="58f07-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="58f07-111">Return values</span></span>

<span data-ttu-id="58f07-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="58f07-112">*Real*</span></span>

<span data-ttu-id="58f07-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="58f07-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="58f07-114">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="58f07-114">Example 1</span></span>

<span data-ttu-id="58f07-115">`POWER (10, 2)` returnerar **100**.</span><span class="sxs-lookup"><span data-stu-id="58f07-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="58f07-116">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="58f07-116">Example 2</span></span>

<span data-ttu-id="58f07-117">`POWER (4, 0.5)` returnerar **2**.</span><span class="sxs-lookup"><span data-stu-id="58f07-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58f07-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="58f07-118">Additional resources</span></span>

[<span data-ttu-id="58f07-119">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="58f07-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
