---
title: Lista över ER-funktioner i kategorin datum och tid
description: Det här ämnet ger information om datum och tid-funktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: fa8e725ac6bd7d280dc0269a70e3f7abf1ad4d43
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916578"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="1a776-103">Lista över ER-funktioner i kategorin datum och tid</span><span class="sxs-lookup"><span data-stu-id="1a776-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a776-104">Funktionerna för elektronisk rapportering (ER) för datum och tid kan användas för att extrahera information från datum- och tidsvärden och för att utföra åtgärder på dem.</span><span class="sxs-lookup"><span data-stu-id="1a776-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="1a776-105">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="1a776-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="1a776-106">Lista över funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="1a776-106">List of supported functions</span></span>

| <span data-ttu-id="1a776-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="1a776-107">Function</span></span> | <span data-ttu-id="1a776-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1a776-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="1a776-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="1a776-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="1a776-110">Den här funktionen returnerar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.</span><span class="sxs-lookup"><span data-stu-id="1a776-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="1a776-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="1a776-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="1a776-112">Den funktionen returnerar ett värde för *Sträng* som visar ett givet datumvärde som text i angivet format och i en valfri angiven kultur.</span><span class="sxs-lookup"><span data-stu-id="1a776-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="1a776-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="1a776-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="1a776-114">Den funktionen returnerar ett värde för *Sträng* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven kultur.</span><span class="sxs-lookup"><span data-stu-id="1a776-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="1a776-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="1a776-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="1a776-116">Den här funktionen returnerar ett värde för *DateTime* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur.</span><span class="sxs-lookup"><span data-stu-id="1a776-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="1a776-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="1a776-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="1a776-118">Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="1a776-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="1a776-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="1a776-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="1a776-120">Den här funktionen returnerar ett värde för *Datum* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur till ett datumvärde.</span><span class="sxs-lookup"><span data-stu-id="1a776-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="1a776-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="1a776-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="1a776-122">Funktionen returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="1a776-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="1a776-123">Dagar</span><span class="sxs-lookup"><span data-stu-id="1a776-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="1a776-124">Funktionen returnerar värdet *heltal* som representerar antalet dagar mellan ett angivet datum och ett andra angivet datum.</span><span class="sxs-lookup"><span data-stu-id="1a776-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="1a776-125">Now</span><span class="sxs-lookup"><span data-stu-id="1a776-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="1a776-126">Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid.</span><span class="sxs-lookup"><span data-stu-id="1a776-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="1a776-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="1a776-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="1a776-128">Den här funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900).</span><span class="sxs-lookup"><span data-stu-id="1a776-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="1a776-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="1a776-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="1a776-130">Den här funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time.</span><span class="sxs-lookup"><span data-stu-id="1a776-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="1a776-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="1a776-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="1a776-132">Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets sessionsdatum och -tid.</span><span class="sxs-lookup"><span data-stu-id="1a776-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="1a776-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="1a776-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="1a776-134">Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum.</span><span class="sxs-lookup"><span data-stu-id="1a776-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="1a776-135">I dag</span><span class="sxs-lookup"><span data-stu-id="1a776-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="1a776-136">Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets serverdatum.</span><span class="sxs-lookup"><span data-stu-id="1a776-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="1a776-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1a776-137">Additional resources</span></span>

[<span data-ttu-id="1a776-138">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1a776-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="1a776-139">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1a776-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="1a776-140">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1a776-140">Electronic reporting formula language</span></span>](er-formula-language.md)
