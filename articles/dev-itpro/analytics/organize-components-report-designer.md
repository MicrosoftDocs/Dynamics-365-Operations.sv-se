---
title: Organisera rapportdelar i rapportdesignern
description: När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna. Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3f2b34cccfd84a9e4bb76e7a1da64e5cefa9982e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551753"
---
# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="74464-104">Organisera rapportdelar i rapportdesignern</span><span class="sxs-lookup"><span data-stu-id="74464-104">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74464-105">När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna.</span><span class="sxs-lookup"><span data-stu-id="74464-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="74464-106">Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.</span><span class="sxs-lookup"><span data-stu-id="74464-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="74464-107">Du kan ändra namn på mappar, rapporter, byggblock och andra objekt i rapportdesignern för att organisera dina filer.</span><span class="sxs-lookup"><span data-stu-id="74464-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="74464-108">Beroende på vilken typ av objekt du byter namn på måste du kanske uppdatera associationer till det objektet.</span><span class="sxs-lookup"><span data-stu-id="74464-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="74464-109">Ändra namn på en mapp eller byggsten i Report Designer</span><span class="sxs-lookup"><span data-stu-id="74464-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="74464-110">I Report Designer kan du byta namn på mappar, rapportdefinitioner, raddefinitioner, kolumndefinitioner och rapportträdsdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="74464-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="74464-111">Byta namn på en mapp eller ett byggblock i Report Designer</span><span class="sxs-lookup"><span data-stu-id="74464-111">Rename a folder or building block in Report Designer</span></span>

1. <span data-ttu-id="74464-112">Använd navigeringsfönstret i Report Designer när du ska leta rätt på den mapp eller det objekt som du ska byta namn på.</span><span class="sxs-lookup"><span data-stu-id="74464-112">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2. <span data-ttu-id="74464-113">Högerklicka på mappen eller objekt och klicka sedan på **Ändra namn**.</span><span class="sxs-lookup"><span data-stu-id="74464-113">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="74464-114">Fältet **Namn** i navigeringsfönstret blir tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="74464-114">The **Name** field in the navigation pane becomes available.</span></span>
3. <span data-ttu-id="74464-115">Skriv in ett nytt namn och tryck sedan på Enter.</span><span class="sxs-lookup"><span data-stu-id="74464-115">Type a new name, and then press Enter.</span></span>
4. <span data-ttu-id="74464-116">Om byggblocket är en raddefinition, kolumndefinition eller rapportträdsdefinition måste du uppdatera andra byggblock som är kopplade till objektet.</span><span class="sxs-lookup"><span data-stu-id="74464-116">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="74464-117">Högerklicka på byggblocket du bytte namn i steg 3, välj **Associationer** och välj sedan ett alternativ i listan om du vill uppdatera det.</span><span class="sxs-lookup"><span data-stu-id="74464-117">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5. <span data-ttu-id="74464-118">Upprepa steg 4 tills alla tillhörande artiklar uppdateras.</span><span class="sxs-lookup"><span data-stu-id="74464-118">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="74464-119">Skapa och hantera grupper</span><span class="sxs-lookup"><span data-stu-id="74464-119">Create and manage report groups</span></span>
<span data-ttu-id="74464-120">Du kan gruppera rapportdefinitioner för att skapa flera rapporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="74464-120">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="74464-121">För att skapa, ändra, ta bort och skapa rapportgrupper måste du ha rollen designer eller administratör.</span><span class="sxs-lookup"><span data-stu-id="74464-121">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="74464-122">Användare med rollen generator kan skapa rapportgrupper och även ändra rapportdefinitioners inställningar för rapportgrupper.</span><span class="sxs-lookup"><span data-stu-id="74464-122">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="74464-123">Skapa en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="74464-123">Create a report group</span></span>

