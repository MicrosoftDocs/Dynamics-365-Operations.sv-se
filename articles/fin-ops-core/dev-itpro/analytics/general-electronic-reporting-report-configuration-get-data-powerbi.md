---
title: Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI
description: I den här artikeln beskrivs hur du kan använda konfigurationen för Elektronisk rapportering (ER) om du vill ordna överföringen av data från till Power BI-tjänster.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: be0e79bb767a8bd2db4c02dc2b73bfbc5cb95675
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281735"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du kan använda konfigurationen för Elektronisk rapportering (ER) om du vill ordna överföringen av data från till Power BI-tjänster. Som exempel använder den här artikeln Intrastat-transaktioner som affärsdata som ska överföras. Power BI-kartvisualiseringen använder dessa Intrastat-transaktionsdata för att presentera en vy för analys av företagsimport-/exportaktiviteter på Power BI-rapporten.

## <a name="overview"></a>Översikt

Microsoft Power BI är en samling programtjänster, appar och kopplingar som samverkar för att omvandla externa källor av data till sammanhängande, visuellt integrerande och interaktiva resultat. Elektronisk rapportering (ER) låter användare av enkelt konfigurera datakällor och arrangera överföring från data från appen till Power BI. Data överförs som filer i formatet OpenXML-kalkylbladet (Microsoft Excel arbetsboksfilen). De överförda filerna lagras i en Microsoft SharePoint Server som har konfigurerats för det syftet. De lagrade filerna används i Power BI för att göra rapporter som inkluderar visualiseringar (tabeller, diagram, kartor, etc). Power BI-rapporter delas med Power BI-användare och de finns i Power BI-instrumentpaneler och på appsidorna. Den här artikeln förklarar följande uppgifter:

- Konfigurera Microsoft Dynamics 365 Finance.
- Förbered din ER-formatkonfiguration för att hämta data från Finance-appen.
- Konfigurera ER-miljön för överföring av data till Power BI.
- Använd överförda data om du vill skapa en Power BI-rapport.
- Gör Power BI-rapporten tillgänglig i Finance.

## <a name="prerequisites"></a>Förutsättningar
För att slutföra exemplet i den här artikeln måste du ha följande åtkomst:

- Tillgång för en av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till SharePoint Server som konfigureras för användning med appen.
- Åtkomsten till den Power BI ramverk

