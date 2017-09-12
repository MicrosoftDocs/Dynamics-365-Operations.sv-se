---
title: "Momsrapporter för Europa"
description: "Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (moms) för vissa europeiska länder."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c0be253e80636d659027f69cbac58062cb28269e
ms.contentlocale: sv-se
ms.lasthandoff: 07/21/2017

---

# <a name="vat-reporting-for-europe"></a><span data-ttu-id="f1321-103">Momsrapporter för Europa</span><span class="sxs-lookup"><span data-stu-id="f1321-103">VAT reporting for Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f1321-104">Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (moms) för vissa europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="f1321-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="f1321-105">Det här avsnittet innehåller en allmän metod för inställning och skapande av momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="f1321-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="f1321-106">Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:</span><span class="sxs-lookup"><span data-stu-id="f1321-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="f1321-107">Österrike</span><span class="sxs-lookup"><span data-stu-id="f1321-107">Austria</span></span>
-   <span data-ttu-id="f1321-108">Belgien</span><span class="sxs-lookup"><span data-stu-id="f1321-108">Belgium</span></span>
-   <span data-ttu-id="f1321-109">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f1321-109">Czech Republic</span></span>
-   <span data-ttu-id="f1321-110">Estland</span><span class="sxs-lookup"><span data-stu-id="f1321-110">Estonia</span></span>
-   <span data-ttu-id="f1321-111">Finland</span><span class="sxs-lookup"><span data-stu-id="f1321-111">Finland</span></span>
-   <span data-ttu-id="f1321-112">Tyskland</span><span class="sxs-lookup"><span data-stu-id="f1321-112">Germany</span></span>
-   <span data-ttu-id="f1321-113">Lettland</span><span class="sxs-lookup"><span data-stu-id="f1321-113">Latvia</span></span>
-   <span data-ttu-id="f1321-114">Litauen</span><span class="sxs-lookup"><span data-stu-id="f1321-114">Lithuania</span></span>
-   <span data-ttu-id="f1321-115">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="f1321-115">Netherlands</span></span>
-   <span data-ttu-id="f1321-116">Sverige</span><span class="sxs-lookup"><span data-stu-id="f1321-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="f1321-117">Översikt över momsrapport</span><span class="sxs-lookup"><span data-stu-id="f1321-117">VAT statement overview</span></span>
<span data-ttu-id="f1321-118">Moms-utdraget baseras på beloppen i momstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="f1321-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="f1321-119">Att generera ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms.</span><span class="sxs-lookup"><span data-stu-id="f1321-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="f1321-120">Den här funktionen beräknar momsen som ska betalas för en given period.</span><span class="sxs-lookup"><span data-stu-id="f1321-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="f1321-121">Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="f1321-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="f1321-122">Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML).</span><span class="sxs-lookup"><span data-stu-id="f1321-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="f1321-123">För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import.</span><span class="sxs-lookup"><span data-stu-id="f1321-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="f1321-124">Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f1321-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="f1321-125">En specifik rapportlayout för varje momsrapporteringskod bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="f1321-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="f1321-126">Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="f1321-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="f1321-127">En specifik rapportlayout för varje momsmyndighet bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="f1321-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="f1321-128">Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden.</span><span class="sxs-lookup"><span data-stu-id="f1321-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="f1321-129">En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta).</span><span class="sxs-lookup"><span data-stu-id="f1321-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="f1321-130">Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder.</span><span class="sxs-lookup"><span data-stu-id="f1321-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="f1321-131">Illustrationen som följer visar datarelationen.</span><span class="sxs-lookup"><span data-stu-id="f1321-131">The following illustration shows the data relationship.</span></span>

