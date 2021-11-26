---
title: Välj stil på körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du konfigurerar formulärkontroller så att standardformaten för tillverkningsstyrning används på dem.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ef39dc6414f0afdadd4a4b5a41e1fb1fe60e4974
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790900"
---
# <a name="style-the-production-floor-execution-interface"></a>Välj stil på körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar formulärkontroller så att standardformaten för tillverkningsstyrning används på dem.

## <a name="forms-and-dialogs"></a>Formulär och dialogrutor

Format kan endast användas i ett formulär eller en dialogruta om följande krav uppfylls:

- Om formuläret ska se ut som det befintliga rapportförloppsformuläret måste namnet på formuläret eller dialogrutan börja med `JmgProductionFloorExecutionCustomInputDialog`.
- Formuläret eller dialogrutan kan innehålla en detaljformulärdel. Om du vill tillämpa utföranden på det måste namnet på detaljformulärdelen börja med `JmgProductionFloorExecutionCustomDetailsDialog`.
- Om formuläret eller dialogrutan ska ha en enkel vy måste namnet på den enkla vyn börja med `JmgProductionFloorExecutionCustomDialog`. Exempel på formulär som har en enkel vy inkluderar startformuläret och det indirekta aktivitetsformuläret.
- Alla kontroller i dialogrutan måste konfigureras enligt beskrivningen i det här ämnet.

> [!IMPORTANT]
> Funktionerna som nämns i de första två poängerna i den här listan kräver version 10.0.19 av Supply Chain Management eller senare.

Format kan endast användas med knappen **OK** eller en dialogruta om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `OkButtonGroup`.

Format kan endast användas med knappen **Avbryt** eller en dialogruta om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `CancelButtonGroup`.

### <a name="header"></a>Siduvud

I följande bild visas ett vanligt formulär eller en dialogsidhuvud.

![Typiskt formulär eller dialogsidhuvud.](media/pfe-styles-header.png "Typiskt formulär eller dialogrubrik")

I Visual Studio skapas sidhuvuden med en struktur som den som visas i följande illustration.

![En typisk kodstruktur för att skapa ett sidhuvud.](media/pfe-styles-header-code-structure.png "En typisk kodstruktur för att skapa ett sidhuvud")

Om du vill lägga till text i sidhuvudet använder du kod som i följande exempel.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

När du skriver sidhuvudkoden använder du följande regler:

- Namnet på huvudgruppen måste vara `TableRowHeaderGroup`.
- Varje textblock (åtskilda av punkter) måste börja med `HeaderFieldWithSeparatorText`.
- Namnet på den sista texten måste börja med `HeaderFieldText`.
- `CaptionImage` kan hoppas över.

### <a name="progress-indicator"></a>Förloppsindikator

Du kan inkludera en förloppsindikator som visas till höger om sidhuvudet. I följande bild visas en förloppsindikator.

![Typisk förloppsindikator.](media/pfe-styles-header-progress.png "Typisk förloppsindikator")

Om du vill visa förloppsindikatorn måste textfältet kallas `ShowProgress`.

## <a name="grid"></a>Rutnät

Format används automatiskt. Ingen specifik konfiguration krävs.

Rutnätet ska ha en `TabularView`-stil, och `run()`-metoden i det anpassade formuläret måste skrivas över, detta eftersom ett nytt rutnät ännu inte stöds. Lägg till följande kod:

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Om du vill uppdatera data i en huvudvy kanske du vill använda något liknande `this.parmParentForm().updateLayout();` i en `click`-metod för din åtgärd. (Som exempel kan du titta på `JmgProductionFloorExecutionReportFeedbackAction`-klassen.) Se bara till att `parmDataSource` angetts i `init`-metoden för ditt nya formulär (`formCaller.parmDataSource(this.dataSource(1));`). Titta exempelvis på `JmgProductionFloorExecutionMainGrid`-formuläret.

## <a name="card-view"></a>Kortvy

Format kan endast användas i kortvy kontroller om följande krav uppfylls:

- Varje kortvy finns i en formulärgrupp.
- Gruppnamnet börjar med `CardGroup` (till exempel `CardGroupJobsView`).

I följande bild visas en kortvy utan kontroller.

![Kortvy utan element.](media/pfe-styles-empty-card.png)

I följande bild visas en kortvy som har kontroller inne i den.

![Kort med element som visar Hz.](media/pfe-styles-elements.png)

