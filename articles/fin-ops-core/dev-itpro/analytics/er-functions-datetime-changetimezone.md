---
title: CHANGETIMEZONE ER funktion
description: Den här artikeln innehåller information om hur funktionen CHANGETIMEZONE elektronisk rapportering (ER) används.
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: d732fd8bd44c4c131f376919b2546a7ecf668495
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286132"
---
# <a name="changetimezone-er-function"></a>CHANGETIMEZONE ER funktion

[!include [banner](../includes/banner.md)]

Funktionen `CHANGETIMEZONE` returnerar värdet *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* i Coordinated Universal Time (Greenwich Mean Time \[GMT\]) som konverteras från ett givet datum/tidsvärde i en tidszon till ett datum/tidsvärde i en annan tidszon.

## <a name="syntax"></a>Syntax

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argument

`datetime`: *DateTime*

Ett datum-/tidsvärde i tidszonen Coordinated Universal Time som representerar det datum/det tidsvärde som ska konverteras.

`base time zone`: *[Sträng](er-formula-supported-data-types-primitive.md#string)*

Namnet på den tidszon som ett givet datum-/tidsvärde flyttas till före konvertering.

`target time zone`: *Sträng*

Namnet på den tidszon som ett konverterat datum-/tidsvärde flyttas till under konvertering.

## <a name="return-values"></a>Returvärden

*DatumTid*

Resultatvärdet för datum/tid i tidszonen Coordinated Universal Time.

## <a name="usage-notes"></a>Användningsanteckningar

För att ange käll- och måltidszoner kan du använda tidszonsnamn som är [tillhandahålls](https://data.iana.org/time-zones/releases/) av [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/) eller [stöds](/windows-hardware/manufacture/desktop/default-time-zones) av Microsoft Windows.

Vid körning är undantaget "Tidszon '\<time zone name\>' existerar inte" kastas om det angivna namnet inte finns i IANA-listan eller i Windows-registret.

För tidszoner där det finns sommartid tar konverteringen hänsyn till förskjutningen av sommartid i Coordinated Universal Time. Den senaste tillgängliga informationen om den här motbokningen används under konverteringen.

## <a name="example-1"></a>Exempel 1

I det här exemplet används tidszonnamnen för Windows.

Du konfigurerar **DSX**-datakällan för typen **beräknade fält**. Det innehåller följande uttryck.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Om du konfigurerar **DSY** datakällan **Calculated field** typen som `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, **DSX** datakällan returnerar texten **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Denna text visar att tidsskillnaden mellan de två angivna tidszonerna den 1 juni är mer än 24 timmar. Därför är det konverterade värdet för datum/tid en dag tidigare än det angivna datumet/tidsvärdet, eftersom bastidszonen ligger före måltidszonen.

Om du konfigurerar **DSY** datakällan **Calculated field** typen som `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, **DSX** datakällan returnerar texten **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Denna text visar att tidsskillnaden mellan de två angivna tidszonerna den 1 december är mindre än 24 timmar. Därför är det konverterade värdet för datum/tid lika med det angivna datum-/tidsvärdet.

> [!NOTE]
> Samma uttryck returnerar en annan avvikelse mellan det angivna och de konverterade datum-/tidsvärdena för samma par tidszoner eftersom en annan tidsförskjutning för utjämnad universaltid används för de angivna tidszonerna vid ett visst datum/en viss tid.

## <a name="example-2"></a>Exempel 2

I det här exemplet används IANA tidszonnamnen.

Du konfigurerar **DSX**-datakällan för typen **beräknade fält**. Det innehåller följande uttryck.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Om du konfigurerar **DSY** datakällan **Calculated field** typen som `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, **DSX** datakällan returnerar texten **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Denna text visar att tidsskillnaden mellan de två angivna tidszonerna den 1 juni är mer än 24 timmar. Därför är det konverterade värdet för datum/tid en dag tidigare än det angivna datumet/tidsvärdet, eftersom bastidszonen ligger före måltidszonen.

Om du konfigurerar **DSY** datakällan **Calculated field** typen som `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, **DSX** datakällan returnerar texten **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Denna text visar att tidsskillnaden mellan de två angivna tidszonerna den 1 december är mindre än 24 timmar. Därför är det konverterade värdet för datum/tid lika med det angivna datum-/tidsvärdet.

## <a name="example-3"></a>Exempel 3

Du konfigurerar **DSX**-datakällan för typen **beräknade fält**. Det innehåller följande uttryck.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Om du konfigurerar **DSY** datakällan **Calculated field** typen som `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, **DSX** datakällan returnerar texten **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00**. Denna text visar att tidsskillnaden mellan de två angivna tidszonerna den 1 juni är mer än 24 timmar. Därför är det konverterade värdet för datum/tid en dag senare än det angivna datumet/tidsvärdet, eftersom måltidszonen ligger före bastidszonen.

## <a name="example-4"></a>Exempel 4

Du kan få en datum-/tidsstämpel från en extern källa som text som saknar tidszoninformation. Du kanske emellertid känner till den tidszon som källan används för. Du får till exempel datum-/tidsstämpel **01/12/2021 12:55:00** från en tjänst som drivs i Spanien. Slutför följande konvertering om du vill spara datum-/tidsvärdet i databasen:

- Konfigurera **DSY** datakällan av typen **Beräkningsfält** för att konvertera datum/tidsstämpel från text till Coordinated Universal Time datum/tidsvärde.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Konfigurera **DSX** datakällan för typen **beräkningsfält** om du vill växla det konverterade datum-/tidsvärdet till Coordinated Universal Time som datum-/tidsvärde för den externa källans tidszon.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> När du använder funktionen `CHANGETIMEZONE` för konvertering av datum/tid, var medveten om att alla datum-/tidsvärden lagras i databasen som värdet i tidszonen Coordinated Universal Time. Innan detta värde kan visas på programsidorna transformeras det. Transformeringen tar hänsyn till tidszonen som har [ställts in](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) som prioriterad zon för den programanvändare som för närvarande är inloggad.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
