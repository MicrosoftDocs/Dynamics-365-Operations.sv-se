---
title: Momsrapporter för Europa
description: Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5c5cd61c45eb7cbc6f040f054a99d9a54e1ee854
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569574"
---
# <a name="vat-reporting-for-europe"></a><span data-ttu-id="f5595-103">Momsrapporter för Europa</span><span class="sxs-lookup"><span data-stu-id="f5595-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5595-104">Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="f5595-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="f5595-105">Det här avsnittet innehåller en allmän metod för inställning och skapande av momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="f5595-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="f5595-106">Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:</span><span class="sxs-lookup"><span data-stu-id="f5595-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="f5595-107">Österrike</span><span class="sxs-lookup"><span data-stu-id="f5595-107">Austria</span></span>
-   <span data-ttu-id="f5595-108">Belgien</span><span class="sxs-lookup"><span data-stu-id="f5595-108">Belgium</span></span>
-   <span data-ttu-id="f5595-109">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f5595-109">Czech Republic</span></span>
-   <span data-ttu-id="f5595-110">Estland</span><span class="sxs-lookup"><span data-stu-id="f5595-110">Estonia</span></span>
-   <span data-ttu-id="f5595-111">Finland</span><span class="sxs-lookup"><span data-stu-id="f5595-111">Finland</span></span>
-   <span data-ttu-id="f5595-112">Tyskland</span><span class="sxs-lookup"><span data-stu-id="f5595-112">Germany</span></span>
-   <span data-ttu-id="f5595-113">Lettland</span><span class="sxs-lookup"><span data-stu-id="f5595-113">Latvia</span></span>
-   <span data-ttu-id="f5595-114">Litauen</span><span class="sxs-lookup"><span data-stu-id="f5595-114">Lithuania</span></span>
-   <span data-ttu-id="f5595-115">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="f5595-115">Netherlands</span></span>
-   <span data-ttu-id="f5595-116">Sverige</span><span class="sxs-lookup"><span data-stu-id="f5595-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="f5595-117">Översikt över momsrapport</span><span class="sxs-lookup"><span data-stu-id="f5595-117">VAT statement overview</span></span>
<span data-ttu-id="f5595-118">Skatteutdraget baseras på beloppen i momstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="f5595-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="f5595-119">Att skapa ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms.</span><span class="sxs-lookup"><span data-stu-id="f5595-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="f5595-120">Den här funktionen beräknar momsen som ska betalas för en given period.</span><span class="sxs-lookup"><span data-stu-id="f5595-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="f5595-121">Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="f5595-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="f5595-122">Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML).</span><span class="sxs-lookup"><span data-stu-id="f5595-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="f5595-123">För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import.</span><span class="sxs-lookup"><span data-stu-id="f5595-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="f5595-124">Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f5595-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="f5595-125">En specifik rapportlayout för varje momsrapporteringskod bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="f5595-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="f5595-126">Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="f5595-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="f5595-127">En specifik rapportlayout för varje momsmyndighet bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="f5595-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="f5595-128">Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden.</span><span class="sxs-lookup"><span data-stu-id="f5595-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="f5595-129">En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta).</span><span class="sxs-lookup"><span data-stu-id="f5595-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="f5595-130">Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder.</span><span class="sxs-lookup"><span data-stu-id="f5595-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="f5595-131">Illustrationen som följer visar datarelationen.</span><span class="sxs-lookup"><span data-stu-id="f5595-131">The following illustration shows the data relationship.</span></span>

