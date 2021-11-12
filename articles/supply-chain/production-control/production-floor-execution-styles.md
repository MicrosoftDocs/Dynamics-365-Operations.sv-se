---
title: Välj stil på körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du konfigurerar formulärkontroller så att standardformaten för tillverkningsstyrning används på dem.
author: johanhoffmann
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 32e49458f6ea7c484bc4200e414d930381b31891
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652087"
---
# <a name="style-the-production-floor-execution-interface"></a>Välj stil på körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar formulärkontroller så att standardformaten för tillverkningsstyrning används på dem.

## <a name="forms-and-dialogs"></a>Formulär och dialogrutor

Format kan endast användas i ett formulär eller en dialogruta om följande krav uppfylls:

- Om formuläret ska se ut som det befintliga rapportförloppsformuläret måste namnet på formuläret eller dialogrutan börja med **JmgProductionFloorExecutionCustomInputDialog**. 
- Formuläret eller dialogrutan kan innehålla en detaljformulärdel. Om du vill tillämpa utföranden på den, måste namnet på detaljformulärdelen starta med **JmgProductionFloorExecutionCustomDetailsDialog**.
- Om formuläret eller dialogrutan ska ha en enkel vy, måste namnet på den enkla vyn börja med **JmgProductionFloorExecutionCustomDialog**. Exempel på formulär som har en enkel vy inkluderar startformuläret och det indirekta aktivitetsformuläret.
- Alla kontroller i dialogrutan måste konfigureras enligt beskrivningen i det här avsnittet.

> [!IMPORTANT]
> Funktionerna som nämns i de första två poängerna i den här listan kräver version 10.0.19 av Supply Chain Management eller senare.

Format kan endast användas med knappen **OK** eller en dialogruta om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med **OkButtonGroup**.

Format kan endast användas med knappen **Avbryt** eller en dialogruta om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med **CancelButtonGroup**.

## <a name="grid"></a>Rutnät

Format används automatiskt. Ingen specifik konfiguration krävs.

## <a name="card-view"></a>Kortvy

Format kan endast användas i kortvy kontroller om följande krav uppfylls:

- Varje kortvy finns i en formulärgrupp.
- Gruppnamnet börjar med **CardGroup** (till exempel **CardGroupJobsView**).

I följande bild visas en kortvy utan kontroller.

![Kortvy utan element.](media/pfe-styles-empty-card.png)

I följande bild visas en kortvy som har kontroller inne i den.

![Kort med element som visar Hz.](media/pfe-styles-elements.png)

