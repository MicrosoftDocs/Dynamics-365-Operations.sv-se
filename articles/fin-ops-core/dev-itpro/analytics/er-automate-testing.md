---
title: Automatisera testning med elektronisk rapportering
description: I den här artikeln beskrivs hur du kan använda baslinjefunktionen för elektronik rapportering (ER) för att automatisera testning av funktioner.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: df2baa988bb634db11d819dd84ef73eaa560bab9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892781"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatisera testning med elektronisk rapportering

[!include[banner](../includes/banner.md)]

I den här artikeln beskrivs hur du kan använda ramverket för elektronik rapportering (ER) för att automatisera testning av vissa funktioner. Exemplet i den här artikeln visar hur du automatiserar testningen av bearbetning av leverantörsbetalningar.

Appen använder ER-ramverket för att generera betalningsfiler och motsvarande dokument under bearbetning av leverantörsbetalningar. ER-ramverket består av en datamodell, modellmappning och formatkomponenter som stöder betalningsbearbetning för olika betalningstyper och genereringen av dokument i olika format. Dessa komponenter kan hämtas från Microsoft Dynamics LCS (Lifecycle Services) och importeras till instansen.

Du kan också anpassa varje komponent i Microsoft och använda den som grund för din egen anpassade komponent. Genom att skapa en anpassad version kan du göra ändringar som stöder specifika krav. Du kan t.ex. ändra mappningen för ER-datamodell och ER-modell för att få åtkomst till kundspecifika programdata, eller ändra ett återställningsformat om du vill ändra layouten i ett genererat dokument.

Du kan använda anpassade ER-format för att bearbeta betalningsfiler som genererar leverantörsbetalningar och även för att bearbeta kontrollrapporter. Versionsnumrering stöds i ER-komponenter. Därför kan Microsoft tillhandahålla uppdaterade versioner av ER-lösningar för bearbetning av leverantörsbetalningar, och du kan automatiskt slå samman den uppdaterade versionen med den anpassade komponenten genom att ombasera den. Du måste dock testa den ombaserade versionen för att vara säker på att den fungerar som förväntat.

ER-datamodeller och ER-modellmappningar är vanliga för många ER-format som används för att bearbeta betalningar av olika typer och för att generera lands-/regionspecifika betalningsdokument. Därför är det starkt önskvärt att automatisera godkännandet av användare och integration så att det utförs automatiskt i flera företag men tar hänsyn till land- eller regionssammanhanget för varje målföretag, använder olika datauppsättningar, och så vidare.

