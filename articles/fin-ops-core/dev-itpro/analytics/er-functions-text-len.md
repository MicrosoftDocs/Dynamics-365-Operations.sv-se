---
title: LEN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LEN elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 3e0ba19e762574dde4f9038b87ce352d13f714f4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041065"
---
# <a name="LEN">LEN ER-funktion</a>

[!include [banner](../includes/banner.md)]

`LEN`-funktionen returnerar antalet tecken i den angivna strängen som ett *heltals*-värde.

## <a name="syntax"></a>Syntax

```vb
LEN (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som anger texten.

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="example"></a>Exempel

`LEN ("Sample")` returnerar **6**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
