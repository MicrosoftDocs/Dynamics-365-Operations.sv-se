---
title: "Återställa datamart med ekonomisk rapportering när du återställer en databas"
description: "Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="e32b2-103">Återställa datamart med ekonomisk rapportering när du återställer en databas</span><span class="sxs-lookup"><span data-stu-id="e32b2-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e32b2-104">Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas.</span><span class="sxs-lookup"><span data-stu-id="e32b2-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="e32b2-105">Om du återställer Finance and Operations-databasen från en säkerhetskopia eller kopierar databasen från en annan miljö måste du följa stegen i det här avsnittet och kontrollera att den ekonomiska rapporteringens datamart använder den återställda Finance and Operations-databasen.</span><span class="sxs-lookup"><span data-stu-id="e32b2-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="e32b2-106">Stegen i processen stöds för Dynamics 365 for Operations maj 2016-versionen (programversion 7.0.1265.23014 och ekonomisk rapportering version 7.0.10000.4) och senare versioner.</span><span class="sxs-lookup"><span data-stu-id="e32b2-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="e32b2-107">Om du har en tidigare version av Finance and Operations, kontakta vårt supportteam för hjälp.</span><span class="sxs-lookup"><span data-stu-id="e32b2-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="e32b2-108">Exportera rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="e32b2-108">Export report definitions</span></span>
<span data-ttu-id="e32b2-109">Först exporterar du de rapportdesigner som finns i rapportdesignern på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e32b2-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="e32b2-110">I Report Designer, gå till **Företag** &gt; **Grupper för byggblock**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="e32b2-111">Välj den grupp med byggblock som du vill exportera och klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="e32b2-112">För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="e32b2-113">Välj de rapportdefinitioner som ska exporteras:</span><span class="sxs-lookup"><span data-stu-id="e32b2-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="e32b2-114">Klicka på **Markera alla** om du vill exportera alla dina rapportdefinitioner och de associerade byggblocken.</span><span class="sxs-lookup"><span data-stu-id="e32b2-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="e32b2-115">Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar klickar du på lämpliga flikar och väljer de artiklar du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="e32b2-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="e32b2-116">Håll knappen Ctrl intryckt för att välja flera olika artiklar i en flik. När du väljer vilka rapporter du vill exportera kommer tillhörande rader, kolumner, träd och dimensionsuppsättningar att väljas.</span><span class="sxs-lookup"><span data-stu-id="e32b2-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="e32b2-117">Klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-117">Click **Export**.</span></span>
5.  <span data-ttu-id="e32b2-118">Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.</span><span class="sxs-lookup"><span data-stu-id="e32b2-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="e32b2-119">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-119">Click **Save**.</span></span>

