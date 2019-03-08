---
title: Inköps- och utgiftsanalys för Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet.
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
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
ms.openlocfilehash: 069c4dc21959ab603ba6ca3da0ac68ef20325265
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "313852"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="2a328-104">Inköps- och utgiftsanalys för Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="2a328-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a328-105">Det här avsnittet beskriver vad som ingår i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="2a328-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="2a328-106">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="2a328-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="2a328-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="2a328-107">Overview</span></span>

<span data-ttu-id="2a328-108">Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla ett öga på inköpsutgifter.</span><span class="sxs-lookup"><span data-stu-id="2a328-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="2a328-109">Chefer kan analysera inköpsutgifter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="2a328-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="2a328-110">Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)</span><span class="sxs-lookup"><span data-stu-id="2a328-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="2a328-111">Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)</span><span class="sxs-lookup"><span data-stu-id="2a328-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="2a328-112">Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt.</span><span class="sxs-lookup"><span data-stu-id="2a328-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="2a328-113">Rapporter visar ändringar i inköpsutgifter över tiden.</span><span class="sxs-lookup"><span data-stu-id="2a328-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="2a328-114">Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter.</span><span class="sxs-lookup"><span data-stu-id="2a328-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="2a328-115">Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="2a328-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="2a328-116">Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.</span><span class="sxs-lookup"><span data-stu-id="2a328-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="2a328-117">Komma åt Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="2a328-117">Accessing the Power BI content</span></span>
<span data-ttu-id="2a328-118">**Analys av inköpsutgift** Power BI-innehåll visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** \> **Förfrågningar och rapporter** \> **Analys av köpprestanda** \> **Analys av inköp och utgifter**).</span><span class="sxs-lookup"><span data-stu-id="2a328-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="2a328-119">Mätvärden som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="2a328-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="2a328-120">Power BI-innehåll för **analys av inköpsutgift** innehåller en rapport som består av en uppsättning mått.</span><span class="sxs-lookup"><span data-stu-id="2a328-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="2a328-121">De här måtten visas som diagram, paneler och tabeller.</span><span class="sxs-lookup"><span data-stu-id="2a328-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="2a328-122">Nedanstående tabell ger en översikt över visualiseringarna.</span><span class="sxs-lookup"><span data-stu-id="2a328-122">The following table provides an overview of the visualizations.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a328-123">Rapportsida</span><span class="sxs-lookup"><span data-stu-id="2a328-123">Report page</span></span></th>
<th><span data-ttu-id="2a328-124">Diagram</span><span class="sxs-lookup"><span data-stu-id="2a328-124">Charts</span></span></th>
<th><span data-ttu-id="2a328-125">Paneler</span><span class="sxs-lookup"><span data-stu-id="2a328-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a328-126">Inköp efter leverantör</span><span class="sxs-lookup"><span data-stu-id="2a328-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-127">De 10 främsta leverantörerna per inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="2a328-128">Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="2a328-129">Inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="2a328-130">Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="2a328-131">Totalt inköp</span><span class="sxs-lookup"><span data-stu-id="2a328-131">Total purchase</span></span></li>
<li><span data-ttu-id="2a328-132">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="2a328-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="2a328-133">Totalt antal leverantörer</span><span class="sxs-lookup"><span data-stu-id="2a328-133">Total # vendors</span></span></li>
<li><span data-ttu-id="2a328-134">Totalt antal aktiva leverantörer</span><span class="sxs-lookup"><span data-stu-id="2a328-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="2a328-135">Inköp efter produkt</span><span class="sxs-lookup"><span data-stu-id="2a328-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-136">Inköp per anskaffningskategori / produktnamn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="2a328-137">Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="2a328-138">De 10 främsta produkterna efter inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="2a328-139">Totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="2a328-139">Total # of products</span></span></li>
<li><span data-ttu-id="2a328-140">Totalt antal aktiva produkters procentuella andel av totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="2a328-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="2a328-141">Antal produkter som står för 80 % av inköp</span><span class="sxs-lookup"><span data-stu-id="2a328-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="2a328-142">Inköp efter period\*</span><span class="sxs-lookup"><span data-stu-id="2a328-142">Purchase by period\*</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-143">Inköp per månad / dag (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="2a328-144">Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="2a328-145">Totala YOY inköpstillväxt (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="2a328-146">Anskaffningsutdrag (matris)</span><span class="sxs-lookup"><span data-stu-id="2a328-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="2a328-147">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="2a328-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="2a328-148">YOY inköpstillväxt %</span><span class="sxs-lookup"><span data-stu-id="2a328-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="2a328-149">Inköp per leverantörsplats</span><span class="sxs-lookup"><span data-stu-id="2a328-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-150">Inköp per ort</span><span class="sxs-lookup"><span data-stu-id="2a328-150">Purchase by city</span></span></li>
<li><span data-ttu-id="2a328-151">Inköp YOY tillväxt %</span><span class="sxs-lookup"><span data-stu-id="2a328-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="2a328-152">Inköp per land</span><span class="sxs-lookup"><span data-stu-id="2a328-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="2a328-153">Analys av inköpsutgift per tid</span><span class="sxs-lookup"><span data-stu-id="2a328-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-154">Inköp innevarande år per månad / dag (linjediagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="2a328-155">Inköp innevarande år och föregående år (linje- och stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="2a328-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="2a328-156">Analys av inköpsutgift per leverantör</span><span class="sxs-lookup"><span data-stu-id="2a328-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="2a328-157">Topp 10 leverantörers inköp % av inköp (tratt)</span><span class="sxs-lookup"><span data-stu-id="2a328-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="2a328-158">Topp 10 leverantörer med ökad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="2a328-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="2a328-159">Topp 10 leverantörer med minskad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="2a328-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a328-160">\* Inköp detta och förra året och tillväxt per anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="2a328-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="2a328-161">Datamodell och enheter</span><span class="sxs-lookup"><span data-stu-id="2a328-161">Data model and entities</span></span>
<span data-ttu-id="2a328-162">Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="2a328-162">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="2a328-163">Informationen visas som sammansatta mått som mellanlagras i Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="2a328-163">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="2a328-164">Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys.</span><span class="sxs-lookup"><span data-stu-id="2a328-164">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="2a328-165">Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="2a328-165">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="2a328-166">De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="2a328-166">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="2a328-167">För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga.</span><span class="sxs-lookup"><span data-stu-id="2a328-167">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="2a328-168">Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Översikt över Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="2a328-168">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="2a328-169">Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.</span><span class="sxs-lookup"><span data-stu-id="2a328-169">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="2a328-170">Enhet</span><span class="sxs-lookup"><span data-stu-id="2a328-170">Entity</span></span>        | <span data-ttu-id="2a328-171">Sammanlagda huvudmått</span><span class="sxs-lookup"><span data-stu-id="2a328-171">Key aggregate measurements</span></span> | <span data-ttu-id="2a328-172">Datakälla</span><span class="sxs-lookup"><span data-stu-id="2a328-172">Data source</span></span>                                 | <span data-ttu-id="2a328-173">Fält</span><span class="sxs-lookup"><span data-stu-id="2a328-173">Field</span></span>              | <span data-ttu-id="2a328-174">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a328-174">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="2a328-175">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="2a328-175">Invoice lines</span></span> | <span data-ttu-id="2a328-176">Inköp</span><span class="sxs-lookup"><span data-stu-id="2a328-176">Purchase</span></span>                   | <span data-ttu-id="2a328-177">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="2a328-177">VendInvoiceTrans</span></span>                            | <span data-ttu-id="2a328-178">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="2a328-178">SUM(LineAmountMST)</span></span> | <span data-ttu-id="2a328-179">Belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="2a328-179">The amount in the accounting currency.</span></span> |

<span data-ttu-id="2a328-180">Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.</span><span class="sxs-lookup"><span data-stu-id="2a328-180">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="2a328-181">Mått</span><span class="sxs-lookup"><span data-stu-id="2a328-181">Measure</span></span>               | <span data-ttu-id="2a328-182">Beräkning</span><span class="sxs-lookup"><span data-stu-id="2a328-182">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2a328-183">Inköp innevarande år</span><span class="sxs-lookup"><span data-stu-id="2a328-183">Purchase current year</span></span> | <span data-ttu-id="2a328-184">Inköp innevarande år = SUM('Fakturarader'\[Inköp\])</span><span class="sxs-lookup"><span data-stu-id="2a328-184">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="2a328-185">Inköp i fjol</span><span class="sxs-lookup"><span data-stu-id="2a328-185">Purchase last year</span></span>    | <span data-ttu-id="2a328-186">Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\]))</span><span class="sxs-lookup"><span data-stu-id="2a328-186">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="2a328-187">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="2a328-187">YOY purchase growth</span></span>   | <span data-ttu-id="2a328-188">YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]</span><span class="sxs-lookup"><span data-stu-id="2a328-188">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="2a328-189">Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.</span><span class="sxs-lookup"><span data-stu-id="2a328-189">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="2a328-190">Enhet</span><span class="sxs-lookup"><span data-stu-id="2a328-190">Entity</span></span>                 | <span data-ttu-id="2a328-191">Exempel på attribut</span><span class="sxs-lookup"><span data-stu-id="2a328-191">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="2a328-192">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="2a328-192">Vendors</span></span>                | <span data-ttu-id="2a328-193">Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="2a328-193">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="2a328-194">Produkter</span><span class="sxs-lookup"><span data-stu-id="2a328-194">Products</span></span>               | <span data-ttu-id="2a328-195">Produktnummer, produktnamn, artikelgruppsnamn</span><span class="sxs-lookup"><span data-stu-id="2a328-195">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="2a328-196">Anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="2a328-196">Procurement categories</span></span> | <span data-ttu-id="2a328-197">Anskaffningskategori, anskaffningskategorinamn</span><span class="sxs-lookup"><span data-stu-id="2a328-197">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="2a328-198">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="2a328-198">Legal entities</span></span>         | <span data-ttu-id="2a328-199">Namn på juridisk person</span><span class="sxs-lookup"><span data-stu-id="2a328-199">Legal entity name</span></span>                                     |
| <span data-ttu-id="2a328-200">Datum</span><span class="sxs-lookup"><span data-stu-id="2a328-200">Dates</span></span>                  | <span data-ttu-id="2a328-201">Datum, Förskjutning för år</span><span class="sxs-lookup"><span data-stu-id="2a328-201">Dates, Year offset</span></span>                                    |

<span data-ttu-id="2a328-202">Som standard visar innehållet data för det aktuella kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="2a328-202">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="2a328-203">Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet.</span><span class="sxs-lookup"><span data-stu-id="2a328-203">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="2a328-204">Du kan också ändra filtret för företaget.</span><span class="sxs-lookup"><span data-stu-id="2a328-204">You can also change the company filter.</span></span>
