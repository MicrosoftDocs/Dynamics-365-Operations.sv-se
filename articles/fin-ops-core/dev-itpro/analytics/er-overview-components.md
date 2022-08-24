---
title: Komponenter för elektronisk rapportering
description: Det här ämnet beskriver komponenterna för Elektronisk rapportering (ER).
author: kfend
ms.date: 09/28/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: 4851374ca4943a84d35f063e0ee65b537ec3b6cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285044"
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
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar rapportgenereringen vid körning beroende på löpande kontext. Det kan exempelvis finnas en regel som stoppar utgående generering av en viss leverantörs betalningar, och som skapar ett undantag när specifika attribut för den valda providern saknas, till exempel bankkontonummer.

En formatkomponent har stöd för följande funktioner:

- Skapa rapporteringsutdata som enskilda filer i olika format, till exempel text, XML Microsoft Word-dokument eller kalkylblad
- Skapa flera filer separat och även packa dem i zip-filer

En formatkomponent låter dig bifoga vissa filer som kan användas i rapporteringsutdatan:

- Excel-arbetsböcker som innehåller ett kalkylblad som kan användas som en mall för utdata i OPENXML-kalkylbladsformat
- Word-filer som innehåller ett dokument som kan användas som en mall för utdata i Microsoft Word-dokumentformat
- Andra filer som kan ingå i formatets utdata som fördefinierade filer.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för utgående formatkomponenter](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Du måste identifiera mappningen av formatkonfigurationen för att kunna köra en enskild ER formatkonfiguration och skapa utgående elektroniska dokument.

#### <a name="format-components-for-incoming-electronic-documents"></a>Formatkomponenter för inkommande elektroniska dokument
En formatkomponent är schemat för de inkommande dokument som importeras vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i de inkommande elektroniska dokument som innehåller data som importeras vid körning. En formatkomponent används för att tolka ett inkommande dokument i olika format, till exempel text och XML.
- En formatmappning som binder enskilda formatelement till element i en domänspecifik datamodell. Vid körning anger elementen i datamodellen dataflödet och reglerna för import av data från ett inkommande dokument, och spara sedan datan i en datamodell.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar dataimporten vid körning, beroende på körningskontexten. Det kan exempelvis finnas en regel som stoppar dataimporten av ett bankutdrag med en viss leverantörs betalningar, och som skapar ett undantag när attributen för en specifik leverantör saknas, till exempel ID-koden för providern.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för inkommande formatkomponenter](./media/ER-overview-03.png)](./media/ER-overview-03.png)

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

Mer information finns i [Importera en ny datamodellkonfiguration](er-quick-start1-new-solution.md#ImportDataModel) och [Exportera slutförd justerad version av ett härlett format](er-calculated-field-type.md#export-completed-version-of-a-derived-format).

### <a name="draft-versions-at-runtime"></a>Utkastversioner vid körning

I dina personliga användarparametrar för ER-ramverket kan du aktivera alternativet som gör att du kan ange om utkastversionen av en ER-konfiguration måste användas vid körning. Information om hur du gör alternativet **Kör utkast** tillgängligt för ER-konfigurationer finns i [Markera ett anpassat format som kan köras](er-quick-start2-customize-report.md#MarkFormatRunnable).

> [!NOTE]
> ER-användarparametrar är företagsspecifika och användarspecifika.

### <a name="draft-format-versions-at-runtime"></a>Utkastformat versioner vid körning

När du kör en ER-lösning ignoreras som standard utkastversionerna av dess formatkomponenter. I stället används bara den relevanta version som har ett annat status än **Utkast**. Ibland kanske du vill tvinga ER att använda utkastversionen av ER-formatkonfigurationen vid körning. När du har presenterat nödvändiga ändringar i utkastversionen kan du till exempel använda den utkastversionen för att testa körningen. På så sätt kan du verifiera att dina ändringar är korrekta. För att börja använda versionen av utkastformatet måste du [ange](er-quick-start2-customize-report.md#MarkFormatRunnable) alternativet **Kör utkast** av den relevanta ER-konfigurationen till **Ja**.

### <a name="draft-model-mapping-versions-at-runtime"></a>Utkastmodell mappningsversioner vid körning

När du kör en ER-lösning ignoreras som standard utkastversionerna av komponenter för modellmappning används alltid. Ibland kanske du vill tvinga ER att ignorera utkastversionen av konfiguration av ER-modellmappning vid körning. I **version 10.0.29 och senare** kan du aktivera alternativet **Alltid ta hänsyn till alternativet "Kör utkast" för ER-modellmappning** för att kontrollera den modellmappningsversion som används när programmet körs. När den här funktionen är aktiverad, sker följande beteende:

- När alternativet **Kör utkast** ställs in på **Nej** för en modellmappning konfiguration används den högsta icke-utkastversionen av den konfigurationen vid körning. Ett undantag utlöstes av en konfiguration som inte är tillgänglig i den aktuella ekonomiinstansen.
- När alternativet **Kör utkast** ställs in på **Ja** för en modellmappning konfiguration används utkastversionen av den konfigurationen vid körning.

## <a name="component-date-effectivity"></a>Komponent giltighetsdatum

ER-format komponentversionerna har giltighetsdatum. Du kan ange Gäller från-datumet för en ER-format komponent för att ange från och med vilket datum komponenten ska aktiveras för rapporteringsprocesser. Programmets sessionsdatum används för att definiera om en komponent är giltig för körning. Den senaste versionen används för rapporteringsprocesser om fler än en version är giltig för ett visst datum.

## <a name="component-access"></a>Åtkomsten till komponenter

Åtkomsten till ER-format och modellmappning komponenter vid körning beror på inställningen för Internationella standardiseringsorganisationen (ISO) lands-/regionskod. När den här inställningen är tom för en vald version av en konfiguration av format eller modellmappning kan format- eller modellmappningskomponenten nås från vilket företag som helst vid körning. När inställningen innehåller ISO-lands-/regionskoder är format- eller modellmappningskomponent endast tillgänglig från de företag som har en primäradress som är definierad för en av en formatkomponents ISO-lands-/regionskoder.

Olika versioner av en format- eller modellmappningskomponent kan ha olika inställningar för ISO-lands-/regionskoder.

För mer information, se [Konfigurera ER-modellmappningar som är beroende av landssammanhang](er-country-dependent-model-mapping.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

