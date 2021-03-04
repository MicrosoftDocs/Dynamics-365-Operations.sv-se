---
title: Lista över ER-funktioner i textkategorin
description: Det här ämnet ger information om textfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 228620afc81e154eced572f3b6024d6836d00d66
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686037"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Lista över ER-funktioner i textkategorin

[!include [banner](../includes/banner.md)]

Textfunktioner för elektronisk rapportering (ER) kan användas för att utföra åtgärder på datakällor av datatypen *Sträng*. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [Char](er-functions-text-char.md) | Den här funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret. |
| [Sammanfoga](er-functions-text-concatenate.md) | Den här funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng. |
| [Format](er-functions-text-format.md) | Den här funktionen returnerar den angivna strängen som ett *Sträng* efter att den har formaterats genom att byta ut alla förekomster av **%N** med argumentet *N* th. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Den här funktionen söker efter ett specifikt värde för *uppräkning* i angiven uppräkningsdatakälla med hjälp av det uppräkningsnamn som anges som ett *sträng*-värde. Om *Enum*-värdet hittas returnerar funktionen den. |
| [GuidValue](er-functions-text-guidvalue.md) | Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Den här funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID. Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde. |
| [Vänster](er-functions-text-left.md) | Den här funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen. |
| [Len](er-functions-text-len.md) | Den här funktionen returnerar ett *Heltal*-värde som visar antalet tecken i den angivna strängen. |
| [Lower](er-functions-text-lower.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde efter att den har konverterats till gemener. |
| [Mid](er-functions-text-mid.md) | Den här funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen som börjar vid den angivna positionen. |
| [NumberFormat](er-functions-text-numberformat.md) | Den här funktionen returnerar ett värde för *Sträng* som visar det angivna numret i det angivna formatet och i en valfri angiven kultur. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Den här funktionen returnerar det angivna talet som ett *sträng*-värde när det har stavats ut (konverteras till textsträngar) på det angivna språket. |
| [PadLeft](er-functions-text-padleft.md) | Den här funktionen returnerar ett *Sträng*-värde med angiven längd i de fall den aktuella strängens början är utfylld med en eller flera instanser av de angivna tecknen. |
| [QrCode](er-functions-text-qrcode.md) | Den här funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format. |
| [Ersätta](er-functions-text-replace.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde när hela eller en del av den har ersatts med en annan sträng. |
| [Höger](er-functions-text-right.md) | Den här funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen. |
| [Text](er-functions-text-text.md) | Den här funktionen returnerar det specificerade numret som ett *Sträng*-värde efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen. |
| [Översätt](er-functions-text-translate.md) | Funktionen returnerar ett *sträng*-värde som innehåller resultatet av teckenersättningen för angiven text i tecken som ingår i en annan uppsättning tecken. |
| [Trim](er-functions-text-trim.md) | Den här funktionen returnerar den angivna textsträngen som ett *Sträng*-värde efter att inledande och efterföljande blanksteg har trunkerats och multipla blanksteg mellan ord har tagits bort. |
| [Upper](er-functions-text-upper.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde efter att den har konverterats till versaler. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]