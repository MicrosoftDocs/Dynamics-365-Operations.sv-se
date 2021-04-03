---
title: Lista över ER-funktioner i kategorin typkonvertering
description: Det här ämnet ger information om konverteringsfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5613496d3131ccd39b198cac214eb791a6d07355
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561528"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="dde95-103">Lista över ER-funktioner i kategorin typkonvertering</span><span class="sxs-lookup"><span data-stu-id="dde95-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dde95-104">Funktioner för elektronisk rapportering (ER) typkonvertering kan användas för att konvertera värden mellan typer.</span><span class="sxs-lookup"><span data-stu-id="dde95-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="dde95-105">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="dde95-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="dde95-106">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="dde95-106">Type conversion functions</span></span>

| <span data-ttu-id="dde95-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="dde95-107">Function</span></span> | <span data-ttu-id="dde95-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dde95-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="dde95-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="dde95-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="dde95-110">Den här funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="dde95-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="dde95-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="dde95-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="dde95-112">Den här funktionen returnerar ett *Int*-värde som representerar den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="dde95-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="dde95-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="dde95-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="dde95-114">Den här funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *sträng*.</span><span class="sxs-lookup"><span data-stu-id="dde95-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="dde95-115">Under konverteringen beaktas de angivna decimal- och siffergrupperingsavgränsarna.</span><span class="sxs-lookup"><span data-stu-id="dde95-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="dde95-116">Värde</span><span class="sxs-lookup"><span data-stu-id="dde95-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="dde95-117">Den här funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *sträng*.</span><span class="sxs-lookup"><span data-stu-id="dde95-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="dde95-118">Skriv konverteringsfunktioner i behållarkategorin</span><span class="sxs-lookup"><span data-stu-id="dde95-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="dde95-119">I följande tabell beskrivs funktioner för typkonvertering i kategorin [behållare](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="dde95-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="dde95-120">Funktion</span><span class="sxs-lookup"><span data-stu-id="dde95-120">Function</span></span> | <span data-ttu-id="dde95-121">beskrivning</span><span class="sxs-lookup"><span data-stu-id="dde95-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="dde95-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="dde95-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="dde95-123">Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *Behållare*.</span><span class="sxs-lookup"><span data-stu-id="dde95-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="dde95-124">Funktioner för typkonvertering i kategorin datum och tid</span><span class="sxs-lookup"><span data-stu-id="dde95-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="dde95-125">I följande tabell beskrivs funktioner för typkonvertering i [kategorin datum och tid](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="dde95-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="dde95-126">Funktion</span><span class="sxs-lookup"><span data-stu-id="dde95-126">Function</span></span> | <span data-ttu-id="dde95-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dde95-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="dde95-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="dde95-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="dde95-129">Den här funktionen returnerar ett värde för *DateTime* som konverteras från ett givet *Sträng*-värde i angivet format och i en valfri angiven kultur.</span><span class="sxs-lookup"><span data-stu-id="dde95-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="dde95-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="dde95-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="dde95-131">Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet *datum*-värde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="dde95-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="dde95-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="dde95-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="dde95-133">Den här funktionen returnerar ett värde för *Datum* som konverteras från ett givet *Sträng*-värde i angivet format och i en valfri angiven kultur till ett datumvärde.</span><span class="sxs-lookup"><span data-stu-id="dde95-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="dde95-134">Skriv konverteringsfunktioner i listkategorin</span><span class="sxs-lookup"><span data-stu-id="dde95-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="dde95-135">I följande tabell beskrivs funktioner för typkonvertering i [listkategorin](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="dde95-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="dde95-136">Funktion</span><span class="sxs-lookup"><span data-stu-id="dde95-136">Function</span></span> | <span data-ttu-id="dde95-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dde95-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="dde95-138">Lista</span><span class="sxs-lookup"><span data-stu-id="dde95-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="dde95-139">Den här funktionen returnerar ett *postlista*-värde som skapas från de angivna argumenten av typen *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="dde95-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="dde95-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="dde95-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="dde95-141">Den här funktionen returnerar ett *postlista*-värde som skapas baserat på strukturen för det angivna argumentet i typen *uppräkning* eller *behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="dde95-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="dde95-142">Dela</span><span class="sxs-lookup"><span data-stu-id="dde95-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="dde95-143">Den här funktionen delar den angivna *Sträng*-värdet i delsträngar och returnerar resultatet som ett nytt värde för *postlistan*.</span><span class="sxs-lookup"><span data-stu-id="dde95-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="dde95-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="dde95-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="dde95-145">Den här funktionen returnerar ett *Sträng*-värde som består av de konkatenerade värdena från det definierade fältet från det angivna *Postlista*-värde.</span><span class="sxs-lookup"><span data-stu-id="dde95-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="dde95-146">Värdena kan avgränsas med angivna avgränsare.</span><span class="sxs-lookup"><span data-stu-id="dde95-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="dde95-147">Skriv konverteringsfunktioner i textkategorin</span><span class="sxs-lookup"><span data-stu-id="dde95-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="dde95-148">I följande tabell beskrivs funktioner för typkonvertering i [textkategorin](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="dde95-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="dde95-149">Funktion</span><span class="sxs-lookup"><span data-stu-id="dde95-149">Function</span></span> | <span data-ttu-id="dde95-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dde95-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="dde95-151">Char</span><span class="sxs-lookup"><span data-stu-id="dde95-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="dde95-152">Den här funktionen returnerar ett *sträng*-värde som representerar ett enstaka tecken som refereras av det angivna Unicode-numret.</span><span class="sxs-lookup"><span data-stu-id="dde95-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="dde95-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="dde95-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="dde95-154">Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*.</span><span class="sxs-lookup"><span data-stu-id="dde95-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="dde95-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="dde95-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="dde95-156">Den här funktionen returnerar ett värde för *Sträng* som representerar det angivna numret i det angivna formatet och i en valfri angiven kultur.</span><span class="sxs-lookup"><span data-stu-id="dde95-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="dde95-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="dde95-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="dde95-158">Den här funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format.</span><span class="sxs-lookup"><span data-stu-id="dde95-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="dde95-159">Text</span><span class="sxs-lookup"><span data-stu-id="dde95-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="dde95-160">Den här funktionen returnerar ett *Sträng*-värde som representerar det angivna numret efter att det har konverterats till en textsträng som formateras enligt serverns lokala inställningar till den aktuella programinstansen.</span><span class="sxs-lookup"><span data-stu-id="dde95-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="dde95-161">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dde95-161">Additional resources</span></span>

[<span data-ttu-id="dde95-162">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="dde95-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="dde95-163">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="dde95-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="dde95-164">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="dde95-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]