---
title: Lista över ER-funktioner i logisk kategori
description: Det här ämnet ger information om logiska funktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686204"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Lista över ER-funktioner i logisk kategori

[!include [banner](../includes/banner.md)]

Logiska funktioner för elektronisk rapportering (ER) kan användas för att arbeta med logiska värden för att utföra mer än en jämförelse i ett enda uttryck eller testa flera villkor. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [Och](er-functions-logical-and.md)                       | Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. |
| [Ärende](er-functions-logical-case.md)                     | Den här funktionen utvärderar värdet för det angivna uttrycket mot de angivna alternativa och returnerar resultatet av det första alternativet som är lika med värdet för det angivna uttrycket. Annars returneras ett valfritt standard resultat om ett standard resultat anges som det sista argumentet för den anropade funktionen som inte föregås av ett alternativ. Värdet som returneras kan vara ett värde för någon av datatyperna som stöds. |
| [Om](er-functions-logical-if.md)                         | Denna funktion returnerar det första definierade värdet när det definierade villkoret uppfylls. Returnera annars det andra angivna värdet. Värdet som returneras kan vara ett värde för någon av datatyperna som stöds. |
| [Inte](er-functions-logical-not.md)                       | Den här funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde. |
| [Eller](er-functions-logical-or.md)                         | Den här funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk. Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant. |
| [ValueIn](er-functions-logical-valuein.md)               | Denna funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan. Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Denna funktion bestämmer om specifik indata av typen *Int64* eller *heltal* matchar något värde för en angiven objekt i den angivna listan. Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. |


## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)
