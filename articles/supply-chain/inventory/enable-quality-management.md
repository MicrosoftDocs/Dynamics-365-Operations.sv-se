---
title: Översikt över kvalitetshantering
description: Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d7828e6bb9a3684c1d76e2cfac96174a8dfbf4
ms.sourcegitcommit: 6d6aa016c4971b0673d461b82fd80b060ae5f7a1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3268826"
---
# <a name="quality-management-overview"></a><span data-ttu-id="f7839-103">Översikt över kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="f7839-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7839-104">Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="f7839-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="f7839-105">Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett ursprungspunkten.</span><span class="sxs-lookup"><span data-stu-id="f7839-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="f7839-106">Eftersom diagnostiktyper länkas till korrigeringsrapporteringen kan Supply Chain Management planera uppgifter för att korrigera problem och förhindra dem från att återkomma.</span><span class="sxs-lookup"><span data-stu-id="f7839-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="f7839-107">Förutom funktioner för att hantera avvikelser inkluderar kvalitetshantering funktioner för att spåra problem efter problemtyp (även interna problem), och för att identifiera lösningar som kortsiktiga och långsiktiga.</span><span class="sxs-lookup"><span data-stu-id="f7839-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="f7839-108">Statistik om KPI:er (Key Performance Indicator) ger insyn i historiken över tidigare avvikelseproblem och lösningarna som användes för att korrigera dem.</span><span class="sxs-lookup"><span data-stu-id="f7839-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="f7839-109">Du kan använda historiska data om du vill granska effektiviteten hos tidigare kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.</span><span class="sxs-lookup"><span data-stu-id="f7839-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="f7839-110">När du ställer in en kvalitetsassociation kan Supply Chain Management skapa kvalitetsorder för olika affärsprocesser, händelser och villkor.</span><span class="sxs-lookup"><span data-stu-id="f7839-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="f7839-111">Kvalitetsassociationen kan omfatta en viss artikel, en specifik grupp artiklar eller alla artiklar.</span><span class="sxs-lookup"><span data-stu-id="f7839-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="f7839-112">Exempel på användningen av kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="f7839-112">Examples of the use of quality management</span></span>
<span data-ttu-id="f7839-113">Kvalitetshanteringen är flexibel och kan implementeras på olika sätt för att uppfylla kraven för specifika nivåer i distributionskedjeåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f7839-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="f7839-114">Följande exempel illustrerar hur dessa funktioner kan användas:</span><span class="sxs-lookup"><span data-stu-id="f7839-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="f7839-115">Starta automatiskt en kvalitetskontrollprocess baserat på fördefinierade villkor (vid lagerställeregistrering av en inköpsorder från en viss leverantör.)</span><span class="sxs-lookup"><span data-stu-id="f7839-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="f7839-116">Blockera lagret under inspektion för att förhindra icke-godkänt lager från att användas (fullständig blockering av inköpsorderkvantiteter).</span><span class="sxs-lookup"><span data-stu-id="f7839-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="f7839-117">Använd artikelsamplingen som en del av en kvalitetsassociation för att definiera hur aktuellt fysiskt lager ska inspekteras.</span><span class="sxs-lookup"><span data-stu-id="f7839-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="f7839-118">Samplingen kan baseras på fasta kvantiteter, en procentsats eller full registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="f7839-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="f7839-119">Funktionen _Kvalitetshantering för lagerprocesser_ omfattar kvalitetshanteringsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="f7839-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="f7839-120">Om du använder den här funktionen kan du se [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md) för exempel på hur kvalitetshanteringen fungerar när den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f7839-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="f7839-121">Skapa en kvalitetsorder för delleveranser.</span><span class="sxs-lookup"><span data-stu-id="f7839-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="f7839-122">Om du vill skapa en kvalitetsorder som baseras på den kvantitet som inlevererats fysiskt till en order måste du markera kryssrutan **Per uppdaterad kvantitet** i formuläret **artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="f7839-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="f7839-123">Skapa testtyper som innehåller minimum-, maximum- och måltestvärden och utför testning av typen ”kvalitativ kontra kvantitativ” som har fördefinierade valideringresultat.</span><span class="sxs-lookup"><span data-stu-id="f7839-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="f7839-124">Ange en godtagbar kvalitetsnivå (AQL) för att kontrollera toleranserna för kvalitetsmått.</span><span class="sxs-lookup"><span data-stu-id="f7839-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="f7839-125">Ange resurser som en inspektionsåtgärd kräver, till exempel ett testområde och testinstrument.</span><span class="sxs-lookup"><span data-stu-id="f7839-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="f7839-126">Arbeta med kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="f7839-126">Working with quality associations</span></span>
<span data-ttu-id="f7839-127">Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="f7839-128">Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="f7839-129">Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="f7839-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="f7839-130">Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f7839-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="f7839-131">Beroende på inställningen för körningsplanen kan själva utlösarprocessen spärras medan det finns en öppen kvalitetsorder, eller så kan de efterföljande processerna, till exempel fakturering av inköpsorder, spärras.</span><span class="sxs-lookup"><span data-stu-id="f7839-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="f7839-132">**Obs!** Medan det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utlevereras.</span><span class="sxs-lookup"><span data-stu-id="f7839-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="f7839-133">Beroende på inställningen **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden.</span><span class="sxs-lookup"><span data-stu-id="f7839-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="f7839-134">För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och villkoren som en kvalitetsorder genereras för.</span><span class="sxs-lookup"><span data-stu-id="f7839-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="f7839-135">Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="f7839-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="f7839-136">En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.</span><span class="sxs-lookup"><span data-stu-id="f7839-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="f7839-137">Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i varje affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="f7839-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="f7839-138">För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.</span><span class="sxs-lookup"><span data-stu-id="f7839-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="f7839-139">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="f7839-139">Reference type</span></span></th>
<th><span data-ttu-id="f7839-140">Händelsetyp</span><span class="sxs-lookup"><span data-stu-id="f7839-140">Event type</span></span></th>
<th><span data-ttu-id="f7839-141">Körning</span><span class="sxs-lookup"><span data-stu-id="f7839-141">Execution</span></span></th>
<th><span data-ttu-id="f7839-142">Händelsespärr</span><span class="sxs-lookup"><span data-stu-id="f7839-142">Event blocking</span></span></th>
<th><span data-ttu-id="f7839-143">Dokumentreferens</span><span class="sxs-lookup"><span data-stu-id="f7839-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="f7839-144">Lager</span><span class="sxs-lookup"><span data-stu-id="f7839-144">Inventory</span></span></td>
<td><span data-ttu-id="f7839-145">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="f7839-145">Not applicable</span></span></td>
<td><span data-ttu-id="f7839-146">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="f7839-146">Not applicable</span></span></td>
<td><span data-ttu-id="f7839-147">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-147">None</span></span></td>
<td><span data-ttu-id="f7839-148">Alla</span><span class="sxs-lookup"><span data-stu-id="f7839-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="f7839-149">Försäljning</span><span class="sxs-lookup"><span data-stu-id="f7839-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="f7839-150">Plockningsprocess har schemalagts</span><span class="sxs-lookup"><span data-stu-id="f7839-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="f7839-151">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-151">Before</span></span></td>
<td><span data-ttu-id="f7839-152">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="f7839-153">Specifikt ID, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="f7839-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-154">Plockningsprocess</span><span class="sxs-lookup"><span data-stu-id="f7839-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-155">Följesedel</span><span class="sxs-lookup"><span data-stu-id="f7839-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-156">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="f7839-157">Följesedel</span><span class="sxs-lookup"><span data-stu-id="f7839-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-158">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-158">Before</span></span></td>
<td><span data-ttu-id="f7839-159">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-160">Följesedel</span><span class="sxs-lookup"><span data-stu-id="f7839-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-161">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="f7839-162">Inköp</span><span class="sxs-lookup"><span data-stu-id="f7839-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="f7839-163">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="f7839-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="f7839-164">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-164">Before</span></span></td>
<td><span data-ttu-id="f7839-165">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-166">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="f7839-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-167">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="f7839-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-168">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="f7839-169">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-169">After</span></span></td>
<td><span data-ttu-id="f7839-170">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-171">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="f7839-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-172">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="f7839-173">Registrering</span><span class="sxs-lookup"><span data-stu-id="f7839-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-174">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="f7839-174">Not applicable</span></span></td>
<td><span data-ttu-id="f7839-175">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-176">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="f7839-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-177">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="f7839-178">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="f7839-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-179">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-179">Before</span></span></td>
<td><span data-ttu-id="f7839-180">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-181">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="f7839-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-182">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="f7839-183">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-183">After</span></span></td>
<td><span data-ttu-id="f7839-184">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-185">Faktura</span><span class="sxs-lookup"><span data-stu-id="f7839-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="f7839-186">Produktion</span><span class="sxs-lookup"><span data-stu-id="f7839-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-187">Registrering</span><span class="sxs-lookup"><span data-stu-id="f7839-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-188">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="f7839-188">Not applicable</span></span></td>
<td><span data-ttu-id="f7839-189">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="f7839-190">Alla</span><span class="sxs-lookup"><span data-stu-id="f7839-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-191">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-192">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="f7839-193">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-194">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-194">Before</span></span></td>
<td><span data-ttu-id="f7839-195">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-196">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-197">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="f7839-198">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-198">After</span></span></td>
<td><span data-ttu-id="f7839-199">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-200">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="f7839-201">Karantän</span><span class="sxs-lookup"><span data-stu-id="f7839-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-202">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="f7839-203">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-203">Before</span></span></td>
<td><span data-ttu-id="f7839-204">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-205">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-206">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-206">After</span></span></td>
<td><span data-ttu-id="f7839-207">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-208">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-208">End</span></span></td>
<td><span data-ttu-id="f7839-209">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-209">Before</span></span></td>
<td><span data-ttu-id="f7839-210">Slut</span><span class="sxs-lookup"><span data-stu-id="f7839-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="f7839-211">Flödesoperation</span><span class="sxs-lookup"><span data-stu-id="f7839-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-212">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="f7839-213">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-213">Before</span></span></td>
<td><span data-ttu-id="f7839-214">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-215">Specifikt ID, Grupp eller Alla och Resursspecifik, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="f7839-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-216">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-217">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-217">After</span></span></td>
<td><span data-ttu-id="f7839-218">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="f7839-219">Produktion av samprodukt</span><span class="sxs-lookup"><span data-stu-id="f7839-219">Co-product production</span></span></td>
<td><span data-ttu-id="f7839-220">Registrering</span><span class="sxs-lookup"><span data-stu-id="f7839-220">Registration</span></span></td>
<td><span data-ttu-id="f7839-221">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="f7839-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-222">Ingen</span><span class="sxs-lookup"><span data-stu-id="f7839-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="f7839-223">Alla</span><span class="sxs-lookup"><span data-stu-id="f7839-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="f7839-224">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="f7839-224">Report as finished</span></span></td>
<td><span data-ttu-id="f7839-225">Före</span><span class="sxs-lookup"><span data-stu-id="f7839-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-226">Efter</span><span class="sxs-lookup"><span data-stu-id="f7839-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f7839-227">Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.</span><span class="sxs-lookup"><span data-stu-id="f7839-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="f7839-228">Typ av process</span><span class="sxs-lookup"><span data-stu-id="f7839-228">Type of process</span></span></th>
<th><span data-ttu-id="f7839-229">När kvalitetsorder kan genereras automatiskt</span><span class="sxs-lookup"><span data-stu-id="f7839-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="f7839-230">När kvalitetsorder kan genereras om det krävs destruktivt test</span><span class="sxs-lookup"><span data-stu-id="f7839-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="f7839-231">Villkorsinformation</span><span class="sxs-lookup"><span data-stu-id="f7839-231">Condition information</span></span></th>
<th><span data-ttu-id="f7839-232">Information om manuell generering</span><span class="sxs-lookup"><span data-stu-id="f7839-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="f7839-233">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f7839-233">Purchase order</span></span></td>
<td><span data-ttu-id="f7839-234">Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</span><span class="sxs-lookup"><span data-stu-id="f7839-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="f7839-235">Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</span><span class="sxs-lookup"><span data-stu-id="f7839-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="f7839-236">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="f7839-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="f7839-237">En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="f7839-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-238">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="f7839-238">Quarantine order</span></span></td>
<td><span data-ttu-id="f7839-239">Före eller efter att karantänordern rapporteras som färdig eller avslutad</span><span class="sxs-lookup"><span data-stu-id="f7839-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="f7839-240">Kvalitetsorder som kräver destruktiva test kan inte genereras.</span><span class="sxs-lookup"><span data-stu-id="f7839-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="f7839-241">Det antas att karantänorderfunktionen hanterar dispositionen av materialet som förstörs.</span><span class="sxs-lookup"><span data-stu-id="f7839-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="f7839-242">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="f7839-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="f7839-243">En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="f7839-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-244">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="f7839-244">Sales order</span></span></td>
<td><span data-ttu-id="f7839-245">Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</span><span class="sxs-lookup"><span data-stu-id="f7839-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="f7839-246">I ett obestämt steg</span><span class="sxs-lookup"><span data-stu-id="f7839-246">At any step</span></span></td>
<td><span data-ttu-id="f7839-247">Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en kund, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="f7839-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="f7839-248">En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="f7839-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-249">Produktionsorder</span><span class="sxs-lookup"><span data-stu-id="f7839-249">Production order</span></span></td>
<td><span data-ttu-id="f7839-250">Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="f7839-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="f7839-251">Efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="f7839-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="f7839-252">Behovet av en kvalitetsorder kan återspegla en särskild plats eller artikel, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="f7839-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="f7839-253">En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="f7839-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-254">Produktionsorder som har en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="f7839-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="f7839-255">Före eller efter att rapporten är färdig för en åtgärd</span><span class="sxs-lookup"><span data-stu-id="f7839-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="f7839-256">Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</span><span class="sxs-lookup"><span data-stu-id="f7839-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="f7839-257">Behovet av en kvalitetsorder kan återspegla en särskild plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="f7839-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="f7839-258">En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="f7839-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f7839-259">Lager</span><span class="sxs-lookup"><span data-stu-id="f7839-259">Inventory</span></span></td>
<td><span data-ttu-id="f7839-260">En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="f7839-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f7839-261">En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet.</span><span class="sxs-lookup"><span data-stu-id="f7839-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="f7839-262">Fysisk lagerbehållning krävs.</span><span class="sxs-lookup"><span data-stu-id="f7839-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="f7839-263">Exempel på automatiska genereringar av kvalitetsorder</span><span class="sxs-lookup"><span data-stu-id="f7839-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="f7839-264">Inköp</span><span class="sxs-lookup"><span data-stu-id="f7839-264">Purchasing</span></span>

