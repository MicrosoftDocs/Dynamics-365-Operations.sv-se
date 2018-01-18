---
title: "Återställa datatorget för Financial reporting"
description: "Det här avsnittet beskriver hur du återställer datatorget för Financial reporting."
author: aolson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 5b956dcc5a4a93033396ae0ffcf8b7aeba2cf3f2
ms.openlocfilehash: a07e8b5bae2c4f71e9212cd2f8080d2481769818
ms.contentlocale: sv-se
ms.lasthandoff: 12/14/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>Återställa datatorget för Financial reporting

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver hur du återställer datatorget för Financial reporting för följande versioner:

- Microsoft Dynamics 365 for Finance and Operations Financial Reporting, version 7.2.6.0 och senare
- Microsoft Dynamics 365 for Finance and Operations Financial Reporting, version 7.0.10000.4 och senare
- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lokal)

Om du vill ha Finance and Operations Financial reporting i version 7.2.6.0 kan du ladda ned KB 4052514 från <https://fix.lcs.dynamics.com/Issue/Resolved?kb=4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Återställ datatorget för Financial reporting för Finance and Operations Financial reporting version 7.2.6.0 och senare

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Återställ datatorget för Financial reporting via Report designer

> [!NOTE]
> Processens steg stöds för Finance and Operations Financial reporting, version 7.2.6.0 och senare. Om du har en tidigare version kan du kontakta supportteamet för att få hjälp.

I vissa fall kan behöva du återställa datatorget för Financial reporting. Du kan göra detta i Report designer-klienten. Här följer några scenarier där du kan behöva återställa datatorget:

- Databasen för Finance and Operations har återställts, men datatorgets databas återställdes inte.
- Felaktiga data visas under en period.
- Supporten uppmanar dig att återställa datatorget som en del av en åtgärd för felsökning.

Återställning av datatorg bör utföras endast under perioder när mängden bearbetning i databasen är liten. Ekonomiska rapporter är inte tillgängliga under återställningen.

#### <a name="reset-the-data-mart"></a>Återställ datatorget

För att återställa datatorget öppnar du menyn **Verktyg** i Report designer och väljer sedan **Återställ datatorg**. Dialogrutan som visas har två avsnitt: **Statistik** och **Återställ**.

[![Dialogrutan Återställ datatorg](./media/Reset-72.jpg)](./media/Reset-72.jpg)

##### <a name="integration-attempts"></a>Integrationsförsök

Rutnätet **Integreringsförsök** visar hur många gånger systemet har försökt att integrera transaktioner. Systemet fortsätter att försöka integrera data under ett antal dagar om de första försöken misslyckas. Du vet är datatorget måste återställas om antalet försök är 8 eller fler, samt om det finns många dimensionskombinations- eller transaktionsposter. I detta fall kommer inte informationen att redovisas.

##### <a name="data-status"></a>Datastatus

Rutnätet **Datastatus** innehåller en ögonblicksbild av transaktioner, valutakurser och dimensionsvärden i datatorget. Ett stort antal inaktuella poster anger att många uppdateringar till posterna har inträffat. Detta kan leda till långsammare rapportgenerering.

##### <a name="misaligned-main-account-categories"></a>Feljusterade huvudkontokategorier

Om du använder en version som är äldre än Microsoft Dynamics 365 for Finance and Operations Financial reporting version 7.2.1 kan du komma att behöva återställa datatorget om du vill byta namn på konton och flytta konton mellan olika kontokategorier. Dessa åtgärder kan förorsaka att huvudkontokategorier feljusteras. Fältet **Feljusterade huvudkontokategorier** anger om du har det problemet.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Återställ datatorget i Finance and Operations Financial reporting version 7.2.6.0

För att återställa datatorget i Finance and Operations Financial reporting version 7.2.6.0 och tidigare väljer du i dialogrutan **Återställ datatorg** kryssrutan **Återställ datatorg** och sedan **OK**. Du bör endast återställa datatorget under ett schemalagt driftstopp.

