---
title: Spåra körningen av ER-format för att felsöka prestandaproblem
description: Den här artikeln innehåller information om hur du använder funktionen för prestandaspårning i elektronisk rapportering (ER) för att felsöka prestandaproblem.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 4ea6901f8d9632b021c35b9ee899385e688fc77e
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108869"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Spåra körning av ER-format för att felsöka prestanda problem

[!include[banner](../includes/banner.md)]

Som en del i processen att utforma konfiguration av elektronisk rapportering (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från programmet och anger den i genererad utdata. Funktionen för ER-prestationsspårning hjälper till att avsevärt minska både tid och kostnad när det gäller att samla in information om ER-formatkörning och använda den för att felsöka prestandaproblem. I den här självstudien finns riktlinjer för hur du utför prestandaspårning för körda ER-format och hur du använder informationen från dessa spårningar för att förbättra prestanda.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra exemplet i den här självstudien måste du ha följande åtkomst:

- Gå till någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till den instans av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som programmet för en av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

Du måste också hämta följande filer och lagra dem lokalt.

| Fil                                  | Innehåll                               |
|---------------------------------------|---------------------------------------|
| Prestandaspårningsmodell.version. 1     | [Konfiguration av exempel på ER-datamodell.](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Prestandaspårningsmetadata.version.1  | [Konfiguration av exempel på ER-metadata.](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Prestandaspårningsmappning.version.1.1 | [Konfiguration av exempel på ER-modellmappning](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Prestandaspårningsformat.version.1.1  | [Konfiguration av exempel på ER-format.](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>Konfigurera ER-parametrar

Varje ER-prestandaspårning som skapas i programmet lagras som en bilaga till körningsloggposten. Dokumenthanteringsramverket (DM) används för att hantera dessa bilagor. Du måste konfigurera återställningsparametrar i förväg för att kunna ange vilken typ av DM-dokument som ska användas för att koppla prestandaspårningar. På arbetsytan **Elektronisk rprogramortering** väljer du **Elektroniska rprogramorteringsparametrar**. Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.

![Sida för parametrar för elektronisk rapportering.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):

- **Klass:** Bifoga fil
- **Grupp:** fil

![Sida för dokumenttyper.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> Den valda dokumenttypen måste vara tillgänglig i alla företag i den aktuella instansen eftersom DM-bilagor är företagsspecifika.

### <a name="configure-rcs-parameters"></a>Konfigurera RCS-parametrar

ER-prestandaspårningar som skapas importeras till RCS för analys med hjälp av ER-formatdesigner och ER-mappningsdesigner. Eftersom ER-prestandaspårning lagras som bilagor till körningsloggposten som är relaterad till ER-formatet, måste du konfigurera RCS-parametrar i förväg för att ange den DM-dokumenttyp som ska användas för att koppla prestandaspårningar. elektronisk I instansen av RCS som har etablerats för ditt företag, i arbetsytan **elektronisk rapportering** väljer du **elektronisk rapportering**. Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.

![Sida för parametrar för elektronisk rapportering i RCS.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):

- **Klass:** Bifoga fil
- **Grupp:** fil

## <a name="design-an-er-solution"></a>Designa en ER-lösning

Anta att du har börjat designa en ny ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner. För närvarande kan du hitta transaktionerna för en vald leverantör på sidan **leverantörstransaktioner** (gå till **leverantörsreskontra\> leverantörer \> alla leverantörer**, välj en leverantörer och sedan i åtgärdspanelen på fliken **leverantörer** i gruppen **transaktioner** väljer du **transaktioner**). Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format. Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, metadata, modellmappning och formatkomponenter.

1. Logga in på den instans av RCS som har etablerats för ditt företag.
2. I den här självstudien ska du skapa och ändra konfigurationer för exempelföretaget **Litware, Inc**. Kontrollera därför att denna konfigurationsleverantör har lagts till i RCS och valts som aktiv. Instruktioner finns i proceduren [skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
4. På sidan **konfigurationer** importerar du de ER-konfigurationer som du hämtade som en förutsättning i RCS i följande ordning: datamodell, metadata, modellmappning, format. Följ dessa steg för varje konfiguration:

    1. På Åtgärdsfönster väljer du **växla \> läs in från XML-fil**.
    2. Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.
    3. Välj **OK**.

    ![Sidan Konfigurationer i RCS.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Kör ER-lösning för att spåra körning

Anta att du har skapat den första versionen av ER-lösningen. Du vill nu testa instansen och analysera körningsprestanda.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importera en ER-konfiguration från RCS till Ekonomi och drift

1. Logga in på app-instansen.
2. För den här självstudien ska du importera konfigurationer från din RCS-instans (där du utformar dina ER-komponenter) instansen (där du testar och slutligen använder dem.) Därför måste du se till att alla nödvändiga artefakter har förberetts. För mer information, se proceduren [Importera e-rapporteringskonfigurationer från Regulatory Configuration Services (RCS)](rcs-download-configurations.md).
3. Följ dessa steg för att importera konfigurationerna från RCS till programmet:

    1. I arbetsytan **elektronisk rapportering** på panelen för konfigurationsleverantören **Litware, Inc.** väljer du **Databaser**.
    2. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **RCS**-typ och väljer sedan **Öppna**.
    3. På snabbfliken **konfigurationer** väljer du konfigurationen **Prestandaspårningsformat**.
    4. I snabbfliken **Versioner** väljer du version **1.1.** för vald konfiguration och sedan **Importera**.

    ![Sidan Konfigurationsdatabas.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Motsvarande versioner av datamodell- och modellmappningskonfigurationer importeras automatiskt som förutsättningar för den importerade ER-formatkonfigurationen.

### <a name="turn-on-the-er-performance-trace"></a>Aktivera ER-prestandaspårning

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** i avsnittet **körningsspårning** gör fäljande steg:

    1. Du använder fältet **körningsspårningsformat** om du vill ange formatet för den genererade prestandaspårning som körningsinformationen lagras i för ER-format och mappningselement.

        - **Felsökningsspårningsformat** – Välj det här värdet om du planerar att interaktivt köra ett ER-format som har en kort körningstid. En samling detaljer om körningen av ER-formatet startas sedan. När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:

            - Kör varje datakälla i modellmappningen som anropas för att hämta data
            - Behandla varje formatobjekt för att ange data i de utdata som genereras

            Om du väljer värdet **Felsökningsspårningsformat** kan du analysera innehållet i spårningen i ER-åtgärdsdesigner. Där kan du visa ER-formatet eller mappningselementen som nämns i spårningen.

        - **Sammansatt spårningsformat** – Välj det här värdet om du planerar att köra ett ER-format som har en lång körningstid i batchläge. En samling sammanlagda detaljer om körningen av ER-formatet startas sedan. När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:

            - Kör varje datakälla i modellmappningen som anropas för att hämta data
            - Kör varje datakälla i formatmappningen som anropas för att hämta data
            - Behandla varje formatobjekt för att ange data i de utdata som genereras

            Värdet **Sammansatt spårningsformat** finns tillgängligt i Microsoft Dynamics 365 Finance version 10.0.20 och senare.

            I ER-formatdesignern för ER modellmappningsdesignern kan du visa den totala körningstiden för en enskild komponent. Spårningen innehåller även information om körningen, t.ex. antalet körningar samt den minsta och maximala tiden för en enda körning.

            > [!NOTE]
            > Spårningen samlas in utifrån den spårade komponentsökvägen. Statistiken kan därför bli felaktig när en enskild överordnad komponent innehåller flera icke-underordnade komponenter, eller när flera underordnade komponenter har samma namn.

    2. Ange följande alternativ till **ja** för att samla in specifik information om körningen av komponenterna ER-modellmappning och ER-format:

        - **Samla in frestatistik** – när det här alternativet är aktiverat samlar prestandaspårningen in följande information:

            - Antalet databasanrop som har gjorts av datakällor
            - Antalet dubblettanrop till databasen.
            - Information om SQL-satserna som användes för att göra databasanrop

        - **Spåra åtkomst av cachelagring** – när det här alternativet är aktiverat samlar prestandaspårningen in information om vad som gäller för ER-modell mappningens cache-användning.
        - **Spåra dataåtkomst** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet anrop till databasen för körda datakällor av postlisttypen.
        - **Spåra listuppräkning** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet poster som begärs från datakällor av postlisttypen.

    > [!NOTE]
    > Parametrarna i dialogrutan **användarparametrar** är specifika för användaren och det aktuella företaget.

    ![Dialogrutan Användarparametrar.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Kör ER-format

1. Välj företaget **DEMF**.
2. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
3. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsformat**.
4. Klicka på **Kör** i åtgärdsfönstret.

Observera att filen som genereras visar information om 265 transaktioner för sex leverantörer.

## <a name="review-the-execution-trace"></a>Granska körningsspårningen

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Exportera den genererade spårningen från programmet

Prestandaspårningen kopplas från källans ER-format och kan serialiseras till en extern ZIP-fil.

1. Gå till **Organisationsadministration \> Elektronisk rapportering \> Konfiguration av felsökningsloggar**.
2. På sidan **elektronisk rapportering kör loggar** i det vänstra fönstret i **konfigurationsnamn** väljer du **prestandaspårningsformat** i för att hitta de loggposter som har genererats vid körning av konfigurationen **Prestandaspårningsformat**.
3. Välj knappen **Bilagor** (gemsymbolen) längst upp till höger på sidan eller tryck på **Ctrl+Shift+A**.

    ![Knappen Bilagor på sidan förkörningsloggar för elektronisk rapportering.](./media/GER-PerfTrace-GER-DebugLog.png)

4. På sidan **bilagor för elektroniska rapportering körningsloggar** i åtgärdsfönstret väljer du **öppna** för att få prestandaspårningen som en zip-fil och spara den lokalt.

    ![Bilagor för körningsloggar för elektronisk rapportering.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> Spårningen som genereras har en referens till källans ER-rapport via en unik rapportidentifierare i **GUID**-format. Versionsnumret för formatet beaktas inte.

Observera att associationen mellan resultatspårningen som har genererats för det körda ER-formatet och ER-modellmappningen baseras på den rotbeskrivare som användes och den gemensamma datamodellen. Versionsnumret för formatet ochmmdellmappning beaktas inte. Inställningen av flaggan **Standard för modellmappning** för modellmappningen beaktas inte heller.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importera genererad spårning till RCS.

1. I RCS på arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
2. På sidan **konfigurationer** i konfigurationsträdet, expandera artikeln **Prestandaspårningsmodell** och väljer artikeln **Prestandaspårningsformat**.
3. Klicka på **Designer** i åtgärdsfönstret.
4. På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
5. I dialogrutan **Inställning av prestandaspårningsresultat** väljer du **Importera prestandaspårning**.
6. Välj **bläddra** för att markera den zip-fil som du exporterade tidigare.
7. Välj **OK**.

    ![Dialogrutan inställningar av prestandaspårningsresultat i RCS.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Använd prestandaspårning för analys i RCS – formatkörning

1. I RCS, på sidan **Formatdesigner** välj **Visa/Dölj** för att expandera innehållet i alla formatobjekt.

    Lägg märke till att ytterligare information visas för vissa artiklar i det aktuella formatet:

    - Den faktiska tid som användes för att mata in data i det genererade utmatninget med hjälp av formaobjekt
    - Samma tid uttryckt i procent av den totala tid som användes för att generera hela utdata

    ![Formatdesignersida i RCS.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Stäng sidan **Formatdesigner**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Använd prestandaspårning för analys i RCS – modellmappning

1. I RCS på sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsmappning**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. Välj **Designer**.
4. På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
5. Välj spårningen som du importerade tidigare.
6. Välj **OK**.

Lägg märke till att ny information blir tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:

- Den faktiska tid som användes för att hämta data genom att använda datakällan
- Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen

Observera att du informerar dig om att den aktuella modellmappningen duplicerar databas begäranden när datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum körs. Den här dubbletten sker eftersom listan med leverantörstransaktioner anropas två gånger för varje förslagen leverantörspost:

- Ett anrop görs för att ange information om varje transaktion i datamodellen, baserat på konfigurerade bindningar.
- Ett samtal görs för att ange det beräknade antalet transaktioner per leverantör i datamodellen.

![Meddelande om dubbla databasbegäranden på sidan Modellmappningsdesigner i RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

Värdet **\[Q:530\]** anger att VendTrans-registret har anropats 530 gånger för att returnera en post från registret till datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Värdet **\[530\]** anger att datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum har anropats 530 gånger för att returnera en post från den datakällan och ange informationen från den i datamodellen.

Vi rekommenderar att du använder cache för datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum för att minska antalet anrop som görs för att få information om 265-transaktioner och förbättra modellmappningens prestanda.

Det kan också vara användbart om du vill minska antalet anrop som görs till datakällan LedgerTransTypeList. Denna datakälla används för att koppla varje värde i **LedgerTransType**-uppräkningen till dess etikett. Genom att använda den här datakällan kan du hitta en lämplig etikett och ange den i datamodellen för varje leverantörstransaktion. Det aktuella antalet anrop till den här datakällan (9 027) är ganska högt för 265 transaktioner.

![Sidan Modellmappningsdesigner i RCS som visar 9 027 anrop till datakällan.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Förbättra modellmappningen utifrån information från körningsspårningen

### <a name="modify-the-logic-of-the-model-mapping"></a>Ändra logiken för modellmappningen

1. Gör så här om du vill använda cache för att förhindra att anrop till databasen dupliceras:

    1. I RCS, på sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du objektet **VendTable**.
    2. Välj **cache**.
    3. Expandera objektet **VendTable**  expandera listan med 1:n-relationer för VendTable-datakälla (**\<Relationer** objekt) och välj objektet **VendTrans.VendTable\_AccountNum**.
    4. Välj **cache**.

    ![Cachelagringskonfiguration för att förhindra dubbla anrop.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Följ dessa steg för att hämta datakällan LedgerTransTypeList till omfattningen för datakällan VendTable:

    1. I fönstret **datakälltyper** expanderar du objektet **funktioner** och markerar objektet **beräknade fält**.
    2. Markera objektet **VendTable** i fönstret **datakällor**.
    3. Markera **Lägg till**.
    4. Skriv **\$TransType** i fältet **Namn**.
    5. Välj **Redigera recept**.
    6. I fältet **Recept** ange **LedgerTransTypeList**.
    7. Välj **Spara**.
    8. Stäng sidan **receptredigering**.
    9. Klicka på **OK**.

3. Gör följande om du vill göra cachelagring av fältet **\$TransType**:

    1. Välj bjektet **LedgerTransTypeList**.
    2. Välj **cache**.
    3. Välj objektet **VendTable.\$TransType**.
    4. Välj **cache**.

    ![Cachelagra konfiguration för fältet $TransType.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Följ dessa steg för att ändra **\$TransTypeRecord** så att det börjar använda cachelagrade fältet **\$TransType**:

    1. I fönstret **Datakällor**, expandera objektet **VendTable** expandera objektet **\<Relations** expandera objektet **VendTrans.VendTable\_AccountNum** och välj sedan  **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Välj **Redigera**.
    3. Välj **Redigera recept**.
    4. I fältet **formel** hittar du följande uttryck:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. I fältet **formel** anger du följande uttryck:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Välj **Spara**.
    7. Stäng sidan **receptredigering**.
    8. Välj **OK**.

5. Välj **Spara**.
6. Stäng sidan **modellmappningsdesigner**.
7. Stäng sidan **modellmappningar**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Slutför den ändrade versionen av ER-modellmappningen

1. I RCS, på sidan **Konfigurationer** på snabbfliken **Versioner** FastTab, välj version **1.2** av konfigurationen **prestandaspårningsmappning**.
2. Välj **Ändra status**.
3. Välj **Slutför**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importera den modifierade ER-modellmappningskonfigurationen från RCS till programmet

Upprepa stegen i avsnittet [Importera en ER-konfiguration från RCS till Ekonomi och drift](#import-configuration) tidigare i den här artikeln om du vill importera version 1.2 av konfigurationen **Mappning av prestandaspårning**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Kör modifierad ER-lösning för att spåra körning

### <a name="run-the-er-format"></a>Kör ER-format

Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i den här artikeln om du vill generera en ny prestandaspårning.

## <a name="work-with-the-execution-trace"></a>Arbeta med körningsspårningen

### <a name="export-the-generated-trace-from-the-application"></a>Exportera den genererade spårningen från programmet

Upprepa stegen i avsnittet [exportera den genererade spårningen från programmet](#export-trace) tidigare i den här artikeln om du vill spara en ny prestandaspårning lokalt.

### <a name="import-the-generated-trace-into-rcs"></a>Importera genererad spårning till RCS.

Upprepa stegen i avsnittet [importera den genererade spårningen till RCS](#import-trace) tidigare i den här artikeln om du vill importera den nya prestandaspårningen till RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Använd prestandaspårning för analys i RCS – modellmappning

Upprepa stegen i avsnittet [Använd prestandaspårning för analys i RCS – modellmappning](#use-trace) tidigare i den här artikeln om du vill analysera den senaste prestandaspårningen.

Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen. Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats. Därför har hela ER-lösningens prestanda förbättrats.

![Spårningsinformation för datamodellen VendTable på sidan för modellmappningsdesigner i RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

I spårningsinformationen indikerar värdet **\[12\]** för VendTable-datakällan att denna datakälla har anropats 12 gånger. Värdet **\[Q:6\]** anger att sex anrop översattes till databasanrop till VendTable-registret. Värdet **\[C:6\]** indikerar att posterna som hämtades från databasen cachelagrades, och sex andra anrop bearbetades med hjälp av cachen.

Observera att antalet anrop till datakällan LedgerTransTypeList har minskats från 9 027 till 240.

![Spårningsinformation för datamodellen LedgerTransTypeList på sidan för modellmappningsdesigner i RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Granska körningsspårningen i programmet

Förutom RCS kan vissa versioner erbjuda funktioner för en ER-ramverk designerupplevelse. Dessa versioner har alternativet **aktivera designläge** som kan aktiveras. Du hittar det här alternativet på fliken **Allmänt** på sidan **parametrar elektronisk rapportering** som du öppnar från arbetsytan **elektronisk rapportering**.

![Aktivera alternativet för designläge på sidan parametrar för elektronisk rapportering.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Om du använder någon av dessa versioner kan du analysera detaljerna för genererade resultat spårningar direkt i programmet. Du behöver inte exportera dem från programmet och importera dem till RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Granska körningsspårningen med hjälp av externa verktyg

### <a name="configure-user-parameters"></a>Konfigurera användarparametrar

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** i fältet **Körnngsspårningsformat**, välj **PerfView XML**.

### <a name="run-the-er-format"></a>Kör ER-format

Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i den här artikeln om du vill generera en ny prestandaspårning.

Observera att en zip-fil kan hämtas i webbläsaren. Den här filen innehåller prestandaspårningen i PerfView-format. Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning.

![Information om prestandaspårning i PerfView-format.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Använd externa verktyg för att granska en körningsspårning som omfattar databasfrågor

På grund av de förbättringar som har gjorts i ER-ramverk innehåller den prestandaspårning som genereras i PerfView-format fler detaljer om ER-formatkörning. I Microsoft Dynamics 365 Finance version 10.0.4 (juli 2019) kan den här spårningen även innehålla information om utförda SQL-frågor till programdatabasen.

### <a name="configure-user-parameters"></a>Konfigurera användarparametrar

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** i avsnittet **körningsspårning** ange följande parametrar:

    - I fältet **körningsspårningsformat**, välj **PerfView XML**.
    - Ställ in alternativet **Samla in frågestatistik** till **Ja**.
    - Ställ in alternativet **Spårningsfråga** till **Ja**.

    ![Avsnitt för körningsspårning, dialogrutan Användarparametrar.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Kör ER-format

Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i den här artikeln om du vill generera en ny prestandaspårning.

Observera att en zip-fil kan hämtas i webbläsaren. Den här filen innehåller prestandaspårningen i PerfView-format. Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning. I den här spårningen finns nu information om åtkomst till SQL-databasen under körningen av ER-formatet.

![Spårningsinformation för det körda ER-formatet i PerfView.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

