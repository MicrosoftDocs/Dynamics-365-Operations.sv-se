---
title: Importera data från manuellt markerade filer i batch-läge
description: I det här avsnittet beskrivs hur du importerar data från manuellt valda filer i batch-läge.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075629"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importera data från manuellt markerade filer i batch-läge

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Om du vill använda ramverket [Elektronisk rapportering (ER)](general-electronic-reporting.md) för att importera data från manuellt valda inkommande filer i batch-läge, konfigurera en ER [format](er-overview-components.md#format-component) som stöder importen. Kör sedan en [modellmappning](er-overview-components.md#model-mapping-component) av typen **Till destination** som använder det formatet som datakälla. När du importerar data bläddrar du till filen som du vill importera och välja den manuellt. 

Den nya ER-kapaciteten som stöder dataimport i batch-läge gör att denna process kan konfigureras som obevakad. Du kan använda ER-konfigurationer för att utföra dataimport genom att schemalägga ett nytt batch-jobb från ER-användargränssnittet (UI).

Det här avsnittet förklarar hur du slutför dataimport från en manuellt vald fil i batch-läge. I exemplen används leverantörstransaktioner som affärsdata. Stegen i dessa exempel kan genomföras i företaget **USMF**. Ingen kod behövs.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:

- En av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- ER-format och modellkonfigurationer för 1099-betalningar

### <a name="create-the-required-er-configurations"></a>Skapa nödvändiga ER-konfigurationer

Skapa de nödvändiga ER-konfigurationerna och skapa andra förutsättningar genom att följa ett av dessa steg:

- Spela upp uppgiftsguiden **ER data från en Microsoft Excel-fil** som är en del av affärsprocessen **7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)**. Dessa uppgiftsguider förklarar processen med hur du utformar och använder ER-konfigurationer för att interaktivt importera leverantörstransaktioner från filer i Microsoft Excel. Mer information finns i [Tolka inkommande dokument i Excel-format](parse-incoming-documents-excel.md).
- Slutför exemplen i [Konfigurera dataimport från SharePoint](er-configure-data-import-sharepoint.md). Dessa uppgiftsguider förklarar processen med hur du utformar och använder ER-konfigurationer för att interaktivt importera leverantörstransaktioner från Excel-filer som lagras i en SharePoint-mappen.

### <a name="download-the-required-er-configurations"></a>Hämta nödvändiga ER-konfigurationer

