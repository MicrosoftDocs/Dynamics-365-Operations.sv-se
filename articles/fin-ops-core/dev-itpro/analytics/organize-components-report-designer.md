---
title: Organisera rapportdelar i rapportdesignern
description: Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d348993422b24776098657dcef25a088ba2f826b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564553"
---
# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="aafab-103">Organisera rapportdelar i rapportdesignern</span><span class="sxs-lookup"><span data-stu-id="aafab-103">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aafab-104">När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna.</span><span class="sxs-lookup"><span data-stu-id="aafab-104">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="aafab-105">Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.</span><span class="sxs-lookup"><span data-stu-id="aafab-105">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="aafab-106">Du kan ändra namn på mappar, rapporter, byggblock och andra objekt i rapportdesignern för att organisera dina filer.</span><span class="sxs-lookup"><span data-stu-id="aafab-106">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="aafab-107">Beroende på vilken typ av objekt du byter namn på måste du kanske uppdatera associationer till det objektet.</span><span class="sxs-lookup"><span data-stu-id="aafab-107">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="aafab-108">Ändra namn på en mapp eller byggsten i Report Designer</span><span class="sxs-lookup"><span data-stu-id="aafab-108">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="aafab-109">I Report Designer kan du byta namn på mappar, rapportdefinitioner, raddefinitioner, kolumndefinitioner och rapportträdsdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="aafab-109">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="aafab-110">Byta namn på en mapp eller ett byggblock i Report Designer</span><span class="sxs-lookup"><span data-stu-id="aafab-110">Rename a folder or building block in Report Designer</span></span>

1. <span data-ttu-id="aafab-111">Använd navigeringsfönstret i Report Designer när du ska leta rätt på den mapp eller det objekt som du ska byta namn på.</span><span class="sxs-lookup"><span data-stu-id="aafab-111">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2. <span data-ttu-id="aafab-112">Högerklicka på mappen eller objekt och klicka sedan på **Ändra namn**.</span><span class="sxs-lookup"><span data-stu-id="aafab-112">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="aafab-113">Fältet **Namn** i navigeringsfönstret blir tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="aafab-113">The **Name** field in the navigation pane becomes available.</span></span>
3. <span data-ttu-id="aafab-114">Skriv in ett nytt namn och tryck sedan på Enter.</span><span class="sxs-lookup"><span data-stu-id="aafab-114">Type a new name, and then press Enter.</span></span>
4. <span data-ttu-id="aafab-115">Om byggblocket är en raddefinition, kolumndefinition eller rapportträdsdefinition måste du uppdatera andra byggblock som är kopplade till objektet.</span><span class="sxs-lookup"><span data-stu-id="aafab-115">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="aafab-116">Högerklicka på byggblocket du bytte namn i steg 3, välj **Associationer** och välj sedan ett alternativ i listan om du vill uppdatera det.</span><span class="sxs-lookup"><span data-stu-id="aafab-116">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5. <span data-ttu-id="aafab-117">Upprepa steg 4 tills alla tillhörande artiklar uppdateras.</span><span class="sxs-lookup"><span data-stu-id="aafab-117">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="aafab-118">Skapa och hantera grupper</span><span class="sxs-lookup"><span data-stu-id="aafab-118">Create and manage report groups</span></span>
<span data-ttu-id="aafab-119">Du kan gruppera rapportdefinitioner för att skapa flera rapporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="aafab-119">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="aafab-120">För att skapa, ändra, ta bort och skapa rapportgrupper måste du ha rollen designer eller administratör.</span><span class="sxs-lookup"><span data-stu-id="aafab-120">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="aafab-121">Användare med rollen generator kan skapa rapportgrupper och även ändra rapportdefinitioners inställningar för rapportgrupper.</span><span class="sxs-lookup"><span data-stu-id="aafab-121">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="aafab-122">Skapa en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="aafab-122">Create a report group</span></span>

