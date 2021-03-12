---
title: Rapporten jämföra lager för artikelpriser
description: Läs mer om hur du genererar en rapport över jämför artikelpriser och sedan bläddrar och/eller exporterar resultatet.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6554aec1991080f4a14aedb3440ff3dfd32e9b61
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983984"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="589de-103">Rapporten jämföra lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="589de-104">I det här avsnittet beskrivs hur du kör rapporten **Jämföra lager för artikelpriser** och gör utdata tillgänglig digitalt, antingen som en interaktiv sida i Dynamics 365 Supply Chain Management, eller som ett exporterat dokument i ett flertal format.</span><span class="sxs-lookup"><span data-stu-id="589de-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="589de-105">När du visar rapporten i din webbläsare, justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="589de-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="589de-106">Du kan sortera resultaten, filtrera dem, öka detaljnivån i data och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="589de-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="589de-107">Rapportresultaten lagras i dataentiteten **jämför artikelpriser**, vilket gör att du kan filtrera och exportera resultaten till ett format som t.ex. CSV eller Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="589de-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="589de-108">Rapporten **jämföra lager för artikelpriser** är användbar när utdata innehåller många rader.</span><span class="sxs-lookup"><span data-stu-id="589de-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="589de-109">Till exempel kommer utdata att innehålla många rader om du har mer än 40 000 artiklar som innehåller ett väntande artikelpris i kostnadsversionen.</span><span class="sxs-lookup"><span data-stu-id="589de-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="589de-110">Aktivera jämföra lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-110">Enable compare item prices storage</span></span>

<span data-ttu-id="589de-111">Innan du kan använda den här funktionen måste du aktivera den i ditt system.</span><span class="sxs-lookup"><span data-stu-id="589de-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="589de-112">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="589de-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="589de-113">Här visas funktionen i listan:</span><span class="sxs-lookup"><span data-stu-id="589de-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="589de-114">**Modul** - Kostnadshantering</span><span class="sxs-lookup"><span data-stu-id="589de-114">**Module** - Cost management</span></span>
- <span data-ttu-id="589de-115">**Funktionsnamn** - jämför lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="589de-116">Generera en rapport för jämföra lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="589de-117">Följ dessa steg för att skapa och lagra rapporten **jämföra lager för artikelpriser**:</span><span class="sxs-lookup"><span data-stu-id="589de-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="589de-118">Gå till **Kostnadshanterings > Förfrågningar och rapporter > Förutbestämda kostnadsrapporter > Jämföra lager för artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="589de-119">Välj **Ny** om du vill öppna fönstret **jämför artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="589de-120">Ange följande alternativ för att definiera vilka priser som ska jämföras i rapporten:</span><span class="sxs-lookup"><span data-stu-id="589de-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="589de-121">På snabbfliken **parametrar** ger du rapporten ett unikt **namn** och använder fälten i **Väntande priser som ska jämföras** och **Priser som används för jämförelsen** för att definiera vilka priser och datum som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="589de-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="589de-122">På snabbfliken **Poster som ska ingå** kan du ställa in filter och begränsningar för att definiera vilka data som ska ingå i rapporten.</span><span class="sxs-lookup"><span data-stu-id="589de-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="589de-123">På snabbfliken **kör i bakgrund** ställer du in hur, när och hur ofta du vill generera rapporten.</span><span class="sxs-lookup"><span data-stu-id="589de-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="589de-124">Den här rapporten körs alltid som en del av ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="589de-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="589de-125">Välj **OK** om du vill använda inställningarna och stänga fönstret.</span><span class="sxs-lookup"><span data-stu-id="589de-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="589de-126">När batchjobbet är klart visas det på sidan **jämföra lager för artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="589de-127">Du kanske måste uppdatera sidan om du vill visa rapporten.</span><span class="sxs-lookup"><span data-stu-id="589de-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="589de-128">Utforska en rapport för jämföra lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="589de-129">När du har genererat en rapport kan du visa och utforska den när som helst enligt följande:</span><span class="sxs-lookup"><span data-stu-id="589de-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="589de-130">Gå till **Kostnadshanterings > Förfrågningar och rapporter > Förutbestämda kostnadsrapporter > Jämföra lager för artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="589de-131">Välj en rapport i listan.</span><span class="sxs-lookup"><span data-stu-id="589de-131">Select a report from the list.</span></span>

