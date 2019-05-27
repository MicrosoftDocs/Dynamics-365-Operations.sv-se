---
title: Inköps- och utgiftsanalys för Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3206573022c0f843b07a468987a112ca6ac435ef
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1527727"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="ae4c6-104">Inköps- och utgiftsanalys för Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="ae4c6-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae4c6-105">Det här avsnittet beskriver vad som ingår i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="ae4c6-106">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="ae4c6-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="ae4c6-107">Overview</span></span>

<span data-ttu-id="ae4c6-108">Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla koll på köputgifterna.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="ae4c6-109">Chefer kan analysera inköpsutgifter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ae4c6-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="ae4c6-110">Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="ae4c6-111">Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="ae4c6-112">Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="ae4c6-113">Rapporter visar ändringar i inköpsutgifter över tiden.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="ae4c6-114">Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="ae4c6-115">Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="ae4c6-116">Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="ae4c6-117">Komma åt Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="ae4c6-117">Accessing the Power BI content</span></span>
<span data-ttu-id="ae4c6-118">**Analys av inköpsutgift** Power BI-innehåll visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** \> **Förfrågningar och rapporter** \> **Analys av köpprestanda** \> **Analys av inköp och utgifter**).</span><span class="sxs-lookup"><span data-stu-id="ae4c6-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="ae4c6-119">Mätvärden som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="ae4c6-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="ae4c6-120">Power BI-innehåll för **analys av inköpsutgift** innehåller en rapport som består av en uppsättning mått.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="ae4c6-121">De här måtten visas som diagram, paneler och tabeller.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="ae4c6-122">Nedanstående avsnitt ger en översikt över visualiseringarna.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="ae4c6-123">Sidan inköp per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-123">Purchase by vendor report page</span></span>
<span data-ttu-id="ae4c6-124">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-124">**Charts**</span></span>
- <span data-ttu-id="ae4c6-125">De 10 främsta leverantörerna per inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="ae4c6-126">Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="ae4c6-127">Inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="ae4c6-128">Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="ae4c6-129">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-129">**Tiles**</span></span>
- <span data-ttu-id="ae4c6-130">Totalt inköp</span><span class="sxs-lookup"><span data-stu-id="ae4c6-130">Total purchase</span></span>
- <span data-ttu-id="ae4c6-131">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="ae4c6-131">YOY purchase growth</span></span>
- <span data-ttu-id="ae4c6-132">Totalt antal leverantörer</span><span class="sxs-lookup"><span data-stu-id="ae4c6-132">Total # vendors</span></span>
- <span data-ttu-id="ae4c6-133">Totalt antal aktiva leverantörer</span><span class="sxs-lookup"><span data-stu-id="ae4c6-133">Total # of active vendors</span></span>

<span data-ttu-id="ae4c6-134">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-134">**Example**</span></span>
<img src="media/spend1.PNG" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="ae4c6-135">Sidan produkt per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-135">Purchase by product report page</span></span>

<span data-ttu-id="ae4c6-136">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-136">**Charts**</span></span>
- <span data-ttu-id="ae4c6-137">Inköp per anskaffningskategori / produktnamn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="ae4c6-138">Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="ae4c6-139">De 10 främsta produkterna efter inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="ae4c6-140">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-140">**Tiles**</span></span>
- <span data-ttu-id="ae4c6-141">Totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="ae4c6-141">Total # of products</span></span></li>
- <span data-ttu-id="ae4c6-142">Totalt antal aktiva produkters procentuella andel av totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="ae4c6-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="ae4c6-143">Antal produkter som står för 80 % av inköp</span><span class="sxs-lookup"><span data-stu-id="ae4c6-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="ae4c6-144">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-144">**Example**</span></span>


