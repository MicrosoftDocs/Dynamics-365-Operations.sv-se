---
title: Funktionen DATEFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen DATEFORMAT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890920"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="e93f6-103">Funktionen DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="e93f6-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e93f6-104">`DATEFORMAT`-funktionen returnerar ett värde för *Sträng* som visar ett givet datumvärde som text i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="e93f6-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="e93f6-105">Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="e93f6-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e93f6-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="e93f6-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="e93f6-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="e93f6-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="e93f6-108">Argument</span><span class="sxs-lookup"><span data-stu-id="e93f6-108">Arguments</span></span>

<span data-ttu-id="e93f6-109">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="e93f6-109">`date`: *Date*</span></span>

<span data-ttu-id="e93f6-110">Ett datumvärde som representerar datumet som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="e93f6-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="e93f6-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e93f6-111">`format`: *String*</span></span>

<span data-ttu-id="e93f6-112">Formatet på utdatasträngen</span><span class="sxs-lookup"><span data-stu-id="e93f6-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="e93f6-113">Formatsträngen är skiftlägeskänslig när du använder antingen ett standardformat eller ett anpassat format.</span><span class="sxs-lookup"><span data-stu-id="e93f6-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="e93f6-114">Till exempel [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" formatspecificeraren returnerar datumet med hjälp av det korta datummönstret, medan standard "D" formatspecificeraren returnerar datumet med hjälp av det långa datummönstret.</span><span class="sxs-lookup"><span data-stu-id="e93f6-114">For example, the [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="e93f6-115">Dessutom returnerar den [anpassade](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" formatspecificeraren månaden från 1 till 12, medan den anpassade "m" formatspecificeraren returnerar minuten från 0 till 59.</span><span class="sxs-lookup"><span data-stu-id="e93f6-115">Additionally, the [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="e93f6-116">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e93f6-116">`culture`: *String*</span></span>

<span data-ttu-id="e93f6-117">Kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="e93f6-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="e93f6-118">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e93f6-118">Return values</span></span>

<span data-ttu-id="e93f6-119">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="e93f6-119">*String*</span></span>

<span data-ttu-id="e93f6-120">Det resulterande strängvärdet.</span><span class="sxs-lookup"><span data-stu-id="e93f6-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e93f6-121">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="e93f6-121">Usage notes</span></span>

<span data-ttu-id="e93f6-122">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="e93f6-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="e93f6-123">Om till exempel funktionen `DATEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="e93f6-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="e93f6-124">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="e93f6-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="e93f6-125">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e93f6-125">Example 1</span></span>

<span data-ttu-id="e93f6-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returnerar det aktuella datumet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="e93f6-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="e93f6-127">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e93f6-127">Example 2</span></span>

<span data-ttu-id="e93f6-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="e93f6-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e93f6-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e93f6-129">Additional resources</span></span>

[<span data-ttu-id="e93f6-130">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e93f6-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]