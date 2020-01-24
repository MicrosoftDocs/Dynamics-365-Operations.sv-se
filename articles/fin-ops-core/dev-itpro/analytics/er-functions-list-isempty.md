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
ms.openlocfilehash: c8450c17fe2de964016951197b0d4e231c550a99
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916141"
---
# <span data-ttu-id="f4d9f-103"><a name="ISEMPTY">Funktionen ISEMPTY ER</a></span><span class="sxs-lookup"><span data-stu-id="f4d9f-103"><a name="ISEMPTY">ISEMPTY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4d9f-104">`ISEMPTY`-funktionen returnerar *booleskt* värde för **SANT** om den angivna listan inte innehåller några poster.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="f4d9f-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4d9f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4d9f-106">Syntax</span></span>

```
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="f4d9f-107">Argument</span><span class="sxs-lookup"><span data-stu-id="f4d9f-107">Arguments</span></span>

<span data-ttu-id="f4d9f-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="f4d9f-108">`list`: *Record list*</span></span>

<span data-ttu-id="f4d9f-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="f4d9f-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="f4d9f-110">Return values</span></span>

<span data-ttu-id="f4d9f-111">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="f4d9f-111">*Boolean*</span></span>

<span data-ttu-id="f4d9f-112">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="f4d9f-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="f4d9f-113">Example 1</span></span>

<span data-ttu-id="f4d9f-114">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `ISEMPTY(DS)` att returnera **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f4d9f-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="f4d9f-115">Example 2</span></span>

<span data-ttu-id="f4d9f-116">Uttrycket `ISEMPTY (SPLIT ("",1))` returnerar **SANT**.</span><span class="sxs-lookup"><span data-stu-id="f4d9f-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4d9f-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f4d9f-117">Additional resources</span></span>

[<span data-ttu-id="f4d9f-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="f4d9f-118">List functions</span></span>](er-functions-category-list.md)
