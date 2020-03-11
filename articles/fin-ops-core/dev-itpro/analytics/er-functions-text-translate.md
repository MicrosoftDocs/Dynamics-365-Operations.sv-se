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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040927"
---
# <span data-ttu-id="d9674-103"><a name="TRANSLATE">Funktionen TRANSLATE ER</a></span><span class="sxs-lookup"><span data-stu-id="d9674-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9674-104">`TRANSLATE`-funktionen returnerar den angivna textsträngen som ett *sträng* värde när hela eller en del av den har ersatts med en annan sträng.</span><span class="sxs-lookup"><span data-stu-id="d9674-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9674-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9674-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="d9674-106">Argument</span><span class="sxs-lookup"><span data-stu-id="d9674-106">Arguments</span></span>

<span data-ttu-id="d9674-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="d9674-107">`text`: *String*</span></span>

<span data-ttu-id="d9674-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="d9674-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="d9674-109">`pattern`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="d9674-109">`pattern`: *String*</span></span>

<span data-ttu-id="d9674-110">Den text som måste bytas ut.</span><span class="sxs-lookup"><span data-stu-id="d9674-110">The text that must be replaced.</span></span>

<span data-ttu-id="d9674-111">`replacement`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="d9674-111">`replacement`: *String*</span></span>

<span data-ttu-id="d9674-112">Den text som ska användas som ersättning.</span><span class="sxs-lookup"><span data-stu-id="d9674-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="d9674-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="d9674-113">Return values</span></span>

<span data-ttu-id="d9674-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="d9674-114">*String*</span></span>

<span data-ttu-id="d9674-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="d9674-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d9674-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="d9674-116">Example</span></span>

<span data-ttu-id="d9674-117">`TRANSLATE ("abcdef", "cd", "GH")` ersätter mönstret **"cd"** med strängen **"GH"** och returnerar **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="d9674-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9674-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d9674-118">Additional resources</span></span>

[<span data-ttu-id="d9674-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="d9674-119">Text functions</span></span>](er-functions-category-text.md)
