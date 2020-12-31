---
title: COUNT ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen COUNT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: b3a5bb33964c70c85c7d8571057060c1c2b9d433
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687730"
---
# <a name="count-er-function"></a><span data-ttu-id="c8181-103">COUNT ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="c8181-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8181-104">`COUNT`-funktionen returnerar ett *heltalsvärde* som representerar antalet poster i den angivna listan, om listan inte är tom.</span><span class="sxs-lookup"><span data-stu-id="c8181-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="c8181-105">Om listan är tom returnerar den här funktionen **0** (noll).</span><span class="sxs-lookup"><span data-stu-id="c8181-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="c8181-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8181-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="c8181-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c8181-107">Arguments</span></span>

<span data-ttu-id="c8181-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c8181-108">`list`: *Record list*</span></span>

<span data-ttu-id="c8181-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="c8181-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8181-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c8181-110">Return values</span></span>

<span data-ttu-id="c8181-111">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="c8181-111">*Integer*</span></span>

<span data-ttu-id="c8181-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="c8181-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="c8181-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="c8181-113">Example</span></span>

<span data-ttu-id="c8181-114">`COUNT (SPLIT("abcd" , 3))` returnerar **2** eftersom `SPLIT`-funktionen som används i det här exemplet skapar en lista som består av två poster.</span><span class="sxs-lookup"><span data-stu-id="c8181-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8181-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c8181-115">Additional resources</span></span>

[<span data-ttu-id="c8181-116">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="c8181-116">List functions</span></span>](er-functions-category-list.md)
