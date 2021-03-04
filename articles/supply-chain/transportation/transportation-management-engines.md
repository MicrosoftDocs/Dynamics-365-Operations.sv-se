---
title: Transporthanteringsmotorer
description: Transporthanteringsmotorer definierar logiken som används för att generera och bearbeta transporttariffer i Transporthantering.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine, TMSFreightBillTypeAssignment, TMSZoneMaster, TMSEngineParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab6667ac02ca55eeb093fa5854a962ac4357aaac
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438037"
---
# <a name="transportation-management-engines"></a>Transporthanteringsmotorer

[!include [banner](../includes/banner.md)]

Transporthanteringsmotorer definierar logiken som används för att generera och bearbeta transporttariffer i Transporthantering. 

En transporthanteringsmotor beräknar uppgifter, till exempel transportföretagets tariff. Motorsystemet låter dig ändra beräkningsstrategier vid körning baserat på data i Supply Chain Management. En transporthanteringsmotor liknar ett plugin-program som hör till ett visst transportkontrakt.

## <a name="what-engines-are-available"></a>Vilka motorer tillgängliga?
Följande tabell visar de transporthanteringsmotorer som är tillgängliga.

| Transporthanteringsmotor | Beskrivning                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tariffmotor**                  | Beräknar tariffer.                                                                                                                                                                                                                                                                                                           |
| **Allmän motor**               | Enkla hjälpmotorer som används av andra motorer och som inte behöver data från Supply Chain Management, till exempel en fördelningsmotor. Fördelningsmotorer används för att minska de slutgiltiga kostnaderna för transport till vissa order och rader som baseras på dimensioner, till exempel volym och vikt. |
| **Milkostnadsmotor**               | Beräknar transportavståndet.                                                                                                                                                                                                                                                                                     |
| **Transporttidsmotor**          | Beräknar den tid det tar att resa från start till mål.                                                                                                                                                                                                                                       |
| **Zonmotor**                  | Beräknar zon baserat på aktuell adress och beräknar antalet zoner som måste passeras för att resa från adress A till adress B.                                                                                                                                                                    |
| **Fraktsedelstyp**            | Standardiserar fraktfakturan och frakträkningsraderna och används för automatisk fraktfakturamatchning.                                                                                                                                                                                                                |


<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Vilka motorer måste konfigureras att utvärdera en försändelse?
---------------------------------------------------

Om du vill utvärdera en försändelse genom att använda ett visst transportföretag, måste du konfigurera flera transporthanteringsmotorer. **Tariffmotor** krävs, men andra transportledningsmotorer kan krävas för att stödja **Tariffmotor**. **Tariffmotor** kan till exempel användas för att hämta data från **Milkostnadsmotor** om du vill beräkna tariffen baserat på milkostnad mellan källa och mål.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>Vad krävs för att initiera en transporthanteringsmotor?
En transporthanteringsmotor kräver att du ställer in initieringsdata för att det ska fungera på ett visst sätt. Inställningen kan innehålla följande typer av data:
-   Referenser till andra transporthanteringsmotorer. Mer information finns i konfigurationexemplet i det här avsnittet.
-   Referenser till .NET-typer som används av transporthanteringsmotorn.
-   Enkla konfigurationsdata.

I de flesta fall kan du klicka på knappen **Parametrar** i transporthanteringsmotorns inställningsformulär för att konfigurera initieringsdatan. **Exempel på konfigurationen för en tariffmotor som refererar till en milkostnadsmotor** Följande exempel visar de inställningar som krävs för en tariffmotor som baseras på .NET-motortypen Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine och som refererar till en milkostnadsmotor.

