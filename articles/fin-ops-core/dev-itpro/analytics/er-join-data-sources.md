---
title: Använd sammanfogningsdatakällor i ER-modellmappningar för att hämta data från flera programtabeller
description: Det här avsnittet beskriver hur du kan använda datakällor av sammanfogningstyp i elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: 224acc19ee5dda430cd9471aa50e9d870a4f8c60
ms.sourcegitcommit: 564aa8eec89defdbe2abaf38d0ebc4cca3e28109
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667964"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Använd sammanfogningsdatakällor för att hämta data från flera programtabeller i ER-modellmappningar (elektronisk rapportering)

[!include[banner](../includes/banner.md)]

När du konfigurerar ER-modellmappningar eller format (elektronisk rapportering) kan du [lägga till](#review) nödvändiga datakällor av typen **sammanfogning**. Vid designtillfället konfigureras **sammanfognings**-datakälla som en uppsättning med flera datakällor som alla returnerar en lista med poster. För alla datakällor utom den första måste du definiera nödvändiga villkor för att kunna koppla poster till aktuella och tidigare datakällor. Vid körning kommer en konfigurerad datakälla av typen **sammanfogning** att [returnera](#executeERformat) en enda överordnad lista med poster som innehåller fält från posterna i kapslade datakällor.

Följande typer av sammanfogningar stöds nu:

- Vänster yttre sammanfogning
    - Koppla alla poster från den första datakällan (längst till vänster) och sedan alla matchningar i enlighet med konfigurerade villkorsposter för den andra datakällan (längst till höger).
- Inre (höger) sammanfogning:
    - Sammanfoga endast poster från den första datakällan (längst till vänster) och endast poster för den andra datakällan (längst till höger) som matchar varandra i enlighet med konfigurerade villkor.

I den konfigurerade datakällan **Sammanfoga** när alla datakällor är av typen **Tabellposter** kan körningen av sammanfogningsdatakällan [utföras på databasnivå](#analyze) med ett enda SQL-uttryck. Detta minskar antalet databasanrop, vilket förbättrar modellmappningens prestanda. Annars utförs körningen av **sammanfogningsdatakällan** i minnet.

> [!NOTE]
> Med funktionen **VALUEIN** i ER-uttryck som anger villkor för sammanfogning av poster i datakällor av sammanfogningstyp som ännu inte stöds. Besök sidan [Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md) för mer information om denna funktion.

Om du vill veta mer om den här funktionen fyller du i exemplet i det här avsnittet.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Exempel: Använd sammanfogningsdatakällor i ER-modell mappningar

Följande steg beskriver hur systemadministratören eller den elektroniska rapportfunktionen kan konfigurera en ER-modellmappning (elektronisk rapportering) för att hämta data från flera programtabeller samtidigt genom att använda datakällor av typen **sammanfogning** för att förbättra prestanda för dataåtkomst. Dessa steg kan utföras för alla företag med Dynamics 365 Finance eller som RCS (Regulatory Configuration Services).

### <a name="prerequisites"></a>Förutsättningar

Om du vill slutföra exemplen i det här avsnittet måste du ha åtkomst till något av följande beroende på vilken service som används för att slutföra dessa steg:

**Gå till Finance för någon av följande roller:**

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

**Gå till RCS för någon av följande roller:**

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Du måste först slutföra dessa steg i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

I förväg måste du även hämta från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=000000) och spara det lokalt som ER-exempelkonfigurationsfil:

| **Beskrivning av innehåll**  | **Filnamn**   |
|--------------------------|-----------------|
| Exempelkonfigurationsfil för **ER-datamodell** som används som datakälla för exemplen.| [Modell för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Konfigurationsfil för **ER-modelmappning** som implementerar ER-datamodellen för exemplen. | [Mappning för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Exempelkonfigurationsfil för **ER-format**. Den här filen beskriver de data som ska fyllas i ER-formatkomponenten för exemplen. | [Format för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>Aktivera en konfigurationsprovider

1. Få åtkomst till Finance eller RCS i den första sessionen av webbläsaren.
2. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
3. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsprovider** kontrollerar du att konfigurationsprovidern för exempelföretaget Litware, Inc. (http://www.litware.com) är listade och markerat som **aktivt**. Om du inte ser den här konfigurationsleverantören ska du följa stegen i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Arbetsytan för elektronisk rapportering](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importera ER-exempelkonfigurationsfiler

1. Välj **rapporteringskonfigurationer**.
2. Importera ER-konfigurationsfilen för datamodell.
    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **bläddra** om du vill söka efter filen **Modell för att lära dig sammanfogningsdatakällor.version.1.1.xml**.
    4. Välj **OK**.
3. Importera ER-konfigurationsfilen för modellmappning.
    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **Bläddra** om du vill söka efter filen **Mapping för att lära dig sammanfogningsdatakällor.1.1.xml**.
    4. Välj **OK**.
4.  Importera ER-formatkonfigurationsfilen.
    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **Bläddra** om du vill söka efter filen **Format för att lära dig sammanfogningsdatakällor.1.1.xml**.
    4. Välj **OK**.
5.  I konfigurationsträdet expanderar du artikeln **Modell för att lära dig sammanfogningsdatakällor** och även andra modellobjekt (om de är tillgängliga).
6.  Studera listan med ER-konfigurationer i trädet och versionsinformation på snabbfliken **versioner** – de används som datakälla för exempelrapporten.

    ![Sidan konfigurationer för elektronisk rapportering](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Aktivera alternativ för körningsspårning
1.  Välj **KONFIGURATIONER**.
2.  Välj **Användarparametrar**.
3.  Ange parametrar för körningsspårning som visas på bildrutan nedan.

    ![Sida för användarparametrar för elektronisk rapportering](./media/GER-JoinDS-Parameters.PNG)

    Om dessa parametrar är aktiverade kommer körningsspårningen att genereras för varje körning av den importerade ER-formatfilen. Med hjälp av information om genererad körningsspårning kan du analysera körningen av komponenter för ER-format och ER-modellmappning. Besök sidan [Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md) för mer information om funktionen ER-körningsspårning.

### <a name="review-er-model-mapping-part-1"></a>Granska ER-modellmappning (del 1)

Granska inställningarna för ER-modellmappningskomponenten. Komponenten är konfigurerad för att få åtkomst till information om versioner av ER-konfigurationer, information om konfigurationer och konfigurationsprovider utan att använda datakällor av typen **Sammanfoga**.

1.  Välj konfigurationen **Mappning för att lära dig sammanfogningsdatakällor**
2.  Välj **designer** om du vill öppna listan över mappningar.
3.  Välj **Designer** för att granska mappningsinformationen. 
4.  Välj **Visa detaljer**.
5.  I konfigurationsträdet expanderar du datamodellobjektet **Set1** och **Set1.Details**:

    1. Bindning **Detaljer: postlista = Versioner** anger att artikeln **Set1.Details** är bunden till datakällan **Versioner** returnerade poster för tabellen **ERSolutionVersionTable**. Varje post i den här tabellen motsvarar en enda version av en ER-konfiguration. Innehållet i den här tabellen visas på fliken **versioner** på sidan **konfigurationer**.
    2. Bindning **ConfigurationVersion: String = @.PublicVersionNumber** innebär att värdet för den offentliga versionen av varje återställnings konfigurations version hämtas från fältet **PublicVersionNumber** i tabellen **ERSolutionVersionTable** och placeras i artikeln **ConfigurationVersion**.
    3. Bindning **ConfigurationTitle: String = @.'>Relations'.Solution.Name** anger att namnet på en ER-konfiguration hämtas från fältet **Namn** i tabellen **ERSolutionTable** med hjälp av många-till-en-relation (**'>Relationer'**) mellan tabellerna **ERSolutionVersionTable** och **ERSolutionTable** . Namn på ER-konfigurationer för den aktuella programinstansen visas i konfigurations trädet på sidan **konfigurationer**.
    4. Bindning **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** innebär att namnet på konfigurationsprovider som äger den nuvarande konfigurationen hämtas från fältet **Namn** i tabellen **ERVendorTable** med hjälp av många-till-en-relation mellan tabellerna **ERSolutionTable** och **ERVendorTable**. Namn på ER-konfigurationsprovider visas i konfigurations trädet på sidan **konfigurationer** på sidhuvudet för varje konfiguration. Hela listan med konfigurationsprovider hittas på tabellsidan **Organisationsadministration \> Elektronisk rapportering \> Konfigurationsprovider**.

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-Set1Review.PNG)

6.  I konfigurationsträdet expanderar du datamodellobjektet **Set1.Summary**:

    1. Bindning **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** anger att objektet **Set1.Summary.VersionsNumber** är bundet till sammansättningsfältet **VersionsNumber** för datakällan **VersionsSummary** av typen **GroupBy** typ som konfigurerades för att returnera antalet poster för tabellen **ERSolutionVersionTable** via datakällan **Versioner**.

    ![Sidan för parametrar för datakälla för GROUPBY](./media/GER-JoinDS-Set1GroupByReview.PNG)

7.  Stäng sidan.

### <a name="review"></a> Granska ER-modellmappning (del 2)

Granska inställningarna för ER-modellmappningskomponenten. Komponenten är konfigurerad för att få åtkomst till information om versioner av ER-konfigurationer, information om konfigurationer och konfigurationsprovider genom att använda datakällor av typen **Sammanfoga**.

1.  I konfigurationsträdet expanderar du datamodellobjektet **Set2** och **Set2.Details**. Observera att bindning **Details: Record list = Details** anger att objektet **Set2.Details** är bundet till datakällan **information** konfigurerad som datakälla av typen **Sammanfoga**.

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-Set2Review.PNG)

    Datakällan **Sammanfoga** kan läggas till genom att välja datakällan **Functions\Join**:

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-AddJoinDS.PNG)

2.  Välj datakällan **Information**.
3.  Välj **redigera** i fönstret **datakällor**.
4.  Välj **Redigera sammanfogning**.
5.  Välj **Visa detaljer**.

    ![Sidan för parametrar för datakälla för JOIN](./media/GER-JoinDS-JoinDSEditor.PNG)

    Den här sidan används för att utforma den begärda datakällan av **sammanfogningstyp**. Under körningen kommer den här datakällan att skapa en enda lista med poster från data källorna i rutnätet **Sammanfogade listor**. Sammanfogning av poster startar från datakällan **ConfigurationProviders** som är i rutnätet som en första kolumn (kolumnen **typ** är tom för den). Poster i alla andra datakällor kopplas därmed till poster i den överordnade datakällan baserat på dess ordning i det här rutnätet. Varje sammanfogad datakälla måste konfigureras som en datakälla som kapslats under en måldatakälla (datakällan **1Versions** är kapslad under **1Configurations**; datakällan **1Configurations** är kapslad under **ConfigurationProviders**). Varje konfigurerad datakälla måste innehålla villkoren för sammanfogningen. I datakällan för den här **sammanfogningen**definieras följande sammanfogningar:

    - Varje post i datakällan **ConfigurationProviders** (hänvisas till tabellen **ERVendorTable**) sammanfogas med poster från **1Configurations** (hänvisas till tabellen **ERSolutionTable**) och har samma värde i fälten **SolutionVendor** och **RecId**. Typen **Inre sammanfogning** används både för den här sammanfogningen och följande villkor för matchande poster: 

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Varje post i datakällan **1Configurations** (hänvisas till tabellen **ERSolutionTable**) sammanfogas med poster från **1Versions** (hänvisas till tabellen **ERSolutionVersionTable**) och har samma värde i fälten **Lösning** och **RecId**. Typen **Inre sammanfogning** används både för den här sammanfogningen och följande villkor för matchande poster:

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - Alternativet **kör** konfigureras som en **fråga** vilket innebär att den här datakällan för sammanfogning ska köras i körtid på databasnivå som ett direkt SQL-anrop.

    Observera att när du sammanfogar poster med datakällor som representerar programtabeller kan du ange sammanfogningsvillkor genom att använda andra par fält än de som beskriver befintliga i AOT-relationer mellan dessa register. Den här typen av sammanfogning kan konfigureras så att den körs på databas nivå också.

6.  Stäng sidan.
7.  Välj **Avbryt**.
8.  I konfigurationsträdet expanderar du datamodellobjektet **Set2.Summary**:

    - Bindning **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** anger att objektet **Set2.Summary.VersionsNumber** är bundet till sammansättningsfältet **VersionsNumber** för datakällan **DetailsSummary** av typen **GroupBy** typ som konfigurerades för att returnera antalet sammanfogade poster för tabellen **Information** via datakällan av typen **Sammanfogning**.
    - Notera att **körning** konfigureras som en **fråga** vilket innebär att den här datakällan för **GroupBy** kommer köras i körtid på databasnivå som ett direkt SQL-anrop. Detta är möjligt eftersom informationen om basdatakällan **Information** för typen **sammanfogning** konfigureras som utförd på databasnivå.

    ![Sidan för parametrar för datakälla för GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9.  Stäng sidan.
10. Välj **Avbryt**.

### <a name="executeERformat"></a> Kör ER-format

1.  Gå till Finance eller RCS i webbläsarens andra session med samma autentiseringsuppgifter och företag som i den första sessionen.
2.  Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
3.  Utöka **Modell för att lära dig sammanfogningsdatakällor**
4.  Välj konfigurationen **Format för att lära dig sammanfogningsdatakällor**
5.  Välj **Designer**.
6.  Välj **Visa detaljer**.
7.  Välj **mappning**.
8.  Växla mellan **expandering/komprimering**.

    Observera att det här formatet har utformats för att fylla en genererad textfil med en ny rad för varje version av en ER-konfiguration (sekvens **Version**). Varje genererad rad innehåller namnet på en konfigurationsprovider som äger den aktuella konfigurationen, konfigurationsnamnet och konfigurationsversionen som är åtskild med semikolon. Den sista raden med genererade filer kommer att innehålla antalet upptäckta versioner av ER-konfigurationer (sekvens **sammanfattning**).

    ![ER-formatdesignersida](./media/GER-JoinDS-FormatReview.PNG)

    Datakällorna **Data** och **Sammanfattning** används för att fylla i information om konfigurationsversion till den genererade filen:

    - Information från datamodellen **Set1** används när du väljer **Nej** för datakällan **Väljare** vid körning på användardialogsidan när du kör ER-format.
    - Information från datamodellen **Set2** används när du väljer **Ja** för datakällan **Väljare** vid körning på användardialogsidan.

    ![ER-formatdesignersida](./media/GER-JoinDS-FormatMappingReview.PNG)

9.  Välj **kör**.
10. På dialogsidan väljer du **Nej** i fältet **Använd sammanfogningsdatakälla**.
11. Välj **OK**.
12. Granska genererad fil

    ![Dialogsidan ER-användare](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analysera körningsspårning för ER-format

1.  I den första sessionen av Finance eller RCS, välj **Designer**.
2.  Välj **resultatspårning**.
3.  I rutnätet **resultatspårning** väljer du den översta posten i den senaste körningsspårningen av ett ER-format som använde den aktuella modellmappningskomponenten.
4.  Välj **OK**.

    Observera att körningsstatistik informerar om dubblerade anrop till programtabeller:

    - **ERSolutionTable** har anropats så många gånger som du har konfigurationsversionsposter i tabellen **ERSolutionVersionTable** medan antalet sådana samtal kan minskas i tid för prestandaförbättring.
    - **ERVendorTable** har anropats två gånger för varje konfigurationsversionspost som upptäcktes i tabellen **ERSolutionVersionTable** medan antalet sådana samtal kan minskas i tid för prestandaförbättring.

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-Set1Run2.PNG)

5.  Stäng sidan.

### <a name="execute-er-format"></a>Kör ER-format

1.  Växla till din webbläsarflik med den andra sessionen av Finance eller RCS.
2.  Välj **kör**.
3.  På dialogsidan väljer du **Ja** i fältet **Använd sammanfogningsdatakälla**.
4.  Välj **OK**.
5.  Granska genererad fil

    ![Dialogsidan ER-användare](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze"></a> Analysera körningsspårning för ER-format

1.  I den första sessionen av Finance eller RCS, välj **Designer**.
2.  Välj **resultatspårning**.
3.  I rutnätet **resultatspårning** väljer du den översta posten som representerar den senaste körningsspårningen av ett ER-format som använde den aktuella modellmappningskomponenten.
4.  Välj **OK**.

    Observera att körningsstatistik informerar om följande:

    - Programdatabasen har anropats en gång för att hämta poster från tabellerna **ERVendorTable**, **ERSolutionTable** och **ERSolutionVersionTable** för åtkomst till obligatoriska fält.

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-Set2Run2.PNG)

    - Programdatabasen har anropats en gång för att beräkna antalet konfigurationsversioner med hjälp av sammanfogningar som konfigurerats i datakällan **Information**.

    ![Sidan ER-modellmappningsdesigner](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="additional-resources"></a>Ytterligare resurser

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem.](trace-execution-er-troubleshoot-perf.md)