1. <span data-ttu-id="589de-132">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="589de-132">Do one of the following:</span></span>

    - <span data-ttu-id="589de-133">Välj **översikt** om du vill få en översikt över dina rapportresultat.</span><span class="sxs-lookup"><span data-stu-id="589de-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="589de-134">Välj **Visa information** om du vill få en mer detaljerad översikt över din rapport</span><span class="sxs-lookup"><span data-stu-id="589de-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="589de-135">När den valda vyn öppnas kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="589de-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="589de-136">Välj nästan alla kolumnrubriker om du vill sortera eller filtrera tabellen efter värden i den kolumnen, på samma sätt som i de flesta standardformulär i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="589de-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="589de-137">Observera att du inte kan sortera eller filtrera kolumnen **nettoändringspris %** eftersom det är ett beräknat fält.</span><span class="sxs-lookup"><span data-stu-id="589de-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="589de-138">Välj **dimensionsvisning** om du vill öppna en ruta där du kan välja vilken dimensionskolumn som ska inkluderas i formuläret.</span><span class="sxs-lookup"><span data-stu-id="589de-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="589de-139">Ange **Spara inställning** till **Ja** om du vill spara inställningarna så att de bevaras nästa gång du öppnar rapporten.</span><span class="sxs-lookup"><span data-stu-id="589de-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="589de-140">Välj **OK** om du vill använda inställningarna och stänga.</span><span class="sxs-lookup"><span data-stu-id="589de-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="589de-141">Markera en rad i formuläret och välj sedan **Visa information** om du vill visa mer information om den valda artikeln.</span><span class="sxs-lookup"><span data-stu-id="589de-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="589de-142">Du kan gå nedåt i informationen härifrån.</span><span class="sxs-lookup"><span data-stu-id="589de-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="589de-143">Markera en rad i formuläret och välj sedan **Visa jämförelsediagram** för att se en interaktiv grafisk representation av resultaten som de är relaterade till den valda artikeln.</span><span class="sxs-lookup"><span data-stu-id="589de-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="589de-144">Du kan utforska dessa resultat genom att välja olika grafiska element i diagrammet och diagramförklaringen.</span><span class="sxs-lookup"><span data-stu-id="589de-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="589de-145">Markera en rad i formuläret och välj sedan **Visa beräkningsinformation** om du vill visa mer information beräkningar relaterade till den valda artikeln.</span><span class="sxs-lookup"><span data-stu-id="589de-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="589de-146">Du kan gå nedåt i informationen härifrån.</span><span class="sxs-lookup"><span data-stu-id="589de-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="589de-147">Exportera en rapport för jämföra lager för artikelpriser</span><span class="sxs-lookup"><span data-stu-id="589de-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="589de-148">Varje rapport som du skapar lagras i dataenheten **jämför artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="589de-149">Du kan använda de standardiserade datahanteringsfunktionerna i Supply Chain Management för att exportera data från den här enheten till alla dataformat som stöds inklusive CSV eller Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="589de-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="589de-150">Nedan finns ett exempel på hur du exporterar rapporten **jämföra lager för artikelpriser**:</span><span class="sxs-lookup"><span data-stu-id="589de-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="589de-151">Gå till **Systemadministration > Arbetsytor > Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="589de-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="589de-152">Välj knappen **Exportera** i avsnittet **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="589de-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="589de-153">Sidan **Export** öppnas, som du kommer att använda för att ställa in exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="589de-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="589de-154">Börja med att ge jobbet ett **gruppnamn**.</span><span class="sxs-lookup"><span data-stu-id="589de-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="589de-155">I avsnittet **valda entiteter** väljer du **Lägg till entitet** för att öppna en dialogruta där du kan ställa in följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="589de-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="589de-156">**Entitetsnamn** - Välj **jämför artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="589de-157">**Måldataformat** – Välj det format som du vill exportera till.</span><span class="sxs-lookup"><span data-stu-id="589de-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="589de-158">Välj **Lägg till** för att lägga till den nya raden och välj sedan **Stäng** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="589de-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="589de-159">Vanligtvis exporterar du en rapport i taget.</span><span class="sxs-lookup"><span data-stu-id="589de-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="589de-160">Det gör du genom att ställa in **filter** för den rad som du just har lagt till i fönstret **Fråga**.</span><span class="sxs-lookup"><span data-stu-id="589de-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="589de-161">På så sätt kan du definiera vilka rapporter från enheten **jämför artikelpriser** som du vill ta med i exporten.</span><span class="sxs-lookup"><span data-stu-id="589de-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="589de-162">Ställ in följande filteralternativ för att exportera en enskild rapport:</span><span class="sxs-lookup"><span data-stu-id="589de-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="589de-163">På fliken **intervall**, välj **Lägg till** om du vill lägga till en ny rad.</span><span class="sxs-lookup"><span data-stu-id="589de-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="589de-164">Ange **Register** till **Jämför artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="589de-165">Ange **härlett register** till **Jämför artikelpriser**.</span><span class="sxs-lookup"><span data-stu-id="589de-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="589de-166">Ställ in **fältet** till det fält som du vill filtrera efter.</span><span class="sxs-lookup"><span data-stu-id="589de-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="589de-167">Vanligtvis ska du använda **körningsnamn** eller **körningstid**.</span><span class="sxs-lookup"><span data-stu-id="589de-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="589de-168">Ange **Kriterier** till värdet från det valda fältet som du vill söka efter (antingen namnet på rapporten eller tiden rapporten genererades).</span><span class="sxs-lookup"><span data-stu-id="589de-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="589de-169">Lägg till fler rader till tabellen **Intervall** tills du har identifierat den rapport som du söker efter, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="589de-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="589de-170">Välj **OK** om du vill spara inställningarna och stänga.</span><span class="sxs-lookup"><span data-stu-id="589de-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="589de-171">Välj **Spara** om du vill spara dina exportinställningar.</span><span class="sxs-lookup"><span data-stu-id="589de-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="589de-172">Öppna fliken **exportalternativ** och välj **exportera nu** för att generera exportfilen.</span><span class="sxs-lookup"><span data-stu-id="589de-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="589de-173">Sidan **körningssammanfattning** öppnas, där du kan se statusen för exportjobbet och en lista över de enheter som har exporterats.</span><span class="sxs-lookup"><span data-stu-id="589de-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="589de-174">Markera enheten **jämför artikelpriser** i området **Bearbetningsstatus för entitet** och välj sedan **hämta fil** för att hämta de data som exporteras från den enheten.</span><span class="sxs-lookup"><span data-stu-id="589de-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="589de-175">Mer information om hur du använder datahantering för att exportera data finns i [översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="589de-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
