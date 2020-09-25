---
title: Funktionen DATEFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen DATEFORMAT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 4e9347937d088f15b4f489f0b85704a8688f8131
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743313"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="89fc7-103">Funktionen DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="89fc7-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89fc7-104">`DATEFORMAT`-funktionen returnerar ett värde för *Sträng* som visar ett givet datumvärde som text i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="89fc7-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="89fc7-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="89fc7-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="89fc7-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="89fc7-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="89fc7-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="89fc7-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="89fc7-108">Argument</span><span class="sxs-lookup"><span data-stu-id="89fc7-108">Arguments</span></span>

<span data-ttu-id="89fc7-109">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="89fc7-109">`date`: *Date*</span></span>

<span data-ttu-id="89fc7-110">Ett datumvärde som representerar datumet som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="89fc7-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="89fc7-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="89fc7-111">`format`: *String*</span></span>

<span data-ttu-id="89fc7-112">Formatet på utdatasträngen</span><span class="sxs-lookup"><span data-stu-id="89fc7-112">The format of the output string.</span></span>

<span data-ttu-id="89fc7-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="89fc7-113">`culture`: *String*</span></span>

<span data-ttu-id="89fc7-114">Kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="89fc7-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="89fc7-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="89fc7-115">Return values</span></span>

<span data-ttu-id="89fc7-116">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="89fc7-116">*String*</span></span>

<span data-ttu-id="89fc7-117">Det resulterande strängvärdet.</span><span class="sxs-lookup"><span data-stu-id="89fc7-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="89fc7-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="89fc7-118">Usage notes</span></span>

<span data-ttu-id="89fc7-119">När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten.</span><span class="sxs-lookup"><span data-stu-id="89fc7-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="89fc7-120">Om till exempel funktionen `DATEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen.</span><span class="sxs-lookup"><span data-stu-id="89fc7-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="89fc7-121">Standardvärdet `culture` är **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="89fc7-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="89fc7-122">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="89fc7-122">Example 1</span></span>

<span data-ttu-id="89fc7-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returnerar det aktuella datumet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="89fc7-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="89fc7-124">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="89fc7-124">Example 2</span></span>

<span data-ttu-id="89fc7-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="89fc7-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89fc7-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="89fc7-126">Additional resources</span></span>

[<span data-ttu-id="89fc7-127">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="89fc7-127">Date and time functions</span></span>](er-functions-category-datetime.md)
