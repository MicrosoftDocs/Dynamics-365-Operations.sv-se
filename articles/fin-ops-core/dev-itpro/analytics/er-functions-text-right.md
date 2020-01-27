---
title: RIGHT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen RIGHT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916739"
---
# <a name="RIGHT">RIGHT ER-funktion</a>

[!include [banner](../includes/banner.md)]

`RIGHT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen.

## <a name="syntax"></a>Syntax

```
RIGHT (text, number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som representerar den ursprungliga texten.

`number`: *Heltal*

Antalet tecken som måste returneras från slutet av den ursprungliga texten.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`RIGHT ("Sample", 3)` returnerar **"ple"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
