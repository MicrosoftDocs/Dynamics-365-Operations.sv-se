---
title: Funktionen ISEMPTY ER
description: Det här avsnittet innehåller information om hur funktionen ISEMPTY elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750446"
---
# <a name="isempty-er-function"></a><span data-ttu-id="340f5-103">Funktionen ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="340f5-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="340f5-104">`ISEMPTY`-funktionen returnerar *booleskt* värde för **SANT** om den angivna listan inte innehåller några poster.</span><span class="sxs-lookup"><span data-stu-id="340f5-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="340f5-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="340f5-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="340f5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="340f5-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="340f5-107">Argument</span><span class="sxs-lookup"><span data-stu-id="340f5-107">Arguments</span></span>

<span data-ttu-id="340f5-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="340f5-108">`list`: *Record list*</span></span>

<span data-ttu-id="340f5-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="340f5-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="340f5-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="340f5-110">Return values</span></span>

<span data-ttu-id="340f5-111">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="340f5-111">*Boolean*</span></span>

<span data-ttu-id="340f5-112">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="340f5-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="340f5-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="340f5-113">Example 1</span></span>

<span data-ttu-id="340f5-114">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `ISEMPTY(DS)` att returnera **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="340f5-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="340f5-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="340f5-115">Example 2</span></span>

<span data-ttu-id="340f5-116">Uttrycket `ISEMPTY (SPLIT ("",1))` returnerar **SANT**.</span><span class="sxs-lookup"><span data-stu-id="340f5-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="340f5-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="340f5-117">Additional resources</span></span>

[<span data-ttu-id="340f5-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="340f5-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]