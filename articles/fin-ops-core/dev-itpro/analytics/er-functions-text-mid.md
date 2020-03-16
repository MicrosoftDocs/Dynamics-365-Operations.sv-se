---
title: MID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MID elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 6fbaf5952222d90a855956fb93713e0f9ef81305
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041042"
---
# <a name="MID">MID ER-funktion</a>

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