![Kort med element för en underhållsbegäran.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Visitkort

Format kan endast användas på visitkort kontroller om följande krav uppfylls:

- Varje visitkort finns i en formulärgrupp.
- Gruppnamnet börjar med **BusinessCardGroup** (till exempel **BusinessCardGroupJobsList**).

Ställ in följande egenskaper på visitkortet:

- **Format**: **lista**
- **Utökat format**: **kortlista**
- **Flerval**: **Nej**
- **Visa kol etiketter**: **Nej**

![Visitkort.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Alternativknapp

Format kan endast användas i alternativknappar om följande krav uppfylls:

- Varje alternativknapp finns i en formulärgrupp.
- Gruppnamnet börjar med **RadioTextBelow** eller **RadioTextRight**, beroende på var du vill att texten ska visas.

Ställ in följande egenskaper på alternativknappen:

- **Växla knapp**: **Kontrollera**
- **Växla värde**: **På** om radioknappen ska väljas. Annars **Av**

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

- **Knappvisning**: **TextWithImageLeft**.
- **Normal bild**: Egenskapen får inte vara tom. Använd till exempel **CoffeeScript**.
- **Text**: Egenskapen får inte vara tom. Använd till exempel **Börja paus**.
- **Bredd**: **Automatiskt**.
- **Höjd**: **Auto**.

### <a name="primary-button"></a>Primär knapp

Format kan endast användas i en primär knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med **DefaultButtonGroup** eller **PrimaryButtonGroup** (t.ex. **DefaultButtonGroup10**).

![Primär knapp.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Sekundär knapp

Format kan endast användas i en sekundär knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppen får namnet **Höger panel** eller så börjar gruppnamnet med **SecondaryButtonGroup**. 

![Sekundär knapp.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Knappen Tredje grupp

Format kan endast användas i en tredje grupp-knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppen får namnet **Vänster panel** eller så börjar gruppnamnet med **ThirdButtonGroup**. 

![Knappen Tredje grupp.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Knappen Fjärde grupp

Format kan endast användas i en fjärde grupp-knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med **FourthButtonGroup**.

Ställ in följande egenskaper på knappen:

- **Knappvisning**: **TextOnly**.
- **Normal bild**: Egenskapen måste vara tom.
- **Text**: Egenskapen får inte vara tom. Använd till exempel **Visa** eller **Redigera**.
- **Bredd**: **Automatiskt**.
- **Höjd**: **Auto**.

![Knappen Fjärde grupp.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Platt knapp

Format kan endast användas i en platt knapp om följande krav uppfylls:

- Knappen finns i en formulärgrupp.
- Gruppnamnet börjar med **FlatButtonGroup**.

Ställ in följande egenskaper på knappen:

- **Knappvisning**: **ImageOnly**.
- **Normal bild**: Egenskapen får inte vara tom. Använd till exempel **CoffeeScript**.
- **Text**: Egenskapen måste vara tom.
- **Bredd**: **Automatiskt**.
- **Höjd**: **Auto**.

![Platt knapp.](media/pfe-styles-flat-button.png)

## <a name="combo-box"></a>Kombinationsruta

En kombinationsruta är en kombination av tre kontroller: en inmatningskontroll, en knapp som rensar indatakontrollen och en knapp som kör en sökning.

Format kan endast användas i kombinationsruta om följande krav uppfylls:

- Kombinationsrutan finns i en formulärgrupp.
- Gruppnamnet börjar med **Combobox**.
- Inuti gruppen är den första kontrollen en kontroll för **AxFormStringControl**. Den här kontrollen visar det aktuella värdet, och det är där användaren anger det nödvändiga värdet.
- Den andra kontrollen är en **CommonButton**-kontroll, och dess namn börjar med **ClearButton**. Den här knappen måste innehålla kod som använder egenskapen **aktivera** för att visa eller dölja knappen. Om du till exempel vill visa eller dölja knappen **Rensa** när användaren skriver information i inmatningskontrollen kan du använda följande kod.

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

    Använd följande kod för den **klickade** metoden på knappen **Rensa**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Ställ in värdet på indatakontrollen, **AxFormStringControl**, när formuläret initieras med hjälp av **init**-metoden.  Om värdet inte är tomt måste du aktivera knappen **Rensa**. Om värdet är tomt måste du inaktivera knappen **Rensa**.

- Den tredje kontrollen är en **CommonButton**-kontroll, och dess namn börjar med **SearchButton**.

I följande illustration visas två kombinationsrutakontroller. Kombinationsrutan till vänster har en tom textruta, och knappen **Rensa** är inaktiverad. Kombinationsrutan till höger har text i textrutan, och knappen **Rensa** är aktiverad.

![Kombinationsrutor med och utan knappen Rensa.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Snabbfilter

Snabbfilterkontrollen lägger till ett sökfält på sidan. Du kan tillämpa utföranden på ett snabbfilter under förutsättning att följande krav uppfylls:

- Snabbfiltret finns i en formulärgrupp.
- Gruppnamnet börjar med **SearchInputGroup**.
- Inuti gruppen är den första kontrollen en kontroll för **QuickFilter**. (Det är här användaren anger söksträngen.)
- Den andra kontrollen är **FormStaticTextControl** med namnet **NumberOfResults**. (Detta är valfritt och visar antalet hittade artiklar om de ingår.)
- Den tredje kontrollen är en **CommonButton**-kontroll med ett namn som börjar med **ClearButton**.

I följande illustration visas två snabbfilterkontroller. Snabbfiltret till vänster har ett tomt snabbfilter och antalet resultat visas inte. Snabbfiltret till höger innehåller en söksträng och visar antalet resultat.

![Exempel på en snabbfilterkontroll med och utan söksträng.](media/pfe-styles-quick-filter.png "Exempel på en snabbfilterkontroll med och utan söksträng")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
