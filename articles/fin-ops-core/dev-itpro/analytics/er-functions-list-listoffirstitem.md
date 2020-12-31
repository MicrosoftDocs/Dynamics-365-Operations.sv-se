---
title: LISTOFFIRSTITEM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTOFFIRSTITEM elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 8ea81bce8cd6b922f3ef1d53ec0c4b2574780377
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686498"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="793d3-103">LISTOFFIRSTITEM ER-funktion</span><span class="sxs-lookup"><span data-stu-id="793d3-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="793d3-104">`LISTOFFIRSTITEM`-funktionen returnerar ett *postlist*-värde som endast består av den första posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="793d3-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="793d3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="793d3-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="793d3-106">Argument</span><span class="sxs-lookup"><span data-stu-id="793d3-106">Arguments</span></span>

<span data-ttu-id="793d3-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="793d3-107">`list`: *Record list*</span></span>

<span data-ttu-id="793d3-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="793d3-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="793d3-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="793d3-109">Return values</span></span>

<span data-ttu-id="793d3-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="793d3-110">*Record list*</span></span>

<span data-ttu-id="793d3-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="793d3-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="793d3-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="793d3-112">Example</span></span>

<span data-ttu-id="793d3-113">Uttrycket `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returnerar textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="793d3-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="793d3-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="793d3-114">Additional resources</span></span>

[<span data-ttu-id="793d3-115">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="793d3-115">List functions</span></span>](er-functions-category-list.md)
