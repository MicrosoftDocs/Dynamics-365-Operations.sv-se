---
title: GETCURRENTCOMPANY ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen GETCURRENTCOMPANY elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: c74ffaf1ee134da8d962e054656301d5e99827ff53f560f5d93f9dcb51819c13
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760784"
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