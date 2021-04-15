---
title: Funktionen DATETIMEFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen DATETIMEFORMAT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 859753c04e3b3d3b61d9a61edaf396637ed5a003
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746997"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="9c1b6-103">Funktionen DATETIMEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="9c1b6-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c1b6-104">`DATETIMEFORMAT`-funktionen returnerar ett värde för *Sträng* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="9c1b6-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="9c1b6-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="9c1b6-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="9c1b6-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="9c1b6-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="9c1b6-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="9c1b6-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="9c1b6-108">Argument</span><span class="sxs-lookup"><span data-stu-id="9c1b6-108">Arguments</span></span>

<span data-ttu-id="9c1b6-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="9c1b6-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="9c1b6-110">Ett datum-/tidsvärde som representerar det datum och den tid som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="9c1b6-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9c1b6-111">`format`: *String*</span></span>

<span data-ttu-id="9c1b6-112">Formatet på utdatasträngen</span><span class="sxs-lookup"><span data-stu-id="9c1b6-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="9c1b6-113">Formatsträngen är skiftlägeskänslig när du använder antingen ett standardformat eller ett anpassat format.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="9c1b6-114">Till exempel [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" formatspecificeraren returnerar datumet med hjälp av det korta datummönstret, medan standard "D" formatspecificeraren returnerar datumet med hjälp av det långa datummönstret.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="9c1b6-115">Dessutom returnerar den [anpassade](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" formatspecificeraren månaden från 1 till 12, medan den anpassade "m" formatspecificeraren returnerar minuten från 0 till 59.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="9c1b6-116">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9c1b6-116">`culture`: *String*</span></span>

<span data-ttu-id="9c1b6-117">Kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="9c1b6-118">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9c1b6-118">Return values</span></span>

<span data-ttu-id="9c1b6-119">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="9c1b6-119">*String*</span></span>

<span data-ttu-id="9c1b6-120">Det resulterande strängvärdet.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9c1b6-121">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="9c1b6-121">Usage notes</span></span>

<span data-ttu-id="9c1b6-122">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="9c1b6-123">Om till exempel funktionen `DATETIMEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="9c1b6-124">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="9c1b6-125">När `DATETIMEFORMAT`-funktionen konverterar ett givet datum/tidsvärde, beaktar den tidszonsinställningen för den programanvändare som kör det ER-format som funktionen anropas i kontexten för.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="9c1b6-126">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="9c1b6-126">Example 1</span></span>

<span data-ttu-id="9c1b6-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="9c1b6-128">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="9c1b6-128">Example 2</span></span>

<span data-ttu-id="9c1b6-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returnerar det aktuella datumet för programsessionen/tidsvärde, 24 december 2015 som **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="9c1b6-130">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="9c1b6-130">Example 3</span></span>

<span data-ttu-id="9c1b6-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returnerar strängvärdet **2019-11-12T08:00:00.0000000-08:00** när funktionen anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT-08:00) Pacific Time (USA och Kanada)** i avsnittet **Språk och land/regionpreferenser**.</span><span class="sxs-lookup"><span data-stu-id="9c1b6-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c1b6-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9c1b6-132">Additional resources</span></span>

[<span data-ttu-id="9c1b6-133">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="9c1b6-133">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]