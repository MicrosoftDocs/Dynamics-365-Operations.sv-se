---
title: Funktionen CONVERTCURRENCY ER
description: Det här avsnittet innehåller information om hur funktionen CONVERTCURRENCY elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: a27fd30236a61576ab9063010ea6bc38d9cf7a1e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686796"
---
# <a name="convertcurrency-er-function"></a>Funktionen CONVERTCURRENCY ER

[!include [banner](../includes/banner.md)]

`CONVERTCURRENCY`-funktionen returnerar ett *Realtal*-värde som representerar resultatet av att konvertera det angivna monetära beloppet från den angivna källvalutan till den angivna målvalutan genom att använda inställningarna för det angivna företaget på det angivna datumet.

## <a name="syntax"></a>Syntax

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argument

`amount`: *Heltal* eller *Realtal*

Ett numeriskt värde som representerar det monetära belopp som måste konverteras.

`source currency`: *Sträng*

Koden för källvalutan.

`target currency`: *Sträng*

Koden för målvalutan.

`date`: *Datum*

Ett *datum*-värde som representerar det datum som används för att bestämma valutakursen för konverteringen.

`company`: *Sträng*

Ett *sträng*-värde som representerar koden för ett företag som tillhandahåller de inställningar som används för konverteringen.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="example"></a>Exempel

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returnerar motsvarigheten för en euro i US-dollar för det aktuella sessionsdatumet baserat på inställningarna för **DEMF**-företaget.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)
