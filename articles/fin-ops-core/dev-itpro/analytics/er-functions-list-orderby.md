---
title: Funktionen ORDERBY ER
description: Det här avsnittet innehåller information om hur funktionen ORDERBY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 51da7f3766f5af901c8be6668bc2511cd8e2f9e9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753202"
---
# <a name="orderby-er-function"></a><span data-ttu-id="ee291-103">Funktionen ORDERBY ER</span><span class="sxs-lookup"><span data-stu-id="ee291-103">ORDERBY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee291-104">`ORDERBY`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har sorterats enligt de angivna argumenten.</span><span class="sxs-lookup"><span data-stu-id="ee291-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="ee291-105">Du kan definiera följande argument som uttryck.</span><span class="sxs-lookup"><span data-stu-id="ee291-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee291-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee291-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="ee291-107">Argument</span><span class="sxs-lookup"><span data-stu-id="ee291-107">Arguments</span></span>

<span data-ttu-id="ee291-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="ee291-108">`list`: *Record list*</span></span>

<span data-ttu-id="ee291-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="ee291-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ee291-110">`expression 1`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="ee291-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="ee291-111">Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="ee291-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="ee291-112">Det refererade fältet måste vara ett fält av den primitiva datatypen.</span><span class="sxs-lookup"><span data-stu-id="ee291-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="ee291-113">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="ee291-113">This argument is required.</span></span>

<span data-ttu-id="ee291-114">`expression N`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="ee291-114">`expression N`: *Field*</span></span>

<span data-ttu-id="ee291-115">Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="ee291-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="ee291-116">Det refererade fältet måste vara ett fält av den primitiva datatypen.</span><span class="sxs-lookup"><span data-stu-id="ee291-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="ee291-117">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="ee291-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee291-118">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ee291-118">Return values</span></span>

<span data-ttu-id="ee291-119">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="ee291-119">*Record list*</span></span>

<span data-ttu-id="ee291-120">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="ee291-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="ee291-121">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="ee291-121">Example 1</span></span>

<span data-ttu-id="ee291-122">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( ORDERBY( DS, DS. Value)).Value` att returnera textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="ee291-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ee291-123">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="ee291-123">Example 2</span></span>

<span data-ttu-id="ee291-124">Om **Leverantör** konfigureras som en ER-datakälla som refererar till tabellen VendTable, kommer uttrycket `ORDERBY (Vendors, Vendors.'name()')` returneras en lista med leverantörerna sorterade efter namn i stigen ordning.</span><span class="sxs-lookup"><span data-stu-id="ee291-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee291-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ee291-125">Additional resources</span></span>

[<span data-ttu-id="ee291-126">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="ee291-126">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]