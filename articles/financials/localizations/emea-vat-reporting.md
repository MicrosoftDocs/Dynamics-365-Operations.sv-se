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
ms.search.scope: Core, Operations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5c5cd61c45eb7cbc6f040f054a99d9a54e1ee854
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="vat-reporting-for-europe"></a><span data-ttu-id="3b2c0-103">Momsrapporter för Europa</span><span class="sxs-lookup"><span data-stu-id="3b2c0-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b2c0-104">Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (moms) för vissa europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="3b2c0-105">Det här avsnittet innehåller en allmän metod för inställning och skapande av momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="3b2c0-106">Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="3b2c0-107">Österrike</span><span class="sxs-lookup"><span data-stu-id="3b2c0-107">Austria</span></span>
-   <span data-ttu-id="3b2c0-108">Belgien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-108">Belgium</span></span>
-   <span data-ttu-id="3b2c0-109">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-109">Czech Republic</span></span>
-   <span data-ttu-id="3b2c0-110">Estland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-110">Estonia</span></span>
-   <span data-ttu-id="3b2c0-111">Finland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-111">Finland</span></span>
-   <span data-ttu-id="3b2c0-112">Tyskland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-112">Germany</span></span>
-   <span data-ttu-id="3b2c0-113">Lettland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-113">Latvia</span></span>
-   <span data-ttu-id="3b2c0-114">Litauen</span><span class="sxs-lookup"><span data-stu-id="3b2c0-114">Lithuania</span></span>
-   <span data-ttu-id="3b2c0-115">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="3b2c0-115">Netherlands</span></span>
-   <span data-ttu-id="3b2c0-116">Sverige</span><span class="sxs-lookup"><span data-stu-id="3b2c0-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="3b2c0-117">Översikt över momsrapport</span><span class="sxs-lookup"><span data-stu-id="3b2c0-117">VAT statement overview</span></span>
<span data-ttu-id="3b2c0-118">Moms-utdraget baseras på beloppen i momstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="3b2c0-119">Att generera ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="3b2c0-120">Den här funktionen beräknar momsen som ska betalas för en given period.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="3b2c0-121">Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="3b2c0-122">Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="3b2c0-123">För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="3b2c0-124">Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="3b2c0-125">En specifik rapportlayout för varje momsrapporteringskod bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="3b2c0-126">Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="3b2c0-127">En specifik rapportlayout för varje momsmyndighet bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="3b2c0-128">Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="3b2c0-129">En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="3b2c0-130">Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="3b2c0-131">Illustrationen som följer visar datarelationen.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-131">The following illustration shows the data relationship.</span></span>