![diagram](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="f1321-133">Inställningar för momsrapport</span><span class="sxs-lookup"><span data-stu-id="f1321-133">VAT statement setup</span></span>
<span data-ttu-id="f1321-134">Om du vill generera en momsrapport måste du konfigurera följande:</span><span class="sxs-lookup"><span data-stu-id="f1321-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="f1321-135">Momsmyndigheter för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="f1321-135">Sales tax authorities for VAT reporting</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](/dynamics365/unified-operations/financials/general-ledger/tasks/set-up-sales-tax-authorities). -->
<span data-ttu-id="f1321-136">Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten.</span><span class="sxs-lookup"><span data-stu-id="f1321-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="f1321-137">På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**.</span><span class="sxs-lookup"><span data-stu-id="f1321-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="f1321-138">Den här layouten används när du ställer in momsrapporteringskoder.</span><span class="sxs-lookup"><span data-stu-id="f1321-138">This layout will be used when you set up sales tax reporting codes.</span></span>

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="f1321-139">Momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="f1321-139">Sales tax reporting codes</span></span>

<span data-ttu-id="f1321-140">Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format.</span><span class="sxs-lookup"><span data-stu-id="f1321-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="f1321-141">Koderna används för att sammanställa och förbereda beloppen för rapporten.</span><span class="sxs-lookup"><span data-stu-id="f1321-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="f1321-142">Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="f1321-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="f1321-143">Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="f1321-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="f1321-144">Du måste tilldela en rapportlayout åt varje kod.</span><span class="sxs-lookup"><span data-stu-id="f1321-144">You must assign each code a report layout.</span></span> <span data-ttu-id="f1321-145">När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="f1321-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](/dynamics365/unified-operations/financials/general-ledger/tasks/set-up-sales-tax-reporting-codes).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="f1321-146">Momskoder för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="f1321-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](/dynamics365/unified-operations/financials/general-ledger/tasks/set-up-sales-tax-codes).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the **Sales tax codes** page. The following table describes the transaction types in the report setup for sales tax codes. The calculation includes transactions for all types of sources except sales tax.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f1321-147"><strong>Transaktionstyp</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-147"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="f1321-148"><strong>Beskrivning av transaktioner och belopp som ska räknas in i transaktionstypen</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-148"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-149"><strong>Momspliktig försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-149"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="f1321-150">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-150">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-151">Transaktionsdatumet ligger i den valda perioden/</span><span class="sxs-lookup"><span data-stu-id="f1321-151">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="f1321-152">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-152">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-153">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-153">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-154"><strong>Skattefri försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-154"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="f1321-155">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-155">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-156">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-156">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-157">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-157">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="f1321-158">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-158">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-159"><strong>Momsskuld</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-159"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="f1321-160">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-160">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-161">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-161">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-162">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-162">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-163">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-163">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-164"><strong>Momspliktiga försäljningskreditfakturor</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-164"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-165">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-165">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-166">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-166">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-167">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-167">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-168">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-168">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-169"><strong>Momsbefriad försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-169"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-170">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-170">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-171">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-171">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-172">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-172">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="f1321-173">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-173">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-174"><strong>Moms på försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-174"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-175">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-175">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-176">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-176">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-177">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-177">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-178">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-178">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-179"><strong>Skattepliktiga inköp</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-179"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="f1321-180">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-180">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-181">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-181">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-182">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-182">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-183">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-183">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-184"><strong>Skattefritt inköp</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-184"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="f1321-185">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-185">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-186">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-186">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-187">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-187">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="f1321-188">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-188">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-189"><strong>Momsfordran</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-189"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="f1321-190">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-190">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-191">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-191">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-192">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-192">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-193">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-193">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-194"><strong>Momspliktig inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-194"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-195">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-195">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-196">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-196">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-197">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-197">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-198">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-198">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-199"><strong>Momsbefriad inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-199"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-200">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-200">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-201">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-201">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-202">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-202">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="f1321-203">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-203">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-204"><strong>Moms på inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-204"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-205">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-205">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-206">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-206">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-207">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f1321-207">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f1321-208">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-208">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-209"><strong>Skattepliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-209"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="f1321-210">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-210">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-211">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-211">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-212"><strong>Momsriktningen</strong> är <strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-212"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="f1321-213">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-213">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-214"><strong>Motbokning momspliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-214"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="f1321-215">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-215">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-216">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-216">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-217"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f1321-217"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f1321-218">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-218">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-219"><strong>Momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-219"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-220">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-220">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-221">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-221">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="f1321-222">e</span><span class="sxs-lookup"><span data-stu-id="f1321-222">e</span></span><li><span data-ttu-id="f1321-223"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f1321-223"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f1321-224">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-224">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-225"><strong>Motbokad momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-225"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="f1321-226">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-226">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-227">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-227">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-228">Momsriktningen är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f1321-228">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="f1321-229">d</span><span class="sxs-lookup"><span data-stu-id="f1321-229">d</span></span><li><span data-ttu-id="f1321-230">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-230">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1321-231"><strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-231"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="f1321-232">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-232">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-233">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-233">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-234"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f1321-234"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f1321-235">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-235">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f1321-236"><strong>Motbokning av importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f1321-236"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="f1321-237">Återförd summa för <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f1321-237">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f1321-238">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f1321-238">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f1321-239"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f1321-239"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f1321-240">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f1321-240">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f1321-241">För tabellen ovan förutsätts att följande kriterier uppfylls:</span><span class="sxs-lookup"><span data-stu-id="f1321-241">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="f1321-242">Momsunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="f1321-242">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="f1321-243">Momsbeloppet är ett transaktionsbelopp från fältet **Faktiskt momsbelopp i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="f1321-243">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="f1321-244">Konfigurera ER-modell och format för rapporten</span><span class="sxs-lookup"><span data-stu-id="f1321-244">Configure the ER model and format for the report</span></span>

