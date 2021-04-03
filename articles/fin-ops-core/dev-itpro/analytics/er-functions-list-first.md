---
title: FIRST ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen FIRST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: ec94a27776cf1069b50b5437f4d167019fdef120
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564745"
---
# <a name="first-er-function"></a><span data-ttu-id="a62ad-103">FIRST ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="a62ad-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a62ad-104">`FIRST`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om den listan inte är tom.</span><span class="sxs-lookup"><span data-stu-id="a62ad-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="a62ad-105">Om listan är tom, genererar den här funktionen ett undantag.</span><span class="sxs-lookup"><span data-stu-id="a62ad-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="a62ad-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a62ad-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="a62ad-107">Argument</span><span class="sxs-lookup"><span data-stu-id="a62ad-107">Arguments</span></span>

<span data-ttu-id="a62ad-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="a62ad-108">`list`: *Record list*</span></span>

<span data-ttu-id="a62ad-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="a62ad-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a62ad-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="a62ad-110">Return values</span></span>

<span data-ttu-id="a62ad-111">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="a62ad-111">*Container (record)*</span></span>

<span data-ttu-id="a62ad-112">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="a62ad-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="a62ad-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="a62ad-113">Example 1</span></span>

<span data-ttu-id="a62ad-114">Uttrycket `FIRST(SPLIT("ABC",1)).Value` returnerar textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="a62ad-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a62ad-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="a62ad-115">Example 2</span></span>

<span data-ttu-id="a62ad-116">Uttrycket `FIRST(SPLIT("",1)).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="a62ad-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a62ad-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a62ad-117">Additional resources</span></span>

[<span data-ttu-id="a62ad-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="a62ad-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]