1. Hämta och lagra följande ER-konfigurationer lokalt.

    | Beskrivning av innehåll | Fil |
    |---------------------|------|
    | **1099 Betalningsmodell** ER-datamodellkonfiguration | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **Format för import av leverantörernas transaktioner (Excel)** ER-formatkonfiguration | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Använd alternativet [Läs in från XML-fil](er-defer-sequence-element.md#import-the-sample-er-configurations) ER för att importera de hämtade ER-konfigurationerna till din instans av Dynamics 365 Finance i följande ordning:

    1. Exempel på konfiguration av ER-datamodell.
    2. Konfiguration för ER-fomat

### <a name="download-the-required-excel-files"></a>Hämta de nödvändiga Excel-filerna

- Hämta följande exempel datauppsättning och spara den lokalt.

    | Beskrivning av innehåll | Fil |
    |---------------------|------|
    | Inkommande **1099import-data.xlsx**-fil som innehåller exempeldata för import | [1099import data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Granska förutsättningarna

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** granskar du den preparerade ER-lösningen för dataimport i batchläge.
3. Granska formatkonfiguration **För import av leverantörers transaktioner (Excel)**.

    - Formatkomponenten i den här konfigurationen har utformats för att parsa en inkommande Excel-fil.
    - Modellmappningskomponenten i denna konfiguration används för att fylla i basdatamodellen genom att använda data från den analyserade Excel-filen.

    ![ER-formatkonfiguration för att importera data i batch-läge från ER-användargränssnittet.](./media/er-configure-data-import-batch-configurations-1.png)

4. Granska **1099 Betalningsmodell** ER-datamodellkonfiguration.

    - Modellkomponenten i den här konfigurationen representerar strukturen för datamodellen som används för att skicka data mellan körande ER-komponenter.
    - Modellmappningskomponenten i den här konfigurationen används för att hämta data från den körda formatkomponenten och sedan uppdatera programregister.

    ![Konfiguration av ER-datamodell för att importera data i batch-läge från ER-användargränssnittet.](./media/er-configure-data-import-batch-configurations-2.png)

5. Öppna **1099import-data.xlsx**-filen i Excel.

    ![Exempel på Excel-fil med data för import i batchläge.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Aktivera batchdataimport för ER från användargränssnittet

1. Gå till **Systemadministration** \> **Arbetsytor** \> **Funktionshantering**.
2. I arbetsytan **Funktionshantering**, välj funktionen **Kör ER-import av dokument som laddats upp manuellt i batch** och välj **Aktivera nu**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importera data från manuellt valda Excel-filer

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer**, välj **1099 betalningsmodell** konfiguration av datamodell.
3. På snabbfliken **Konfigurationskomponenter** markerar du länken **För 1099 manuella transaktioner import**.
4. På sidan **Mappning av modell till datakälla** förväljs **För 1099 manuella transaktioner** modellmappning. Välj **kör**.
5. På fliken **Parametrar** väljer du **Bläddra**. Sök och välj filen **1099import-data.xlsx** och välj **OK**.
6. I **Ange verifikations-ID** anger du **V-00001**.
7. På fliken **Kör i bakgrunden** ange alternativet **Batchbearbetning** till **Ja**.

    Lägg märke till att fältet **Uppgiftsbeskrivning** är inställt på **Kör av modellmappning "För 1099 manuella transaktionsimport", konfiguration "1099 betalningsmodell"**. Det här värdet indikerar att körningen av den valda modellmappningen kommer att tidsplanerats som ett nytt batchjobb.

    ![Ange detaljer för dataimporten i batchläge i dialogrutan Parametrar för elektronisk rapport.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Välj **OK**. Ett meddelande meddelar dig om att ett nytt batchjobb har tidsplanerats.

    ![Meddelande om ett nytt tidsplanerat batchjobb på sidan Mappning av modell till datakälla.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Granska dataimportresultaten på sidan Batchjobb

1. Gå till **Vanlig** \> **Förfrågningar** \> **Batchjobb** \> **Mina batchjobb**.
2. Filtrera listan med **batchjobb** på sidan Batchjobb för att hitta den tidsplanerade batchen och välj den sedan.
3. Markera länken **jobb-ID** för att granska jobbuppgifter.
4. På snabbfliken **batchuppgifter** väljer du **Logga**.

    ![Inloggningsknappen på sidan Batchjobb.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Granska körningsinformation.

    ![Körningslogg för det tidsplanerade batchjobbet på sidan Batchjobb.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Ändra dataimportparametrarna

När batchen har tidsplanerats och den ännu inte har körts kan du ändra parametrarna för den schemalagda dataimporten.

1. Gå till **Vanlig** \> **Förfrågningar** \> **Batchjobb** \> **Mina batchjobb**.
2. Filtrera listan med **batchjobb** på sidan Batchjobb för att hitta den tidsplanerade batchen och välj den sedan.
3. Välj **Ändra status**.
4. I dialogrutan **Välj ny status**, välj **Undanhåll** och välj **OK**.
5. Markera länken **jobb-ID** för att komma åt jobbdetaljerna.
6. På snabbfliken **batchuppgifter** väljer du **parametrar**.
7. I dialogrutan **Parametrar för elektronisk rapportering** följer du dessa steg:

    1. Välj **Bläddra** för att välja den alternativa filen för dataimport.
    2. Välj **Ange verifikations-ID** för att ändra verifikationsnumret för import av leverantörstransaktioner.

        ![Ändra parametrarna för dataimporten för det tidsplanerade batchjobbet i dialogrutan Parametrar för elektronisk rapport.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Välj **OK**.

8. Kontrollera att batchen fortfarande är markerad och välj sedan **Ändra status** igen.
9. I dialogrutan **Välj ny status**, välj **Vänta** och välj **OK**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Granska dataimportresultaten på sidan ER-källa

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektronisk rapporteringskälla**.
2. Välj posten **För import av leverantörstransaktioner (Excel)** som skapats automatiskt under dataimporten.

    ![Post för konfigurationen För import av leverantörers transaktioner (Excel) på sidan Elektronisk rapporteringskälla.](./media/er-configure-data-import-batch-files-source-1.png)

3. Välj **Filtillstånd för källorna**.
4. På snabbflikarna **Filer** och **Källoggar för importformatet**, granska importuppgifterna.
5. På snabbfliken **Filer** väljer du posten. Observera att den importerade filen är kopplad till den här posten.

    ![Importerad fil som är kopplad till posten på fil tillstånden för källsidan.](./media/er-configure-data-import-batch-files-source-2.png)

6. Välj **bilagor** för att granska den importerade filen.

    ![Importerad fil på dokumentvysidan.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > För att behålla dessa bilagor använder ER-ramverket en dokumenttyp som [ställts in](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) för aktuellt företag i fältet **Andra** i ER-parametrarna.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Granska dataimportresultaten på sidan Leverantörkvittning för 1099-sida

1. Gå till **Leverantörsreskontra** \> **Periodiska uppgifter** \> **1099-skatt** \> **Leverantörskvittning för 1099-rapportering**.
2. I fältet **Från datum** anger du **12/31/2017** (31 december, 2017).
3. Välj **Manuella 1099-transaktioner**.

    ![Importerade leverantörstransaktioner på transaktionssidan 1099-skatt.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