<span data-ttu-id="f1321-245">Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden.</span><span class="sxs-lookup"><span data-stu-id="f1321-245">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="f1321-246">För mer information:</span><span class="sxs-lookup"><span data-stu-id="f1321-246">For additional information:</span></span>

-   [<span data-ttu-id="f1321-247">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f1321-247">Electronic reporting overview</span></span>](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting)
-   [<span data-ttu-id="f1321-248">Hämta konfigurationer för elektronisk rapportering från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="f1321-248">Download Electronic reporting configurations from Lifecycle Services</span></span>](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [<span data-ttu-id="f1321-249">Lokaliseringskrav – Skapa en GER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="f1321-249">Localization requirements – Create a GER configuration</span></span>](/dynamics365/unified-operations/dev-itpro/analytics/electronic-reporting-configuration)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="f1321-250">Landspecifika resurser för momsrapporter</span><span class="sxs-lookup"><span data-stu-id="f1321-250">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="f1321-251">Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning.</span><span class="sxs-lookup"><span data-stu-id="f1321-251">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="f1321-252">Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="f1321-252">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="f1321-253">Land</span><span class="sxs-lookup"><span data-stu-id="f1321-253">Country</span></span>        | <span data-ttu-id="f1321-254">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f1321-254">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="f1321-255">Österrike</span><span class="sxs-lookup"><span data-stu-id="f1321-255">Austria</span></span>        |  [<span data-ttu-id="f1321-256">Detaljerad momsinformation för Österrike</span><span class="sxs-lookup"><span data-stu-id="f1321-256">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="f1321-257">Belgien</span><span class="sxs-lookup"><span data-stu-id="f1321-257">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="f1321-258">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f1321-258">Czech Republic</span></span> |  [<span data-ttu-id="f1321-259">Detaljerad momsrapport för Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f1321-259">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="f1321-260">Estland</span><span class="sxs-lookup"><span data-stu-id="f1321-260">Estonia</span></span>        |  [<span data-ttu-id="f1321-261">Detaljerad momsinformation för Estland</span><span class="sxs-lookup"><span data-stu-id="f1321-261">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="f1321-262">Finland</span><span class="sxs-lookup"><span data-stu-id="f1321-262">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="f1321-263">Tyskland</span><span class="sxs-lookup"><span data-stu-id="f1321-263">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="f1321-264">Italien</span><span class="sxs-lookup"><span data-stu-id="f1321-264">Italy</span></span>          | [<span data-ttu-id="f1321-265">Detaljerad momsinformation för Italien</span><span class="sxs-lookup"><span data-stu-id="f1321-265">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="f1321-266">Lettland</span><span class="sxs-lookup"><span data-stu-id="f1321-266">Latvia</span></span>         | [<span data-ttu-id="f1321-267">Detaljerad momsinformation för Lettland</span><span class="sxs-lookup"><span data-stu-id="f1321-267">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="f1321-268">Litauen</span><span class="sxs-lookup"><span data-stu-id="f1321-268">Lithuania</span></span>      | [<span data-ttu-id="f1321-269">Detaljerad momsinformation för Litauen</span><span class="sxs-lookup"><span data-stu-id="f1321-269">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="f1321-270">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="f1321-270">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="f1321-271">Sverige</span><span class="sxs-lookup"><span data-stu-id="f1321-271">Sweden</span></span>         |                                                                                 |






