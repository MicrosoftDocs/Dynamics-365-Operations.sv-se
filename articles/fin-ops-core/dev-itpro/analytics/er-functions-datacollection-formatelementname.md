---
title: FORMATELEMENTNAME ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FORMATELEMENTNAME elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755238"
---
# <a name="formatelementname-er-function"></a>FORMATELEMENTNAME ER-funktion

[!include [banner](../includes/banner.md)]

`FORMATELEMENTNAME`-funktionen returnerar ett *sträng*-värde som representerar namnet på det aktuella elementet för elektronisk rapportering (ER)-format.

## <a name="syntax"></a>Syntax

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]