[![Kryssrutan Återställ datatorg](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Återställ datatorget och välj en orsak i Microsoft Dynamics 365 for Finance and Operations Financial reporting version 7.3.0

Om du upptäcker att en återställning av datatorg krävs väljer du kryssrutan **Återställ datatorg** och sedan en orsak i fältet **Orsak**. Följande alternativ är tillgängliga:

- **Saknade eller felaktiga data** – Utifrån statistiken har du bedömt att data kanske saknas. Vi rekommenderar att du samarbetar med supporten för att fastställa orsaken innan du fortsätter.
- **Återställ databas** – Databasen för Finance and Operations har återställts, men databasen för Financial reporting återställdes inte.
- **Övrigt** – Du återställer datatorget av något annat skäl. Om du misstänker att det finns ett problem kan du kontakta supporten för att identifiera det.

[![Återställ datatorg](./media/Integration.png)](./media/Integration.png)

> [!NOTE]
> Verifiera att alla återställningsuppgifter för datatorg har slutfört en inledande inläsning innan du påbörjar återställningen. Du kan bekräfta detta genom att leta efter ett värde i kolumnen Senaste körning genom att markera **verktyg**&gt;**integrationsstatus**.

#### <a name="clear-users-and-companies"></a>Rensa användare och företag

Välj kryssrutan **Rensa användare och företag** om du har återställt databasen men sedan ändrat användare eller företag. Du bör sällan få behov av att välja denna kryssruta.

Markera **OK** när du vill starta återställningen. Du uppmanas att bekräfta att du vill starta processen. Observera att Financial reporting inte är tillgängligt under återställningen och den initiala dataintegration som därefter uppstår.

Välj **Verktyg** &gt; **Integrationsstatus** för att se när integrering senast kördes, samt dess status.

[![Visa installationsstatus för integrationen](./media/New-integration.PNG)](./media/New-integration.PNG)

> [!NOTE]
> Återställningen är klar när alla mappningar visar status för RanToCompletion och fönstret Integrationsstatus säger ”fullständig Integration” i det nedre vänstra hörnet.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Återställ datatorget för Financial reporting för Finance and Operations Financial reporting version 7.0.10000.4 och senare

Om du återställer Finance and Operations-databasen från en säkerhetskopia eller kopierar databasen från en annan miljö måste du följa stegen i det här avsnittet i syfte att säkerställa att Financial reporting-datatorget använder den återställda Finance and Operations-databasen på ett korrekt sätt.

> [!NOTE]
> Observera att stegen i processen stöds för Microsoft Dynamics AX, programvaruversion 7.0.1 (maj 2016) (programversion 7.0.1265.23014 och Financial reporting, version 7.0.10000.4) och senare versioner. Om du har en tidigare version av Finance and Operations, kontakta vårt supportteam för hjälp.

### <a name="export-report-definitions"></a>Exportera rapportdefinitioner

Följ först dessa steg för att exportera rapportdesignen från Report designer.

1. I Report Designer, välj **Företag** &gt; **Grupper för byggblock**.
2. Välj den grupp med byggblock som du vill exportera och välj sedan **Exportera**.

    > [!NOTE]
    > För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.

3. Välj de rapportdefinitioner som ska exporteras:

    - Om du vill exportera alla rapportdefinitioner och motsvarande byggblock väljer du **Markera alla**.
    - Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar väljer du lämpliga flikar och sedan de artiklar du vill exportera. Håll knappen Ctrl intryckt för att välja flera olika artiklar i en flik. När du väljer vilka rapporter du vill exportera kommer tillhörande rader, kolumner, träd och dimensionsuppsättningar att väljas.

4. Välj **Exportera**.
5. Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.
6. Välj **Spara**.

Du kan kopiera eller överföra filen till en säker plats. På så sätt kan filen senare importeras till en annan miljö. Mer information om hur du använder ett Microsoft Azure-lagringskonto finns i [Överföra data med kommandoradsverktyget AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> Microsoft tillhandahåller inget lagringskonto som en del av ditt Finance and Operations-avtal. Du måste antingen köpa ett konto för lagring eller använda ett lagringskonto från en separat Azure-prenumeration.

> [!WARNING]
> Var medveten om hur enheten D fungerar på virtuella Azure-datorer (VM). Förvara inte dina exporterade byggblocksgrupper på enhet D permanent. Mer information om tillfälliga enheter finns i [Förstå temporärenheten på virtuella Windows Azure-datorer](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Stoppa tjänster

Följande Microsoft Windows-tjänster har öppna anslutningar till Finance and Operations-databasen. Du måste därför använda Microsofts fjärrskrivbord för att ansluta till alla datorer i miljön och sedan stoppa dessa tjänster via services.msc.

- World wide web-publiceringstjänst (gäller alla AOS-datorer)
- Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)
- Processtjänsten Management Reporter 2012 (endast på BI-datorer)

### <a name="reset"></a>Återställ

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Hämta det senaste MinorVersionDataUpgrade.zip-paketet

Hämta det senaste MinorVersionDataUpgrade.zip-paketet. Instruktioner om hur du hittar och hämtar rätt version av datauppgraderingspaketet finns på[Hämta senaste distribuerbara datauppgraderingspaket](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package). 

En uppgradering krävs inte för att hämta MinorVersionDataUpgrade.zip-paketet. Därför måste du helt enkelt följa stegen i avsnittet ”Hämta senaste distribuerbara datauppgraderingspaketet”. Du kan hoppa över de övriga stegen i avsnittet.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Kör skript mot Finance and Operations-databasen

Kör följande skript mot Finance and Operations-databasen (inte mot Financial reporting.databasen):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Dessa skript bidrar till att inställningar för användare, roller och ändringsspårning är korrekta.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Kör ett Windows PowerShell-kommando för att återställa databasen

Starta Microsoft Windows PowerShell som administratör på AOS-datorn om du vill återställa integreringen mellan Finance and Operations och Financial reporting.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Här följer en förklaring av parametrarna i kommandot **Återställ datatorgsintegration**:

- Giltiga värden för **-Orsak** är **BEARBETNING**, **DATAFEL** samt **ÖVRIGT**.
- Parametern **-ReasonDetail** är fritext.
- Orsaken och orsaksdetaljen registreras i telemetri-/miljöövervakningen.

> [!NOTE]
> När du kör kommandona uppmanas du att ange **Y** för att bekräfta att du vill återställa databasen.

#### <a name="restart-services"></a>Återstarta tjänster

Använd services.msc för att starta om tjänsterna som du tidigare har stoppat:

- World wide web publishing service (gäller alla AOS-datorer)
- Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)
- Management Reporter 2012 processtjänst (endast på BI-datorer)

#### <a name="import-report-definitions"></a>Importera rapportdefinitioner

Importera dina rapportdesigner från Report designer med den fil som skapades vid exporten.

1. I Report Designer, välj **Företag** &gt; **Grupper för byggblock**.
2. Välj den grupp med byggblock som du vill exportera och välj sedan **Exportera**.

    > [!NOTE]
    > För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.

3. Välj byggblocket **Standard** och klicka sedan på **Importera**.
4. Välj filen som innehåller de exporterade rapportdefinitionerna och välj sedan **Öppna**.
5. Välj vilka rapportdefinitioner som ska importeras i dialogrutan **Importera**:

    - Om du vill importera alla rapportdefinitioner och motsvarande byggblock väljer du **Markera alla**.
    - Om du vill importera specifika rader, kolumner, träd eller dimensionsgrupper klickar du på motsvarande rapporter, rader, kolumner, träd eller dimensionsgrupper.

6. Välj **Importera**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Återställ datatorget för Financial reporting i Finance and Operations (lokal)

1. Be alla användare att avsluta Report designer och Financial reporting-avsnittet i Finance and Operations.
2. Kör följande skript mot Financial reporting-databasen (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. Trunkera eller ta bort alla poster från tabellen FINANCIALREPORTS i Finance and Operations-databasen (AXDB).
4. Trunkera eller ta bort alla poster från tabellen FINANCIALREPORTVERSION om denna finns i Finance and Operations-databasen. Om tabellen inte finns i databasen för Finance and Operations, hoppa då över detta steg.
5. Kör skriptet **ResetDatamart.sql** mot Financial reporting-databasen. Skriptet inaktiverar datatorgsintegrering, raderar all datatorgsinformation och återaktiverar sedan datatorgsintegreringen.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. Efter återställningen kan du manuellt bekräfta dataomladdningen genom att köra följande fråga mot Financial reporting-databasen.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Kontrollera att alla rader har ett **LastRunTime**-värde och att **StateType** anges som **5**. Ett **StateType**-värde på **5** anger att datan har laddats om. Värdet av **7** anger felstatus. Ibland anger organisationshierarkikartan denna status första gången den körs. Felstatusen bör emellertid lösas automatiskt.

