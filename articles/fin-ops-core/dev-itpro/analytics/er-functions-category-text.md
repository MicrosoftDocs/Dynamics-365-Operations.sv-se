---
title: Lista över ER-funktioner i textkategorin
description: Det här ämnet ger information om textfunktionerna som stöds i elektronisk rapportering (ER).
author: kfend
ms.date: 02/28/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e4c7885024586034c062304cce21a25e5b6c8c9b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268806"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Lista över ER-funktioner i textkategorin

[!include [banner](../includes/banner.md)]

Textfunktioner för elektronisk rapportering (ER) kan användas för att utföra åtgärder på datakällor av datatypen *Sträng*. Den här artikeln innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [Char](er-functions-text-char.md) | Den här funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret. |
| [Sammanfoga](er-functions-text-concatenate.md) | Den här funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng. |
| [Format](er-functions-text-format.md) | Den här funktionen returnerar den angivna strängen som ett *Sträng* efter att den har formaterats genom att byta ut alla förekomster av **%N** med argumentet *N* th. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Den här funktionen söker efter ett specifikt värde för *uppräkning* i angiven uppräkningsdatakälla med hjälp av det uppräkningsnamn som anges som ett *sträng*-värde. Om *Enum*-värdet hittas returnerar funktionen den. |
| [GetLabelText](er-functions-text-getlabeltext.md) | Med denna funktion söker du efter en specifik etikett för att returnera ett *[sträng](er-formula-supported-data-types-primitive.md#string)* värde som representerar översättningen av den angivna etiketten på det angivna språket. |
| [GuidValue](er-functions-text-guidvalue.md) | Den här funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Den här funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID. Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde. |
| [Vänster](er-functions-text-left.md) | Den här funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen. |
| [Len](er-functions-text-len.md) | Den här funktionen returnerar ett *Heltal*-värde som visar antalet tecken i den angivna strängen. |
| [Lower](er-functions-text-lower.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde efter att den har konverterats till gemener. |
| [Mid](er-functions-text-mid.md) | Den här funktionen returnerar ett *[sträng](er-formula-supported-data-types-primitive.md#string)*-värde som visar angivet antal tecken från början av den angivna strängen som börjar vid den angivna positionen. |
| [NewGUID](er-functions-text-newguid.md) | Den här funktionen returnerar ett nyligen genererat *[GUID](er-formula-supported-data-types-primitive.md#guid)* värde. |
| [NumberFormat](er-functions-text-numberformat.md) | Den här funktionen returnerar ett värde för *Sträng* som visar det angivna numret i det angivna formatet och i en valfri angiven kultur. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Den här funktionen returnerar det angivna talet som ett *sträng*-värde när det har stavats ut (konverteras till textsträngar) på det angivna språket. |
| [PadLeft](er-functions-text-padleft.md) | Den här funktionen returnerar ett *Sträng*-värde med angiven längd i de fall den aktuella strängens början är utfylld med en eller flera instanser av de angivna tecknen. |
| [QrCode](er-functions-text-qrcode.md) | Den här funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format. |
| [Ersätta](er-functions-text-replace.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde när hela eller en del av den har ersatts med en annan sträng. |
| [Höger](er-functions-text-right.md) | Den här funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen. |
| [Text](er-functions-text-text.md) | Den här funktionen returnerar det specificerade numret som ett *Sträng*-värde efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen. |
| [Översätt](er-functions-text-translate.md) | Funktionen returnerar ett *sträng*-värde som innehåller resultatet av teckenersättningen för angiven text i tecken som ingår i en annan uppsättning tecken. |
| [Trim](er-functions-text-trim.md) | Denna funktion returnerar den angivna textsträngen som ett *Sträng*-värde efter tabb, carriage return, radflöde och formulärflödestecken har ersatts med ett blanksteg, efter att inledande och avslutande blanksteg har trunkerats samt efter att flera blanksteg mellan ord har tagits bort. |
| [Upper](er-functions-text-upper.md) | Den här funktionen returnerar den angivna textsträngen som ett *sträng*-värde efter att den har konverterats till versaler. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