<span data-ttu-id="e32b2-120">Filen kan kopieras eller laddas upp till en säker plats, vilket gör det möjligt att importera den till en annan miljö vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="e32b2-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="e32b2-121">Information om hur du använder ett Microsoft Azure-lagringskonto finns i [Överföra data med verktyget kommandoradsverktyget AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="e32b2-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="e32b2-122">Microsoft tillhandahåller inget lagringskonto som en del av ditt Finance and Operations-avtal.</span><span class="sxs-lookup"><span data-stu-id="e32b2-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="e32b2-123">Du måste antingen köpa ett konto för lagring eller använda ett lagringskonto från en separat Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e32b2-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="e32b2-124">Var medveten om hur enheten D fungerar på virtuella Azure-datorer.</span><span class="sxs-lookup"><span data-stu-id="e32b2-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="e32b2-125">Förvara inte de exporterade byggblocksgrupperna här permanent.</span><span class="sxs-lookup"><span data-stu-id="e32b2-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="e32b2-126">Mer information om tillfälliga enheter finns i [Förstå den tillfälliga enheten på virtuella Windows Azure-datorer](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="e32b2-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="e32b2-127">Stoppa tjänster</span><span class="sxs-lookup"><span data-stu-id="e32b2-127">Stop services</span></span>
<span data-ttu-id="e32b2-128">Använda fjärrskrivbordet för att ansluta till alla datorer i miljön och stoppa följande tjänster för Windows via services.msc:</span><span class="sxs-lookup"><span data-stu-id="e32b2-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="e32b2-129">World wide web publishing service (gäller alla AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="e32b2-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="e32b2-131">Management Reporter 2012 processtjänst (endast på BI-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="e32b2-132">Tjänsterna har öppna anslutningar till Finance and Operations-databasen.</span><span class="sxs-lookup"><span data-stu-id="e32b2-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="e32b2-133">Återställ</span><span class="sxs-lookup"><span data-stu-id="e32b2-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="e32b2-134">Leta upp och hämta senaste MinorVersionDataUpgrade.zip-paketet</span><span class="sxs-lookup"><span data-stu-id="e32b2-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="e32b2-135">Leta reda på det senaste MinorVersionDataUpgrade-paketet med hjälp av instruktionerna i [Hämta det senaste distributionspaketet för datauppgradering](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="e32b2-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="e32b2-136">Instruktionerna förklarar hur du hittar och hämtar rätt version av datauppgraderingspaketet.</span><span class="sxs-lookup"><span data-stu-id="e32b2-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="e32b2-137">En uppgradering krävs inte för att hämta MinorVersionDataUpgrade.zip-paketet.</span><span class="sxs-lookup"><span data-stu-id="e32b2-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="e32b2-138">Du behöver bara utföra åtgärderna i ”Hämta senaste distributionspaketet för datauppgradering” utan att utföra någon av de övriga stegen i artikeln för att hämta en kopia av paketet MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="e32b2-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="e32b2-139">Köra skript mot Finance and Operations-databasen</span><span class="sxs-lookup"><span data-stu-id="e32b2-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="e32b2-140">Kör följande skript mot Finance and Operations-databasen (inte mot finansiella rapporteringsdatabasen).</span><span class="sxs-lookup"><span data-stu-id="e32b2-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="e32b2-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="e32b2-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="e32b2-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="e32b2-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="e32b2-143">Dessa skript ser till att inställningar för användare, roller och ändringsspårning är korrekta.</span><span class="sxs-lookup"><span data-stu-id="e32b2-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="e32b2-144">Köra PowerShell-kommando för att återställa databasen</span><span class="sxs-lookup"><span data-stu-id="e32b2-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="e32b2-145">Kör följande kommandon på AOS-datorn i PowerShell eller som administratör om du vill återställa integreringen mellan Finance and Operations och finansiell rapportering:</span><span class="sxs-lookup"><span data-stu-id="e32b2-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="e32b2-146">När du har kört kommandona kommer du att ombedjas trycka på "Y" för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="e32b2-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="e32b2-147">Beskrivning av parametrarna:</span><span class="sxs-lookup"><span data-stu-id="e32b2-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="e32b2-148">Giltiga värden för -Reason är: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="e32b2-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="e32b2-149">Parametern -ReasonDetail är fritext.</span><span class="sxs-lookup"><span data-stu-id="e32b2-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="e32b2-150">Reason och reasonDetail registreras övervaka telemetri/miljö-övervakning.</span><span class="sxs-lookup"><span data-stu-id="e32b2-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="e32b2-151">Starta tjänster</span><span class="sxs-lookup"><span data-stu-id="e32b2-151">Start services</span></span>
<span data-ttu-id="e32b2-152">Använd services.msc för att starta om tjänsterna som du tidigare har stoppat:</span><span class="sxs-lookup"><span data-stu-id="e32b2-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="e32b2-153">World wide web publishing service (gäller alla AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="e32b2-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="e32b2-155">Management Reporter 2012 processtjänst (endast på BI-datorer)</span><span class="sxs-lookup"><span data-stu-id="e32b2-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="e32b2-156">Importera rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="e32b2-156">Import report definitions</span></span>
<span data-ttu-id="e32b2-157">Importera dina rapportdesigner från Report Designer med den fil som skapades vid exporten:</span><span class="sxs-lookup"><span data-stu-id="e32b2-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="e32b2-158">I Report Designer, gå till **Företag** &gt; **Grupper för byggblock**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="e32b2-159">Välj den grupp med byggblock som du vill exportera och klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="e32b2-160">För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="e32b2-161">Välj byggblocket **Standard** och klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="e32b2-162">Välj filen som innehåller de exporterade rapportdefinitionerna och klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="e32b2-163">I dialogrutan Importera väljer du de rapportdefinitioner som du vill importera:</span><span class="sxs-lookup"><span data-stu-id="e32b2-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="e32b2-164">Klicka på **Markera alla** om du vill importera alla rapportdefinitioner och stödjande byggblock.</span><span class="sxs-lookup"><span data-stu-id="e32b2-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="e32b2-165">Om du vill importera specifika rapporter väljer du de rader, kolumner, träd eller dimensionsuppsättningar som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="e32b2-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="e32b2-166">Klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="e32b2-166">Click **Import**.</span></span>





