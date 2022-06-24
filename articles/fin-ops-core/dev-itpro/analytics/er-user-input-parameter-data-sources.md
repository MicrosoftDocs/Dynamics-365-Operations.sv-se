---
title: Använd datakällan USER INPUT PARAMETER när du vill ange parametrar för en rapport
description: I den här artikeln beskrivs hur du använder datakällor för USER INPUT PARAMETER för att ange parametrar för rapporter som du genererar.
author: NickSelin
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.openlocfilehash: 62b7a8173416a1d36a2985823d186a7a0e6a7e60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872984"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Använd datakällan USER INPUT PARAMETER när du vill ange parametrar för en rapport

[!include[banner](../includes/banner.md)]

När du designar [Elektronisk rapportering](general-electronic-reporting.md) (ER) [modellmappning](er-overview-components.md#model-mapping-component) och ER [format](er-overview-components.md#format-component) komponenter, kan du använda datakällor för en typ *USER INPUT PARAMETER* för att erhålla de nödvändiga värdena som kan anges i datainmatningsfälten i dialogrutan vid körning, innan exekvering av ett ER-format börjar. Det här ämnet beskriver vilka datakällor för *USER INPUT PARAMETER* som för närvarande stöds.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Obligatoriska egenskaper

Du måste ange följande egenskaper för datakällor för varje typ *USER INPUT PARAMETER*:

- I fältet **Namn**, ange det interna namnet på datakällan. Du kan använda det här namnet i andra [uttryck](er-formula-language.md) och bindande delar av den konfigurerade modellmappningen eller formatkomponenten.

## <a name="optional-properties"></a><a name="optional-properties"></a>Ytterligare egenskaper

Du kan valfritt ange följande egenskaper för datakällor för varje typ *USER INPUT PARAMETER*:

- Ange i fältet **Etikett** den etikett som används för det relaterade datainmatningsfältet i dialogrutan vid körning. Du kan lägga till olika etikettext för olika språkkoder genom att aktivera fältet **Etikett** och sedan välja **Översätt**.
- I fältet **Hjälp** ange hjälptexten som visas vid designtillfället längst ner på sidan **Formatdesigner** på sidan **Modellmappningsdesigner** när en redigerbar datakälla av typen *USER INPUT PARAMETER* väljs. Den här texten kan innehålla mer information om datakällan som hjälper användarna när de konfigurerar det redigerbara formatet eller komponenten för modellmappning. Du kan lägga till olika hjälptext för olika språkkoder genom att välja **Översätt**.

    > [!NOTE]
    > Knappen **Översätt** som du kan använda för att lägga till [språkspecifika etiketter och text](er-design-multilingual-reports.md#format-component) blir bara tillgänglig när du har lagt till datakällan, sparat ändringarna och öppnat datakällan igen för redigering.

- I fältet **Läs bara**, konfigurera ett uttryck som returnerar en *[booleskt](er-formula-supported-data-types-primitive.md#boolean)* värde.

    - Om det konfigurerade uttrycket returnerar värdet **Sant** vid körning, är det relaterade datainmatningsfältet nedtonat i dialogrutan och du kan inte ändra värdet.
    - Om det konfigurerade uttrycket returnerar värdet **Falskt** vid körning, eller om inget uttryck är konfigurerat är det relaterade datainmatningsfältet tillgängligt i dialogrutan och du kan ändra dess värde.

- Konfigurera ett uttryck i fältet **Standardvärde** som returnerar värdet för den refererade parametertypen. Det här värdet kan användas för att fylla i ett standardvärde för det relaterade datainmatningsfältet i dialogrutan vid körning.

    När du kör ett ER-format sparas det värde som du anger i det relaterade datainmatningsfältet i dialogrutan vid körningen i minnet som det tidigare använda värdet. Tidigare använda värden sparas individuellt för varje fält, kör ER-format, aktuell användare och aktuell organisation (företag).

    - Ställ in alternativet **Återställ alltid till standardvärde** till **Ja** om värdet som returneras av uttrycka **Standardvärde** ska alltid användas som standardvärde, oavsett det tidigare använda värdet.
    - Ställ in alternativet **Återställ alltid till standardvärde** till **Nej** om värdet som returneras av uttrycksvärdet **Standardvärde** ska alltid användas som standardvärde endast när det tidigare använda värdet saknas.

    > [!NOTE]
    > Om du ställer in alternativet **Återställ alltid till standardvärde** till **Ja**, ett uttryck måste konfigureras i fältet **Standardvärde**.

- Om du ställer in alternativet **Tillåt flera val** till **Ja**, kan du välja flera värden för den konfigurerade parametern under körning. Om du ställer in värdet **Nej**, kan du bara välja ett enda värde.

    > [!NOTE]
    > Detta alternativ kan inte tillämpas på alla typer *USER INPUT PARAMETER*. Vid designtid används ett undantag för att informera användaren om att den konfigurerade användarindataparametern inte stöder flera val och att bara ett enda värde kan väljas eller anges.
    >
    > Om du ställer in alternativet **Tillåt flera val** till **Ja**, och du har angett ett uttryck i fältet **Standardvärde**, kan det uttrycket bara användas för att ställa in ett enda standardvärde.

- Välj alternativet **Redigera synlighet** om du vill ange om den konfigurerade parametern ska visas i dialogrutan vid körning.

    > [!NOTE]
    > Standardvärdet för datakällorna för en typ *USER INPUT PARAMETER* beror på vilken ER-komponent som innehåller dem.
    >
    > - Om en datakälla är konfigurerad i formatkomponenten visas den som standard.
    > - Om en datakälla konfigureras i modellmappningskomponenten visas den bara om värdet på datakällan påverkar resultatet när en ER-komponent körs. Du har till exempel lagt till en datakälla men inte använd den i uttryck och bindande delar av den aktuella modellmappningskomponenten. I det här fallet visas inte relevant datainmatningsfält som standard i dialogrutan vid körning. 

    På sidan **Formeldesigner** i fältet **Formel** konfigurerar du ett uttryck som returnerar ett *booleskt* värde.

    - Om det konfigurerade uttrycket returnerar värdet **Sant** vid körning, eller om inget uttryck är konfigurerat är det relaterade datainmatningsfältet är synligt i dialogrutan vid körning.
    - Om det konfigurerade uttrycket returnerar värdet **Falsk** döljs det relaterade datainmatningsfältet i dialogrutan vid körning. Om den anropas av andra uttryck vid körning returnerar den standardvärdet, det tidigare använda värdet eller standardvärdet för det aktuella datatypvärdet, beroende på andra inställningar.

## <a name="type-specific-properties"></a>Typspecifika egenskaper

### <a name="application-dependent-user-input-parameter"></a>Programberoende parameter för användarindata

Använd en datakälla **Allmänt** \> **Indataparameter för användare** för att erhålla det eller de nödvändiga värdena för en datatyp som är specificerad för den aktuella instansen av Microsoft Dynamics 365 Finance app. När du lägger till en datakälla av den här typen till en ER-komponent ska du ange följande egenskaper:

- I fältet **Namn på Operations-datatyp (EDT, enum)** välj en app [Utökad datatyp (EDT)](../extensibility/extensible-edts.md) eller en programuppräkning.

> [!NOTE]
> Vi rekommenderar att du granskar uttrycken som är konfigurerade i fältet **Skrivskyddat** och **Standardvärde** när du ändrar referensen **Namn på Operations-datatyp (EDT, enum)** i en redigerbar datakälla av denna typ *USER INPUT PARAMETER*.

I följande bild visas egenskaperna för `$TaxRegNum` datakälla som konfigurerats i **Instat XML (DE)** ER-formatkonfigurationen. Denna datakälla är konfigurerad att använda *beskrivning* EDT för att erbjuda dataregistreringsfältet **Momsregistreringsnummer** i dialogrutan vid körning.

![Egenskaper för en datakälla för typen USER INPUT PARAMETER i dialogrutan på sidan Formatdesigner.](./media/er-user-input-parameter-data-sources-01.png)

Följande illustration visar dialogrutan som visas vid körning när **Instat XML (DE)** ER-formatkonfigurationen körs för att [generera](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) Intrastat-deklarationen. Observera att det konfigurerade fältet **Skatteregistreringsnummer** är tillgängligt för dataregistrering.

![Dialogrutan Intrastat-rapport för det köra ER-formatet på Intrastat-sidan.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Datamodelluppräkning, användarindataparameter

Använd en datakälla för typen **Datamodell** \> **Uppräkning, användarindataparameter** för att erhålla det värde eller de värden som krävs för en enskild datamodell [uppräkning](er-formula-supported-data-types-primitive.md#enumeration). När du lägger till en datakälla av den här typen till en ER-komponent ska du ange följande egenskaper:

- I fältet **Modell**, ange en referens till basdatamodellen.
- I fältet **Modelluppräkning**, ange en referens till en uppräkning av den refererade datamodellen.
- I fältet **Version** välj revisionsnumret för ER-datamodellkomponenten som innehåller den refererade modelluppräkningen.

    > [!TIP]
    > Vid design kan du lämna fältet **Version** tomt om du vill komma åt listan över uppräkningar för den refererade datamodellkomponenten som finns i utkastversionen för motsvarande ER-datamodellkonfiguration. På det här sättet kan du redigera utkastversionen för modellmappningen eller formatkomponenten och utkastversionen av basdatamodellkomponenten.
    >
    > Observera dock att fältet **Version** bara kan lämnas tomt i utkastversionen av en modellmappning eller formatkomponent. När du ändrar statusen för en ER-modellmappning eller formatkonfiguration från **Utkast** till **Slutförd** fylls fältet automatiskt i av det högsta modelländringsnummer som är tillgängligt i den aktuella ekonomiinstansen. Om du inför en ny uppräkning eller ett nytt uppräkningsvärde i utkastversionen av din grunddatamodell och refererar till den i den redigerbara modellmappnings- eller formatkomponenten, ska du fylla i den utkastversionen av grunddatamodellkonfigurationen innan utkastversionen av ER-modellmappningen eller formatkonfigurationen är klar. Annars kommer ett undantag för "Sökväg inte att hitta" att föra in när du ändrar statusen för modellmappningen eller formatkonfigurationen från **Utkast** till **Slutförd**. Meddelandet informerar dig om att uppräknings- eller uppräkningsvärdet som refereras saknas i basdatamodellen.

I följande bild visas egenskaperna för `$ReportDirection` datakälla som konfigurerats i **Instat XML (DE) Contoso** ER-formatkonfigurationen. Konfigurationen **Instat XML (DE) Contoso** har [härletts](general-electronic-reporting.md#Configuration) från **Instat XML (DE)** konfigurationen. Denna datakälla är konfigurerad att använda *ReportDirection* modelluppräkning för att erbjuda lämpligt uppslagsfält i dialogrutan vid körning.

![Egenskaper för en datakälla för typen USER INPUT PARAMETER i dialogrutan på sidan Formatdesigner.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Formatuppräkning, användarindataparameter

Använd en datakälla för typen **Formatuppräkning** \> **Uppräkning, användarindataparameter** för att erhålla det eller de nödvändiga värdena för en enda formatuppräkning. När du lägger till en datakälla av den här typen till en ER-komponent ska du ange följande egenskaper:

- I fältet **Formatuppräkning**, ange en uppräkning av det redigerbara formatet.

> [!NOTE]
> Datakällor av den här typen kan bara konfigureras inom omfattningen av den redigerbara formatkomponenten.

## <a name="additional-resources"></a>Ytterligare resurser

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Initiera datakällvärden för typen USER INPUT PARAMETER från källkod](er-initiate-uip-data-source-value-from-source-code.md)
