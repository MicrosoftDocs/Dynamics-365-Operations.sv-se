---
title: Organisera rapportdelar i rapportdesignern
description: "När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna. Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fade9e2acdb94daa6a908d949c578fd7ed439882
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="cd10e-104">Organisera rapportdelar i rapportdesignern</span><span class="sxs-lookup"><span data-stu-id="cd10e-104">Organize report components in report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cd10e-105">När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna.</span><span class="sxs-lookup"><span data-stu-id="cd10e-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="cd10e-106">Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.</span><span class="sxs-lookup"><span data-stu-id="cd10e-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="cd10e-107">Du kan ändra namn på mappar, rapporter, byggblock och andra objekt i rapportdesignern för att organisera dina filer.</span><span class="sxs-lookup"><span data-stu-id="cd10e-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="cd10e-108">Beroende på vilken typ av objekt du byter namn på måste du kanske uppdatera associationer till det objektet.</span><span class="sxs-lookup"><span data-stu-id="cd10e-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="cd10e-109">Ändra namn på en mapp eller byggsten i Report Designer</span><span class="sxs-lookup"><span data-stu-id="cd10e-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="cd10e-110">I Report Designer kan du ändra namn på mappar, rapportdefinitioner, raddefinitioner, kolumndefinitioner och rapportträddefinitioner.</span><span class="sxs-lookup"><span data-stu-id="cd10e-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="cd10e-111">**Obs!** Om du byter namn på ett byggblock måste du uppdatera alla rapportdefinitioner som använder byggblocket.</span><span class="sxs-lookup"><span data-stu-id="cd10e-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="cd10e-112">I annat fall kan ingen ny rapport skapas.</span><span class="sxs-lookup"><span data-stu-id="cd10e-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="cd10e-113">Ändra namn på en mapp eller byggsten i Report Designer</span><span class="sxs-lookup"><span data-stu-id="cd10e-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="cd10e-114">I Report Designer, använd navigeringsrutan för att hitta mappen eller objektet du vill byta namn på.</span><span class="sxs-lookup"><span data-stu-id="cd10e-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="cd10e-115">Högerklicka på mappen eller objekt och klicka sedan på **Ändra namn**.</span><span class="sxs-lookup"><span data-stu-id="cd10e-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="cd10e-116">Fältet **Namn** i navigeringsfönstret blir tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="cd10e-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="cd10e-117">Skriv in ett nytt namn och tryck sedan på Retur.</span><span class="sxs-lookup"><span data-stu-id="cd10e-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="cd10e-118">Om byggblocket är en raddefinition, kolumndefinition eller rapportträdsdefinition måste du uppdatera andra byggblock som är kopplade till objektet.</span><span class="sxs-lookup"><span data-stu-id="cd10e-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="cd10e-119">Högerklicka på byggblocket du bytte namn i steg 3, välj **Associationer** och välj sedan ett alternativ i listan om du vill uppdatera det.</span><span class="sxs-lookup"><span data-stu-id="cd10e-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="cd10e-120">Upprepa steg 4 tills alla tillhörande artiklar uppdateras.</span><span class="sxs-lookup"><span data-stu-id="cd10e-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="cd10e-121">Skapa och hantera grupper</span><span class="sxs-lookup"><span data-stu-id="cd10e-121">Create and manage report groups</span></span>
<span data-ttu-id="cd10e-122">Du kan gruppera rapportdefinitioner för att generera flera rapporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="cd10e-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="cd10e-123">För att skapa, ändra, ta bort och skapa rapportgrupper måste du ha rollen designer eller administratör.</span><span class="sxs-lookup"><span data-stu-id="cd10e-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="cd10e-124">Användare med rollen generator kan skapa rapportgrupper och även ändra rapportdefinitioners inställningar för rapportgrupper.</span><span class="sxs-lookup"><span data-stu-id="cd10e-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="cd10e-125">Skapa en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="cd10e-125">Create a report group</span></span>

