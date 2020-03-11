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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72d2ea1b26c295c97575a3c7a479ee4e06762424
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042215"
---
# <span data-ttu-id="a108e-103"><a name="COUNT">COUNT ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="a108e-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a108e-104">`COUNT`-funktionen returnerar ett *heltalsvärde* som representerar antalet poster i den angivna listan, om listan inte är tom.</span><span class="sxs-lookup"><span data-stu-id="a108e-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="a108e-105">Om listan är tom returnerar den här funktionen **0** (noll).</span><span class="sxs-lookup"><span data-stu-id="a108e-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="a108e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a108e-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="a108e-107">Argument</span><span class="sxs-lookup"><span data-stu-id="a108e-107">Arguments</span></span>

<span data-ttu-id="a108e-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="a108e-108">`list`: *Record list*</span></span>

<span data-ttu-id="a108e-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="a108e-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a108e-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="a108e-110">Return values</span></span>

<span data-ttu-id="a108e-111">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="a108e-111">*Integer*</span></span>

<span data-ttu-id="a108e-112">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="a108e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="a108e-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="a108e-113">Example</span></span>

<span data-ttu-id="a108e-114">`COUNT (SPLIT("abcd" , 3))` returnerar **2** eftersom `SPLIT`-funktionen som används i det här exemplet skapar en lista som består av två poster.</span><span class="sxs-lookup"><span data-stu-id="a108e-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a108e-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a108e-115">Additional resources</span></span>

[<span data-ttu-id="a108e-116">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="a108e-116">List functions</span></span>](er-functions-category-list.md)
