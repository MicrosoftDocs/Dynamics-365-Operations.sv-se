---
title: "Konfigurera dataimporten från SharePoint"
description: "Det här avsnittet beskriver hur du importerar data från Microsoft SharePoint."
author: NickSelin
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 4285db9c71208bce45d64933e692a25ef3f46b26
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="configure-data-import-from-sharepoint"></a>Konfigurera dataimporten från SharePoint

[!include[banner](../includes/banner.md)]

Om du vill importera data från en inkommande fil med ramverket för elektronisk rapportering (ER) måste du konfigurera ett ER-format som stöder import och sedan köra en modellmappning av typen **Till mål** som använder det formatet som en datakälla. När du importerar data måste du gå till den fil som du vill importera. Den importerade filen kan manuellt väljas av användaren. Med den nya ER-kapaciteten för att stödja import av data från Microsoft SharePoint kan den här processen konfigureras som obevakad. Du kan använda ER-konfigurationer för att utföra dataimport från filer som är lagrade i Microsoft SharePoint-mappar. Det här avsnittet beskriver hur du slutför importen från SharePoint till Microsoft Dynamics 365 for Finance and Operations. I exemplen används leverantörstransaktioner som affärsdata.

## <a name="prerequisites"></a>Krav
För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:

- Gå till Finance and Operation för någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till instansen på Microsoft SharePoint Server som konfigureras för användning med Finance and Operations.
- ER-format och modellkonfigurationer för 1099-betalningar

### <a name="create-required-er-configurations"></a>Skapa nödvändiga ER-konfigurationer
Spela upp uppgiftsguiden **ER data från Microsoft Excel-fil** som ingår i affärsprocessen **7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)**. Dessa uppgiftsguider förklarar processen med hur du utformar och använder ER-konfigurationer för att interaktivt importera leverantörstransaktioner från externa filer i Microsoft Excel. Mer information finns i [Tolka inkommande dokument i Microsoft Excel](parse-incoming-documents-excel.md). Slutligen kommer du att ha:

- ER-konfigurationer:

    - ER-modellkonfiguration **1099-betalningsmodell**
    - ER-formatkonfiguration **Format för import av leverantörernas transaktioner från Excel**

[![ER-konfigurationer för import av data från SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)](./media/GERImportFromSharePoint-01-Configurations.PNG)

- Exempel på den importerade filen för dataimport:

    - Excel-filen **1099import-data.xlsx** med leverantörstransaktioner som ska importeras till Finance and Operations

[![Exempelfilen i Microsoft Excel för att importera från SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)](./media/GERImportFromSharePoint-02-Excel.PNG)

> [!NOTE]
> Format för import av leverantörstransaktioner väljs som standardvärde för modellmappning. Därför om du kör en modellmappning av **1099-betalningsmodell** och den modellmappningen är av typen **till målet** kör modellmappningen det här formatet för att importera data från externa filer. Den använder sedan den data för att uppdatera programregister.

## <a name="configure-document-management-parameters"></a>Konfigurera dokumenthanteringsparametrar
1. På sidan **Dokumenthanteringsparametrar** konfigurerar du åtkomst till den SharePoint Server-instans som ska användas av det företag som du för närvarande är inloggad på. I det här exemplet är USMF företaget.
2. Testa anslutningen till SharePoint Server-instansen för att kontrollera att du har åtkomst.

[![Dokumenthanteringsinställningar - SharePoint server](./media/GERImportFromSharePoint-03-SharePointSetup.png)](./media/GERImportFromSharePoint-03-SharePointSetup.png)

3. Öppna den konfigurerade SharePoint-webbplatsen och skapa följande mappar där inkommande filer kan lagras:

    - Filimportkälla (huvudsaklig)
    - Filimportkälla (alternativ)

