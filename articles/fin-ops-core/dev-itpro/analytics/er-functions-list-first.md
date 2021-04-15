---
title: FIRST ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen FIRST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746589"
---
# <a name="first-er-function"></a><span data-ttu-id="c35b6-103">FIRST ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="c35b6-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c35b6-104">`FIRST`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om den listan inte är tom.</span><span class="sxs-lookup"><span data-stu-id="c35b6-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="c35b6-105">Om listan är tom, genererar den här funktionen ett undantag.</span><span class="sxs-lookup"><span data-stu-id="c35b6-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="c35b6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c35b6-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="c35b6-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c35b6-107">Arguments</span></span>

<span data-ttu-id="c35b6-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c35b6-108">`list`: *Record list*</span></span>

<span data-ttu-id="c35b6-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="c35b6-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c35b6-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c35b6-110">Return values</span></span>

<span data-ttu-id="c35b6-111">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="c35b6-111">*Container (record)*</span></span>

<span data-ttu-id="c35b6-112">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="c35b6-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c35b6-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="c35b6-113">Example 1</span></span>

<span data-ttu-id="c35b6-114">Uttrycket `FIRST(SPLIT("ABC",1)).Value` returnerar textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="c35b6-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c35b6-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="c35b6-115">Example 2</span></span>

<span data-ttu-id="c35b6-116">Uttrycket `FIRST(SPLIT("",1)).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="c35b6-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c35b6-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c35b6-117">Additional resources</span></span>

[<span data-ttu-id="c35b6-118">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="c35b6-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]