---
title: NEWGUID ER-funktion
description: Den här artikeln innehåller information om hur funktionen NEWGUID elektronisk rapportering (ER) används.
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274785"
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
