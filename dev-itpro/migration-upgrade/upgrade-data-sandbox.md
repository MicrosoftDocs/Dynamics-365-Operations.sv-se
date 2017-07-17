---
title: "Datauppgradering i begränsat läge"
description: "I det här avsnittet beskrivs hur du utför en datauppgradering från AX 2012 till Dynamics 365 for Finance and Operations i begränsat läge."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: sv-se
ms.lasthandoff: 06/15/2017

---

# Datauppgradering i begränsat läge
<a id="data-upgrade-in-a-sandbox-environment" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

Utdata från den här uppgiften är en uppgraderad databas som du kan använda i en avgränsad miljö. Ett begränsat läge är en miljö där företagsanvändare och funktionella gruppmedlemmar kan validera programfunktioner. Funktionaliteten inkluderar anpassningar och data som har hämtats fram från Microsoft Dynamics AX 2012.

Vi rekommenderar att du kör datauppgraderingsprocessen i en utvecklingsmiljö innan du kör den i en delad avgränsad miljö eftersom det minskar den totala tiden som krävs för en lyckad datauppgradering. Om du vill ha mer information, se [Datauppgradering i en utvecklingsmiljö](prepare-data-upgrade.md).

## Översikt över uppgraderingen av begränsade data
<a id="overview-of-the-sandbox-data-upgrade-process" class="xliff"></a>

Innan du börjar uppgradera data i en avgränsad miljö kommer du att ha redan uppgraderade data i en utvecklingsmiljö, såsom beskrivs i [Datauppgradering i en utvecklingsmiljö](prepare-data-upgrade.md). De två processerna är mycket lika. Den största skillnaden är att ett begränsat läge använder Microsoft Azure SQL-databasen för datalagring, medan en utvecklingsmiljö använder Microsoft SQL Server. Den här tekniska skillnaden i databasskiktet kräver att du ändrar datauppgraderingen en aning i en avgränsad miljö eftersom det inte går att återställa en säkerhetskopia från AX 2012-databasinstansen till SQL-databasen.

![Uppgradering av begränsade data](./media/data-upgrade-sandbox.png)

Här följer de högnivåsteg som ska följas under uppgraderingen.

1. Skapa en kopia av AX 2012-databasen. Vi rekommenderar att du använder en kopia eftersom du måste ta bort några objekt i kopian som ska exporteras.
2. Exportera den kopierade databasen till en bacpac-fil med hjälp av ett kostnadsfritt SQL Server-verktyg som heter SQLPackage.exe. Verktyget ger en speciell typ av säkerhetskopia av databasen som kan importeras till SQL-databasen.
3. Överför bacpac-filen till Azure-lagring.
4. Hämta bacpac-filen till Application Object Server (AOS)-datorn i den begränsade miljön och importera den med hjälp av SQLPackage.exe. Du måste sedan köra ett skript mot den importerade databasen för att återställa SQL-databasanvändare.
5. Kör paketet MajorVersionDataUpgrade.zip för att köra datauppgraderingen mot den importerade databasen.

## Skapa en kopia av AX 2012-databasen
<a id="create-a-copy-of-the-ax-2012-database" class="xliff"></a>

Du måste skapa en kopia av AX 2012-databasen som du uppgraderar, eftersom du måste ta bort några objekt från databasen. Dessa objekt kan vara en Microsoft Windows-autentiseringsanvändare. Ändringarna gör den modifierade databasen oanvändbar för AX 2012. I det här steget ska du skapa en kopia av databasen och ta bort de här objekten.

Det här steget måste utföras av databasadministratören (DBA) eller en person som har liknande kunskap och erfarenhet.

För att skapa en databaskopia, skapa en säkerhetskopia av den ursprungliga databasen och återställa den under ett nytt namn. Kontrollera att det finns tillräckligt med utrymme för båda databaserna. Du kan skapa kopian på en annan server. Versionen på SQL Server-instansen som körs i databasen är inte viktig.

Här följer ett exempel på kod som skapar en kopia av en databas. Du måste ändra det här exemplet så att det avspeglar ditt specifika databasnamn.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

När du har skapat kopian, kör följande Transact-SQL (T-SQL)-skript mot den.
ATT GÖRA 

### Exportera den kopierade databasen till en bacpac-fil
<a id="export-the-copied-database-to-a-bacpac-file" class="xliff"></a>

Exportera den kopierade databasen till en bacpac-fil med hjälp av verktyget SQLPackage.exe. Det här steget bör utföras av databasadministratören eller teammedlem som har motsvarande kunskaper.

