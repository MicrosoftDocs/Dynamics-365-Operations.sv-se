---
title: Funktionen ISEMPTY ER
description: Det här avsnittet innehåller information om hur funktionen ISEMPTY elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563882"
---
# <a name="isempty-er-function"></a><span data-ttu-id="74f49-103">Funktionen ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="74f49-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74f49-104">`ISEMPTY`-funktionen returnerar *booleskt* värde för **SANT** om den angivna listan inte innehåller några poster.</span><span class="sxs-lookup"><span data-stu-id="74f49-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="74f49-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="74f49-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="74f49-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="74f49-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="74f49-107">Argument</span><span class="sxs-lookup"><span data-stu-id="74f49-107">Arguments</span></span>

<span data-ttu-id="74f49-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="74f49-108">`list`: *Record list*</span></span>

<span data-ttu-id="74f49-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="74f49-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="74f49-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="74f49-110">Return values</span></span>

<span data-ttu-id="74f49-111">*Boolesk*</span><span class="sxs-lookup"><span data-stu-id="74f49-111">*Boolean*</span></span>

<span data-ttu-id="74f49-112">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="74f49-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="74f49-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="74f49-113">Example 1</span></span>

<span data-ttu-id="74f49-114">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `ISEMPTY(DS)` att returnera **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="74f49-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="74f49-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="74f49-115">Example 2</span></span>

<span data-ttu-id="74f49-116">Uttrycket `ISEMPTY (SPLIT ("",1))` returnerar **SANT**.</span><span class="sxs-lookup"><span data-stu-id="74f49-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74f49-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="74f49-117">Additional resources</span></span>

[<span data-ttu-id="74f49-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="74f49-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]