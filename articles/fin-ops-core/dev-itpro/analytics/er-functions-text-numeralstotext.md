---
title: Funktionen NUMERALSTOTEXT ER
description: Det här avsnittet innehåller information om hur funktionen NUMERALSTOTEXT elektronisk rapportering (ER) används.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4af3926998d128f8269ab9af46caeb8be896509
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680228"
---
# <a name="numeralstotext-er-function"></a><span data-ttu-id="b5ba8-103">Funktionen NUMERALSTOTEXT ER</span><span class="sxs-lookup"><span data-stu-id="b5ba8-103">NUMERALSTOTEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5ba8-104">`NUMERALSTOTEXT`-funktionen returnerar det angivna talet som ett *sträng*-värde när det har stavats ut (konverteras till textsträngar) på det angivna språket.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5ba8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5ba8-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="b5ba8-106">Argument</span><span class="sxs-lookup"><span data-stu-id="b5ba8-106">Arguments</span></span>

<span data-ttu-id="b5ba8-107">`number`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="b5ba8-108">Ett numeriskt värde som anger det tal som måste anges.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="b5ba8-109">`language`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-109">`language`: *String*</span></span>

<span data-ttu-id="b5ba8-110">Ett *sträng*-värde som representerar språkkoden.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="b5ba8-111">`currency`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-111">`currency`: *String*</span></span>

<span data-ttu-id="b5ba8-112">Ett *sträng*-värde som representerar valutakoden.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="b5ba8-113">`print currency name flag`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="b5ba8-114">Ett *booleskt* värde som anger om ett valutanamn måste läggas till i den stavade texten.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="b5ba8-115">`decimal points`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="b5ba8-116">Ett *heltals*-värde som anger antalet decimaler som den stavade texten ska ha.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="b5ba8-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b5ba8-117">Return values</span></span>

<span data-ttu-id="b5ba8-118">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b5ba8-118">*String*</span></span>

<span data-ttu-id="b5ba8-119">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b5ba8-120">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b5ba8-120">Usage notes</span></span>

<span data-ttu-id="b5ba8-121">Språkkod är valfritt.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-121">The language code is optional.</span></span> <span data-ttu-id="b5ba8-122">Om den är definierad som en tom sträng används istället språkkoden för löpande kontext.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="b5ba8-123">Standardspråk är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="b5ba8-124">Språkkoden för den löpande kontexten definieras i en **mapp** eller **fil**-element i det elektroniska rapporteringsformatet (ER) som körs.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="b5ba8-125">Valutakoden är valfri.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-125">The currency code is optional.</span></span> <span data-ttu-id="b5ba8-126">Om den är definierad som en tom sträng används istället företagsvaluta för löpande kontext.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="b5ba8-127">Argumenten `print currency name flag` och `decimal points` analyseras endast för följande språkkoder: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** och **RU**.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="b5ba8-128">I tillägg analyseras argumentet `print currency name flag` endast för företag vars länder eller regioner stöder valutanamnnedgång.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="b5ba8-129">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b5ba8-129">Example 1</span></span>

<span data-ttu-id="b5ba8-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returnerar **"1234 och 56"**.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b5ba8-131">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b5ba8-131">Example 2</span></span>

<span data-ttu-id="b5ba8-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returnerar **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="b5ba8-133">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="b5ba8-133">Example 3</span></span>

<span data-ttu-id="b5ba8-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returnerar **"сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="b5ba8-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5ba8-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b5ba8-135">Additional resources</span></span>

[<span data-ttu-id="b5ba8-136">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="b5ba8-136">Text functions</span></span>](er-functions-category-text.md)
