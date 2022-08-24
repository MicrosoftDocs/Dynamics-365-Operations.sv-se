---
title: Konfigurera sökdatakällor att använda programspecifika parametrar för ER
description: I denna artikel beskrivs hur du kan konfigurera sökdatakällor i elektronisk rapportering (ER) att använda parametrar specifika för ER-program.
author: kfend
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: f3ce5837b1d20860588848a1b518b3d801a05db4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285134"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Konfigurera sökdatakällor att använda programspecifika parametrar för ER 

[!include[banner](../includes/banner.md)]

Med hjälp av programspecifika parametrar för [elektronisk rapportering (ER)](general-electronic-reporting.md) kan du konfigurera datafiltreringen i ett ER-format så att denna baseras på en uppsättning abstrakta regler. Denna uppsättning regler kan konfigureras till att använda datakällan av typen **Sökning** som finns i ett ER-format. Du kan sedan ange verkliga regler utanför ER-komponentverktygen med hjälp av det användargränssnitt (UI) som genereras automatiskt baserat på de inställningar för datakällan för **Sökning** för tillhörande ER-format och aktuella data för juridisk person. Så småningom får du åtkomst till de angivna reglerna via ER-formatets **Sökning**-datakälla när detta ER-format körs.

> [!NOTE]
> Använd de konfigurerade datakällorna i det redigerbara ER-formatet för att ange vilka programdata som används för att konfigurera verkliga regler.

Använd [ER Operations-designern](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) för att införa en datakälla av typen **Sökning** i ditt ER-format. Datakällan måste konfigureras för att den ska kunna beskriva hur dina abstrakta regler ser ut, bland annat följande:

   - Parameteruppsättningen för vissa datatyper vars värde anges för att ange en enda regel.
   - Värdetypen för vissa datatyper som returneras av en enda regel när den här regeln anses vara den lämpligaste bland andra.

Du kan konfigurera följande typer av **Sökning**-datakällor beroende på vilken typ av värde som returneras av någon konfigurerad regel:

   - Använd typen **Datamodell\Sökningstyp** när ett uppräkningsvärde för en modell måste returneras.
   - Använd typen **Dynamics 365 Operations\sökning** när ett uppräkningsvärde för ett program eller ett programvärde [utökad datatyp](../extensibility/extensible-edts.md) måste returneras.
   - Använd typen **Formatuppräkning\Sökning** när ett uppräkningsvärde för format måste returneras.

I följande bild visas hur en uppräkning av format kan konfigureras i provformatet för ER.

   ![Visar en formatuppräkning som bas för den konfigurerade sökdatakällan.](./media/er-lookup-data-sources-img1.gif)

I följande bild visas de formatkomponenter som konfigurerats för att rapportera olika typer av skatter i ett annat avsnitt i en genererad rapport.

   ![Visar formatavsnitt för att rapportera olika typer av skatter separat.](./media/er-lookup-data-sources-img2.png)

I följande bild visas hur ER Operations-designern tillåter att en datakälla av typen **Formatuppräkning\Sökning** läggs till.  Den tillagda datakällan konfigureras som att ett värde för `List of taxation levels`-formaträkning returneras.

   ![Lägga till en ER-datakälla för Formatuppräkning\Sökningstyp.](./media/er-lookup-data-sources-img3.gif)

I följande bild visas hur den tillagda datakällan är konfigurerad att använda fältet **Kod** i postlistan **Model.Data.tax** tillhörande datakällan **Modell** som en parameter som måste anges för varje enskild konfigurerad regel.

![Konfigurera parametrar för den tillagde datakällan för Formatuppräkning\Sökningstyp.](./media/er-lookup-data-sources-img4.gif)

Den tillagda `Model.Data.Tax`-datakällan konfigureras i syfte att ange en skattekod för varje konfigurerad regel, detta genom att få åtkomst till programtabellen **TaxTable**.

   ![Granska sökdatakällan för enskilt företag tillhörande typen Formatuppräkning\Sökningstyp.](./media/er-lookup-data-sources-img5.gif)

Du kan ställa in sökningsregler för det valda ER-formatet genom att använda det användargränssnitt som automatiskt anpassas efter strukturen för den konfigurerade datakällan. Detta användargränssnitt kräver för närvarande att du för varje regel anger det returnerade värdet som uppräkningsvärdet `List of taxation levels` för format, samt även skattekoden som en parameter.

   ![Konfigurera regler för den konfigurerade datakällan.](./media/er-lookup-data-sources-img6.gif)

