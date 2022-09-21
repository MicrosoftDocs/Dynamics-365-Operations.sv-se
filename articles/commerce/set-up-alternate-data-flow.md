---
title: Ställa in alternativt dataflöde för rekommendationer
description: I den här artikeln beskrivs hur du konfigurerar en miljö med hjälp av ett alternativt dataflöde för att tillhandahålla data till tjänsten för rekommendationer.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460170"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Ställa in alternativt dataflöde för rekommendationer

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du konfigurerar en miljö med hjälp av ett alternativt dataflöde för att tillhandahålla data till tjänsten för rekommendationer.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Jämförelse av medföljande dataflödet med alternativt dataflöde

I följande bild visas medföljande dataflödet ut ur rutan i en miljö.

![Medföljande dataflödet i en miljö](media/reco-out-of-the-box-dataflow-2.png)

I följande bild beskrivs ett alternativt dataflöde där enhetens batchjobb för synkronisering ersätts med alternativa dataflödessteg.

![Alternativt dataflöde i en miljö](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Antaganden

- I den här artikeln förutsätts det att du redan har aktiverat tjänsten rekommendationer för din miljö. Mer information finns i [Aktivera produktrekommendationer](enable-product-recommendations.md).
- När du arbetar med filer och mappar i Microsoft Azure Data Lake Storage-konto:

    - Du kan använda antingen Azure webbportalgränssnitt eller programmet Azure Storage Explorer.
    - Startpunkterna för att arbeta med filer och mappar finns i behållaren **dynamics365-financeandoperations** som finns under mappen som är namngiven för att matcha din miljö-URL.
    - Om namnet på din sandbox-miljö är **MyUAT**, miljöbasens URL kommer att vara `myuat.sandbox.operations.dynamics.com`.
    - Om fler än en miljö är ansluten till samma lagringskonto har varje miljö sin egen rotmapp.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas innan du kan implementera den alternativa dataflödesmetoden.

### <a name="set-up-microsoft-power-platform"></a>Ställ in Microsoft Power Platform

Så här ställer du in Microsoft Power Platform, följa instruktionen [Aktivera Microsoft Power Platform integrationen](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Installera tillägget för export till Data Lake

För att installera tillägget Export till Data Lake följer du instruktionerna i [Installera tillägget för export till Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Observera konfigurationsvärdena eftersom du behöver dem för några av de steg som följer.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Konfigurera register att exportera i Dynamics 365

Tabellsynkronisering från Dynamics 365 Azure Data Lake Storage hanteras på sidan **Exportera till Data Lake**. Eftersom den sidan för närvarande inte har något menyalternativ kan bara användare med säkerhetsrollen **Systemadministratör** öppna det.

Konfigurera register att exportera i Dynamics 365 genom att följa dessa steg.

1. För att öppna sidan **Exportera till Data Lake**, lägg till strängen `?mi=DataFeedsDefinitionWorkspace` i miljöns bas-URL, som visas i följande exempel:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. På sidan **Exportera till Data Lake** och kopiera tabellerna som är listade i avsnittet [Lista över RetailSales cubtabeller](#list-of-retailsales-cube-tables) i den här artikeln.
1. Expandera listan med filteralternativ i kolumnen **Systemnamn**.
1. För filtertyp, välj **är en av**. Placera sedan markören i textrutan och klistra in listan över register som du kopierat från sidan **Exportera till Data Lake**.
1. Välj **Använd** längst ned i listan med filteralternativ.
1. Markera alla rader i rutnätet och välj sedan **Aktivera**.

> [!NOTE]
> Innan du går vidare till nästa steg måste alla rader uppdateras till statusvärdet **Kör**. Felsöka och korrigera eventuella fel efter behov.

### <a name="create-a-synapse-workspace"></a>Skapa en Synapse-arbetsyta

Skapa en Synapse-arbetsyta om du inte redan har en genom att följa instruktionerna i [Snabbstart: Skapa en Synapse-arbetsyta](/azure/synapse-analytics/quickstart-create-workspace).

För att dina Azure-resurser ska organiseras rekommenderar vi att du sätter samman Data Lake Storage-kontot och Synapse-arbetsytan i en resursgrupp i Azure. Du kan återanvända lagringskontot som du skapade när du installerade tillägget Exportera till Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Skapa en databas i Synapse för bearbetning av rekommendationsdata

Använd programmet Common Data Model utility konsol (CDMUtil_ConsoleApp) om du vill skapa en databas i din Synapse-arbetsyta och fylla i den från Common Data Model i Data Lake Storage. Vi rekommenderar att du använder verktyget Common Data Model med din databas i en utvecklingsmiljö om det finns några utökningar.

> [!NOTE]
> I följande steg förutsätts det att inga filtilläggsdata läggs till i RetailSales-kuben.

Följ dessa steg för att skapa en databas i Synapse.

1. Gå till [Dynamics-365-FastTrack-Implementation-Assets GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) och följ stegen för att hämta zip-filen **CDMUtilConsoleApp.zip**.
1. Extrahera zip-filen i en lokal mapp.
1. Öppna filen **CDMUtil_ConsoleApp.dll.config** i en textredigerare och uppdatera följande värden:

    1. Ange värdet **Klientorganisations-ID** (Azure klientorganisations-ID).
    1. Ställ in värdet för **åtkomstnyckeln** (åtkomstnyckeln för Data Lake Storage-kontot).

        1. Öppna ditt lagringskonto i Azure-portalen.
        1. Välj **Åtkomstnycklar** på menyn till vänster om sidan.
        1. Välj **Visa nycklar** överst på sidan.
        1. Välj kopieringsknappen för ett av de två nyckelfälten och klistra sedan in värdet mellan de dubbla citationstecken i konfigurationsfilen.

    1. Ställ in ett värde för **ManifestURL** som är URL-adressen till filen **Tables.manifest.cdm.json** i Azure Data Lake Storage. Om du vill hämta URL-adressen bläddrar du till filen i Azure-portal, väljer ellipsen (**...**) till höger om vyn och väljer **egenskaper**. URL-adressen är den första egenskapen som visas på fliken **Översikt**.
    1. Ange värdet **TargetDbConnectionString** till anslutningssträngen för den inbyggda serverlösa SQL-poolen i din Synapse-arbetsyta.

        1. Markera fliken **Hantera** i Synapse-arbetsytan.
        1. Välj **SQL-pooler** på undermenyn.
        1. Välj namnet **Inbyggda** för att visa poolens egenskaper.
        1. I dialogrutan egenskaper väljer du den ADO.NET som du vill använda. Kopiera sedan värdet för anslutningssträngen och klistra in det mellan de dubbla citationstecken i konfigurationsfilen.

        > [!NOTE]
        > Du måste ha behörighet att skapa databaser. Du kanske vill använda det inbyggda administratörskontot för **sqladminuser** för att underlätta användningen.

    1. Avmarkera noden **ProcessEntities** och ställ in dess värde på **sant** (till exempel `<add key="ProcessEntities" value ="true"/>`).

1. Spara och stäng filen **CDMUtil_ConsoleApp.dll.config**.
1. Kopiera filen **EntityList.json** till katalogen **/Manifest**.
1. I fönstret kommandotolken, kör **cdmutil_consoleapp.exe**.

> [!NOTE]
> När du granskar utdata bör det finnas 35 enheter/vyer, minst 75 tabeller och inga fel.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Förbered Katalog med sammanlagda mått Data RetailSales

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Backa dina aktuella RetailSales-kubdata från Data Lake Storage

Det enklaste sättet att säkerhetskopiera dina aktuella RetailSales-kubdata är att byta namn på katalogen **RetailSales** i Data Lake Storage **RetailSales-säkerhetskopia** eller något liknande. Den här metoden behåller befintliga data om felsökning krävs senare.

Kubmappen **/RetailSales** finns på följande plats:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Skapa en ny RetailSales-mapp och överför modellfilen

Skapa en ny **RetailSales** katalog och överför **model.json**-filen till Data Lake Storage, genom att följa dessa steg.

1. Skapa en ny, tom katalog på samma nivå som föregående katalog och ge den namnet **RetailSales**.
1. För över **model.json**-filen till den nya katalogen.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Skapa ett pipeline för att kopiera RetailSales-kubdata

Pipeline läser vyerna av RetailSales-kuben och exporterar data till CSV-filer i Data Lake Storage.

Skapa en pipeline för att kopiera RetailSales-kubdata med dessa steg.

1. Markera fliken **Integrera** i Synapse-arbetsytan.
1. Välj plustecknet (**+**) och välj sedan **Importera från pipelinemall**.
1. Hämta och välj sedan [ExportRetailSalesCubeViews.zip-filen](https://aka.ms/reco-alternate-dataflow-files).
1. Markera din länkade tjänst för SQL-databasen.
1. Välj den tjänst som är kopplad till ditt lagringskonto.
1. Öppna verktyget **Kopiera data** och ändra egenskapen **Mappsökväg** till **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Testkörning av pipeline

Vi rekommenderar att du testar pipeline genom att bara använda en vy. Vyn **RetailSales_RetailMediaTemplateView** fungerar bra eftersom den vanligtvis innehåller färre än 10 rader.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Planera pipeline att köra med ett återkommande schema

Varje gång pipeline körs sker Azure-förbrukning. Vi rekommenderar att du tidsplanerar körningen med intervaller på 48 timmar eller längre. Du kan alltid köra pipeline manuellt om du måste synkronisera data på en gång. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Registerlista för synkronisering från Dynamics 365 till Data Lake Storage

Följande lista över register är en underuppsättning av alla register som krävs för hela RetailSales-kuben. Endast 15 av vyerna i RetailSales-kuben används av rekommendationer från tjänsten och listan med obligatoriska register filtrerades enligt detta.

### <a name="list-of-retailsales-cube-tables"></a>Lista över kubregister för RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Katalog
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Visa en lista för parametern som ska överföras till Synapse-pipeline

Följande kommaseparerade lista innehåller RetailSales-kubvyerna som pipelinen kommer att utföra en "select"-operation på. Därefter kopieras resultaten till Data Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> Pipeline parameter måste vara en lista med visningsnamn som avgränsas med ett kommatecken. Det får inte finnas några mellanslag eller radmatningar.

## <a name="environment-specific-fixes"></a>Miljöspecifika korrigeringar

### <a name="retailchannelview-fix"></a>RETAILCHANNELVIEW-korrigering

Vyn **RETAILCHANNELVIEW** innehåller ett hårdkodat heltal som representerar en organisation av typen "butikskanal". Det faktiska värdet av typen kan ändras från miljö till miljö, eller från innehavare till innehavare.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Följ dessa steg för att uppdatera hårdkodade heltal.

1. I Dynamics 365, sök värdet **ChannelID** för din onlinekanal.
1. I en instans av SQL Server Management Studio (SSMS) som är kopplad till Synapse-databasen, kör följande fråga.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Kopiera värdet från den första kolumnen (**INSTANCERELATIONTYPE**) och klistra in det i visningsdefinitionen.

## <a name="troubleshooting"></a>Felsökning

### <a name="pipeline-task-fails"></a>Pipeline misslyckas

Det ska finnas 15 körningar av pipeline-uppgifter för **CopyData** uppgiften. Om körningen misslyckas måste du validera att alla underordnade SQL-objekt finns och att frågorna körs. Det enklaste sättet att komma till alla beroenden är att använda SSMS för att ansluta till databasen. Du kan sedan välja och hålla ned (eller högerklicka) en vy och välja **Generera SKAPA som ett nytt fönster**.

Felmeddelandet kan innehålla följande text:

- Fel: Fel har inträffat på sidan "Källa"
- Extern fil för felhantering: 'Max fel antal'.
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Exempelscenario

I det här exemplet **RetailSales_RetailProductCategory** och felmeddelandet "Max-felräkning" visas.

Följ dessa steg för att felsöka felet.

1. Öppna filen **EntityList.json** i en textredigerare (till exempel Visual Studio Code).
1. Sök efter visningsdefinition för **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Den här vyn beror bara på en annan vy: **RetailProductCategoryView** _. Sök efter visningsdefinition för _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Den här vyn beror på tre andra vyer: **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS** och **RETAILCATEGORYEXPANDED**. Sök efter definitionen för var och en av dessa vyer och visa en lista över dess beroenden. Fortsätt tills du hittar alla beroende vyer.

    Här är hela listan i beroende trädordning. Tretton vyer måste valideras.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. I Excel skapar du följande 13 **select count(\*) från \<view_name\>** utdrag. Kör dessa satser i SSMS och skicka resultaten till text. Rulla sedan genom resultaten för att se om någon av vyerna misslyckades. Det första felet föreslår att minst en av vyerna kommer att misslyckas.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Ett sätt att validera vad du letar efter är att skapa en rotberoende vy för att generera visningsdefinitionen i SSMS. Kontrollera sedan att det finns en Azure Data Lake-filkolumn som kallas **r.filepath**. Om den här kolumnen finns innebär det att vyn som du inspekterar läser in data från Data Lake Storage.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
