---
title: FORMATELEMENTNAME ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FORMATELEMENTNAME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d66fed3815188fa7e31735e3523376ae4ea1cf46
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917682"
---
# <a name="FORMATELEMENTNAME">FORMATELEMENTNAME ER-funktion</a>

[!include [banner](../includes/banner.md)]

`FORMATELEMENTNAME`-funktionen returnerar ett *sträng*-värde som representerar namnet på det aktuella elementet för elektronisk rapportering (ER)-format.

## <a name="syntax"></a>Syntax

```
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Den här funktionen kan anropas i ER-uttryck som har konfigurerats för egenskaperna **Insamlade datanyckelnamn** och **Insamlat datanyckelvärde** egenskaper för en ER-formatkomponent från gruppen **Text** som finns under komponenten **gemensam\\fil** där alternativet **Samla in utgångsdetaljer** är aktiverat.

## <a name="example"></a>Exempel

För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Datainsamlingsfunktioner](er-functions-category-data-collection.md)
