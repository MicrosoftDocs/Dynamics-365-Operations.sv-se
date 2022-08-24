---
title: FA_SUM ER-funktion
description: Den här artikeln innehåller information om hur funktionen FA_SUM elektronisk rapportering (ER) används.
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
ms.openlocfilehash: bcedbc3df835b219b8df6d05f1db6b331f1e9254
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278930"
---
# <a name="fa_sum-er-function"></a>FA_SUM ER-funktion

[!include [banner](../includes/banner.md)]

`FA_SUM`-funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångsbeloppen för den angivna anläggningstillgångsartikeln, värdemodellkoden och datumperioden.

## <a name="syntax"></a>Syntax

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Argument

`fixed asset code`: *Sträng*

Ett *sträng*-värde som representerar koden för en anläggningstillgångsartikel som saldot beräknas för.

`value model code`: *Sträng*

Ett *sträng*-värde som representerar koden för en värdemodell som saldot beräknas för.

`start date`: *Datum*

Ett *datum*-värde som representerar startdatumet för en period som anläggningstillgångens belopp beräknas för.

`end date`: *Datum*

Ett *datum*-värde som representerar slutdatumet för en period som anläggningstillgångens belopp beräknas för.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="example"></a>Exempel

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returnerar databehållaren för anläggningstillgången **COMP-000001** som har förberetts för den **aktuella** värdemodellen och för en period från **Datum1** till **Datum2**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
