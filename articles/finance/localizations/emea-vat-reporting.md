---
title: Momsrapporter för Europa
description: Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: efa9be4a5243444c2bf0b154836efbf8cfa76de9
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894672"
---
# <a name="vat-reporting-for-europe"></a><span data-ttu-id="3495e-103">Momsrapporter för Europa</span><span class="sxs-lookup"><span data-stu-id="3495e-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3495e-104">Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="3495e-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="3495e-105">Det här avsnittet innehåller en allmän metod för inställning och skapande av momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="3495e-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="3495e-106">Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:</span><span class="sxs-lookup"><span data-stu-id="3495e-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="3495e-107">Österrike</span><span class="sxs-lookup"><span data-stu-id="3495e-107">Austria</span></span>
-   <span data-ttu-id="3495e-108">Belgien</span><span class="sxs-lookup"><span data-stu-id="3495e-108">Belgium</span></span>
-   <span data-ttu-id="3495e-109">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3495e-109">Czech Republic</span></span>
-   <span data-ttu-id="3495e-110">Estland</span><span class="sxs-lookup"><span data-stu-id="3495e-110">Estonia</span></span>
-   <span data-ttu-id="3495e-111">Finland</span><span class="sxs-lookup"><span data-stu-id="3495e-111">Finland</span></span>
-   <span data-ttu-id="3495e-112">Tyskland</span><span class="sxs-lookup"><span data-stu-id="3495e-112">Germany</span></span>
-   <span data-ttu-id="3495e-113">Lettland</span><span class="sxs-lookup"><span data-stu-id="3495e-113">Latvia</span></span>
-   <span data-ttu-id="3495e-114">Litauen</span><span class="sxs-lookup"><span data-stu-id="3495e-114">Lithuania</span></span>
-   <span data-ttu-id="3495e-115">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="3495e-115">Netherlands</span></span>
-   <span data-ttu-id="3495e-116">Sverige</span><span class="sxs-lookup"><span data-stu-id="3495e-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="3495e-117">Översikt över momsrapport</span><span class="sxs-lookup"><span data-stu-id="3495e-117">VAT statement overview</span></span>
<span data-ttu-id="3495e-118">Skatteutdraget baseras på beloppen i momstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="3495e-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="3495e-119">Att skapa ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms.</span><span class="sxs-lookup"><span data-stu-id="3495e-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="3495e-120">Den här funktionen beräknar momsen som ska betalas för en given period.</span><span class="sxs-lookup"><span data-stu-id="3495e-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="3495e-121">Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="3495e-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="3495e-122">Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML).</span><span class="sxs-lookup"><span data-stu-id="3495e-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="3495e-123">För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import.</span><span class="sxs-lookup"><span data-stu-id="3495e-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="3495e-124">Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3495e-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="3495e-125">En specifik rapportlayout för varje momsrapporteringskod bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="3495e-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="3495e-126">Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="3495e-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="3495e-127">En specifik rapportlayout för varje momsmyndighet bör fastställas.</span><span class="sxs-lookup"><span data-stu-id="3495e-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="3495e-128">Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden.</span><span class="sxs-lookup"><span data-stu-id="3495e-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="3495e-129">En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta).</span><span class="sxs-lookup"><span data-stu-id="3495e-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="3495e-130">Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder.</span><span class="sxs-lookup"><span data-stu-id="3495e-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="3495e-131">Illustrationen som följer visar datarelationen.</span><span class="sxs-lookup"><span data-stu-id="3495e-131">The following illustration shows the data relationship.</span></span>

