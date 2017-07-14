---
title: "Konfigurera elektronisk rapportering för att hämta data till Power BI"
description: "I det här avsnittet beskrivs hur du kan använda konfigurationen för Elektronisk rapportering (ER) om du vill ordna överföringen av data från Finance and Operations till Power BI-tjänster. Som exempel använder det här avsnittet Intrastat-transaktioner som affärsdata som ska överföras. Power BI-kartvisualiseringen använder dessa Intrastat-transaktionsdata för att presentera en vy för analys av företagsimport-/exportaktiviteter på Power BI-rapporten."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 36c5e78f4b85d0c763c35b62a6592365501db325
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Konfigurera elektronisk rapportering för att hämta data till Power BI
<a id="configure-electronic-reporting-to-pull-data-into-power-bi" class="xliff"></a>

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du kan använda konfigurationen för Elektronisk rapportering (ER) om du vill ordna överföringen av data från Finance and Operations till Power BI-tjänster. Som exempel använder det här avsnittet Intrastat-transaktioner som affärsdata som ska överföras. Power BI-kartvisualiseringen använder dessa Intrastat-transaktionsdata för att presentera en vy för analys av företagsimport-/exportaktiviteter på Power BI-rapporten.

Översikt
<a id="overview" class="xliff"></a>
--------

Microsoft Power BI är en samling programtjänster, appar och kopplingar som samverkar för att omvandla externa källor av data till sammanhängande, visuellt integrerande och interaktiva resultat. Elektronisk rapportering (ER) låter användare av Microsoft Dynamics 365 for Finance and Operations enkelt konfigurera datakällor och ordna överföringen av data från Dynamics 365 for Finance and Operations till Power BI. Data överförs som filer i formatet OpenXML-kalkylbladet (Microsoft Excel arbetsboksfilen). De överförda filerna lagras i en Microsoft SharePoint Server som har konfigurerats för det syftet. De lagrade filerna används i Power BI för att göra rapporter som inkluderar visualiseringar (tabeller, diagram, kartor, etc). Power BI-rapporter delas med Power BI-användare och de finns i Power BI-instrumentpaneler och på sidor för Finance and Operations. Det här avsnittet förklarar följande uppgifter:

-   Konfigurera Finance and Operations.
-   Förbered din ER-formatkonfiguration för att hämta data från Finance and Operations.
-   Konfigurera ER-miljön för överföring av data till Power BI.
-   Använd överförda data om du vill skapa en Power BI-rapport.
-   Gör Power BI-rapporten tillgänglig i Finance and Operations.

## Förutsättningar
<a id="prerequisites" class="xliff"></a>
För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:

-   Gå till Finance and Operation för någon av följande roller:
    -   Utvecklare för elektronisk rapportering
    -   Konsult för funktionen för elektronisk rapportering
    -   Systemadministratör
-   Åtkomst till den SharePoint Server som konfigureras för användning med Finance and Operations.
-   Åtkomst till Power BI-ramverket

