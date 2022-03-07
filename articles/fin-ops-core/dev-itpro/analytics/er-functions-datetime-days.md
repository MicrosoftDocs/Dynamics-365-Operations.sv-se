---
title: DAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DAYS elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 310359a29a506d69d1f34aaa710a82b0f2ea528e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746901"
---
# <a name="days-er-function"></a>DAYS ER-funktion

[!include [banner](../includes/banner.md)]

Funktionen `DAYS` returnerar värdet *heltal* som representerar antalet dagar mellan ett angivet datum och ett andra angivet datum.

## <a name="syntax"></a>Syntax

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argument

`date 1`: *Datum*

Ett datumvärde som representerar det startdatum som ska användas för beräkningen av antalet dagar.

`date 2`: *Datum*

Ett datumvärde som representerar det slutdatum som ska användas för beräkningen av antalet dagar.

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

`DAYS`-funktionen returnerar ett positivt värde när det första datumet är senare än det andra, returnerar **0** (noll) när det första datumet är lika med det andra och det returnerar ett negativt värde när det första datumet är tidigare än det andra datumet.

## <a name="example"></a>Exempel

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returnerar **-1**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]