---
title: Funktionen EMPTYLIST ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYLIST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: ccb52d7d88f292720360ae913ead5be239165193
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687680"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="22e1d-103">Funktionen EMPTYLIST ER</span><span class="sxs-lookup"><span data-stu-id="22e1d-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22e1d-104">`EMPTYLIST`-funktionen returnerar en tomt värde för *Postlista* genom att använda den definierade en lista som källa för liststrukturen.</span><span class="sxs-lookup"><span data-stu-id="22e1d-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="22e1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="22e1d-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="22e1d-106">Argument</span><span class="sxs-lookup"><span data-stu-id="22e1d-106">Arguments</span></span>

<span data-ttu-id="22e1d-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="22e1d-107">`list`: *Record list*</span></span>

<span data-ttu-id="22e1d-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="22e1d-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="22e1d-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="22e1d-109">Return values</span></span>

<span data-ttu-id="22e1d-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="22e1d-110">*Record list*</span></span>

<span data-ttu-id="22e1d-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="22e1d-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="22e1d-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="22e1d-112">Example</span></span>

<span data-ttu-id="22e1d-113">`EMPTYLIST (SPLIT ("abc", 1))` returnerar en ny tom lista som har samma struktur som listan som returneras från `SPLIT`-funktionen som används.</span><span class="sxs-lookup"><span data-stu-id="22e1d-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22e1d-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="22e1d-114">Additional resources</span></span>

[<span data-ttu-id="22e1d-115">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="22e1d-115">List functions</span></span>](er-functions-category-list.md)
