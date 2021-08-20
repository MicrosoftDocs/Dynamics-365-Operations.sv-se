---
title: Lista över ER-funktioner i kategorin typkonvertering
description: Det här ämnet ger information om konverteringsfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: a6d678c2a38039285bd835abcbbaf13ec00298c0660c62e7496a5d7405db8f61
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766419"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Lista över ER-funktioner i kategorin typkonvertering

[!include [banner](../includes/banner.md)]

Funktioner för elektronisk rapportering (ER) typkonvertering kan användas för att konvertera värden mellan typer. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="type-conversion-functions"></a>Funktioner för typkonvertering

| Funktion | Beskrivning |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Den här funktionen returnerar ett *Int64*-värde som representerar den angivna strängen. |
| [IntValue](er-functions-conversion-intvalue.md)       | Den här funktionen returnerar ett *Int*-värde som representerar den angivna strängen. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Den här funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *sträng*. Under konverteringen beaktas de angivna decimal- och siffergrupperingsavgränsarna. |
| [Värde](er-functions-conversion-value.md)             | Den här funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *sträng*. |

## <a name="type-conversion-functions-in-the-container-category"></a>Skriv konverteringsfunktioner i behållarkategorin

I följande tabell beskrivs funktioner för typkonvertering i kategorin [behållare](er-functions-category-container.md).

| Funktion | beskrivning |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *Behållare*. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Funktioner för typkonvertering i kategorin datum och tid

I följande tabell beskrivs funktioner för typkonvertering i [kategorin datum och tid](er-functions-category-datetime.md).

| Funktion | Beskrivning |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Den här funktionen returnerar ett värde för *DateTime* som konverteras från ett givet *Sträng*-värde i angivet format och i en valfri angiven kultur. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Den här funktionen returnerar värdet *DateTime* som konverteras från ett givet *datum*-värde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Den här funktionen returnerar ett värde för *Datum* som konverteras från ett givet *Sträng*-värde i angivet format och i en valfri angiven kultur till ett datumvärde. |

## <a name="type-conversion-functions-in-the-list-category"></a>Skriv konverteringsfunktioner i listkategorin

I följande tabell beskrivs funktioner för typkonvertering i [listkategorin](er-functions-category-list.md).

| Funktion | Beskrivning |
|----------|-------------|
| [Lista](er-functions-list-list.md)                 | Den här funktionen returnerar ett *postlista*-värde som skapas från de angivna argumenten av typen *Behållare (post)*. |
| [ListOfFields](er-functions-list-listoffields.md) | Den här funktionen returnerar ett *postlista*-värde som skapas baserat på strukturen för det angivna argumentet i typen *uppräkning* eller *behållare (post)*. |
| [Dela](er-functions-list-split.md)               | Den här funktionen delar den angivna *Sträng*-värdet i delsträngar och returnerar resultatet som ett nytt värde för *postlistan*. |
| [StringJoin](er-functions-list-stringjoin.md)     | Den här funktionen returnerar ett *Sträng*-värde som består av de konkatenerade värdena från det definierade fältet från det angivna *Postlista*-värde. Värdena kan avgränsas med angivna avgränsare. |

## <a name="type-conversion-functions-in-the-text-category"></a>Skriv konverteringsfunktioner i textkategorin

I följande tabell beskrivs funktioner för typkonvertering i [textkategorin](er-functions-category-text.md).

| Funktion | Beskrivning |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Den här funktionen returnerar ett *sträng*-värde som representerar ett enstaka tecken som refereras av det angivna Unicode-numret. |
| [GuidValue](er-functions-text-guidvalue.md)       | Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Den här funktionen returnerar ett värde för *Sträng* som representerar det angivna numret i det angivna formatet och i en valfri angiven kultur. |
| [QrCode](er-functions-text-qrcode.md)             | Den här funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format. |
| [Text](er-functions-text-text.md)                 | Den här funktionen returnerar ett *Sträng*-värde som representerar det angivna numret efter att det har konverterats till en textsträng som formateras enligt serverns lokala inställningar till den aktuella programinstansen. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]