1. <span data-ttu-id="74464-124">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74464-124">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74464-125">På menyn **Arkiv** klickar du på **Ny** &gt; **Rapportgruppsdefinition** för att öppna en ny rapportgrupp i visningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74464-125">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="74464-126">Du kan även klicka på knappen **Rapportgrupp** ![Rapportgrupp](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Rapportgrupp") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="74464-126">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3. <span data-ttu-id="74464-127">Klicka på fliken **Rapportgrupp**. För att åsidosätta informationen om de enskilda rapportdefinitionerna genereringen av denna rapport väljer du kryssrutan **Åsidosätt företags-, informations- och datuminställningar från individuella rapportdefinitioner**.</span><span class="sxs-lookup"><span data-stu-id="74464-127">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="74464-128">Företagets namn, detaljnivå, preliminär inställning och datuminformation fylls i automatiskt, men du kan fortfarande göra uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="74464-128">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4. <span data-ttu-id="74464-129">Välj kryssrutan **Inkludera alla rapporteringsvalutor** om du vill skapa fler rapporter som visar vilken valuta som används i rapporten.</span><span class="sxs-lookup"><span data-stu-id="74464-129">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="74464-130">Du kan komma åt flera vyer genom att klicka på knappen **Valuta** i Web Viewer när du visar rapporten.</span><span class="sxs-lookup"><span data-stu-id="74464-130">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5. <span data-ttu-id="74464-131">I fältet **Rapporter i grupp** klickar du på **Lägg till** för att välja rapporter som ska ingå i rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="74464-131">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="74464-132">Om du vill välja flera rapporter i dialogrutan **Lägg till** kan du hålla ned Ctrl-tangenten samtidigt som du markerar rapporter.</span><span class="sxs-lookup"><span data-stu-id="74464-132">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="74464-133">När du är klar med att välja rapporter klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="74464-133">When you've finished selecting reports, click **OK**.</span></span>
6. <span data-ttu-id="74464-134">Klicka på **Arkiv** &gt; **Spara** för att spara den nya rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="74464-134">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="74464-135">Ändra en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="74464-135">Modify a report group</span></span>

