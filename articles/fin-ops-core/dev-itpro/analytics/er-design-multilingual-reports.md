---
title: Designa flerspråkiga rapporter i elektronisk rapportering
description: I det här avsnittet beskrivs hur du kan använda elektronisk rapporteringsetiketter för att skapa flerspråkiga rapporter.
author: NickSelin
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65efb8dbec925b5238acaa5d6769f3085e9715b9
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/12/2020
ms.locfileid: "3444631"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Designa flerspråkiga rapporter i elektronisk rapportering

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Som affärsanvändare använder du ramverket [elektronisk rapportering (ER)](general-electronic-reporting.md) för att konfigurera format för utgående dokument som måste genereras i enlighet med lagkraven för olika länder eller regioner. När de här kraven kräver att utgående dokument genereras på olika språk för olika länder eller regioner kan du konfigurera ett enskilt ER-[format](general-electronic-reporting.md#FormatComponentOutbound) som innehåller språkberoende resurser. På så sätt kan du återanvända formatet för att skapa utgående dokument för olika länder eller regioner. Du kanske också vill använda ett enda ER-format för att skapa ett utgående dokument på olika språk för motsvarande kunder, leverantörer, dotterbolag eller andra parter.

Du kan konfigurera ER-datamodeller och modellmappningar som datakällor för konfigurerade ER-format för att definiera det dataflöde som anger vilka appdata som placeras i genererade dokument. Som en ER-konfiguration [provider](general-electronic-reporting.md#Provider), du kan [publicera](tasks/er-upload-configuration-into-lifecycle-services.md#upload-configuration-into-lcs) konfigurerade [datamodeller](general-electronic-reporting.md#data-model-and-model-mapping-components), [modellmappning](general-electronic-reporting.md#data-model-and-model-mapping-components) och [format](general-electronic-reporting.md#FormatComponentOutbound) som komponenter i en ER-lösning för att generera specifika utgående dokument. Du kan också tillåta kunder att [överföra](general-electronic-reporting-manage-configuration-lifecycle.md) den publicerade ER-lösningen så att den kan användas och anpassas. Om du tror att kunderna kan tala om andra språk kan du konfigurera ER-komponenterna så att de innehåller språkberoende resurser. På så sätt kan innehållet i en redigerbar återställningskomponent visas på kundens användarspråk vid designtillfället.

Du kan konfigurera språkberoende resurser som ER-etiketter. Du kan sedan använda dessa etiketter för att konfigurera ER-komponenter i följande syfte:

- I designläge:

    - Presentera innehållet i de konfigurerade återställningskomponenterna på det språk som användaren föredrar.

- Vid körning:

    - Generera språkberoende innehåll för utgående dokument.
    - Innehåller varnings- och felmeddelanden på det språk som användaren föredrar.
    - Fråga efter obligatoriska fält på användarens önskade språk.

ER-etiketter kan konfigureras i varje ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller olika komponenter. Etiketterna kan underhållas oberoende av den konfigurerade logiken för ER-datamodeller, ER-modellmappningar och ER-formatkomponenter.

Alla ER-etiketter identifieras med ett ID som är unikt i omfånget för ER-konfigurationen som innehåller den etiketten. Alla etiketter kan innehålla etikettext för alla språk som stöds i den aktuella instansen av Microsoft Dynamics 365 Finance. Dessa språk som stöds omfattar språken i distribuerade anpassningar.

## <a name="entry"></a>Post

När du utformar en ER-datamodell, en ER-modellmappning eller ett ER-format visas alternativet **Översätt** varje gång du väljer ett fält som kan innehålla översättningsbart sammanhang. När du väljer det här alternativet kan du länka det markerade fältet till en ER-etikett i **textöversättning** <a name="TextTranslationPane">-fönstret</a>. Du kan välja en befintlig ER-etikett eller lägga till en ny ER-etikett om den inte är tillgänglig ännu. När du väljer eller lägger till en ER-etikett kan du lägga till relaterad text för varje språk som stöds i den aktuella ekonomiinstansen.

Följande illustration visar hur översättningen görs i en redigerbar ER-datamodell. I det här exemplet översätts attributet **Beskrivning** i fältet **PurchaseOrder** för den redigerbara **Fakturamodellen** till österrikisk tyska (DE-AT) och japanska (JA).

![Ge översättning av en ER-etikett i ER-datamodelldesigner](./media/er-multilingual-labels-refer.png)

Endast etikettext för etiketter som finns i en redigerbar återställningskomponent kan översättas. Om du t.ex. väljer **Översätt** för attributet etikett i en datakälla för ER-modellmappning och sedan väljer en ER-etikett som finns i den överordnade ER-datamodellen, visas innehållet i etiketten, men du kan inte ändra det. I dessa fall är fältet **översatt text** inte tillgängligt, som visas i bilden nedan.

![Granska medföljande översättning av en ER-etikett i ER-modellmaningsdesigner](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Du kan inte använda designer för att ta bort en etikett som har angetts i en redigerbar ER-komponent.

## <a name="scope"></a>Område

ER-etiketter kan refereras till i flera översättningsbara attribut i ER-komponenter.

### <a name="data-model-component"></a>Datamodellkomponent

När du konfigurerar en ER-datamodell kan du lägga till ER-etiketter för den. Attributen **Etikett** och **Beskrivning** för modellartikeln, varje modells fält och varje <a id="LinkModelEnum"></a>modelluppräkningsvärde kan länkas till en ER-etikett som läggs till i ER-datamodellen.

![Tillhandahålla översättning för attributet beskrivning i ER-datamodelldesigner](./media/er-multilingual-labels-refer.png)

När en ER-datamodell konfigureras på det här sättet visas dess innehåll för användarna av ER-datamodelldesigner på varje användares prioriterade språk. Modellunderhåll är därför förenklat. Följande bilder visar hur den här funktionen fungerar för användare med inställd DE-AT och JA som önskat språk.

![Layout för ER-datamodelldesigner för en användare som har inställt DE-AT som sitt prioriterade språk](./media/er-multilingual-labels-refer-de.png)

![Layout för ER-datamodelldesigner för en användare som har inställt JA som sitt prioriterade språk](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Komponent för modellmappning

Eftersom ER-modellmappning baseras på en ER-datamodell, visas etiketterna för de datamodellelement som refereras till på användarens önskade språk i modellmappningsverktyget. Följande bild visar hur betydelsen av fältet **PurchaseOrder** beskrivs i den redigerbara modellmappningen genom att använda etiketten för attributet **Beskrivning** som har lagts till i den konfigurerade datamodellen. Observera att etiketten visas på användarens önskade språk (DE-AT i det här exemplet).

![Layout för ER-mappningsdesigner för en användare som har inställt DE-AT som sitt prioriterade språk](./media/er-multilingual-labels-show-mapping.png)

När attributet **Etikett** i datakällan **Användarindataparametrar** har konfigurerats som länkad till en ER-etikett, visas det parameterfält som motsvarar denna data källa i dialogrutan för användare under körning till användarna på det språk de föredrar.

### <a name="format-component"></a>Formatkomponent

När du konfigurerar en ER-format kan du lägga till ER-etiketter för den. Attribut **Etikett** och **Hjälptext** för varje konfigurerad datakälla kan länkas till en ER-etikett som har lagts till i ER-format. Attributen **etikett** och **beskrivning** i varje <a id="LinkFormatEnum"></a>format uppräkningsvärde kan också länkas till en ER-etikett som kan användas från det redigerbara återställningsformatet.

> [!NOTE]
> Du kan också länka dessa attribut till en ER-etikett för den överordnade ER-datamodellen som återanvänder modellens etiketter i varje återställnings format som har konfigurerats för den här ER-datamodellen.

När en ER-format konfigureras på det här sättet visas dess innehåll för format av ER-åtgärdsdesigner på varje användares prioriterade språk. Därför förenklas formatunderhåll och analys av den konfigurerade logiken.

Eftersom ER-format baseras på en ER-datamodell, visas etiketterna som hänvisas till i datamodellelement presenterade i ER-formatdesigner på användarens önskade språk i.

När attributet **Etikett** i datakällan **Användarindataparametrar** länkas till en ER-etikett, visas det parameterfält som motsvarar parametern i dialogrutan för användare som presenteras under körning till användarna som en uppmaning. I följande illustrationer visas hur du kan länka attributet **Etikett** för datakällan **Användarindataparametrar** vid designtillfället till en ER-etikett, så att användarna uppmanas att ange parametern i olika språk (visas för engelska USA (en-US) och DE-AT de språk som används) under körning.

![Tillhandahålla översättning av attribut för en indataparameter av ett ER-åtgärdsdesigner](./media/er-multilingual-labels-refer-format.png)

![ER leverantörs betalningsbearbetning vid körning för ett EN-US användarens prioriterade språk](./media/er-multilingual-labels-show-runtime-en.png)

![ER leverantörs betalningsbearbetning vid körning för ett DE-AT användarens prioriterade språk](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Uttryck

Om du vill använda en etikett i ett ER [uttryck](er-formula-language.md) måste du använda syntaxen **@"GER\_LABEL:X"**, där prefixet **@** indikerar att operanden refererar till en etikett **GER\_LABEL** anger att en ER-etikett är involverad och **X** är ER-etikett-ID.

![Konfigurera ett ER-uttryck som innehåller en referens till en ER-etikett i ER-formeldesigner](./media/er-multilingual-labels-expression1.png)

Om du vill referera till en systemetikett (program) använder du syntaxen **@"X"**, där prefixen **@** indikerar att operanden refererar till en etikett och **X** är systemets etikett-ID.

![Konfigurera ett ER-uttryck som innehåller en referens till en appetikett i ER-formeldesigner](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Modellmappning

Du kan konfigurera ett uttryck för en ER-modell genom att använda en etikett. När den här mappningen anropas av ett ER-format som körs för att generera ett utgående dokument, innehåller kontexten för körningen en språkkod. En konfigurerad uttrycksetikett fylls i med den etikettext som har konfigurerats för det aktuella språket i kontexten.

Om en refererad etikett inte har någon översättning för språket i den formatkontext som anropar modellmappningen används etikettexten i EN-US-språk i stället.

#### <a name="format"></a>Format

Du kan konfigurera ett ER-uttryck för en ER-format genom att använda etiketter. När detta format körs för att generera ett utgående dokument, innehåller kontexten för körningen en språkkod. En konfigurerad uttrycksetikett fylls i med den etikettext som har konfigurerats för det aktuella språket i kontexten.

![Tillhandahålla översättning av en ER-etikett för det redigerbara ER-uttrycket i ER-formeldesigner](./media/er-multilingual-labels-refer-in-expression.png)

![Exempel på databindning som refererar till en ER-etikett i ER-åtgärdsdesigner](./media/er-multilingual-labels-refer-in-binding.png)

Du kan konfigurera **FIL**-komponenten i ett ER-format om du vill generera rapporten på användarens önskade språk.

![Ställ in FIL-komponenten i ER-åtgärdsdesigner för att generera rapporten på användarens önskade språk](./media/er-multilingual-labels-language-context-user.png)

Om du konfigurerar ett ER-format på det här sättet genereras rapporten med hjälp av motsvarande text i ER-etiketterna. I följande illustrationer visas exempel på rapporter för användarspråken EN-US och DE-AT.

![Förhandsgranskning av rapporten som har genererats i EN-US-användares prioriterade språk](./media/er-multilingual-labels-report-preview-en.png)

![Förhandsgranskning av rapporten som har genererats i DE-AT-användares prioriterade språk](./media/er-multilingual-labels-report-preview-de.png)

Om en refererad etikett inte har någon översättning för språket i den formatkontext används etikettexten i EN-US-språk i stället.

## <a name="language"></a>Språk

ER har olika sätt att ange ett språk för en genererad rapport. I fältet **Språkinställningar** på fältet **Format** kan du välja följande värden:

- **Företagspreferens** – Generera en rapport på ett av företaget angivna språk.

    ![Ange i formuläret ER-åtgärdsdesigner som designer ett företag som anger vilket språk som en genererad rapport ska utföras på](./media/er-multilingual-labels-language-context-company.png)

- **Användarinställningar** – Generera en rapport på användarens önskade språk.
- **Explicit definierad** – Generera en rapport på ett språk som anges i designläge.

    ![Ange i ER-åtgärdsdesigner ett designtidsspråk som språket i en genererad rapport](./media/er-multilingual-labels-language-context-fixed.png)

- **Definierade under körning** – Generera en rapport på ett språk som anges i körning. Om du väljer det här värdet ska du i fältet **Språk** konfigurera ett ER-uttryck som returnerar språk koden för språket, t.x. det språk som tillhör motsvarande kund.

    ![Ange i ER-åtgärdsdesigner en körning definieras språket i en genererad rapport](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="translation"></a>Översättning

Du kan lägga till obligatoriska ER-etiketter i en redigerbar ER-komponent. När en ER-etikett läggs till kan den översättas på två sätt: manuellt och automatiskt.

### <a name="manual-translation"></a>Manuell översättning

När du lägger till en ER-etikett **Textöversättning** [fönstret](#TextTranslationPane), kan du manuellt översätta den till alla språk som stöds i den aktuella Finance-instansen. Du kan välja önskat språk i fältet **Språk** i avsnittet **Systemspråk** eller **Användarspråk** anger du lämplig text i motsvarande fält för **Översatt text** och väljer sedan **Översätt**. Processen måste upprepas för alla språk som krävs och alla etiketter som du lägger till.

### <a name="automatic-translation"></a>Automatisk översättning

Konfigurationen av en ER-komponent görs i utkastversionen av ER-konfigurationen som den redigerbara återställningskomponenten finns i.

![Sidan ER-konfigurationer ger åtkomst till konfigurationens version i utkaststatus](./media/er-multilingual-labels-configurations.png)

Som tidigare nämnts i det här avsnittet kan du lägga till nödvändiga ER-etiketter till en redigerbar ER-komponent. På det här sättet kan du ange texten i ER-etiketterna på språket EN-US. Du kan sedan exportera etiketterna för ER-komponenten med hjälp av den inbyggda ER-funktionen. Markera utkastversionen av en ER-konfiguration som innehåller den redigerbara ER-komponenten och välj sedan **Byt \> Exportetiketter**.

![Sidan ER-konfigurationer som tillåter export av ER-etiketter från den valda konfigurationsversionen](./media/er-multilingual-labels-export.png)

Du kan exportera antingen alla etiketter eller etiketterna för ett enskilt språk som du anger i början av exporten. Etiketter exporteras som zip-filer som innehåller XML-filer. Alla XML-filer innehåller etiketter för ett enskilt språk.

![Exempel på den exporterade filen som innehåller ER-etiketter för språket DE-AT](./media/er-multilingual-labels-in-xml.png)

Det här formatet används för automatisk översättning av etiketter med externa översättningstjänst som [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). När du får de översatta etiketterna kan du importera dem tillbaka till utkastversionen av en ER-konfiguration som innehåller de ER-komponenter som äger dessa etiketter. Markera utkastversionen av en ER-konfiguration som innehåller den redigerbara ER-komponenten och välj sedan **Byt \> Lastetiketter**.

![Sidan ER-konfigurationer som tillåter import av ER-etiketter till den valda konfigurationsversionen](./media/er-multilingual-labels-load.png)

Översatta etiketter importeras till den valda ER-konfigurationen. Översatta etiketter som finns i denna ER-konfiguration ersätts. Om en översatt etikett saknas i ER-konfigurationen, läggs den till.

## <a name="lifecycle"></a>Livscykel

Etiketter för en ER-komponent som kan redigeras behålls, tillsammans med annat innehåll för komponenten, i en lämplig version av en ER-konfiguration.

Etiketter för en grundläggande ER-komponent kan refereras till en härledd version av ER-komponenten som du skapar för att införa dina ändringar.

ER-versioner kontrollerar etiketttilldelningen till alla attribut i en ER-komponent. Ändringar i etikettilldelningen registreras i listan över ändringar (delta) i en redigerbar ER-komponent som har skapats som en härledd version av den angivna ER-komponenten. Ändringarna kommer att valideras när en härledd version baseras på en ny grundläggande version.

## <a name="functions"></a>Funktioner

Den inbyggda ER-funktionen [LISTOFFIELDS](er-functions-list-listoffields.md) kan komma åt ER-etiketter som har konfigurerats för vissa artiklar i ER-komponenter.

Som tidigare nämnts i det här avsnittet **Etikett** och **Beskrivning** för varje [modell](#LinkModelEnum) eller [format](#LinkFormatEnum) ER-uppräkningens värde kan kopplas till en ER-etikett som är tillgänglig i rätt ER-komponent. Du kan konfigurera ett ER-uttryck där du anropar funktionen **LISTOFFIELDS** genom att använda ER-uppräkning som argument. Det här uttrycket returnerar en lista som innehåller en post för varje värde av en ER-uppräkning som har definierats som argument för den här funktionen. Varje post innehåller värdet för en ER-etikett som är länkad till ett ER-uppräkningsvärde:

- Värdet för en ER-etikett som är länkad till attributet **etikett** lagras i fältet **etikett** för den returnerade posten.
- Värdet för en ER-etikett som är länkad till attributet **Beskrivning** lagras i fältet **Beskrivning** för den returnerade posten.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Funktioner för elektronisk rapportering](er-formula-language.md#functions)