|          Parameter           |                                                                                  Beskrivning                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | Den .NET-typ som tolkar tariffbastilldelningsdata för ett visst schema. Syntaxen av parametervärdet består av två segment avgränsade med ett vertikalstreck ( |
|  <em>MileageEngineCode</em>  |                       Koden för milkostnadsmotor som identifierar milkostnad motorposten i databasen.                        |
| <em>ApportionmentEngine</em> |                        Koden för allmän motor som identifierar fördelningsmotorn i databasen.                        |

<a name="how-is-metadata-used-in-transportation-management-engines"></a>Hur används metadata i transportledningsmotorer?
----------------------------------------------------------

Transporthanteringsmotorer, som utgår från data som anges i Supply Chain Management kan använda olika datascheman. Transporthanteringssystemet möjliggör för olika transportledningsmotorer att använda samma allmänna register i den fysiska databasen. Om du vill vara säker på att den körtiden för tolkningen av motordata är korrekt, kan du definiera metadata för databasregistren. Detta minskar kostnaden för att skapa nya transporthanteringsmotorer eftersom ytterligare register- och formulärstrukturer inte krävs i Operations.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Vad användas som sökningsdata i tariffberäkningar?
De data som du använder när du beräknar tariffer kontrolleras av metadatakonfigurationen. Om du till exempel vill söka efter tariffer baserat på postnummer, måste du ställa in metadata baserat på uppslagningtypen för ett postnummer.

## <a name="do-all-engine-configurations-require-metadata"></a>Kräver alla motorkonfigurationer metadata?
Nej, transporthanteringsmotorer som används för att hämta data som krävs för tariffberäkningen från externa system behöver inte metadata. Tariffdata för dessa motorer kan hämtas från externa transportföretags system, vanligen via en webbtjänst. Du kan till exempel använda en milkostnadsmotor som kan hämta data direkt från Bing-kartor, så att du inte behöver metadata för denna motor.

| **Obs!**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| De transportledningsmotorer som levereras med Supply Chain Management är beroende av data som hämtas från programmet. Motorer som ansluter till externa system inkluderas inte i Operations. Med den motorbaserade utvidgningsmodellen kan du dock bygga tillägg med hjälp av Visual Studio Tools. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Hur kan jag konfigurera metadata för en transportledningsmotor?
Metadata för transporthanteringsmotorer konfigureras olika för olika typer av motorer.

| Transporthanteringsmotor               | Metadatakonfiguration                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tariffmotor**                                | Kräver en **Tariffbastyp**. Tariffbastypen innehåller metadata för tariffbasdata och tariffbastilldelningsdata. Strukturen för metadata för tariffer bestäms av typen av tariffmotor. Strukturen för metadatan vid tilldelning av tariffbas bestäms av vilken typ av tilldelare för tariffbas som är kopplad till den tariffmotorn. Du ställer in tariffbastypen för en tariffmotor på sidan **Tariffmotor** och på sidan **Tariffmall**. |
| **Zonmotor**                                | Kräver att metadata ska ställas in direkt på zonoriginalet.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Transporttidsmotor** och **Milkostnadmotor** | Hämtar metadata direkt från milkostnadsmotorns konfigurationsinställningsformulär.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Exempel på metadata för en tariffmotor** Transportledningsmotorn kräver identifiering av ursprungsadressen, destinationens stat och land/region samt start- och slutpunkt för försändelsen. Genom att använda dessa krav ser metadata ut som i följande tabell. Registret innehåller också information om vilken typ av ingångsdata som krävs.
-   Definiera den här informationen i **Transporthantering** &gt; **Inställningar** på sidan **Tariffbastyp**.

| Sekvens | Namn                          | Fälttyp | Datatyp | Uppslagstyp    | Obligatoriskt |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Ursprungligt postnummer            | Uppdrag | Sträng    | Postnummer    | Markerad  |
| 2        | Destination – delstat             | Uppdrag | Sträng    | Ort          |           |
| 3        | Destination – från postnummer | Uppdrag | Sträng    | Postnummer    | Markerad  |
| 4        | Destination – till postnummer   | Uppdrag | Sträng    | Postnummer    | Markerad  |
| 5        | Destinationsland           | Uppdrag | Sträng    | Land/region |           |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]