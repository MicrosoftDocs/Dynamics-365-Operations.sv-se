---
title: Intrastat
description: "Det här avsnittet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU). Det ger en översikt över rapporteringsprocessen och beskriver nödvändiga inställningar och förutsättningar."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d927f827b9cbc0dc6d9ba5a22c8a05371836faff
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="intrastat"></a><span data-ttu-id="a8fe8-104">Intrastat</span><span class="sxs-lookup"><span data-stu-id="a8fe8-104">Intrastat</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8fe8-105">Det här avsnittet ger information om Intrastat-rapportering för handel av varor och, i vissa fall, tjänster mellan länder/regioner i den Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="a8fe8-105">This article provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="a8fe8-106">Det ger en översikt över rapporteringsprocessen och beskriver nödvändiga inställningar och förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="a8fe8-107">Intrastat är systemet för att samla information och generera statistik över handeln med varor mellan länder/regioner i den Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="a8fe8-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="a8fe8-108">Intrastat-rapportering krävs när en produkt korsar gränsen till ett annat EU-land eller en annan EU-region.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="a8fe8-109">I flera länder/regioner gäller Intrastat-rapportering även för tjänster.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="a8fe8-110">Obligatoriska och valfria element kan samlas in i Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="a8fe8-111">Följande element är obligatoriska: momsnumret för parten som ansvarar för att ge information, referensperioden, flödet (införsel eller utförsel), den åttasiffriga artikelkoden, partnerns medlemsstat (medlemsstaten för försändelsen vid införsel och medlemsstaten för destinationen vid utförsel), värdet på varorna, varornas kvantitet (nettomassa och fyllnadsenhet) och transaktionens natur.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="a8fe8-112">Länder/regioner kan också samla in valfria element under olika omständigheter.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="a8fe8-113">Exempel på valfria element är ursprungsland/ursprungsregion, leveransvillkor, transportsätt, en mer detaljerad artikelkod än CN8, ursprungsregionen vid utförsel och måldestinationen vid införsel, den statistiska proceduren, det statistiska värdet, en beskrivning av varorna och hamn/flygplats för lastning/avlastning.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="a8fe8-114">Översikt över processen vid Intrastat-rapportering</span><span class="sxs-lookup"><span data-stu-id="a8fe8-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="a8fe8-115">Följande avsnitt beskriver det generella flödet av information som används för Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="a8fe8-116">1. Ange en transaktion som korsar gränsen till ett annat EU-land eller en annan EU-region</span><span class="sxs-lookup"><span data-stu-id="a8fe8-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="a8fe8-117">En kundfaktura, fritextfaktura, inköpsfaktura, projektfaktura, kundföljesedel, produktinleverans för leverantör eller överföringsorder överförs bara till Intrastat-journalen om landet/regionen för destinationen (vid utförsel) eller försändelsen (vid införsel) är **EU**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="a8fe8-118">Denna funktion har utökats för Microsoft Dynamics 365 for Operations version 1611 och låter dig ange fraktadresser för en transaktion inom gemenskapen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="a8fe8-119">Om en fraktadress skiljer sig åt från en leverantörsföretagsadress (eller en kunderföretagsadress för returorder), fungerar Intrastat-rapporteringen med den här informationen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="a8fe8-120">När du skapar en försäljningsorder, fritextfaktura, inköpsorder, leverantörsfaktura, projektfaktura eller överföringsorder har vissa fält som är relaterade till utländsk handel standardvärden i dokumenthuvudet eller på raden.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="a8fe8-121">Standardtransaktionskoden hämtas från motsvarande fält på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-122">Standardartikelkoden, ursprungsland/ursprungsregion och ursprungsstat/ursprungsprovins hämtas från artikeln.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="a8fe8-123">Du kan ändra standardvärdena och du kan även fylla i annan utländsk handelsrelaterad information: statistikprocedur, transportmetod och hamn.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="a8fe8-124">2. Använd Intrastat-journalen för att generera information om handel mellan EU-länder/EU-regioner</span><span class="sxs-lookup"><span data-stu-id="a8fe8-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="a8fe8-125">För statistiska ändamål genererar du information om handeln mellan EU-länder/EU-regioner varje månad.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="a8fe8-126">Du kan överföra transaktioner från en fritextfaktura, kundfaktura, kundföljesedel, leverantörsfaktura, leverantörföljesedel, projektfaktura eller överföringsorder enligt överföringsvillkoren som har ställts in på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-127">Alternativt kan du ange transaktioner manuellt.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="a8fe8-128">Du kan uppdatera överförda transaktioner manuellt i Intrastat-journalen om uppdateringar krävs.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="a8fe8-129">Under vissa förhållanden som ställs in på sidan **Komprimering av Intrastat** kan du komprimera transaktionerna i Intrastat-journalen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="a8fe8-130">Vissa länder/regioner låter dig tillämpa en liten transaktionströskel.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="a8fe8-131">Du kan då rapportera transaktioner som är under det tröskelvärdet under den angivna artikelkoden.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="a8fe8-132">Du kan uppdatera artikelkoden på motsvarande Intrastat-journalrader baserat på inställningen **Minimigräns** på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-133">Du kan också komprimera dessa transaktioner baserat på inställningen **Komprimering av Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="a8fe8-134">Du kan validera fullständigheten för transaktionerna i Intrastat-journalen baserat på inställningen **Checkinställningar** på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-135">Data i motsvarande fält kan valideras för fullständighet: land/region, delstat eller provins, vikt, artikelkod, transaktionskod, fyllnadsenhet, hamn, ursprung, leveransvillkor, transportmetod och momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="a8fe8-136">Transaktioner som inte är kompletta markeras som inte giltiga.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="a8fe8-137">3. Använd Intrastat-journalen för att rapportera information om handel mellan EU-länder/EU-regioner</span><span class="sxs-lookup"><span data-stu-id="a8fe8-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="a8fe8-138">För statistiska ändamål rapporterar du information om handeln mellan EU-länder/EU-regioner varje månad.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="a8fe8-139">Du kan skriva ut Intrastat-rapporten baserat på inställningarna för **Mappning av rapportformat** på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-140">Du kan även generera en elektronisk fil baserat på inställningarna för **Mappning av filformat** på sidan **Utländska handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="a8fe8-141">Se uppgiftsinspelningar för Intrastat-rapportering om du vill ha mer information om Intrastat-rapportering:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="a8fe8-142">Generera en EU Intrastat-deklaration,</span><span class="sxs-lookup"><span data-stu-id="a8fe8-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="a8fe8-143">Överföra transaktioner till Intrastat,</span><span class="sxs-lookup"><span data-stu-id="a8fe8-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="a8fe8-144">Ange fraktadressen för en inomeuropeisk transaktion.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8fe8-145">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a8fe8-145">Prerequisites</span></span>
<span data-ttu-id="a8fe8-146">Följande tabell anger förutsättningarna för Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8fe8-147">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="a8fe8-147">Prerequisite</span></span></th>
<th><span data-ttu-id="a8fe8-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a8fe8-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8fe8-149">Adressinställning</span><span class="sxs-lookup"><span data-stu-id="a8fe8-149">Address setup</span></span></td>
<td><span data-ttu-id="a8fe8-150">Ställ in ISO-koder (International Organization for Standardization) för länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-151">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="a8fe8-151">Legal entity</span></span></td>
<td><span data-ttu-id="a8fe8-152">Ställ in momsregistreringsnummer för import/export, filialnummertillägg för import/export och Intrastat-koden som tilldelas den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-153">Produktkategorihierarki (försäljningshierarki, anskaffningshierarki)</span><span class="sxs-lookup"><span data-stu-id="a8fe8-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="a8fe8-154">Tilldela Intrastat-artikelkoderna till kategorinoder på fliken <strong>Artikelkoder</strong> på sidan <strong>Kategorihierarki</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="a8fe8-155">När du tilldelar en artikelkod till en överordnad kategorinod gäller den koden för alla underordnade kategorinoder.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="a8fe8-156">De valda artikelkoderna är tillgängliga i vyn <strong>Markerad</strong> när du väljer en artikelkod i informationen om frisläppta produkter och på försäljningsorder-, inköpsorder- och överföringsorderrader.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-157">Information om frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="a8fe8-157">Released product details</span></span></td>
<td><span data-ttu-id="a8fe8-158">Ställ in följande information om utrikeshandel för frisläppta produkter:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-159"><strong>Artikelkod</strong> – Välj från listan över valda varor som hämtas från tilldelade produktkategorier eller från hela listan med Intrastat-artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="a8fe8-160"><strong>Procent för statistiska avgifter</strong></span><span class="sxs-lookup"><span data-stu-id="a8fe8-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="a8fe8-161"><strong>Ursprungsland/ursprungsregion</strong> – Välj standardlandet/standardregionen där varorna erhölls helt eller tillverkades.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="a8fe8-162"><strong>Delstat/provins för ursprung/destination</strong> – Välj den förvalda delstaten/provinsen för destinationen för införsel och ursprungsdelstaten/ursprungsprovinsen för utförsel.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="a8fe8-163"><strong>Nettovikt i kg</strong></span><span class="sxs-lookup"><span data-stu-id="a8fe8-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-164">Kunder</span><span class="sxs-lookup"><span data-stu-id="a8fe8-164">Customers</span></span></td>
<td><span data-ttu-id="a8fe8-165">Ställ in kundens leveransadress i EU-landet/EU-regionen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-166">Leverantörer</span><span class="sxs-lookup"><span data-stu-id="a8fe8-166">Vendors</span></span></td>
<td><span data-ttu-id="a8fe8-167">Ställ in leverantörens adress i EU-landet/EU-regionen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-168">Övriga avgifter</span><span class="sxs-lookup"><span data-stu-id="a8fe8-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="a8fe8-169">Ställ in tilläggskoden som ska tas med i fakturabeloppet, det statistiska beloppet eller båda.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="a8fe8-170">På sidan <strong>Avgiftskoder</strong> på fliken <strong>Utländsk handel</strong> aktiverar du <strong>Intrastat-fakturavärde</strong> om du vill inkludera avgiftsbeloppen i fakturavärdet och aktiverar <strong>Intrastat-statistikvärde</strong> om du vill ta med avgiftsbeloppet i det statistiska värdet.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-171">Elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="a8fe8-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="a8fe8-172">Ställ in konfigurationer för elektronisk rapportering när du vill exportera Intrastat-data i en elektronisk fil som har formatet som krävs av relevanta myndigheter och för att granska Intrastat-data i ett användarvänligt, läsbart format (exempelvis i Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="a8fe8-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-173">Lagerförvaring</span><span class="sxs-lookup"><span data-stu-id="a8fe8-173">Warehousing</span></span></td>
<td><span data-ttu-id="a8fe8-174">Associera leverantörskonton med lagerkoder för att ange mombefrielsenummer när du överför överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="a8fe8-175">Inställningar</span><span class="sxs-lookup"><span data-stu-id="a8fe8-175">Setup</span></span>
<span data-ttu-id="a8fe8-176">Följande avsnitt beskriver de inställningar som krävs för Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="a8fe8-177">Ställ in alla nödvändiga Intrastat-relaterade listor</span><span class="sxs-lookup"><span data-stu-id="a8fe8-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8fe8-178">Lista</span><span class="sxs-lookup"><span data-stu-id="a8fe8-178">List</span></span></th>
<th><span data-ttu-id="a8fe8-179">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="a8fe8-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8fe8-180">Artikelkoder</span><span class="sxs-lookup"><span data-stu-id="a8fe8-180">Commodity codes</span></span></td>
<td><span data-ttu-id="a8fe8-181">Ställ in en kategorihierarki av typen <strong>Artikelkod</strong> och ange alla artikelkoder enligt den kombinerade nomenklaturlistan.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="a8fe8-182">För varje vara ställer du in följande information:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-183">Namnet på varan och artikelkoden</span><span class="sxs-lookup"><span data-stu-id="a8fe8-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="a8fe8-184">Det egna namnet och/eller det översatta namnet</span><span class="sxs-lookup"><span data-stu-id="a8fe8-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="a8fe8-185">Inställningar för att rapportera ytterligare (kompletterande) enheter på fliken <strong>Utrikeshandel</strong>. Du kan välja ytterligare enheter i enhetslistan.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="a8fe8-186">Du kan även ange om vikten av varorna måste rapporteras utöver den valda ytterligare enheten.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-187">Transaktionskoder</span><span class="sxs-lookup"><span data-stu-id="a8fe8-187">Transaction codes</span></span></td>
<td><span data-ttu-id="a8fe8-188">Ställ in transaktionens natur enligt landets/regionens krav.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-188">Set up the nature of the transaction according to your country&#39;s/region&#39;s requirements.</span></span> <span data-ttu-id="a8fe8-189">För varje transaktionskod som du anger måste du ställa in reglerna för att beräkna fakturabelopp och statistiska belopp för överföringsorder och försäljnings-/inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="a8fe8-190">För överföringsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-191"><strong>Tom</strong> – Beloppet kommer att vara 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a8fe8-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="a8fe8-192"><strong>Ekonomiskt självkostnadsbelopp</strong> – Beloppet kommer att vara lika med den ekonomiska kostnaden.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="a8fe8-193"><strong>Total kostnad</strong> – Beloppet kommer att vara lika med totalkostnaden för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="a8fe8-194"><strong>Manuellt</strong> – Beloppet kommer att vara samma som det belopp som angetts manuellt på överföringsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="a8fe8-195">För försäljnings- och inköpsorder ställer du in en av följande regler för beräkning av fakturabelopp och statistiska belopp:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-196"><strong>Tom</strong> – Beloppet kommer att vara 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a8fe8-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="a8fe8-197"><strong>Fakturabelopp</strong> – Beloppet kommer att vara samma som det fakturerade beloppet för varan.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="a8fe8-198"><strong>Basbelopp</strong> – Beloppet kommer att vara samma som det fakturerade beloppet före en eventuell rabatt.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-199">Transportmetoder</span><span class="sxs-lookup"><span data-stu-id="a8fe8-199">Transport methods</span></span></td>
<td><span data-ttu-id="a8fe8-200">Ställ in transportsätt enligt landets/regionens krav.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-200">Set up the transport mode according to your country&#39;s/region&#39;s requirements.</span></span> <span data-ttu-id="a8fe8-201">För varje leveranssätt kan du ställa in en standardtransportmetod på fliken <strong>Utländsk handel</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-202">Hamnar</span><span class="sxs-lookup"><span data-stu-id="a8fe8-202">Ports</span></span></td>
<td><span data-ttu-id="a8fe8-203">Ställ in hamnen/flygplatsen för lastning/avlastning om denna information samlas in av ditt land/din region.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-204">Statistikprocedurer</span><span class="sxs-lookup"><span data-stu-id="a8fe8-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="a8fe8-205">Ställ in statistikproceduren om denna information samlas in av ditt land/din region.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="a8fe8-206">Ställ in regler för komprimeringen av Intrastat-transaktioner</span><span class="sxs-lookup"><span data-stu-id="a8fe8-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="a8fe8-207">På sidan **Komprimering av Intrastat** kan du välja vilka fält du vill använda för komprimering.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="a8fe8-208">Alla transaktioner som har samma kombination av värden för de valda fälten i Intrastat-journalen komprimeras till en enda transaktion när du kör funktionen Komprimera i Intrastat-journalen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="a8fe8-209">Konfigurera utländska handelsparametrar</span><span class="sxs-lookup"><span data-stu-id="a8fe8-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="a8fe8-210">Använd sidan **Utländska handelsparametrar** för att ställa in parametrarna i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8fe8-211">Flik</span><span class="sxs-lookup"><span data-stu-id="a8fe8-211">Tab</span></span></th>
<th><span data-ttu-id="a8fe8-212">Parametrar</span><span class="sxs-lookup"><span data-stu-id="a8fe8-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8fe8-213">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a8fe8-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="a8fe8-214"><strong>Allmänt</strong> – Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-215">Standardtransaktionskoder för försäljningsorder, inköpsorder, kreditfakturor och överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="a8fe8-216">Transaktionskoden som har ställts in för kreditfakturor används också som koden för fysiska varureturer och används för att avvika fysiska returer jämfört med korrigeringskreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span></li>
<li><span data-ttu-id="a8fe8-217">Medarbetaren som ansvarar för att förbereda Intrastat-rapporter.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-217">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="a8fe8-218"><strong>Minimigräns</strong> – Ange inställningarna för att uppdatera transaktioner som är under tröskeln:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-218"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-219">Tröskelbeloppet och vikten</span><span class="sxs-lookup"><span data-stu-id="a8fe8-219">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="a8fe8-220">Varukoden som ska användas för transaktioner som är under tröskeln</span><span class="sxs-lookup"><span data-stu-id="a8fe8-220">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="a8fe8-221"><strong>Överför</strong> – Ange villkoren för överföring av transaktioner till Intrastat-journalen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-221"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="a8fe8-222">Du kan ange att transaktionerna bara överförs när artiklarna uppfyller något eller alla av följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-222">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-223">Artiklarna är inte serviceartiklar.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-223">The items aren&#39;t service items.</span></span></li>
<li><span data-ttu-id="a8fe8-224">Artiklarna har en varukod.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-224">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="a8fe8-225">Artiklarna har en vikt.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-225">The items have a weight.</span></span></li>
<li><span data-ttu-id="a8fe8-226">Artiklarna har ytterligare enheter.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-226">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="a8fe8-227"><strong>Checkinställningar</strong> – Ange reglerna för att validera fullständigheten av Intrastat-data.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-227"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="a8fe8-228">Du kan välja vilka data som valideras.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-228">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="a8fe8-229"><strong>Avrundningsregler</strong> – Ange följande inställningar för avrundningsbelopp och vikter i Intrastat-rapportering:</span><span class="sxs-lookup"><span data-stu-id="a8fe8-229"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="a8fe8-230">Avrundningsregeln (precision)</span><span class="sxs-lookup"><span data-stu-id="a8fe8-230">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="a8fe8-231">Avrundningsmetod: upp, ned eller normal</span><span class="sxs-lookup"><span data-stu-id="a8fe8-231">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="a8fe8-232">Antal decimaler för belopp och vikter</span><span class="sxs-lookup"><span data-stu-id="a8fe8-232">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="a8fe8-233">Instruktioner för att avrunda vikter som är mindre än 1 kilo (kg): upp till 1 kg, normal eller ingen avrundning</span><span class="sxs-lookup"><span data-stu-id="a8fe8-233">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="a8fe8-234"><strong>Elektronisk rapportering</strong> – Ange referenser till elektroniska rapporteringskonfigurationer så att du kan generera en elektronisk fil och en rapport.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-234"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="a8fe8-235"><strong>Artikelkodhierarki</strong> – Ange kategorihierarkin för typen <strong>Artikelkod</strong> som representerar Intrastat-artikelkoden CN8.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-235"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-236">Kontaktinformation för agent</span><span class="sxs-lookup"><span data-stu-id="a8fe8-236">Agent contact information</span></span></td>
<td><span data-ttu-id="a8fe8-237">Ange agentens namn, adress, momsregistreringsnummer, telefonnummer och faxnummer.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-237">Specify the agent&#39;s name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8fe8-238">Egenskaper för land/region</span><span class="sxs-lookup"><span data-stu-id="a8fe8-238">Country/region properties</span></span></td>
<td><span data-ttu-id="a8fe8-239">Ange ursprungsland/ursprungsregion för den aktuella juridiska personen till <strong>Inrikes</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-239">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="a8fe8-240">Ange ursprungsland/ursprungsregion för EU-länder/EU-regioner som deltar i EU-handel med den aktuella juridiska personen till <strong>EU</strong>.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-240">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="a8fe8-241">För varje land/region identifierar du också lands-/regionskoden för utrikeshandelsyften.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-241">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8fe8-242">Nummerserie</span><span class="sxs-lookup"><span data-stu-id="a8fe8-242">Number sequence</span></span></td>
<td><span data-ttu-id="a8fe8-243">Ange nummerserien för Intrastat-journalen.</span><span class="sxs-lookup"><span data-stu-id="a8fe8-243">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>






