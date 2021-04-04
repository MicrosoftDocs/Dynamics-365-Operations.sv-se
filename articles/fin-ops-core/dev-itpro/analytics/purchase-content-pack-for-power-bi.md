---
title: Inköps- och utgiftsanalys för Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a4149b13754b544558dbb5666fbec7df97e5c5d8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559559"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="f57db-103">Inköps- och utgiftsanalys för Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="f57db-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f57db-104">Det här avsnittet beskriver vad som ingår i **Inköps- och utgiftsanalys** Microsoft Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="f57db-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="f57db-105">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="f57db-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="f57db-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="f57db-106">Overview</span></span>

<span data-ttu-id="f57db-107">Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla koll på köputgifterna.</span><span class="sxs-lookup"><span data-stu-id="f57db-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="f57db-108">Chefer kan analysera inköpsutgifter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="f57db-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="f57db-109">Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)</span><span class="sxs-lookup"><span data-stu-id="f57db-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="f57db-110">Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)</span><span class="sxs-lookup"><span data-stu-id="f57db-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="f57db-111">Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt.</span><span class="sxs-lookup"><span data-stu-id="f57db-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="f57db-112">Rapporter visar ändringar i inköpsutgifter över tiden.</span><span class="sxs-lookup"><span data-stu-id="f57db-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="f57db-113">Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter.</span><span class="sxs-lookup"><span data-stu-id="f57db-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="f57db-114">Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="f57db-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="f57db-115">Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.</span><span class="sxs-lookup"><span data-stu-id="f57db-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="f57db-116">Komma åt Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="f57db-116">Accessing the Power BI content</span></span>
<span data-ttu-id="f57db-117">**Analys av inköpsutgift** Power BI-innehåll visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** \> **Förfrågningar och rapporter** \> **Analys av köpprestanda** \> **Analys av inköp och utgifter**).</span><span class="sxs-lookup"><span data-stu-id="f57db-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="f57db-118">Mätvärden som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="f57db-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="f57db-119">Power BI-innehåll för **analys av inköpsutgift** innehåller en rapport som består av en uppsättning mått.</span><span class="sxs-lookup"><span data-stu-id="f57db-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="f57db-120">De här måtten visas som diagram, paneler och tabeller.</span><span class="sxs-lookup"><span data-stu-id="f57db-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="f57db-121">Nedanstående avsnitt ger en översikt över visualiseringarna.</span><span class="sxs-lookup"><span data-stu-id="f57db-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="f57db-122">Sidan inköp per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-122">Purchase by vendor report page</span></span>
<span data-ttu-id="f57db-123">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-123">**Charts**</span></span>
- <span data-ttu-id="f57db-124">De 10 främsta leverantörerna per inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="f57db-125">Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="f57db-126">Inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="f57db-127">Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="f57db-128">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="f57db-128">**Tiles**</span></span>
- <span data-ttu-id="f57db-129">Totalt inköp</span><span class="sxs-lookup"><span data-stu-id="f57db-129">Total purchase</span></span>
- <span data-ttu-id="f57db-130">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="f57db-130">YOY purchase growth</span></span>
- <span data-ttu-id="f57db-131">Totalt antal leverantörer</span><span class="sxs-lookup"><span data-stu-id="f57db-131">Total # vendors</span></span>
- <span data-ttu-id="f57db-132">Totalt antal aktiva leverantörer</span><span class="sxs-lookup"><span data-stu-id="f57db-132">Total # of active vendors</span></span>

<span data-ttu-id="f57db-133">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="f57db-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="f57db-134">Sidan produkt per leverantörrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-134">Purchase by product report page</span></span>

