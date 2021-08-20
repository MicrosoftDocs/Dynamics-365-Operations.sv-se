---
title: MID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MID elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 33a8d02e937b3d88d98cac96ae28a30345ccffb23be37d7add67f721dfb9cc70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742372"
---
# <a name="mid-er-function"></a>MID ER-funktion

[!include [banner](../includes/banner.md)]

`MID`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen som börjar vid den angivna positionen.

## <a name="syntax"></a>Syntax

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som anger vilken text som ska returnera tecken från.

`starting position`: *Heltal*

Ett *heltal*-värde som anger positionen för det första tecknet som måste returneras från den angivna texten.

`number of characters`: *Heltal*

Ett *heltal*-värde som anger antalet tecken som måste returneras med början från den angivna startpositionen.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Om värdet för `starting position`-argumentet är mindre än 0 (noll), räknas de tecken som returneras från den första positionen i den angivna strängen.

Om värdet för `starting position`-argumentet överskrider längden på den angivna strängen, returneras en tom sträng.

## <a name="example"></a>Exempel

`MID ("Sample", 2, 3)` returnerar **"amp"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]