1. <span data-ttu-id="aafab-123">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aafab-123">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="aafab-124">På menyn **Arkiv** klickar du på **Ny** &gt; **Rapportgruppsdefinition** för att öppna en ny rapportgrupp i visningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aafab-124">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="aafab-125">Du kan även klicka på knappen **Rapportgrupp** ![Rapportgrupp](media/report-group.gif "Rapportgrupp") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="aafab-125">Alternatively, click the **Report Group** button ![Report Group](media/report-group.gif "Report Group") on the toolbar.</span></span>
3. <span data-ttu-id="aafab-126">Klicka på fliken **Rapportgrupp**. För att åsidosätta informationen om de enskilda rapportdefinitionerna genereringen av denna rapport väljer du kryssrutan **Åsidosätt företags-, informations- och datuminställningar från individuella rapportdefinitioner**.</span><span class="sxs-lookup"><span data-stu-id="aafab-126">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="aafab-127">Företagets namn, detaljnivå, preliminär inställning och datuminformation fylls i automatiskt, men du kan fortfarande göra uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="aafab-127">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4. <span data-ttu-id="aafab-128">Välj kryssrutan **Inkludera alla rapporteringsvalutor** om du vill skapa fler rapporter som visar vilken valuta som används i rapporten.</span><span class="sxs-lookup"><span data-stu-id="aafab-128">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="aafab-129">Du kan komma åt flera vyer genom att klicka på knappen **Valuta** i Web Viewer när du visar rapporten.</span><span class="sxs-lookup"><span data-stu-id="aafab-129">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5. <span data-ttu-id="aafab-130">I fältet **Rapporter i grupp** klickar du på **Lägg till** för att välja rapporter som ska ingå i rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="aafab-130">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="aafab-131">Om du vill välja flera rapporter i dialogrutan **Lägg till** kan du hålla ned Ctrl-tangenten samtidigt som du markerar rapporter.</span><span class="sxs-lookup"><span data-stu-id="aafab-131">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="aafab-132">När du är klar med att välja rapporter klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="aafab-132">When you've finished selecting reports, click **OK**.</span></span>
6. <span data-ttu-id="aafab-133">Klicka på **Arkiv** &gt; **Spara** för att spara den nya rapportgruppen.</span><span class="sxs-lookup"><span data-stu-id="aafab-133">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="aafab-134">Ändra en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="aafab-134">Modify a report group</span></span>

1. <span data-ttu-id="aafab-135">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aafab-135">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="aafab-136">Dubbelklicka på rapportgruppen att modifiera.</span><span class="sxs-lookup"><span data-stu-id="aafab-136">Double-click the report group to modify.</span></span>
3. <span data-ttu-id="aafab-137">Klicka på fliken **Rapportgrupp** och utför valfria ändringar.</span><span class="sxs-lookup"><span data-stu-id="aafab-137">On the **Report Group** tab, make the changes that you want.</span></span>
4. <span data-ttu-id="aafab-138">På menyn **Arkiv** klickar du på **Spara** för att spara den ändrade rapportgruppen. Du kan också klicka på knappen **Spara** ![Spara](media/save.gif "Spara") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="aafab-138">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](media/save.gif "Save") on the toolbar.</span></span>

> <span data-ttu-id="aafab-139">Om du har schemalagda rapporter som skapas vid inställda intervall kan du åsidosätta dessa inställningar och skapa en rapport direkt.</span><span class="sxs-lookup"><span data-stu-id="aafab-139">[NOTE] If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="aafab-140">Skapar en rapportgruppsrapport</span><span class="sxs-lookup"><span data-stu-id="aafab-140">Generate a report group report</span></span>

