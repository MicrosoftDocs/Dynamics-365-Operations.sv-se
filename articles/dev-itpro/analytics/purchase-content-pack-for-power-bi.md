---
title: "Analys av inköpsutgift – Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3e42746329b1194c0ce0e2fb5c476742259a5b43
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="d1e7a-104">Analys av inköpsutgift – Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="d1e7a-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d1e7a-105">Det här avsnittet beskriver vad som ingår i Microsoft Power BI-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="d1e7a-106">Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="d1e7a-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="d1e7a-107">Overview</span></span>

<span data-ttu-id="d1e7a-108">Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla ett öga på inköpsutgifter.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="d1e7a-109">Chefer kan analysera inköpsutgifter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d1e7a-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="d1e7a-110">Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="d1e7a-111">Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="d1e7a-112">Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="d1e7a-113">Rapporter visar ändringar i inköpsutgifter över tiden.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="d1e7a-114">Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="d1e7a-115">Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="d1e7a-116">Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="d1e7a-117">Åtkomst till Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="d1e7a-117">Accessing the Power BI content</span></span>
<span data-ttu-id="d1e7a-118">Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017), visas Power BI-innehållet **Utgiftsanalys för inköp** på sidan **Inköps- och utgiftsanalys** (**Anskaffning och inköp** > **Förfrågningar och rapporter** > **Analys av inköpsprestanda** > **Inköps- och utgiftsanalys**).</span><span class="sxs-lookup"><span data-stu-id="d1e7a-118">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), the **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="d1e7a-119">Mått som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="d1e7a-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="d1e7a-120">Power BI-innehållet **Inköps- och utgiftsanalys** innehåller en rapport som består av en uppsättning mått.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="d1e7a-121">De här måtten visas som diagram, paneler och tabeller.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="d1e7a-122">Nedanstående tabell ger en översikt över visualiseringarna.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1e7a-123">Rapportsida</span><span class="sxs-lookup"><span data-stu-id="d1e7a-123">Report page</span></span></th>
<th><span data-ttu-id="d1e7a-124">Diagram</span><span class="sxs-lookup"><span data-stu-id="d1e7a-124">Charts</span></span></th>
<th><span data-ttu-id="d1e7a-125">Paneler</span><span class="sxs-lookup"><span data-stu-id="d1e7a-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d1e7a-126">Inköp efter leverantör</span><span class="sxs-lookup"><span data-stu-id="d1e7a-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-127">De 10 främsta leverantörerna per inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="d1e7a-128">Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="d1e7a-129">Inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="d1e7a-130">Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d1e7a-131">Totalt inköp</span><span class="sxs-lookup"><span data-stu-id="d1e7a-131">Total purchase</span></span></li>
<li><span data-ttu-id="d1e7a-132">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="d1e7a-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d1e7a-133">Totalt antal leverantörer</span><span class="sxs-lookup"><span data-stu-id="d1e7a-133">Total # vendors</span></span></li>
<li><span data-ttu-id="d1e7a-134">Totalt antal aktiva leverantörer</span><span class="sxs-lookup"><span data-stu-id="d1e7a-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d1e7a-135">Inköp efter produkt</span><span class="sxs-lookup"><span data-stu-id="d1e7a-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-136">Inköp per anskaffningskategori / produktnamn (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="d1e7a-137">Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="d1e7a-138">De 10 främsta produkterna efter inköp (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d1e7a-139">Totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="d1e7a-139">Total # of products</span></span></li>
<li><span data-ttu-id="d1e7a-140">Totalt antal aktiva produkters procentuella andel av totalt antal produkter</span><span class="sxs-lookup"><span data-stu-id="d1e7a-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="d1e7a-141">Antal produkter som står för 80 % av inköp</span><span class="sxs-lookup"><span data-stu-id="d1e7a-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d1e7a-142">Inköp efter period*</span><span class="sxs-lookup"><span data-stu-id="d1e7a-142">Purchase by period*</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-143">Inköp per månad / dag (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="d1e7a-144">Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="d1e7a-145">Totala YOY inköpstillväxt (stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="d1e7a-146">Anskaffningsutdrag (matris)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d1e7a-147">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="d1e7a-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d1e7a-148">YOY inköpstillväxt %</span><span class="sxs-lookup"><span data-stu-id="d1e7a-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d1e7a-149">Inköp per leverantörsplats</span><span class="sxs-lookup"><span data-stu-id="d1e7a-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-150">Inköp per ort</span><span class="sxs-lookup"><span data-stu-id="d1e7a-150">Purchase by city</span></span></li>
<li><span data-ttu-id="d1e7a-151">Inköp YOY tillväxt %</span><span class="sxs-lookup"><span data-stu-id="d1e7a-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="d1e7a-152">Inköp per land</span><span class="sxs-lookup"><span data-stu-id="d1e7a-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d1e7a-153">Analys av inköpsutgift per tid</span><span class="sxs-lookup"><span data-stu-id="d1e7a-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-154">Inköp innevarande år per månad / dag (linjediagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="d1e7a-155">Inköp innevarande år och föregående år (linje- och stapeldiagram)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d1e7a-156">Analys av inköpsutgift per leverantör</span><span class="sxs-lookup"><span data-stu-id="d1e7a-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d1e7a-157">Topp 10 leverantörers inköp % av inköp (tratt)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="d1e7a-158">Topp 10 leverantörer med ökad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="d1e7a-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="d1e7a-159">Topp 10 leverantörer med minskad utgifts YOY</span><span class="sxs-lookup"><span data-stu-id="d1e7a-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d1e7a-160">\* Inköp detta och förra året och tillväxt per anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="d1e7a-161">Utöka Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="d1e7a-161">Extending the Power BI content</span></span>
<span data-ttu-id="d1e7a-162">Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-162">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="d1e7a-163">Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-163">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="d1e7a-164">Du hittar Power BI-innehållet **Inköps- och utgiftsanalys** i biblioteket Gemensamma tillgångar i LCS.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-164">You can find the **Purchase spend analysis** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="d1e7a-165">Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="d1e7a-165">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="d1e7a-166">Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-166">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

<span data-ttu-id="d1e7a-167">Hämta innehållet för **Inköps- och utgiftsanalys** som avser den version av Dynamics 365 som du använder.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-167">Be sure to download the **Purchase spend analysis** content that applies to the version of Dynamics 365 that you're using.</span></span>

> [!NOTE]
> <span data-ttu-id="d1e7a-168">Om du använder Microsoft Dynamics 365 for Operations version 1611 krävs KB 4011327 för detta Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-168">If you're using Microsoft Dynamics 365 for Operations version 1611, KB 4011327 is a prerequisite for this Power BI content.</span></span> <span data-ttu-id="d1e7a-169">När du loggar in på LCS får du åtkomst till KB här: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-169">After you sign in to LCS, you can access the KB at https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="d1e7a-170">Datamodell och enheter</span><span class="sxs-lookup"><span data-stu-id="d1e7a-170">Data model and entities</span></span>
<span data-ttu-id="d1e7a-171">Följande data används för att fylla i rapportsidorna i Power-Bi-innehållet **Inköps- och utgiftsanalys**.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-171">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="d1e7a-172">Informationen visas som sammansatta mått som mellanlagras i Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-172">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="d1e7a-173">Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-173">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="d1e7a-174">Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d1e7a-174">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="d1e7a-175">De sammanlagda måtten i det här innehållet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-175">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="d1e7a-176">För att förbereda kubens sammanlagda mått i enhetslagringen måste du göra dem driftfärdiga.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-176">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="d1e7a-177">Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Översikt över Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d1e7a-177">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="d1e7a-178">Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-178">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="d1e7a-179">Enhet</span><span class="sxs-lookup"><span data-stu-id="d1e7a-179">Entity</span></span>        | <span data-ttu-id="d1e7a-180">Sammanlagda huvudmått</span><span class="sxs-lookup"><span data-stu-id="d1e7a-180">Key aggregate measurements</span></span> | <span data-ttu-id="d1e7a-181">Datakälla</span><span class="sxs-lookup"><span data-stu-id="d1e7a-181">Data source</span></span>                                 | <span data-ttu-id="d1e7a-182">Fält</span><span class="sxs-lookup"><span data-stu-id="d1e7a-182">Field</span></span>              | <span data-ttu-id="d1e7a-183">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d1e7a-183">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="d1e7a-184">Fakturarader</span><span class="sxs-lookup"><span data-stu-id="d1e7a-184">Invoice lines</span></span> | <span data-ttu-id="d1e7a-185">Inköp</span><span class="sxs-lookup"><span data-stu-id="d1e7a-185">Purchase</span></span>                   | <span data-ttu-id="d1e7a-186">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="d1e7a-186">VendInvoiceTrans</span></span>                            | <span data-ttu-id="d1e7a-187">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="d1e7a-187">SUM(LineAmountMST)</span></span> | <span data-ttu-id="d1e7a-188">Belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-188">The amount in the accounting currency.</span></span> |

<span data-ttu-id="d1e7a-189">Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-189">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="d1e7a-190">Mått</span><span class="sxs-lookup"><span data-stu-id="d1e7a-190">Measure</span></span>               | <span data-ttu-id="d1e7a-191">Beräkning</span><span class="sxs-lookup"><span data-stu-id="d1e7a-191">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d1e7a-192">Inköp innevarande år</span><span class="sxs-lookup"><span data-stu-id="d1e7a-192">Purchase current year</span></span> | <span data-ttu-id="d1e7a-193">Inköp innevarande år = SUM('Fakturarader'\[Inköp\])</span><span class="sxs-lookup"><span data-stu-id="d1e7a-193">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="d1e7a-194">Inköp i fjol</span><span class="sxs-lookup"><span data-stu-id="d1e7a-194">Purchase last year</span></span>    | <span data-ttu-id="d1e7a-195">Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\]))</span><span class="sxs-lookup"><span data-stu-id="d1e7a-195">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="d1e7a-196">YOY inköpstillväxt</span><span class="sxs-lookup"><span data-stu-id="d1e7a-196">YOY purchase growth</span></span>   | <span data-ttu-id="d1e7a-197">YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]</span><span class="sxs-lookup"><span data-stu-id="d1e7a-197">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="d1e7a-198">Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-198">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="d1e7a-199">Enhet</span><span class="sxs-lookup"><span data-stu-id="d1e7a-199">Entity</span></span>                 | <span data-ttu-id="d1e7a-200">Exempel på attribut</span><span class="sxs-lookup"><span data-stu-id="d1e7a-200">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="d1e7a-201">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="d1e7a-201">Vendors</span></span>                | <span data-ttu-id="d1e7a-202">Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="d1e7a-202">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="d1e7a-203">Produkter</span><span class="sxs-lookup"><span data-stu-id="d1e7a-203">Products</span></span>               | <span data-ttu-id="d1e7a-204">Produktnummer, produktnamn, artikelgruppsnamn</span><span class="sxs-lookup"><span data-stu-id="d1e7a-204">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="d1e7a-205">Anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="d1e7a-205">Procurement categories</span></span> | <span data-ttu-id="d1e7a-206">Anskaffningskategori, anskaffningskategorinamn</span><span class="sxs-lookup"><span data-stu-id="d1e7a-206">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="d1e7a-207">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="d1e7a-207">Legal entities</span></span>         | <span data-ttu-id="d1e7a-208">Namn på juridisk person</span><span class="sxs-lookup"><span data-stu-id="d1e7a-208">Legal entity name</span></span>                                     |
| <span data-ttu-id="d1e7a-209">Datum</span><span class="sxs-lookup"><span data-stu-id="d1e7a-209">Dates</span></span>                  | <span data-ttu-id="d1e7a-210">Datum, Förskjutning för år</span><span class="sxs-lookup"><span data-stu-id="d1e7a-210">Dates, Year offset</span></span>                                    |

<span data-ttu-id="d1e7a-211">Som standard visar innehållet data för det aktuella kalenderåret.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-211">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="d1e7a-212">Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-212">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="d1e7a-213">Du kan också ändra filtret för företaget.</span><span class="sxs-lookup"><span data-stu-id="d1e7a-213">You can also change the company filter.</span></span>

