---
title: FIRST ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen FIRST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042100"
---
# <span data-ttu-id="c0655-103"><a name="FIRST">FIRST ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="c0655-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0655-104">`FIRST`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om den listan inte är tom.</span><span class="sxs-lookup"><span data-stu-id="c0655-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="c0655-105">Om listan är tom, genererar den här funktionen ett undantag.</span><span class="sxs-lookup"><span data-stu-id="c0655-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0655-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0655-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="c0655-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c0655-107">Arguments</span></span>

<span data-ttu-id="c0655-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c0655-108">`list`: *Record list*</span></span>

<span data-ttu-id="c0655-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="c0655-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c0655-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c0655-110">Return values</span></span>

<span data-ttu-id="c0655-111">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="c0655-111">*Container (record)*</span></span>

<span data-ttu-id="c0655-112">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="c0655-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c0655-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="c0655-113">Example 1</span></span>

<span data-ttu-id="c0655-114">Uttrycket `FIRST(SPLIT("ABC",1)).Value` returnerar textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="c0655-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c0655-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="c0655-115">Example 2</span></span>

<span data-ttu-id="c0655-116">Uttrycket `FIRST(SPLIT("",1)).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="c0655-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0655-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c0655-117">Additional resources</span></span>

[<span data-ttu-id="c0655-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="c0655-118">List functions</span></span>](er-functions-category-list.md)