1.  <span data-ttu-id="cd10e-126">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd10e-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="cd10e-127">På menyn **Arkiv** klickar du på **Ny** &gt; **Rapportgruppsdefinition** för att öppna en ny rapportgrupp i visningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd10e-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="cd10e-128">Du kan även klicka på knappen **Rapportgrupp** ![Rapportgrupp](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Rapportgrupp") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="cd10e-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="cd10e-129">Klicka på **Rapportgrupp** fliken.</span><span class="sxs-lookup"><span data-stu-id="cd10e-129">Click the **Report Group** tab.</span></span> <span data-ttu-id="cd10e-130">Om du vill åsidosätta informationen om enskilda rapportdefinitioner för generering av rapporten väljer du **Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner** kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="cd10e-130">To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="cd10e-131">Företagets namn, detaljnivå, preliminär inställning och datuminformation fylls i automatiskt, men du kan fortfarande göra uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="cd10e-131">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="cd10e-132">Välj kryssrutan **Inkludera alla rapporteringsvalutor** om du vill skapa fler rapporter som visar vilken valuta som används i rapporten.</span><span class="sxs-lookup"><span data-stu-id="cd10e-132">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="cd10e-133">Du kan komma åt flera vyer genom att klicka på knappen **Valuta** i Web Viewer när du visar rapporten.</span><span class="sxs-lookup"><span data-stu-id="cd10e-133">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="cd10e-134">I fältet **Rapporter i grupp** klickar du på **Lägg till** för att välja rapporter som ska ingå i rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="cd10e-134">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="cd10e-135">Om du vill välja flera rapporter i dialogrutan **Lägg till** kan du hålla ned Ctrl-tangenten samtidigt som du markerar rapporter.</span><span class="sxs-lookup"><span data-stu-id="cd10e-135">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="cd10e-136">När du är klar med att välja rapporter klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd10e-136">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="cd10e-137">Klicka på **Arkiv** &gt; **Spara** för att spara den nya rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="cd10e-137">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="cd10e-138">Ändra en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="cd10e-138">Modify a report group</span></span>

1.  <span data-ttu-id="cd10e-139">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd10e-139">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="cd10e-140">Dubbelklicka på rapportgruppen att modifiera.</span><span class="sxs-lookup"><span data-stu-id="cd10e-140">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="cd10e-141">Klicka på fliken **Rapportgrupp** och utför valfria ändringar.</span><span class="sxs-lookup"><span data-stu-id="cd10e-141">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="cd10e-142">På menyn **Arkiv** klickar du på **Spara** för att spara den ändrade rapportgruppen. Du kan också klicka på knappen **Spara** ![Spara](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Spara") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="cd10e-142">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="cd10e-143">**Obs!** Om du har schemalagda rapporter som genereras vid inställda intervall kan du åsidosätta dessa inställningar och generera en rapport direkt.</span><span class="sxs-lookup"><span data-stu-id="cd10e-143">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="cd10e-144">Genererar en rapportgruppsrapport</span><span class="sxs-lookup"><span data-stu-id="cd10e-144">Generate a report group report</span></span>

