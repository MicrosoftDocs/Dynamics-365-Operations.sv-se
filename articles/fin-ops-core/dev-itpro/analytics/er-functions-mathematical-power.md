---
title: POWER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen POWER elektronisk rapportering (ER) används.
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
ms.openlocfilehash: ce1f4c735f815c46003ded35156bb47febf177a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750166"
---
# <a name="power-er-function"></a><span data-ttu-id="2dd4b-103">POWER ER-funktion</span><span class="sxs-lookup"><span data-stu-id="2dd4b-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2dd4b-104">`POWER`-funktionen returnerar ett *verkligt* värde som representerar resultatet av att höja det angivna positiva talet till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="2dd4b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2dd4b-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="2dd4b-106">Argument</span><span class="sxs-lookup"><span data-stu-id="2dd4b-106">Arguments</span></span>

<span data-ttu-id="2dd4b-107">`number`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="2dd4b-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="2dd4b-108">Ett numeriskt värde som måste höjas till den angivna effekten.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="2dd4b-109">`power`: *Realtal* eller *heltal*</span><span class="sxs-lookup"><span data-stu-id="2dd4b-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="2dd4b-110">Ett numeriskt värde som representerar den specifika effekten.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="2dd4b-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="2dd4b-111">Return values</span></span>

<span data-ttu-id="2dd4b-112">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="2dd4b-112">*Real*</span></span>

<span data-ttu-id="2dd4b-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2dd4b-114">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="2dd4b-114">Example 1</span></span>

<span data-ttu-id="2dd4b-115">`POWER (10, 2)` returnerar **100**.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2dd4b-116">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="2dd4b-116">Example 2</span></span>

<span data-ttu-id="2dd4b-117">`POWER (4, 0.5)` returnerar **2**.</span><span class="sxs-lookup"><span data-stu-id="2dd4b-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2dd4b-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2dd4b-118">Additional resources</span></span>

[<span data-ttu-id="2dd4b-119">Matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="2dd4b-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]