Mer information om hur du skapar en anpassad version av ett format som baseras på det format som du har fått från en konfigurationsleverantör finns i [ER uppgraderar ditt format genom att anta en ny, grundläggande version av det formatet](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Viktiga begrepp

Funktionella privilegierade användare kan skapa godtagande och integrationstestning för användare utan att behöva skriva källkoden.

- Använd funktionen ER-baslinje för att jämföra genererade dokument med huvudkopior. Mer information finns i [Spåra genererade rapportresultat och jämför dem med baslinjevärden](er-trace-reports-compare-baseline.md).
- Använd uppgiftsinspelare om du vill registrera testfall och ta med utvärdering av baslinje. Mer information finns i [Uppgiftsinspelarresurser](../user-interface/task-recorder.md).
- Gruppera testfall för obligatoriska testscenarier. Mer information finns i [skapa och automatisera användaracceptanstest](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Använd affärsprocessmodelleraren (BPM) i LCS för att göra bibliotek för användaracceptanstester.
    - Använd BPM-testbibliotek för att skapa en testplan och testpaket i Microsoft Azure DevOps Services (Azure DevOps).

Funktionella privilegierade användare kan köra tester av användarens acceptans och integration.

- Använda Regression Suite Automation Tool (RSAT) för att köra testfall av önskat testprogrampaket.
- Rapportera resultaten från testet till Azure DevOps, och undersök dessa resultat med hjälp av den här tjänsten.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra uppgifterna i detta ämne måste du slutföra följande förutsättningar:

- Distribuera en topologi som stöder testautomatisering. Du måste ha tillgång till instansen av denna topologi för rollen **systemadministratör**. Den här topologin måste innehålla de demodata som ska användas i det här exemplet. Mer information finns i [distribuera och använd en miljö som stöder kontinuerlig automatisering av bygga och testa](../perf-test/continuous-build-test-automation.md).
- Om du vill köra acceptans- och integrationstest automatiskt måste du installera RSAT i den topologi som du använder och konfigurera det på lämpligt sätt. Information om hur du installerar och konfigurerar RSAT och konfigurerar den så att den fungerar med Finance and Operations-appar och Azure DevOps, se [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Var uppmärksam på förutsättningarna för att använda verktyget. Följande illustration visar ett exempel på RSAT-inställningar. Den blå rektangeln innesluter parametrarna som anger åtkomsten till Azure DevOps. Den gröna rektangeln innesluter parametrarna som anger åtkomsten till instansen.

    ![RSAT-inställningar.](media/GER-Configure.png "Skärmbild av dialogrutan RSAT-inställningar")

- Om du vill ordna testfall i paket som hjälper till att garantera korrekt körningsordning så att du kan samla in loggar över testkörningar för vidare rapportering och utredning måste du ha åtkomst till Azure DevOps från den distribuerade topologin.
- Om du vill slutföra exemplet i den här artikeln rekommenderar vi att du hämtar [ER-användning för test av RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Zip-filen innehåller följande uppgiftsguider:

    | Innehåll                                           | Filnamn och plats |
    |---------------------------------------------------|------------------------|
    | Exempel på uppgiftsinspelning för förberedelse av data för testning | Förbered\\inspelning.xml |
    | Exempel på uppgiftsinspelning för att bearbeta leverantörsbetalning   | Bearbeta\\inspelning.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Förbered modulen leverantörsreskontra om du vill bearbeta leverantörsbetalningar

1. Logga in på instansen.
2. Hämta följande ER-konfigurationer från LCS. För instruktioner, se [ER-importera en konfiguration från Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).

    - **Betalningsmodell** ER-modellkonfiguration
    - **Betalningsmodellmappnning 1611** Mappningskonfiguration för ER-modell
    - **BACS (UK)** ER-formatkonfiguration

    ![Konfigurationer för elektronisk rapportering.](media/GER-Configurations.png "Skärmbild av sidan Konfigurationer i elektroniskt rapportering")

3. Välj demoföretaget **GBSI** som har kontexten land/region i Storbritannien.
4. Konfigurera parametrar för leverantörsreskontra:

    1. Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsmetoder**.
    2. Välj Metod för **elektroniska** betalningar.
    3. Konfigurera den valda betalningsmetoden så att den använder ER-formatet **BACS (UK)** som du hämtade tidigare för bearbetning av leverantörsbetalningar:

        1. På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.
        2. I fältet **Exportera formatkonfiguration** väljer du **BACS (UK)**.

    ![Sidan Betalningsmetoder.](media/GER-APParameters.png "Skärmbild av sidan betalningsmetoder")

    > [!NOTE]
    > Om du har den härledda versionen av det här ER-formatet som har skapats för anpassningar kan du välja den här konfigurationen i betalningsmetoden **elektronisk**.

5. Skapa ett exempel på en leverantörsbetalning:

    1. Gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.
    2. Kontrollera att du inte har bokfört betalningsjournalen.

        ![Sidan betalningsjournal.](media/GER-APJournal.png "Skärmbild av sidan betalningsjournal")

    3. Välj **rader** och ange en rad med följande information.

        | Fält               | Exempelvärde   |
        |---------------------|-----------------|
        | Leverantörsnamn         | GB\_SI\_000001  |
        | Debet               | 1,000.00        |
        | Valuta            | GBP             |
        | Motkontotyp | Bank            |
        | Motkonto      | GBSI-OPERATION       |
        | Betalningsmetod   | Elektronisk      |

    ![Sidan Leverantörsbetalningar.](media/GER-APJournalLines.png "Skärmbild av sidan leverantörsbetalningar")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Förbered ER-ramverket för att testa bearbetning av leverantörsbetalning

### <a name="configure-er-parameters"></a>Konfigurera ER-parametrar

1. Gå till **Organisationsadministration \> Elektronisk rapportering \> Parametrar för elektronisk rapportering**.
2. På fliken **Bilagor** i fältet **Baslinje**, välj **Fil** som dokumenttyp som ramverket dokumenthantering (DM) använder för att behålla dokument som är relaterade till baslinjefunktioner som DM-bilagor.

    ![Sida för parametrar för elektronisk rapportering.](media/GER-ERParameters.png "Skärmbild av sidan parametrar för elektronisk rapportering")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Generera baslinjekopior av dokument relaterade till leverantörsbetalningar

1. Gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.
2. Markera **rader**
3. Välj **Generera betalningar**.
4. Välj Metod för **elektroniska** betalningar.
5. Välj bankkontot **GBSI OPER**.
6. Ange alternativet **Skriv ut kontrollrapport** till **Ja**.
7. Hämta den genererade utdata som en zip-fil.
8. Öppna den hämtade filen.
9. Extrahera följande filer från den hämtade filen:

    - **Fil** betalningsfil i textformat
    - **ERVendOutPaymControlReport** kontrollrapportfil i XLSX-format

    ![Extraherade filer.](media/GER-APJournalProcessed.png "Skärmbild av extraherade filnamn i Utforskaren i Windows")

### <a name="turn-on-the-er-baseline-feature"></a>Aktivera funktionen för ER-baslinje

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. Välj **Användarparametrar** på fliken **Konfigurationer** i åtgärdsfönstret.
3. Ställ in alternativet **Kör i felsökningsläge** till **Ja**.

Genom att aktivera parametern **kör i felsökningsläge** tvingar du ER-ramverket att utföra följande åtgärder efter körningen av ett återställningsformat som genererar utgående dokument:

1. Fastställ om en baslinje har konfigurerats för någon av komponenterna i det körda ER-formatet.
2. Ta reda på om varje konfigurerad baslinje är tillämplig i de aktuella villkoren (företagskod för det inloggade företaget, filnamn och filnamnstillägg för genererade utdata och så vidare).
3. Utför följande åtgärder för varje tillämplig baslinje:

    1. Jämför de utdata som genereras under körningen av ER-formatet med motsvarande baslinje.
    2. Spara resultaten av jämförelsen i felsökningsloggen för ER-konfigurationer.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Konfigurera ER-baslinjer för bearbetning av leverantörsbetalning

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. Välj **baslinjer**.
3. Välj **Ny**.
4. I fältet **Referenser** väljer du formatet **BACS (UK)**.
5. Välj **bilagor**.
6. Lägg till en ny baslinje för leverantörsbetalningsfilen:

    1. Välj **Ny**.
    2. I fältet **typ** väljer du DM-dokumenttypen **fil** som du konfigurerade i ER-parametrarna för att lagra baslinjeartefakter.
    3. Bläddra för att välja den lokalt sparade betalningsfilen **Fil** i textformat.
    4. I fältet **Beskrivning**, ange **TXT-fil för betalning**.

7. Lägg till en ny baslinje för kontrollrapporten för leverantörsbetalningen:

    1. Välj **Ny**.
    2. I fältet **typ** väljer du DM-dokumenttypen **fil** som du konfigurerade i ER-parametrarna för att lagra baslinjeartefakter.
    3. Bläddra för att välja den lokalt sparade kontrollrapportfilen **ERVendOutPaymControlReport** i XLSX-format.
    4. I fältet **Beskrivning**, ange **XLSX-kontrollrapport för betalning**.

    ![Baslinjer för leverantörsbetalningsfilen och kontrollrapporten.](media/GER-BaselineAttachments.png "Skärmbild av sidan konfigurationer med rapporten XLSX-kontroll för betalning vald")

8. Stäng sidan.
9. På snabbfliken **Baslinjer** väljer du **Ny** för att konfigurera en baslinje för betalningsfilen:

    1. Namnge raden **baslinjeinställning för betalningsfil**.
    2. I fältet **filkomponentnamn** väljer du **fil** för att använda den här baslinjen till ER-formatets utdata som genererar betalningsfilen i BACS (UK) textformat.
    3. I fältet **företag** väljer du **GBSI** för att använda denna baslinje när ER-formatet **BACS (UK)** körs i GBSI-företag.
    4. I fältet **Filnamnsmask** anger du **\*.TXT** för att endast använda den här baslinjen till utdata för den **fil** formatkomponent som har filnamnstillägget **.txt**.
    5. I fältet **baslinje** väljer du **TXT-fil för betalning** så att denna baslinje används för jämförelse med den genererade utdata.

10. Välj **ny** om du vill konfigurera en baslinje för kontrollrapporten:

    1. Namnge raden **baslinjeinställning för kontrollrapport**.
    2. I fältet **filkomponentnamn** väljer du **ERVendOutPaymControlReport** för att använda den här baslinjen till ER-formatets utdata som genererar kontrollrapporten.
    3. I fältet **företag** väljer du **GBSI** för att använda denna baslinje när ER-formatet **BACS (UK)** körs i GBSI-företag.
    4. I fältet **Filnamnsmask** anger du **\*.XLSX** för att endast använda den här baslinjen till utdata för den **ERVendOutPaymControlReport** formatkomponent som har filnamnstillägget **.xslx**.
    5. I fältet **baslinje** väljer du **XLSX-kontrollrapport för betalning** så att denna baslinje används för jämförelse med den genererade utdata.

    ![Snabbfliken Baslinjer på sidan Konfigurationer.](media/GER-BaselineRules.png "Skärmbild av snabbfliken Baslinjer på sidan Konfigurationer")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Registrera tester för att validera bearbetning av leverantörsbetalning

Som funktionell priviligierad användare kan du registrera dina egna steg för att testa bearbetning av leverantörsbetalning. Vi rekommenderar att du spelar upp (och redigerar, efter behov) uppgiftsinspelningen **förbereda\\inspelning.xml** som du hämtade tidigare. Den här inspelningen används för att ställa in alla testdata till rätt tillstånd. Det steget är nödvändigt eftersom testningen kan utföras många gånger, och varje test måste använda data som är i samma tillstånd.

### <a name="reset-user-settings"></a>Återställ användarinställningar

1. Öppna standardinstrumentpanelen.
2. Välj knappen **inställningar** (kugghjulssymbolen).
3. Välj **Användaralternativ**.
4. Välj **Användardata**
5. Välj **Återställ**.
6. Välj **ja** för att bekräfta att du vill återställa användardata.
7. Stäng sidan.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Registrera stegen för att förbereda data för testning

1. Välj knappen **inställningar** (kugghjulssymbolen).
2. Välj **uppgiftsregistrering**.
3. Välj **Spela upp inspelning**.
4. Välj **Öppna från datorn**.
5. Välj **bläddra** och markera den lokalt sparade filen **Förbered\\inspelning.xml**.
6. Välj **start**.
7. Fortsätt välja **Spela upp nästa väntande steg** tills alla steg i inspelningen har spelats upp.

Den här uppgiftsinspelningen utför följande åtgärder:

1. Ställ in status för den bearbetade betalningsraden till **ingen**.

    ![Uppgiftsinspelning av steg 3 till 4.](media/GER-Recording1Review1.png "Skärmbild av uppgiftsinspelning steg 3 till 4")

2. Aktivera ER-användarparametern **kör i felsökningsläge**.

    ![Uppgiftsinspelning av steg 9 till 10.](media/GER-Recording1Review2.png "Skärmbild av uppgiftsinspelning steg 9 till 10")

3. Rensa upp ER-felsökningsloggen som innehåller resultaten av jämförelsen mellan skapade filer till baslinjer.

    ![Uppgiftsinspelning av steg 13 till 15.](media/GER-Recording1Review3.png "Skärmbild av uppgiftsinspelning steg 13 till 15")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Registrera stegen för att testa bearbetning av leverantörsbetalning

Vi rekommenderar att du spelar upp (och redigerar, efter behov) uppgiftsinspelningen **bearbeta\\inspelning.xml** som du hämtade tidigare. Den här registreringen används för att bearbeta leverantörsbetalningar och validera resultaten av jämförelsen av genererade dokument till motsvarande baslinjer.

1. Välj knappen **inställningar** (kugghjulssymbolen).
2. Välj **uppgiftsregistrering**.
3. Välj **Spela upp inspelning**.
4. Välj **Öppna från datorn**.
5. Välj **bläddra** och markera den lokalt sparade filen **Bearbeta\\inspelning.xml**.
6. Välj **start**.
7. Fortsätt välja **Spela upp nästa väntande steg** tills alla steg i inspelningen har spelats upp.

Den här uppgiftsinspelningen utför följande åtgärder:

1. Starta bearbetning av leverantörsbetalningar
2. Välj korrekta körningsparametrar och aktivera genereringen av en kontrollrapport.

    ![Uppgiftsinspelning av steg 3 till 8.](media/GER-Recording2Review1.png "Skärmbild av uppgiftsinspelning steg 3 till 8")

3. Få åtkomst till ER-felsökningsloggen för att spela in av jämförelsen mellan skapade utdata till motsvarande baslinjer.

    I ER-felsökningsloggen visas resultatet av jämförelsen i fältet **Genererad text**. Fälten **Formatkomponent** och **Formatsökväg som orsakade en loggpost** refererar till den filkomponent för vilken den genererade utdata har jämförts med baslinjen.

    ![Poster på sidan för körningsloggar för elektronisk rapportering.](media/GER-ERDebugLog.png "Skärmbild av poster i körningsloggar för elektronisk rapportering")

4. Jämförelsen mellan aktuella utdata för baslinjen registreras genom att du **validerar** alternativet uppgiftsinspelaren och väljer **aktuellt värde**.

    ![Använda alternativet Validera för jämförelse med det aktuella värdet.](media/GER-TRRecordValidation.png "Skärmbild för användning av alternativet Validera för jämförelse med det aktuella värdet")

    Följande illustration visar hur de inspelade valideringsstegen ser ut i uppgiftsinspelningen.

    ![Uppgiftsinspelning av steg 13 till 15.](media/GER-Recording2Review2.png "Skärmbild av uppgiftsinspelning steg 13 till 15")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Lägg till de registrerade testerna i Azure DevOps

1. Öppna Azure DevOps-miljön.
2. Välj det projekt som du definierade i RSAT-parametrarna när du [konfigurerade verktyget](#prerequisites).
3. Välj den testplan som du definierade i RSAT-parametrarna när du [konfigurerade verktyget](#prerequisites).
4. Skapa ett nytt testfall för den valda testplanen:

    1. Namnge testfallet **Förbered data för testbearbetning av leverantörens elektroniska betalning**.
    2. Bifoga filen **Inspelning.xml** från mappen **Förbered** som du hämtade tidigare.

5. Skapa ett nytt testfall för den valda testplanen:

    1. Namnge testfallet **Testa bearbetning av leverantörsbetalningar genom att använda ER-formatet BACS (UK)**.
    2. Bifoga filen **Inspelning.xml** från mappen **Bearbeta** som du hämtade tidigare.

    ![Nytt testärende för den valda testplanen.](media/GER-RSAT-DevOps-Tests-Passed.png "Skärmbild av nya testärenden för den valda testplanen")

> [!NOTE]
> Var uppmärksam på korrekt körningsordning för de tester som läggs till.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Förbered RSAT för körning av de registrerade testerna

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Läs in testerna från Azure DevOps till RSAT

1. Öppna det lokala programmet för RSAT i den aktuella topologin.
2. Välj **Läs in** för att läsa in testerna som för närvarande finns i Azure DevOps i RSAT.

    ![Tester som lästs in i RSAT.](media/GER-RSAT-RSAT-Tests-Loaded.png "Skärmbild av de tester som har lästs in i RSAT")

### <a name="create-automation-and-parameters-files"></a>Skapa automatisering och parameterfiler

1. Välj testerna som du har läst in från Azure DevOps i RSAT.
2. Välj **Ny** för att skapa RSAT automatisering och parameterfiler.

    ![RSAT-automatisering och parameterfiler som skapats i RSAT.](media/GER-RSAT-RSAT-Tests-Initiated.png "Skärmbild av RSAT automatisering och parameterfiler som skapats i RSAT")

### <a name="modify-the-parameters-files"></a>Ändra parameterfilerna

1. I RSAT namnger du testfallet **Förbered data för testbearbetning av leverantörens elektroniska betalning**.
2. Välj **Redigera**.
3. I Microsoft Excel-arbetsbok som är öppen, i kalkylbladet **allmänt** ändrar du företagskoden till **GBSI**, eftersom detta företag kommer att användas för testkörningen.
4. I RSAT väljer du testfallet **Testa bearbetning av leverantörsbetalningar genom att använda ER-formatet BACS (UK)**.
5. Välj **Redigera**.
6. I den Excel-arbetsbok som är öppen, i kalkylbladet **allmänt** ändrar du företagskoden till **GBSI**.
7. I kalkylbladet **ERFormatMappingRunLogTable** ska du notera att celler A:3 och C:3 innehåller texten i fälten i ER-felsökningsloggtabellen som används för att validera resultaten av jämförelsen av utdata till baslinjen. Dessa texter används för att utvärdera ER-felsökningsloggposter som skapas under testkörningen.

    ![Kalkylbladet ERFormatMappingRunLogTable.](media/GER-RSAT-RSAT-ExcelParameters.png "Skärmbild av kalkylbladet ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Kör testerna och analysera resultaten

### <a name="run-the-tests-in-rsat"></a>Kör testerna i RSAT

1. Markera de inlästa testerna i RSAT.
2. Välj **kör**.

Observera att testfall körs automatiskt i appen med hjälp av en webbläsare.

### <a name="analyze-the-results-of-test-execution"></a>Analysera resultaten av testkörningen

Resultaten från testkörningen lagras i RSAT. Observera att båda testerna godkändes.

![Tester som har godkänts i RSAT.](media/GER-RSAT-RSAT-Tests-Passed.png "Skärmbild av tester som har godkänts i RSAT")

Observera att resultaten av testkörningen också skickas till Azure DevOps så att du kan analysera ytterligare.

![Resultat från testkörningen i Azure DevOps.](media/GER-RSAT-DevOps-Tests-Added.png "Skärmbild av resultaten från testkörningen i Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Simulera en situation där testerna misslyckas

Det här testpaketet måste misslyckas när minst ett av genererade utdata inte matchar motsvarande baslinje. För att uppnå denna situation kan du använda den härledda versionen av **BACS (UK)** som genererar en betalningsfil med annat innehåll än motsvarande baslinje. Om du vill simulera den här situationen kan du använda samma **BACS (UK)**-format men ändra betalningsbeloppet på den bearbetade betalningsraden.

1. Öppna appen och gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.
2. Markera **rader**
3. Markera betalningsraden och välj **betalningsstatus \> ingen**.
4. I fältet **Debet**, ändra värdet från **1 000,00** till **2 000,00**.
5. Spara ändringarna genom att klicka på **Spara**.

### <a name="run-the-tests-in-rsat"></a>Kör testerna i RSAT

1. Markera de inlästa testerna i RSAT.
2. Välj **kör**.

Observera att testfall körs automatiskt i appen med hjälp av en webbläsare.

### <a name="analyze-the-results-of-test-execution"></a>Analysera resultaten av testkörningen

Resultaten från testkörningen lagras i RSAT. Observera att det andra testet misslyckades under det andra körningsförsöket.

![Misslyckade testresultat i RSAT.](media/GER-RSAT-RSAT-Tests-Failed.png "Skärmbild av misslyckade testresultaten i RSAT")

Observera att resultaten av testkörningen också skickas till Azure DevOps så att du kan analysera ytterligare.

![Misslyckade testresultat i Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed.png "Skärmbild av misslyckade testresultaten i Azure DevOps")

Du får tillgång till status för varje test. Du kan också komma åt körningsloggen så att du analyserar orsakerna till eventuella fel. I följande bild visar körningsloggen att felet uppstod på grund av skillnaden mellan den genererade betalningsfilen och dess baslinje.

![Körningslogg för analys av fel i Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Skärmbild av körningsloggen för att analysera fel i Azure DevOps")

Som du har sett kan funktionen för ett ER-format utvärderas automatiskt med hjälp av RSAT som testplattform och med hjälp av testfall som baseras på uppgiftsinspelare som använder funktionen för ER-baslinje.

## <a name="additional-resources"></a>Ytterligare resurser

- [Uppgiftsinspelarresurser](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Skapa och automatisera användaracceptanstest](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Distribuera och använd miljöer som har stöd för kontinuerlig bygg- och testautomatisering](../perf-test/continuous-build-test-automation.md)
- [Spåra genererade rapportresultat och jämför dem med baslinjevärden](er-trace-reports-compare-baseline.md)
- [ER Uppgradera ditt format genom att implementera en ny basversion för det formatet](tasks/er-upgrade-format.md)
- [ER importera en konfiguration från Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]