---
title: Komponenter för elektronisk rapportering
description: Det här ämnet beskriver komponenterna för Elektronisk rapportering (ER).
author: nselin
ms.date: 09/28/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.topic: overview
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a24aa52c805722c20045b6227ceac0103cfbe6b
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2022
ms.locfileid: "8324045"
---
# <a name="electronic-reporting-components"></a>Komponenter för elektronisk rapportering

[!include [banner](../includes/banner.md)]

Elektronisk rapportering (ER) stöder följande typer av komponenter:

- Datamodell
- Modellmappning
- Format
- Metadata

## <a name="data-model-component"></a>Datamodellkomponent

En datamodellskomponent är en abstrakt representation av en datastruktur. Det beskriver en specifik domän för ett visst affärsområde tillräckligt detaljerat för att uppfylla rapporteringskraven för domänen. En datamodellkomponent för omfattar följande delar:

- **Datamodell** – En datamodell som en uppsättning domänspecifika affärsenheter och en hierarkiskt strukturerad definition av relationer mellan dem.
- **Modellmappning** – Valda programdatakällor är länkade till enskilda element i en datamodell som vid körning specificerar dataflöde och regler för att ange affärsdata i en datamodellkomponent.

En affärsenhet av datamodellen representeras som en behållare eller post. Affärsenhetsegenskaper återges som dataobjekt eller fält. Varje dataobjekt har ett unikt namn, en unik etikett, en unik beskrivning och ett unikt värde. Värdet på respektive dataobjekt kan vara utformat så att det tolkas som en sträng, ett heltal, ett realtal, ett datum, en uppräkning, (enum) eller booleskt värde. Dessutom kan dataposten vara en annan post eller postlista.

En enskild datamodellskomponent kan innehålla flera hierarkier av domänspecifika affärsenheter. Den kan också innehålla modellmappningar som har stöd för ett rapportspecifikt dataflöde vid körning. Hierarkierna särskiljs av en enda post som har valts som rot för modellmappningen. Datamodellen för betalningsdomänområdet kan exempelvis stödja följande mappningar:


- Företag \> Leverantör -\> Betalningstransaktioner i AP-domänen
- Kund \> Företag -\> Betalningstransaktioner i AR-domänen

Affärsenheter såsom företags- och betalningstransaktioner skapas en gång. Olika mappningar kan återanvändas efter behov.

## <a name="model-mapping-component"></a>Komponent för modellmappning

Modellmappning länkar programdatakällor till enskilda element i en datamodell som vid körning specificerar dataflöde och regler för att ange affärsdata i en datamodellkomponent.

En modellmappning som har stöd för utgående elektroniska dokument har följande funktioner:

- Den kan använda olika datatyper som datakällor för en datamodell. Dessa datatyper inkluderar tabeller, dataenheter, metoder och uppräkningar.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.
- Den stöder datatransformeringen till erforderliga grupper. Dessutom kan du filtrera, sortera och summera data, samt lägga till logiska, beräknade fält som utformas via formler som liknar Microsoft Excel-formler. Mer information finns i [Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md).

En modellmappning som har stöd för inkommande elektroniska dokument har följande funktioner:

- Olika uppdateringsbara dataelement används som mål. Dessa dataelement inkluderar tabeller, dataenheter och vyer. Datan kan uppdateras med inkommande data från elektroniska dokument. Flera mål kan användas i en enda modellmappning.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.

En datamodellkomponent har utformats för varje affärsdomän som används som en enhetlig datakälla för rapportering. Den enhetliga datakällan används för rapportering från den fysiska implementeringen av datakällor. Komponenten representerar domänspecifika affärsbegrepp och -funktioner i ett formulär som utgör ett rapporteringsformulärs ursprungliga konstruktion och vidare underhåll effektivare.

## <a name="format-component"></a>Formatkomponent

### <a name="format-components-for-outgoing-electronic-documents"></a>Formatkomponenter för utgående elektroniska dokument

