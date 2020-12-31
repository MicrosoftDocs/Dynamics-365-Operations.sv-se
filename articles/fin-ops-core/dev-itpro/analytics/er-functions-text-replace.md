---
title: REPLACE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen REPLACE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3c9d3b6748ecb1680586a2d47a425b5ef98551f1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682930"
---
# <a name="replace-er-function"></a><span data-ttu-id="7fd3a-103">REPLACE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="7fd3a-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7fd3a-104">`REPLACE`-funktionen returnerar den angivna textsträngen som ett *sträng* värde när hela eller en del av den har ersatts med en annan sträng.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="7fd3a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fd3a-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="7fd3a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="7fd3a-106">Arguments</span></span>

<span data-ttu-id="7fd3a-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="7fd3a-107">`text`: *String*</span></span>

<span data-ttu-id="7fd3a-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="7fd3a-109">`pattern`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="7fd3a-109">`pattern`: *String*</span></span>

<span data-ttu-id="7fd3a-110">Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som måste ersättas.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="7fd3a-111">Om `regular expression flag`-argumentet är **SANT** innehåller det här argumentet ett reguljärt uttryck som definierar både ett sökmönster och en ersättningstext.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="7fd3a-112">`replacement`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="7fd3a-112">`replacement`: *String*</span></span>

<span data-ttu-id="7fd3a-113">Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som ersättning.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="7fd3a-114">Om `regular expression flag`-argumentet är **SANT** används inte det här argumentet.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="7fd3a-115">`regular expression flag`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="7fd3a-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="7fd3a-116">Ett *booleskt* värde som anger om ett reguljärt uttryck används för att göra ersättningen.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="7fd3a-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="7fd3a-117">Return values</span></span>

<span data-ttu-id="7fd3a-118">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7fd3a-118">*String*</span></span>

<span data-ttu-id="7fd3a-119">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7fd3a-120">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="7fd3a-120">Usage notes</span></span>

<span data-ttu-id="7fd3a-121">Om `regular expression flag`-argumentet är **SANT** returnerar den här funktionen den angivna strängen när den har ändrats genom att använda det reguljära uttrycket som anges av `pattern`-argumentet.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="7fd3a-122">Vanliga uttryck används för att hitta tecken som måste ersättas.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="7fd3a-123">Om argumentet `regular expression flag` är **FALSKT**, returnerar funktionen den angivna strängen efter att tecken uppsättningen som har definierats i argumentet `pattern` ersatts av tecknen i argumentet `replacement`.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="7fd3a-124">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="7fd3a-124">Example 1</span></span>

<span data-ttu-id="7fd3a-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` tillämpar ett reguljärt uttryck som tar bort alla icke-numeriska symboler och returnerar **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="7fd3a-126">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="7fd3a-126">Example 2</span></span>

<span data-ttu-id="7fd3a-127">`REPLACE ("abcdef", "cd", "GH", false)` ersätter mönstret **"cd"** med strängen **"GH"** och returnerar **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="7fd3a-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7fd3a-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7fd3a-128">Additional resources</span></span>

[<span data-ttu-id="7fd3a-129">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="7fd3a-129">Text functions</span></span>](er-functions-category-text.md)
