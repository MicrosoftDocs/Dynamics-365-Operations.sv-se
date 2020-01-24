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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917268"
---
# <span data-ttu-id="4128a-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="4128a-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4128a-104">`LISTOFFIRSTITEM`-funktionen returnerar ett *postlist*-värde som endast består av den första posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="4128a-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="4128a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4128a-105">Syntax</span></span>

```
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="4128a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="4128a-106">Arguments</span></span>

<span data-ttu-id="4128a-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="4128a-107">`list`: *Record list*</span></span>

<span data-ttu-id="4128a-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="4128a-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4128a-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4128a-109">Return values</span></span>

<span data-ttu-id="4128a-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="4128a-110">*Record list*</span></span>

<span data-ttu-id="4128a-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="4128a-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="4128a-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="4128a-112">Example</span></span>

<span data-ttu-id="4128a-113">Uttrycket `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returnerar textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="4128a-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4128a-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4128a-114">Additional resources</span></span>

[<span data-ttu-id="4128a-115">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="4128a-115">List functions</span></span>](er-functions-category-list.md)