<span data-ttu-id="f57db-135">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-135">**Charts**</span></span>
- <span data-ttu-id="f57db-136">Inköp per anskaffningskategori / produktnamn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="f57db-137">Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="f57db-138">De 10 främsta produkterna efter inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="f57db-139">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="f57db-139">**Tiles**</span></span>
- <span data-ttu-id="f57db-140">Totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="f57db-140">Total # of products</span></span></li>
- <span data-ttu-id="f57db-141">Totalt antal aktiva produkters procentuella andel av totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="f57db-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="f57db-142">Antal produkter som står för 80 % av inköp</span><span class="sxs-lookup"><span data-stu-id="f57db-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="f57db-143">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="f57db-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="f57db-144">Sidan inköp per periodrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-144">Purchase by period report page</span></span>
<span data-ttu-id="f57db-145">Den här sidan visar inköp i år och förra året och tillväxt efter upphandlingskategori.</span><span class="sxs-lookup"><span data-stu-id="f57db-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="f57db-146">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-146">**Charts**</span></span> 
- <span data-ttu-id="f57db-147">Inköp per månad / dag (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="f57db-148">Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="f57db-149">Totala YOY inköpstillväxt (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="f57db-150">Anskaffningsutdrag (matris)</span><span class="sxs-lookup"><span data-stu-id="f57db-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="f57db-151">**Paneler**</span><span class="sxs-lookup"><span data-stu-id="f57db-151">**Tiles**</span></span>
- <span data-ttu-id="f57db-152">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="f57db-152">YOY purchase growth</span></span>
- <span data-ttu-id="f57db-153">YOY inköpstillväxt %</span><span class="sxs-lookup"><span data-stu-id="f57db-153">YOY purchase growth %</span></span>

<span data-ttu-id="f57db-154">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="f57db-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="f57db-155">Sidan inköp per leverantörplatsrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="f57db-156">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-156">**Charts**</span></span>
- <span data-ttu-id="f57db-157">Inköp per ort</span><span class="sxs-lookup"><span data-stu-id="f57db-157">Purchase by city</span></span>
- <span data-ttu-id="f57db-158">Inköp YOY tillväxt %</span><span class="sxs-lookup"><span data-stu-id="f57db-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="f57db-159">Inköp per land</span><span class="sxs-lookup"><span data-stu-id="f57db-159">Purchase by country</span></span>

<span data-ttu-id="f57db-160">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="f57db-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="f57db-161">Analys av inköpsutgift per tidsrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="f57db-162">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-162">**Charts**</span></span> 
- <span data-ttu-id="f57db-163">Inköp innevarande år per månad / dag (linjediagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="f57db-164">Inköp innevarande år och föregående år (linje- och stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="f57db-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="f57db-165">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="f57db-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="f57db-166">Analys av inköpsutgift per leverantörsrapport</span><span class="sxs-lookup"><span data-stu-id="f57db-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="f57db-167">**Diagram**</span><span class="sxs-lookup"><span data-stu-id="f57db-167">**Charts**</span></span> 
- <span data-ttu-id="f57db-168">Topp 10 leverantörers inköp % av inköp (tratt)</span><span class="sxs-lookup"><span data-stu-id="f57db-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="f57db-169">Topp 10 leverantörer med ökad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="f57db-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="f57db-170">Topp 10 leverantörer med minskad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="f57db-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="f57db-171">**Exempel** 
</span><span class="sxs-lookup"><span data-stu-id="f57db-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="f57db-172">Datamodell och enheter</span><span class="sxs-lookup"><span data-stu-id="f57db-172">Data model and entities</span></span>
<span data-ttu-id="f57db-173">Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="f57db-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="f57db-174">Informationen visas som sammansatta mått som mellanlagras i Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="f57db-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="f57db-175">Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys.</span><span class="sxs-lookup"><span data-stu-id="f57db-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="f57db-176">Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="f57db-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="f57db-177">De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="f57db-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="f57db-178">För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga.</span><span class="sxs-lookup"><span data-stu-id="f57db-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="f57db-179">Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="f57db-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="f57db-180">Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.</span><span class="sxs-lookup"><span data-stu-id="f57db-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="f57db-181">Enhet</span><span class="sxs-lookup"><span data-stu-id="f57db-181">Entity</span></span>        | <span data-ttu-id="f57db-182">Sammanlagda huvudmått</span><span class="sxs-lookup"><span data-stu-id="f57db-182">Key aggregate measurements</span></span> | <span data-ttu-id="f57db-183">Datakälla</span><span class="sxs-lookup"><span data-stu-id="f57db-183">Data source</span></span>                                 | <span data-ttu-id="f57db-184">Fält</span><span class="sxs-lookup"><span data-stu-id="f57db-184">Field</span></span>              | <span data-ttu-id="f57db-185">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f57db-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="f57db-186">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="f57db-186">Invoice lines</span></span> | <span data-ttu-id="f57db-187">Inköp</span><span class="sxs-lookup"><span data-stu-id="f57db-187">Purchase</span></span>                   | <span data-ttu-id="f57db-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="f57db-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="f57db-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="f57db-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="f57db-190">Belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="f57db-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="f57db-191">Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.</span><span class="sxs-lookup"><span data-stu-id="f57db-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="f57db-192">Mått</span><span class="sxs-lookup"><span data-stu-id="f57db-192">Measure</span></span>               | <span data-ttu-id="f57db-193">Beräkning</span><span class="sxs-lookup"><span data-stu-id="f57db-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f57db-194">Inköp innevarande år</span><span class="sxs-lookup"><span data-stu-id="f57db-194">Purchase current year</span></span> | <span data-ttu-id="f57db-195">Inköp innevarande år = SUM('Fakturarader'\[Inköp\])</span><span class="sxs-lookup"><span data-stu-id="f57db-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="f57db-196">Inköp i fjol</span><span class="sxs-lookup"><span data-stu-id="f57db-196">Purchase last year</span></span>    | <span data-ttu-id="f57db-197">Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\]))</span><span class="sxs-lookup"><span data-stu-id="f57db-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="f57db-198">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="f57db-198">YOY purchase growth</span></span>   | <span data-ttu-id="f57db-199">YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]</span><span class="sxs-lookup"><span data-stu-id="f57db-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="f57db-200">Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.</span><span class="sxs-lookup"><span data-stu-id="f57db-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="f57db-201">Enhet</span><span class="sxs-lookup"><span data-stu-id="f57db-201">Entity</span></span>                 | <span data-ttu-id="f57db-202">Exempel på attribut</span><span class="sxs-lookup"><span data-stu-id="f57db-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="f57db-203">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f57db-203">Vendors</span></span>                | <span data-ttu-id="f57db-204">Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="f57db-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="f57db-205">Produkter</span><span class="sxs-lookup"><span data-stu-id="f57db-205">Products</span></span>               | <span data-ttu-id="f57db-206">Produktnummer, produktnamn, artikelgruppsnamn</span><span class="sxs-lookup"><span data-stu-id="f57db-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="f57db-207">Anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="f57db-207">Procurement categories</span></span> | <span data-ttu-id="f57db-208">Anskaffningskategori, anskaffningskategorinamn</span><span class="sxs-lookup"><span data-stu-id="f57db-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="f57db-209">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="f57db-209">Legal entities</span></span>         | <span data-ttu-id="f57db-210">Namn på juridisk person</span><span class="sxs-lookup"><span data-stu-id="f57db-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="f57db-211">Datum</span><span class="sxs-lookup"><span data-stu-id="f57db-211">Dates</span></span>                  | <span data-ttu-id="f57db-212">Datum, Förskjutning för år</span><span class="sxs-lookup"><span data-stu-id="f57db-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="f57db-213">Som standard visar innehållet data för det aktuella kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="f57db-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="f57db-214">Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet.</span><span class="sxs-lookup"><span data-stu-id="f57db-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="f57db-215">Du kan också ändra filtret för företaget.</span><span class="sxs-lookup"><span data-stu-id="f57db-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]