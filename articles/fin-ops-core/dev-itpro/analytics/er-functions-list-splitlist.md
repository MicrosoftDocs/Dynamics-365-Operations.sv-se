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
ms.openlocfilehash: 56ef02e3ea0ca2207ccdc79468a9ea4c1fbe8f95
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041893"
---
# <span data-ttu-id="c79d7-103"><a name="SPLITLIST">Funktionen SPLITLIST ER</a></span><span class="sxs-lookup"><span data-stu-id="c79d7-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c79d7-104">`SPLITLIST`-funktionen delar upp angivna listan i underlistor (eller batchar) som var och en innehåller det definierade antalet poster.</span><span class="sxs-lookup"><span data-stu-id="c79d7-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="c79d7-105">Den returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.</span><span class="sxs-lookup"><span data-stu-id="c79d7-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="c79d7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c79d7-106">Syntax</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="c79d7-107">Argument</span><span class="sxs-lookup"><span data-stu-id="c79d7-107">Arguments</span></span>

<span data-ttu-id="c79d7-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c79d7-108">`list`: *Record list*</span></span>

<span data-ttu-id="c79d7-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="c79d7-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="c79d7-110">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="c79d7-110">`number`: *Integer*</span></span>

<span data-ttu-id="c79d7-111">Det maximala antalet poster per batch.</span><span class="sxs-lookup"><span data-stu-id="c79d7-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="c79d7-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c79d7-112">Return values</span></span>

<span data-ttu-id="c79d7-113">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="c79d7-113">*Record list*</span></span>

<span data-ttu-id="c79d7-114">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="c79d7-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c79d7-115">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="c79d7-115">Usage notes</span></span>

<span data-ttu-id="c79d7-116">Listan av batchar som returneras innehåller följande element:</span><span class="sxs-lookup"><span data-stu-id="c79d7-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="c79d7-117">**Värde:** *lista*</span><span class="sxs-lookup"><span data-stu-id="c79d7-117">**Value:** *List*</span></span>

    <span data-ttu-id="c79d7-118">Listan över poster som tillhör den aktuella batchen.</span><span class="sxs-lookup"><span data-stu-id="c79d7-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="c79d7-119">**Batchnumber:** *heltal*</span><span class="sxs-lookup"><span data-stu-id="c79d7-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="c79d7-120">Numret på den aktuella batchen i den returnerade listan.</span><span class="sxs-lookup"><span data-stu-id="c79d7-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="c79d7-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="c79d7-121">Example</span></span>

<span data-ttu-id="c79d7-122">Följande bild visar hur en datakälla på en **rad** skapas av tre poster.</span><span class="sxs-lookup"><span data-stu-id="c79d7-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="c79d7-123">Den här listan är indelad i batchar som innehåller högst två poster.</span><span class="sxs-lookup"><span data-stu-id="c79d7-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="c79d7-124">Följande illustration visar layouten på det designade formatet.</span><span class="sxs-lookup"><span data-stu-id="c79d7-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="c79d7-125">I den här formatlayouten skapas bindningar till datakällans **rader** för att skapa utdata i XML-format.</span><span class="sxs-lookup"><span data-stu-id="c79d7-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="c79d7-126">Dessa utdata visar enskilda noder för varje batch och poster i den.</span><span class="sxs-lookup"><span data-stu-id="c79d7-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="c79d7-127">Följande illustration visar resultatet när det designade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="c79d7-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="c79d7-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c79d7-128">Additional resources</span></span>

[<span data-ttu-id="c79d7-129">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="c79d7-129">List functions</span></span>](er-functions-category-list.md)