## <a name="configure-document-management-parameters"></a>Konfigurera dokumenthanteringsparametrar
1. På sidan **Dokumenthanteringsparametrar** konfigurerar du åtkomst till den SharePoint Server som ska användas i det företag som du loggat in på (DEMF-företaget i det här exemplet).
2. Testa anslutningen till SharePoint Server för att kontrollera att du har åtkomst.

    [![Sidan Dokumenthanteringsparametrar.](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. Öppna den konfigurerade SharePoint-siten. Skapa en ny mapp där ER ska lagra Excel-filer som har den affärsdata som Power BI-rapporterna kräver som källa för Power BI-datauppsättningar.
4. På sidan **Dokumenttyper** skapar du en ny dokumenttyp som kommer att användas för åtkomst till den SharePoint-mapp som du precis skapade. Ange **Fil** i **Grupp** och **SharePoint** i **Plats** och sedan ange adressen för SharePoint-mappen.

    [![Sida för dokumenttyper.](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Konfigurera ER-parametrar
1. På arbetsytan **Elektronisk rapportering** klickar du på länken **Elektroniska rapporteringsparametrar**.
2. På fliken **Bilagor** väljer du dokumenttypen **Fil** för alla fälten.
3. På arbetsytan **Elektronisk rapportering** gör du önskad leverantör aktiv genom att klicka på **Ställ in aktiv**. För mer information kan du spela upp uppgiftsguiden **ER Välja tjänsteleverantör**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Använd en ER-datamodell som källa för data
Du måste ha en ER-datamodell som källa för affärsdata som ska användas för Power BI-rapporter. Den här datamodellen överförs från ER-konfigurationens databas. For more information, see [Hämta Konfigurationer för elektronisk rapportering för Lifecycle Services](download-electronic-reporting-configuration-lcs.md) eller spela upp uppgiftsguiden **ER importera en konfiguration från Lifecycle Services**. Välj **Intrastat** som datamodellen som ska överföras från den valda ER-konfigurationens databas. (I det här exemplet används version 1 av modellen.) Du kan använda den **Intrastat** ER modellkonfiguration på **konfigurationer** sidan.

[![Intrastatkonfiguration för ER-modell på sidan Konfigurationer.](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Designa en konfiguration för ER-format
Du måste skapa en ny konfiguration för ER-format som använder datamodellen **Intrastat** som källa för affärsdata. Den här formatkonfigurationen måste skapa utdataresultat som elektroniska dokument i OpenXML-format (Excel-fil). För mer information kan du spela upp uppgiftsguiden **ER Skapa en konfiguration för rapporter i OPENXML-format**. Ange ett namn på den nya konfigurationen **Importera/exportera aktiviteter** som visas i följande bild. Använd [Excel-filen ER-data – importera och exportera detaljer](https://download.microsoft.com/download/f/7/5/f755c0fd-025c-4aa9-920b-909abb8302ad/ER-data-import-and-export-details.xlsx) som en mall när du utformar ER-formatet. (För mer information om hur du importerar ett mallformat, kan du spela upp uppgiftsguiden).

[![Konfiguration för importera/exportera aktiviteter.](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

Följ stegen nedan för att ändra formatkonfigurationen för **Importera/exportera aktiviteter**.

1. Klicka på **Designer**.
2. På fliken **Format** namnger du filelement för detta format **Excel utdatafil**.

    [![Element för Excel-utdatafil.](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. På fliken **Mappning** anger du namnet för den Excel-fil som ska skapas när som helst som det här formatet körs på fliken. Konfigurera det relaterade uttrycket för att returnera värdet **Importera och exportera information** (.xlsx-filnamnstillägget kommer att läggas till automatiskt.)

    [![Formatdesigner.](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. Lägg till ett nytt datakällobjekt för det här formatet. (Den här uppräkningen kommer att krävas för ytterligare databindning).

    1. Namnet på datakällan **direction\__enum**.
    2. Välj **Uppräkning för datamodell** som typ av datakälla.
    3. Hänvisa till uppräkningen för datamodell **Riktning**.

    [![direction_enum.](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. Slutför bindningen av element av **Intrastat**-datamodellen och elementen i designformatet som visas i följande bild.

    [![Slutför bindning.](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

När det har utförts, skapar ER-formatet utmatningsresultatet i Excel-format. Det skickar information om Intrastat-transaktionerna till utmatningsresultatet och separerar dem som transaktioner som beskriver antingen importaktiviteter eller exportaktiviteter. Klicka på **Kör** för att testa det nya ER-formatet för listan med Intrastat-transaktioner på sidan **Intrastat** (**Skatt** &gt; **Deklarationer** &gt; **Utländsk handel** &gt; **Intrastat**).

[![Intrastat-sidan.](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

Följande utleveransresultat genereras. Filnamnet **Importera och exportera detaljer.xlsx** som du angav i formatinställningarna.

[![Importera och exportera detaljer.xlsx.](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Konfigurera ER-mål
Du måste konfigurera ER-ramverket om du vill skicka utleveransresultatet för den nya ER-formatkonfigurationen på ett särskilt sätt.

- Utleveransresultatet måste skickas till mappen för den valda SharePoint Server.
- Varje körning av formatkonfigurationen måste skapa en ny version av samma Excel-fil.

På sidan **Elektronisk rapportering** (**Organisationadministration** &gt; **Elektronisk rapportering**), klickar du på artikeln **Elektroniskt rapporteringmål** och lägger till en ny mål. På fältet **Referens** väljer du formatkonfigurationen **Importera/exportera aktiviteter** som du skapade tidigare. Gör på följande sätt när du vill lägga till en post för filmål för referensen.

1. I fältet **Namn** anger du rubriken för filmålen.
2. I fältet **Filnamn** väljer du namnet **Excel-utdatafil** för Excel-filformatkomponenten.

Klicka på knappen **Inställningar** för den nya målposten. Följ sedan dessa steg i dialogrutan **Målinställningar**.

1. På fliken **Power BI** anger **Aktiverad** till **Ja**.
2. I fältet **SharePoint** väljer du dokumenttypen **Delad** som du skapade tidigare.

## <a name="schedule-execution-of-the-configured-er-format"></a>Tidsplanera körning av den konfigurerade ER-formatet
1. På sidan **Konfigurationer** (**Organisationadministration** &gt; **Elektronisk rapportering** &gt; **Konfigurationer**), i konfigurationsträdet väljer du konfigurationen **Importera/exportera aktiviteter** som du skapade tidigare.
2. Ändra status för version 1.1 från **Utkast** till **Slutför** om du vill göra detta format tillgängligt för användning.

    [![Konfiguration av import-/exportaktiviteter på sidan Konfigurationer.](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. Välj den slutförda versionen av konfigurationen **Importera/exportera aktiviteter** och klicka sedan på **Kör**. Observera att den konfigurerade målen tillämpas på utleveransresultatet som skapas i Excel-formatet.
4. Ange alternativet **Batchbearbetning** till **Ja** till att köra den här rapporten i obevakat läge.
5. Klicka på **Upprepning** för att schemalägga den krävda upprepningen av denna batch-körning. Upprepningen definierar hur ofta de uppdaterade data ska överföras till Power BI.

    [![Dialogrutan Elektroniska rapportparametrar.](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. När det har konfigurerat hittar du ER-rapportkörningsjobbet på sidan **Batchjobb** (**Systemadministration &gt; Förfrågningar &gt; Batchjobb**).

    [![Sidan Batchjobb.](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. När det här jobbet körs för första gången, skapar målen en ny Excel-fil som har det konfigurerade namnet i den valda SharePoint-mappen. Varje efterföljande tid som jobbet körs, skapar målen en ny version av den här Excel-filen.

    [![Ny version av Excel-filen.](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Skapa en Power BI-datauppsättning genom att använda utleveransresultatet av ER-formatet
1. Logga in på Power BI och antingen öppna en befintlig Power BI-grupp (arbetsyta) eller skapa en ny grupp. Antingen klicka på **Lägg till** under **Filer** i avsnittet **Importera eller ansluta till data** eller klicka på plusteckenet (**+**) nästa till **Datauppsättningar** i vänstra rutan.

    [![Skapa en datauppsättning.](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. Välj alternativet **SharePoint – gruppwebbplatser** och ange sedan sökvägen till den SharePoint Server som du använder (`https://ax7partner.litware.com` i vårt exempel).
3. Bläddra till mappen **/Shared Documents/GER data/PowerBI** och välj de Excel-filer som du skapade som källa för data för den nya Power BI datauppsättningen.

    [![Välja Excel-filen](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. Klicka på **Anslut** och klicka sedan på **Importera**. En ny datauppsättning skapas som baseras på den valda Excel-filen. Datauppsättningen kan också läggas till automatiskt till den nyskapade instrumentpanelen.

    [![Datauppsättning på instrumentpanelen.](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. Konfigurera uppdateringstidsplanen för denna datauppsättning för att framtvinga en periodisk uppdatering. Regelbundna uppdateringar aktiverar förbrukningen av nya affärsdata som kommer via periodisk körning av ER-rapporten via nya versioner av den Excel-fil som skapas på SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Skapa en Power BI-rapport genom att använda den nya datauppsättningen
1. Klicka på den Power BI-uppsättning för **Importera och exportera detaljer** som du skapade.
2. Konfigurera visualiseringen. Välj till exempel visualiseringen **Ifylld karta** och konfigurera den enligt följande:

    - Tilldela datauppsättningsfältet **CountryOrigin** till fältet **Plats** på kartvisualiseringen.
    - Tilldela datauppsättningsfältet **Belopp** till fältet **Färgmättnad** på kartvisualiseringen.
    - Lägg till datauppsättningsfältet **Aktivitet** och **År** till fältsamlingen **Filter** på kartvisualiseringen.

3. Spara Power BI-rapporten som **Importera och exportera detaljer**-rapport.

    [![Importera och exportera detaljrapport.](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    Observera att kartan visar de länder/regioner som nämns i Excel-filen (Österrike och Schweiz i det här exemplet). Dessa länder/regioner färgas för att visa andelen av fakturerade belopp för varje.

4. Uppdatera listan över Intrastat-transaktioner. Exporttransaktionen som kommer från Italien läggs till.

    [![Lista för Intrastattransaktioner.](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. Vänta på nästa schemalagda körning av ER-rapporten och nästa schemalagda uppdateringen av Power BI-datauppsättningen. Granska sedan Power BI-rapporten (välj att bara visa importera transaktioner). Den uppdaterade kartan visar nu Italien.

    [![Uppdaterad karta.](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>Åtkomst till Power BI-rapport i Finance
Konfigurera integration med Power BI. Mer information finns i [Konfigurera Power BI-integration för arbetsytor](configure-power-bi-integration.md).

1. På arbetsytan **Elektronisk rapportering** som stödjer Power BI-integration (**Organisationadministration** &gt; **Arbetsytor** &gt; **Elektronisk rapporteringarbetsyta**), klickar du på **Alternativ** &gt; **Öppna rapportkatalog**.
2. Välj Power BI-rapporten för **Importera och exportera** detaljer som du skapade om du vill visa den rapporten som en åtgärdsartikel på den valda sidan.
3. Klicka på åtgärdsartikeln för att öppna den sida som visar rapporten som du utformade i Power BI.

    [![Importera och exportera detaljrapport som utformats i Power BI.](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
