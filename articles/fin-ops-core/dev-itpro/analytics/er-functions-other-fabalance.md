---
title: FA_BALANCE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FA_BALANCE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
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
ms.openlocfilehash: ec78b9c5bf800503023315eb893076486b0a1fb0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744329"
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