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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2745298ae1f6787c3de5a4aaf6a2a6350f5f3e85
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686229"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista över ER-funktioner i kategorin datum och tid

[!include [banner](../includes/banner.md)]

Funktionerna för elektronisk rapportering (ER) för datum och tid kan användas för att extrahera information från datum- och tidsvärden och för att utföra åtgärder på dem. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Den här funktionen returnerar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum. |
| [DateFormat](er-functions-datetime-dateformat.md) | Den funktionen returnerar ett värde för *Sträng* som visar ett givet datumvärde som text i angivet format och i en valfri angiven kultur. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Den funktionen returnerar ett värde för *Sträng* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven kultur. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Den här funktionen returnerar ett värde för *DateTime* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Den här funktionen returnerar ett värde för *Datum* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur till ett datumvärde. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Funktionen returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet. |
| [Dagar](er-functions-datetime-days.md) | Funktionen returnerar värdet *heltal* som representerar antalet dagar mellan ett angivet datum och ett andra angivet datum. |
| [Now](er-functions-datetime-now.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid. |
| [NullDate](er-functions-datetime-nulldate.md) | Den här funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets sessionsdatum och -tid. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum. |
| [I dag](er-functions-datetime-today.md) | Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets serverdatum. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)
