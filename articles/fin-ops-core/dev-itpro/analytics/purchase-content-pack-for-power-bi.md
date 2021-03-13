---
title: Inköps- och utgiftsanalys för Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5914abaafab509e278d7a85441928feddb0b5164
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093452"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="4eb5a-103">Inköps- och utgiftsanalys för Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="4eb5a-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4eb5a-104">Det här avsnittet beskriver vad som ingår i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="4eb5a-105">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="4eb5a-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="4eb5a-106">Overview</span></span>

<span data-ttu-id="4eb5a-107">Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla koll på köputgifterna.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="4eb5a-108">Chefer kan analysera inköpsutgifter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="4eb5a-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="4eb5a-109">Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="4eb5a-110">Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="4eb5a-111">Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="4eb5a-112">Rapporter visar ändringar i inköpsutgifter över tiden.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="4eb5a-113">Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="4eb5a-114">Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="4eb5a-115">Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="4eb5a-116">Komma åt Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="4eb5a-116">Accessing the Power BI content</span></span>
<span data-ttu-id="4eb5a-117">**Analys av inköpsutgift** Power BI-innehåll visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** \> **Förfrågningar och rapporter** \> **Analys av köpprestanda** \> **Analys av inköp och utgifter**).</span><span class="sxs-lookup"><span data-stu-id="4eb5a-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="4eb5a-118">Mätvärden som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="4eb5a-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="4eb5a-119">Power BI-innehåll för **analys av inköpsutgift** innehåller en rapport som består av en uppsättning mått.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="4eb5a-120">De här måtten visas som diagram, paneler och tabeller.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="4eb5a-121">Nedanstående avsnitt ger en översikt över visualiseringarna.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="4eb5a-122">Sidan inköp per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-122">Purchase by vendor report page</span></span>
<span data-ttu-id="4eb5a-123">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-123">**Charts**</span></span>
- <span data-ttu-id="4eb5a-124">De 10 främsta leverantörerna per inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="4eb5a-125">Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="4eb5a-126">Inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="4eb5a-127">Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="4eb5a-128">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-128">**Tiles**</span></span>
- <span data-ttu-id="4eb5a-129">Totalt inköp</span><span class="sxs-lookup"><span data-stu-id="4eb5a-129">Total purchase</span></span>
- <span data-ttu-id="4eb5a-130">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="4eb5a-130">YOY purchase growth</span></span>
- <span data-ttu-id="4eb5a-131">Totalt antal leverantörer</span><span class="sxs-lookup"><span data-stu-id="4eb5a-131">Total # vendors</span></span>
- <span data-ttu-id="4eb5a-132">Totalt antal aktiva leverantörer</span><span class="sxs-lookup"><span data-stu-id="4eb5a-132">Total # of active vendors</span></span>

<span data-ttu-id="4eb5a-133">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="4eb5a-134">Sidan produkt per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-134">Purchase by product report page</span></span>

