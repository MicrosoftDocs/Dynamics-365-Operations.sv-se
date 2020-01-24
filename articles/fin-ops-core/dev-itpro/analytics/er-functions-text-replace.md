---
title: REPLACE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen REPLACE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916877"
---
# <span data-ttu-id="0a530-103"><a name="REPLACE">REPLACE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="0a530-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a530-104">`REPLACE`-funktionen returnerar den angivna textsträngen som ett *sträng* värde när hela eller en del av den har ersatts med en annan sträng.</span><span class="sxs-lookup"><span data-stu-id="0a530-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a530-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a530-105">Syntax</span></span>

```
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="0a530-106">Argument</span><span class="sxs-lookup"><span data-stu-id="0a530-106">Arguments</span></span>

<span data-ttu-id="0a530-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0a530-107">`text`: *String*</span></span>

<span data-ttu-id="0a530-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="0a530-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="0a530-109">`pattern`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0a530-109">`pattern`: *String*</span></span>

<span data-ttu-id="0a530-110">Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som måste ersättas.</span><span class="sxs-lookup"><span data-stu-id="0a530-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="0a530-111">Om `regular expression flag`-argumentet är **SANT** innehåller det här argumentet ett reguljärt uttryck som definierar både ett sökmönster och en ersättningstext.</span><span class="sxs-lookup"><span data-stu-id="0a530-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="0a530-112">`replacement`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0a530-112">`replacement`: *String*</span></span>

<span data-ttu-id="0a530-113">Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som ersättning.</span><span class="sxs-lookup"><span data-stu-id="0a530-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="0a530-114">Om `regular expression flag`-argumentet är **SANT** används inte det här argumentet.</span><span class="sxs-lookup"><span data-stu-id="0a530-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="0a530-115">`regular expression flag`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="0a530-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="0a530-116">Ett *booleskt* värde som anger om ett reguljärt uttryck används för att göra ersättningen.</span><span class="sxs-lookup"><span data-stu-id="0a530-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="0a530-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0a530-117">Return values</span></span>

<span data-ttu-id="0a530-118">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0a530-118">*String*</span></span>

<span data-ttu-id="0a530-119">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="0a530-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0a530-120">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="0a530-120">Usage notes</span></span>

<span data-ttu-id="0a530-121">Om `regular expression flag`-argumentet är **SANT** returnerar den här funktionen den angivna strängen när den har ändrats genom att använda det reguljära uttrycket som anges av `pattern`-argumentet.</span><span class="sxs-lookup"><span data-stu-id="0a530-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="0a530-122">Vanliga uttryck används för att hitta tecken som måste ersättas.</span><span class="sxs-lookup"><span data-stu-id="0a530-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="0a530-123">Om argumentet `regular expression flag` är **FALSKT** fungerar den här funktionen som [TRANSLATE](er-functions-text-translate.md).</span><span class="sxs-lookup"><span data-stu-id="0a530-123">If the `regular expression flag` argument is **FALSE**, this function behaves like [TRANSLATE](er-functions-text-translate.md).</span></span> <span data-ttu-id="0a530-124">De tecken som anges av `replacement` argument används för att ersätta tecken som hittas.</span><span class="sxs-lookup"><span data-stu-id="0a530-124">The characters that are specified by the `replacement` argument are used to replace the characters that are found.</span></span> 

## <a name="example-1"></a><span data-ttu-id="0a530-125">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="0a530-125">Example 1</span></span>

<span data-ttu-id="0a530-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` tillämpar ett reguljärt uttryck som tar bort alla icke-numeriska symboler och returnerar **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="0a530-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="0a530-127">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="0a530-127">Example 2</span></span>

<span data-ttu-id="0a530-128">`REPLACE ("abcdef", "cd", "GH", false)` ersätter mönstret **"cd"** med strängen **"GH"** och returnerar **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="0a530-128">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a530-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0a530-129">Additional resources</span></span>

[<span data-ttu-id="0a530-130">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="0a530-130">Text functions</span></span>](er-functions-category-text.md)