[![Dokumenthanteringsinställningar - SharePoint server](./media/GERImportFromSharePoint-04-SharePointFolder1.png)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

[![Dokumenthanteringsinställningar - SharePoint server](./media/GERImportFromSharePoint-05-SharePointFolder2.png)](./media/GERImportFromSharePoint-05-SharePointFolder2.png)

4. I Finance and Operations, på sidan **Dokumenttyper** skapar du följande dokumenttyper som kommer att användas för åtkomst till de SharePoint-mappar som du precis skapade:

    - SP huvudsaklig
    - SP alternativ

5. För skapade dokumenttyper, i fältet **grupp** anger du **fil** och i fältet **plats** anger du **SharePoint**. Ange sedan adressen till SharePoint-mappen:

    - För dokumenttyp **SP huvudsaklig**: filimportkälla (huvudsaklig)
    - För dokumenttyp **SP alternativ**: filimportkälla (alternativ)

[![SharePoint-inställning - ny dokumenttyp](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Konfigurera ER källor för ER-format
1. Klicka på **Organisationsadministration** > **Elektronisk rapportering** > **Elektronisk rapporteringskälla**.
2. På sidan **Elektronisk rapporteringskälla** kan du konfigurera källfilerna för dataimport genom att använda det konfigurerade ER-formatet.
3. Ange en filnamnmask så att endast filer med filtillägget .xlsx importeras. Filnamnmasken är valfri och används endast när den har definierats. Du kan endast definiera en mask för varje ER-format.
4. Markera båda SharePoint-mapparna som du skapade tidigare.

[![Inställning av ER-källfiler](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
>*ER-källa* definieras för varje programföretag individuellt. Däremot delas *ER-konfigurationer* mellan flera företag.

> [!NOTE]
> När du tar bort en inställning för ER-källan för ett ER-format tas även alla kopplade fillägen bort (se nedan).

## <a name="review-the-files-states-for-the-er-format"></a>Granska filtillstånden för ER-format
1. På sidan **källa för elektronisk rapportering** väljer du **filtillstånd för källorna** för att granska innehållet i de konfigurerade filkällorna för det aktuella ER-formatet.
2. I avsnittet **filer**, granska listan med filer. Den här listan innehåller följande:

    - Källfilerna som är tillämpliga baserade på filnamn (om en filnamnmask anges), och som är redo för dataimport. För dessa filer är avsnittet **Källoggar för importformatet** är tomt.
    - Tidigare importerade filer. För var och en av dessa filer i avsnittet **Källoggar för importformatet** kan du granska historik för import av filen.

Du kan också öppna sidan **Filtillstånd för källorna** genom att välja **Organisationsadministration**\>**Elektronisk rapportering**\>**Filtillstånd för källorna**. I det här fallet innehåller sidan information om filkällor för alla ER-format som filkällorna har konfigurerats för för företaget som du är inloggad i.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importera data från Excel-filer som är i en mapp i SharePoint
1. I SharePoint, överför Microsoft Excel-filen **1099import-data.xlsx** som innehåller leverantörstransaktionerna till **Filimportkälla (huvudsaklig)** SharePoint-mapp som du skapade tidigare.

[![SharePoint innehåll - Microsoft Excel-fil för import](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. I Finance and Operations på sidan **Filtillstånd för källorna**, välj **Uppdatera**för att uppdatera sidan. Observera att Excel-filen som överfördes till SharePoint visades i det här formuläret med statusen **klar**. Följande statusvärden stöds för närvarande:

    - **Klar** - tilldelas automatiskt för varje ny fil i en SharePoint-mapp. Denna status innebär att filen är klar för import.
    - **Importera** - tilldelas automatiskt av en ER-rapport när filen låses av importprocessen för att förhindra dess användning av andra processer (om många av dem körs samtidigt).
    - **Importerad** - tilldelas automatiskt av en ER-rapport när filimporten är slutförd. Denna status innebär att den importerade filen har tagits bort från den konfigurerade filkällan (SharePoint-mapp).
    - **Misslyckad** - tilldelas automatiskt av en ER-rapport när filimporten är slutförd med fel eller undantag.
    - **Spärrad** - tilldelas manuellt av användaren i formuläret. Denna status innebär att filen inte importeras just nu. Denna status kan användas för att skjuta upp importen av vissa filer.

[![ER-fil anger sidan för valda källor](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importera data från SharePoint-filer
1. Öppnar ER-konfigurationsträdet, markera **1099-betalningsmodell** och utöka listan över ER-modellkomponenter.
2. Välj namnet på modellmappning för att öppna listan över modellmappningar av den valda ER-modellkonfigurationen.

[![ER-fil anger sidan för valda källor](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Välj **kör** för att köra den valda modellmappningen. Eftersom du har konfigurerat filkällor för ER-formatet kan du ändra inställningen för **Filkälla** enligt behov. Om du sparar inställningen för det här alternativet importeras .xslx-filer från konfigurerade källor (SharePoint-mapparna, i det här exemplet).

    I det här exemplet importerar du en enstaka fil. Om det finns flera filer har de valts för import i den ordning som de lades till i SharePoint-mappen. Varje körning av ett ER-format importerar en enstaka vald fil.

[![Kör ER-modell-mappning](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. Modellmappningen kan köras automatiskt i batchläge. I detta fall importeras varje gång som en batch kör detta ER-format, en enskild fil från konfigurerade filkällor. Använd följande kod för att implementera den här batchkörningen.

    ```
    ERObjectsFactory::createMappingDestinationRunByImportFormatMappingId().run()
    ```

    När en fil har importerats från SharePoint-mappen raderas den från den mappen.

5. Ange verifikations-ID som **V-00001** och välj sedan **OK**.

[![Kör ER-modell-mappning](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. På sidan **Filtillstånd för källorna**, välj **Uppdatera**för att uppdatera sidan.

[![ER-fil anger sidan för valda källor](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. I avsnittet **filer**, granska listan med filer. Avsnittet **Källoggar för importformatet** ger historik för Excel-filimporten. Eftersom den här filen har importerats, markeras den som **borttagen** i SharePoint-mappen.
8. Granska SharePoint-mappen **Filimportkälla (huvudsaklig)**. Excel-filerna som har importerats har tagits bort från den här mappen.
9. I Finance and Operations, välj **Leverantörsreskontra**\>**Periodiska uppgifter**\>**1099-skatt**\>**Leverantörskvittning för 1099-rapportering**.
10. I fälten **från datum** och **till datum** anger du lämpliga värden. Välj sedan **Manuella 1099-transaktioner**.

    Leverantörstransaktionerna som har importerats från Excel-filer i SharePoint för verifikation **V-00001**, visas på sidan.

[![1099 leverantörstransaktionssida](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Förbered en Excel-fil för import
1. Öppna Excel-filen som du använt tidigare. I rad 3, kolumn 1, lägg till en leverantörskod som inte finns i programmet. Lägg till ytterligare falsk leverantörsinformation på raden.

[![Exempelfilen i Microsoft Excel för att importera från SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Skicka den uppdaterade Excel-filen som innehåller leverantörstransaktioner till SharePoint-mappen **Filimportkälla (huvudsaklig)**.
3. I Finance and Operations, öppna ER-konfigurationsträdet, markera **1099-betalningsmodell** och utöka listan över ER-modellkomponenter.
4. Välj namnet på modellmappningen för att uppdatera modellmappningen så att den felaktiga leverantörskoden betraktas som ett fel under dataimporten.
5. Välj **Designer**.
6. På fliken **valideringar** måste du ändra åtgärd efter validering för valideringsregeln som har konfigurerats för att utvärdera om leverantörskontot som importeras finns i programmet. Uppdatera värdet för fältet **Åtgärd efter validering** till **Stoppa körning**, spara ändringarna och stäng sidan.

[![Sidan ER-modellmappningsdesigner](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Spara ändringarna och stäng ER-modellmappningsdesigner.
8. Välj **kör** för att köra den ändrade ER-modellmappningen.
9. Ange verifikations-ID som **V-00002** och välj sedan **OK**.

    Observera att informationsloggen innehåller meddelandet som informerar som finns i SharePoint-mappfil innehåller felaktigt leverantörskonto och inte kan importeras.

[![Kör ER-modell-mappning](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. På sidan **Filtillstånd för källorna**, välj **uppdatera**, och sedan, i avsnittet **filer** granskar du listan med filer.

[![ER-fil anger sidan för valda källor](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

Avsnittet **Källoggar för importformatet** anger att importen har misslyckats och att filen fortfarande är i SharePoint-mappen (kryssrutan **Är borttagen** är inte markerad). Om du åtgärdar filen i SharePoint genom att lägga till rätt leverantörskod och ändrar status för en fil från **misslyckad** till **klar** i avsnittet **Källoggar för importformatet** kan du importera filen igen.

11. Granska SharePoint-mappen **Filimportkälla (huvudsaklig)**. Observera att Excel-filen som inte importeras fortfarande är i den här mappen.
12. I Finance and Operations, välj **Leverantörsreskontra**\>**Periodiska uppgifter**\>**1099-skatt**\>**Leverantörskvittning för 1099-rapportering**, ange tillämpliga värden i **Från-datum** och **Till-datum** och markera **manuell 1099-transaktioner**.

    Endast transaktioner för verifikation V-00001 är tillgängliga. Inga transaktioner för verifikation V-00002 är tillgängliga även om felet för den senaste importerade transaktionen har hittats i Excel-filen.

