---
title: DATEVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DATEVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 43e65055b0803ed330a19568f9565c3fae488ab2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682423"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="9d9b1-103">DATEVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="9d9b1-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d9b1-104">`DATEVALUE`-funktionen returnerar ett värde för *Datum* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) till ett datumvärde.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="9d9b1-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="9d9b1-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="9d9b1-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="9d9b1-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="9d9b1-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="9d9b1-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="9d9b1-108">Argument</span><span class="sxs-lookup"><span data-stu-id="9d9b1-108">Arguments</span></span>

<span data-ttu-id="9d9b1-109">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9d9b1-109">`text`: *String*</span></span>

<span data-ttu-id="9d9b1-110">Text som representerar värdet till format.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-110">Text that represents the value to format.</span></span>

<span data-ttu-id="9d9b1-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9d9b1-111">`format`: *String*</span></span>

<span data-ttu-id="9d9b1-112">Formatet för en given text.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-112">The format of the given text.</span></span>

<span data-ttu-id="9d9b1-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9d9b1-113">`culture`: *String*</span></span>

<span data-ttu-id="9d9b1-114">Den kultur som används för att formatera den givna texten.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="9d9b1-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9d9b1-115">Return values</span></span>

<span data-ttu-id="9d9b1-116">*Datum*</span><span class="sxs-lookup"><span data-stu-id="9d9b1-116">*Date*</span></span>

<span data-ttu-id="9d9b1-117">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9d9b1-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="9d9b1-118">Usage notes</span></span>

<span data-ttu-id="9d9b1-119">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="9d9b1-120">Om till exempel funktionen `DATEVALUE` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="9d9b1-121">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="9d9b1-122">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="9d9b1-122">Example 1</span></span>

<span data-ttu-id="9d9b1-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returnerar datumvärdet **21 december 2016**, baserat på det angivna anpassade formatet och standardprogrammets **EN-US**-kultur.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="9d9b1-124">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="9d9b1-124">Example 2</span></span>

<span data-ttu-id="9d9b1-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returnerar datumvärdet **21 januari 2016**, baserat på angivet anpassat format och kultur.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="9d9b1-126">Men `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum för den angivna kulturen.</span><span class="sxs-lookup"><span data-stu-id="9d9b1-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d9b1-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9d9b1-127">Additional resources</span></span>

[<span data-ttu-id="9d9b1-128">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="9d9b1-128">Date and time functions</span></span>](er-functions-category-datetime.md)