En formatkomponent är schemat för de rapporteringsutdata som skapas vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i det utgående elektroniska dokument som skapas vid körning.
- Datakällor som en uppsättning parametrar för användarindata och en domänspecifik datamodell som använder en vald modellmappning.
- En formatmappning som en uppsättning bindningar av formatdatakällor som har vissa element i ett format som vid körning specificerar dataflödet och reglerna för formatets utdatagenerering.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar rapportgenereringen vid körning beroende på löpande kontext. Det kan exempelvis finnas en regel som stoppar utgående generering av en viss leverantörs betalningar, och som skapar ett undantag när specifika attribut för den valda leverantören saknas, till exempel bankkontonummer.

En formatkomponent har stöd för följande funktioner:

- Skapa rapporteringsutdata som enskilda filer i olika format, till exempel text, XML Microsoft Word-dokument eller kalkylblad
- Skapa flera filer separat och även packa dem i zip-filer

En formatkomponent låter dig bifoga vissa filer som kan användas i rapporteringsutdatan:

- Excel-arbetsböcker som innehåller ett kalkylblad som kan användas som en mall för utdata i OPENXML-kalkylbladsformat
- Word-filer som innehåller ett dokument som kan användas som en mall för utdata i Microsoft Word-dokumentformat
- Andra filer som kan ingå i formatets utdata som fördefinierade filer.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för inkommande formatkomponenter.](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Om du vill köra en enskild ER formatkonfiguration för att importera data från ett inkommande elektroniskt dokument måste du identifiera önskad mappning för en formatkonfiguration, samt även integreringspunkten för en modellmappning. Du kan använda samma modellmappning och mål tillsammans med olika format för olika typer av inkommande dokument.

## <a name="component-versioning"></a>Komponentversionsnumrering

Versionsnumrering stöds för ER-komponenter. Följande arbetsflöde tillhandahålls för att hantera ändringar i ER-komponenter:

1. Den version som ursprungligen skapades är markerad som en **Utkast**-version. Den här versionen kan redigeras och är tillgänglig för provkörningar.
2. **Utkast**-versionen kan konverteras till en **Slutförd** version. Den här versionen kan användas i lokala rapporteringsprocesser.
3. Den **Slutförda** versionen kan konverteras till en **Delad** version. Denna version publiceras i Microsoft Dynamics Lifecycle Services (LCS) och kan användas inom globala rapporteringsprocesser.
4. **Delad**-versionen kan konverteras till en **Avslutad** version. Den här versionen kan sedan tas bort.

Versioner som har statusen **Slutförd** eller **Delad** är tillgängliga för annan dataöverföring. Följande åtgärder kan utföras på en komponent som har dessa statusvärden:

- Komponenten kan serialiseras i XML-format och exporteras från en XML-fil.
- Komponenten kan omserialiseras från en XML-fil och importeras till programmet som en ny version av en ER-komponent.

## <a name="component-date-effectivity"></a>Komponent giltighetsdatum

ER-komponentversionerna har giltighetsdatum. Du kan ange Gäller från-datumet för en ER-komponent för att ange från och med vilket datum komponenten ska aktiveras för rapporteringsprocesser. Programmets sessionsdatum används för att definiera om en komponent är giltig för körning. Den senaste versionen används för rapporteringsprocesser om fler än en version är giltig för ett visst datum.

## <a name="component-access"></a>Åtkomsten till komponenter

Åtkomsten till ER-formatkomponenter beror på inställningen för Internationella standardiseringsorganisationen (ISO) lands-/regionskod. När den här inställningen är tom för en vald version av en formatkonfiguration kan formatkomponenten nås från vilket företag som helst vid körning. När inställningen innehåller ISO-lands-/regionskoder är formatkomponenten endast tillgänglig från de företag som har en primäradress som är definierad för en av en formatkomponents ISO-lands-/regionskoder.

Olika versioner av en dataformatkomponent kan ha olika inställningar för ISO-lands-/regionskoder.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

