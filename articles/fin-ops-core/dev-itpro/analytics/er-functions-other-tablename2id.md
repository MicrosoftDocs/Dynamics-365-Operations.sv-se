---
title: TABLENAME2ID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TABLENAME2ID elektronisk rapportering (ER) används.
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
ms.openlocfilehash: d9f9e38f46df8a93b5cb16b8d0d5e5afbff8558a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744009"
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