![Kort med element för en underhållsbegäran.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Visitkort

Format kan endast användas på visitkort kontroller om följande krav uppfylls:

- Varje visitkort finns i en formulärgrupp.
- Gruppnamnet börjar med `BusinessCardGroup` (till exempel `BusinessCardGroupJobsList`).

Ställ in följande egenskaper på visitkortet:

- **Format:** *lista*
- **Extended style:** *cardList*
- **Multi Select:** *Nej*
- **Show Col Labels:** *Nej*

![Visitkort.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Alternativknapp

Format kan endast användas i alternativknappar om följande krav uppfylls:

- Varje alternativknapp finns i en formulärgrupp.
- Gruppnamnet börjar med `RadioTextBelow` eller `RadioTextRight` beroende på var du vill att texten ska visas.

Ställ in följande egenskaper på alternativknappen:

- **Växlingsknapp:** *Kontroll*
- **Växla värde:** *På* om radioknappen ska väljas. Annars *Av*

Illustrationen visar ett exempel där texten visas nedanför alternativknapparna.

![Alternativknapparna med text under.](media/pfe-styles-radio-text-below.png)

Illustrationen visar ett exempel där texten visas till texten visas till höger om alternativknapparna.

![Alternativknappar med text till höger.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Alternativknappar i Internet Explorer

Format för alternativknappar stöds i Internet Explorer. Följande bild visar hur den här alternativknappen ser ut i Internet Explorer.

![Alternativknappar i Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Knappar

Format kan endast användas i knappar om följande krav uppfylls:

- Varje grupp med knappar finns i en formulärgrupp. Alla knappar i gruppen kommer att ha samma stil.
- Det finns inga krav för namnet på gruppen.

Ställ in följande egenskaper på knapparna:

- **Button Display:** *TextWithImageLeft*
- **Normal Image:** Denna egenskap får inte vara tom. Använd till exempel *CoffeeScript*.
- **Text:** Denna egenskap får inte vara tom. Använd till exempel *Börja paus*.
- **Width:** *Automatisk* eller *SizeToContent*
- **Height** *Automatisk* eller *SizeToContent*

### <a name="primary-button"></a>Primär knapp

Format kan endast användas i en primär knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `DefaultButtonGroup` eller `PrimaryButtonGroup` (till exempel `DefaultButtonGroup10`).

![Primär knapp.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Sekundär knapp

Format kan endast användas i en sekundär knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppen får namnet **Höger panel**, eller också inleds gruppnamnet med `SecondaryButtonGroup`.

![Sekundär knapp.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Knappen Tredje grupp

Format kan endast användas i en tredje grupp-knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppen får namnet **Vänster panel**, eller också börjar gruppnamnet med `ThirdButtonGroup`.

![Knappen Tredje grupp.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Knappen Fjärde grupp

Format kan endast användas i en fjärde grupp-knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `FourthButtonGroup`.

Ställ in följande egenskaper på knappen:

- **Button Display:** *TextOnly*
- **Normal Image:** Denna egenskap måste vara tom.
- **Text:** Denna egenskap får inte vara tom. Använd till exempel *Visa* eller *Redigera*.
- **Width:** *Automatisk*
- **Height:** *Automatisk*

![Knappen Fjärde grupp.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Platt knapp

Format kan endast användas i en platt knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `FlatButtonGroup`.

Ställ in följande egenskaper på knappen:

- **Button Display:** *ImageOnly*
- **Normal Image:** Denna egenskap får inte vara tom. Använd till exempel *CoffeeScript*.
- **Text:** Denna egenskap måste vara tom.
- **Width:** *Automatisk* eller *SizeToContent*
- **Height** *Automatisk* eller *SizeToContent*

![Platt knapp.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Knappen Fortsätt

Format kan endast användas på en fortsättningsknapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med `ContinueButtonGroup`.

Ställ in följande egenskaper på knappen:

- **Button Display:** *ImageOnly*
- **Normal Image:** *Framåt*
- **Text:** Denna egenskap måste vara tom.
- **Width:** *Automatisk* eller *SizeToContent*
- **Height** *Automatisk* eller *SizeToContent*

![Knappen Fortsätt.](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Kombinationsruta

En kombinationsruta är en kombination av tre kontroller: en inmatningskontroll, en knapp som rensar indatakontrollen och en knapp som kör en sökning.

Format kan endast användas i kombinationsruta om följande krav uppfylls:

- Kombinationsrutan finns i en formulärgrupp.
- Gruppnamnet börjar med `Combobox`.
- Inuti gruppen är den första kontrollen en `AxFormStringControl`-kontroll. Den här kontrollen visar det aktuella värdet, och det är där användaren anger det nödvändiga värdet.
- Den andra kontrollen är en `CommonButton`-kontroll vars namn börjar med `ClearButton`. Den här knappen måste innehålla kod som använder egenskapen `enable` för att visa eller dölja knappen. Om du till exempel vill visa eller dölja knappen **Rensa** när användaren skriver information i inmatningskontrollen kan du använda följande kod.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Du bör ha en metod där data ställs in i inmatningskontrollen. Aktivera knappen **Rensa** i den metoden. Här är ett exempel:

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Använd följande kod för metoden `clicked` på knappen **Rensa**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Ställ in värdet för indatakontrollen, `AxFormStringControl`, när formuläret initieras med hjälp av `init`-metoden. Om värdet inte är tomt måste du aktivera knappen **Rensa**. Om värdet är tomt måste du inaktivera knappen **Rensa**.

- Den tredje kontrollen är en `CommonButton`-kontroll vars namn börjar med `SearchButton`.

I följande illustration visas två kombinationsrutakontroller. Kombinationsrutan till vänster har en tom textruta, och knappen **Rensa** är inaktiverad. Kombinationsrutan till höger har text i textrutan, och knappen **Rensa** är aktiverad.

![Kombinationsrutor med och utan knappen Rensa.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Snabbfilter

Snabbfilterkontrollen lägger till ett sökfält på sidan. Du kan tillämpa utföranden på ett snabbfilter under förutsättning att följande krav uppfylls:

- Snabbfiltret finns i en formulärgrupp.
- Gruppnamnet börjar med `SearchInputGroup`.
- Inuti gruppen är den första kontrollen en `QuickFilter`-kontroll. (Denna kontroll är platsen där användaren anger söksträngen.)
- Den andra kontrollen är en `FormStaticTextControl` som kallas `NumberOfResults`. (Den här kontrollen är valfri. Om den inkluderas visar den antalet funna artiklar.)
- Den tredje kontrollen är en `CommonButton`-kontroll vars namn börjar med `ClearButton`.

I följande illustration visas två snabbfilterkontroller. Snabbfiltret till vänster har ett tomt snabbfilter och antalet resultat visas inte. Snabbfiltret till höger innehåller en söksträng och visar antalet resultat.

![Exempel på en snabbfilterkontroll med och utan söksträng.](media/pfe-styles-quick-filter.png "Exempel på en snabbfilterkontroll med och utan söksträng")

## <a name="center-align-elements-on-a-tab"></a>Centerjustera element på en flik

För att anpassa elementen i mitten av en flik måste gruppnamnet starta med `TabContentGroup`, och gruppen måste ha följande egenskaper:

- **Breddläge:** `SizeToAvailable`
- **Höjdläge:** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Anpassa ett rutnät, en detaljdel och ett snabbfilter

Om du vill ordna ett anpassat rutnät, en detaljdel och ett snabbfilter så att dessa liknar standarddesignen, tänk då på följande när du sammanställer dem:

- Om rutnätet har ett snabbfilter ska både rutnätet och snabbfiltret finnas inuti gruppen som har ett namn som börjar med `GridGroup`.
- Om du vill tillämpa format på en detaljdel måste gruppnamnet börja med `DetailInformationGroup`,

I följande bild visas ett vanligt rutnät med ett snabbfilter och en detaljdel till höger.

![Ett typiskt rutnät som innehåller ett snabbfilter och en detaljdel.](media/pfe-styles-align-grid.png "Ett typiskt rutnät som innehåller ett snabbfilter och en detaljdel")

I Visual Studio kan rutnät, detaljdel samt snabbfilter skapas med hjälp av en struktur liknande den i följande illustration.

![En typisk kodstruktur som arrangerar ett rutnät, en detaljdel och ett snabbfilter.](media/pfe-styles-header-code-structure2.png "En typisk kodstruktur som arrangerar ett rutnät, en detaljdel och ett snabbfilter")

## <a name="additional-resources"></a>Ytterligare resurser

- [Anpassa körningsgränssnittet för produktionsgolvet](production-floor-execution-customize.md)
- [Designa körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
