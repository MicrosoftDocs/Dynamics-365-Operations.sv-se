---
title: Funktionen DATETODATETIME ER
description: Det här avsnittet innehåller information om hur funktionen DATETODATETIME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: eac09c9b410815ad9ae71dec53fc0416b020ca1e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744825"
---
# <a name="datetodatetime-er-function"></a>Funktionen DATETODATETIME ER

[!include [banner](../includes/banner.md)]

`DATETODATETIME` funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).

## <a name="syntax"></a>Syntax

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argument

`date`: *Datum*

Ett datumvärde som representerar datumet som ska konverteras.

## <a name="return-values"></a>Returvärden

*Datum/tid*

Det resulterande datum/tid-värdet.

## <a name="example-1"></a>Exempel 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')`-returnerar datumet för den aktuella Microsoft Dynamics 365 Finance-sessionen, 24 december 2015, som **12/24/2015 12:00:00 AM**. I det här exemplet är **CompInfo** en ER-datakälla (Elektronisk rapportering) av typen **Finance and Operations/tabell** och refererar till CompanyInfo-tabellen.

## <a name="example-2"></a>Exempel 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returnerar datum/tid-värdet **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)
