---
title: Funktionen EMPTYLIST ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYLIST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 1e2a92d9951c3ad27503cf82f1b45026f16c3835
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746685"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="c83f9-103">Funktionen EMPTYLIST ER</span><span class="sxs-lookup"><span data-stu-id="c83f9-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c83f9-104">`EMPTYLIST`-funktionen returnerar en tomt värde för *Postlista* genom att använda den definierade en lista som källa för liststrukturen.</span><span class="sxs-lookup"><span data-stu-id="c83f9-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="c83f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c83f9-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="c83f9-106">Argument</span><span class="sxs-lookup"><span data-stu-id="c83f9-106">Arguments</span></span>

<span data-ttu-id="c83f9-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c83f9-107">`list`: *Record list*</span></span>

<span data-ttu-id="c83f9-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="c83f9-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c83f9-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c83f9-109">Return values</span></span>

<span data-ttu-id="c83f9-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c83f9-110">*Record list*</span></span>

<span data-ttu-id="c83f9-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="c83f9-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="c83f9-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="c83f9-112">Example</span></span>

<span data-ttu-id="c83f9-113">`EMPTYLIST (SPLIT ("abc", 1))` returnerar en ny tom lista som har samma struktur som listan som returneras från `SPLIT`-funktionen som används.</span><span class="sxs-lookup"><span data-stu-id="c83f9-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c83f9-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c83f9-114">Additional resources</span></span>

[<span data-ttu-id="c83f9-115">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="c83f9-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]