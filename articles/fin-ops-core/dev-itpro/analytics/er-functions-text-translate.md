---
title: Funktionen TRANSLATE ER
description: Det här avsnittet innehåller information om hur funktionen TRANSLATE elektronisk rapportering (ER) används.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51b9a2e25a9f1dfc08e9e0f7fc3ad84b359a6d1b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744249"
---
# <a name="translate-er-function"></a><span data-ttu-id="92aee-103">Funktionen TRANSLATE ER</span><span class="sxs-lookup"><span data-stu-id="92aee-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92aee-104">Funktionen `TRANSLATE` returnerar ett *sträng*-värde som innehåller resultatet av teckenersättningen för angiven text i tecken som ingår i en annan uppsättning.</span><span class="sxs-lookup"><span data-stu-id="92aee-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="92aee-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="92aee-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="92aee-106">Argument</span><span class="sxs-lookup"><span data-stu-id="92aee-106">Arguments</span></span>

<span data-ttu-id="92aee-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="92aee-107">`text`: *String*</span></span>

<span data-ttu-id="92aee-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="92aee-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="92aee-109">`pattern`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="92aee-109">`pattern`: *String*</span></span>

<span data-ttu-id="92aee-110">Den text som måste bytas ut.</span><span class="sxs-lookup"><span data-stu-id="92aee-110">The text that must be replaced.</span></span>

<span data-ttu-id="92aee-111">`replacement`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="92aee-111">`replacement`: *String*</span></span>

<span data-ttu-id="92aee-112">Den text som ska användas som ersättning.</span><span class="sxs-lookup"><span data-stu-id="92aee-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="92aee-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="92aee-113">Return values</span></span>

<span data-ttu-id="92aee-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="92aee-114">*String*</span></span>

<span data-ttu-id="92aee-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="92aee-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="92aee-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="92aee-116">Usage notes</span></span>

<span data-ttu-id="92aee-117">Funktionen `TRANSLATE` ersätter ett tecken i taget.</span><span class="sxs-lookup"><span data-stu-id="92aee-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="92aee-118">Funktionen ersätter det första tecknet i `text`-argumentet med `pattern`-argumentets första tecken och sedan det andra tecknet och följer samma flöde tills det är klart.</span><span class="sxs-lookup"><span data-stu-id="92aee-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="92aee-119">När ett tecken från `text` och `pattern`-argumenten matchar ersätts det med ett tecken från `replacement`-argumentet som ligger på samma position som tecknet från `pattern`-argumentet.</span><span class="sxs-lookup"><span data-stu-id="92aee-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="92aee-120">Om ett tecken förekommer flera gånger i `pattern`-argumentet, används `replacement` argumentmappning som motsvarar den första förekomsten av det här tecknet.</span><span class="sxs-lookup"><span data-stu-id="92aee-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="92aee-121">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="92aee-121">Example 1</span></span>

<span data-ttu-id="92aee-122">`TRANSLATE ("abcdef", "cd", "GH")` ersätter tecknet **"c"** i **den angivna "abcdef"**-texten med tecknet **"G"** i `replacement`-texten på grund av följande:</span><span class="sxs-lookup"><span data-stu-id="92aee-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="92aee-123">Tecknet **"c"** visas i `pattern`-texten i den första positionen.</span><span class="sxs-lookup"><span data-stu-id="92aee-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="92aee-124">Den första positionen av `replacement`-texten innehåller tecknet **"G"**.</span><span class="sxs-lookup"><span data-stu-id="92aee-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="92aee-125">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="92aee-125">Example 2</span></span>

<span data-ttu-id="92aee-126">`TRANSLATE ("abcdef", "ccd", "GH")` returnerar **"abGdef"**.</span><span class="sxs-lookup"><span data-stu-id="92aee-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="92aee-127">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="92aee-127">Example 3</span></span>

<span data-ttu-id="92aee-128">`TRANSLATE ("abccba", "abc", "123")` returnerar **"123321"**.</span><span class="sxs-lookup"><span data-stu-id="92aee-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92aee-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="92aee-129">Additional resources</span></span>

[<span data-ttu-id="92aee-130">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="92aee-130">Text functions</span></span>](er-functions-category-text.md)
