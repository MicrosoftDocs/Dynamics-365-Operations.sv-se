---
title: Skapa ett program för återkommande dataexport
description: I detta ämne beskrivs hur du skapar en logisk Microsoft Azure-app som exporterar data från Microsoft Dynamics 365 Human Resources i ett återkommande schema.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 368eee6bb182f363f47467a5c5ad8208a57db7ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069792"
---
# <a name="create-a-recurring-data-export-app"></a>Skapa ett program för återkommande dataexport


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs hur du skapar en logisk Microsoft Azure-app som exporterar data från Microsoft Dynamics 365 Human Resources i ett återkommande schema. Självstudierna drar fördel av personalens DMF-paket REST API (Application Programming Interface) för att exportera data. När data har exporterats sparar logikprogrammet det exporterade datapaketet i en Microsoft OneDrive för företag-mapp.

## <a name="business-scenario"></a>Affärsscenario

I ett typiskt affärsscenario för Microsoft Dynamics 365-integreringer måste data exporteras till ett underordnat system i ett återkommande schema. I den här självstudien visas hur du exporterar alla Microsoft Dynamics 365 Human Resources och spara listan över medarbetare i OneDrive för företag-mapp.

> [!TIP]
> De specifika data som exporteras i den här självstudien och de exporterade data är bara exempel. Du kan enkelt ändra dem för att uppfylla affärskrav.

## <a name="technologies-used"></a>Tekniker som används

