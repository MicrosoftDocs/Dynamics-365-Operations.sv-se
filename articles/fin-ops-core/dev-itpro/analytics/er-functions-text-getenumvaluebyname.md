---
title: Funktionen GETENUMVALUEBYNAME ER
description: Det här avsnittet innehåller information om hur funktionen GETENUMVALUEBYNAME elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 4ded0c62b4556b21e731cd9b98db2863ec6ec442
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916854"
---
# <span data-ttu-id="953dd-103"><a name="GETENUMVALUEBYNAME">Funktionen GETENUMVALUEBYNAME ER</a></span><span class="sxs-lookup"><span data-stu-id="953dd-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="953dd-104">`GETENUMVALUEBYNAME`-funktionen söker efter ett specifikt värde för *uppräkning* i angiven uppräkningsdatakälla med hjälp av det uppräkningsnamn som anges som ett *sträng*-värde.</span><span class="sxs-lookup"><span data-stu-id="953dd-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="953dd-105">Om *Enum*-värdet hittas returnerar funktionen den.</span><span class="sxs-lookup"><span data-stu-id="953dd-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="953dd-106">Annars returnerar funktionen **null**-uppräkningsvärdet.</span><span class="sxs-lookup"><span data-stu-id="953dd-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="953dd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="953dd-107">Syntax</span></span>

```
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="953dd-108">Argument</span><span class="sxs-lookup"><span data-stu-id="953dd-108">Arguments</span></span>

<span data-ttu-id="953dd-109">`enumeration data source path`: *Uppräkning*</span><span class="sxs-lookup"><span data-stu-id="953dd-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="953dd-110">Den giltiga sökvägen till en datakälla för någon av följande uppräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="953dd-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="953dd-111">Elektronisk rapportering (ER) modelluppräkning</span><span class="sxs-lookup"><span data-stu-id="953dd-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="953dd-112">ER-formatuppräkning</span><span class="sxs-lookup"><span data-stu-id="953dd-112">ER format enumeration</span></span>
- <span data-ttu-id="953dd-113">Microsoft Dynamics 365 Finance uppräkning</span><span class="sxs-lookup"><span data-stu-id="953dd-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="953dd-114">`enumeration value text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="953dd-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="953dd-115">Ett strängvärde som representerar namnet på ett enda uppräkningsvärde.</span><span class="sxs-lookup"><span data-stu-id="953dd-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="953dd-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="953dd-116">Return values</span></span>

<span data-ttu-id="953dd-117">Kan ha värdet null *Enum*</span><span class="sxs-lookup"><span data-stu-id="953dd-117">Nullable *Enum*</span></span>

<span data-ttu-id="953dd-118">Det resulterande fasttextvärde.</span><span class="sxs-lookup"><span data-stu-id="953dd-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="953dd-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="953dd-119">Usage notes</span></span>

<span data-ttu-id="953dd-120">Inget undantag genereras om *fasttextvärde* inte hittas med hjälp av namnet på uppräkningsvärdet som anges som ett *sträng*-värde.</span><span class="sxs-lookup"><span data-stu-id="953dd-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="953dd-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="953dd-121">Example</span></span>

<span data-ttu-id="953dd-122">I följande illustration introduceras uppräkningen **ReportDirection** i en datamodell.</span><span class="sxs-lookup"><span data-stu-id="953dd-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="953dd-123">Observera att etiketter definieras för uppräkningsvärden.</span><span class="sxs-lookup"><span data-stu-id="953dd-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="953dd-124">Illustrationen som följer visar dessa detaljer:</span><span class="sxs-lookup"><span data-stu-id="953dd-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="953dd-125">**$Direction** datakällan har konfigurerats i en ER-rapport.</span><span class="sxs-lookup"><span data-stu-id="953dd-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="953dd-126">Den här datakällan konfigureras baserat på den **ReportDirection** modelluppräkning.</span><span class="sxs-lookup"><span data-stu-id="953dd-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="953dd-127">`$IsArrivals`-uttrycket är utformat för att använda modelluppräkningsbaserad **$Direction** datakälla som en parameter för denna funktion.</span><span class="sxs-lookup"><span data-stu-id="953dd-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="953dd-128">Värdet för detta jämförelseuttryck är **SANT**.</span><span class="sxs-lookup"><span data-stu-id="953dd-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="953dd-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="953dd-129">Additional resources</span></span>

[<span data-ttu-id="953dd-130">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="953dd-130">Text functions</span></span>](er-functions-category-text.md)
