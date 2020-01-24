---
title: Funktionen ORDERBY ER
description: Det här avsnittet innehåller information om hur funktionen ORDERBY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a6aed53dcad6d402fc2ca61ae0687016cdb3af5b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916210"
---
# <span data-ttu-id="0d07f-103"><a name="ORDERBY">Funktionen ORDERBY ER</a></span><span class="sxs-lookup"><span data-stu-id="0d07f-103"><a name="ORDERBY">ORDERBY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d07f-104">`ORDERBY`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har sorterats enligt de angivna argumenten.</span><span class="sxs-lookup"><span data-stu-id="0d07f-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="0d07f-105">Du kan definiera följande argument som uttryck.</span><span class="sxs-lookup"><span data-stu-id="0d07f-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d07f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d07f-106">Syntax</span></span>

```
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="0d07f-107">Argument</span><span class="sxs-lookup"><span data-stu-id="0d07f-107">Arguments</span></span>

<span data-ttu-id="0d07f-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="0d07f-108">`list`: *Record list*</span></span>

<span data-ttu-id="0d07f-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="0d07f-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0d07f-110">`expression 1`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="0d07f-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="0d07f-111">Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="0d07f-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="0d07f-112">Det refererade fältet måste vara ett fält av den primitiva datatypen.</span><span class="sxs-lookup"><span data-stu-id="0d07f-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="0d07f-113">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="0d07f-113">This argument is required.</span></span>

<span data-ttu-id="0d07f-114">`expression N`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="0d07f-114">`expression N`: *Field*</span></span>

<span data-ttu-id="0d07f-115">Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="0d07f-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="0d07f-116">Det refererade fältet måste vara ett fält av den primitiva datatypen.</span><span class="sxs-lookup"><span data-stu-id="0d07f-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="0d07f-117">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="0d07f-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0d07f-118">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0d07f-118">Return values</span></span>

<span data-ttu-id="0d07f-119">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="0d07f-119">*Record list*</span></span>

<span data-ttu-id="0d07f-120">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="0d07f-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="0d07f-121">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="0d07f-121">Example 1</span></span>

<span data-ttu-id="0d07f-122">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( ORDERBY( DS, DS. Value)).Value` att returnera textvärdet **"A"**.</span><span class="sxs-lookup"><span data-stu-id="0d07f-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0d07f-123">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="0d07f-123">Example 2</span></span>

<span data-ttu-id="0d07f-124">Om **Leverantör** konfigureras som en ER-datakälla som refererar till tabellen VendTable, kommer uttrycket `ORDERBY (Vendors, Vendors.'name()')` returneras en lista med leverantörerna sorterade efter namn i stigen ordning.</span><span class="sxs-lookup"><span data-stu-id="0d07f-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d07f-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0d07f-125">Additional resources</span></span>

[<span data-ttu-id="0d07f-126">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="0d07f-126">List functions</span></span>](er-functions-category-list.md)
