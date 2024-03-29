---
title: Konfigurera dataimport från SharePoint
description: Den här artikeln beskriver hur du importerar data från Microsoft SharePoint.
author: kfend
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 11208267de0cc35db55c64ccf2de224df854404d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277799"
---
# <a name="configure-data-import-from-sharepoint"></a>Konfigurera dataimport från SharePoint

[!include[banner](../includes/banner.md)]

Om du vill importera data från en inkommande fil med ramverket för elektronisk rapportering (ER) måste du konfigurera ett ER-format som stöder import och sedan köra en modellmappning av typen **Till mål** som använder det formatet som en datakälla. När du importerar data måste du gå till den fil som du vill importera. Den importerade filen kan manuellt väljas av användaren. Med den nya ER-kapaciteten för att stödja import av data från Microsoft SharePoint kan den här processen konfigureras som obevakad. Du kan använda ER-konfigurationer för att utföra dataimport från filer som är lagrade i Microsoft SharePoint-mappar. Den här artikeln beskrivs hur du slutför importen från SharePoint. I exemplen används leverantörstransaktioner som affärsdata.

## <a name="prerequisites"></a>Förutsättningar
För att slutföra exemplet i den här artikeln måste du ha följande åtkomst:

- Gå till någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till instansen på Microsoft SharePoint Server som konfigureras för användning med appen.
- ER-format och modellkonfigurationer för 1099-betalningar.

### <a name="create-required-er-configurations"></a>Skapa nödvändiga ER-konfigurationer
Spela upp uppgiftsguiden **ER data från en Microsoft Excel-fil** som är en del av affärsprocessen **7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)**. Dessa uppgiftsguider förklarar processen med hur du utformar och använder ER-konfigurationer för att interaktivt importera leverantörstransaktioner från filer i Microsoft Excel. Mer information finns i [Tolka inkommande dokument i Excel-format](parse-incoming-documents-excel.md). När du har slutfört uppgiftsguiderna har du följande inställning.

#### <a name="er-configurations"></a>ER-konfigurationer

- ER-modellkonfiguration **1099-betalningsmodell**
- ER-formatkonfiguration **Format för import av leverantörernas transaktioner från Excel**

