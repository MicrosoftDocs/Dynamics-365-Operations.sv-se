---
title: Använd sammanfogningsdatakällor i ER-modellmappningar för att hämta data från flera programtabeller
description: Den här artikeln beskriver hur du kan använda datakällor av sammanfogningstyp i elektronisk rapportering (ER).
author: kfend
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: 3f03e69dbce7c9039f22dbb8f3afa06f16d9c080
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285164"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Använd sammanfogningsdatakällor för att hämta data från flera programtabeller i ER-modellmappningar (elektronisk rapportering)

[!include[banner](../includes/banner.md)]

När du konfigurerar ER-modellmappningar eller format (elektronisk rapportering) kan du [lägga till](#review) nödvändiga datakällor av typen **sammanfogning**. Vid designtillfället konfigureras **sammanfognings**-datakälla som en uppsättning med flera datakällor som alla returnerar en lista med poster. För alla datakällor utom den första måste du definiera nödvändiga villkor för att kunna koppla poster till aktuella och tidigare datakällor. Vid körning kommer en konfigurerad datakälla av typen **sammanfogning** att [returnera](#executeERformat) en enda överordnad lista med poster som innehåller fält från posterna i kapslade datakällor.

Följande typer av sammanfogningar stöds nu:

- Vänster yttre sammanfogning
    - Koppla alla poster från den första datakällan (längst till vänster) och sedan alla matchningar i enlighet med konfigurerade villkorsposter för den andra datakällan (längst till höger).
- Inre (höger) sammanfogning:
    - Sammanfoga endast poster från den första datakällan (längst till vänster) och endast poster för den andra datakällan (längst till höger) som matchar varandra i enlighet med konfigurerade villkor.

I den konfigurerade datakällan **Sammanfoga** när alla datakällor är av typen **Tabellposter** kan körningen av sammanfogningsdatakällan [utföras på databasnivå](#analyze) med ett enda SQL-uttryck. Denna instruktion minskar antal databasanrop, vilket förbättrar modellmappningens prestanda. Annars utförs körningen av **sammanfogningsdatakällan** i minnet.

> [!NOTE]
> Med funktionen **VALUEIN** i ER-uttryck som anger villkor för sammanfogning av poster i datakällor av sammanfogningstyp som ännu inte stöds. Besök sidan [Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md) för mer information om denna funktion.

Om du vill veta mer om den här funktionen fyller du i exemplet i den här artikeln.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Exempel: Använd sammanfogningsdatakällor i ER-modell mappningar

Följande steg beskriver hur systemadministratören eller den elektroniska rapportfunktionen kan konfigurera en ER-modellmappning (elektronisk rapportering) för att hämta data från flera programtabeller samtidigt genom att använda datakällor av typen **sammanfogning** för att förbättra prestanda för dataåtkomst. Dessa steg kan utföras i alla företag som Dynamics 365 Finance eller Regulatory Configuration Services (RCS).

### <a name="prerequisites"></a>Förutsättningar

Om du vill slutföra exemplen i den här artikeln måste du ha åtkomst till något av följande beroende på vilken service som används för att slutföra dessa steg:

**Gå till Finance för någon av följande roller:**

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

**Gå till RCS för någon av följande roller:**

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Du måste först slutföra dessa steg i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

I förväg måste du också hämta och spara följande exempelkonfigurationsfiler för ER:

| **Beskrivning av innehåll**  | **Filnamn**   |
|--------------------------|-----------------|
| Exempelkonfigurationsfil för **ER-datamodell** som används som datakälla för exemplen.| [Modell för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| Konfigurationsfil för **ER-modelmappning** som implementerar ER-datamodellen för exemplen. | [Mappning för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://download.microsoft.com/download/9/2/f/92f339ca-41fc-4f5e-b458-6983c957d3dd/MappingtolearnJOINdatasources.version.1.1.xml)|
| Exempelkonfigurationsfil för **ER-format**. Den här filen beskriver de data som ska fyllas i ER-formatkomponenten för exemplen. | [Format för att lära dig sammanfogningsdatakällor.version.1.1.xml](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>Aktivera en konfigurationsprovider

1. Få åtkomst till Finance eller RCS i den första sessionen av webbläsaren.
2. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
3. På sidan **Lokaliseringskonfigurationer** i avsnittet **Konfigurationsleverantörer** kontrollerar du att konfigurationsleverantören för exempelföretaget [Litware, Inc.](http://www.litware.com) är listat och att det är markerat som **Aktivt**. Om du inte ser den här konfigurationsleverantören ska du följa stegen i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Arbetsytan för elektronisk rapportering.](./media/GER-JoinDS-ActiveProvider.PNG)

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
4. Importera ER-formatkonfigurationsfilen.
    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **Bläddra** om du vill söka efter filen **Format för att lära dig sammanfogningsdatakällor.1.1.xml**.
    4. Välj **OK**.
5. I konfigurationsträdet expanderar du artikeln **Modell för att lära dig sammanfogningsdatakällor** och även andra modellobjekt (om de är tillgängliga).
6. Studera listan med ER-konfigurationer i trädet samt versionsinformationen i snabbfliken **Versioner** – de används som datakälla för exempelrapporten.

    ![Sidan Konfigurationer för elektronisk rapportering.](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Aktivera alternativ för körningsspårning

1. Välj **KONFIGURATIONER**.
2. Välj **Användarparametrar**.
3. Ange parametrar för körningsspårning som visas på bildrutan nedan.

    ![Sida för användarparametrar för elektronisk rapportering.](./media/GER-JoinDS-Parameters.PNG)

    Om dessa parametrar är aktiverade kommer körningsspårningen att genereras för varje körning av den importerade ER-formatfilen. Med hjälp av information om genererad körningsspårning kan du analysera körningen av komponenter för ER-format och ER-modellmappning. Besök sidan [Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md) för mer information om funktionen ER-körningsspårning.

### <a name="review-er-model-mapping-part-1"></a>Granska ER-modellmappning (del 1)

Granska inställningarna för ER-modellmappningskomponenten. Komponenten är konfigurerad för att få åtkomst till information om versioner av ER-konfigurationer, information om konfigurationer och konfigurationsprovider utan att använda datakällor av typen **Sammanfoga**.

1. Välj konfigurationen **Mappning för att lära dig sammanfogningsdatakällor**
2. Välj **designer** om du vill öppna listan över mappningar.
3. Välj **Designer** för att granska mappningsinformationen.
4. Välj **Visa detaljer**.
5. I konfigurationsträdet expanderar du datamodellobjektet **Set1** och **Set1.Details**:

    1. Bindning **Detaljer: postlista = Versioner** anger att artikeln **Set1.Details** är bunden till datakällan **Versioner** returnerade poster för tabellen **ERSolutionVersionTable**. Varje post i den här tabellen motsvarar en enda version av en ER-konfiguration. Innehållet i detta register visas på snabbfliken **Versioner** på sidan **Konfigurationer**.
    2. Bindning **ConfigurationVersion: String = @.PublicVersionNumber** innebär att värdet för den offentliga versionen av varje återställnings konfigurations version hämtas från fältet **PublicVersionNumber** i tabellen **ERSolutionVersionTable** och placeras i artikeln **ConfigurationVersion**.
    3. Bindning **ConfigurationTitle: String = @.'>Relations'.Solution.Name** anger att namnet på en ER-konfiguration hämtas från fältet **Namn** i tabellen **ERSolutionTable** med hjälp av många-till-en-relation (**'>Relationer'**) mellan tabellerna **ERSolutionVersionTable** och **ERSolutionTable** . Namn på ER-konfigurationer för den aktuella programinstansen visas i konfigurations trädet på sidan **konfigurationer**.
    4. Bindning **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** innebär att namnet på konfigurationsprovider som äger den nuvarande konfigurationen hämtas från fältet **Namn** i tabellen **ERVendorTable** med hjälp av många-till-en-relation mellan tabellerna **ERSolutionTable** och **ERVendorTable**. Namn på ER-konfigurationsprovider visas i konfigurations trädet på sidan **konfigurationer** på sidhuvudet för varje konfiguration. Hela listan med konfigurationsprovider hittas på tabellsidan **Organisationsadministration \> Elektronisk rapportering \> Konfigurationsprovider**.

    ![Designersida för ER-modellmappning, lista över bundna datamodellartiklar.](./media/GER-JoinDS-Set1Review.PNG)

6. I konfigurationsträdet expanderar du datamodellobjektet **Set1.Summary**:

    1. Bindning **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** anger att objektet **Set1.Summary.VersionsNumber** är bundet till sammansättningsfältet **VersionsNumber** för datakällan **VersionsSummary** av typen **GroupBy** typ som konfigurerades för att returnera antalet poster för tabellen **ERSolutionVersionTable** via datakällan **Versioner**.

    ![Redigera parametersidan för "Gruppera efter".](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Stäng sidan.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Granska ER-modellmappning (del 2)

Granska inställningarna för ER-modellmappningskomponenten. Komponenten är konfigurerad för att få åtkomst till information om versioner av ER-konfigurationer, information om konfigurationer och konfigurationsprovider genom att använda datakällor av typen **Sammanfoga**.

1. I konfigurationsträdet expanderar du datamodellobjektet **Set2** och **Set2.Details**. Bindningen **Detaljer: Postlista = Detaljer** anger att objektet **Set2.Details** är bundet till datakällan **Detaljer** konfigurerad som datakälla av typen **Koppling**.

    ![Designersidan för ER-modellmappning som visar expanderade modellartiklar för Uppsättning 2: Postdata.](./media/GER-JoinDS-Set2Review.PNG)

    Datakällan **Sammanfoga** kan läggas till genom att välja datakällan **Functions\Join**:

    ![Designersida för ER-modellmappning, Sammanfoga typ av datakälla.](./media/GER-JoinDS-AddJoinDS.PNG)

2. Välj datakällan **Information**.
3. Välj **redigera** i fönstret **datakällor**.
4. Välj **Redigera sammanfogning**.
5. Välj **Visa detaljer**.

    ![Parametersida för JOIN-datakälla.](./media/GER-JoinDS-JoinDSEditor.PNG)

    Den här sidan används för att utforma den begärda datakällan av **sammanfogningstyp**. Under körningen kommer den här datakällan att skapa en enda lista med poster från data källorna i rutnätet **Sammanfogade listor**. Sammanfogning av poster startar från datakällan **ConfigurationProviders** som är i rutnätet som en första kolumn (kolumnen **typ** är tom för den). Poster i alla andra datakällor kopplas därmed till poster i den överordnade datakällan baserat på dess ordning i det här rutnätet. Varje kopplad datakälla måste konfigureras som en datakälla som kapslats under en måldatakälla (datakällan `1Versions` är kapslad under `1Configurations`; datakällan `1Configurations` är kapslad under **ConfigurationProviders**). Varje konfigurerad datakälla måste innehålla villkoren för sammanfogningen. I datakällan för den här **sammanfogningen** definieras följande sammanfogningar:

    - Varje post i datakällan **ConfigurationProviders** (hänvisas till tabellen **ERVendorTable**) sammanfogas med poster från **1Configurations** (hänvisas till tabellen **ERSolutionTable**) och har samma värde i fälten **SolutionVendor** och **RecId**. Typen **Inre sammanfogning** används både för den här sammanfogningen och följande villkor för matchande poster:

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Varje post i datakällan **1Configurations** (hänvisas till tabellen **ERSolutionTable**) sammanfogas med poster från **1Versions** (hänvisas till tabellen **ERSolutionVersionTable**) och har samma värde i fälten **Lösning** och **RecId**. Typen **Inre sammanfogning** används både för den här sammanfogningen och följande villkor för matchande poster:

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - Alternativet **kör** konfigureras som en **fråga** vilket innebär att den här datakällan för sammanfogning ska köras i körtid på databasnivå som ett direkt SQL-anrop.

    För att koppla poster från datakällor som representerar programtabeller kan du ange sammanfogningsvillkor genom att använda andra par fält än de som beskriver befintliga i AOT-relationer mellan dessa register. Den här typen av sammanfogning kan konfigureras så att den körs på databas nivå också.

6. Stäng sidan.
7. Välj **Avbryt**.
8. I konfigurationsträdet expanderar du datamodellobjektet **Set2.Summary**:

    - Bindning **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** anger att objektet **Set2.Summary.VersionsNumber** är bundet till sammansättningsfältet **VersionsNumber** för datakällan **DetailsSummary** av typen **GroupBy** typ som konfigurerades för att returnera antalet sammanfogade poster för tabellen **Information** via datakällan av typen **Sammanfogning**.
    - Platsalternativet **Körning** konfigureras som en **Fråga** vilket innebär att den här datakällan för **GroupBy** kommer köras i körtid på databasnivå som ett direkt SQL-anrop. Beteendet är möjligt eftersom basdatakällan **Information** för typen **Koppling** konfigureras som körd på databasnivå.

    ![Parametersida för GROUPBY-datakälla.](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Stäng sidan.
10. Välj **Avbryt**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Kör ER-format

1. Gå till Finance eller RCS i webbläsarens andra session med samma autentiseringsuppgifter och företag som i den första sessionen.
2. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
3. Utöka **Modell för att lära dig sammanfogningsdatakällor**
4. Välj konfigurationen **Format för att lära dig sammanfogningsdatakällor**
5. Välj **Designer**.
6. Välj **Visa detaljer**.
7. Välj **mappning**.
8. Växla mellan **expandering/komprimering**.

    Det här formatet har utformats för att fylla en genererad textfil med en ny rad för varje version av en ER-konfiguration (ordning för **Version**). Varje genererad rad innehåller namnet på en konfigurationsprovider som äger den aktuella konfigurationen, konfigurationsnamnet och konfigurationsversionen som är åtskilda med semikolon. Den sista raden med genererade filer kommer att innehålla antalet upptäckta versioner av ER-konfigurationer (sekvens **sammanfattning**).

    ![Designersida för ER-format, fliken Format.](./media/GER-JoinDS-FormatReview.PNG)

    Datakällorna **Data** och **Sammanfattning** används för att fylla i information om konfigurationsversion till den genererade filen:

    - Information från datamodellen **Set1** används när du väljer **Nej** för datakällan **Väljare** vid körning på användardialogsidan när du kör ER-format.
    - Information från datamodellen **Set2** används när du väljer **Ja** för datakällan **Väljare** vid körning på användardialogsidan.

    ![Designersida för ER-format, fliken Mappa.](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Välj **kör**.
10. På dialogsidan väljer du **Nej** i fältet **Använd sammanfogningsdatakälla**.
11. Välj **OK**.
12. Granska genererad fil

    ![Fil genererad av elektroniska rapportparametrar som inte använder JOIN-datakälla.](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analysera körningsspårning för ER-format

1. I den första sessionen av Finance eller RCS, välj **Designer**.
2. Välj **resultatspårning**.
3. I rutnätet **resultatspårning** väljer du den översta posten i den senaste körningsspårningen av ett ER-format som använde den aktuella modellmappningskomponenten.
4. Välj **OK**.

    Körningsstatistik informerar om dubblerade anrop till programtabeller:

    - **ERSolutionTable** har anropats så många gånger som du har konfigurationsversionsposter i tabellen **ERSolutionVersionTable** medan antalet sådana samtal kan minskas i tid för prestandaförbättring.
    - **ERVendorTable** har anropats två gånger för varje konfigurationsversionspost som upptäcktes i tabellen **ERSolutionVersionTable** medan antalet sådana samtal kan minskas i tid för prestandaförbättring.

    ![Körningsstatistik på designersidan för ER-modellmappning.](./media/GER-JoinDS-Set1Run2.PNG)

5. Stäng sidan.

### <a name="execute-er-format"></a>Kör ER-format

1. Växla till din webbläsarflik med den andra sessionen av Finance eller RCS.
2. Välj **kör**.
3. På dialogsidan väljer du **Ja** i fältet **Använd sammanfogningsdatakälla**.
4. Välj **OK**.
5. Granska genererad fil

    ![Fil genererad av elektroniska rapportparametrar som använder JOIN-datakälla.](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analysera körningsspårning för ER-format

1. I den första sessionen av Finance eller RCS, välj **Designer**.
2. Välj **resultatspårning**.
3. I rutnätet **resultatspårning** väljer du den översta posten som representerar den senaste körningsspårningen av ett ER-format som använde den aktuella modellmappningskomponenten.
4. Välj **OK**.

    Statistik informerar dig om följande:

    - Programdatabasen har anropats en gång för att hämta poster från tabellerna **ERVendorTable**, **ERSolutionTable** och **ERSolutionVersionTable** för åtkomst till obligatoriska fält.

    ![Information om prestandastatistik för designersida för ER-modellmappning.](./media/GER-JoinDS-Set2Run2.PNG)

    - Programdatabasen har anropats en gång för att beräkna antalet konfigurationsversioner med hjälp av sammanfogningar som konfigurerats i datakällan **Information**.

    ![Designersida för ER-modellmappning som visar anrop i programdatabasen.](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Begränsningar

Som du ser i exemplet i den här artikeln kan **KOPPLA**-datakällan skapas från flera datakällor som beskriver de enskilda datauppsättningarna för poster som måste kopplas. Du kan konfigurera dessa datakällor med hjälp av inbyggt ER-[FILTER](er-functions-list-filter.md). När du konfigurerar datakällan så att den anropas utanför **KOPPLA**-datakällan kan du använda företagsintervall som en del av villkor för dataurval. Den inledande implementeringen av **KOPPLA**-datakällan stöder inte datakällor av den här typen. Om du till exempel anropar en [FILTER](er-functions-list-filter.md)-baserad datakälla inom körningsintervallet av en **KOPPLA**-datakälla, och den anropade datakällan innehåller företagsintervall som en del av villkor för dataurval, uppstår ett undantag.

I Microsoft Dynamics 365 Finance version 10.0.12 (augusti 2020) kan du använda företagsintervall inom intervallet för körning av [FILTER](er-functions-list-filter.md)-baserade datakällor som anropas inom körningsintervallet för en **KOPPLA**-datakälla. På grund av begränsningar i programmets [fråge](../dev-ref/xpp-library-objects.md#query-object-model)-verktyg kan företagsintervall endast användas för den första datakällan i en **KOPPLA**-datakälla.

### <a name="example"></a>Exempel

Du måste t.ex. göra ett enskilt anrop till programdatabasen för att få en lista över utländska handelstransaktioner för flera företag och information om den lagerartikel som det refereras till i dessa transaktioner.

I det här fallet konfigurerar du följande artefakter i din ER-modellmappning:

- **Intrastat**-rotdatakälla som representerar **Intrastat**-registret.
- **Artiklars** rotdatakälla som representerar **InventTable**-registret.
- **Företags** rotdatakälla som returnerar listan med företag (**DEMF** och **GBSI** i det här exemplet) där transaktioner måste nås. Företagskoden är tillgänglig från fältet **Companies.Code**.
- **X1** rotdatakälla med uttrycket `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. Som en del av villkoret för dataurval innehåller det här uttrycket definitionen av företagsintervall `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- **X2** datakällan som ett kapslat element i **X1** datakälla. Det innehåller uttrycket `FILTER (Items, Items.ItemId = X1.ItemId)`.

Slutligen kan du konfigurera en **KOPPLA**-datakälla där **X1** är den första datakällan och **X2** är den andra datakällan. Du kan ange **Fråga** som alternativet **Kör** för att tvinga ER att köra den här datakällan på databasnivå som ett direkt SQL-anrop.

När den konfigurerade datakällan körs medan ER-körningen [spåras](trace-execution-er-troubleshoot-perf.md) visas följande uttryck i ER-modellmappningsdesignern som en del av ER-prestationsspårningen.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Ett fel uppstår om du kör en **KOPPLA**-datakälla som har konfigurerats så att den innehåller villkor för dataurval med företagsintervall för ytterligare datakällor för den körda **KOPPLA**-datakällan.

## <a name="additional-resources"></a>Ytterligare resurser

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem.](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
