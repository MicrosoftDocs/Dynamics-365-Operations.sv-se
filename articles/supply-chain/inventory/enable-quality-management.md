---
title: Översikt över kvalitetshantering
description: Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba38f9c43fed81768155a27dda88a4bfb4a7828e
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653566"
---
# <a name="quality-management-overview"></a><span data-ttu-id="78511-103">Översikt över kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="78511-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78511-104">Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="78511-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="78511-105">Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett ursprungspunkten.</span><span class="sxs-lookup"><span data-stu-id="78511-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="78511-106">Eftersom diagnostiktyper länkas till korrigeringsrapporteringen kan Supply Chain Management planera uppgifter för att korrigera problem och förhindra dem från att återkomma.</span><span class="sxs-lookup"><span data-stu-id="78511-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="78511-107">Förutom funktioner för att hantera avvikelser inkluderar kvalitetshantering funktioner för att spåra problem efter problemtyp (även interna problem), och för att identifiera lösningar som kortsiktiga och långsiktiga.</span><span class="sxs-lookup"><span data-stu-id="78511-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="78511-108">Statistik om KPI:er (Key Performance Indicator) ger insyn i historiken över tidigare avvikelseproblem och lösningarna som användes för att korrigera dem.</span><span class="sxs-lookup"><span data-stu-id="78511-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="78511-109">Du kan använda historiska data om du vill granska effektiviteten hos tidigare kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.</span><span class="sxs-lookup"><span data-stu-id="78511-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="78511-110">När du ställer in en kvalitetsassociation kan Supply Chain Management skapa kvalitetsorder för olika affärsprocesser, händelser och villkor.</span><span class="sxs-lookup"><span data-stu-id="78511-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="78511-111">Kvalitetsassociationen kan omfatta en viss artikel, en specifik grupp artiklar eller alla artiklar.</span><span class="sxs-lookup"><span data-stu-id="78511-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="78511-112">Exempel på användningen av kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="78511-112">Examples of the use of quality management</span></span>
<span data-ttu-id="78511-113">Kvalitetshanteringen är flexibel och kan implementeras på olika sätt för att uppfylla kraven för specifika nivåer i distributionskedjeåtgärder.</span><span class="sxs-lookup"><span data-stu-id="78511-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="78511-114">Följande exempel illustrerar hur dessa funktioner kan användas:</span><span class="sxs-lookup"><span data-stu-id="78511-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="78511-115">Starta automatiskt en kvalitetskontrollprocess baserat på fördefinierade villkor (vid lagerställeregistrering av en inköpsorder från en viss leverantör.)</span><span class="sxs-lookup"><span data-stu-id="78511-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="78511-116">Blockera lagret under inspektion för att förhindra icke-godkänt lager från att användas (fullständig blockering av inköpsorderkvantiteter).</span><span class="sxs-lookup"><span data-stu-id="78511-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="78511-117">Använd artikelsamplingen som en del av en kvalitetsassociation för att definiera hur aktuellt fysiskt lager ska inspekteras.</span><span class="sxs-lookup"><span data-stu-id="78511-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="78511-118">Samplingen kan baseras på fasta kvantiteter eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="78511-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="78511-119">Skapa en kvalitetsorder för delleveranser.</span><span class="sxs-lookup"><span data-stu-id="78511-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="78511-120">Om du vill skapa en kvalitetsorder som baseras på den kvantitet som inlevererats fysiskt till en order måste du markera kryssrutan **Per uppdaterad kvantitet** i formuläret **artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="78511-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="78511-121">Skapa testtyper som innehåller minimum-, maximum- och måltestvärden och utför testning av typen ”kvalitativ kontra kvantitativ” som har fördefinierade valideringresultat.</span><span class="sxs-lookup"><span data-stu-id="78511-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="78511-122">Ange en godtagbar kvalitetsnivå (AQL) för att kontrollera toleranserna för kvalitetsmått.</span><span class="sxs-lookup"><span data-stu-id="78511-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="78511-123">Ange resurser som en inspektionsåtgärd kräver, till exempel ett testområde och testinstrument.</span><span class="sxs-lookup"><span data-stu-id="78511-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="78511-124">Arbeta med kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="78511-124">Working with quality associations</span></span>
<span data-ttu-id="78511-125">Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="78511-126">Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="78511-127">Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="78511-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="78511-128">Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras.</span><span class="sxs-lookup"><span data-stu-id="78511-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="78511-129">Beroende på inställningen för körningsplanen kan själva utlösarprocessen spärras medan det finns en öppen kvalitetsorder, eller så kan de efterföljande processerna, till exempel fakturering av inköpsorder, spärras.</span><span class="sxs-lookup"><span data-stu-id="78511-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="78511-130">**Obs!** Medan det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utlevereras.</span><span class="sxs-lookup"><span data-stu-id="78511-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="78511-131">Beroende på inställningen **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden.</span><span class="sxs-lookup"><span data-stu-id="78511-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="78511-132">För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och villkoren som en kvalitetsorder genereras för.</span><span class="sxs-lookup"><span data-stu-id="78511-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="78511-133">Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="78511-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="78511-134">En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.</span><span class="sxs-lookup"><span data-stu-id="78511-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="78511-135">Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i varje affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="78511-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="78511-136">För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.</span><span class="sxs-lookup"><span data-stu-id="78511-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="78511-137">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="78511-137">Reference type</span></span></th>
<th><span data-ttu-id="78511-138">Händelsetyp</span><span class="sxs-lookup"><span data-stu-id="78511-138">Event type</span></span></th>
<th><span data-ttu-id="78511-139">Körning</span><span class="sxs-lookup"><span data-stu-id="78511-139">Execution</span></span></th>
<th><span data-ttu-id="78511-140">Händelsespärr</span><span class="sxs-lookup"><span data-stu-id="78511-140">Event blocking</span></span></th>
<th><span data-ttu-id="78511-141">Dokumentreferens</span><span class="sxs-lookup"><span data-stu-id="78511-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="78511-142">Lager</span><span class="sxs-lookup"><span data-stu-id="78511-142">Inventory</span></span></td>
<td><span data-ttu-id="78511-143">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="78511-143">Not applicable</span></span></td>
<td><span data-ttu-id="78511-144">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="78511-144">Not applicable</span></span></td>
<td><span data-ttu-id="78511-145">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-145">None</span></span></td>
<td><span data-ttu-id="78511-146">Alla</span><span class="sxs-lookup"><span data-stu-id="78511-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="78511-147">Försäljning</span><span class="sxs-lookup"><span data-stu-id="78511-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="78511-148">Plockningsprocess har schemalagts</span><span class="sxs-lookup"><span data-stu-id="78511-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="78511-149">Före</span><span class="sxs-lookup"><span data-stu-id="78511-149">Before</span></span></td>
<td><span data-ttu-id="78511-150">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="78511-151">Specifikt ID, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="78511-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-152">Plockningsprocess</span><span class="sxs-lookup"><span data-stu-id="78511-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-153">Följesedel</span><span class="sxs-lookup"><span data-stu-id="78511-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-154">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="78511-155">Följesedel</span><span class="sxs-lookup"><span data-stu-id="78511-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-156">Före</span><span class="sxs-lookup"><span data-stu-id="78511-156">Before</span></span></td>
<td><span data-ttu-id="78511-157">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-158">Följesedel</span><span class="sxs-lookup"><span data-stu-id="78511-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-159">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="78511-160">Inköp</span><span class="sxs-lookup"><span data-stu-id="78511-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="78511-161">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="78511-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="78511-162">Före</span><span class="sxs-lookup"><span data-stu-id="78511-162">Before</span></span></td>
<td><span data-ttu-id="78511-163">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-164">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="78511-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-165">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="78511-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-166">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="78511-167">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-167">After</span></span></td>
<td><span data-ttu-id="78511-168">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-169">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="78511-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-170">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="78511-171">Registrering</span><span class="sxs-lookup"><span data-stu-id="78511-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-172">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="78511-172">Not applicable</span></span></td>
<td><span data-ttu-id="78511-173">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-174">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="78511-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-175">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="78511-176">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="78511-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-177">Före</span><span class="sxs-lookup"><span data-stu-id="78511-177">Before</span></span></td>
<td><span data-ttu-id="78511-178">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-179">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="78511-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-180">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="78511-181">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-181">After</span></span></td>
<td><span data-ttu-id="78511-182">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-183">Faktura</span><span class="sxs-lookup"><span data-stu-id="78511-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="78511-184">Produktion</span><span class="sxs-lookup"><span data-stu-id="78511-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-185">Registrering</span><span class="sxs-lookup"><span data-stu-id="78511-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-186">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="78511-186">Not applicable</span></span></td>
<td><span data-ttu-id="78511-187">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="78511-188">Alla</span><span class="sxs-lookup"><span data-stu-id="78511-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-189">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-190">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="78511-191">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-192">Före</span><span class="sxs-lookup"><span data-stu-id="78511-192">Before</span></span></td>
<td><span data-ttu-id="78511-193">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-194">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-195">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="78511-196">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-196">After</span></span></td>
<td><span data-ttu-id="78511-197">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-198">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="78511-199">Karantän</span><span class="sxs-lookup"><span data-stu-id="78511-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-200">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="78511-201">Före</span><span class="sxs-lookup"><span data-stu-id="78511-201">Before</span></span></td>
<td><span data-ttu-id="78511-202">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-203">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-204">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-204">After</span></span></td>
<td><span data-ttu-id="78511-205">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-206">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-206">End</span></span></td>
<td><span data-ttu-id="78511-207">Före</span><span class="sxs-lookup"><span data-stu-id="78511-207">Before</span></span></td>
<td><span data-ttu-id="78511-208">Slut</span><span class="sxs-lookup"><span data-stu-id="78511-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="78511-209">Flödesoperation</span><span class="sxs-lookup"><span data-stu-id="78511-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-210">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="78511-211">Före</span><span class="sxs-lookup"><span data-stu-id="78511-211">Before</span></span></td>
<td><span data-ttu-id="78511-212">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-213">Specifikt ID, Grupp eller Alla och Resursspecifik, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="78511-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-214">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-215">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-215">After</span></span></td>
<td><span data-ttu-id="78511-216">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="78511-217">Produktion av samprodukt</span><span class="sxs-lookup"><span data-stu-id="78511-217">Co-product production</span></span></td>
<td><span data-ttu-id="78511-218">Registrering</span><span class="sxs-lookup"><span data-stu-id="78511-218">Registration</span></span></td>
<td><span data-ttu-id="78511-219">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="78511-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-220">Ingen</span><span class="sxs-lookup"><span data-stu-id="78511-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="78511-221">Alla</span><span class="sxs-lookup"><span data-stu-id="78511-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="78511-222">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="78511-222">Report as finished</span></span></td>
<td><span data-ttu-id="78511-223">Före</span><span class="sxs-lookup"><span data-stu-id="78511-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-224">Efter</span><span class="sxs-lookup"><span data-stu-id="78511-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="78511-225">Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.</span><span class="sxs-lookup"><span data-stu-id="78511-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="78511-226">Typ av process</span><span class="sxs-lookup"><span data-stu-id="78511-226">Type of process</span></span></th>
<th><span data-ttu-id="78511-227">När kvalitetsorder kan genereras automatiskt</span><span class="sxs-lookup"><span data-stu-id="78511-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="78511-228">När kvalitetsorder kan genereras om det krävs destruktivt test</span><span class="sxs-lookup"><span data-stu-id="78511-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="78511-229">Villkorsinformation</span><span class="sxs-lookup"><span data-stu-id="78511-229">Condition information</span></span></th>
<th><span data-ttu-id="78511-230">Information om manuell generering</span><span class="sxs-lookup"><span data-stu-id="78511-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="78511-231">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="78511-231">Purchase order</span></span></td>
<td><span data-ttu-id="78511-232">Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</span><span class="sxs-lookup"><span data-stu-id="78511-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="78511-233">Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</span><span class="sxs-lookup"><span data-stu-id="78511-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="78511-234">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="78511-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="78511-235">En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="78511-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-236">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="78511-236">Quarantine order</span></span></td>
<td><span data-ttu-id="78511-237">Före eller efter att karantänordern rapporteras som färdig eller avslutad</span><span class="sxs-lookup"><span data-stu-id="78511-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="78511-238">Kvalitetsorder som kräver destruktiva test kan inte genereras.</span><span class="sxs-lookup"><span data-stu-id="78511-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="78511-239">Det antas att karantänorderfunktionen hanterar dispositionen av materialet som förstörs.</span><span class="sxs-lookup"><span data-stu-id="78511-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="78511-240">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="78511-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="78511-241">En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="78511-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-242">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="78511-242">Sales order</span></span></td>
<td><span data-ttu-id="78511-243">Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</span><span class="sxs-lookup"><span data-stu-id="78511-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="78511-244">I ett obestämt steg</span><span class="sxs-lookup"><span data-stu-id="78511-244">At any step</span></span></td>
<td><span data-ttu-id="78511-245">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en kund, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="78511-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="78511-246">En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="78511-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-247">Produktionsorder</span><span class="sxs-lookup"><span data-stu-id="78511-247">Production order</span></span></td>
<td><span data-ttu-id="78511-248">Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="78511-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="78511-249">Efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="78511-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="78511-250">Behovet av en kvalitetsorder kan återspegla en särskild plats eller artikel, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="78511-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="78511-251">En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="78511-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-252">Produktionsorder som har en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="78511-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="78511-253">Före eller efter att rapporten är färdig för en åtgärd</span><span class="sxs-lookup"><span data-stu-id="78511-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="78511-254">Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</span><span class="sxs-lookup"><span data-stu-id="78511-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="78511-255">Behovet av en kvalitetsorder kan återspegla en särskild plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="78511-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="78511-256">En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="78511-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="78511-257">Lager</span><span class="sxs-lookup"><span data-stu-id="78511-257">Inventory</span></span></td>
<td><span data-ttu-id="78511-258">En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="78511-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="78511-259">En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet.</span><span class="sxs-lookup"><span data-stu-id="78511-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="78511-260">Fysisk lagerbehållning krävs.</span><span class="sxs-lookup"><span data-stu-id="78511-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="78511-261">Exempel på automatiska genereringar av kvalitetsorder</span><span class="sxs-lookup"><span data-stu-id="78511-261">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="78511-262">Inköp</span><span class="sxs-lookup"><span data-stu-id="78511-262">Purchasing</span></span>

