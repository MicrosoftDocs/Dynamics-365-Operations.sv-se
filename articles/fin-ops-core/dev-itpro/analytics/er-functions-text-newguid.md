---
title: NEWGUID ER-funktion
description: Den här artikeln innehåller information om hur funktionen NEWGUID elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 321e2eda4accf9c8fe33b5a4c092c7be55276f26
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861828"
---
# <a name="newguid-er-function"></a>NEWGUID ER-funktion

[!include [banner](../includes/banner.md)]

Funktionen `NEWGUID` genererar en ny globalt unik identifierare (GUID) och returnerar den som ett *[GUID](er-formula-supported-data-types-primitive.md#guid)*-värde.

## <a name="syntax"></a>Syntax

```vb
NEWGUID ()
```

## <a name="return-values"></a>Returvärden

*GUID*

Det resulterande GUID-värdet.

## <a name="example"></a>Exempel

`NEWGUID()` returnerar alltid ett nytt *GUID*-värde, t.ex. **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