I följande bild visas hur datakällan `Model.Data.Summary.LevelByLookup` för typen **Beräknat fält** kan konfigureras att anropa den konfigurerade datakällan **Sökning** som tillhandahåller erforderliga parametrar. För att bearbeta detta anrop vid körning går ER igenom listan med konfigurerade regler i den definierade sekvensen i syfte att hitta den första regel som uppfyller de angivna villkoren. I detta exempel är det regeln som innehåller skattekoden som matchar den angivna. Det innebär att den lämpligaste regeln hittas och att uppräkningsvärdet som konfigureras för den hittade regeln returneras av denna datakälla.

> [!NOTE]
> Ett undantag utlöses när ingen tillämplig regel hittas. Om du vill förhindra dessa undantag kan du konfigurera ytterligare regler i slutet av regellistan som hanterar fall där ett icke-konfigurerat värde eller inget värde anges. Använd alternativen **\*Ej tom**\* och **\*Tom**\* i enlighet därmed.  
>
> ![Lägg till en datakälla för att anropa den konfigurerade sökdatakällan.](./media/er-lookup-data-sources-img7.png)

När du anger alternativet **Mellan företag** som **Ja** för den redigerbara sökdatakällan lägger du till en ny, erforderlig **Företag**-parameter i parameteruppsättningen i denna datakälla. Värdet för parametern **Företag** måste anges vid körning när sökdatakällan anropas. När företagskoden anges vid körning används de regler som konfigurerats för detta företag för att hitta den lämpligaste regeln, och motsvarande värde returneras. I följande bild visas hur du kan göra detta och hur uppsättningen av parametrar för den redigerbara datakällan ändras.

   ![Granska sökningsdatakällan mellan företag tillhörande typen Formatuppräkning\Sökningstyp.](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Välj alla företag separat för att konfigurera regeluppsättningen för denna sökdatakälla för det redigerbara ER-formatet. Ett undantag avslutas vid körning när sökning mellan företag anropas med koden för det företag för vilket sökinställningen inte kunde slutföras.
>
> Se till att du beviljar behörigheter för en användare som kör ER-formatet med datakällan **Sökning** mellan företag, så att denne får åtkomst till data för samtliga företag som finns i denna datakällas definitionsområde. I annat fall körs ett undantag i samband med körning.

Med start i version 10.0.19 finns de utökade funktionerna för datakällor för **Sökning** tillgängliga. När du anger alternativet **Utökat** som **Ja** för den redigerbara sökdatakällan omvandlas den konfigureras sökdatakällan till den strukturerade datakälla som ger ytterligare möjligheter att analysera den konfigurerade regeluppsättningen. Illustrationen nedan visar denna omvandling.

   ![Granskning av strukturerad sökdatakälla för typen Formatuppräkning\Sökning.](./media/er-lookup-data-sources-img9.gif)

- Underartikeln **Sökning** har utformats som en funktion för att hitta den lämpligaste regeln från uppsättningen konfigurerbara regler baserat på den tillhandahållna uppsättningen parametrar.
- Underartikeln **IsLookupResultSet** har utformats som en funktion för att acceptera det angivna värdet i datakällan för basräkning och returnera det *booleska* värdet **True** när uppsättningen regler innehåller minst en regel för vilken det angivna uppräkningsvärdet har konfigurerats som ett returnerat värde. Denna funktion returnerar det *booleska* värdet **False** när det inte finns några konfigurerade regler för att returnera det angivna uppräkningsvärdet.
- Underartikeln **Inställning** har utformats som en funktion som returnerar uppsättningen konfigurerade regler som poster i en postlista. Returnerade värden och uppsättningen parametrar för de konfigurerade reglerna visas i alla returnerade poster som fält för relevanta datatyper:

    - Det returnerade värdet visas som fältet **Sökningsresultat**.
    - De konfigurerade parametrarna presenteras som fält med namn på parametrar (fältet **Kod** i detta exempel).

Mer information om hur du konfigurerar datakällan för **Sökning** finns i [Konfigurera ER-format att använda parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md). Mer information om hur du ställer in sökningsreglerna finns i [Ställa in parametrar för ett ER-format per juridisk person](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ER-format för användning av parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md)

[Ställa in parametrarna för ett ER-format per juridisk person](er-app-specific-parameters-set-up.md)
