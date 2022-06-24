---
title: Funktionen CONVERTCURRENCY ER
description: Den här artikeln innehåller information om hur funktionen CONVERTCURRENCY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e51086d977652e4be4c19390a824d4f4507b60d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898474"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]