<img src="media/purchaseByProduct.PNG" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="ae4c6-145">Sidan inköp per periodrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-145">Purchase by period report page</span></span>
<span data-ttu-id="ae4c6-146">Den här sidan visar inköp i år och förra året och tillväxt efter upphandlingskategori.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="ae4c6-147">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-147">**Charts**</span></span> 
- <span data-ttu-id="ae4c6-148">Inköp per månad / dag (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="ae4c6-149">Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="ae4c6-150">Totala YOY inköpstillväxt (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="ae4c6-151">Anskaffningsutdrag (matris)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="ae4c6-152">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-152">**Tiles**</span></span>
- <span data-ttu-id="ae4c6-153">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="ae4c6-153">YOY purchase growth</span></span>
- <span data-ttu-id="ae4c6-154">YOY inköpstillväxt %</span><span class="sxs-lookup"><span data-stu-id="ae4c6-154">YOY purchase growth %</span></span>

<span data-ttu-id="ae4c6-155">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-155">**Example**</span></span>
<img src="media/purchaseByPeriod.PNG" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="ae4c6-156">Sidan inköp per leverantörplatsrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="ae4c6-157">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-157">**Charts**</span></span>
- <span data-ttu-id="ae4c6-158">Inköp per ort</span><span class="sxs-lookup"><span data-stu-id="ae4c6-158">Purchase by city</span></span>
- <span data-ttu-id="ae4c6-159">Inköp YOY tillväxt %</span><span class="sxs-lookup"><span data-stu-id="ae4c6-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="ae4c6-160">Inköp per land</span><span class="sxs-lookup"><span data-stu-id="ae4c6-160">Purchase by country</span></span>

<span data-ttu-id="ae4c6-161">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-161">**Example**</span></span>
<img src="media/purchByVendorLocation.PNG" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="ae4c6-162">Analys av inköpsutgift per tidsrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="ae4c6-163">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-163">**Charts**</span></span> 
- <span data-ttu-id="ae4c6-164">Inköp innevarande år per månad / dag (linjediagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="ae4c6-165">Inköp innevarande år och föregående år (linje- och stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="ae4c6-166">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-166">**Example**</span></span>
<img src="media/PurchByTIme.PNG" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="ae4c6-167">Analys av inköpsutgift per leverantörsrapport</span><span class="sxs-lookup"><span data-stu-id="ae4c6-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="ae4c6-168">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="ae4c6-168">**Charts**</span></span> 
- <span data-ttu-id="ae4c6-169">Topp 10 leverantörers inköp % av inköp (tratt)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="ae4c6-170">Topp 10 leverantörer med ökad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="ae4c6-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="ae4c6-171">Topp 10 leverantörer med minskad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="ae4c6-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="ae4c6-172">**Exempel** 
</span><span class="sxs-lookup"><span data-stu-id="ae4c6-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.PNG" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="ae4c6-173">Datamodell och enheter</span><span class="sxs-lookup"><span data-stu-id="ae4c6-173">Data model and entities</span></span>
<span data-ttu-id="ae4c6-174">Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="ae4c6-175">Informationen visas som sammansatta mått som mellanlagras i Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="ae4c6-176">Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="ae4c6-177">Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c6-177">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="ae4c6-178">De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="ae4c6-179">För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="ae4c6-180">Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Översikt över Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c6-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="ae4c6-181">Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="ae4c6-182">Enhet</span><span class="sxs-lookup"><span data-stu-id="ae4c6-182">Entity</span></span>        | <span data-ttu-id="ae4c6-183">Sammanlagda huvudmått</span><span class="sxs-lookup"><span data-stu-id="ae4c6-183">Key aggregate measurements</span></span> | <span data-ttu-id="ae4c6-184">Datakälla</span><span class="sxs-lookup"><span data-stu-id="ae4c6-184">Data source</span></span>                                 | <span data-ttu-id="ae4c6-185">Fält</span><span class="sxs-lookup"><span data-stu-id="ae4c6-185">Field</span></span>              | <span data-ttu-id="ae4c6-186">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ae4c6-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="ae4c6-187">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="ae4c6-187">Invoice lines</span></span> | <span data-ttu-id="ae4c6-188">Inköp</span><span class="sxs-lookup"><span data-stu-id="ae4c6-188">Purchase</span></span>                   | <span data-ttu-id="ae4c6-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="ae4c6-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="ae4c6-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="ae4c6-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="ae4c6-191">Belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="ae4c6-192">Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="ae4c6-193">Mått</span><span class="sxs-lookup"><span data-stu-id="ae4c6-193">Measure</span></span>               | <span data-ttu-id="ae4c6-194">Beräkning</span><span class="sxs-lookup"><span data-stu-id="ae4c6-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ae4c6-195">Inköp innevarande år</span><span class="sxs-lookup"><span data-stu-id="ae4c6-195">Purchase current year</span></span> | <span data-ttu-id="ae4c6-196">Inköp innevarande år = SUM('Fakturarader'\[Inköp\])</span><span class="sxs-lookup"><span data-stu-id="ae4c6-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="ae4c6-197">Inköp i fjol</span><span class="sxs-lookup"><span data-stu-id="ae4c6-197">Purchase last year</span></span>    | <span data-ttu-id="ae4c6-198">Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\]))</span><span class="sxs-lookup"><span data-stu-id="ae4c6-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="ae4c6-199">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="ae4c6-199">YOY purchase growth</span></span>   | <span data-ttu-id="ae4c6-200">YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]</span><span class="sxs-lookup"><span data-stu-id="ae4c6-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="ae4c6-201">Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="ae4c6-202">Enhet</span><span class="sxs-lookup"><span data-stu-id="ae4c6-202">Entity</span></span>                 | <span data-ttu-id="ae4c6-203">Exempel på attribut</span><span class="sxs-lookup"><span data-stu-id="ae4c6-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="ae4c6-204">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="ae4c6-204">Vendors</span></span>                | <span data-ttu-id="ae4c6-205">Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="ae4c6-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="ae4c6-206">Produkter</span><span class="sxs-lookup"><span data-stu-id="ae4c6-206">Products</span></span>               | <span data-ttu-id="ae4c6-207">Produktnummer, produktnamn, artikelgruppsnamn</span><span class="sxs-lookup"><span data-stu-id="ae4c6-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="ae4c6-208">Anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="ae4c6-208">Procurement categories</span></span> | <span data-ttu-id="ae4c6-209">Anskaffningskategori, anskaffningskategorinamn</span><span class="sxs-lookup"><span data-stu-id="ae4c6-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="ae4c6-210">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="ae4c6-210">Legal entities</span></span>         | <span data-ttu-id="ae4c6-211">Namn på juridisk person</span><span class="sxs-lookup"><span data-stu-id="ae4c6-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="ae4c6-212">Datum</span><span class="sxs-lookup"><span data-stu-id="ae4c6-212">Dates</span></span>                  | <span data-ttu-id="ae4c6-213">Datum, Förskjutning för år</span><span class="sxs-lookup"><span data-stu-id="ae4c6-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="ae4c6-214">Som standard visar innehållet data för det aktuella kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="ae4c6-215">Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="ae4c6-216">Du kan också ändra filtret för företaget.</span><span class="sxs-lookup"><span data-stu-id="ae4c6-216">You can also change the company filter.</span></span>
