---
title: Funktionen ISEMPTY ER
description: Det här avsnittet innehåller information om hur funktionen ISEMPTY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 5b6fde7cbadec7aae052742ef598e1af4dbae793
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745139"
---
# <a name="isempty-er-function"></a><span data-ttu-id="d262d-103">Funktionen ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="d262d-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d262d-104">`ISEMPTY`-funktionen returnerar *booleskt* värde för **SANT** om den angivna listan inte innehåller några poster.</span><span class="sxs-lookup"><span data-stu-id="d262d-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="d262d-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="d262d-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d262d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d262d-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="d262d-107">Argument</span><span class="sxs-lookup"><span data-stu-id="d262d-107">Arguments</span></span>

<span data-ttu-id="d262d-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="d262d-108">`list`: *Record list*</span></span>

<span data-ttu-id="d262d-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="d262d-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d262d-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="d262d-110">Return values</span></span>

<span data-ttu-id="d262d-111">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="d262d-111">*Boolean*</span></span>

<span data-ttu-id="d262d-112">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="d262d-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="d262d-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="d262d-113">Example 1</span></span>

<span data-ttu-id="d262d-114">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `ISEMPTY(DS)` att returnera **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="d262d-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d262d-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="d262d-115">Example 2</span></span>

<span data-ttu-id="d262d-116">Uttrycket `ISEMPTY (SPLIT ("",1))` returnerar **SANT**.</span><span class="sxs-lookup"><span data-stu-id="d262d-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d262d-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d262d-117">Additional resources</span></span>

[<span data-ttu-id="d262d-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="d262d-118">List functions</span></span>](er-functions-category-list.md)
