---
title: Funktionen DATETIMEVALUE ER
description: Det här avsnittet innehåller information om hur funktionen DATETIMEVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: de601ad08b85797a4241ef74ecb3eba37eda37ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917544"
---
# <span data-ttu-id="b1e59-103"><a name="DATETIMEVALUE">Funktionen DATETIMEVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="b1e59-103"><a name="DATETIMEVALUE">DATETIMEVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1e59-104">`DATETIMEVALUE`-funktionen returnerar ett värde för *DateTime* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="b1e59-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="b1e59-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b1e59-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b1e59-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="b1e59-106">Syntax 1</span></span>

```
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="b1e59-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="b1e59-107">Syntax 2</span></span>

```
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="b1e59-108">Argument</span><span class="sxs-lookup"><span data-stu-id="b1e59-108">Arguments</span></span>

<span data-ttu-id="b1e59-109">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b1e59-109">`text`: *String*</span></span>

<span data-ttu-id="b1e59-110">Text som representerar värdet till format.</span><span class="sxs-lookup"><span data-stu-id="b1e59-110">Text that represents the value to format.</span></span>

<span data-ttu-id="b1e59-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b1e59-111">`format`: *String*</span></span>

<span data-ttu-id="b1e59-112">Formatet för en given text.</span><span class="sxs-lookup"><span data-stu-id="b1e59-112">The format of the given text.</span></span>

<span data-ttu-id="b1e59-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b1e59-113">`culture`: *String*</span></span>

<span data-ttu-id="b1e59-114">Den kultur som används för att formatera den givna texten.</span><span class="sxs-lookup"><span data-stu-id="b1e59-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b1e59-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b1e59-115">Return values</span></span>

<span data-ttu-id="b1e59-116">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="b1e59-116">*DateTime*</span></span>

<span data-ttu-id="b1e59-117">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="b1e59-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b1e59-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b1e59-118">Usage notes</span></span>

<span data-ttu-id="b1e59-119">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="b1e59-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="b1e59-120">Om till exempel funktionen `DATETIMEVALUE` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="b1e59-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="b1e59-121">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b1e59-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="b1e59-122">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b1e59-122">Example 1</span></span>

<span data-ttu-id="b1e59-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returnerar **2:55:00 är den 21 december 2016**, baserat på det angivna anpassade formatet och standardprogrammets **EN-US**-kultur.</span><span class="sxs-lookup"><span data-stu-id="b1e59-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="b1e59-124">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b1e59-124">Example 2</span></span>

<span data-ttu-id="b1e59-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returnerar **2:55:00 på 21 december 2016**, baserat på det angivna anpassade formatet och kulturen.</span><span class="sxs-lookup"><span data-stu-id="b1e59-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="b1e59-126">Men `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum/tidsvärde för den angivna kulturen.</span><span class="sxs-lookup"><span data-stu-id="b1e59-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b1e59-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b1e59-127">Additional resources</span></span>

[<span data-ttu-id="b1e59-128">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="b1e59-128">Date and time functions</span></span>](er-functions-category-datetime.md)