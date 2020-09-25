---
title: LEFT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LEFT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 112852ab955fdf8de9f78cc93486cc1d5f048517
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743793"
---
# <a name="left-er-function"></a>LEFT ER-funktion

[!include [banner](../includes/banner.md)]

`LEFT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen.

## <a name="syntax"></a>Syntax

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som representerar den ursprungliga texten.

`number`: *Heltal*

Antalet tecken som måste returneras från början av den ursprungliga texten.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`LEFT ("Sample", 3)` returnerar **"Sam"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
