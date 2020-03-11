---
title: LISTOFFIELDS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTOFFIELDS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 0d51b59c437bd216c6d229546136bb604239fa92
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042008"
---
# <a name="LISTOFFIELDS">LISTOFFIELDS ER-funktion</a>

[!include [banner](../includes/banner.md)]

`LISTOFFIELDS`-funktionen returnerar ett *postlista*-värde som skapas baserat på strukturen för det angivna argumentet i typen *uppräkning* eller *behållare (post)*.

## <a name="syntax-1"></a>Syntax 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Syntax 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argument

`path`: datakällareferens

Den giltiga referenssökvägen till en datakälla för någon av följande datatyper:

- Uppräkning för modell
- Formatuppräkning
- Uppräkning för program
- Behållare (post)

`language`: *Sträng*

Text som representerar en språkkod.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Listan som skapas består av poster som innehåller följande fält:

- **Namn** (*Sträng* datatyp)
- **Etikett** (*Sträng* datatyp)
- **Beskrivning** (*Sträng* datatyp)
- **Istranslated** (*boolesk* datatyp)

Om `path`-argumentet refererar till en datakälla för typen *behållare (post)*, läggs en ny post till i listan som skapas för varje fält i den refererade behållarposten. För varje post som skapas returnerar fältet **namn** namnet på fältet för den refererade behållarposten som den aktuella posten skapades för.

Om `path`-argumentet refererar till en datakälla för en av typerna *Uppräkning*, för varje uppräkningsvärde för den refererade uppräkningen läggs en ny post till i listan som skapades. För varje post som skapades returnerar fältet **Namn** fältet returnerar värdet på den refererade uppräkningen som den aktuella posten skapades för, fältet **beskrivning** returnerar beskrivningen av uppräkningen och fältet **etikett** returnerar etiketten för den uppräkningen.

Vid körning, när syntax 1 används, måste fälten **etikett** och **beskrivning** returnera värden som baseras på språkinställningarna för det format för elektronisk rapportering (ER) som körs:

- Om etiketterna och beskrivningarna för det begärda språket är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på det språket, och fältet **IsTranslated** returneras **sant**.
- Om etiketterna och beskrivningarna för det begärda språket inte är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på standardspråket **EN-US** och fältet **IsTranslated** returneras **falskt**.

Vid körning, när syntax 2 används, måste fälten **etikett** och **beskrivning** returnera värden som baseras på språket som definieras som det andra argumentet av de anropade funktionerna:

- Om etiketterna och beskrivningarna för det begärda språket är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på det språket, och fältet **IsTranslated** returneras **sant**.
- Om etiketterna och beskrivningarna för det begärda språket inte är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på språket **EN-US** och fältet **IsTranslated** returneras **falskt**.

## <a name="example-1"></a>Exempel 1

I följande illustration introduceras en uppräkning i en ER-datamodell.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

Illustrationen som följer visar dessa detaljer:

- Modelluppräkningen har infogats i en rapport som en datakälla.
- ER-uttryck använder uppräkningsmodellen som en parameter för funktionen `LISTOFFIELDS`.
- En datakälla av typen *postlista* infogas i en rapport med hjälp av det ER-uttryck som skapats.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

Följande exempel visar de ER-formatelement som är kopplade till en datakälla av typen *postlista* som skapats med funktionen `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

Följande illustration visar resultatet när det designade formatet har körts.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Baserat på språkinställningarna i de överordnade **FILE**- och **FOLDER**-elementen infogas översatt text för etiketter och beskrivningar i utdata till ER-formatet.

## <a name="example-2"></a>Exempel 2

Till exempel kan du använda datakälltypen *Beräknat fält* för att konfigurera datakällor för **enumType\_de** och **enumType\_deCH** för uppräkning av datamodell **enumType**:

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

I det här fallet kan du använda följande uttryck för att få etiketten på uppräkningsvärdet på tyska (Schweiz), om denna översättning är tillgänglig. Om schweizisk tysk översättning inte är tillgänglig är etiketten på tyska.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)
