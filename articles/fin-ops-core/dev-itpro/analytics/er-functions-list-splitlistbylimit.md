---
title: Funktionen SPLITLISTBYLIMIT ER
description: Det här avsnittet innehåller information om hur funktionen SPLITLISTBYLIMIT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 54c78f36c93e1bdb472b84fc7ca6428d20088bad
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041870"
---
# <span data-ttu-id="65c2f-103"><a name="SPLITLISTBYLIMIT">Funktionen SPLITLISTBYLIMIT ER</a></span><span class="sxs-lookup"><span data-stu-id="65c2f-103"><a name="SPLITLISTBYLIMIT">SPLITLISTBYLIMIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65c2f-104">`SPLITLISTBYLIMIT`-funktionen delar upp den angivna listan i en ny lista över underlistor (batchar).</span><span class="sxs-lookup"><span data-stu-id="65c2f-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="65c2f-105">Antalet poster i varje batch beräknas dynamiskt.</span><span class="sxs-lookup"><span data-stu-id="65c2f-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="65c2f-106">Funktionen returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.</span><span class="sxs-lookup"><span data-stu-id="65c2f-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="65c2f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="65c2f-107">Syntax</span></span>

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="65c2f-108">Argument</span><span class="sxs-lookup"><span data-stu-id="65c2f-108">Arguments</span></span>

<span data-ttu-id="65c2f-109">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="65c2f-109">`list`: *Record list*</span></span>

<span data-ttu-id="65c2f-110">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="65c2f-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="65c2f-111">`limit value`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="65c2f-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="65c2f-112">Det högsta värdet för den gräns som används för att dela upp den ursprungliga listan i batchar.</span><span class="sxs-lookup"><span data-stu-id="65c2f-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="65c2f-113">`limit source`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="65c2f-113">`limit source`: *Field*</span></span>

<span data-ttu-id="65c2f-114">Den giltiga sökvägen för ett fält med typen *Heltal* eller *Realtaltal* i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="65c2f-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="65c2f-115">Värdet i det här fältet definierar steget som den totala summan ökas på.</span><span class="sxs-lookup"><span data-stu-id="65c2f-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="65c2f-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="65c2f-116">Return values</span></span>

<span data-ttu-id="65c2f-117">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="65c2f-117">*Record list*</span></span>

<span data-ttu-id="65c2f-118">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="65c2f-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="65c2f-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="65c2f-119">Usage notes</span></span>

<span data-ttu-id="65c2f-120">Listan av batchar som returneras innehåller följande element:</span><span class="sxs-lookup"><span data-stu-id="65c2f-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="65c2f-121">**Värde**: *lista*</span><span class="sxs-lookup"><span data-stu-id="65c2f-121">**Value**: *List*</span></span>

    <span data-ttu-id="65c2f-122">Listan över poster som tillhör den aktuella batchen.</span><span class="sxs-lookup"><span data-stu-id="65c2f-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="65c2f-123">**Batchnumber**: *heltal*</span><span class="sxs-lookup"><span data-stu-id="65c2f-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="65c2f-124">Numret på den aktuella batchen i den returnerade listan.</span><span class="sxs-lookup"><span data-stu-id="65c2f-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="65c2f-125">Gränsen tillämpas inte på en enskild artikel i ursprungslistan när gränskällan överskrider angiven gräns.</span><span class="sxs-lookup"><span data-stu-id="65c2f-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="65c2f-126">Exempel</span><span class="sxs-lookup"><span data-stu-id="65c2f-126">Example</span></span>

<span data-ttu-id="65c2f-127">Följande illustration visar flödet av ER-format (elektronisk rapportering).</span><span class="sxs-lookup"><span data-stu-id="65c2f-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="65c2f-128">I följande illustrationer visar de datakällor som används för det formatet.</span><span class="sxs-lookup"><span data-stu-id="65c2f-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="65c2f-129">Följande illustration visar resultatet när formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="65c2f-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="65c2f-130">I det här fallet är resultatet en förenklad lista över varuartiklar.</span><span class="sxs-lookup"><span data-stu-id="65c2f-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="65c2f-131">I följande exempel visas samma format som har justerats för att visa listan med varuartiklar i batchar, där varje enskild batch måste innehålla varuartiklar och inte överskrida gränsen på 9.</span><span class="sxs-lookup"><span data-stu-id="65c2f-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="65c2f-132">Följande illustration visar resultatet när det anpassade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="65c2f-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="65c2f-133">Gränsen tillämpas inte på den sista artikeln i den ursprungliga listan eftersom värdet (**11**) i gränskälla (**vikt**) överskrider angiven gräns (**9**).</span><span class="sxs-lookup"><span data-stu-id="65c2f-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="65c2f-134">För att ignorera underlistor under rapportgenerering använder du antingen `WHERE` eller uttrycket **Aktiverad** för respektive formatelement du önskar.</span><span class="sxs-lookup"><span data-stu-id="65c2f-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65c2f-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="65c2f-135">Additional resources</span></span>

[<span data-ttu-id="65c2f-136">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="65c2f-136">List functions</span></span>](er-functions-category-list.md)