I den här självstudien används följande tekniker:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**– Huvuddatakällan för medarbetare som ska exporteras.
- **[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – tekniken som tillhandahåller dirigering och schemaläggning av den återkommande exporten.

    - **[Kopplingar](/azure/connectors/apis-list)** – tekniken som används för att ansluta logikappen till de obligatoriska slutpunkterna.

        - [HTTP med Azure AD](/connectors/webcontents/)koppling
        - [OneDrive för företag](/azure/connectors/connectors-create-api-onedriveforbusiness) koppling

- **[DMF-paket REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – den teknik som används för att utlösa exporten och övervakningen av dess förlopp.
- **[OneDrive för företag](https://onedrive.live.com/about/business/)** – målet för de exporterade arbetarna.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar övningen i den här självstudien måste du ha följande artiklar:

- En personalmiljö med behörigheter på administratörsnivå i miljön
- En [Azure-prenumeration](https://azure.microsoft.com/free/) som ska vara värd för logikappen

## <a name="the-exercise"></a>Övningen

I slutet av övningen har du en logiskapp som är ansluten till personalmiljön och ditt OneDrive för företag-konto. Logikappen exporterar ett datapaket från personal, väntar på att exporten ska slutföras, hämta det exporterade datapaketet och sparar datapaketet i den OneDrive för företag-mapp som du har angett.

Den slutförda logikappen kommer att likna följande bild.

![Översikt över logikappar.](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Steg 1: skapa ett projekt för dataexport i personal

Skapa ett dataexportprojekt i personal som exporterar medarbetare. Namnge projektets **exportarbetare** och se till att alternativet **Generera datapaket** är inställt på **ja**. Lägg till en enskild enhet **(** arbetare) i projektet och välj det format du vill exportera i. (Microsoft Excel-formatet används i den här självstudien.)

![Exportera dataprojekt för medarbetare.](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Kom ihåg namnet på dataexportprojektet. Du kommer att behöva det när du skapar logikappen i nästa steg.

### <a name="step-2-create-the-logic-app"></a>Steg 2: skapa logikappen

Den stora delen av övningen innebär att skapa logikappen.

1. Skapa en logikapp i Azure-portalen.

    ![Sida för att skapa logikapp.](media/integration-logic-app-creation-1.png)

2. Starta med en tom logikapp i modulen Logic Apps Designer.
3. Lägg till en [utlösare för upprepningsschema](/azure/connectors/connectors-native-recurrence) om du vill köra logikappen var 24:e timme (eller enligt ett schema som du väljer).

    ![Dialogrutan Upprepning.](media/integration-logic-app-recurrence-step.png)

4. Anropa [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API för att schemalägga exporten av ditt datapaket.

    1. Använd åtgärden **anropa en HTTP-begäran** från HTTP med Azure AD-koppling.

        - **Grundläggande resurs-URL** : URL för din personalmiljö (inkluderar inte information om sökväg/namnområde.)
        - **Azure AD resurs-URI:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Personaltjänsten tillhandahåller inte ännu en anslutning som visar alla API:er som utgör DMF-paketets REST API, t.ex. **ExportToPackage**. I stället måste du anropa API:erna genom att använda råa HTTPS-begäran via HTTP med Azure AD-kopplingen. Den här kopplingen använder Azure Active Directory (Azure AD) för autentisering och auktorisering till personal.

        ![HTTP med Azure AD-anslutningsprogram.](media/integration-logic-app-http-aad-connector-step.png)

    2. Logga in på din personalmiljön via HTTP med Azure AD-koppling.
    3. Ställ in en HTTP **POST**-begäran för att anropa **ExportToPackage** DMF REST API.

        - **Metod:** POST
        - **Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Huvudtext av begäran:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Åtgärden Anropa en HTTP-begäran.](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Du kanske vill byta namn på varje steg så att det blir mer meningsfullt än standardnamnet **Anropa en HTTP-begäran**. Du kan till exempel byta namn på det här steget **ExportToPackage**.

5. [Initiera en variabel](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) för att lagra körningsstatusen för **ExportToPackage**-begäran.

    ![Åtgärden Initiera variabel.](media/integration-logic-app-initialize-variable-step.png)

6. Vänta tills körningsstatusen för dataexporten har **slutförts**.

    1. Lägg till en [Till slinga](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) som upprepas tills värdet av **ExecutionStatus**-variabeln är **slutförd**.
    2. Lägg till åtgärden **fördröjning** som väntar fem sekunder innan den avsöker den aktuella körningsstatusen för exporten.

        ![Fram till slinga-behållare.](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Ställ in gränsvärdet till **15** om du vill vänta i högst 75 sekunder (15 iterationer × 5 sekunder) för att exporten ska kunna slutföras. Om exporten tar längre tid, kan du justera antalet så att det blir lämpligt.        

    3. Lägg till åtgärden **Anropa HTTP-begäran** för att anropa [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, och ange **ExecutionStatus**-variabeln till resultatet av **GetExecutionSummaryStatus**-svar.

        > Det här exemplet utför ingen felkontroll. **GetExecutionSummaryStatus** API:n kan returnera terminaltillstånd som har misslyckats (dvs. andra lägen än **slutförd**). Mer information finns i [API-dokumentationen](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Metod:** POST
        - **Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Brödtext för begäran:** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > Du kan behöva ange värdet för **brödtext för begäran** antingen i kodvyn eller i funktionsredigeraren i designern.

        ![Åtgärden Anropa en HTTP-begäran 2.](media/integration-logic-app-get-execution-status-step.png)

        ![Åtgärden Ange variabel.](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > Värdet för åtgärden **Ange variabel** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) skiljer sig från värdet för **Invoke an HTTP request 2** brödtextvärde, även om designern visar värdena på samma sätt.

7. Skaffa hämtnings-URL för det exporterade paketet.

    - Lägg till åtgärden **Anropa HTTP-begäran** för att anropa [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.

        - **Metod:** POST
        - **Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Begärans brödtext:** {"executionId": body('GetExportedPackageURL')?['value']}

        ![Åtgärden GetExportedPackageURL.](media/integration-logic-app-get-exported-package-step.png)

8. Hämta det exporterade paketet.

    - Lägg till en HTTP **GET**-begäran (en inbyggd [åtgärd för HTTP-koppling](/azure/connectors/connectors-native-http)) för att hämta paketet från den URL som returnerades i föregående steg.

        - **Metod:** GET
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Du kan behöva ange värdet för **URI** antingen i kodvyn eller i funktionsredigeraren i designern.

        ![Åtgärden HTTP GET.](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > Denna begäran kräver ingen ytterligare autentisering eftersom den URL som **GetExportedPackageUrl** API:n returnerar innehåller en token för delad åtkomst för signaturer som beviljar åtkomst för att hämta filen.

9. Spara det hämtade paketet med hjälp av [OneDrive för företag](/azure/connectors/connectors-create-api-onedriveforbusiness)-kopplingen.

    - Lägg till en åtgärd för OneDrive för företag [Skapa fil](/connectors/onedriveforbusinessconnector/#create-file).
    - Anslut till ditt OneDrive för företag-konto efter behov.

        - **Mappsökväg:** en mapp som du väljer
        - **Filnamn:** worker\_package.zip
        - **Filinnehåll:** brödtexten från föregående steg (dynamiskt innehåll)

        ![Åtgärden Skapa fil.](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Steg 3: testa logikappen

Om du vill testa din logikapp väljer du knappen **Kör** i designern. Du kommer att se att stegen i logikappen börjar köras. Efter 30 till 40 sekunder bör logikappen slutföras och mappen OneDrive för företag bör innehålla en ny paketfil som innehåller de exporterade arbetarna.

Om ett fel rapporteras för något steg väljer du det misslyckade steget i designer och granskar fälten **indata** och **utdata**. Felsök och justera steget efter behov för att korrigera felen.

Följande bild visar hur Logic Apps Designer ser ut när alla steg i logikappen körs korrekt.

![Lyckad körning av logikappar.](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Sammanfattning

I den här självstudien lärde du dig att använda en logikapp för att exportera data från personal och spara exporterade data till en OneDrive för företag-mapp. Du kan ändra stegen i den här självstudien så att de passar dina affärsbehov.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
