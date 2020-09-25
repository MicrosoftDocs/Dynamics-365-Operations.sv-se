---
title: Funktionen SPLITLIST ER
description: Det här avsnittet innehåller information om hur funktionen SPLITLIST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 950fc711f0e28eaee7fabc437ee16a022e1b705e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744801"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="09874-103">Funktionen SPLITLIST ER</span><span class="sxs-lookup"><span data-stu-id="09874-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09874-104">`SPLITLIST`-funktionen delar upp angivna listan i underlistor (eller batchar) som var och en innehåller det definierade antalet poster.</span><span class="sxs-lookup"><span data-stu-id="09874-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="09874-105">Den returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.</span><span class="sxs-lookup"><span data-stu-id="09874-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="09874-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="09874-106">Syntax</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="09874-107">Argument</span><span class="sxs-lookup"><span data-stu-id="09874-107">Arguments</span></span>

<span data-ttu-id="09874-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="09874-108">`list`: *Record list*</span></span>

<span data-ttu-id="09874-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="09874-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="09874-110">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="09874-110">`number`: *Integer*</span></span>

<span data-ttu-id="09874-111">Det maximala antalet poster per batch.</span><span class="sxs-lookup"><span data-stu-id="09874-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="09874-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="09874-112">Return values</span></span>

<span data-ttu-id="09874-113">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="09874-113">*Record list*</span></span>

<span data-ttu-id="09874-114">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="09874-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="09874-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="09874-115">Usage notes</span></span>

<span data-ttu-id="09874-116">Listan av batchar som returneras innehåller följande element:</span><span class="sxs-lookup"><span data-stu-id="09874-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="09874-117">**Värde:** *lista*</span><span class="sxs-lookup"><span data-stu-id="09874-117">**Value:** *List*</span></span>

    <span data-ttu-id="09874-118">Listan över poster som tillhör den aktuella batchen.</span><span class="sxs-lookup"><span data-stu-id="09874-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="09874-119">**Batchnumber:** *heltal*</span><span class="sxs-lookup"><span data-stu-id="09874-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="09874-120">Numret på den aktuella batchen i den returnerade listan.</span><span class="sxs-lookup"><span data-stu-id="09874-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="09874-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="09874-121">Example</span></span>

<span data-ttu-id="09874-122">Följande bild visar hur en datakälla på en **rad** skapas av tre poster.</span><span class="sxs-lookup"><span data-stu-id="09874-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="09874-123">Den här listan är indelad i batchar som innehåller högst två poster.</span><span class="sxs-lookup"><span data-stu-id="09874-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="09874-124">Följande illustration visar layouten på det designade formatet.</span><span class="sxs-lookup"><span data-stu-id="09874-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="09874-125">I den här formatlayouten skapas bindningar till datakällans **rader** för att skapa utdata i XML-format.</span><span class="sxs-lookup"><span data-stu-id="09874-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="09874-126">Dessa utdata visar enskilda noder för varje batch och poster i den.</span><span class="sxs-lookup"><span data-stu-id="09874-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="09874-127">Följande illustration visar resultatet när det designade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="09874-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="09874-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="09874-128">Additional resources</span></span>

[<span data-ttu-id="09874-129">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="09874-129">List functions</span></span>](er-functions-category-list.md)