1. <span data-ttu-id="aafab-141">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aafab-141">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="aafab-142">Öppna rapportgruppen att skapa.</span><span class="sxs-lookup"><span data-stu-id="aafab-142">Open the report group to generate.</span></span>
3. <span data-ttu-id="aafab-143">Klicka på knappen **Generera rapport** ![Generera rapport](media/generate-report.gif "Generera rapport") för att generera rapporter.</span><span class="sxs-lookup"><span data-stu-id="aafab-143">Click the **Generate Report** button ![Generate Report](media/generate-report.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="aafab-144">Ta bort en rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="aafab-144">Delete a report group</span></span>

1. <span data-ttu-id="aafab-145">Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aafab-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="aafab-146">Högerklicka på rapportgruppen och välj sedan **Ta bort** för att ta bort.</span><span class="sxs-lookup"><span data-stu-id="aafab-146">Right-click the report group to delete, and then select **Delete**.</span></span>
3. <span data-ttu-id="aafab-147">När ett bekräftelsemeddelande visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aafab-147">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="aafab-148">Flikkontroller för Rapportgrupp</span><span class="sxs-lookup"><span data-stu-id="aafab-148">Report Group tab controls</span></span>
<span data-ttu-id="aafab-149">I följande tabell hittar du beskrivningar av kontrollerna på fliken **Rapportgrupp**.</span><span class="sxs-lookup"><span data-stu-id="aafab-149">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="aafab-150">Kontroll</span><span class="sxs-lookup"><span data-stu-id="aafab-150">Control</span></span></th>
<th><span data-ttu-id="aafab-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aafab-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="aafab-152">Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner</span><span class="sxs-lookup"><span data-stu-id="aafab-152">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="aafab-153">Markera den här kryssrutan för att åsidosätta individuella rapportdefinitioner av rapporter i denna rapport för generering av dessa rapporter.</span><span class="sxs-lookup"><span data-stu-id="aafab-153">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-154">Företagets namn</span><span class="sxs-lookup"><span data-stu-id="aafab-154">Company name</span></span></td>
<td><span data-ttu-id="aafab-155">Välj företag att använda för rapporter.</span><span class="sxs-lookup"><span data-stu-id="aafab-155">Select the company to use for the reports.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-156">Detaljnivå</span><span class="sxs-lookup"><span data-stu-id="aafab-156">Detail level</span></span></td>
<td><span data-ttu-id="aafab-157">Ange vilken detaljnivå rapporten ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="aafab-157">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="aafab-158"><strong>Ekonomisk</strong> – En sammanfattningsrapport på hög nivå.</span><span class="sxs-lookup"><span data-stu-id="aafab-158"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="aafab-159">Du kan inte detaljgranska till konton och dimensioner, förutom i dem som det finns konton och dimensioner tillagda för i rapportträdet.</span><span class="sxs-lookup"><span data-stu-id="aafab-159">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="aafab-160"><strong>Ekonomisk &amp; Konto</strong> − En rapport som innehåller en sammanfattning på hög nivå och kontodetaljer.</span><span class="sxs-lookup"><span data-stu-id="aafab-160"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="aafab-161"><strong>Ekonomisk, Konto &amp; Transaktion</strong> − En rapport som innehåller en sammanfattning på hög nivå och transaktionsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="aafab-161"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-162">Preliminära</span><span class="sxs-lookup"><span data-stu-id="aafab-162">Provisional</span></span></td>
<td><span data-ttu-id="aafab-163">Ange vilka typer av aktiviteter rapporterna ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="aafab-163">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="aafab-164"><strong>Endast bokförd aktivitet</strong> – Inkludera endast bokförda transaktioner och saldon i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="aafab-164"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="aafab-165"><strong>Bokförd och icke bokförd aktivitet</strong> – Inkludera alla inmatade och bokförda transaktioner och saldon i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="aafab-165"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="aafab-166"><strong>Endast icke bokförd aktivitet</strong> – Inkludera endast inmatade, men ännu ej bokförda, transaktioner i aktuella ekonomidata.</span><span class="sxs-lookup"><span data-stu-id="aafab-166"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-167">Inkluderar alla rapporteringsvalutor</span><span class="sxs-lookup"><span data-stu-id="aafab-167">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="aafab-168">Om ytterligare rapporteringsvalutor som är konfigurerade i ditt Microsoft Dynamics ERP-system kommer att visas här.</span><span class="sxs-lookup"><span data-stu-id="aafab-168">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="aafab-169">Välj den här kryssrutan om du vill ha skapa fler rapporter i de valutor som anges.</span><span class="sxs-lookup"><span data-stu-id="aafab-169">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="aafab-170">Klicka på <strong>Valuta</strong> och välj en valuta om du vill visa rapporterna i Web Viewer.</span><span class="sxs-lookup"><span data-stu-id="aafab-170">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-171">Datuminformation sparas inte med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="aafab-171">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="aafab-172">Basperiod</span><span class="sxs-lookup"><span data-stu-id="aafab-172">Base period</span></span></li>
<li><span data-ttu-id="aafab-173">Basår</span><span class="sxs-lookup"><span data-stu-id="aafab-173">Base year</span></span></li>
<li><span data-ttu-id="aafab-174">Period</span><span class="sxs-lookup"><span data-stu-id="aafab-174">Period covered</span></span></li>
</ul>
<span data-ttu-id="aafab-175">Endast standardbasperiodinställningar sparas tillsammans med rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="aafab-175">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-176">Datuminformation sparas med rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="aafab-176">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="aafab-177">Rapportdatum</span><span class="sxs-lookup"><span data-stu-id="aafab-177">Report date</span></span></li>
<li><span data-ttu-id="aafab-178">Standardbasperioden</span><span class="sxs-lookup"><span data-stu-id="aafab-178">Default base period</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="aafab-179">Rapporter i grupp</span><span class="sxs-lookup"><span data-stu-id="aafab-179">Reports in group</span></span></td>
<td><span data-ttu-id="aafab-180">Lägg till, ta bort och ordna om rapporter i rapporten.</span><span class="sxs-lookup"><span data-stu-id="aafab-180">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="aafab-181">Om du vill lägga till rapportdefinitioner i rapportgruppen dubbelklickar du på rapportgruppen för att öppna den och klickar sedan på <strong>Lägg till</strong>.</span><span class="sxs-lookup"><span data-stu-id="aafab-181">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="aafab-182">Välj de rapporter som du vill ta med i rapportgruppen och klicka på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="aafab-182">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="aafab-183">Om du vill ta bort en rapport från rapportgruppen väljer du den och klickar på <strong>Ta bort</strong>.</span><span class="sxs-lookup"><span data-stu-id="aafab-183">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="aafab-184">Om du vill ändra i vilken ordning rapporterna skapas, välj en rapport i listan och sedan klicka på <strong>Flytta upp</strong> eller <strong>Flytta ned</strong>.</span><span class="sxs-lookup"><span data-stu-id="aafab-184">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="aafab-185">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="aafab-185">Additional resources</span></span>

[<span data-ttu-id="aafab-186">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="aafab-186">Financial reporting</span></span>](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]