1.  <span data-ttu-id="cd10e-145">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd10e-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="cd10e-146">Öppna rapportgruppen att generera.</span><span class="sxs-lookup"><span data-stu-id="cd10e-146">Open the report group to generate.</span></span>
3.  <span data-ttu-id="cd10e-147">Klicka på knappen **Skapa rapport** ![Skapa rapport](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Skapa rapport") för att skapa rapporter.</span><span class="sxs-lookup"><span data-stu-id="cd10e-147">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="cd10e-148">Ta bort en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="cd10e-148">Delete a report group</span></span>

1.  <span data-ttu-id="cd10e-149">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd10e-149">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="cd10e-150">Högerklicka på rapportgruppen och välj sedan **Ta bort** för att ta bort.</span><span class="sxs-lookup"><span data-stu-id="cd10e-150">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="cd10e-151">När ett bekräftelsemeddelande visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cd10e-151">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="cd10e-152">Flikkontroller för Rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="cd10e-152">Report Group tab controls</span></span>
<span data-ttu-id="cd10e-153">I följande tabell hittar du beskrivningar av kontrollerna på fliken **Rapportgrupp**.</span><span class="sxs-lookup"><span data-stu-id="cd10e-153">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd10e-154">Kontroll</span><span class="sxs-lookup"><span data-stu-id="cd10e-154">Control</span></span></th>
<th><span data-ttu-id="cd10e-155">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cd10e-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd10e-156">Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="cd10e-156">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="cd10e-157">Markera den här kryssrutan för att åsidosätta individuella rapportdefinitioner av rapporter i denna rapport för generering av dessa rapporter.</span><span class="sxs-lookup"><span data-stu-id="cd10e-157">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd10e-158">Företagets namn</span><span class="sxs-lookup"><span data-stu-id="cd10e-158">Company name</span></span></td>
<td><span data-ttu-id="cd10e-159">Välj företag att använda för rapporter.</span><span class="sxs-lookup"><span data-stu-id="cd10e-159">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd10e-160">Detaljnivå</span><span class="sxs-lookup"><span data-stu-id="cd10e-160">Detail level</span></span></td>
<td><span data-ttu-id="cd10e-161">Ange vilken detaljnivå rapporten ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="cd10e-161">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="cd10e-162"><strong>Finansiella</strong> – en hög nivå sammanfattande rapport.</span><span class="sxs-lookup"><span data-stu-id="cd10e-162"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="cd10e-163">Du kan inte detaljgranska till konton och dimensioner, förutom i dem som det finns konton och dimensioner tillagda för i rapportträdet.</span><span class="sxs-lookup"><span data-stu-id="cd10e-163">You can't drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="cd10e-164"><strong>Ekonomisk &amp; Konto</strong> − En rapport som innehåller en sammanfattning på hög nivå och kontodetaljer.</span><span class="sxs-lookup"><span data-stu-id="cd10e-164"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="cd10e-165"><strong>Ekonomisk, Konto &amp; Transaktion</strong> − En rapport som innehåller en sammanfattning på hög nivå och transaktionsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="cd10e-165"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd10e-166">Preliminära</span><span class="sxs-lookup"><span data-stu-id="cd10e-166">Provisional</span></span></td>
<td><span data-ttu-id="cd10e-167">Ange vilka typer av aktiviteter rapporterna ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="cd10e-167">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="cd10e-168"><strong>Endast bokförd aktivitet</strong> – Omfattar endast transaktioner och saldon som har bokförs i dina ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="cd10e-168"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="cd10e-169"><strong>Bokförd och okonterad aktivitet</strong> – Omfattar alla transaktioner och saldon som registreras och bokförs i dina ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="cd10e-169"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="cd10e-170"><strong>Endast okonterad aktivitet</strong> – Omfattar endast transaktioner som registrerats, men som ännu inte har bokförts i dina ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="cd10e-170"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd10e-171">Inkluderar alla rapporteringsvalutor</span><span class="sxs-lookup"><span data-stu-id="cd10e-171">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="cd10e-172">Om ytterligare rapporteringsvalutor som är konfigurerade i ditt Microsoft Dynamics ERP-system kommer att visas här.</span><span class="sxs-lookup"><span data-stu-id="cd10e-172">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="cd10e-173">Välj den här kryssrutan om du vill ha skapa fler rapporter i de valutor som anges.</span><span class="sxs-lookup"><span data-stu-id="cd10e-173">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="cd10e-174">De kan sedan visas i Web Viewer om du klickar på knappen <strong>Valuta</strong> och väljer en valuta.</span><span class="sxs-lookup"><span data-stu-id="cd10e-174">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd10e-175">Datuminformation sparas inte med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="cd10e-175">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="cd10e-176">Basperiod</span><span class="sxs-lookup"><span data-stu-id="cd10e-176">Base period</span></span></li>
<li><span data-ttu-id="cd10e-177">Basår</span><span class="sxs-lookup"><span data-stu-id="cd10e-177">Base year</span></span></li>
<li><span data-ttu-id="cd10e-178">Period</span><span class="sxs-lookup"><span data-stu-id="cd10e-178">Period covered</span></span></li>
</ul>
<span data-ttu-id="cd10e-179">Endast standardbasperiodinställningar sparas tillsammans med rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cd10e-179">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd10e-180">Datuminformation sparas med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="cd10e-180">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="cd10e-181">Rapportdatum</span><span class="sxs-lookup"><span data-stu-id="cd10e-181">Report date</span></span></li>
<li><span data-ttu-id="cd10e-182">Standardbasperioden</span><span class="sxs-lookup"><span data-stu-id="cd10e-182">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd10e-183">Rapporter i grupp</span><span class="sxs-lookup"><span data-stu-id="cd10e-183">Reports in group</span></span></td>
<td><span data-ttu-id="cd10e-184">Lägg till, ta bort och ordna om rapporter i rapporten.</span><span class="sxs-lookup"><span data-stu-id="cd10e-184">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="cd10e-185">För att lägga till rapportdefinitioner i rapporten grupp, dubbelklicka på rapportgrupp för att öppna den och klicka sedan på <strong>Lägg till</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd10e-185">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="cd10e-186">Välj de rapporter som ska ingå i rapportgrupp, och klicka sedan på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd10e-186">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="cd10e-187">För att ta bort en rapport från rapportgrupp, välj den och klicka sedan på <strong>Ta bort</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd10e-187">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="cd10e-188">Om du vill ändra i vilken ordning rapporterna skapas, välj en rapport i listan och sedan klicka på <strong>Flytta upp</strong> eller <strong>Flytta ned</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd10e-188">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="cd10e-189">Se även</span><span class="sxs-lookup"><span data-stu-id="cd10e-189">See also</span></span>
--------

[<span data-ttu-id="cd10e-190">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="cd10e-190">Financial reporting</span></span>](financial-reporting-intro.md)