![ER-konfigurationer för import av data från SharePoint.](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Exempel på den importerade filen för dataimport

- Excel-filen **1099import-data.xlsx** med leverantörstransaktioner som ska importeras.

![Exempel på Excel-fil för import från SharePoint.](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> Format för import av leverantörstransaktioner väljs som standardvärde för modellmappning. Därför om du kör en modellmappning av **1099-betalningsmodell** och den modellmappningen är av typen **till målet** kör modellmappningen det här formatet för att importera data från externa filer. Den använder sedan den data för att uppdatera programregister.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>Konfigurera åtkomst till SharePoint för lagring av filer
Om du vill lagra elektroniska rapportfiler på en SharePoint-plats, måste du konfigurera åtkomst till SharePoint Server-instansen som används av det aktuella företaget. I det här exemplet är USMF företaget. Instruktioner finns i [Konfigurera SharePoint-lagring](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Följ instruktionerna i [Konfigurera SharePoint-lagring](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).
2. Öppna den konfigurerade SharePoint-siten.
3. Skapa följande mappar där inkommande elektroniska rapportfiler kan lagras:

     - Filimportkälla (huvudsaklig) (exempel framgår av bilden nedan)
     - Filimportkälla (alternativ)

    ![Filimportkälla (huvudsaklig).](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Valfritt) Skapa följande mappar där inkommande filer kan lagras efter import. 

    - Arkivera arkivmapp - den här mappen är för importerade filer.
    - Mapp för filer med varning - den här mappen är för filer som importerades med en varning.
    - Mapp för filer med fel - den här mappen är för filer som misslyckades med import.

4. Gå till **Organisationsadministration > Dokumenthantering > Dokumenttyper**.
5. Skapa följande dokumenttyper att använda för att komma åt SharePoint-mappar som du har skapat. Instruktioner finns i [Konfigurera dokumenttyper](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types).

|Dokumenttyp       | Grupp              | Plats      | SharePoint-mapp      |
|--------------------|--------------------|---------------|------------------------|
|SP huvudsaklig             |Fil                |SharePoint     |Filimportkälla (huvudsaklig)|
|SP alternativ             |Fil                |SharePoint     |Filimportkälla (alternativ)|
|SP-arkiv             |Fil                |SharePoint     |Arkivera arkivmapp|
|SP-varning             |Fil                |SharePoint     |Mapp för filer med varning|
|SP-fel             |Fil                |SharePoint     |Mapp för filer med fel|

![SharePoint-inställning - ny dokumenttyp.](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Konfigurera ER källor för ER-format
1. Klicka på **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektronisk rapporteringskälla**.
2. På sidan **Elektronisk rapporteringskälla** kan du konfigurera källfilerna för dataimport genom att använda det konfigurerade ER-formatet.
3. Ange en filnamnmask så att endast filer med filtillägget .xlsx importeras. Filnamnmasken är valfri och används endast när den har definierats. Du kan endast definiera en mask för varje ER-format.
4. Ändra **Sortera filer före import** till **Sortera inte**, om det finns flera filer som ska importeras och ordningen för import inte är viktig
5. Markera alla SharePoint-mapparna som du skapade tidigare.

    [![Inställning av ER-källfiler.](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - *ER-källa* definieras för varje programföretag individuellt. Däremot delas *ER-konfigurationer* mellan flera företag.
> - När du tar bort en inställning för ER-källan för ett ER-format tas även alla kopplade fillägen bort genom bekräftelse (se nedan).

## <a name="review-the-files-states-for-the-er-format"></a>Granska filtillstånden för ER-format
1. På sidan **källa för elektronisk rapportering** väljer du **filtillstånd för källorna** för att granska innehållet i de konfigurerade filkällorna för det aktuella ER-formatet.
2. I avsnittet **filer**, granska listan med filer. Den här listan innehåller följande:

    - Källfilerna som är tillämpliga baserade på filnamn (om en filnamnmask anges), och som är redo för dataimport. För dessa filer är avsnittet **Källoggar för importformatet** är tomt.
    - Tidigare importerade filer. För var och en av dessa filer i avsnittet **Källoggar för importformatet** kan du granska historik för import av filen.

Du kan också öppna sidan **Filtillstånd för källorna** genom att välja **Organisationsadministration**\>**Elektronisk rapportering**\>**Filtillstånd för källorna**. I det här fallet innehåller sidan information om filkällor för alla ER-format som filkällorna har konfigurerats för för företaget som du är inloggad i.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importera data från Excel-filer som är i en mapp i SharePoint
1. I SharePoint överför Microsoft Excel-fil **1099import-data.xlsx** som innehåller leverantörstransaktionerna till **Filimportkälla (huvudsaklig)** SharePoint-mapp som du skapade tidigare.

    [![SharePoint-innehåll – Microsoft Excel-fil som ska importeras.](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. På sidan **Filtillstånd för källorna**, välj **Uppdatera** för att uppdatera sidan. Excel-filen som överfördes till SharePoint visades på den här sidan med statusen **Klart**. Följande statusvärden stöds för närvarande:

    - **Klar** - tilldelas automatiskt för varje ny fil i en SharePoint-mapp. Denna status innebär att filen är klar för import.
    - **Importera** - tilldelas automatiskt av en ER-rapport när filen låses av importprocessen för att förhindra dess användning av andra processer (om många av dem körs samtidigt).
    - **Importerad** - tilldelas automatiskt av en ER-rapport när filimporten är slutförd. Denna status innebär att den importerade filen har tagits bort från den konfigurerade filkällan (SharePoint-mapp).
    - **Misslyckad** - tilldelas automatiskt av en ER-rapport när filimporten är slutförd med fel eller undantag.
    - **Spärrad** - tilldelas manuellt av användaren på den här sidan. Denna status innebär att filen inte importeras just nu. Denna status kan användas för att skjuta upp importen av vissa filer.

    [![Uppdaterad ER-fil anger sida för valda källor.](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importera data från SharePoint-fil.
1. Öppnar ER-konfigurationsträdet, markera **1099-betalningsmodell** och utöka listan över ER-modellkomponenter.
2. Välj namnet på modellmappning för att öppna listan över modellmappningar av den valda ER-modellkonfigurationen.

    [![Konfigurationssida.](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Välj **kör** för att köra den valda modellmappningen. Eftersom du har konfigurerat filkällor för ER-formatet kan du ändra inställningen för **Filkälla** enligt behov. Om du sparar inställningen för det här alternativet importeras .xslx-filer från konfigurerade källor (SharePoint-mapparna, i det här exemplet).

    I det här exemplet importerar du en enstaka fil. Om det finns flera filer har de valts för import i den ordning som de lades till i SharePoint-mappen. Varje körning av ett ER-format importerar en enstaka vald fil.

    [![Importera från SharePoint och kör ER-modellmappning.](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. Modellmappningen kan köras [obevakad](#limitations) i batchläge. I detta fall importeras varje gång som en batch kör detta ER-format, en enskild fil från konfigurerade filkällor.

    När en fil har importerats från SharePoint-mappen, har den tagits bort från mappen och flyttas till mappen för importerade filer eller till mappen för importerade filer med varningar. Annars flyttas den till mappen för misslyckade filer eller stannar kvar i den här mappen om mappen för misslyckade filer inte har konfigurerats. 

5. Ange verifikations-ID som **V-00001** och välj sedan **OK**.

    [![Kör ER-modell-mappning.](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. På sidan **Filtillstånd för källorna**, välj **Uppdatera** för att uppdatera sidan.

    [![ER-fil anger sidan för källor.](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. I avsnittet **filer**, granska listan med filer. Avsnittet **Källoggar för importformatet** ger historik för Excel-filimporten. Eftersom den här filen har importerats, markeras den som **borttagen** i SharePoint-mappen.
8. Granska **Filimportkälla (huvudsaklig)** SharePoint-mapp. Excel-filerna som har importerats har tagits bort från den här mappen.
9. Välj **Leverantörsreskontra** \> **Periodiska uppgifter** \> **1099-skatt** \> **Leverantörskvittning för 1099-rapportering**.
10. I fälten **från datum** och **till datum** anger du lämpliga värden. Välj sedan **Manuella 1099-transaktioner**.

    Leverantörstransaktionerna som har importerats från Excel-filer i SharePoint för verifikation **V-00001**, visas på sidan.

    [![1099-leverantörstransaktionssida.](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Förbered en Excel-fil för import
1. Öppna Excel-filen som du använt tidigare. I rad 3, kolumn 1, lägg till en leverantörskod som inte finns i programmet. Lägg till ytterligare falsk leverantörsinformation på raden.

    [![Microsoft Excel-exempelfil för import från SharePoint.](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Skicka den uppdaterade Excel-filen som innehåller leverantörstransaktioner till SharePoint-mappen **Filimportkälla (huvudsaklig)**.
3. Öppnar ER-konfigurationsträdet, markera **1099-betalningsmodell** och utöka listan över ER-modellkomponenter.
4. Välj namnet på modellmappningen för att uppdatera modellmappningen så att den felaktiga leverantörskoden betraktas som ett fel under dataimporten.
5. Välj **Designer**.
6. På fliken **valideringar** måste du ändra åtgärd efter validering för valideringsregeln som har konfigurerats för att utvärdera om leverantörskontot som importeras finns i programmet. Uppdatera värdet för fältet **Åtgärd efter validering** till **Stoppa körning**, spara ändringarna och stäng sidan.

    [![Sidan ER-modellmappningsdesigner.](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Spara ändringarna och stäng ER-modellmappningsdesigner.
8. Välj **kör** för att köra den ändrade ER-modellmappningen.
9. Ange verifikations-ID som **V-00002** och välj sedan **OK**.

    Informationsloggen innehåller ett meddelande att det finns en fil i SharePoint-mappen som innehåller felaktigt leverantörskonto och inte kan importeras.

    [![Avslutad körning av ER-modellmappning.](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. På sidan **Filtillstånd för källorna**, välj **uppdatera**, och sedan, i avsnittet **filer** granskar du listan med filer.

    [![ER-fil anger sida för valda källor.](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   Avsnittet **Källoggar för importformatet** anger att importen har misslyckats och att filen är i SharePoint-mappen för filer med fel (kryssrutan **checkÄr borttagen** är inte markerad). Om du vill åtgärda filen i SharePoint genom att lägga till rätt leverantörskod och flytta den till SharePoint-mappen för filernas importkälla (huvudsaklig) kan du importera filen igen.

11. Välj **Leverantörsreskontra** \> **Periodiska uppgifter** \> **1099-skatt** \> **Leverantörskvittning för 1099-rapportering**, ange tillämpliga värden i fälten **Från-datum** och **Till-datum** och markera **manuella 1099-transaktioner**.

    Endast transaktioner för verifikation V-00001 är tillgängliga. Inga transaktioner för verifikation V-00002 är tillgängliga även om felet för den senaste importerade transaktionen har hittats i Excel-filen.

## <a name=""></a><a name="limitations">Begränsningar</a>

I versioner av Dynamics 365 Finance före version 10.0.25, erbjuder användargränssnittet (UI) i ER-ramverket inte möjligheten att initiera ett nytt batchjobb som kommer att köra en modellmappning för dataimport i obevakat läge. Istället måste du utveckla ny logik så att den konfigurerade ER-modellmappningen kan anropas från programmets användargränssnitt för att importera data från inkommande filer. För att den här logiken ska kunna utvecklas krävs vissa tekniska åtgärder. 

Mer information om relevant ER-API finns i [Kod för att köra formatmappning för dataimport](er-apis-app73.md#code-to-run-a-format-mapping-for-data-import) i avsnittet om [API-ändringar i ER-ramverk för Application update 7.3](er-apis-app73.md). Granska koden i klassen `BankImport_RU` för modellen `Application Suite` för att se hur din anpassade logik kan implementeras. Klassen `BankImport_RU` utökar `RunBaseBatch`-klassen. Granska i synnerhet metoden `runER()` där `ERIModelMappingDestinationRun`-objektet skapas som körning av en ER-modellmappning.

I Ekonomi version 10.0.25 och senare erbjuder ER-ramverkets gränssnitt möjligheten att initiera ett nytt batchjobb som kommer att köra en modellmappning för dataimport i obevakat läge. Mer information om den här processen finns i [Importera data i batchläge från manuellt valda filer](er-configure-data-import-batch.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Ändringar av API för ER-ramverk i Application update 7.3](er-apis-app73.md)

[Ändringar av API för ER-ramverk i Application update 10.0.23](er-apis-app10-0-23.md)

[Ändringar av API för ER-ramverk i Application update 10.0.25](er-apis-app10-0-25.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
