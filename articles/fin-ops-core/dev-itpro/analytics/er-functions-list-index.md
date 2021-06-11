---
title: INDEX ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen INDEX elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 5a0fdb8958670efe8e2a37cee183bf836fa6c7e8
ms.sourcegitcommit: 047b0503868cc7d7b21868e24405d76af35db747
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "6087761"
---
# <a name="index-er-function"></a><span data-ttu-id="30fad-103">INDEX ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="30fad-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30fad-104">`INDEX`-funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="30fad-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="30fad-105">Om indexet är utom räckvidd för posterna i den angivna listan erhålls ett undantag.</span><span class="sxs-lookup"><span data-stu-id="30fad-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="30fad-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="30fad-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="30fad-107">Argument</span><span class="sxs-lookup"><span data-stu-id="30fad-107">Arguments</span></span>

<span data-ttu-id="30fad-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="30fad-108">`list`: *Record list*</span></span>

<span data-ttu-id="30fad-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="30fad-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="30fad-110">`index`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="30fad-110">`index`: *Integer*</span></span>

<span data-ttu-id="30fad-111">Ett numeriskt index som anger positionen för den önskade posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="30fad-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

> [!NOTE]
> <span data-ttu-id="30fad-112">Eftersom enbaserad numrering används för den här funktionen måste du ange värdet **1** för att returnera den första posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="30fad-112">Because one-based numbering is used for this function, specify the value **1** to return the first record of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="30fad-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="30fad-113">Return values</span></span>

<span data-ttu-id="30fad-114">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="30fad-114">*Container (record)*</span></span>

<span data-ttu-id="30fad-115">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="30fad-115">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="30fad-116">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="30fad-116">Example 1</span></span>

<span data-ttu-id="30fad-117">Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `DS.Value` returnera textvärdet **"B"** för den andra posten i denna postlista.</span><span class="sxs-lookup"><span data-stu-id="30fad-117">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="30fad-118">Uttrycket `INDEX (SPLIT ("A|B|C", "|"), 2).Value` returnerar också textvärdet **"B"**.</span><span class="sxs-lookup"><span data-stu-id="30fad-118">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="30fad-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="30fad-119">Example 2</span></span>

<span data-ttu-id="30fad-120">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="30fad-120">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30fad-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="30fad-121">Additional resources</span></span>

[<span data-ttu-id="30fad-122">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="30fad-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