<span data-ttu-id="f7839-265">I inköp, om du ställer in fältet **händelsetyp** till **produktinleverans** och fältet **körning** till **efter** på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="f7839-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="f7839-266">Om alternativet **per uppdaterad kvantitet** är inställt på **Ja**, genereras en kvalitetsorder för varje inleverans mot inköpsordern, baserat på inlevererad kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="f7839-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="f7839-267">Varje gång en kvantitet inlevereras mot inköpsordern genereras nya kvalitetsorder utifrån den nylevererade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="f7839-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="f7839-268">Om alternativet **per uppdaterad kvantitet** är inställt på **Nej**, genereras en kvalitetsorder för första inleveransen mot inköpsordern, baserat på inlevererad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="f7839-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="f7839-269">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="f7839-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="f7839-270">Kvalitetsorder genereras inte för efterföljande inleveranser mot inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="f7839-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="f7839-271">Produktion</span><span class="sxs-lookup"><span data-stu-id="f7839-271">Production</span></span>

<span data-ttu-id="f7839-272">I produktion, om du ställer in fältet **händelsetyp** till **Rapportera som slutförd** och fältet **körning** till **efter** på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="f7839-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="f7839-273">Om alternativet **per uppdaterad kvantitet** är inställt på **Ja**, genereras en kvalitetsorder för varje slutförd kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="f7839-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="f7839-274">Varje gång en kvantitet rapporteras som slutförd mot produktionsorden genereras nya kvalitetsorder utifrån den nyligen avslutade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="f7839-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="f7839-275">Denna generations logik är förenlig med inköp.</span><span class="sxs-lookup"><span data-stu-id="f7839-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="f7839-276">Om alternativet **Per uppdaterad kvantitet** anges till **Nej**, genereras en kvalitetsorder första gången som en kvantitet rapporteras som färdig, baserat på den färdiga kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="f7839-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="f7839-277">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna av artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="f7839-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="f7839-278">Kvalitetsorder genereras inte för senare färdiga kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="f7839-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="f7839-279">Kvantitetsspecifikation</span><span class="sxs-lookup"><span data-stu-id="f7839-279">Quality specification</span></span></th>
<th><span data-ttu-id="f7839-280">Per uppdaterad kvantitet</span><span class="sxs-lookup"><span data-stu-id="f7839-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="f7839-281">Per spårningsdimension</span><span class="sxs-lookup"><span data-stu-id="f7839-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="f7839-282">Resultat</span><span class="sxs-lookup"><span data-stu-id="f7839-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="f7839-283">Procent: 10 %</span><span class="sxs-lookup"><span data-stu-id="f7839-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="f7839-284">Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="f7839-285">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-285">Batch number: No</span></span></p>
<p><span data-ttu-id="f7839-286">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="f7839-287">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="f7839-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="f7839-288">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="f7839-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="f7839-289">Kvalitetsorder #1 för 3 (10 % av 30)</span><span class="sxs-lookup"><span data-stu-id="f7839-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="f7839-290">Rapportera som slutförd för 70</span><span class="sxs-lookup"><span data-stu-id="f7839-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="f7839-291">Kvalitetsorder #2 för 7 (10 % av det resterande orderkvantiteten, vilket är lika med 70 i det här fallet)</span><span class="sxs-lookup"><span data-stu-id="f7839-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="f7839-292">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="f7839-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="f7839-293">Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-293">No</span></span></td>
<td>
<p><span data-ttu-id="f7839-294">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-294">Batch number: No</span></span></p>
<p><span data-ttu-id="f7839-295">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="f7839-296">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="f7839-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="f7839-297">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="f7839-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="f7839-298">Kvalitetsorder #1 för 1 (för den första kvantiteten som rapporteras som färdig, som har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="f7839-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="f7839-299">Kvalitetsorder #2 för 1 (för den återstående kvantiteten som fortfarande har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="f7839-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="f7839-300">Rapportera som slutförd för 10</span><span class="sxs-lookup"><span data-stu-id="f7839-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="f7839-301">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="f7839-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="f7839-302">Rapportera som slutförd för 60</span><span class="sxs-lookup"><span data-stu-id="f7839-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="f7839-303">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="f7839-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="f7839-304">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="f7839-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="f7839-305">Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="f7839-306">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="f7839-307">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="f7839-308">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="f7839-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="f7839-309">Rapportera som färdig till 3:1 #b1, #s1; 1 för #b2, #s2; och 1 för #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="f7839-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="f7839-310">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1</span><span class="sxs-lookup"><span data-stu-id="f7839-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="f7839-311">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2</span><span class="sxs-lookup"><span data-stu-id="f7839-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="f7839-312">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3</span><span class="sxs-lookup"><span data-stu-id="f7839-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="f7839-313">Rapportera som färdig för 2:1 #b4, #s4; och 1 för #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="f7839-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="f7839-314">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4</span><span class="sxs-lookup"><span data-stu-id="f7839-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="f7839-315">Kvalitetsorder #5 för 1 av batch #b5, seriell #s5</span><span class="sxs-lookup"><span data-stu-id="f7839-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="f7839-316"><strong>Obs!</strong> batchen kan återanvändas.</span><span class="sxs-lookup"><span data-stu-id="f7839-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="f7839-317">Fast kvantitet: 2</span><span class="sxs-lookup"><span data-stu-id="f7839-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="f7839-318">Nej</span><span class="sxs-lookup"><span data-stu-id="f7839-318">No</span></span></td>
<td>
<p><span data-ttu-id="f7839-319">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="f7839-320">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="f7839-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="f7839-321">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="f7839-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="f7839-322">Rapportera som färdig till 4: 1 för #b1, #s1; 1 för #b2, #s2; 1 för #b3, #s3; och 1 för #b4, #s4</span><span class="sxs-lookup"><span data-stu-id="f7839-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="f7839-323">Kvalitetsorder #1 för 1 av batch #b1, seriell #s1</span><span class="sxs-lookup"><span data-stu-id="f7839-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="f7839-324">Kvalitetsorder #2 för 1 av batch #b2, seriell #s2</span><span class="sxs-lookup"><span data-stu-id="f7839-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="f7839-325">Kvalitetsorder #3 för 1 av batch #b3, seriell #s3</span><span class="sxs-lookup"><span data-stu-id="f7839-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="f7839-326">Kvalitetsorder #4 för 1 av batch #b4, seriell #s4</span><span class="sxs-lookup"><span data-stu-id="f7839-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="f7839-327">Kvalitetsorder #5 för 2, utan referens till ett batch- och ett serienummer</span><span class="sxs-lookup"><span data-stu-id="f7839-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="f7839-328">Rapportera som färdig till 6: 1 för #b5, #s5; 1 för #b6, #s6; 1 för #b7, #s7; 1 för #b8, #s8; 1 för #b9, #s9; och 1 för #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="f7839-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="f7839-329">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="f7839-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f7839-330">Funktionen *Kvalitetshantering för lagerprocesser* tillsätter funktioner för bearbetning av kvalitetsorder för produktion med **Händelsetyp** inställd på *Rapportera som färdig* och **Körning** inställd på *Efter* och för köp med **Händelsetypen** inställd på *Registrering*.</span><span class="sxs-lookup"><span data-stu-id="f7839-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="f7839-331">Mer information finns i [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="f7839-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="f7839-332">Kvalitetshanteringssidor</span><span class="sxs-lookup"><span data-stu-id="f7839-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7839-333">Sida</span><span class="sxs-lookup"><span data-stu-id="f7839-333">Page</span></span></th>
<th><span data-ttu-id="f7839-334">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f7839-334">Description</span></span></th>
<th><span data-ttu-id="f7839-335">Exempel</span><span class="sxs-lookup"><span data-stu-id="f7839-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f7839-336">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="f7839-336">Quality associations</span></span></td>
<td><span data-ttu-id="f7839-337">Se föregående avsnitt i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f7839-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="f7839-338">En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:</span><span class="sxs-lookup"><span data-stu-id="f7839-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="f7839-339">Transaktionshändelsen</span><span class="sxs-lookup"><span data-stu-id="f7839-339">The transaction event</span></span></li>
<li><span data-ttu-id="f7839-340">Uppsättningen med tester som måste utföras på artiklarna</span><span class="sxs-lookup"><span data-stu-id="f7839-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="f7839-341">Den godtagbara kvalitetsnivån</span><span class="sxs-lookup"><span data-stu-id="f7839-341">The AQL</span></span></li>
<li><span data-ttu-id="f7839-342">Samplingsplanen</span><span class="sxs-lookup"><span data-stu-id="f7839-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="f7839-343">Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="f7839-344">En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f7839-345">Tester</span><span class="sxs-lookup"><span data-stu-id="f7839-345">Tests</span></span></td>
<td><span data-ttu-id="f7839-346">Använd den här sidan när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna.</span><span class="sxs-lookup"><span data-stu-id="f7839-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="f7839-347">Du kan tilldela en eller flera enskilda tester till en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7839-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="f7839-348">I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden.</span><span class="sxs-lookup"><span data-stu-id="f7839-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="f7839-349">Måttvärden används för kvantitativa tester, och testvariabler används för kvalitativa tester.</span><span class="sxs-lookup"><span data-stu-id="f7839-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="f7839-350">Ett kvantitativt test har testtypen <strong>Heltal</strong> eller <strong>Del</strong> och har också en bestämd måttenhet.</span><span class="sxs-lookup"><span data-stu-id="f7839-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="f7839-351">Kvalitetsspecifikationer och testresultat uttrycks som nummer.</span><span class="sxs-lookup"><span data-stu-id="f7839-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="f7839-352">Ett kvalitativt test har testtypen <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="f7839-353">Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ.</span><span class="sxs-lookup"><span data-stu-id="f7839-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="f7839-354">Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.</span><span class="sxs-lookup"><span data-stu-id="f7839-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="f7839-355">Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test om förpackningsskador.</span><span class="sxs-lookup"><span data-stu-id="f7839-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="f7839-356">Företaget definierar mer information om det kvalitativa testet för att identifiera testvariabeln (skadad förpackning) och dess utfall.</span><span class="sxs-lookup"><span data-stu-id="f7839-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="f7839-357">Företaget använder sidan <strong>Testgrupper</strong> för att tilldela de två testerna till en testgrupp och ange testspecifik information.</span><span class="sxs-lookup"><span data-stu-id="f7839-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="f7839-358">Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.</span><span class="sxs-lookup"><span data-stu-id="f7839-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f7839-359">Testgrupper</span><span class="sxs-lookup"><span data-stu-id="f7839-359">Test groups</span></span></td>
<td><span data-ttu-id="f7839-360">Använd den här sidan när du vill ställa in, redigera och visa testgrupper och enskilda tester som har tilldelats en testgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7839-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="f7839-361">I det övre fönstret visas testgrupper, och i det nedre visas testerna som har tilldelats en vald testgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7839-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="f7839-362">Du kan tilldela flera principer till en testgrupp, t.ex. en samplingsplan, en godtagbar kvalitetsnivå och behovet av destruktiv testning.</span><span class="sxs-lookup"><span data-stu-id="f7839-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="f7839-363">När du tilldelar ett enskilt test till en testgrupp definierar du ytterligare information, till exempel sekvensen, dokument och giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="f7839-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="f7839-364">För ett kvantitativt test innehåller informationen som du anger även acceptabla mätvärden.</span><span class="sxs-lookup"><span data-stu-id="f7839-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="f7839-365">För ett kvalitativt test innehåller informationen testvariabeln och standardresultatet.</span><span class="sxs-lookup"><span data-stu-id="f7839-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="f7839-366">Den testgrupp som har tilldelats till en kvalitetsorder definierar standarduppsättningen med test som måste utföras på den angivna artikeln.</span><span class="sxs-lookup"><span data-stu-id="f7839-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="f7839-367">Du kan dock lägga till, ta bort eller ändra tester för en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="f7839-368">Testresultaten rapporteras för varje test på en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="f7839-369">Ett tillverkningsföretag definierar en testgrupp för varje variant av sina kvalitetsriktlinjer.</span><span class="sxs-lookup"><span data-stu-id="f7839-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="f7839-370">De olika testgrupperna återspeglar skillnaderna i samplingsplanerna, uppsättningarna med tester som måste utföras tillsammans, den godtagbara kvalitetsnivån och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="f7839-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="f7839-371">För kvantitativa tester finns det också skillnader i de godtagbara måttvärdena.</span><span class="sxs-lookup"><span data-stu-id="f7839-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="f7839-372">Om du vill framtvinga kvalitetsriktlinjerna tilldelar företaget en testgrupp till varje regel för automatisk generering av kvalitetsorder på sidan <strong>Kvalitetsassociationer</strong> och tilldelar även en testgrupp till kvalitetsorder som har skapats manuellt.</span><span class="sxs-lookup"><span data-stu-id="f7839-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f7839-373">Kvalitetsgrupper för artiklar</span><span class="sxs-lookup"><span data-stu-id="f7839-373">Item quality groups</span></span></td>
<td><span data-ttu-id="f7839-374">Använd den här sidan när du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel.</span><span class="sxs-lookup"><span data-stu-id="f7839-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="f7839-375">En kvalitetsgrupp representerar gemensamma testbehov för artiklar.</span><span class="sxs-lookup"><span data-stu-id="f7839-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="f7839-376">När du har definierat testkraven på sidan <strong>Testgrupper</strong> kan du definiera reglerna för automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f7839-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="f7839-377">För att förenkla processen definierar du inte regler för enskilda artiklar.</span><span class="sxs-lookup"><span data-stu-id="f7839-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="f7839-378">I stället definierar du regler för en kvalitetsgrupp genom att använda sidan <strong>Kvalitetsassociationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="f7839-379">Du kan också använda <strong>Kvalitetsgrupper för artiklar</strong> för en vald kvalitetsgrupp för att tilldela relevanta artiklar till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="f7839-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="f7839-380">Du kan också använda sidan <strong>Kvalitetsgrupper för artiklar</strong> för en vald artikel för att tilldela relevanta kvalitetsgrupper till den artikeln.</span><span class="sxs-lookup"><span data-stu-id="f7839-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="f7839-381">Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion.</span><span class="sxs-lookup"><span data-stu-id="f7839-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="f7839-382">Företaget definierar en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="f7839-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="f7839-383">Senare köper företaget en ny typ av råmaterial som har samma testbehov.</span><span class="sxs-lookup"><span data-stu-id="f7839-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="f7839-384">I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="f7839-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="f7839-385">Samma tillverkningsföretag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans.</span><span class="sxs-lookup"><span data-stu-id="f7839-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="f7839-386">Företaget definierar två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till varje grupp.</span><span class="sxs-lookup"><span data-stu-id="f7839-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f7839-387">Testvariabler</span><span class="sxs-lookup"><span data-stu-id="f7839-387">Test variables</span></span></td>
<td><span data-ttu-id="f7839-388">Använd den här sidan för att definiera och visa variablerna som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="f7839-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="f7839-389">För varje variabel definierar du fasta resultat som representerar de möjliga alternativen.</span><span class="sxs-lookup"><span data-stu-id="f7839-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="f7839-390">Du definierar testerna på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="f7839-391">För kvalitativa tester måste du ange testtypen till <strong>Alternativ</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="f7839-392">Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel till ett enskilt test.</span><span class="sxs-lookup"><span data-stu-id="f7839-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="f7839-393">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="f7839-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="f7839-394">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="f7839-394">This inspection test has several variables.</span></span> <span data-ttu-id="f7839-395">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="f7839-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="f7839-396">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="f7839-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f7839-397">Resultat från testvariabel</span><span class="sxs-lookup"><span data-stu-id="f7839-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="f7839-398">Använd den här sidan när du vill ställa in, redigera och visa möjliga testresultat för en testvariabel som hör till ett kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="f7839-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="f7839-399">För varje resultat tilldelar du statusen <strong>godkänt</strong> eller <strong>underkänt</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="f7839-400">Du måste definiera en variabel och dess resultat för varje kvalitativt test som definieras på sidan <strong>Tester</strong>.</span><span class="sxs-lookup"><span data-stu-id="f7839-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="f7839-401">(För kvalitativa tester anges testtypen som <strong>Alternativ</strong> på sidan <strong>Tester</strong>.) Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel och standardresultatet till ett enskilt kvalitativt test.</span><span class="sxs-lookup"><span data-stu-id="f7839-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="f7839-402">Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="f7839-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="f7839-403">Det här inspektionstestet har flera variabler.</span><span class="sxs-lookup"><span data-stu-id="f7839-403">This inspection test has of several variables.</span></span> <span data-ttu-id="f7839-404">En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig.</span><span class="sxs-lookup"><span data-stu-id="f7839-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="f7839-405">En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</span><span class="sxs-lookup"><span data-stu-id="f7839-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="f7839-406">Statusen <strong>godkänt</strong> eller <strong>underkänt</strong> tilldelas till varje resultat.</span><span class="sxs-lookup"><span data-stu-id="f7839-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="f7839-407">Under inspektionstestet av respektive variabel rapporterar inspektören testresultatet genom att välja något av resultaten.</span><span class="sxs-lookup"><span data-stu-id="f7839-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="f7839-408">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f7839-408">Additional resources</span></span>
--------

[<span data-ttu-id="f7839-409">Kvalitetshanteringsprocesser</span><span class="sxs-lookup"><span data-stu-id="f7839-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="f7839-410">Avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="f7839-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="f7839-411">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="f7839-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)
