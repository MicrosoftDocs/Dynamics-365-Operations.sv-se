---
title: FA_BALANCE ER-funktion
description: Den här artikeln innehåller information om hur funktionen FA_BALANCE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: c3dd44f0d5ff143189b2c55c4df80847c2161231
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902695"
---
# <a name="fa_balance-er-function"></a>FA_BALANCE ER-funktion

[!include [banner](../includes/banner.md)]

`FA_BALANCE`-funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångssaldo för den angivna anläggningstillgångsartikeln, värdemodellkoden, rapporteringsår och rapporterigsdatum.

## <a name="syntax"></a>Syntax

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argument

`fixed asset code`: *Sträng*

Ett *sträng*-värde som representerar koden för en anläggningstillgångsartikel som saldot beräknas för.

`value model code`: *Sträng*

Ett *sträng*-värde som representerar koden för en värdemodell som saldot beräknas för.

`reporting year`: *Fasttextvärde*

Ett fasttextvärde för programuppräkningen **AssetYear** som definierar en period för saldoberäkningen.

`reporting date`: *Datum*

Ett *datum*-värde som definierar ett datum för saldoberäkningen.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="example"></a>Exempel

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returnerar databehållaren för belopp tillhörande anläggningstillgången **COMP-000001** som har förberetts för värdemodellen **Aktuell** på aktuellt programsessionsdatum.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]