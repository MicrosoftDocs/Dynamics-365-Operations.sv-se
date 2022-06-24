---
title: Lista över ER-funktioner i kategorin datum och tid
description: Det här ämnet ger information om datum och tid-funktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: e6e15d143bad016883f03ecf0125ce9429215a71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880266"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista över ER-funktioner i kategorin datum och tid

[!include [banner](../includes/banner.md)]

Funktionerna för elektronisk rapportering (ER) för datum och tid kan användas för att extrahera information från datum- och tidsvärden och för att utföra åtgärder på dem. Den här artikeln innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Den här funktionen returnerar *[DateTime](er-formula-supported-data-types-primitive.md#datetime)*-värde som är angivet antal dagar före eller efter ett angivet startdatum. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i en annan tidszon. |
| [DateFormat](er-functions-datetime-dateformat.md) | Den funktionen returnerar ett värde för *[Sträng](er-formula-supported-data-types-primitive.md#string)* som visar ett givet datumvärde som text i angivet format och i en valfri angiven kultur. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Den funktionen returnerar ett värde för *Sträng* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven kultur. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Den här funktionen returnerar ett värde för *DateTime* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Den här funktionen returnerar ett värde för *[Datum](er-formula-supported-data-types-primitive.md#date)* som konverteras från ett givet textvärde i angivet format och i en valfri angiven kultur till ett datumvärde. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Funktionen returnerar värdet *[heltal](er-formula-supported-data-types-primitive.md#integer)* som representerar antalet dagar mellan 1 januari och det angivna datumet. |
| [Dagar](er-functions-datetime-days.md) | Funktionen returnerar värdet *heltal* som representerar antalet dagar mellan ett angivet datum och ett andra angivet datum. |
| [Now](er-functions-datetime-now.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid. |
| [NullDate](er-functions-datetime-nulldate.md) | Den här funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Den här funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets sessionsdatum och -tid. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum. |
| [I dag](er-functions-datetime-today.md) | Den här funktionen returnerar ett *Datum*-värde som representerar aktuella programmets serverdatum. |
| [WeekNum](er-functions-datetime-weeknum.md) | Den här funktionen returnerar ett *heltal*-värde som representerar den veckan på året. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
