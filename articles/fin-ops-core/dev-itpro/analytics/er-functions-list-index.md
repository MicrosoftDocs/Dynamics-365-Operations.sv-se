---
title: INDEX ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen INDEX elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a7fe2cbb5421da3c6dd1d044316b276836c5e5c1
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917314"
---
# <span data-ttu-id="ec67b-103"><a name="INDEX">INDEX ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="ec67b-103"><a name="INDEX">INDEX ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec67b-104">`INDEX`-funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="ec67b-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="ec67b-105">Om indexet är utom räckvidd för posterna i den angivna listan erhålls ett undantag.</span><span class="sxs-lookup"><span data-stu-id="ec67b-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="ec67b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec67b-106">Syntax</span></span>

```
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="ec67b-107">Argument</span><span class="sxs-lookup"><span data-stu-id="ec67b-107">Arguments</span></span>

<span data-ttu-id="ec67b-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="ec67b-108">`list`: *Record list*</span></span>

<span data-ttu-id="ec67b-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="ec67b-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ec67b-110">`index`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="ec67b-110">`index`: *Integer*</span></span>

<span data-ttu-id="ec67b-111">Ett numeriskt index som anger positionen för den önskade posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="ec67b-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="ec67b-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ec67b-112">Return values</span></span>

<span data-ttu-id="ec67b-113">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="ec67b-113">*Container (record)*</span></span>

<span data-ttu-id="ec67b-114">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="ec67b-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="ec67b-115">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="ec67b-115">Example 1</span></span>

<span data-ttu-id="ec67b-116">Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `DS.Value` returnera textvärdet **"B"** för den andra posten i denna postlista.</span><span class="sxs-lookup"><span data-stu-id="ec67b-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="ec67b-117">Uttrycket `INDEX (SPLIT ("A|B|C", "|"), 2).Value` returnerar också textvärdet **"B"**.</span><span class="sxs-lookup"><span data-stu-id="ec67b-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ec67b-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="ec67b-118">Example 2</span></span>

<span data-ttu-id="ec67b-119">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="ec67b-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec67b-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ec67b-120">Additional resources</span></span>

[<span data-ttu-id="ec67b-121">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="ec67b-121">List functions</span></span>](er-functions-category-list.md)
