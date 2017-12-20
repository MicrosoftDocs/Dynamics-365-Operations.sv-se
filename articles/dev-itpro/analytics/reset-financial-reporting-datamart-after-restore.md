---
title: "Återställa datatorget för Financial reporting"
description: "Det här avsnittet beskriver hur du återställer datatorget för Financial reporting."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
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
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: sv-se
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="ce20c-103">Återställa datatorget för Financial reporting</span><span class="sxs-lookup"><span data-stu-id="ce20c-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ce20c-104">Det här avsnittet beskriver hur du återställer datatorget för Financial reporting för följande versioner:</span><span class="sxs-lookup"><span data-stu-id="ce20c-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="ce20c-105">Microsoft Dynamics 365 for Finance and Operations Financial Reporting, version 7.2.6.0 och senare</span><span class="sxs-lookup"><span data-stu-id="ce20c-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="ce20c-106">Microsoft Dynamics 365 for Finance and Operations Financial Reporting, version 7.0.10000.4 och senare</span><span class="sxs-lookup"><span data-stu-id="ce20c-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="ce20c-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lokal)</span><span class="sxs-lookup"><span data-stu-id="ce20c-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="ce20c-108">Om du vill ha Finance and Operations Financial reporting i version 7.2.6.0 kan du ladda ned KB 4052514 från <https://support.microsoft.com/en-us/help/4052514>.</span><span class="sxs-lookup"><span data-stu-id="ce20c-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="ce20c-109">Återställ datatorget för Financial reporting för Finance and Operations Financial reporting version 7.2.6.0 och senare</span><span class="sxs-lookup"><span data-stu-id="ce20c-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="ce20c-110">Återställ datatorget för Financial reporting via Report designer</span><span class="sxs-lookup"><span data-stu-id="ce20c-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="ce20c-111">Processens steg stöds för Finance and Operations Financial reporting, version 7.2.6.0 och senare.</span><span class="sxs-lookup"><span data-stu-id="ce20c-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="ce20c-112">Om du har en tidigare version kan du kontakta supportteamet för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="ce20c-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="ce20c-113">I vissa fall kan behöva du återställa datatorget för Financial reporting.</span><span class="sxs-lookup"><span data-stu-id="ce20c-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="ce20c-114">Du kan göra detta i Report designer-klienten.</span><span class="sxs-lookup"><span data-stu-id="ce20c-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="ce20c-115">Här följer några scenarier där du kan behöva återställa datatorget:</span><span class="sxs-lookup"><span data-stu-id="ce20c-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="ce20c-116">Databasen för Finance and Operations har återställts, men datatorgets databas återställdes inte.</span><span class="sxs-lookup"><span data-stu-id="ce20c-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="ce20c-117">Felaktiga data visas under en period.</span><span class="sxs-lookup"><span data-stu-id="ce20c-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="ce20c-118">Supporten uppmanar dig att återställa datatorget som en del av en åtgärd för felsökning.</span><span class="sxs-lookup"><span data-stu-id="ce20c-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="ce20c-119">Återställning av datatorg bör utföras endast under perioder när mängden bearbetning i databasen är liten.</span><span class="sxs-lookup"><span data-stu-id="ce20c-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="ce20c-120">Ekonomiska rapporter är inte tillgängliga under återställningen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="ce20c-121">Återställ datatorget</span><span class="sxs-lookup"><span data-stu-id="ce20c-121">Reset the data mart</span></span>

