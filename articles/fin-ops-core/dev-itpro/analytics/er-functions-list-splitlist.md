---
title: Funktionen SPLITLIST ER
description: Det här avsnittet innehåller information om hur funktionen SPLITLIST elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745579"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="4646d-103">Funktionen SPLITLIST ER</span><span class="sxs-lookup"><span data-stu-id="4646d-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4646d-104">`SPLITLIST`-funktionen delar upp angivna listan i underlistor (eller batchar) som var och en innehåller det definierade antalet poster.</span><span class="sxs-lookup"><span data-stu-id="4646d-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="4646d-105">Den returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.</span><span class="sxs-lookup"><span data-stu-id="4646d-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="4646d-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="4646d-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="4646d-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="4646d-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="4646d-108">Argument</span><span class="sxs-lookup"><span data-stu-id="4646d-108">Arguments</span></span>

<span data-ttu-id="4646d-109">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="4646d-109">`list`: *Record list*</span></span>

<span data-ttu-id="4646d-110">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="4646d-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="4646d-111">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="4646d-111">`number`: *Integer*</span></span>

<span data-ttu-id="4646d-112">Det maximala antalet poster per batch.</span><span class="sxs-lookup"><span data-stu-id="4646d-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="4646d-113">`on-demand reading flag`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="4646d-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="4646d-114">Ett *booleskt* värde som anger om element i underlistor ska genereras på begäran.</span><span class="sxs-lookup"><span data-stu-id="4646d-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="4646d-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4646d-115">Return values</span></span>

<span data-ttu-id="4646d-116">*Postlista*</span><span class="sxs-lookup"><span data-stu-id="4646d-116">*Record list*</span></span>

<span data-ttu-id="4646d-117">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="4646d-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4646d-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="4646d-118">Usage notes</span></span>

<span data-ttu-id="4646d-119">Listan av batchar som returneras innehåller följande element:</span><span class="sxs-lookup"><span data-stu-id="4646d-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="4646d-120">**Värde:** *lista*</span><span class="sxs-lookup"><span data-stu-id="4646d-120">**Value:** *List*</span></span>

    <span data-ttu-id="4646d-121">Listan över poster som tillhör den aktuella batchen.</span><span class="sxs-lookup"><span data-stu-id="4646d-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="4646d-122">**Batchnumber:** *heltal*</span><span class="sxs-lookup"><span data-stu-id="4646d-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="4646d-123">Numret på den aktuella batchen i den returnerade listan.</span><span class="sxs-lookup"><span data-stu-id="4646d-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="4646d-124">När inläsningsflaggan på begäran är inställd på **Sant**, genereras underlistor på begäran vilket möjliggör en minskning av minnesförbrukningen men kan orsaka prestandaförsämring om element inte används sekventiellt.</span><span class="sxs-lookup"><span data-stu-id="4646d-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="4646d-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="4646d-125">Example</span></span>

<span data-ttu-id="4646d-126">Följande bild visar hur en datakälla på en **rad** skapas av tre poster.</span><span class="sxs-lookup"><span data-stu-id="4646d-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="4646d-127">Den här listan är indelad i batchar som innehåller högst två poster.</span><span class="sxs-lookup"><span data-stu-id="4646d-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="4646d-128">Följande illustration visar layouten på det designade formatet.</span><span class="sxs-lookup"><span data-stu-id="4646d-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="4646d-129">I den här formatlayouten skapas bindningar till datakällans **rader** för att skapa utdata i XML-format.</span><span class="sxs-lookup"><span data-stu-id="4646d-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="4646d-130">Dessa utdata visar enskilda noder för varje batch och poster i den.</span><span class="sxs-lookup"><span data-stu-id="4646d-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="4646d-131">Följande illustration visar resultatet när det designade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="4646d-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="4646d-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4646d-132">Additional resources</span></span>

[<span data-ttu-id="4646d-133">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="4646d-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
