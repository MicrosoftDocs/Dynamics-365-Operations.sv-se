---
title: Funktionen DATETIMEFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen DATETIMEFORMAT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 98919f40751a77465ae26acbd46af4396c588b13
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916417"
---
# <span data-ttu-id="b22dd-103"><a name="DATETIMEFORMAT">Funktionen DATETIMEFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="b22dd-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b22dd-104">`DATETIMEFORMAT`-funktionen returnerar ett värde för *Sträng* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="b22dd-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="b22dd-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b22dd-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b22dd-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="b22dd-106">Syntax 1</span></span>

```
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="b22dd-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="b22dd-107">Syntax 2</span></span>

```
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="b22dd-108">Argument</span><span class="sxs-lookup"><span data-stu-id="b22dd-108">Arguments</span></span>

<span data-ttu-id="b22dd-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="b22dd-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="b22dd-110">Ett datum-/tidsvärde som representerar det datum och den tid som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="b22dd-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="b22dd-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b22dd-111">`format`: *String*</span></span>

<span data-ttu-id="b22dd-112">Formatet på utdatasträngen</span><span class="sxs-lookup"><span data-stu-id="b22dd-112">The format of the output string.</span></span>

<span data-ttu-id="b22dd-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b22dd-113">`culture`: *String*</span></span>

<span data-ttu-id="b22dd-114">Kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="b22dd-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="b22dd-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b22dd-115">Return values</span></span>

<span data-ttu-id="b22dd-116">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b22dd-116">*String*</span></span>

<span data-ttu-id="b22dd-117">Det resulterande strängvärdet.</span><span class="sxs-lookup"><span data-stu-id="b22dd-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b22dd-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b22dd-118">Usage notes</span></span>

<span data-ttu-id="b22dd-119">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="b22dd-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="b22dd-120">Om till exempel funktionen `DATETIMEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="b22dd-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="b22dd-121">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b22dd-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="b22dd-122">När `DATETIMEFORMAT`-funktionen konverterar ett givet datum/tidsvärde, beaktar den tidszonsinställningen för den programanvändare som kör det ER-format som funktionen anropas i kontexten för.</span><span class="sxs-lookup"><span data-stu-id="b22dd-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="b22dd-123">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b22dd-123">Example 1</span></span>

<span data-ttu-id="b22dd-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="b22dd-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="b22dd-125">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b22dd-125">Example 2</span></span>

<span data-ttu-id="b22dd-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returnerar det aktuella datumet för programsessionen/tidsvärde, 24 december 2015 som **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="b22dd-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="b22dd-127">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="b22dd-127">Example 3</span></span>

<span data-ttu-id="b22dd-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returnerar strängvärdet **2019-11-12T08:00:00.0000000-08:00** när det anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT-08:00) Pacific Time (USA och Kanada)** i avsnittet **Språk och land/regionpreferenser**.</span><span class="sxs-lookup"><span data-stu-id="b22dd-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b22dd-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b22dd-129">Additional resources</span></span>

[<span data-ttu-id="b22dd-130">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="b22dd-130">Date and time functions</span></span>](er-functions-category-datetime.md)