<span data-ttu-id="ce20c-122">För att återställa datatorget öppnar du menyn **Verktyg** i Report designer och väljer sedan **Återställ datatorg**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="ce20c-123">Dialogrutan som visas har två avsnitt: **Statistik** och **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="ce20c-124">[![Dialogrutan Återställ datatorg](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="ce20c-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="ce20c-125">Integrationsförsök</span><span class="sxs-lookup"><span data-stu-id="ce20c-125">Integration attempts</span></span>

<span data-ttu-id="ce20c-126">Rutnätet **Integreringsförsök** visar hur många gånger systemet har försökt att integrera transaktioner.</span><span class="sxs-lookup"><span data-stu-id="ce20c-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="ce20c-127">Systemet fortsätter att försöka integrera data under ett antal dagar om de första försöken misslyckas.</span><span class="sxs-lookup"><span data-stu-id="ce20c-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="ce20c-128">Du vet är datatorget måste återställas om antalet försök är 8 eller fler, samt om det finns många dimensionskombinations- eller transaktionsposter.</span><span class="sxs-lookup"><span data-stu-id="ce20c-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="ce20c-129">I detta fall kommer inte informationen att redovisas.</span><span class="sxs-lookup"><span data-stu-id="ce20c-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="ce20c-130">Datastatus</span><span class="sxs-lookup"><span data-stu-id="ce20c-130">Data status</span></span>

<span data-ttu-id="ce20c-131">Rutnätet **Datastatus** innehåller en ögonblicksbild av transaktioner, valutakurser och dimensionsvärden i datatorget.</span><span class="sxs-lookup"><span data-stu-id="ce20c-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="ce20c-132">Ett stort antal inaktuella poster anger att många uppdateringar till posterna har inträffat.</span><span class="sxs-lookup"><span data-stu-id="ce20c-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="ce20c-133">Detta kan leda till långsammare rapportgenerering.</span><span class="sxs-lookup"><span data-stu-id="ce20c-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="ce20c-134">Feljusterade huvudkontokategorier</span><span class="sxs-lookup"><span data-stu-id="ce20c-134">Misaligned main account categories</span></span>

<span data-ttu-id="ce20c-135">Om du använder en version som är äldre än Microsoft Dynamics 365 for Finance and Operations Financial reporting version 7.2.1 kan du komma att behöva återställa datatorget om du vill byta namn på konton och flytta konton mellan olika kontokategorier.</span><span class="sxs-lookup"><span data-stu-id="ce20c-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="ce20c-136">Dessa åtgärder kan förorsaka att huvudkontokategorier feljusteras.</span><span class="sxs-lookup"><span data-stu-id="ce20c-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="ce20c-137">Fältet **Feljusterade huvudkontokategorier** anger om du har det problemet.</span><span class="sxs-lookup"><span data-stu-id="ce20c-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="ce20c-138">Återställ datatorget i Finance and Operations Financial reporting version 7.2.6.0</span><span class="sxs-lookup"><span data-stu-id="ce20c-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="ce20c-139">För att återställa datatorget i Finance and Operations Financial reporting version 7.2.6.0 och tidigare väljer du i dialogrutan **Återställ datatorg** kryssrutan **Återställ datatorg** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="ce20c-140">Du bör endast återställa datatorget under ett schemalagt driftstopp.</span><span class="sxs-lookup"><span data-stu-id="ce20c-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="ce20c-141">[![Kryssrutan Återställ datatorg](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="ce20c-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="ce20c-142">Återställ datatorget och välj en orsak i Microsoft Dynamics 365 for Finance and Operations Financial reporting version 7.3.0</span><span class="sxs-lookup"><span data-stu-id="ce20c-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="ce20c-143">Om du upptäcker att en återställning av datatorg krävs väljer du kryssrutan **Återställ datatorg** och sedan en orsak i fältet **Orsak**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="ce20c-144">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="ce20c-144">The following options are available:</span></span>

- <span data-ttu-id="ce20c-145">**Saknade eller felaktiga data** – Utifrån statistiken har du bedömt att data kanske saknas.</span><span class="sxs-lookup"><span data-stu-id="ce20c-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="ce20c-146">Vi rekommenderar att du samarbetar med supporten för att fastställa orsaken innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="ce20c-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="ce20c-147">**Återställ databas** – Databasen för Finance and Operations har återställts, men databasen för Financial reporting återställdes inte.</span><span class="sxs-lookup"><span data-stu-id="ce20c-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="ce20c-148">**Övrigt** – Du återställer datatorget av något annat skäl.</span><span class="sxs-lookup"><span data-stu-id="ce20c-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="ce20c-149">Om du misstänker att det finns ett problem kan du kontakta supporten för att identifiera det.</span><span class="sxs-lookup"><span data-stu-id="ce20c-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="ce20c-150">Kontrollera att alla befintliga uppgifter är färdigintegrerade innan du slutför stegen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="ce20c-151">Du kan visa integrationens status genom att välja **Verktyg** &gt; **Integrationsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="ce20c-152">Rensa användare och företag</span><span class="sxs-lookup"><span data-stu-id="ce20c-152">Clear users and companies</span></span>

<span data-ttu-id="ce20c-153">Välj kryssrutan **Rensa användare och företag** om du har återställt databasen men sedan ändrat användare eller företag.</span><span class="sxs-lookup"><span data-stu-id="ce20c-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="ce20c-154">Du bör sällan få behov av att välja denna kryssruta.</span><span class="sxs-lookup"><span data-stu-id="ce20c-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="ce20c-155">Markera **OK** när du vill starta återställningen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="ce20c-156">Du uppmanas att bekräfta att du vill starta processen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="ce20c-157">Observera att Financial reporting inte är tillgängligt under återställningen och den initiala dataintegration som därefter uppstår.</span><span class="sxs-lookup"><span data-stu-id="ce20c-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="ce20c-158">Välj **Verktyg** &gt; **Integrationsstatus** för att se när integrering senast kördes, samt dess status.</span><span class="sxs-lookup"><span data-stu-id="ce20c-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="ce20c-159">[![Visa installationsstatus för integrationen](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="ce20c-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="ce20c-160">Återställ datatorget för Financial reporting för Finance and Operations Financial reporting version 7.0.10000.4 och senare</span><span class="sxs-lookup"><span data-stu-id="ce20c-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="ce20c-161">Om du återställer Finance and Operations-databasen från en säkerhetskopia eller kopierar databasen från en annan miljö måste du följa stegen i det här avsnittet i syfte att säkerställa att Financial reporting-datatorget använder den återställda Finance and Operations-databasen på ett korrekt sätt.</span><span class="sxs-lookup"><span data-stu-id="ce20c-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="ce20c-162">Observera att stegen i processen stöds för Microsoft Dynamics AX, programvaruversion 7.0.1 (maj 2016) (programversion 7.0.1265.23014 och Financial reporting, version 7.0.10000.4) och senare versioner.</span><span class="sxs-lookup"><span data-stu-id="ce20c-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="ce20c-163">Om du har en tidigare version av Finance and Operations, kontakta vårt supportteam för hjälp.</span><span class="sxs-lookup"><span data-stu-id="ce20c-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="ce20c-164">Exportera rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="ce20c-164">Export report definitions</span></span>

<span data-ttu-id="ce20c-165">Följ först dessa steg för att exportera rapportdesignen från Report designer.</span><span class="sxs-lookup"><span data-stu-id="ce20c-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="ce20c-166">I Report Designer, välj **Företag** &gt; **Grupper för byggblock**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="ce20c-167">Välj den grupp med byggblock som du vill exportera och välj sedan **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce20c-168">För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="ce20c-169">Välj de rapportdefinitioner som ska exporteras:</span><span class="sxs-lookup"><span data-stu-id="ce20c-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="ce20c-170">Om du vill exportera alla rapportdefinitioner och motsvarande byggblock väljer du **Markera alla**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="ce20c-171">Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar väljer du lämpliga flikar och sedan de artiklar du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="ce20c-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="ce20c-172">Håll knappen Ctrl intryckt för att välja flera olika artiklar i en flik. När du väljer vilka rapporter du vill exportera kommer tillhörande rader, kolumner, träd och dimensionsuppsättningar att väljas.</span><span class="sxs-lookup"><span data-stu-id="ce20c-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="ce20c-173">Välj **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-173">Select **Export**.</span></span>
5. <span data-ttu-id="ce20c-174">Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.</span><span class="sxs-lookup"><span data-stu-id="ce20c-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="ce20c-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-175">Select **Save**.</span></span>

<span data-ttu-id="ce20c-176">Du kan kopiera eller överföra filen till en säker plats.</span><span class="sxs-lookup"><span data-stu-id="ce20c-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="ce20c-177">På så sätt kan filen senare importeras till en annan miljö.</span><span class="sxs-lookup"><span data-stu-id="ce20c-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="ce20c-178">Mer information om hur du använder ett Microsoft Azure-lagringskonto finns i [Överföra data med kommandoradsverktyget AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="ce20c-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="ce20c-179">Microsoft tillhandahåller inget lagringskonto som en del av ditt Finance and Operations-avtal.</span><span class="sxs-lookup"><span data-stu-id="ce20c-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="ce20c-180">Du måste antingen köpa ett konto för lagring eller använda ett lagringskonto från en separat Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ce20c-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="ce20c-181">Var medveten om hur enheten D fungerar på virtuella Azure-datorer (VM).</span><span class="sxs-lookup"><span data-stu-id="ce20c-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="ce20c-182">Förvara inte dina exporterade byggblocksgrupper på enhet D permanent. Mer information om tillfälliga enheter finns i [Förstå temporärenheten på virtuella Windows Azure-datorer](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="ce20c-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="ce20c-183">Stoppa tjänster</span><span class="sxs-lookup"><span data-stu-id="ce20c-183">Stop services</span></span>

<span data-ttu-id="ce20c-184">Följande Microsoft Windows-tjänster har öppna anslutningar till Finance and Operations-databasen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="ce20c-185">Du måste därför använda Microsofts fjärrskrivbord för att ansluta till alla datorer i miljön och sedan stoppa dessa tjänster via services.msc.</span><span class="sxs-lookup"><span data-stu-id="ce20c-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="ce20c-186">World wide web-publiceringstjänst (gäller alla AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="ce20c-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="ce20c-188">Processtjänsten Management Reporter 2012 (endast på BI-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="ce20c-189">Återställ</span><span class="sxs-lookup"><span data-stu-id="ce20c-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="ce20c-190">Hämta det senaste MinorVersionDataUpgrade.zip-paketet</span><span class="sxs-lookup"><span data-stu-id="ce20c-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="ce20c-191">Hämta det senaste MinorVersionDataUpgrade.zip-paketet.</span><span class="sxs-lookup"><span data-stu-id="ce20c-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="ce20c-192">Instruktioner om hur du hittar och hämtar rätt version av datauppgraderingspaketet finns på[Hämta senaste distribuerbara datauppgraderingspaket](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="ce20c-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="ce20c-193">En uppgradering krävs inte för att hämta MinorVersionDataUpgrade.zip-paketet.</span><span class="sxs-lookup"><span data-stu-id="ce20c-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="ce20c-194">Därför måste du helt enkelt följa stegen i avsnittet ”Hämta senaste distribuerbara datauppgraderingspaketet”.</span><span class="sxs-lookup"><span data-stu-id="ce20c-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="ce20c-195">Du kan hoppa över de övriga stegen i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ce20c-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="ce20c-196">Kör skript mot Finance and Operations-databasen</span><span class="sxs-lookup"><span data-stu-id="ce20c-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="ce20c-197">Kör följande skript mot Finance and Operations-databasen (inte mot Financial reporting.databasen):</span><span class="sxs-lookup"><span data-stu-id="ce20c-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="ce20c-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="ce20c-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="ce20c-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="ce20c-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="ce20c-200">Dessa skript bidrar till att inställningar för användare, roller och ändringsspårning är korrekta.</span><span class="sxs-lookup"><span data-stu-id="ce20c-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="ce20c-201">Kör ett Windows PowerShell-kommando för att återställa databasen</span><span class="sxs-lookup"><span data-stu-id="ce20c-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="ce20c-202">Starta Microsoft Windows PowerShell som administratör på AOS-datorn om du vill återställa integreringen mellan Finance and Operations och Financial reporting.</span><span class="sxs-lookup"><span data-stu-id="ce20c-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="ce20c-203">Här följer en förklaring av parametrarna i kommandot **Återställ datatorgsintegration**:</span><span class="sxs-lookup"><span data-stu-id="ce20c-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="ce20c-204">Giltiga värden för **-Orsak** är **BEARBETNING**, **DATAFEL** samt **ÖVRIGT**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="ce20c-205">Parametern **-ReasonDetail** är fritext.</span><span class="sxs-lookup"><span data-stu-id="ce20c-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="ce20c-206">Orsaken och orsaksdetaljen registreras i telemetri-/miljöövervakningen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="ce20c-207">När du kör kommandona uppmanas du att ange **Y** för att bekräfta att du vill återställa databasen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="ce20c-208">Återstarta tjänster</span><span class="sxs-lookup"><span data-stu-id="ce20c-208">Restart services</span></span>

<span data-ttu-id="ce20c-209">Använd services.msc för att starta om tjänsterna som du tidigare har stoppat:</span><span class="sxs-lookup"><span data-stu-id="ce20c-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="ce20c-210">World wide web publishing service (gäller alla AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="ce20c-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="ce20c-212">Management Reporter 2012 processtjänst (endast på BI-datorer)</span><span class="sxs-lookup"><span data-stu-id="ce20c-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="ce20c-213">Importera rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="ce20c-213">Import report definitions</span></span>

<span data-ttu-id="ce20c-214">Importera dina rapportdesigner från Report designer med den fil som skapades vid exporten.</span><span class="sxs-lookup"><span data-stu-id="ce20c-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="ce20c-215">I Report Designer, välj **Företag** &gt; **Grupper för byggblock**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="ce20c-216">Välj den grupp med byggblock som du vill exportera och välj sedan **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce20c-217">För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="ce20c-218">Välj byggblocket **Standard** och klicka sedan på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="ce20c-219">Välj filen som innehåller de exporterade rapportdefinitionerna och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="ce20c-220">Välj vilka rapportdefinitioner som ska importeras i dialogrutan **Importera**:</span><span class="sxs-lookup"><span data-stu-id="ce20c-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="ce20c-221">Om du vill importera alla rapportdefinitioner och motsvarande byggblock väljer du **Markera alla**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="ce20c-222">Om du vill importera specifika rader, kolumner, träd eller dimensionsgrupper klickar du på motsvarande rapporter, rader, kolumner, träd eller dimensionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ce20c-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="ce20c-223">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="ce20c-224">Återställ datatorget för Financial reporting i Finance and Operations (lokal)</span><span class="sxs-lookup"><span data-stu-id="ce20c-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="ce20c-225">Be alla användare att avsluta Report designer och Financial reporting-avsnittet i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ce20c-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="ce20c-226">Kör följande skript mot Financial reporting-databasen (MRDB).</span><span class="sxs-lookup"><span data-stu-id="ce20c-226">Run the following script against the Financial reporting database (MRDB).</span></span>

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

3. <span data-ttu-id="ce20c-227">Trunkera eller ta bort alla poster från tabellen FINANCIALREPORTS i Finance and Operations-databasen (AXDB).</span><span class="sxs-lookup"><span data-stu-id="ce20c-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="ce20c-228">Trunkera eller ta bort alla poster från tabellen FINANCIALREPORTVERSION om denna finns i Finance and Operations-databasen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="ce20c-229">Om tabellen inte finns i databasen för Finance and Operations, hoppa då över detta steg.</span><span class="sxs-lookup"><span data-stu-id="ce20c-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="ce20c-230">Kör skriptet **ResetDatamart.sql** mot Financial reporting-databasen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="ce20c-231">Skriptet inaktiverar datatorgsintegrering, raderar all datatorgsinformation och återaktiverar sedan datatorgsintegreringen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

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

6. <span data-ttu-id="ce20c-232">Efter återställningen kan du manuellt bekräfta dataomladdningen genom att köra följande fråga mot Financial reporting-databasen.</span><span class="sxs-lookup"><span data-stu-id="ce20c-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="ce20c-233">Kontrollera att alla rader har ett **LastRunTime**-värde och att **StateType** anges som **5**.</span><span class="sxs-lookup"><span data-stu-id="ce20c-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="ce20c-234">Ett **StateType**-värde på **5** anger att datan har laddats om.</span><span class="sxs-lookup"><span data-stu-id="ce20c-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="ce20c-235">Värdet av **7** anger felstatus.</span><span class="sxs-lookup"><span data-stu-id="ce20c-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="ce20c-236">Ibland anger organisationshierarkikartan denna status första gången den körs.</span><span class="sxs-lookup"><span data-stu-id="ce20c-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="ce20c-237">Felstatusen bör emellertid lösas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ce20c-237">However, the faulted state but should be automatically resolved.</span></span>

