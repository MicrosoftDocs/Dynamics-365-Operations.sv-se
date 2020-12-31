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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a49def8aaa5398fbc7e0f06cc26df8a745207c93
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688001"
---
# <a name="index-er-function"></a><span data-ttu-id="0f5bd-103">INDEX ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="0f5bd-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f5bd-104">`INDEX`-funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="0f5bd-105">Om indexet är utom räckvidd för posterna i den angivna listan erhålls ett undantag.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f5bd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f5bd-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="0f5bd-107">Argument</span><span class="sxs-lookup"><span data-stu-id="0f5bd-107">Arguments</span></span>

<span data-ttu-id="0f5bd-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="0f5bd-108">`list`: *Record list*</span></span>

<span data-ttu-id="0f5bd-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0f5bd-110">`index`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="0f5bd-110">`index`: *Integer*</span></span>

<span data-ttu-id="0f5bd-111">Ett numeriskt index som anger positionen för den önskade posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="0f5bd-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0f5bd-112">Return values</span></span>

<span data-ttu-id="0f5bd-113">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="0f5bd-113">*Container (record)*</span></span>

<span data-ttu-id="0f5bd-114">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="0f5bd-115">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="0f5bd-115">Example 1</span></span>

<span data-ttu-id="0f5bd-116">Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `DS.Value` returnera textvärdet **"B"** för den andra posten i denna postlista.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="0f5bd-117">Uttrycket `INDEX (SPLIT ("A|B|C", "|"), 2).Value` returnerar också textvärdet **"B"**.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0f5bd-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="0f5bd-118">Example 2</span></span>

<span data-ttu-id="0f5bd-119">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="0f5bd-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f5bd-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0f5bd-120">Additional resources</span></span>

[<span data-ttu-id="0f5bd-121">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="0f5bd-121">List functions</span></span>](er-functions-category-list.md)