![diagram](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="3b2c0-133">Inställningar för momsrapport</span><span class="sxs-lookup"><span data-stu-id="3b2c0-133">VAT statement setup</span></span>
<span data-ttu-id="3b2c0-134">Om du vill generera en momsrapport måste du konfigurera följande:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="3b2c0-135">Momsmyndigheter för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="3b2c0-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="3b2c0-136">Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="3b2c0-137">På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="3b2c0-138">Den här layouten används när du ställer in momsrapporteringskoder.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="3b2c0-139">Momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="3b2c0-139">Sales tax reporting codes</span></span>

<span data-ttu-id="3b2c0-140">Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="3b2c0-141">Koderna används för att sammanställa och förbereda beloppen för rapporten.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="3b2c0-142">Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="3b2c0-143">Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="3b2c0-144">Du måste tilldela en rapportlayout åt varje kod.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-144">You must assign each code a report layout.</span></span> <span data-ttu-id="3b2c0-145">När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="3b2c0-146">Momskoder för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="3b2c0-146">Sales tax codes for VAT reporting</span></span>

<span data-ttu-id="3b2c0-147"><!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>sidan Momskoder</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-147"><!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="3b2c0-148">Följande tabell beskriver transaktionstyperna i rapportinställningarna för momskoder.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-148">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="3b2c0-149">Beräkningen innefattar transaktioner för alla typer av källor utom moms.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-149">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3b2c0-150"><strong>Transaktionstyp</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-150"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="3b2c0-151"><strong>Beskrivning av transaktioner och belopp som ska räknas in i transaktionstypen</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-151"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-152"><strong>Momspliktig försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-152"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="3b2c0-153">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-153">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-154">Transaktionsdatumet ligger i den valda perioden/</span><span class="sxs-lookup"><span data-stu-id="3b2c0-154">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="3b2c0-155">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-155">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-156">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-156">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-157"><strong>Skattefri försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-157"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="3b2c0-158">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-158">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-159">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-159">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-160">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-160">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-161">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-161">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-162"><strong>Momsskuld</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-162"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="3b2c0-163">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-163">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-164">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-164">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-165">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-165">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-166">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-166">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-167"><strong>Momspliktiga försäljningskreditfakturor</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-167"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-168">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-168">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-169">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-169">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-170">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-170">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-171">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-171">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-172"><strong>Momsbefriad försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-172"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-173">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-173">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-174">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-174">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-175">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-175">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-176">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-176">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-177"><strong>Moms på försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-177"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-178">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-178">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-179">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-179">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-180">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-180">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-181">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-181">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-182"><strong>Skattepliktiga inköp</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-182"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="3b2c0-183">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-183">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-184">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-184">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-185">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-185">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-186">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-186">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-187"><strong>Skattefritt inköp</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-187"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="3b2c0-188">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-188">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-189">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-189">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-190">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-190">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-191">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-191">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-192"><strong>Momsfordran</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-192"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="3b2c0-193">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-193">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-194">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-194">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-195">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-195">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-196">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-196">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-197"><strong>Momspliktig inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-197"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-198">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-198">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-199">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-199">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-200">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-200">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-201">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-201">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-202"><strong>Momsbefriad inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-202"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-203">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-203">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-204">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-204">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-205">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-205">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-206">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-206">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-207"><strong>Moms på inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-207"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-208">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-208">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-209">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-209">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-210">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3b2c0-210">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3b2c0-211">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-211">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-212"><strong>Skattepliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-212"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="3b2c0-213">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-213">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-214">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-214">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-215"><strong>Momsriktningen</strong> är <strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-215"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="3b2c0-216">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-216">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-217"><strong>Motbokning momspliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-217"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="3b2c0-218">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-218">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-219">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-219">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-220"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-220"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3b2c0-221">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-221">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-222"><strong>Momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-222"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-223">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-223">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-224">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-224">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="3b2c0-225">e</span><span class="sxs-lookup"><span data-stu-id="3b2c0-225">e</span></span><li><span data-ttu-id="3b2c0-226"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-226"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3b2c0-227">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-227">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-228"><strong>Motbokad momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-228"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="3b2c0-229">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-229">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-230">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-230">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-231">Momsriktningen är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-231">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="3b2c0-232">d</span><span class="sxs-lookup"><span data-stu-id="3b2c0-232">d</span></span><li><span data-ttu-id="3b2c0-233">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-233">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b2c0-234"><strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-234"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="3b2c0-235">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-235">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-236">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-236">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-237"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-237"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3b2c0-238">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-238">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b2c0-239"><strong>Motbokning av importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3b2c0-239"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="3b2c0-240">Återförd summa för <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-240">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3b2c0-241">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-241">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3b2c0-242"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-242"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3b2c0-243">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-243">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3b2c0-244">För tabellen ovan förutsätts att följande kriterier uppfylls:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-244">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="3b2c0-245">Momsunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-245">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="3b2c0-246">Momsbeloppet är ett transaktionsbelopp från fältet **Faktiskt momsbelopp i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-246">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="3b2c0-247">Konfigurera ER-modell och format för rapporten</span><span class="sxs-lookup"><span data-stu-id="3b2c0-247">Configure the ER model and format for the report</span></span>

<span data-ttu-id="3b2c0-248">Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-248">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="3b2c0-249">För mer information:</span><span class="sxs-lookup"><span data-stu-id="3b2c0-249">For additional information:</span></span>

-   [<span data-ttu-id="3b2c0-250">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="3b2c0-250">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="3b2c0-251">Hämta konfigurationer för elektronisk rapportering från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="3b2c0-251">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="3b2c0-252">Lokaliseringskrav – Skapa en GER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="3b2c0-252">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="3b2c0-253">Landspecifika resurser för momsrapporter</span><span class="sxs-lookup"><span data-stu-id="3b2c0-253">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="3b2c0-254">Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-254">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="3b2c0-255">Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="3b2c0-255">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="3b2c0-256">Land</span><span class="sxs-lookup"><span data-stu-id="3b2c0-256">Country</span></span>        | <span data-ttu-id="3b2c0-257">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="3b2c0-257">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="3b2c0-258">Österrike</span><span class="sxs-lookup"><span data-stu-id="3b2c0-258">Austria</span></span>        |  [<span data-ttu-id="3b2c0-259">Detaljerad momsinformation för Österrike</span><span class="sxs-lookup"><span data-stu-id="3b2c0-259">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="3b2c0-260">Belgien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-260">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="3b2c0-261">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-261">Czech Republic</span></span> |  [<span data-ttu-id="3b2c0-262">Detaljerad momsrapport för Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-262">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="3b2c0-263">Estland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-263">Estonia</span></span>        |  [<span data-ttu-id="3b2c0-264">Detaljerad momsinformation för Estland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-264">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="3b2c0-265">Finland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-265">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="3b2c0-266">Tyskland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-266">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="3b2c0-267">Italien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-267">Italy</span></span>          | [<span data-ttu-id="3b2c0-268">Detaljerad momsinformation för Italien</span><span class="sxs-lookup"><span data-stu-id="3b2c0-268">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="3b2c0-269">Lettland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-269">Latvia</span></span>         | [<span data-ttu-id="3b2c0-270">Detaljerad momsinformation för Lettland</span><span class="sxs-lookup"><span data-stu-id="3b2c0-270">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="3b2c0-271">Litauen</span><span class="sxs-lookup"><span data-stu-id="3b2c0-271">Lithuania</span></span>      | [<span data-ttu-id="3b2c0-272">Detaljerad momsinformation för Litauen</span><span class="sxs-lookup"><span data-stu-id="3b2c0-272">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="3b2c0-273">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="3b2c0-273">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="3b2c0-274">Sverige</span><span class="sxs-lookup"><span data-stu-id="3b2c0-274">Sweden</span></span>         |                                                                                 |






