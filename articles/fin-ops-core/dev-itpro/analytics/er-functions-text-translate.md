---
title: Funktionen TRANSLATE ER
description: Det här avsnittet innehåller information om hur funktionen TRANSLATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 11954f3e48d8dc2257b3a0bc8768df47af3c5c0c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916716"
---
# <span data-ttu-id="84613-103"><a name="TRANSLATE">Funktionen TRANSLATE ER</a></span><span class="sxs-lookup"><span data-stu-id="84613-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84613-104">`TRANSLATE`-funktionen returnerar den angivna textsträngen som ett *sträng* värde när hela eller en del av den har ersatts med en annan sträng.</span><span class="sxs-lookup"><span data-stu-id="84613-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="84613-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="84613-105">Syntax</span></span>

```
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="84613-106">Argument</span><span class="sxs-lookup"><span data-stu-id="84613-106">Arguments</span></span>

<span data-ttu-id="84613-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="84613-107">`text`: *String*</span></span>

<span data-ttu-id="84613-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="84613-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="84613-109">`pattern`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="84613-109">`pattern`: *String*</span></span>

<span data-ttu-id="84613-110">Den text som måste bytas ut.</span><span class="sxs-lookup"><span data-stu-id="84613-110">The text that must be replaced.</span></span>

<span data-ttu-id="84613-111">`replacement`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="84613-111">`replacement`: *String*</span></span>

<span data-ttu-id="84613-112">Den text som ska användas som ersättning.</span><span class="sxs-lookup"><span data-stu-id="84613-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="84613-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="84613-113">Return values</span></span>

<span data-ttu-id="84613-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="84613-114">*String*</span></span>

<span data-ttu-id="84613-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="84613-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="84613-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="84613-116">Example</span></span>

<span data-ttu-id="84613-117">`TRANSLATE ("abcdef", "cd", "GH")` ersätter mönstret **"cd"** med strängen **"GH"** och returnerar **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="84613-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="84613-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="84613-118">Additional resources</span></span>

[<span data-ttu-id="84613-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="84613-119">Text functions</span></span>](er-functions-category-text.md)