![diagram](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="f5595-133">Inställningar för momsrapport</span><span class="sxs-lookup"><span data-stu-id="f5595-133">VAT statement setup</span></span>
<span data-ttu-id="f5595-134">Om du vill skapa en momsrapport måste du konfigurera följande:</span><span class="sxs-lookup"><span data-stu-id="f5595-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="f5595-135">Momsmyndigheter för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="f5595-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="f5595-136">Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten.</span><span class="sxs-lookup"><span data-stu-id="f5595-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="f5595-137">På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**.</span><span class="sxs-lookup"><span data-stu-id="f5595-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="f5595-138">Den här layouten används när du ställer in momsrapporteringskoder.</span><span class="sxs-lookup"><span data-stu-id="f5595-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="f5595-139">Momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="f5595-139">Sales tax reporting codes</span></span>

<span data-ttu-id="f5595-140">Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format.</span><span class="sxs-lookup"><span data-stu-id="f5595-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="f5595-141">Koderna används för att sammanställa och förbereda beloppen för rapporten.</span><span class="sxs-lookup"><span data-stu-id="f5595-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="f5595-142">Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="f5595-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="f5595-143">Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="f5595-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="f5595-144">Du måste tilldela en rapportlayout åt varje kod.</span><span class="sxs-lookup"><span data-stu-id="f5595-144">You must assign each code a report layout.</span></span> <span data-ttu-id="f5595-145">När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="f5595-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="f5595-146">Momskoder för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="f5595-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> <span data-ttu-id="f5595-147"> Basbelopp och momsbelopp för momstransaktioner kan sammanställas baserade på rapporteringskoder i momsrapporten (XML-taggar eller deklarationsrutor).</span><span class="sxs-lookup"><span data-stu-id="f5595-147">Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes).</span></span> <span data-ttu-id="f5595-148">Du kan konfigurera detta genom att associera momsrapporteringskoder för olika transaktionstyper för momskoder på sidan <strong>Momskoder</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-148">You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="f5595-149">Följande tabell beskriver transaktionstyperna i rapportinställningarna för momskoder.</span><span class="sxs-lookup"><span data-stu-id="f5595-149">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="f5595-150">Beräkningen innefattar transaktioner för alla typer av källor utom moms.</span><span class="sxs-lookup"><span data-stu-id="f5595-150">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f5595-151"><strong>Transaktionstyp</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-151"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="f5595-152"><strong>Beskrivning av transaktioner och belopp som ska räknas in i transaktionstypen</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-152"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-153"><strong>Momspliktig försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-153"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="f5595-154">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-154">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-155">Transaktionsdatumet ligger i den valda perioden/</span><span class="sxs-lookup"><span data-stu-id="f5595-155">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="f5595-156">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-156">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-157">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-157">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-158"><strong>Skattefri försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-158"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="f5595-159">Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-159">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-160">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-160">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-161">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-161">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="f5595-162">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-162">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-163"><strong>Momsskuld</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-163"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="f5595-164">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-164">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-165">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-165">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-166">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-166">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-167">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-167">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-168"><strong>Momspliktiga försäljningskreditfakturor</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-168"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-169">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-169">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-170">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-170">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-171">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-171">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-172">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-172">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-173"><strong>Momsbefriad försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-173"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-174">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-174">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-175">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-175">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-176">Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-176">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="f5595-177">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-177">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-178"><strong>Moms på försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-178"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-179">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-179">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-180">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-180">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-181">Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-181">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-182">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-182">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-183"><strong>Skattepliktiga inköp</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-183"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="f5595-184">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-184">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-185">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-185">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-186">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-186">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-187">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-187">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-188"><strong>Skattefritt inköp</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-188"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="f5595-189">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-189">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-190">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-190">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-191">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-191">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="f5595-192">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-192">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-193"><strong>Momsfordran</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-193"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="f5595-194">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-194">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-195">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-195">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-196">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-196">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-197">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-197">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-198"><strong>Momspliktig inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-198"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-199">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-199">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-200">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-200">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-201">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-201">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-202">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-202">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-203"><strong>Momsbefriad inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-203"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-204">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-204">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-205">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-205">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-206">Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-206">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="f5595-207">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-207">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-208"><strong>Moms på inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-208"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-209">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-209">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-210">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-210">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-211">Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="f5595-211">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="f5595-212">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-212">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-213"><strong>Skattepliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-213"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="f5595-214">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-214">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-215">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-215">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-216"><strong>Momsriktningen</strong> är <strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-216"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="f5595-217">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-217">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-218"><strong>Motbokning momspliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-218"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="f5595-219">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-219">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-220">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-220">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-221"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-221"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f5595-222">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-222">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-223"><strong>Momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-223"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-224">Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-224">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-225">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-225">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="f5595-226">e</span><span class="sxs-lookup"><span data-stu-id="f5595-226">e</span></span><li><span data-ttu-id="f5595-227"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-227"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f5595-228">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-228">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-229"><strong>Motbokad momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-229"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="f5595-230">Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-230">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-231">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-231">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-232">Momsriktningen är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-232">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="f5595-233">d</span><span class="sxs-lookup"><span data-stu-id="f5595-233">d</span></span><li><span data-ttu-id="f5595-234">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-234">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5595-235"><strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-235"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="f5595-236">Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-236">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-237">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-237">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-238"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-238"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f5595-239">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-239">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5595-240"><strong>Motbokning av importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="f5595-240"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="f5595-241">Återförd summa för <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f5595-241">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="f5595-242">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="f5595-242">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="f5595-243"><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5595-243"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="f5595-244">Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="f5595-244">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f5595-245">För tabellen ovan förutsätts att följande kriterier uppfylls:</span><span class="sxs-lookup"><span data-stu-id="f5595-245">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="f5595-246">Momsunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="f5595-246">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="f5595-247">Momsbeloppet är ett transaktionsbelopp från fältet **Faktiskt momsbelopp i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="f5595-247">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="f5595-248">Konfigurera ER-modell och format för rapporten</span><span class="sxs-lookup"><span data-stu-id="f5595-248">Configure the ER model and format for the report</span></span>

