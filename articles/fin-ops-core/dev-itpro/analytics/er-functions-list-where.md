---
title: WHERE ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen WHERE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 50d90697f522f3c4d7b62190928008b6d923ffc6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916095"
---
# <span data-ttu-id="9ae54-103"><a name="WHERE">WHERE ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="9ae54-103"><a name="WHERE">WHERE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ae54-104">`WHERE`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har filtreras enligt det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="9ae54-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ae54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ae54-105">Syntax</span></span>

```
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="9ae54-106">Argument</span><span class="sxs-lookup"><span data-stu-id="9ae54-106">Arguments</span></span>

<span data-ttu-id="9ae54-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="9ae54-107">`list`: *Record list*</span></span>

<span data-ttu-id="9ae54-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="9ae54-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="9ae54-109">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="9ae54-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="9ae54-110">Ett giltigt villkorsuttryck som används för att filtrera poster i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="9ae54-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="9ae54-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9ae54-111">Return values</span></span>

<span data-ttu-id="9ae54-112">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="9ae54-112">*Record list*</span></span>

<span data-ttu-id="9ae54-113">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="9ae54-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9ae54-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="9ae54-114">Usage notes</span></span>

<span data-ttu-id="9ae54-115">Till skillnad från funktionen [FILTER](er-functions-list-filter.md) tillämpas angivet villkor på alla ER-datakällor (elektronisk rapportering) av typen *Postlista* som finns i minnet.</span><span class="sxs-lookup"><span data-stu-id="9ae54-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="9ae54-116">Om argumenten som har konfigurerats för den här funktionen (`list` och `condition`) tillåter att den här begäran översätts till direkt SQL-anrop, genereras ett varningsmeddelande vid designtillfället.</span><span class="sxs-lookup"><span data-stu-id="9ae54-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="9ae54-117">Det här meddelandet informerar användaren om att prestanda kan förbättras om [FILTER](er-functions-list-filter.md) funktionen används i stället för `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="9ae54-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="9ae54-118">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="9ae54-118">Example 1</span></span>

<span data-ttu-id="9ae54-119">Om **Leverantör** konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar uttrycket `WHERE (Vendors, Vendors.VendGroup = "40")` en lista över endast de leverantörer som ingår i leverantörsgrupp 40.</span><span class="sxs-lookup"><span data-stu-id="9ae54-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="9ae54-120">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="9ae54-120">Example 2</span></span>

<span data-ttu-id="9ae54-121">Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket , kommer uttrycket `SPLIT ("A|B|C", "|")` returnera uttrycket `WHERE( DS, DS.Value = "B")` en lista över en post innehåller text **"B"** i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="9ae54-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ae54-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9ae54-122">Additional resources</span></span>

[<span data-ttu-id="9ae54-123">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="9ae54-123">List functions</span></span>](er-functions-category-list.md)