<span data-ttu-id="4eb5a-135">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-135">**Charts**</span></span>
- <span data-ttu-id="4eb5a-136">Inköp per anskaffningskategori / produktnamn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="4eb5a-137">Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="4eb5a-138">De 10 främsta produkterna efter inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="4eb5a-139">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-139">**Tiles**</span></span>
- <span data-ttu-id="4eb5a-140">Totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="4eb5a-140">Total # of products</span></span></li>
- <span data-ttu-id="4eb5a-141">Totalt antal aktiva produkters procentuella andel av totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="4eb5a-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="4eb5a-142">Antal produkter som står för 80 % av inköp</span><span class="sxs-lookup"><span data-stu-id="4eb5a-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="4eb5a-143">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="4eb5a-144">Sidan inköp per periodrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-144">Purchase by period report page</span></span>
<span data-ttu-id="4eb5a-145">Den här sidan visar inköp i år och förra året och tillväxt efter upphandlingskategori.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="4eb5a-146">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-146">**Charts**</span></span> 
- <span data-ttu-id="4eb5a-147">Inköp per månad / dag (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="4eb5a-148">Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="4eb5a-149">Totala YOY inköpstillväxt (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="4eb5a-150">Anskaffningsutdrag (matris)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="4eb5a-151">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-151">**Tiles**</span></span>
- <span data-ttu-id="4eb5a-152">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="4eb5a-152">YOY purchase growth</span></span>
- <span data-ttu-id="4eb5a-153">YOY inköpstillväxt %</span><span class="sxs-lookup"><span data-stu-id="4eb5a-153">YOY purchase growth %</span></span>

<span data-ttu-id="4eb5a-154">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="4eb5a-155">Sidan inköp per leverantörplatsrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="4eb5a-156">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-156">**Charts**</span></span>
- <span data-ttu-id="4eb5a-157">Inköp per ort</span><span class="sxs-lookup"><span data-stu-id="4eb5a-157">Purchase by city</span></span>
- <span data-ttu-id="4eb5a-158">Inköp YOY tillväxt %</span><span class="sxs-lookup"><span data-stu-id="4eb5a-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="4eb5a-159">Inköp per land</span><span class="sxs-lookup"><span data-stu-id="4eb5a-159">Purchase by country</span></span>

<span data-ttu-id="4eb5a-160">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="4eb5a-161">Analys av inköpsutgift per tidsrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="4eb5a-162">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-162">**Charts**</span></span> 
- <span data-ttu-id="4eb5a-163">Inköp innevarande år per månad / dag (linjediagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="4eb5a-164">Inköp innevarande år och föregående år (linje- och stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="4eb5a-165">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="4eb5a-166">Analys av inköpsutgift per leverantörsrapport</span><span class="sxs-lookup"><span data-stu-id="4eb5a-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="4eb5a-167">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="4eb5a-167">**Charts**</span></span> 
- <span data-ttu-id="4eb5a-168">Topp 10 leverantörers inköp % av inköp (tratt)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="4eb5a-169">Topp 10 leverantörer med ökad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="4eb5a-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="4eb5a-170">Topp 10 leverantörer med minskad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="4eb5a-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="4eb5a-171">**Exempel** 
</span><span class="sxs-lookup"><span data-stu-id="4eb5a-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="4eb5a-172">Datamodell och enheter</span><span class="sxs-lookup"><span data-stu-id="4eb5a-172">Data model and entities</span></span>
<span data-ttu-id="4eb5a-173">Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="4eb5a-174">Informationen visas som sammansatta mått som mellanlagras i Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="4eb5a-175">Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="4eb5a-176">Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="4eb5a-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="4eb5a-177">De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="4eb5a-178">För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="4eb5a-179">Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="4eb5a-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="4eb5a-180">Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="4eb5a-181">Enhet</span><span class="sxs-lookup"><span data-stu-id="4eb5a-181">Entity</span></span>        | <span data-ttu-id="4eb5a-182">Sammanlagda huvudmått</span><span class="sxs-lookup"><span data-stu-id="4eb5a-182">Key aggregate measurements</span></span> | <span data-ttu-id="4eb5a-183">Datakälla</span><span class="sxs-lookup"><span data-stu-id="4eb5a-183">Data source</span></span>                                 | <span data-ttu-id="4eb5a-184">Fält</span><span class="sxs-lookup"><span data-stu-id="4eb5a-184">Field</span></span>              | <span data-ttu-id="4eb5a-185">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4eb5a-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="4eb5a-186">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="4eb5a-186">Invoice lines</span></span> | <span data-ttu-id="4eb5a-187">Inköp</span><span class="sxs-lookup"><span data-stu-id="4eb5a-187">Purchase</span></span>                   | <span data-ttu-id="4eb5a-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="4eb5a-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="4eb5a-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="4eb5a-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="4eb5a-190">Belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="4eb5a-191">Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="4eb5a-192">Mått</span><span class="sxs-lookup"><span data-stu-id="4eb5a-192">Measure</span></span>               | <span data-ttu-id="4eb5a-193">Beräkning</span><span class="sxs-lookup"><span data-stu-id="4eb5a-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4eb5a-194">Inköp innevarande år</span><span class="sxs-lookup"><span data-stu-id="4eb5a-194">Purchase current year</span></span> | <span data-ttu-id="4eb5a-195">Inköp innevarande år = SUM('Fakturarader'\[Inköp\])</span><span class="sxs-lookup"><span data-stu-id="4eb5a-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="4eb5a-196">Inköp i fjol</span><span class="sxs-lookup"><span data-stu-id="4eb5a-196">Purchase last year</span></span>    | <span data-ttu-id="4eb5a-197">Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\]))</span><span class="sxs-lookup"><span data-stu-id="4eb5a-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="4eb5a-198">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="4eb5a-198">YOY purchase growth</span></span>   | <span data-ttu-id="4eb5a-199">YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]</span><span class="sxs-lookup"><span data-stu-id="4eb5a-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="4eb5a-200">Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="4eb5a-201">Enhet</span><span class="sxs-lookup"><span data-stu-id="4eb5a-201">Entity</span></span>                 | <span data-ttu-id="4eb5a-202">Exempel på attribut</span><span class="sxs-lookup"><span data-stu-id="4eb5a-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="4eb5a-203">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="4eb5a-203">Vendors</span></span>                | <span data-ttu-id="4eb5a-204">Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="4eb5a-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="4eb5a-205">Produkter</span><span class="sxs-lookup"><span data-stu-id="4eb5a-205">Products</span></span>               | <span data-ttu-id="4eb5a-206">Produktnummer, produktnamn, artikelgruppsnamn</span><span class="sxs-lookup"><span data-stu-id="4eb5a-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="4eb5a-207">Anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="4eb5a-207">Procurement categories</span></span> | <span data-ttu-id="4eb5a-208">Anskaffningskategori, anskaffningskategorinamn</span><span class="sxs-lookup"><span data-stu-id="4eb5a-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="4eb5a-209">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="4eb5a-209">Legal entities</span></span>         | <span data-ttu-id="4eb5a-210">Namn på juridisk person</span><span class="sxs-lookup"><span data-stu-id="4eb5a-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="4eb5a-211">Datum</span><span class="sxs-lookup"><span data-stu-id="4eb5a-211">Dates</span></span>                  | <span data-ttu-id="4eb5a-212">Datum, Förskjutning för år</span><span class="sxs-lookup"><span data-stu-id="4eb5a-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="4eb5a-213">Som standard visar innehållet data för det aktuella kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="4eb5a-214">Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="4eb5a-215">Du kan också ändra filtret för företaget.</span><span class="sxs-lookup"><span data-stu-id="4eb5a-215">You can also change the company filter.</span></span>
