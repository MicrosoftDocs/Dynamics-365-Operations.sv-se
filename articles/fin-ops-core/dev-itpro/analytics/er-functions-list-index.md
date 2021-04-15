---
title: INDEX ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen INDEX elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 14f10359a3f20fb9d23639babce764b9ef64243d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750470"
---
# <a name="index-er-function"></a><span data-ttu-id="ba7c4-103">INDEX ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="ba7c4-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba7c4-104">`INDEX`-funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="ba7c4-105">Om indexet är utom räckvidd för posterna i den angivna listan erhålls ett undantag.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba7c4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba7c4-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="ba7c4-107">Argument</span><span class="sxs-lookup"><span data-stu-id="ba7c4-107">Arguments</span></span>

<span data-ttu-id="ba7c4-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="ba7c4-108">`list`: *Record list*</span></span>

<span data-ttu-id="ba7c4-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ba7c4-110">`index`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="ba7c4-110">`index`: *Integer*</span></span>

<span data-ttu-id="ba7c4-111">Ett numeriskt index som anger positionen för den önskade posten i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="ba7c4-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ba7c4-112">Return values</span></span>

<span data-ttu-id="ba7c4-113">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="ba7c4-113">*Container (record)*</span></span>

<span data-ttu-id="ba7c4-114">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="ba7c4-115">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="ba7c4-115">Example 1</span></span>

<span data-ttu-id="ba7c4-116">Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `DS.Value` returnera textvärdet **"B"** för den andra posten i denna postlista.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="ba7c4-117">Uttrycket `INDEX (SPLIT ("A|B|C", "|"), 2).Value` returnerar också textvärdet **"B"**.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ba7c4-118">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="ba7c4-118">Example 2</span></span>

<span data-ttu-id="ba7c4-119">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genererar ett undantag vid körning.</span><span class="sxs-lookup"><span data-stu-id="ba7c4-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba7c4-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ba7c4-120">Additional resources</span></span>

[<span data-ttu-id="ba7c4-121">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="ba7c4-121">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]