<span data-ttu-id="78511-263">I inköp, om du ställer in fältet **händelsetyp** till **produktinleverans** och fältet **körning** till **efter** på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="78511-263">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="78511-264">Om alternativet **per uppdaterad kvantitet** är inställt på **Ja**, genereras en kvalitetsorder för varje inleverans mot inköpsordern, baserat på inlevererad kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="78511-264">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="78511-265">Varje gång en kvantitet inlevereras mot inköpsordern genereras nya kvalitetsorder utifrån den nylevererade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78511-265">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="78511-266">Om alternativet **per uppdaterad kvantitet** är inställt på **Nej**, genereras en kvalitetsorder för första inleveransen mot inköpsordern, baserat på inlevererad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="78511-266">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="78511-267">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="78511-267">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="78511-268">Kvalitetsorder genereras inte för efterföljande inleveranser mot inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="78511-268">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="78511-269">Kvantitetsspecifikation</span><span class="sxs-lookup"><span data-stu-id="78511-269">Quality specification</span></span></th>
<th><span data-ttu-id="78511-270">Per uppdaterad kvantitet</span><span class="sxs-lookup"><span data-stu-id="78511-270">Per updated quantity</span></span></th>
<th><span data-ttu-id="78511-271">Per spårningsdimension</span><span class="sxs-lookup"><span data-stu-id="78511-271">Per tracking dimension</span></span></th>
<th><span data-ttu-id="78511-272">Resultat</span><span class="sxs-lookup"><span data-stu-id="78511-272">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="78511-273">Procent: 10 %</span><span class="sxs-lookup"><span data-stu-id="78511-273">Percentage: 10%</span></span></td>
<td><span data-ttu-id="78511-274">Ja</span><span class="sxs-lookup"><span data-stu-id="78511-274">Yes</span></span></td>
<td>
<p><span data-ttu-id="78511-275">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-275">Batch number: No</span></span></p>
<p><span data-ttu-id="78511-276">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-276">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-277">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="78511-277">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="78511-278">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="78511-278">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="78511-279">Kvalitetsorder #1 för 3 (10 % av 30)</span><span class="sxs-lookup"><span data-stu-id="78511-279">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-280">Rapportera som slutförd för 70</span><span class="sxs-lookup"><span data-stu-id="78511-280">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="78511-281">Kvalitetsorder #2 för 7 (10 % av det resterande orderkvantiteten, vilket är lika med 70 i det här fallet)</span><span class="sxs-lookup"><span data-stu-id="78511-281">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-282">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="78511-282">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="78511-283">Nej</span><span class="sxs-lookup"><span data-stu-id="78511-283">No</span></span></td>
<td>
<p><span data-ttu-id="78511-284">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-284">Batch number: No</span></span></p>
<p><span data-ttu-id="78511-285">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-285">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="78511-286">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="78511-286">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="78511-287">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="78511-287">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="78511-288">Kvalitetsorder #1 skapas för 1 (för den första kvantiteten som rapporteras som färdig, som har ett fast värde på 1).</span><span class="sxs-lookup"><span data-stu-id="78511-288">Quality order #1 is created for 1 (for the first reported-as-finished quantity, which has a fixed value of 1).</span></span></li>
<li><span data-ttu-id="78511-289">Inga fler kvalitetsorder skapas med den resterande kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78511-289">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-290">Rapportera som slutförd för 10</span><span class="sxs-lookup"><span data-stu-id="78511-290">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="78511-291">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-291">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-292">Rapportera som slutförd för 60</span><span class="sxs-lookup"><span data-stu-id="78511-292">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="78511-293">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-293">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-294">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="78511-294">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="78511-295">Ja</span><span class="sxs-lookup"><span data-stu-id="78511-295">Yes</span></span></td>
<td>
<p><span data-ttu-id="78511-296">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-296">Batch number: Yes</span></span></p>
<p><span data-ttu-id="78511-297">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-297">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-298">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="78511-298">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="78511-299">Rapportera som slutförd för 3</span><span class="sxs-lookup"><span data-stu-id="78511-299">Report as finished for 3</span></span>
<ul>
<li><span data-ttu-id="78511-300">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1</span><span class="sxs-lookup"><span data-stu-id="78511-300">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="78511-301">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2</span><span class="sxs-lookup"><span data-stu-id="78511-301">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="78511-302">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3</span><span class="sxs-lookup"><span data-stu-id="78511-302">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-303">Rapportera som slutförd för 2</span><span class="sxs-lookup"><span data-stu-id="78511-303">Report as finished for 2</span></span>
<ul>
<li><span data-ttu-id="78511-304">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4</span><span class="sxs-lookup"><span data-stu-id="78511-304">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="78511-305">Kvalitetsorder #5 för 1 av batch #b5, seriell #s5</span><span class="sxs-lookup"><span data-stu-id="78511-305">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="78511-306"><strong>Obs!</strong> batchen kan återanvändas.</span><span class="sxs-lookup"><span data-stu-id="78511-306"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-307">Fast kvantitet: 2</span><span class="sxs-lookup"><span data-stu-id="78511-307">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="78511-308">Nej</span><span class="sxs-lookup"><span data-stu-id="78511-308">No</span></span></td>
<td>
<p><span data-ttu-id="78511-309">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-309">Batch number: Yes</span></span></p>
<p><span data-ttu-id="78511-310">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-310">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-311">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="78511-311">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="78511-312">Rapportera som slutförd för 4</span><span class="sxs-lookup"><span data-stu-id="78511-312">Report as finished for 4</span></span>
<ul>
<li><span data-ttu-id="78511-313">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1.</span><span class="sxs-lookup"><span data-stu-id="78511-313">Quality order #1 for 1 of batch #b1, serial #s1.</span></span></li>
<li><span data-ttu-id="78511-314">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2.</span><span class="sxs-lookup"><span data-stu-id="78511-314">Quality order #2 for 1 of batch #b2, serial #s2.</span></span></li>
<li><span data-ttu-id="78511-315">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3.</span><span class="sxs-lookup"><span data-stu-id="78511-315">Quality order #3 for 1 of batch #b3, serial #s3.</span></span></li>
<li><span data-ttu-id="78511-316">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4.</span><span class="sxs-lookup"><span data-stu-id="78511-316">Quality order #4 for 1 of batch #b4, serial #s4.</span></span></li>
<li><span data-ttu-id="78511-317">Inga fler kvalitetsorder skapas med den resterande kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78511-317">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-318">Rapport som slutförd för 6</span><span class="sxs-lookup"><span data-stu-id="78511-318">Report as finished for 6</span></span>
<ul>
<li><span data-ttu-id="78511-319">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-319">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a><span data-ttu-id="78511-320">Produktion</span><span class="sxs-lookup"><span data-stu-id="78511-320">Production</span></span>