![diagram](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="3495e-133">Inställningar för momsrapport</span><span class="sxs-lookup"><span data-stu-id="3495e-133">VAT statement setup</span></span>
<span data-ttu-id="3495e-134">Om du vill skapa en momsrapport måste du konfigurera följande:</span><span class="sxs-lookup"><span data-stu-id="3495e-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="3495e-135">Momsmyndigheter för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="3495e-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="3495e-136">Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten.</span><span class="sxs-lookup"><span data-stu-id="3495e-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="3495e-137">På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**.</span><span class="sxs-lookup"><span data-stu-id="3495e-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="3495e-138">Den här layouten används när du ställer in momsrapporteringskoder.</span><span class="sxs-lookup"><span data-stu-id="3495e-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="3495e-139">Momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="3495e-139">Sales tax reporting codes</span></span>

<span data-ttu-id="3495e-140">Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format.</span><span class="sxs-lookup"><span data-stu-id="3495e-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="3495e-141">Koderna används för att sammanställa och förbereda beloppen för rapporten.</span><span class="sxs-lookup"><span data-stu-id="3495e-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="3495e-142">Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="3495e-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="3495e-143">Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="3495e-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="3495e-144">Du måste tilldela en rapportlayout åt varje kod.</span><span class="sxs-lookup"><span data-stu-id="3495e-144">You must assign each code a report layout.</span></span> <span data-ttu-id="3495e-145">När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="3495e-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="3495e-146">Momskoder för momsrapportering</span><span class="sxs-lookup"><span data-stu-id="3495e-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> <span data-ttu-id="3495e-147"> Basbelopp och momsbelopp för momstransaktioner kan sammanställas baserade på rapporteringskoder i momsrapporten (XML-taggar eller deklarationsrutor).</span><span class="sxs-lookup"><span data-stu-id="3495e-147">Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes).</span></span> <span data-ttu-id="3495e-148">Du kan konfigurera detta genom att associera momsrapporteringskoder för olika transaktionstyper för momskoder på sidan <strong>Momskoder</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-148">You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="3495e-149">Följande tabell beskriver transaktionstyperna i rapportinställningarna för momskoder.</span><span class="sxs-lookup"><span data-stu-id="3495e-149">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="3495e-150">Beräkningen innefattar transaktioner för alla typer av källor utom moms.</span><span class="sxs-lookup"><span data-stu-id="3495e-150">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3495e-151"><strong>Transaktionstyp</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-151"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="3495e-152"><strong>Beskrivning av transaktioner och belopp som ska räknas in i transaktionstypen</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-152"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-153"><strong>Momspliktig försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-153"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="3495e-154">Summan av <strong>Skatteunderlagsbelopp</strong> för skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-154">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-155">Transaktionsdatumet ligger i den valda perioden/</span><span class="sxs-lookup"><span data-stu-id="3495e-155">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="3495e-156">Försäljningen är lokal (<strong>Skatteriktning</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-156">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-157">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-157">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-158"><strong>Skattefri försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-158"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="3495e-159">Summan av <strong>Skatteunderlagsbelopp</strong> för skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-159">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-160">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-160">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-161">Försäljningen är export (<strong>Skatteriktning</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-161">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="3495e-162">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-162">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-163"><strong>Momsskuld</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-163"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="3495e-164">Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-164">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-165">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-165">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-166">Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-166">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-167">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-167">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-168"><strong>Momspliktiga försäljningskreditfakturor</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-168"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-169">Summan av <strong>Skatteunderlagsbeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-169">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-170">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-170">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-171">Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-171">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-172">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-172">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-173"><strong>Momsbefriad försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-173"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-174">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-174">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-175">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-175">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-176">Försäljningen är export (<strong>Skatteriktningen</strong> är <strong>Skattefri försäljning</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-176">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="3495e-177">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-177">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-178"><strong>Moms på försäljningskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-178"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-179">Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-179">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-180">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-180">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-181">Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-181">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-182">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-182">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-183"><strong>Skattepliktiga inköp</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-183"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="3495e-184">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-184">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-185">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-185">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-186">Försäljningen är inhemsk (<strong>Skatteriktningen</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-186">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-187">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-187">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-188"><strong>Skattefritt inköp</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-188"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="3495e-189">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-189">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-190">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-190">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-191">Inköpet är import (<strong>Skatteriktningen</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-191">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="3495e-192">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-192">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-193"><strong>Momsfordran</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-193"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="3495e-194">Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-194">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-195">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-195">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-196">Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-196">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-197">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-197">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-198"><strong>Momspliktig inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-198"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-199">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-199">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-200">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-200">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-201">Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-201">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-202">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-202">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-203"><strong>Momsbefriad inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-203"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-204">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-204">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-205">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-205">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-206">Inköpet är import (<strong>Skatteriktning</strong> är <strong>Skattefritt inköp</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-206">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="3495e-207">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-207">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-208"><strong>Moms på inköpskreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-208"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-209">Summan av <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-209">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-210">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-210">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-211">Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</span><span class="sxs-lookup"><span data-stu-id="3495e-211">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="3495e-212">Transaktionens <strong>Skattbasbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-212">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-213"><strong>Skattepliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-213"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="3495e-214">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-214">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-215">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-215">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-216"><strong>Skatteriktningen</strong> är <strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-216"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="3495e-217">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-217">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-218"><strong>Motbokning momspliktig import</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-218"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="3495e-219">Återförd summa för <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-219">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-220">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-220">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-221"><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-221"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3495e-222">Transaktionens <strong>Skattbasbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-222">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-223"><strong>Momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-223"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-224">Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-224">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-225">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-225">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="3495e-226">e</span><span class="sxs-lookup"><span data-stu-id="3495e-226">e</span></span><li><span data-ttu-id="3495e-227"><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-227"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3495e-228">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-228">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-229"><strong>Motbokad momspliktig importkreditfaktura</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-229"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="3495e-230">Återförd summa för <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-230">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-231">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-231">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-232">Skatteriktningen är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-232">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="3495e-233">d</span><span class="sxs-lookup"><span data-stu-id="3495e-233">d</span></span><li><span data-ttu-id="3495e-234">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-234">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3495e-235"><strong>Importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-235"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="3495e-236">Summan av <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-236">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-237">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-237">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-238"><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-238"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3495e-239">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-239">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3495e-240"><strong>Motbokning av importavgift</strong></span><span class="sxs-lookup"><span data-stu-id="3495e-240"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="3495e-241">Återförd summa för <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3495e-241">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="3495e-242">Transaktionsdatumet ligger i den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="3495e-242">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="3495e-243"><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</span><span class="sxs-lookup"><span data-stu-id="3495e-243"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="3495e-244">Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</span><span class="sxs-lookup"><span data-stu-id="3495e-244">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3495e-245">För tabellen ovan förutsätts att följande kriterier uppfylls:</span><span class="sxs-lookup"><span data-stu-id="3495e-245">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="3495e-246">Skatteunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="3495e-246">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="3495e-247">Skattebeloppet är ett transaktionsbelopp från fältet **Faktiskt skattebelopp i redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="3495e-247">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="3495e-248">Konfigurera ER-modell och format för rapporten</span><span class="sxs-lookup"><span data-stu-id="3495e-248">Configure the ER model and format for the report</span></span>

<span data-ttu-id="3495e-249">Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden.</span><span class="sxs-lookup"><span data-stu-id="3495e-249">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="3495e-250">För mer information:</span><span class="sxs-lookup"><span data-stu-id="3495e-250">For additional information:</span></span>

-   [<span data-ttu-id="3495e-251">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="3495e-251">Electronic reporting overview</span></span>](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="3495e-252">Hämta konfigurationer för elektronisk rapportering från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="3495e-252">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="3495e-253">Lokaliseringskrav – Skapa en GER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="3495e-253">Localization requirements – Create a GER configuration</span></span>](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="3495e-254">Landspecifika resurser för momsrapporter</span><span class="sxs-lookup"><span data-stu-id="3495e-254">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="3495e-255">Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning.</span><span class="sxs-lookup"><span data-stu-id="3495e-255">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="3495e-256">Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="3495e-256">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="3495e-257">Land</span><span class="sxs-lookup"><span data-stu-id="3495e-257">Country</span></span>        | <span data-ttu-id="3495e-258">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="3495e-258">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="3495e-259">Österrike</span><span class="sxs-lookup"><span data-stu-id="3495e-259">Austria</span></span>        |  [<span data-ttu-id="3495e-260">Detaljerad momsinformation för Österrike</span><span class="sxs-lookup"><span data-stu-id="3495e-260">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="3495e-261">Belgien</span><span class="sxs-lookup"><span data-stu-id="3495e-261">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="3495e-262">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3495e-262">Czech Republic</span></span> |  [<span data-ttu-id="3495e-263">Momsutdrag för Tjeckien</span><span class="sxs-lookup"><span data-stu-id="3495e-263">VAT statement for the Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="3495e-264">Estland</span><span class="sxs-lookup"><span data-stu-id="3495e-264">Estonia</span></span>        |  [<span data-ttu-id="3495e-265">Detaljerad momsinformation för Estland</span><span class="sxs-lookup"><span data-stu-id="3495e-265">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="3495e-266">Finland</span><span class="sxs-lookup"><span data-stu-id="3495e-266">Finland</span></span>        | [<span data-ttu-id="3495e-267">Momsrapport för Finland</span><span class="sxs-lookup"><span data-stu-id="3495e-267">Sales tax report for Finland</span></span>](emea-fin-sales-tax-payment-report-finland.md)          |
| <span data-ttu-id="3495e-268">Tyskland</span><span class="sxs-lookup"><span data-stu-id="3495e-268">Germany</span></span>        | [<span data-ttu-id="3495e-269">Momsdeklaration för Tyskland</span><span class="sxs-lookup"><span data-stu-id="3495e-269">VAT declaration for Germany</span></span>](emea-de-vat-declaration.md)                       |
| <span data-ttu-id="3495e-270">Italien</span><span class="sxs-lookup"><span data-stu-id="3495e-270">Italy</span></span>          | [<span data-ttu-id="3495e-271">Detaljerad momsinformation för Italien</span><span class="sxs-lookup"><span data-stu-id="3495e-271">VAT statements details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="3495e-272">Lettland</span><span class="sxs-lookup"><span data-stu-id="3495e-272">Latvia</span></span>         | [<span data-ttu-id="3495e-273">Detaljerad momsinformation för Lettland</span><span class="sxs-lookup"><span data-stu-id="3495e-273">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="3495e-274">Litauen</span><span class="sxs-lookup"><span data-stu-id="3495e-274">Lithuania</span></span>      | [<span data-ttu-id="3495e-275">Detaljerad momsinformation för Litauen</span><span class="sxs-lookup"><span data-stu-id="3495e-275">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="3495e-276">Nederländerna</span><span class="sxs-lookup"><span data-stu-id="3495e-276">Netherlands</span></span>    | [<span data-ttu-id="3495e-277">Momsdeklaration för Nederländerna</span><span class="sxs-lookup"><span data-stu-id="3495e-277">VAT declaration for the Netherlands</span></span>](emea-nl-vat-declaration.md)           |
| <span data-ttu-id="3495e-278">Sverige</span><span class="sxs-lookup"><span data-stu-id="3495e-278">Sweden</span></span>         | [<span data-ttu-id="3495e-279">Momsrapport för Sverige</span><span class="sxs-lookup"><span data-stu-id="3495e-279">Sales tax report for Sweden</span></span>](emea-swe-sales-tax-payment-report-sweden.md)          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]