<span data-ttu-id="f5595-249">Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden.</span><span class="sxs-lookup"><span data-stu-id="f5595-249">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="f5595-250">För mer information:</span><span class="sxs-lookup"><span data-stu-id="f5595-250">For additional information:</span></span>

-   [<span data-ttu-id="f5595-251">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f5595-251">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="f5595-252">Hämta konfigurationer för elektronisk rapportering från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="f5595-252">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="f5595-253">Lokaliseringskrav – Skapa en GER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="f5595-253">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="f5595-254">Landspecifika resurser för momsrapporter</span><span class="sxs-lookup"><span data-stu-id="f5595-254">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="f5595-255">Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning.</span><span class="sxs-lookup"><span data-stu-id="f5595-255">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="f5595-256">Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="f5595-256">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="f5595-257">Land</span><span class="sxs-lookup"><span data-stu-id="f5595-257">Country</span></span>        | <span data-ttu-id="f5595-258">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f5595-258">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="f5595-259">Österrike</span><span class="sxs-lookup"><span data-stu-id="f5595-259">Austria</span></span>        |  [<span data-ttu-id="f5595-260">Detaljerad momsinformation för Österrike</span><span class="sxs-lookup"><span data-stu-id="f5595-260">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="f5595-261">Belgien</span><span class="sxs-lookup"><span data-stu-id="f5595-261">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="f5595-262">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f5595-262">Czech Republic</span></span> |  [<span data-ttu-id="f5595-263">Detaljerad momsrapport för Tjeckien</span><span class="sxs-lookup"><span data-stu-id="f5595-263">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="f5595-264">Estland</span><span class="sxs-lookup"><span data-stu-id="f5595-264">Estonia</span></span>        |  [<span data-ttu-id="f5595-265">Detaljerad momsinformation för Estland</span><span class="sxs-lookup"><span data-stu-id="f5595-265">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="f5595-266">Finland</span><span class="sxs-lookup"><span data-stu-id="f5595-266">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="f5595-267">Tyskland</span><span class="sxs-lookup"><span data-stu-id="f5595-267">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="f5595-268">Italien</span><span class="sxs-lookup"><span data-stu-id="f5595-268">Italy</span></span>          | [<span data-ttu-id="f5595-269">Detaljerad momsinformation för Italien</span><span class="sxs-lookup"><span data-stu-id="f5595-269">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="f5595-270">Lettland</span><span class="sxs-lookup"><span data-stu-id="f5595-270">Latvia</span></span>         | [<span data-ttu-id="f5595-271">Detaljerad momsinformation för Lettland</span><span class="sxs-lookup"><span data-stu-id="f5595-271">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="f5595-272">Litauen</span><span class="sxs-lookup"><span data-stu-id="f5595-272">Lithuania</span></span>      | [<span data-ttu-id="f5595-273">Detaljerad momsinformation för Litauen</span><span class="sxs-lookup"><span data-stu-id="f5595-273">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="f5595-274">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="f5595-274">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="f5595-275">Sverige</span><span class="sxs-lookup"><span data-stu-id="f5595-275">Sweden</span></span>         |                                                                                 |





