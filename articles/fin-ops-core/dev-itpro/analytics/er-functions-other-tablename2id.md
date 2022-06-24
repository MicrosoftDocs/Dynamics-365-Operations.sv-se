---
title: TABLENAME2ID ER-funktion
description: Den här artikeln innehåller information om hur funktionen TABLENAME2ID elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: b5deea69d5c43be599ccf02c0344ba8d662a6e0f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886861"
---
# <a name="tablename2id-er-function"></a>TABLENAME2ID ER-funktion

[!include [banner](../includes/banner.md)]

`TABLENAME2ID`-funktionen returnerar en numerisk representation av tabell-ID för det angivna tabellnamnet som värdet *heltal*.

## <a name="syntax"></a>Syntax

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som representerar ett giltigt tabellnamn.

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Körningen av den här funktionen kan ha olika resultat i olika instanser av Microsoft Dynamics 365 Finance, även om samma företagsnamn används.

## <a name="example"></a>Exempel

`TABLENAME2ID ("Intrastat")` returnerar **1510**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]