<span data-ttu-id="78511-321">I produktion, om du ställer in fältet **händelsetyp** till **Rapportera som slutförd** och fältet **körning** till **efter** på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="78511-321">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="78511-322">Om alternativet **per uppdaterad kvantitet** är inställt på **Ja**, genereras en kvalitetsorder för varje slutförd kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="78511-322">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="78511-323">Varje gång en kvantitet rapporteras som slutförd mot produktionsorden genereras nya kvalitetsorder utifrån den nyligen avslutade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78511-323">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="78511-324">Denna generations logik är förenlig med inköp.</span><span class="sxs-lookup"><span data-stu-id="78511-324">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="78511-325">Om alternativet **Per uppdaterad kvantitet** anges till **Nej**, genereras en kvalitetsorder första gången som en kvantitet rapporteras som färdig, baserat på den färdiga kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78511-325">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="78511-326">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna av artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="78511-326">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="78511-327">Kvalitetsorder genereras inte för senare färdiga kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="78511-327">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="78511-328">Kvantitetsspecifikation</span><span class="sxs-lookup"><span data-stu-id="78511-328">Quality specification</span></span></th>
<th><span data-ttu-id="78511-329">Per uppdaterad kvantitet</span><span class="sxs-lookup"><span data-stu-id="78511-329">Per updated quantity</span></span></th>
<th><span data-ttu-id="78511-330">Per spårningsdimension</span><span class="sxs-lookup"><span data-stu-id="78511-330">Per tracking dimension</span></span></th>
<th><span data-ttu-id="78511-331">Resultat</span><span class="sxs-lookup"><span data-stu-id="78511-331">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="78511-332">Procent: 10 %</span><span class="sxs-lookup"><span data-stu-id="78511-332">Percentage: 10%</span></span></td>
<td><span data-ttu-id="78511-333">Ja</span><span class="sxs-lookup"><span data-stu-id="78511-333">Yes</span></span></td>
<td>
<p><span data-ttu-id="78511-334">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-334">Batch number: No</span></span></p>
<p><span data-ttu-id="78511-335">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-335">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-336">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="78511-336">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="78511-337">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="78511-337">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="78511-338">Kvalitetsorder #1 för 3 (10 % av 30)</span><span class="sxs-lookup"><span data-stu-id="78511-338">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-339">Rapportera som slutförd för 70</span><span class="sxs-lookup"><span data-stu-id="78511-339">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="78511-340">Kvalitetsorder #2 för 7 (10 % av det resterande orderkvantiteten, vilket är lika med 70 i det här fallet)</span><span class="sxs-lookup"><span data-stu-id="78511-340">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-341">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="78511-341">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="78511-342">Nej</span><span class="sxs-lookup"><span data-stu-id="78511-342">No</span></span></td>
<td>
<p><span data-ttu-id="78511-343">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-343">Batch number: No</span></span></p>
<p><span data-ttu-id="78511-344">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="78511-344">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="78511-345">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="78511-345">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="78511-346">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="78511-346">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="78511-347">Kvalitetsorder #1 för 1 (för den första kvantiteten som rapporteras som färdig, som har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="78511-347">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="78511-348">Kvalitetsorder #2 för 1 (för den återstående kvantiteten som fortfarande har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="78511-348">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-349">Rapportera som slutförd för 10</span><span class="sxs-lookup"><span data-stu-id="78511-349">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="78511-350">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-350">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-351">Rapportera som slutförd för 60</span><span class="sxs-lookup"><span data-stu-id="78511-351">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="78511-352">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-352">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-353">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="78511-353">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="78511-354">Ja</span><span class="sxs-lookup"><span data-stu-id="78511-354">Yes</span></span></td>
<td>
<p><span data-ttu-id="78511-355">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-355">Batch number: Yes</span></span></p>
<p><span data-ttu-id="78511-356">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-356">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-357">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="78511-357">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="78511-358">Rapportera som färdig till 3:1 #b1, #s1; 1 för #b2, #s2; och 1 för #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="78511-358">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="78511-359">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1</span><span class="sxs-lookup"><span data-stu-id="78511-359">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="78511-360">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2</span><span class="sxs-lookup"><span data-stu-id="78511-360">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="78511-361">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3</span><span class="sxs-lookup"><span data-stu-id="78511-361">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-362">Rapportera som färdig för 2:1 #b4, #s4; och 1 för #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="78511-362">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="78511-363">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4</span><span class="sxs-lookup"><span data-stu-id="78511-363">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="78511-364">Kvalitetsorder #5 för 1 av batch #b5, seriell #s5</span><span class="sxs-lookup"><span data-stu-id="78511-364">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="78511-365"><strong>Obs!</strong> batchen kan återanvändas.</span><span class="sxs-lookup"><span data-stu-id="78511-365"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="78511-366">Fast kvantitet: 2</span><span class="sxs-lookup"><span data-stu-id="78511-366">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="78511-367">Nej</span><span class="sxs-lookup"><span data-stu-id="78511-367">No</span></span></td>
<td>
<p><span data-ttu-id="78511-368">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-368">Batch number: Yes</span></span></p>
<p><span data-ttu-id="78511-369">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="78511-369">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="78511-370">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="78511-370">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="78511-371">Rapportera som färdig till 4: 1 för #b1, #s1; 1 för #b2, #s2; 1 för #b3, #s3; och 1 för #b4, #s4</span><span class="sxs-lookup"><span data-stu-id="78511-371">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="78511-372">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1</span><span class="sxs-lookup"><span data-stu-id="78511-372">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="78511-373">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2</span><span class="sxs-lookup"><span data-stu-id="78511-373">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="78511-374">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3</span><span class="sxs-lookup"><span data-stu-id="78511-374">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="78511-375">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4</span><span class="sxs-lookup"><span data-stu-id="78511-375">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="78511-376">Kvalitetsorder #5 för 2, utan referens till ett batch- och ett serienummer</span><span class="sxs-lookup"><span data-stu-id="78511-376">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="78511-377">Rapportera som färdig till 6: 1 för #b5, #s5; 1 för #b6, #s6; 1 för #b7, #s7; 1 för #b8, #s8; 1 för #b9, #s9; och 1 för #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="78511-377">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="78511-378">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="78511-378">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="78511-379">Kvalitetshanteringssidor</span><span class="sxs-lookup"><span data-stu-id="78511-379">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78511-380">Sida</span><span class="sxs-lookup"><span data-stu-id="78511-380">Page</span></span></th>
<th><span data-ttu-id="78511-381">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="78511-381">Description</span></span></th>
<th><span data-ttu-id="78511-382">Exempel</span><span class="sxs-lookup"><span data-stu-id="78511-382">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="78511-383">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="78511-383">Quality associations</span></span></td>
<td><span data-ttu-id="78511-384">Se föregående avsnitt i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="78511-384">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="78511-385">En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:</span><span class="sxs-lookup"><span data-stu-id="78511-385">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="78511-386">Transaktionshändelsen</span><span class="sxs-lookup"><span data-stu-id="78511-386">The transaction event</span></span></li>
<li><span data-ttu-id="78511-387">Uppsättningen med tester som måste utföras på artiklarna</span><span class="sxs-lookup"><span data-stu-id="78511-387">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="78511-388">Den godtagbara kvalitetsnivån</span><span class="sxs-lookup"><span data-stu-id="78511-388">The AQL</span></span></li>
<li><span data-ttu-id="78511-389">Samplingsplanen</span><span class="sxs-lookup"><span data-stu-id="78511-389">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="78511-390">Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-390">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="78511-391">En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-391">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="78511-392">Tester</span><span class="sxs-lookup"><span data-stu-id="78511-392">Tests</span></span></td>
<td><span data-ttu-id="78511-393">Använd den här sidan när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna.</span><span class="sxs-lookup"><span data-stu-id="78511-393">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="78511-394">Du kan tilldela en eller flera enskilda tester till en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="78511-394">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="78511-395">I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden.</span><span class="sxs-lookup"><span data-stu-id="78511-395">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="78511-396">Måttvärden används för kvantitativa tester, och testvariabler används för kvalitativa tester.</span><span class="sxs-lookup"><span data-stu-id="78511-396">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="78511-397">Ett kvantitativt test har testtypen <strong>Heltal</strong> eller <strong>Del</strong> och har också en bestämd måttenhet.</span><span class="sxs-lookup"><span data-stu-id="78511-397">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="78511-398">Kvalitetsspecifikationer och testresultat uttrycks som nummer.</span><span class="sxs-lookup"><span data-stu-id="78511-398">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="78511-399">Ett kvalitativt test har testtypen <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-399">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="78511-400">Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ.</span><span class="sxs-lookup"><span data-stu-id="78511-400">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="78511-401">Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.</span><span class="sxs-lookup"><span data-stu-id="78511-401">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="78511-402">Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test om förpackningsskador.</span><span class="sxs-lookup"><span data-stu-id="78511-402">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="78511-403">Företaget definierar mer information om det kvalitativa testet för att identifiera testvariabeln (skadad förpackning) och dess utfall.</span><span class="sxs-lookup"><span data-stu-id="78511-403">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="78511-404">Företaget använder sidan <strong>Testgrupper</strong> för att tilldela de två testerna till en testgrupp och ange testspecifik information.</span><span class="sxs-lookup"><span data-stu-id="78511-404">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="78511-405">Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.</span><span class="sxs-lookup"><span data-stu-id="78511-405">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="78511-406">Testgrupper</span><span class="sxs-lookup"><span data-stu-id="78511-406">Test groups</span></span></td>
<td><span data-ttu-id="78511-407">Använd den här sidan när du vill ställa in, redigera och visa testgrupper och enskilda tester som har tilldelats en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="78511-407">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="78511-408">I det övre fönstret visas testgrupper, och i det nedre visas testerna som har tilldelats en vald testgrupp.</span><span class="sxs-lookup"><span data-stu-id="78511-408">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="78511-409">Du kan tilldela flera principer till en testgrupp, t.ex. en samplingsplan, en godtagbar kvalitetsnivå och behovet av destruktiv testning.</span><span class="sxs-lookup"><span data-stu-id="78511-409">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="78511-410">När du tilldelar ett enskilt test till en testgrupp definierar du ytterligare information, till exempel sekvensen, dokument och giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="78511-410">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="78511-411">För ett kvantitativt test innehåller informationen som du anger även acceptabla mätvärden.</span><span class="sxs-lookup"><span data-stu-id="78511-411">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="78511-412">För ett kvalitativt test innehåller informationen testvariabeln och standardresultatet.</span><span class="sxs-lookup"><span data-stu-id="78511-412">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="78511-413">Den testgrupp som har tilldelats till en kvalitetsorder definierar standarduppsättningen med test som måste utföras på den angivna artikeln.</span><span class="sxs-lookup"><span data-stu-id="78511-413">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="78511-414">Du kan dock lägga till, ta bort eller ändra tester för en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-414">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="78511-415">Testresultaten rapporteras för varje test på en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-415">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="78511-416">Ett tillverkningsföretag definierar en testgrupp för varje variant av sina kvalitetsriktlinjer.</span><span class="sxs-lookup"><span data-stu-id="78511-416">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="78511-417">De olika testgrupperna återspeglar skillnaderna i samplingsplanerna, uppsättningarna med tester som måste utföras tillsammans, den godtagbara kvalitetsnivån och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="78511-417">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="78511-418">För kvantitativa tester finns det också skillnader i de godtagbara måttvärdena.</span><span class="sxs-lookup"><span data-stu-id="78511-418">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="78511-419">Om du vill framtvinga kvalitetsriktlinjerna tilldelar företaget en testgrupp till varje regel för automatisk generering av kvalitetsorder på sidan <strong>Kvalitetsassociationer</strong> och tilldelar även en testgrupp till kvalitetsorder som har skapats manuellt.</span><span class="sxs-lookup"><span data-stu-id="78511-419">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="78511-420">Kvalitetsgrupper för artiklar</span><span class="sxs-lookup"><span data-stu-id="78511-420">Item quality groups</span></span></td>
<td><span data-ttu-id="78511-421">Använd den här sidan när du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel.</span><span class="sxs-lookup"><span data-stu-id="78511-421">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="78511-422">En kvalitetsgrupp representerar gemensamma testbehov för artiklar.</span><span class="sxs-lookup"><span data-stu-id="78511-422">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="78511-423">När du har definierat testkraven på sidan <strong>Testgrupper</strong> kan du definiera reglerna för automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="78511-423">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="78511-424">För att förenkla processen definierar du inte regler för enskilda artiklar.</span><span class="sxs-lookup"><span data-stu-id="78511-424">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="78511-425">I stället definierar du regler för en kvalitetsgrupp genom att använda sidan <strong>Kvalitetsassociationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-425">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="78511-426">Du kan också använda <strong>Kvalitetsgrupper för artiklar</strong> för en vald kvalitetsgrupp för att tilldela relevanta artiklar till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="78511-426">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="78511-427">Du kan också använda sidan <strong>Kvalitetsgrupper för artiklar</strong> för en vald artikel för att tilldela relevanta kvalitetsgrupper till den artikeln.</span><span class="sxs-lookup"><span data-stu-id="78511-427">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="78511-428">Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion.</span><span class="sxs-lookup"><span data-stu-id="78511-428">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="78511-429">Företaget definierar en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="78511-429">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="78511-430">Senare köper företaget en ny typ av råmaterial som har samma testbehov.</span><span class="sxs-lookup"><span data-stu-id="78511-430">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="78511-431">I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="78511-431">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="78511-432">Samma tillverkningsföretag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans.</span><span class="sxs-lookup"><span data-stu-id="78511-432">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="78511-433">Företaget definierar två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till varje grupp.</span><span class="sxs-lookup"><span data-stu-id="78511-433">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="78511-434">Testvariabler</span><span class="sxs-lookup"><span data-stu-id="78511-434">Test variables</span></span></td>
<td><span data-ttu-id="78511-435">Använd den här sidan för att definiera och visa variablerna som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="78511-435">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="78511-436">För varje variabel definierar du fasta resultat som representerar de möjliga alternativen.</span><span class="sxs-lookup"><span data-stu-id="78511-436">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="78511-437">Du definierar testerna på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-437">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="78511-438">För kvalitativa tester måste du ange testtypen till <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-438">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="78511-439">Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel till ett enskilt test.</span><span class="sxs-lookup"><span data-stu-id="78511-439">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="78511-440">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="78511-440">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="78511-441">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="78511-441">This inspection test has several variables.</span></span> <span data-ttu-id="78511-442">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="78511-442">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="78511-443">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="78511-443">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="78511-444">Resultat från testvariabel</span><span class="sxs-lookup"><span data-stu-id="78511-444">Test variable outcomes</span></span></td>
<td><span data-ttu-id="78511-445">Använd den här sidan när du vill ställa in, redigera och visa möjliga testresultat för en testvariabel som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="78511-445">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="78511-446">För varje resultat tilldelar du statusen <strong>godkänt</strong> eller <strong>underkänt</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-446">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="78511-447">Du måste definiera en variabel och dess resultat för varje kvalitativt test som definieras på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="78511-447">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="78511-448">(För kvalitativa tester anges testtypen som <strong>Alternativ</strong> på sidan <strong>Tester</strong>.) Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel och standardresultatet till ett enskilt kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="78511-448">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="78511-449">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="78511-449">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="78511-450">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="78511-450">This inspection test has of several variables.</span></span> <span data-ttu-id="78511-451">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="78511-451">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="78511-452">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="78511-452">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="78511-453">Statusen <strong>godkänt</strong> eller <strong>underkänt</strong> tilldelas till varje resultat.</span><span class="sxs-lookup"><span data-stu-id="78511-453">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="78511-454">Under inspektionstestet av respektive variabel rapporterar inspektören testresultatet genom att välja något av resultaten.</span><span class="sxs-lookup"><span data-stu-id="78511-454">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="78511-455">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="78511-455">Additional resources</span></span>
--------

[<span data-ttu-id="78511-456">Kvalitetshanteringsprocesser</span><span class="sxs-lookup"><span data-stu-id="78511-456">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="78511-457">Aktivera avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="78511-457">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)