1. <span data-ttu-id="74464-136">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74464-136">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74464-137">Dubbelklicka på rapportgruppen att modifiera.</span><span class="sxs-lookup"><span data-stu-id="74464-137">Double-click the report group to modify.</span></span>
3. <span data-ttu-id="74464-138">Klicka på fliken **Rapportgrupp** och utför valfria ändringar.</span><span class="sxs-lookup"><span data-stu-id="74464-138">On the **Report Group** tab, make the changes that you want.</span></span>
4. <span data-ttu-id="74464-139">På menyn **Arkiv** klickar du på **Spara** för att spara den ändrade rapportgruppen. Du kan också klicka på knappen **Spara** ![Spara](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Spara") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="74464-139">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

> <span data-ttu-id="74464-140">Om du har schemalagda rapporter som skapas vid inställda intervall kan du åsidosätta dessa inställningar och skapa en rapport direkt.</span><span class="sxs-lookup"><span data-stu-id="74464-140">[NOTE] If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="74464-141">Skapar en rapportgruppsrapport</span><span class="sxs-lookup"><span data-stu-id="74464-141">Generate a report group report</span></span>

1. <span data-ttu-id="74464-142">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74464-142">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74464-143">Öppna rapportgruppen att skapa.</span><span class="sxs-lookup"><span data-stu-id="74464-143">Open the report group to generate.</span></span>
3. <span data-ttu-id="74464-144">Klicka på knappen **Skapa rapport** ![Skapa rapport](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Skapa rapport") för att skapa rapporter.</span><span class="sxs-lookup"><span data-stu-id="74464-144">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="74464-145">Ta bort en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="74464-145">Delete a report group</span></span>

1. <span data-ttu-id="74464-146">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74464-146">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74464-147">Högerklicka på rapportgruppen och välj sedan **Ta bort** för att ta bort.</span><span class="sxs-lookup"><span data-stu-id="74464-147">Right-click the report group to delete, and then select **Delete**.</span></span>
3. <span data-ttu-id="74464-148">När ett bekräftelsemeddelande visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="74464-148">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="74464-149">Flikkontroller för Rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="74464-149">Report Group tab controls</span></span>
<span data-ttu-id="74464-150">I följande tabell hittar du beskrivningar av kontrollerna på fliken **Rapportgrupp**.</span><span class="sxs-lookup"><span data-stu-id="74464-150">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="74464-151">Kontroll</span><span class="sxs-lookup"><span data-stu-id="74464-151">Control</span></span></th>
<th><span data-ttu-id="74464-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74464-152">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="74464-153">Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="74464-153">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="74464-154">Markera den här kryssrutan för att åsidosätta individuella rapportdefinitioner av rapporter i denna rapport för generering av dessa rapporter.</span><span class="sxs-lookup"><span data-stu-id="74464-154">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74464-155">Företagets namn</span><span class="sxs-lookup"><span data-stu-id="74464-155">Company name</span></span></td>
<td><span data-ttu-id="74464-156">Välj företag att använda för rapporter.</span><span class="sxs-lookup"><span data-stu-id="74464-156">Select the company to use for the reports.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74464-157">Detaljnivå</span><span class="sxs-lookup"><span data-stu-id="74464-157">Detail level</span></span></td>
<td><span data-ttu-id="74464-158">Ange vilken detaljnivå rapporten ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="74464-158">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="74464-159"><strong>Ekonomisk</strong> – En sammanfattningsrapport på hög nivå.</span><span class="sxs-lookup"><span data-stu-id="74464-159"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="74464-160">Du kan inte detaljgranska till konton och dimensioner, förutom i dem som det finns konton och dimensioner tillagda för i rapportträdet.</span><span class="sxs-lookup"><span data-stu-id="74464-160">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="74464-161"><strong>Ekonomisk &amp; Konto</strong> − En rapport som innehåller en sammanfattning på hög nivå och kontodetaljer.</span><span class="sxs-lookup"><span data-stu-id="74464-161"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="74464-162"><strong>Ekonomisk, Konto &amp; Transaktion</strong> − En rapport som innehåller en sammanfattning på hög nivå och transaktionsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="74464-162"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74464-163">Preliminära</span><span class="sxs-lookup"><span data-stu-id="74464-163">Provisional</span></span></td>
<td><span data-ttu-id="74464-164">Ange vilka typer av aktiviteter rapporterna ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="74464-164">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="74464-165"><strong>Endast bokförd aktivitet</strong> – Inkludera endast bokförda transaktioner och saldon i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="74464-165"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="74464-166"><strong>Bokförd och icke bokförd aktivitet</strong> – Inkludera alla inmatade och bokförda transaktioner och saldon i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="74464-166"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="74464-167"><strong>Endast icke bokförd aktivitet</strong> – Inkludera endast inmatade, men ännu ej bokförda, transaktioner i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="74464-167"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74464-168">Inkluderar alla rapporteringsvalutor</span><span class="sxs-lookup"><span data-stu-id="74464-168">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="74464-169">Om ytterligare rapporteringsvalutor som är konfigurerade i ditt Microsoft Dynamics ERP-system kommer att visas här.</span><span class="sxs-lookup"><span data-stu-id="74464-169">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="74464-170">Välj den här kryssrutan om du vill ha skapa fler rapporter i de valutor som anges.</span><span class="sxs-lookup"><span data-stu-id="74464-170">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="74464-171">Klicka på <strong>Valuta</strong> och välj en valuta om du vill visa rapporterna i Web Viewer.</span><span class="sxs-lookup"><span data-stu-id="74464-171">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74464-172">Datuminformation sparas inte med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="74464-172">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="74464-173">Basperiod</span><span class="sxs-lookup"><span data-stu-id="74464-173">Base period</span></span></li>
<li><span data-ttu-id="74464-174">Basår</span><span class="sxs-lookup"><span data-stu-id="74464-174">Base year</span></span></li>
<li><span data-ttu-id="74464-175">Period</span><span class="sxs-lookup"><span data-stu-id="74464-175">Period covered</span></span></li>
</ul>
<span data-ttu-id="74464-176">Endast standardbasperiodinställningar sparas tillsammans med rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="74464-176">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74464-177">Datuminformation sparas med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="74464-177">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="74464-178">Rapportdatum</span><span class="sxs-lookup"><span data-stu-id="74464-178">Report date</span></span></li>
<li><span data-ttu-id="74464-179">Standardbasperioden</span><span class="sxs-lookup"><span data-stu-id="74464-179">Default base period</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74464-180">Rapporter i grupp</span><span class="sxs-lookup"><span data-stu-id="74464-180">Reports in group</span></span></td>
<td><span data-ttu-id="74464-181">Lägg till, ta bort och ordna om rapporter i rapporten.</span><span class="sxs-lookup"><span data-stu-id="74464-181">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="74464-182">Om du vill lägga till rapportdefinitioner i rapportgruppen dubbelklickar du på rapportgruppen för att öppna den och klickar sedan på <strong>Lägg till</strong>.</span><span class="sxs-lookup"><span data-stu-id="74464-182">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="74464-183">Välj de rapporter som du vill ta med i rapportgruppen och klicka på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="74464-183">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="74464-184">Om du vill ta bort en rapport från rapportgruppen väljer du den och klickar på <strong>Ta bort</strong>.</span><span class="sxs-lookup"><span data-stu-id="74464-184">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="74464-185">Om du vill ändra i vilken ordning rapporterna skapas, välj en rapport i listan och sedan klicka på <strong>Flytta upp</strong> eller <strong>Flytta ned</strong>.</span><span class="sxs-lookup"><span data-stu-id="74464-185">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="74464-186">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="74464-186">Additional resources</span></span>

[<span data-ttu-id="74464-187">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="74464-187">Financial reporting</span></span>](financial-reporting-intro.md)