Det är mycket viktigt att du installerar den senaste versionen av SQL Server Management Studio innan du påbörjar det här steget. Även om SQLPackage finns i tidigare versioner av Management Studio kommer det inte att fungera för det här steget om du inte först installerar den senaste versionen.

Det här steget är viktigt, eftersom exporten måste göras igen under driftstoppet före publiceringen. Nedan följer några tips:

- Bacpac-processsen är mycket i/o- och CPU-intensiv. Kör därför exporten på en kraftfull dator.
- SQLPackage bör köras lokalt på den dator som är värd för databasen. Kör inte SQLPackage på en lokal bärbar dator som du ansluter till datorn där databasen körs, eftersom den här processen också belastar nätverket intensivt.

Öppna därefter **en kommandorad**-fönster i administratörsläge och kör följande kommandon:

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Här följer en förklaring av parametrarna:

- **ssn** (källservernamn) – namnet på SQL Server som exporten sker ifrån. För vår process ska parametern alltid vara inställd på **localhost**.
- **sdn** (källdatabasnamn) – namnet på databasen du vill exportera.
- **tf** (målfilen) – sökvägen och namnet på den fil du vill exportera till. Mappen finns redan, men filen kommer att skapas av processen.
- **/p:CommandTimeout** – tidsgränsvärde per fråga. Den här parametern gör att större tabeller kan exporteras utan att uppnå en tidsgräns.

### Överföra bacpac-filen till Azure-lagring
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

Överför din bacpac-fil till Azure-lagring. Se ATT GÖRA UsingStorageExplorer.docx

### Importera bacpac-filen till SQL-databasen
<a id="import-the-bacpac-file-into-sql-database" class="xliff"></a>

I det här steget ska du importera den exporterade bacpac-filen till SQL-databasinstansen som den begränsade miljön använder. Du måste först installera den senaste versionen av Management Studio på den begränsade AOS-datorn. Sedan importerar du filen med hjälp av verktyget SQLPackage.exe.

Du utför uppgifterna på AOS-datorn direkt i din begränsade miljö, eftersom det inte finns brandväggsregler som begränsar åtkomsten till SQL-databasinstansen. Du kan emellertid få åtkomst med hjälp av AOS-datorn.

Du måste ha den senaste versionen av Management Studio innan du startar importen, som för exportsteget. Det här steget fungerar inte om du har en äldre version.

Av prestandaskäl rekommenderar vi att du placerar bacpac-filen på enhet D på AOS-datorn. På virtuella Azure-datorer (VMs) är enhet D en fysisk disk som vanligtvis har högre prestanda än andra tillgängliga diskar.

Öppna därefter **ett kommandorad**-fönster i administratörsläge och kör följande kommandon:

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Här följer en förklaring av parametrarna:

- **tsn** (målserverns namn) – namnet på SQL Azure-servern du importerar till. Namnet finns i LCS. Lägg till suffixet **. database.windows.net**.
- **tdn** (måldatabasnamn) – namnet på databasen du vill importera till. Databasen bör inte finnas redan. Importen skapar den.
- **sf**(källfil) – sökvägen till och namnet på filen som ska importeras från.
- **tp** (mållösenord) – SQL-lösenordet till SQL-måldatabasinstansen.
- **tu** (målanvändared) – SQL-användarnamnet för SQL-måldatabasinstansen. Vi rekommenderar att du använder **sqladmin**. Du kan hämta lösenordet för den här användaren från ditt LCS-projekt.
- **/p:CommandTimeout** – tidsgränsvärde per fråga. Den här parametern gör att större tabeller kan exporteras utan att uppnå en tidsgräns.
- **/p:DatabaseServiceObjective** – tjänstenivå för den databas som skapas. Du kan kontrollera värdet för den befintliga databasen med hjälp av Management Studio. Högerklicka på databasen och välj sedan **Egenskaper**.

När du kör kommandona visas följande varning. Du kan ignorera den.

![Begränsat fel](./media/sandbox-2.png)
 
### Köra paketet MajorVersionDataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

Kör distributionspaketet för datauppgradering enligt [Uppgradera data i miljöer för utveckling, demo eller begränsade miljöer](upgrade-data-to-latest-update.md).

### Uppgradera en kopia av databasen i en utvecklingsmiljö
<a id="upgrade-a-copy-of-the-database-in-a-development-environment" class="xliff"></a>

Det är användbart att uppgradera samma databas i en utvecklingsmiljö. Om du har en kopia av databasen tillgänglig för utvecklingsmiljöer blir det mycket enklare att undersöka fel som hittas i den uppgraderade, avgränsade miljön.

