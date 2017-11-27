---
title: "Översikt över kvalitetshantering"
description: "Det här ämnet beskriver hur du kan använda kvalitetshantering i Microsoft Dynamics 365 for Finance and Operations för att förbättra produktens kvalitet inom din leveranskedja."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8961d1c62167192fcf32d17c2941b8813ea0629
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="quality-management-overview"></a><span data-ttu-id="465d0-103">Översikt över kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="465d0-103">Quality management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="465d0-104">Det här ämnet beskriver hur du kan använda kvalitetshantering i Microsoft Dynamics 365 for Finance and Operations för att förbättra produktens kvalitet inom din leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="465d0-104">This topic describes how you can use quality management in Microsoft Dynamics 365 for Finance and Operations to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="465d0-105">Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett ursprungspunkten.</span><span class="sxs-lookup"><span data-stu-id="465d0-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="465d0-106">Eftersom diagnostiktyper länkas till korrigeringsrapporteringen kan Microsoft Dynamics 365 for Finance and Operations planera uppgifter för att korrigera problem och hindra dem från att återkomma.</span><span class="sxs-lookup"><span data-stu-id="465d0-106">Because diagnostic types are linked to correction reporting, Microsoft Dynamics 365 for Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="465d0-107">Förutom funktioner för att hantera avvikelser inkluderar kvalitetshantering funktioner för att spåra problem efter problemtyp (även interna problem), och för att identifiera lösningar som kortsiktiga och långsiktiga.</span><span class="sxs-lookup"><span data-stu-id="465d0-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="465d0-108">Statistik om KPI:er (Key Performance Indicator) ger insyn i historiken över tidigare avvikelseproblem och lösningarna som användes för att korrigera dem.</span><span class="sxs-lookup"><span data-stu-id="465d0-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="465d0-109">Du kan använda historiska data om du vill granska effektiviteten hos tidigare kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.</span><span class="sxs-lookup"><span data-stu-id="465d0-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="465d0-110">När du ställer in en kvalitetsassociation kan Finance and Operations skapa kvalitetsorder för olika affärsprocesser, händelser och villkor.</span><span class="sxs-lookup"><span data-stu-id="465d0-110">When you set up a quality association, Finance and Operations can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="465d0-111">Kvalitetsassociationen kan omfatta en viss artikel, en specifik grupp artiklar eller alla artiklar.</span><span class="sxs-lookup"><span data-stu-id="465d0-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="465d0-112">Exempel på användningen av kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="465d0-112">Examples of the use of quality management</span></span>
<span data-ttu-id="465d0-113">Kvalitetshanteringen är flexibel och kan implementeras på olika sätt för att uppfylla kraven för specifika nivåer i distributionskedjeåtgärder.</span><span class="sxs-lookup"><span data-stu-id="465d0-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="465d0-114">Följande exempel illustrerar hur dessa funktioner kan användas:</span><span class="sxs-lookup"><span data-stu-id="465d0-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="465d0-115">Starta automatiskt en kvalitetskontrollprocess baserat på fördefinierade villkor (vid lagerställeregistrering av en inköpsorder från en viss leverantör.)</span><span class="sxs-lookup"><span data-stu-id="465d0-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="465d0-116">Blockera lagret under inspektion för att förhindra icke-godkänt lager från att användas (fullständig blockering av inköpsorderkvantiteter).</span><span class="sxs-lookup"><span data-stu-id="465d0-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="465d0-117">Använd artikelsamplingen som en del av en kvalitetsassociation för att definiera hur aktuellt fysiskt lager ska inspekteras.</span><span class="sxs-lookup"><span data-stu-id="465d0-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="465d0-118">Samplingen kan baseras på fasta kvantiteter eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="465d0-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="465d0-119">Skapa en kvalitetsorder för delleveranser.</span><span class="sxs-lookup"><span data-stu-id="465d0-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="465d0-120">Om du vill skapa en kvalitetsorder som baseras på den kvantitet som inlevererats fysiskt till en order måste du markera kryssrutan **Per uppdaterad kvantitet** i formuläret **artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="465d0-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="465d0-121">Skapa testtyper som innehåller minimum-, maximum- och måltestvärden och utför testning av typen ”kvalitativ kontra kvantitativ” som har fördefinierade valideringresultat.</span><span class="sxs-lookup"><span data-stu-id="465d0-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="465d0-122">Ange en godtagbar kvalitetsnivå (AQL) för att kontrollera toleranserna för kvalitetsmått.</span><span class="sxs-lookup"><span data-stu-id="465d0-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="465d0-123">Ange resurser som en inspektionsåtgärd kräver, till exempel ett testområde och testinstrument.</span><span class="sxs-lookup"><span data-stu-id="465d0-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="465d0-124">Arbeta med kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="465d0-124">Working with quality associations</span></span>
<span data-ttu-id="465d0-125">Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="465d0-126">Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="465d0-127">Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="465d0-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="465d0-128">Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras.</span><span class="sxs-lookup"><span data-stu-id="465d0-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="465d0-129">Beroende på inställningen för körningsplanen kan själva utlösarprocessen spärras medan det finns en öppen kvalitetsorder, eller så kan de efterföljande processerna, till exempel fakturering av inköpsorder, spärras.</span><span class="sxs-lookup"><span data-stu-id="465d0-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="465d0-130">**Obs!** Medan det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utlevereras.</span><span class="sxs-lookup"><span data-stu-id="465d0-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="465d0-131">Beroende på inställningen **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden.</span><span class="sxs-lookup"><span data-stu-id="465d0-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="465d0-132">För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och villkoren som en kvalitetsorder genereras för.</span><span class="sxs-lookup"><span data-stu-id="465d0-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="465d0-133">Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="465d0-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="465d0-134">En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.</span><span class="sxs-lookup"><span data-stu-id="465d0-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="465d0-135">Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i varje affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="465d0-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="465d0-136">För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.</span><span class="sxs-lookup"><span data-stu-id="465d0-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="465d0-137">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="465d0-137">Reference type</span></span></th>
<th><span data-ttu-id="465d0-138">Händelsetyp</span><span class="sxs-lookup"><span data-stu-id="465d0-138">Event type</span></span></th>
<th><span data-ttu-id="465d0-139">Körning</span><span class="sxs-lookup"><span data-stu-id="465d0-139">Execution</span></span></th>
<th><span data-ttu-id="465d0-140">Händelsespärr</span><span class="sxs-lookup"><span data-stu-id="465d0-140">Event blocking</span></span></th>
<th><span data-ttu-id="465d0-141">Dokumentreferens</span><span class="sxs-lookup"><span data-stu-id="465d0-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="465d0-142">Lager</span><span class="sxs-lookup"><span data-stu-id="465d0-142">Inventory</span></span></td>
<td><span data-ttu-id="465d0-143">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="465d0-143">Not applicable</span></span></td>
<td><span data-ttu-id="465d0-144">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="465d0-144">Not applicable</span></span></td>
<td><span data-ttu-id="465d0-145">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-145">None</span></span></td>
<td><span data-ttu-id="465d0-146">Alla</span><span class="sxs-lookup"><span data-stu-id="465d0-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="465d0-147">Försäljning</span><span class="sxs-lookup"><span data-stu-id="465d0-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="465d0-148">Plockningsprocess har schemalagts</span><span class="sxs-lookup"><span data-stu-id="465d0-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="465d0-149">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-149">Before</span></span></td>
<td><span data-ttu-id="465d0-150">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="465d0-151">Specifikt ID, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="465d0-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-152">Plockningsprocess</span><span class="sxs-lookup"><span data-stu-id="465d0-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-153">Följesedel</span><span class="sxs-lookup"><span data-stu-id="465d0-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-154">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="465d0-155">Följesedel</span><span class="sxs-lookup"><span data-stu-id="465d0-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-156">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-156">Before</span></span></td>
<td><span data-ttu-id="465d0-157">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-158">Följesedel</span><span class="sxs-lookup"><span data-stu-id="465d0-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-159">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="465d0-160">Inköp</span><span class="sxs-lookup"><span data-stu-id="465d0-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="465d0-161">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="465d0-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="465d0-162">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-162">Before</span></span></td>
<td><span data-ttu-id="465d0-163">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-164">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="465d0-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-165">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="465d0-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-166">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="465d0-167">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-167">After</span></span></td>
<td><span data-ttu-id="465d0-168">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-169">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="465d0-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-170">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="465d0-171">Registrering</span><span class="sxs-lookup"><span data-stu-id="465d0-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-172">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="465d0-172">Not applicable</span></span></td>
<td><span data-ttu-id="465d0-173">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-174">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="465d0-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-175">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="465d0-176">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="465d0-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-177">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-177">Before</span></span></td>
<td><span data-ttu-id="465d0-178">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-179">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="465d0-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-180">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="465d0-181">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-181">After</span></span></td>
<td><span data-ttu-id="465d0-182">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-183">Faktura</span><span class="sxs-lookup"><span data-stu-id="465d0-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="465d0-184">Produktion</span><span class="sxs-lookup"><span data-stu-id="465d0-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-185">Registrering</span><span class="sxs-lookup"><span data-stu-id="465d0-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-186">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="465d0-186">Not applicable</span></span></td>
<td><span data-ttu-id="465d0-187">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="465d0-188">Alla</span><span class="sxs-lookup"><span data-stu-id="465d0-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-189">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-190">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="465d0-191">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-192">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-192">Before</span></span></td>
<td><span data-ttu-id="465d0-193">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-194">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-195">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="465d0-196">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-196">After</span></span></td>
<td><span data-ttu-id="465d0-197">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-198">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="465d0-199">Karantän</span><span class="sxs-lookup"><span data-stu-id="465d0-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-200">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="465d0-201">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-201">Before</span></span></td>
<td><span data-ttu-id="465d0-202">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-203">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-204">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-204">After</span></span></td>
<td><span data-ttu-id="465d0-205">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-206">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-206">End</span></span></td>
<td><span data-ttu-id="465d0-207">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-207">Before</span></span></td>
<td><span data-ttu-id="465d0-208">Slut</span><span class="sxs-lookup"><span data-stu-id="465d0-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="465d0-209">Flödesoperation</span><span class="sxs-lookup"><span data-stu-id="465d0-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-210">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="465d0-211">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-211">Before</span></span></td>
<td><span data-ttu-id="465d0-212">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-213">Specifikt ID, Grupp eller Alla och Resursspecifik, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="465d0-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-214">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-215">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-215">After</span></span></td>
<td><span data-ttu-id="465d0-216">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="465d0-217">Produktion av samprodukt</span><span class="sxs-lookup"><span data-stu-id="465d0-217">Co-product production</span></span></td>
<td><span data-ttu-id="465d0-218">Registrering</span><span class="sxs-lookup"><span data-stu-id="465d0-218">Registration</span></span></td>
<td><span data-ttu-id="465d0-219">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="465d0-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-220">Ingen</span><span class="sxs-lookup"><span data-stu-id="465d0-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="465d0-221">Alla</span><span class="sxs-lookup"><span data-stu-id="465d0-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="465d0-222">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="465d0-222">Report as finished</span></span></td>
<td><span data-ttu-id="465d0-223">Före</span><span class="sxs-lookup"><span data-stu-id="465d0-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-224">Efter</span><span class="sxs-lookup"><span data-stu-id="465d0-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="465d0-225">Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.</span><span class="sxs-lookup"><span data-stu-id="465d0-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="465d0-226">Typ av process</span><span class="sxs-lookup"><span data-stu-id="465d0-226">Type of process</span></span></th>
<th><span data-ttu-id="465d0-227">När kvalitetsorder kan genereras automatiskt</span><span class="sxs-lookup"><span data-stu-id="465d0-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="465d0-228">När kvalitetsorder kan genereras om det krävs destruktivt test</span><span class="sxs-lookup"><span data-stu-id="465d0-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="465d0-229">Villkorsinformation</span><span class="sxs-lookup"><span data-stu-id="465d0-229">Condition information</span></span></th>
<th><span data-ttu-id="465d0-230">Information om manuell generering</span><span class="sxs-lookup"><span data-stu-id="465d0-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="465d0-231">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="465d0-231">Purchase order</span></span></td>
<td><span data-ttu-id="465d0-232">Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</span><span class="sxs-lookup"><span data-stu-id="465d0-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="465d0-233">Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</span><span class="sxs-lookup"><span data-stu-id="465d0-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="465d0-234">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="465d0-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="465d0-235">En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="465d0-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-236">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="465d0-236">Quarantine order</span></span></td>
<td><span data-ttu-id="465d0-237">Före eller efter att karantänordern rapporteras som färdig eller avslutad</span><span class="sxs-lookup"><span data-stu-id="465d0-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="465d0-238">Kvalitetsorder som kräver destruktiva test kan inte genereras.</span><span class="sxs-lookup"><span data-stu-id="465d0-238">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="465d0-239">Det antas att karantänorderfunktionen hanterar dispositionen av materialet som förstörs.</span><span class="sxs-lookup"><span data-stu-id="465d0-239">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="465d0-240">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="465d0-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="465d0-241">En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="465d0-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-242">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="465d0-242">Sales order</span></span></td>
<td><span data-ttu-id="465d0-243">Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</span><span class="sxs-lookup"><span data-stu-id="465d0-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="465d0-244">I ett obestämt steg</span><span class="sxs-lookup"><span data-stu-id="465d0-244">At any step</span></span></td>
<td><span data-ttu-id="465d0-245">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en kund, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="465d0-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="465d0-246">En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="465d0-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-247">Produktionsorder</span><span class="sxs-lookup"><span data-stu-id="465d0-247">Production order</span></span></td>
<td><span data-ttu-id="465d0-248">Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="465d0-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="465d0-249">Efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="465d0-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="465d0-250">Behovet av en kvalitetsorder kan återspegla en särskild plats eller artikel, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="465d0-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="465d0-251">En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="465d0-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-252">Produktionsorder som har en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="465d0-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="465d0-253">Före eller efter att rapporten är färdig för en åtgärd</span><span class="sxs-lookup"><span data-stu-id="465d0-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="465d0-254">Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</span><span class="sxs-lookup"><span data-stu-id="465d0-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="465d0-255">Behovet av en kvalitetsorder kan återspegla en särskild plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="465d0-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="465d0-256">En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="465d0-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="465d0-257">Lager</span><span class="sxs-lookup"><span data-stu-id="465d0-257">Inventory</span></span></td>
<td><span data-ttu-id="465d0-258">En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="465d0-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="465d0-259">En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet.</span><span class="sxs-lookup"><span data-stu-id="465d0-259">A quality order must be created manually for an item's inventory quantity.</span></span> <span data-ttu-id="465d0-260">Fysisk lagerbehållning krävs.</span><span class="sxs-lookup"><span data-stu-id="465d0-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="465d0-261">Kvalitetshanteringssidor</span><span class="sxs-lookup"><span data-stu-id="465d0-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="465d0-262">Sida</span><span class="sxs-lookup"><span data-stu-id="465d0-262">Page</span></span></th>
<th><span data-ttu-id="465d0-263">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="465d0-263">Description</span></span></th>
<th><span data-ttu-id="465d0-264">Exempel</span><span class="sxs-lookup"><span data-stu-id="465d0-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="465d0-265">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="465d0-265">Quality associations</span></span></td>
<td><span data-ttu-id="465d0-266">Se föregående avsnitt i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="465d0-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="465d0-267">En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:</span><span class="sxs-lookup"><span data-stu-id="465d0-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="465d0-268">Transaktionshändelsen</span><span class="sxs-lookup"><span data-stu-id="465d0-268">The transaction event</span></span></li>
<li><span data-ttu-id="465d0-269">Uppsättningen med tester som måste utföras på artiklarna</span><span class="sxs-lookup"><span data-stu-id="465d0-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="465d0-270">Den godtagbara kvalitetsnivån</span><span class="sxs-lookup"><span data-stu-id="465d0-270">The AQL</span></span></li>
<li><span data-ttu-id="465d0-271">Samplingsplanen</span><span class="sxs-lookup"><span data-stu-id="465d0-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="465d0-272">Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="465d0-273">En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="465d0-274">Tester</span><span class="sxs-lookup"><span data-stu-id="465d0-274">Tests</span></span></td>
<td><span data-ttu-id="465d0-275">Använd den här sidan när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna.</span><span class="sxs-lookup"><span data-stu-id="465d0-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="465d0-276">Du kan tilldela en eller flera enskilda tester till en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="465d0-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="465d0-277">I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden.</span><span class="sxs-lookup"><span data-stu-id="465d0-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="465d0-278">Måttvärden används för kvantitativa tester, och testvariabler används för kvalitativa tester.</span><span class="sxs-lookup"><span data-stu-id="465d0-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="465d0-279">Ett kvantitativt test har testtypen <strong>Heltal</strong> eller <strong>Del</strong> och har också en bestämd måttenhet.</span><span class="sxs-lookup"><span data-stu-id="465d0-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="465d0-280">Kvalitetsspecifikationer och testresultat uttrycks som nummer.</span><span class="sxs-lookup"><span data-stu-id="465d0-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="465d0-281">Ett kvalitativt test har testtypen <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="465d0-282">Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ.</span><span class="sxs-lookup"><span data-stu-id="465d0-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="465d0-283">Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.</span><span class="sxs-lookup"><span data-stu-id="465d0-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="465d0-284">Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test om förpackningsskador.</span><span class="sxs-lookup"><span data-stu-id="465d0-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="465d0-285">Företaget definierar mer information om det kvalitativa testet för att identifiera testvariabeln (skadad förpackning) och dess utfall.</span><span class="sxs-lookup"><span data-stu-id="465d0-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="465d0-286">Företaget använder sidan <strong>Testgrupper</strong> för att tilldela de två testerna till en testgrupp och ange testspecifik information.</span><span class="sxs-lookup"><span data-stu-id="465d0-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="465d0-287">Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.</span><span class="sxs-lookup"><span data-stu-id="465d0-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="465d0-288">Testgrupper</span><span class="sxs-lookup"><span data-stu-id="465d0-288">Test groups</span></span></td>
<td><span data-ttu-id="465d0-289">Använd den här sidan när du vill ställa in, redigera och visa testgrupper och enskilda tester som har tilldelats en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="465d0-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="465d0-290">I det övre fönstret visas testgrupper, och i det nedre visas testerna som har tilldelats en vald testgrupp.</span><span class="sxs-lookup"><span data-stu-id="465d0-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="465d0-291">Du kan tilldela flera principer till en testgrupp, t.ex. en samplingsplan, en godtagbar kvalitetsnivå och behovet av destruktiv testning.</span><span class="sxs-lookup"><span data-stu-id="465d0-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="465d0-292">När du tilldelar ett enskilt test till en testgrupp definierar du ytterligare information, till exempel sekvensen, dokument och giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="465d0-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="465d0-293">För ett kvantitativt test innehåller informationen som du anger även acceptabla mätvärden.</span><span class="sxs-lookup"><span data-stu-id="465d0-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="465d0-294">För ett kvalitativt test innehåller informationen testvariabeln och standardresultatet.</span><span class="sxs-lookup"><span data-stu-id="465d0-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="465d0-295">Den testgrupp som har tilldelats till en kvalitetsorder definierar standarduppsättningen med test som måste utföras på den angivna artikeln.</span><span class="sxs-lookup"><span data-stu-id="465d0-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="465d0-296">Du kan dock lägga till, ta bort eller ändra tester för en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="465d0-297">Testresultaten rapporteras för varje test på en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="465d0-298">Ett tillverkningsföretag definierar en testgrupp för varje variant av sina kvalitetsriktlinjer.</span><span class="sxs-lookup"><span data-stu-id="465d0-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="465d0-299">De olika testgrupperna återspeglar skillnaderna i samplingsplanerna, uppsättningarna med tester som måste utföras tillsammans, den godtagbara kvalitetsnivån och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="465d0-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="465d0-300">För kvantitativa tester finns det också skillnader i de godtagbara måttvärdena.</span><span class="sxs-lookup"><span data-stu-id="465d0-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="465d0-301">Om du vill framtvinga kvalitetsriktlinjerna tilldelar företaget en testgrupp till varje regel för automatisk generering av kvalitetsorder på sidan <strong>Kvalitetsassociationer</strong> och tilldelar även en testgrupp till kvalitetsorder som har skapats manuellt.</span><span class="sxs-lookup"><span data-stu-id="465d0-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="465d0-302">Kvalitetsgrupper för artiklar</span><span class="sxs-lookup"><span data-stu-id="465d0-302">Item quality groups</span></span></td>
<td><span data-ttu-id="465d0-303">Använd den här sidan när du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel.</span><span class="sxs-lookup"><span data-stu-id="465d0-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="465d0-304">En kvalitetsgrupp representerar gemensamma testbehov för artiklar.</span><span class="sxs-lookup"><span data-stu-id="465d0-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="465d0-305">När du har definierat testkraven på sidan <strong>Testgrupper</strong> kan du definiera reglerna för automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="465d0-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="465d0-306">För att förenkla processen definierar du inte regler för enskilda artiklar.</span><span class="sxs-lookup"><span data-stu-id="465d0-306">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="465d0-307">I stället definierar du regler för en kvalitetsgrupp genom att använda sidan <strong>Kvalitetsassociationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="465d0-308">Du kan också använda <strong>Kvalitetsgrupper för artiklar</strong> för en vald kvalitetsgrupp för att tilldela relevanta artiklar till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="465d0-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="465d0-309">Du kan också använda sidan <strong>Kvalitetsgrupper för artiklar</strong> för en vald artikel för att tilldela relevanta kvalitetsgrupper till den artikeln.</span><span class="sxs-lookup"><span data-stu-id="465d0-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="465d0-310">Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion.</span><span class="sxs-lookup"><span data-stu-id="465d0-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="465d0-311">Företaget definierar en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="465d0-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="465d0-312">Senare köper företaget en ny typ av råmaterial som har samma testbehov.</span><span class="sxs-lookup"><span data-stu-id="465d0-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="465d0-313">I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="465d0-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="465d0-314">Samma tillverkningsföretag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans.</span><span class="sxs-lookup"><span data-stu-id="465d0-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="465d0-315">Företaget definierar två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till varje grupp.</span><span class="sxs-lookup"><span data-stu-id="465d0-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="465d0-316">Testvariabler</span><span class="sxs-lookup"><span data-stu-id="465d0-316">Test variables</span></span></td>
<td><span data-ttu-id="465d0-317">Använd den här sidan för att definiera och visa variablerna som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="465d0-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="465d0-318">För varje variabel definierar du fasta resultat som representerar de möjliga alternativen.</span><span class="sxs-lookup"><span data-stu-id="465d0-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="465d0-319">Du definierar testerna på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="465d0-320">För kvalitativa tester måste du ange testtypen till <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="465d0-321">Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel till ett enskilt test.</span><span class="sxs-lookup"><span data-stu-id="465d0-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="465d0-322">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="465d0-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="465d0-323">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="465d0-323">This inspection test has several variables.</span></span> <span data-ttu-id="465d0-324">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="465d0-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="465d0-325">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="465d0-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="465d0-326">Resultat från testvariabel</span><span class="sxs-lookup"><span data-stu-id="465d0-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="465d0-327">Använd den här sidan när du vill ställa in, redigera och visa möjliga testresultat för en testvariabel som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="465d0-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="465d0-328">För varje resultat tilldelar du statusen <strong>godkänt</strong> eller <strong>underkänt</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="465d0-329">Du måste definiera en variabel och dess resultat för varje kvalitativt test som definieras på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="465d0-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="465d0-330">(För kvalitativa tester anges testtypen som <strong>Alternativ</strong> på sidan <strong>Tester</strong>.) Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel och standardresultatet till ett enskilt kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="465d0-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="465d0-331">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="465d0-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="465d0-332">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="465d0-332">This inspection test has of several variables.</span></span> <span data-ttu-id="465d0-333">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="465d0-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="465d0-334">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="465d0-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="465d0-335">Statusen <strong>godkänt</strong> eller <strong>underkänt</strong> tilldelas till varje resultat.</span><span class="sxs-lookup"><span data-stu-id="465d0-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="465d0-336">Under inspektionstestet av respektive variabel rapporterar inspektören testresultatet genom att välja något av resultaten.</span><span class="sxs-lookup"><span data-stu-id="465d0-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="465d0-337">Se även</span><span class="sxs-lookup"><span data-stu-id="465d0-337">See also</span></span>
--------

[<span data-ttu-id="465d0-338">Kvalitetshanteringsprocesser</span><span class="sxs-lookup"><span data-stu-id="465d0-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="465d0-339">Aktivera avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="465d0-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)

