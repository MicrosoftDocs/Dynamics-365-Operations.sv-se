---
title: Designa flerspråkiga rapporter i elektronisk rapportering
description: I det här avsnittet beskrivs hur du kan använda elektronisk rapporteringsetiketter för att skapa flerspråkiga rapporter.
author: NickSelin
ms.date: 04/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa8297d4f5c56a7a20561b1a90c5852e65dbff31
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811619"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Designa flerspråkiga rapporter i elektronisk rapportering

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Som affärsanvändare använder du ramverket [elektronisk rapportering (ER)](general-electronic-reporting.md) för att konfigurera format för utgående dokument som måste genereras i enlighet med lagkraven för olika länder eller regioner. När de här kraven kräver att utgående dokument genereras på olika språk för olika länder eller regioner kan du konfigurera ett enskilt ER-format som innehåller språkberoende resurser. På så sätt kan du återanvända formatet för att skapa utgående dokument för olika länder eller regioner. Du kanske också vill använda ett enda ER-format för att skapa ett utgående dokument på olika språk för motsvarande kunder, leverantörer, dotterbolag eller andra parter.

Du kan konfigurera ER-datamodeller och modellmappningar som datakällor för konfigurerade ER-format för att definiera det dataflöde som anger vilka appdata som placeras i genererade dokument. Som en ER-konfiguration [provider](general-electronic-reporting.md#Provider), du kan [publicera](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) konfigurerade datamodeller, modellmappning och format som komponenter i en ER-lösning för att generera specifika utgående dokument. Du kan också tillåta kunder att [överföra](general-electronic-reporting-manage-configuration-lifecycle.md) den publicerade ER-lösningen så att den kan användas och anpassas. Om du tror att kunderna kan tala om andra språk kan du konfigurera ER-komponenterna så att de innehåller språkberoende resurser. På så sätt kan innehållet i en redigerbar återställningskomponent visas på kundens användarspråk vid designtillfället.

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

![Tillhandahålla översättning av en ER-etikett i ER-datamodelldesignern.](./media/er-multilingual-labels-refer.png)

Endast etikettext för etiketter som finns i en redigerbar återställningskomponent kan översättas. Om du t.ex. väljer **Översätt** för attributet etikett i en datakälla för ER-modellmappning och sedan väljer en ER-etikett som finns i den överordnade ER-datamodellen, visas innehållet i etiketten, men du kan inte ändra det. I dessa fall är fältet **översatt text** inte tillgängligt, som visas i bilden nedan.

![Granska medföljande översättning av en ER-etikett i ER-modellmappningsdesignern.](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Du kan inte använda designer för att ta bort en etikett som har angetts i en redigerbar ER-komponent.

## <a name="scope"></a>Område

ER-etiketter kan refereras till i flera översättningsbara attribut i ER-komponenter.

### <a name="data-model-component"></a>Datamodellkomponent

När du konfigurerar en ER-datamodell kan du lägga till ER-etiketter för den. Attributen **Etikett** och **Beskrivning** för modellartikeln, varje modells fält och varje <a id="LinkModelEnum"></a>modelluppräkningsvärde kan länkas till en ER-etikett som läggs till i ER-datamodellen.

![Tillhandahålla översättning för attributet Beskrivning i ER-datamodelldesignern.](./media/er-multilingual-labels-refer.png)

När en ER-datamodell konfigureras på det här sättet visas dess innehåll för användarna av ER-datamodelldesigner på varje användares prioriterade språk. Modellunderhåll är därför förenklat. Följande bilder visar hur den här funktionen fungerar för användare med inställd DE-AT och JA som önskat språk.

![Layout för ER-datamodelldesignern för en användare som har angett DE-AT som prioriterat språk.](./media/er-multilingual-labels-refer-de.png)

![Layout för ER-datamodelldesignern för en användare som har JA angivet som prioriterat språk.](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Komponent för modellmappning

Eftersom ER-modellmappning baseras på en ER-datamodell, visas etiketterna för de datamodellelement som refereras till på användarens önskade språk i modellmappningsverktyget. Följande bild visar hur betydelsen av fältet **PurchaseOrder** beskrivs i den redigerbara modellmappningen genom att använda etiketten för attributet **Beskrivning** som har lagts till i den konfigurerade datamodellen. Observera att etiketten visas på användarens önskade språk (DE-AT i det här exemplet).

![Layout för ER-mappningsdesignern för en användare som har DE-AT angivet som prioriterat språk.](./media/er-multilingual-labels-show-mapping.png)

När attributet **Etikett** i datakällan **Användarindataparametrar** har konfigurerats som länkad till en ER-etikett, visas det parameterfält som motsvarar denna data källa i dialogrutan för användare under körning till användarna på det språk de föredrar.

### <a name="format-component"></a>Formatkomponent

När du konfigurerar en ER-format kan du lägga till ER-etiketter för den. Attribut **Etikett** och **Hjälptext** för varje konfigurerad datakälla kan länkas till en ER-etikett som har lagts till i ER-format. Attributen **etikett** och **beskrivning** i varje <a id="LinkFormatEnum"></a>format uppräkningsvärde kan också länkas till en ER-etikett som kan användas från det redigerbara återställningsformatet.

> [!NOTE]
> Du kan också länka dessa attribut till en ER-etikett för den överordnade ER-datamodellen som återanvänder modellens etiketter i varje återställnings format som har konfigurerats för den här ER-datamodellen.

När en ER-format konfigureras på det här sättet visas dess innehåll för format av ER-åtgärdsdesigner på varje användares prioriterade språk. Därför förenklas formatunderhåll och analys av den konfigurerade logiken.

Eftersom ER-format baseras på en ER-datamodell, visas etiketterna som hänvisas till i datamodellelement presenterade i ER-formatdesigner på användarens önskade språk i.

När attributet **Etikett** i datakällan **Användarindataparametrar** länkas till en ER-etikett, visas det parameterfält som motsvarar parametern i dialogrutan för användare som presenteras under körning till användarna som en uppmaning. I följande illustrationer visas hur du kan länka attributet **Etikett** för datakällan **Användarindataparametrar** vid designtillfället till en ER-etikett, så att användarna uppmanas att ange parametern i olika språk (visas för engelska USA (en-US) och DE-AT de språk som används) under körning.

![Tillhandahålla översättning av attribut för en användarindataparameter i ER-funktionsdesignern.](./media/er-multilingual-labels-refer-format.png)

![Betalningsbearbetning för ER-leverantör vid körning för användarens prioriterade språk EN-US.](./media/er-multilingual-labels-show-runtime-en.png)

![Betalningsbearbetning för ER-leverantör vid körning för användarens prioriterade språk DE-AT.](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Uttryck

Om du vill använda en etikett i ett ER [uttryck](er-formula-language.md) måste du använda syntaxen **@"GER\_LABEL:X"**, där prefixet **@** indikerar att operanden refererar till en etikett **GER\_LABEL** anger att en ER-etikett är involverad och **X** är ER-etikett-ID.

![Konfigurera ett ER-uttryck som innehåller en referens till en ER-etikett i ER-formeldesignern.](./media/er-multilingual-labels-expression1.png)

Om du vill referera till en systemetikett (program) använder du syntaxen **@"X"**, där prefixen **@** indikerar att operanden refererar till en etikett och **X** är systemets etikett-ID.

![Konfigurera ett ER-uttryck som innehåller en referens till en programetikett i ER-formeldesignern.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Modellmappning

Du kan konfigurera ett uttryck för en ER-modell genom att använda en etikett. När den här mappningen anropas av ett ER-format som körs för att generera ett utgående dokument, innehåller kontexten för körningen en språkkod. En konfigurerad uttrycksetikett fylls i med den etikettext som har konfigurerats för det aktuella språket i kontexten.

Om en refererad etikett inte har någon översättning för språket i den formatkontext som anropar modellmappningen används etikettexten i EN-US-språk i stället.

#### <a name="format"></a>Format

Du kan konfigurera ett ER-uttryck för en ER-format genom att använda etiketter. När detta format körs för att generera ett utgående dokument, innehåller kontexten för körningen en språkkod. En konfigurerad uttrycksetikett fylls i med den etikettext som har konfigurerats för det aktuella språket i kontexten.

![Tillhandahålla översättning av en ER-etikett för det redigerbara ER-uttrycket i ER-formeldesignern.](./media/er-multilingual-labels-refer-in-expression.png)

![Exempel på databindning som refererar till en ER-etikett i ER-funktionsdesignern.](./media/er-multilingual-labels-refer-in-binding.png)

Du kan konfigurera **FIL**-komponenten i ett ER-format om du vill generera rapporten på användarens önskade språk.

![Konfigurera komponenten FIL i ER-funktionsdesignern i syfte att generera rapporten på användarens önskade språk.](./media/er-multilingual-labels-language-context-user.png)

Om du konfigurerar ett ER-format på det här sättet genereras rapporten med hjälp av motsvarande text i ER-etiketterna. I följande illustrationer visas exempel på rapporter för användarspråken EN-US och DE-AT.

![Förhandsgranskning av rapporten som har genererats i EN-US-användares prioriterade språk.](./media/er-multilingual-labels-report-preview-en.png)

![Förhandsgranskning av rapporten som har genererats i DE-AT-användarens prioriterade språk.](./media/er-multilingual-labels-report-preview-de.png)

Om en refererad etikett inte har någon översättning för språket i den formatkontext används etikettexten i EN-US-språk i stället.

## <a name="language"></a>Språk

ER har olika sätt att ange ett språk för en genererad rapport. I fältet **Språkinställningar** på fältet **Format** kan du välja följande värden:

- **Företagspreferens** – Generera en rapport på ett av företaget angivna språk.

    ![I ER-funktionsdesignern anger du ett företagsprioriterat språk som språket för en genererad rapport.](./media/er-multilingual-labels-language-context-company.png)

- **Användarinställningar** – Generera en rapport på användarens önskade språk.
- **Explicit definierad** – Generera en rapport på ett språk som anges i designläge.

    ![I ER-funktionsdesignern anger du ett språk angivet i samband med design som språket i en genererad rapport.](./media/er-multilingual-labels-language-context-fixed.png)

- **Definierade under körning** – Generera en rapport på ett språk som anges i körning. Om du väljer det här värdet ska du i fältet **Språk** konfigurera ett ER-uttryck som returnerar språk koden för språket, som det språk som tillhör motsvarande kund.

    ![I ER-funktionsdesignern anger du ett körningsdefinierat språk som språket i en genererad rapport.](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>Språkspecifik formatering

ER har olika sätt att specificera språket för en genererad rapport. Därför kan korrekt språkspecifik formatering användas för datum, tid och numeriska värden. När du utformar ett ER-format kan du, på fliken **Format**, i fältet **Språkinställningar**, välja ett av följande värden för respektive formatkomponent av typen **Common\\Fil**, **Excel\\Fil**, **PDF\\Fil** eller **PDF\\Sammanslagning**:

- **Användarinställningar** – Formatera värdena efter användarens prioriterade språk. Det språket definieras i fältet **Datum, tid och nummerformat** på fliken **Inställningar** på sidan **Användaralternativ**.

    ![Definiera användarens prioriterade språk som språket för en genererad rapport i ER-funktionsdesignern.](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **Explicit definierade** – Formatera värdena enligt det språk som anges vid designtidpunkten.

    ![Definiera det språk som angetts i samband med utformningen som språket för en genererad rapport i ER-funktionsdesignern.](./media/er-multilingual-labels-culture-context-fixed.png)

- **Definieras vid körning** – Formatera värdena enligt det språk som anges vid körningstidpunkten. Om du väljer detta värde ska du på fliken **Mappning**, i fältet **Format för datum, tid och nummer** konfigurera ett ER-uttryck som returnerar språkkoden för språket, exempelvis tillhörande kunds språk.

    ![Definiera det språk som definierats i samband med körning som språket för en genererad rapport i ER-funktionsdesignern.](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> En ER-komponent som du definierar en specifik konstnad för kan innehålla underordnade ER-komponenter som konfigurerats för att fylla i ett textvärde. Som standard används den överordnade komponenten när värdena för dessa komponenter formateras. Du kan använda följande inbyggda ER-funktioner när du konfigurerar bindande element för dessa komponenter och tillämpar ett alternativt språk för värdeformatering:
>
> - [DATEFORMAT](er-functions-datetime-dateformat.md#syntax-2)
> - [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md#syntax-2)
> - [NUMBERFORMAT](er-functions-text-numberformat.md#syntax-2)
>
> I version 10.0.20 och senare används språken för formatkomponenter av typen **Common\\Fil** och **Excel\\Fil** för att formatera värden i samband med [PDF-konvertering](electronic-reporting-destinations.md#OutputConversionToPDF) av ett genererat dokument.

## <a name="translation"></a>Översättning

Du kan lägga till obligatoriska ER-etiketter i en redigerbar ER-komponent. När en ER-etikett läggs till kan den översättas på två sätt: manuellt och automatiskt.

### <a name="manual-translation"></a>Manuell översättning

När du lägger till en ER-etikett **Textöversättning** [fönstret](#TextTranslationPane), kan du manuellt översätta den till alla språk som stöds i den aktuella Finance-instansen. Du kan välja önskat språk i fältet **Språk** i avsnittet **Systemspråk** eller **Användarspråk** anger du lämplig text i motsvarande fält för **Översatt text** och väljer sedan **Översätt**. Processen måste upprepas för alla språk som krävs och alla etiketter som du lägger till.

### <a name="automatic-translation"></a>Automatisk översättning

Konfigurationen av en ER-komponent görs i utkastversionen av ER-konfigurationen som den redigerbara återställningskomponenten finns i.

![Sidan ER-konfigurationer ger åtkomst till konfigurationens version i utkaststatus.](./media/er-multilingual-labels-configurations.png)

Som tidigare nämnts i det här avsnittet kan du lägga till nödvändiga ER-etiketter till en redigerbar ER-komponent. På det här sättet kan du ange texten i ER-etiketterna på språket EN-US. Du kan sedan exportera etiketterna för ER-komponenten med hjälp av den inbyggda ER-funktionen. Markera utkastversionen av en ER-konfiguration som innehåller den redigerbara ER-komponenten och välj sedan **Byt \> Exportetiketter**.

![Sidan ER-konfigurationer som tillåter export av ER-etiketter från den valda konfigurationsversionen.](./media/er-multilingual-labels-export.png)

Du kan exportera antingen alla etiketter eller etiketterna för ett enskilt språk som du anger i början av exporten. Etiketter exporteras som zip-filer som innehåller XML-filer. Alla XML-filer innehåller etiketter för ett enskilt språk.

![Exempel på den exporterade filen som innehåller ER-etiketter för språket DE-AT.](./media/er-multilingual-labels-in-xml.png)

Det här formatet används för automatisk översättning av etiketter med externa översättningstjänst som [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). När du får de översatta etiketterna kan du importera dem tillbaka till utkastversionen av en ER-konfiguration som innehåller de ER-komponenter som äger dessa etiketter. Markera utkastversionen av en ER-konfiguration som innehåller den redigerbara ER-komponenten och välj sedan **Byt \> Lastetiketter**.

![Sidan ER-konfigurationer som tillåter import av ER-etiketter till den valda konfigurationsversionen.](./media/er-multilingual-labels-load.png)

Översatta etiketter importeras till den valda ER-konfigurationen. Översatta etiketter som finns i denna ER-konfiguration ersätts. Om en översatt etikett saknas i ER-konfigurationen, läggs den till.

## <a name="lifecycle"></a>Livscykel

Etiketter för en ER-komponent som kan redigeras behålls, tillsammans med annat innehåll för komponenten, i en lämplig version av en ER-konfiguration.

Etiketter för en grundläggande ER-komponent kan refereras till en härledd version av ER-komponenten som du skapar för att införa dina ändringar.

> [!TIP]
> När du designar en ER-lösning kan du härleda din egen ER [datamodell](er-overview-components.md#data-model-component) komponent från den som tillhandahålls. I denna härledda datamodell kan du införa egna ER-etiketter och använda dem i alla ER-format som kommer att använda datamodellen som datakälla. Du kan sedan härleda din egen ER [format](er-overview-components.md#format-component) komponent från den som tillhandahålls genom att välja den härledda ER-datamodellen istället för den som tillhandahålls. I version 10.0.28 och senare kan du aktivera funktionen **Utökad åtkomst till etiketter för den stigande ER-datamodellen** för att komma åt etiketter för en stigande ER-datamodell i härledda ER-formatkomponenter, även när ER-datamodellen som du valde för den härledda ER-komponenten skiljer sig från den som användes i ER-baskomponenten.
>
> När samma etikettnamn används i den härledda komponenten och dess stigande komponenter, används översättningen av den etiketten som den mest relevanta.

ER-versioner kontrollerar etiketttilldelningen till alla attribut i en ER-komponent. Ändringar i etikettilldelningen registreras i listan över ändringar (delta) i en redigerbar ER-komponent som har skapats som en härledd version av den angivna ER-komponenten. Ändringarna kommer att valideras när en härledd version baseras på en ny grundläggande version.

## <a name="functions"></a>Funktioner

Den inbyggda ER-funktionen [LISTOFFIELDS](er-functions-list-listoffields.md) kan komma åt ER-etiketter som har konfigurerats för vissa artiklar i ER-komponenter.

Som tidigare nämnts i det här avsnittet **Etikett** och **Beskrivning** för varje [modell](#LinkModelEnum) eller [format](#LinkFormatEnum) ER-uppräkningens värde kan kopplas till en ER-etikett som är tillgänglig i rätt ER-komponent. Du kan konfigurera ett ER-uttryck där du anropar funktionen **LISTOFFIELDS** genom att använda ER-uppräkning som argument. Det här uttrycket returnerar en lista som innehåller en post för varje värde av en ER-uppräkning som har definierats som argument för den här funktionen. Varje post innehåller värdet för en ER-etikett som är länkad till ett ER-uppräkningsvärde:

- Värdet för en ER-etikett som är länkad till attributet **etikett** lagras i fältet **etikett** för den returnerade posten.
- Värdet för en ER-etikett som är länkad till attributet **Beskrivning** lagras i fältet **Beskrivning** för den returnerade posten.

## <a name="performance"></a><a name=performance></a>Resultat

När du konfigurerar en ER-formatkomponent för att generera en rapport på det [språk](#language) du föredrar, eller för att importera ett inkommande dokument där innehållet analyseras efter önskat språk, rekommenderar vi att du aktiverar funktionen **Cachelagra önskat språk för aktuell användare för ER-körningar** i arbetsytan [Funktionshantering](../../fin-ops/get-started/feature-management/feature-management-overview.md). Den här funktionen förbättrar prestandan, särskilt för ER-formatkomponenter som innehåller flera referenser till etiketter i ER-formler och -bindningar och många [validerings](general-electronic-reporting-formula-designer.md#TestFormula)regler för att generera användarmeddelanden på önskat språk.

När du ändrar statusen för en ER-konfigurationsversion från **Utkast** till **Slutförd** lagras dessa etiketter i programdatabasen om konfigurationsversionen innehåller ER-etiketter. Lagringsschemat beror på statusen för funktionen **Accelerera lagring av ER-etiketter**:

- Om funktionen inte är aktiverad lagras alla etiketter i fältet **LABELXML** i tabellen **ERSOLUTIONVERSIONTABLE** som ett enda XML-villkor.
- Om funktionen aktiveras skapas en separat post för varje språk i tabellen **ERSOLUTIONVERSIONLABELSTABLE**. I fältet **INNEHÅLL** i den här tabellen lagras etiketter per språk som ett komprimerat XML-element.

Vi rekommenderar att du aktiverar funktionen **Accelerera lagring av ER-etiketter** i arbetsytan för **funktionshantering** . Den här funktionen underlättar användningen av nätverksbredden och den generella systemprestandan, eftersom ER-etiketter för ett enskilt språk i de flesta fall används när du arbetar med en enda ER-konfiguration.

För att tillämpa det valda lagringsschemat för att behålla etiketter för alla ER-konfigurationer i den aktuella Ekonomi-instansen, utför följande steg.

1. Gå till **Organisationsadministration** > **Periodisk** > **Tillämpa de valda etiketternas lagringsschema för alla ER-konfigurationer**.
2. Välj **OK**.


## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Funktioner för elektronisk rapportering](er-formula-language.md#Functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