## Konfigurera dokumenthanteringsparametrar
<a id="configure-document-management-parameters" class="xliff"></a>
1.  På sidan **Dokumenthanteringsparametrar** konfigurerar du åtkomst till den SharePoint Server som ska användas i det företag som du loggat in på (DEMF-företaget i det här exemplet).
2.  Testa anslutningen till SharePoint Server för att kontrollera att du har åtkomst. [![Sidan dokumenthanteringsparametrar](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)
3.  Öppna den konfigurerade SharePoint-siten. Skapa en ny mapp där ER ska lagra Excel-filer som har den affärsdata som Power BI-rapporterna kräver som källa för Power BI-datauppsättningar.
4.  I Finance and Operations, på sidan **Dokumenttyper** skapar du en ny dokumenttyp som kommer att användas för åtkomst till den SharePoint-mapp som du precis skapade. Ange **Fil** i fältet **Grupp** och **SharePoint** i fältet **Plats** och ange sedan adressen för SharePoint-mappen. [![Sida för dokumenttyper](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## Konfigurera ER-parametrar
<a id="configure-er-parameters" class="xliff"></a>
1.  På arbetsytan **Elektronisk rapportering** klickar du på länken **Elektroniska rapporteringsparametrar**.
2.  På fliken **Bilagor** väljer du dokumenttypen **Fil** för alla fälten.
3.  På arbetsytan **Elektronisk rapportering** gör du önskad leverantör aktiv genom att klicka på **Ställ in aktiv**. För mer information kan du spela upp uppgiftsguiden **ER Välja tjänsteleverantör**.

## Använd en ER-datamodell som källa för data
<a id="use-an-er-data-model-as-the-source-of-data" class="xliff"></a>
Du måste ha en ER-datamodell som källa för affärsdata som ska användas för Power BI-rapporter. Den här datamodellen överförs från ER-konfigurationens databas. For more information, see [Hämta Konfigurationer för elektronisk rapportering för Lifecycle Services](download-electronic-reporting-configuration-lcs.md) eller spela upp uppgiftsguiden **ER importera en konfiguration från Lifecycle Services**. Välj **Intrastat** som datamodellen som ska överföras från den valda ER-konfigurationens databas. (I det här exemplet används version 1 av modellen.) Du kan använda den **Intrastat** ER modellkonfiguration på **konfigurationer** sidan. [![Sidan Konfigurationer](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## Designa en konfiguration för ER-format
<a id="design-an-er-format-configuration" class="xliff"></a>
Du måste skapa en ny konfiguration för ER-format som använder datamodellen **Intrastat** som källa för affärsdata. Den här formatkonfigurationen måste skapa utdataresultat som elektroniska dokument i OpenXML-format (Excel-fil). För mer information kan du spela upp uppgiftsguiden **ER Skapa en konfiguration för rapporter i OPENXML-format**. Ange ett namn på den nya konfigurationen **Importera/exportera aktiviteter** som visas i följande bild. Använd [Excel-filen ER-data - importera och exportera detaljer](https://go.microsoft.com/fwlink/?linkid=845208) som en mall när du utformar ER-formatet. (För mer information om hur du importerar ett mallformat, kan du spela upp uppgiftsguiden.) [![Konfiguration av Importera/exportera aktiviteter](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png) Om du vill ändra **Importera/exportera aktiviteter** konfigurationen, gör du följande.

1.  Klicka på **Designer**.
2.  På fliken **Format** namnger du filelement för detta format **Excel utdatafil**. [![Elementet Excel utdatafil](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)
3.  På fliken **Mappning** anger du namnet för den Excel-fil som ska skapas när som helst som det här formatet körs på fliken. Konfigurera det relaterade uttrycket för att returnera värdet **Importera och exportera information** (.xlsx-filnamnstillägget kommer att läggas till automatiskt.) [![Formatdesigner](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Lägg till ett nytt datakällobjekt för det här formatet. (Den här uppräkningen kommer att krävas för ytterligare databindning).
    1.  Namnet på datakällan **direction\__enum**.
    2.  Välj **Uppräkning för datamodell** som typ av datakälla.
    3.  Hänvisa till uppräkningen för datamodell **Riktning**.

    [![direction\_enum](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Slutför bindningen av element av **Intrastat**-datamodellen och elementen i designformatet som visas i följande bild. [![Slutför bindande](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

När det har utförts, genererar ER-formatet utmatningsresultatet i Excel-format. Det skickar information om Intrastat-transaktionerna till utmatningsresultatet och separerar dem som transaktioner som beskriver antingen importaktiviteter eller exportaktiviteter. Klicka på **Kör** för att testa det nya ER-formatet för listan med Intrastat-transaktioner på sidan **Intrastat** (**Moms** &gt; **Deklarationer** &gt; **Utländsk handel** &gt; **Intrastat**). [![Sidan Intrastat](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png) Följande utleveransresultat genereras. Filnamnet **Importera och exportera detaljer.xlsx** som du angav i formatinställningarna. [![Importera och exportera detaljer.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## Konfigurera ER-destinationer
<a id="configure-the-er-destination" class="xliff"></a>
Du måste konfigurera ER-ramverket om du vill skicka utleveransresultatet för den nya ER-formatkonfigurationen på ett särskilt sätt.

-   Utleveransresultatet måste skickas till mappen för den valda SharePoint Server.
-   Varje körning av formatkonfigurationen måste skapa en ny version av samma Excel-fil.

På sidan **Elektronisk rapportering** (**Organisationadministration** &gt; **Elektronisk rapportering**), klickar du på artikeln **Elektroniskt rapporteringmål** och lägger till en ny destination. På fältet **Referens** väljer du formatkonfigurationen **Importera/exportera aktiviteter** som du skapade tidigare. Gör på följande sätt när du vill lägga till en post för fildestination för referensen.

1.  I fältet **Namn** anger du rubriken för fildestinationen.
2.  I fältet **Filnamn** väljer du namnet **Excel-utdatafil** för Excel-filformatkomponenten.

Klicka på knappen **Inställningar** för den nya målposten. Följ sedan dessa steg i dialogrutan **Målinställningar**.

1.  På fliken **Power BI** anger du alternativet **Aktiverad** till **Ja**.
2.  I fältet **SharePoint** väljer du dokumenttypen **Delad** som du skapade tidigare.

## Tidsplanera körning av den konfigurerade ER-formatet
<a id="schedule-execution-of-the-configured-er-format" class="xliff"></a>
På sidan **Konfigurationer** (**Organisationadministration** &gt; **Elektronisk rapportering** &gt; **Konfigurationer**, i konfigurationsträdet väljer du konfigurationen **Importera/exportera aktiviteter** som du skapade tidigare. Ändra status för version 1.1 från **Utkast** till **Slutför** om du vill göra detta format tillgängligt för användning. [![Sidan Konfigurationer](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png) Välj den slutförda versionen av konfigurationen **Importera/exportera aktiviteter** och klicka sedan på **Kör**.. Observera att den konfigurerade destinationen tillämpas på utleveransresultatet som genereras i Excel-formatet. Ange alternativet **Batchbearbetning** till **Ja** till att köra den här rapporten i obevakat läge. Klicka på **Upprepning** för att schemalägga den krävda upprepningen av denna batch-körning. Upprepningen definierar hur ofta de uppdaterade data ska överföras från Finance and Operations till Power BI. [![Dialogrutan Elektroniska rapportparametrar](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png) När det har konfigurerat hittar du ER-rapportkörningsjobbet på sidan **Batchjobb** (**Systemadministration &gt; Förfrågningar &gt; Batchjobb**. [![Sidan Batchjobb](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png) När det här jobbet körs för första gången, skapar destinationen en ny Excel-fil som har det konfigurerade namnet i den valda SharePoint-mappen. Varje efterföljande tid som jobbet körs, skapar destinationen en ny version av den här Excel-filen. [![Ny version av Excel-filen](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## Skapa en Power BI-datauppsättning genom att använda utleveransresultatet av ER-formatet
<a id="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format" class="xliff"></a>
Logga in på Power BI och antingen öppna en befintlig Power BI-grupp (arbetsyta) eller skapa en ny grupp. Antingen klicka på **Lägg till** under **Filer** i avsnittet **Importera eller ansluta till data** eller klicka på plusteckenet (**+**) nästa till **Datauppsättningar** i vänstra rutan. [![Skapa en datauppsättning](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png) Välj alternativet **SharePoint – gruppwebbplatser** och ange sedan sökvägen till den SharePoint Server som du använder (**https://ax7partner.spoppe.com** i vårt exempel). Bläddra till **/Shared Documents/GER datum/PowerBI**-mappen och sedan välja de Excel-filer som du skapade som källa för data för den nya Power BI-datauppsättningen. [![Välja Excel-filen](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png) Klick på **Anslut**, och klicka sedan på **Importera**. En ny datauppsättning skapas som baseras på den valda Excel-filen. Datauppsättningen kan också läggas till automatiskt till den nyskapade instrumentpanelen. [![Datauppsättning på instrumentpanelen](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png) Konfigurera uppdateringstidsplanen för denna datauppsättning för att framtvinga en periodisk uppdatering. Regelbundna uppdateringar aktiverar förbrukningen av nya affärsdata som kommer från Finance and Operations via periodisk körning av ER-rapporten via nya versioner av den Excel-fil som skapas på SharePoint Server.

## Skapa en Power BI-rapport genom att använda den nya datauppsättningen
<a id="create-a-power-bi-report-by-using-the-new-dataset" class="xliff"></a>
För att skapa en ny Power BI-rapport klickar du på den Power BI-uppsättning för **Importera och exportera detaljer** som du skapade. Konfigurera sedan visualiseringen. Välj till exempel visualiseringen **Ifylld karta** och konfigurera den enligt följande:

-   Tilldela datauppsättningsfältet **CountryOrigin** till fältet **Plats** på kartvisualiseringen.
-   Tilldela datauppsättningsfältet **Belopp** till fältet **Färgmättnad** på kartvisualiseringen.
-   Lägg till datauppsättningsfältet **Aktivitet** och **År** till fältsamlingen **Filter** på kartvisualiseringen.

Spara Power BI-rapporten som **Importera och exportera detaljer-rapport**. [![Importera och exportera detaljer-rapport](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png) Observera att kartan visar de länder/regioner som nämns i Excel-filen (Österrike och Schweiz i det här exemplet). Dessa länder/regioner färgas för att visa andelen av fakturerade belopp för varje. Uppdatera listan över Intrastat-transaktioner. Exporttransaktionen som kommer från Italien läggs till. [![Visa Intrastat-lista](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png) Vänta på nästa schemalagda körning av ER-rapporten och nästa schemalagda uppdateringen av Power BI-datauppsättningen. Granska sedan Power BI-rapporten (välj att bara visa importera transaktioner). Den uppdaterade kartan visar nu Italien. [![Uppdaterad karta](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## Gör Power BI-rapporten tillgänglig i Finance and Operations.
<a id="access-power-bi-report-in-finance-and-operations" class="xliff"></a>
Ställ in integrationen mellan med Finance and Operations och Power BI. Mer information finns i [Konfigurera Power BI-integration för arbetsytor](configure-power-bi-integration.md). På arbetsytan **Elektronisk rapportering** som stödjer Power BI-integration (**Organisationadministration** &gt; **Arbetsytor** &gt; **Elektronisk rapporteringarbetsyta**), klickar du på **Alternativ** &gt; **Öppna rapportkatalog**. Välj Power BI-rapporten för **Importera och exportera detaljer** som du skapade om du vill visa den rapporten som en åtgärdsartikel på den valda sidan. Klicka på åtgärdsartikeln för att öppna den sida i Finance and Operations som visar rapporten som du utformade i Power BI. [![Importera och exportera detaljer-rapport](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

Se även
<a id="see-also" class="xliff"></a>
--------

[Destinationer för elektronisk rapportering](electronic-reporting-destinations.md)

[Översikt över elektronisk rapportering](general-electronic-reporting.md)




