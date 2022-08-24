---
title: GETCURRENTCOMPANY ER-funktionen
description: Den här artikeln innehåller information om hur funktionen GETCURRENTCOMPANY elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: b5f5f7d7c884000f59b93e10875f78289a879779
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280198"
---
# <a name="getcurrentcompany-er-function"></a>GETCURRENTCOMPANY ER-funktionen

[!include [banner](../includes/banner.md)]

Funktionen `GETCURRENTCOMPANY` returnerar ett *Sträng*-värde som representerar koden för den juridiska person (företag) som användaren är inloggad i för närvarande.

## <a name="syntax"></a>Syntax

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`GETCURRENTCOMPANY ()` returnerar **USMF** för en användare som är inloggad på företaget **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
