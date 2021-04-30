---
title: DATEVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DATEVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: cfaf183c61d3663442cbc244239b872b9e1957bb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891243"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="5feb6-103">DATEVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="5feb6-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5feb6-104">`DATEVALUE`-funktionen returnerar ett värde för *Datum* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) till ett datumvärde.</span><span class="sxs-lookup"><span data-stu-id="5feb6-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="5feb6-105">Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="5feb6-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="5feb6-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="5feb6-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="5feb6-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="5feb6-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="5feb6-108">Argument</span><span class="sxs-lookup"><span data-stu-id="5feb6-108">Arguments</span></span>

<span data-ttu-id="5feb6-109">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5feb6-109">`text`: *String*</span></span>

<span data-ttu-id="5feb6-110">Text som representerar värdet till format.</span><span class="sxs-lookup"><span data-stu-id="5feb6-110">Text that represents the value to format.</span></span>

<span data-ttu-id="5feb6-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5feb6-111">`format`: *String*</span></span>

<span data-ttu-id="5feb6-112">Formatet för en given text.</span><span class="sxs-lookup"><span data-stu-id="5feb6-112">The format of the given text.</span></span>

<span data-ttu-id="5feb6-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5feb6-113">`culture`: *String*</span></span>

<span data-ttu-id="5feb6-114">Den kultur som används för att formatera den givna texten.</span><span class="sxs-lookup"><span data-stu-id="5feb6-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="5feb6-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="5feb6-115">Return values</span></span>

<span data-ttu-id="5feb6-116">*Datum*</span><span class="sxs-lookup"><span data-stu-id="5feb6-116">*Date*</span></span>

<span data-ttu-id="5feb6-117">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="5feb6-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5feb6-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="5feb6-118">Usage notes</span></span>

<span data-ttu-id="5feb6-119">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="5feb6-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="5feb6-120">Om till exempel funktionen `DATEVALUE` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="5feb6-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="5feb6-121">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="5feb6-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="5feb6-122">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="5feb6-122">Example 1</span></span>

<span data-ttu-id="5feb6-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returnerar datumvärdet **21 december 2016**, baserat på det angivna anpassade formatet och standardprogrammets **EN-US**-kultur.</span><span class="sxs-lookup"><span data-stu-id="5feb6-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="5feb6-124">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="5feb6-124">Example 2</span></span>

<span data-ttu-id="5feb6-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returnerar datumvärdet **21 januari 2016**, baserat på angivet anpassat format och kultur.</span><span class="sxs-lookup"><span data-stu-id="5feb6-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="5feb6-126">Men `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum för den angivna kulturen.</span><span class="sxs-lookup"><span data-stu-id="5feb6-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5feb6-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5feb6-127">Additional resources</span></span>

[<span data-ttu-id="5feb6-128">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="5feb6-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]