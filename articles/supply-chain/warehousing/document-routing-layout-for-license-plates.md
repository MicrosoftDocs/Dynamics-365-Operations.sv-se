---
title: Etikettlayouter för dokumentflödet
description: I denna artikel beskrivs hur du använder formateringsfunktioner för att skriva ut värden på etiketter.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a4e0c16b71c257cae832870ca58679884047ea16
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708656"
---
# <a name="document-routing-label-layout"></a>Etikettlayout för dokumentflödet

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du skapar layouter för licens, behållare och cykeletiketter. Den innehåller även riktlinjer för hur du använder ZPL (Programming Language) som används för att skapa layouter.

Etikettlayouter för dokumentflöde definierar hur etiketter läggs ut och vilken data som skrivs ut på dem. Du konfigurerar utlösningspunkterna för utskrivning när du konfigurerar menyalternativ för mobilenheter och arbetsmallar.

Informationen i den här artikeln gäller för alla layouter för dokumentflödesetiketter, inklusive layouter för [registreringsskyltar](tasks/license-plate-label-printing.md), [behållaretiketter](print-container-labels.md) och [cykeletiketter](configure-wave-label-printing.md).

Du kan skriva ut mycket komplexa etiketter, förutsatt att utskriftsenheten kan tolka texten som skickas till den. En ZPL-layout som innehåller en streckkod kan till exempel likna följande exempel.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

Som en del av etikettens utskriftsprocess kommer texten `$LicensePlateId$` i det här exemplet att ersättas med ett datavärde. Många av de vanligaste verktygen för att skapa etiketter kan användas för att formatera texten i etikettexten. Många av dessa verktyg stöder `$FieldName$`-formatet. Dessutom använder Microsoft Dynamics 365 Supply Chain Management särskild formatlogik som en del av fältmappningen för layouten för dokumentflödet.

Om du vill se vilka värden som kommer att skrivas ut **Lagerstyrning \> Förfrågningar och rapporter \> ID-nummeretiketter**.

## <a name="turn-on-this-feature-for-your-system"></a>Aktivera funktionen i systemet

Om ditt system inte redan innehåller funktionerna som beskrivs i denna artikel går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Förbättrade etikettlayouter på registreringsskyltar*. (Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras.)

## <a name="custom-number-formats"></a>Anpassade nummerformat

Du kan anpassa formateringen av numeriska fältvärden som skrivs ut med hjälp av koder som har följande format.

```dos
$FieldName:FormatString$
```

Här följer en förklaring av detta format:

- `FieldName` är namnet på datafältet (t.ex. **antal**).
- `FormatString` definierar hur data måste skrivas ut.

Följande exempel visar hur du kan anpassa fältet arbetskvantitet (**antal**):

- Om du alltid vill visa fyra siffror (genom att använda nollor som platshållare) ska du använda `$Qty:0000$`. Om kvantiteten till exempel är 10 visas etiketten "0010".
- Om du alltid vill visa två decimaler använder du `$Qty:0.00$`. Om kvantiteten till exempel är 10 visas etiketten "10,00".

En fullständig lista över tillgängliga nummerformatsträngar finns i [Anpassade nummerformatsträngar](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Anpassade strängformat

Du kan ta bort de första tecknen i en sträng med hjälp av följande fält och formatkod.

```dos
$FieldName:#..$
```

Här `#` anger du antalet tecken som ska hoppas över. Om du t.ex. vill skriva ut ett ID-nummer med SSCC (Serial Shipping Container Code) som inte innehåller de första två tecknen använder du `$LicensePlateId:2..$`. I det här fallet skrivs ID-numret 0011111111111222221 ut som "11111111111222221."

## <a name="custom-datetime-formats"></a>Anpassade datum- och tidsformat

I följande exempel visas hur du kan styra det format som används för att skriva ut datum.

```dos
$PrintedDate:dd-MM-yyyy$
```

I det här exemplet skrivs 30 april 2020 ut som "30-04-2020".

En fullständig lista över tillgängliga datum-/tidsformat finns i [Anpassade formatsträngar för datum och tid](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Skriva ut enskilda rader från samköpsdata

Om ett datafält innehåller flera rader (dvs. rader som är avgränsade med radbrytningar), kan du skriva ut en enskild rad genom att använda följande format.

```dos
$FieldName[#]$
```

Här är `#` radnumret som du vill skriva ut. (Använd 1 för den första raden.)

Ditt system har till exempel ett fält `AdditionalAddress` som lagrar följande radadress:

Contoso Inc.  
123 gatunamn  
Någon stad, någon delstat

Du kan skriva ut den här adressen, en rad i taget, med hjälp av följande koder.

| Kod | Text som skrivs ut |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 gatunamn |
| `$AdditionalAddress[3]$` | Någon stad, någon delstat |

## <a name="print-and-format-from-a-display-method"></a>Skriva ut och formatera från en visningsmetod

Du kan skriva ut från en visningsmetod med hjälp av följande format.

```dos
$DisplayMethod()$
```

Du kan kombinera det här formatet med andra typer som beskrivs tidigare i denna artikel. Du har till exempel en visningsmetod med namnet `DisplayListOfItemsNumbers()` och du vill skriva ut det första artikelnumret för den här metoden. I det här fallet kan du använda följande kod.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Mer information om hur du skriver ut etiketter

Mer information om hur du konfigurerar och skriver ut etiketter finns i följande artiklar:

- [Utskrift av ID-nummeretiketten](tasks/license-plate-label-printing.md)
- [Skriv ut behållaretiketter](print-container-labels.md)
- [Utskrift av påfyllnadsetikett](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
