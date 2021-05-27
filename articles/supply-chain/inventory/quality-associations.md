---
title: Kvalitetsassociationer
description: I detta ämne beskrivs hur du kan använda kvalitetsassociationer i Microsoft Dynamics 365 Supply Chain Management för att automatiskt generera kvalitetsorder som hör till dina försäljnings-, inköps- och produktionsprocesser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c6fab1b89b7e58d9e443c27da03a6b13afcc9c6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022334"
---
# <a name="quality-associations"></a><span data-ttu-id="4c10a-103">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="4c10a-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c10a-104">I detta ämne beskrivs hur du kan använda kvalitetsassociationer i Microsoft Dynamics 365 Supply Chain Management för att automatiskt generera kvalitetsorder som hör till dina försäljnings-, inköps- och produktionsprocesser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="4c10a-105">En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:</span><span class="sxs-lookup"><span data-stu-id="4c10a-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="4c10a-106">Transaktionshändelsen</span><span class="sxs-lookup"><span data-stu-id="4c10a-106">The transaction event</span></span>
- <span data-ttu-id="4c10a-107">Uppsättningen med tester som måste utföras på artiklarna</span><span class="sxs-lookup"><span data-stu-id="4c10a-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="4c10a-108">Godtagbar kvalitetsnivå (AQL)</span><span class="sxs-lookup"><span data-stu-id="4c10a-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="4c10a-109">Samplingsplanen</span><span class="sxs-lookup"><span data-stu-id="4c10a-109">The sampling plan</span></span>

<span data-ttu-id="4c10a-110">Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="4c10a-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="4c10a-111">En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="4c10a-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="4c10a-112">Arbeta med kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="4c10a-112">Working with quality associations</span></span>

<span data-ttu-id="4c10a-113">Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="4c10a-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="4c10a-114">Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="4c10a-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="4c10a-115">Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="4c10a-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="4c10a-116">Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras.</span><span class="sxs-lookup"><span data-stu-id="4c10a-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="4c10a-117">Beroende på hur körningsplanen har ställts in kan själva utlösarprocessen spärras när det finns en öppen kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="4c10a-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="4c10a-118">Efterföljande processer, såsom inköpsorderfakturering, kan också spärras.</span><span class="sxs-lookup"><span data-stu-id="4c10a-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="4c10a-119">Även om det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utfärdas.</span><span class="sxs-lookup"><span data-stu-id="4c10a-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="4c10a-120">Beroende på inställningen för fältet **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden.</span><span class="sxs-lookup"><span data-stu-id="4c10a-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="4c10a-121">Mer information finns i [Artikelsampling för kvalitetshantering](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="4c10a-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="4c10a-122">För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och de villkor som en kvalitetsorder genereras för.</span><span class="sxs-lookup"><span data-stu-id="4c10a-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="4c10a-123">Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="4c10a-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="4c10a-124">En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="4c10a-125">Om du vill arbeta med kvalitetsassociationer går du till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsassociationer**.</span><span class="sxs-lookup"><span data-stu-id="4c10a-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="4c10a-126">Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i respektive affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="4c10a-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="4c10a-127">För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.</span><span class="sxs-lookup"><span data-stu-id="4c10a-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c10a-128">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="4c10a-128">Reference type</span></span></th>
<th><span data-ttu-id="4c10a-129">Händelsetyp</span><span class="sxs-lookup"><span data-stu-id="4c10a-129">Event type</span></span></th>
<th><span data-ttu-id="4c10a-130">Körning</span><span class="sxs-lookup"><span data-stu-id="4c10a-130">Execution</span></span></th>
<th><span data-ttu-id="4c10a-131">Händelsespärr</span><span class="sxs-lookup"><span data-stu-id="4c10a-131">Event blocking</span></span></th>
<th><span data-ttu-id="4c10a-132">Dokumentreferens</span><span class="sxs-lookup"><span data-stu-id="4c10a-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4c10a-133">Lager</span><span class="sxs-lookup"><span data-stu-id="4c10a-133">Inventory</span></span></td>
<td><span data-ttu-id="4c10a-134">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4c10a-134">Not applicable</span></span></td>
<td><span data-ttu-id="4c10a-135">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4c10a-135">Not applicable</span></span></td>
<td><span data-ttu-id="4c10a-136">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-136">None</span></span></td>
<td><span data-ttu-id="4c10a-137">Alla</span><span class="sxs-lookup"><span data-stu-id="4c10a-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="4c10a-138">Försäljning</span><span class="sxs-lookup"><span data-stu-id="4c10a-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="4c10a-139">Plockningsprocess har schemalagts</span><span class="sxs-lookup"><span data-stu-id="4c10a-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="4c10a-140">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-140">Before</span></span></td>
<td><span data-ttu-id="4c10a-141">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="4c10a-142">Specifikt ID, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="4c10a-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-143">Plockningsprocess</span><span class="sxs-lookup"><span data-stu-id="4c10a-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-144">Följesedel</span><span class="sxs-lookup"><span data-stu-id="4c10a-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-145">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="4c10a-146">Följesedel</span><span class="sxs-lookup"><span data-stu-id="4c10a-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-147">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-147">Before</span></span></td>
<td><span data-ttu-id="4c10a-148">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-149">Följesedel</span><span class="sxs-lookup"><span data-stu-id="4c10a-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-150">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="4c10a-151">Inköp</span><span class="sxs-lookup"><span data-stu-id="4c10a-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="4c10a-152">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="4c10a-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="4c10a-153">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-153">Before</span></span></td>
<td><span data-ttu-id="4c10a-154">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-155">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="4c10a-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-156">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="4c10a-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-157">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="4c10a-158">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-158">After</span></span></td>
<td><span data-ttu-id="4c10a-159">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-160">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="4c10a-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-161">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="4c10a-162">Registrering</span><span class="sxs-lookup"><span data-stu-id="4c10a-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-163">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4c10a-163">Not applicable</span></span></td>
<td><span data-ttu-id="4c10a-164">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-165">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="4c10a-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-166">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="4c10a-167">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="4c10a-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-168">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-168">Before</span></span></td>
<td><span data-ttu-id="4c10a-169">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-170">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="4c10a-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-171">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="4c10a-172">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-172">After</span></span></td>
<td><span data-ttu-id="4c10a-173">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-174">Faktura</span><span class="sxs-lookup"><span data-stu-id="4c10a-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="4c10a-175">Produktion</span><span class="sxs-lookup"><span data-stu-id="4c10a-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-176">Registrering</span><span class="sxs-lookup"><span data-stu-id="4c10a-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-177">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4c10a-177">Not applicable</span></span></td>
<td><span data-ttu-id="4c10a-178">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="4c10a-179">Alla</span><span class="sxs-lookup"><span data-stu-id="4c10a-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-180">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-181">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="4c10a-182">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-183">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-183">Before</span></span></td>
<td><span data-ttu-id="4c10a-184">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-185">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-186">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="4c10a-187">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-187">After</span></span></td>
<td><span data-ttu-id="4c10a-188">Ingen</span><span class="sxs-lookup"><span data-stu-id="4c10a-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-189">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="4c10a-190">Karantän</span><span class="sxs-lookup"><span data-stu-id="4c10a-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-191">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="4c10a-192">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-192">Before</span></span></td>
<td><span data-ttu-id="4c10a-193">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-194">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-195">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-195">After</span></span></td>
<td><span data-ttu-id="4c10a-196">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-197">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-197">End</span></span></td>
<td><span data-ttu-id="4c10a-198">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-198">Before</span></span></td>
<td><span data-ttu-id="4c10a-199">Slut</span><span class="sxs-lookup"><span data-stu-id="4c10a-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="4c10a-200">Flödesoperation</span><span class="sxs-lookup"><span data-stu-id="4c10a-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-201">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="4c10a-202">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-202">Before</span></span></td>
<td><span data-ttu-id="4c10a-203">None</span><span class="sxs-lookup"><span data-stu-id="4c10a-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-204">Specifikt ID, Grupp eller Alla samt Specifik resurs, Grupp eller Alla</span><span class="sxs-lookup"><span data-stu-id="4c10a-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-205">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-206">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-206">After</span></span></td>
<td><span data-ttu-id="4c10a-207">None</span><span class="sxs-lookup"><span data-stu-id="4c10a-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="4c10a-208">Produktion av samprodukt</span><span class="sxs-lookup"><span data-stu-id="4c10a-208">Co-product production</span></span></td>
<td><span data-ttu-id="4c10a-209">Registrering</span><span class="sxs-lookup"><span data-stu-id="4c10a-209">Registration</span></span></td>
<td><span data-ttu-id="4c10a-210">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="4c10a-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-211">None</span><span class="sxs-lookup"><span data-stu-id="4c10a-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="4c10a-212">Allt</span><span class="sxs-lookup"><span data-stu-id="4c10a-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="4c10a-213">Rapportera som färdig</span><span class="sxs-lookup"><span data-stu-id="4c10a-213">Report as finished</span></span></td>
<td><span data-ttu-id="4c10a-214">Före</span><span class="sxs-lookup"><span data-stu-id="4c10a-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-215">Efter</span><span class="sxs-lookup"><span data-stu-id="4c10a-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4c10a-216">Funktionen *Kvalitetshantering för lagerprocesser* tillsätter funktioner för bearbetning av kvalitetsorder för produktion där fältet **Händelsetyp** är inställt på *Rapportera som färdig* och fältet **Körning** inställt på *Efter*, samt för köp där fältet **Händelsetyp** är inställt på *Registrering*.</span><span class="sxs-lookup"><span data-stu-id="4c10a-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="4c10a-217">Mer information finns i [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="4c10a-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="4c10a-218">Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.</span><span class="sxs-lookup"><span data-stu-id="4c10a-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="4c10a-219">Typ av process</span><span class="sxs-lookup"><span data-stu-id="4c10a-219">Type of process</span></span></th>
<th><span data-ttu-id="4c10a-220">När kvalitetsorder kan genereras automatiskt</span><span class="sxs-lookup"><span data-stu-id="4c10a-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="4c10a-221">När kvalitetsorder kan genereras om det krävs destruktivt test</span><span class="sxs-lookup"><span data-stu-id="4c10a-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="4c10a-222">Villkorsinformation</span><span class="sxs-lookup"><span data-stu-id="4c10a-222">Condition information</span></span></th>
<th><span data-ttu-id="4c10a-223">Information om manuell generering</span><span class="sxs-lookup"><span data-stu-id="4c10a-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4c10a-224">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="4c10a-224">Purchase order</span></span></td>
<td><span data-ttu-id="4c10a-225">Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</span><span class="sxs-lookup"><span data-stu-id="4c10a-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="4c10a-226">Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</span><span class="sxs-lookup"><span data-stu-id="4c10a-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="4c10a-227">Behovet av en kvalitetsorder kan återspegla en specifik, artikel eller leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="4c10a-228">En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-229">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="4c10a-229">Quarantine order</span></span></td>
<td><span data-ttu-id="4c10a-230">Före eller efter att karantänordern rapporteras som färdig eller avslutad</span><span class="sxs-lookup"><span data-stu-id="4c10a-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="4c10a-231">Kvalitetsorder som kräver destruktiva tester kan inte genereras.</span><span class="sxs-lookup"><span data-stu-id="4c10a-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="4c10a-232">Det antas att funktionen för karantänorder hanterar dispositionen av materialet som förstörs.</span><span class="sxs-lookup"><span data-stu-id="4c10a-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="4c10a-233">Behovet av en kvalitetsorder kan återspegla en specifik, artikel eller leverantör, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="4c10a-234">En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-235">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="4c10a-235">Sales order</span></span></td>
<td><span data-ttu-id="4c10a-236">Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</span><span class="sxs-lookup"><span data-stu-id="4c10a-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="4c10a-237">I ett obestämt steg</span><span class="sxs-lookup"><span data-stu-id="4c10a-237">At any step</span></span></td>
<td><span data-ttu-id="4c10a-238">Behovet av en kvalitetsorder kan återspegla en specifik plats, artikel eller kund, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="4c10a-239">En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-240">Produktionsorder</span><span class="sxs-lookup"><span data-stu-id="4c10a-240">Production order</span></span></td>
<td><span data-ttu-id="4c10a-241">Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="4c10a-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="4c10a-242">Efter att den fullständiga kvantiteten för produktionsordern rapporteras</span><span class="sxs-lookup"><span data-stu-id="4c10a-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="4c10a-243">Behovet av en kvalitetsorder kan återspegla en specifik plats eller artikel, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="4c10a-244">En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-245">Produktionsorder som har en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="4c10a-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="4c10a-246">Före eller efter att rapporten är färdig för en åtgärd</span><span class="sxs-lookup"><span data-stu-id="4c10a-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="4c10a-247">Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</span><span class="sxs-lookup"><span data-stu-id="4c10a-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="4c10a-248">Behovet av en kvalitetsorder kan återspegla en specifik plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</span><span class="sxs-lookup"><span data-stu-id="4c10a-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="4c10a-249">En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</span><span class="sxs-lookup"><span data-stu-id="4c10a-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-250">Lager</span><span class="sxs-lookup"><span data-stu-id="4c10a-250">Inventory</span></span></td>
<td><span data-ttu-id="4c10a-251">En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="4c10a-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="4c10a-252">En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet.</span><span class="sxs-lookup"><span data-stu-id="4c10a-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="4c10a-253">Fysisk lagerbehållning krävs.</span><span class="sxs-lookup"><span data-stu-id="4c10a-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="4c10a-254">Exempel på automatisk generering av kvalitetsorder</span><span class="sxs-lookup"><span data-stu-id="4c10a-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="4c10a-255">Inköp</span><span class="sxs-lookup"><span data-stu-id="4c10a-255">Purchasing</span></span>

<span data-ttu-id="4c10a-256">I inköp, om du ställer in fältet **händelsetyp** till *produktinleverans* och fältet **körning** till *efter* på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="4c10a-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="4c10a-257">Om alternativet **per uppdaterad kvantitet** är inställt på *Ja*, genereras en kvalitetsorder för varje inleverans mot inköpsordern, baserat på inlevererad kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="4c10a-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="4c10a-258">Varje gång en kvantitet inlevereras mot inköpsordern genereras nya kvalitetsorder utifrån den nylevererade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="4c10a-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="4c10a-259">Om alternativet **per uppdaterad kvantitet** är inställt på *Nej*, genereras en kvalitetsorder för första inleveransen mot inköpsordern, baserat på inlevererad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4c10a-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="4c10a-260">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4c10a-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="4c10a-261">Kvalitetsorder genereras inte för efterföljande inleveranser mot inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="4c10a-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="4c10a-262">Produktion</span><span class="sxs-lookup"><span data-stu-id="4c10a-262">Production</span></span>

<span data-ttu-id="4c10a-263">I produktion, om du ställer in fältet **händelsetyp** till *Rapportera som slutförd* och fältet **körning** till *efter* på sidan **kvalitetsassociationer**, får du följande resultat:</span><span class="sxs-lookup"><span data-stu-id="4c10a-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="4c10a-264">Om alternativet **per uppdaterad kvantitet** är inställt på *Ja*, genereras en kvalitetsorder för varje slutförd kvantitet och inställningar i artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="4c10a-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="4c10a-265">Varje gång en kvantitet rapporteras som slutförd mot produktionsorden genereras nya kvalitetsorder utifrån den nyligen avslutade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="4c10a-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="4c10a-266">Denna generations logik är förenlig med inköp.</span><span class="sxs-lookup"><span data-stu-id="4c10a-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="4c10a-267">Om alternativet **Per uppdaterad kvantitet** anges till *Nej*, genereras en kvalitetsorder första gången som en kvantitet rapporteras som färdig, baserat på den färdiga kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="4c10a-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="4c10a-268">Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna av artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="4c10a-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="4c10a-269">Kvalitetsorder genereras inte för senare färdiga kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="4c10a-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c10a-270">Kvantitetsspecifikation</span><span class="sxs-lookup"><span data-stu-id="4c10a-270">Quality specification</span></span></th>
<th><span data-ttu-id="4c10a-271">Per uppdaterad kvantitet</span><span class="sxs-lookup"><span data-stu-id="4c10a-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="4c10a-272">Per spårningsdimension</span><span class="sxs-lookup"><span data-stu-id="4c10a-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="4c10a-273">Resultat</span><span class="sxs-lookup"><span data-stu-id="4c10a-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4c10a-274">Procent: 10 %</span><span class="sxs-lookup"><span data-stu-id="4c10a-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="4c10a-275">Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="4c10a-276">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="4c10a-276">Batch number: No</span></span></p>
<p><span data-ttu-id="4c10a-277">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="4c10a-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="4c10a-278">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="4c10a-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="4c10a-279">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="4c10a-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="4c10a-280">Kvalitetsorder 1 för 3 (10 % av 30)</span><span class="sxs-lookup"><span data-stu-id="4c10a-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c10a-281">Rapportera som slutförd för 70</span><span class="sxs-lookup"><span data-stu-id="4c10a-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="4c10a-282">Kvalitetsorder 2 för 7 (10 % av det resterande orderkvantiteten, vilket i det här fallet är lika med 70)</span><span class="sxs-lookup"><span data-stu-id="4c10a-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-283">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="4c10a-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="4c10a-284">Nr</span><span class="sxs-lookup"><span data-stu-id="4c10a-284">No</span></span></td>
<td>
<p><span data-ttu-id="4c10a-285">Batchnummer: Nej</span><span class="sxs-lookup"><span data-stu-id="4c10a-285">Batch number: No</span></span></p>
<p><span data-ttu-id="4c10a-286">Serienummer: Nej</span><span class="sxs-lookup"><span data-stu-id="4c10a-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="4c10a-287">Orderkvantitet: 100</span><span class="sxs-lookup"><span data-stu-id="4c10a-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="4c10a-288">Rapportera som slutförd för 30</span><span class="sxs-lookup"><span data-stu-id="4c10a-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="4c10a-289">Kvalitetsorder 1 för 1 (för den första kvantiteten som rapporteras som färdig, som har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="4c10a-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="4c10a-290">Kvalitetsorder 2 för 1 (för den återstående kvantiteten som fortfarande har ett fast värde på 1)</span><span class="sxs-lookup"><span data-stu-id="4c10a-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c10a-291">Rapportera som slutförd för 10</span><span class="sxs-lookup"><span data-stu-id="4c10a-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="4c10a-292">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="4c10a-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c10a-293">Rapportera som slutförd för 60</span><span class="sxs-lookup"><span data-stu-id="4c10a-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="4c10a-294">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="4c10a-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-295">Fast kvantitet: 1</span><span class="sxs-lookup"><span data-stu-id="4c10a-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="4c10a-296">Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="4c10a-297">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="4c10a-298">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="4c10a-299">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="4c10a-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="4c10a-300">Rapportera som färdig för 3:1 för batchnummer b1, serienummer s1; 1 för batchnummer b2, serienummer s2; samt 1 för batchnummer b3, serienummer s3</span><span class="sxs-lookup"><span data-stu-id="4c10a-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="4c10a-301">Kvalitetsorder 1 för 1 av batchnummer b1, serienummer s1</span><span class="sxs-lookup"><span data-stu-id="4c10a-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="4c10a-302">Kvalitetsorder 2 för 1 av batchnummer b2, serienummer s2</span><span class="sxs-lookup"><span data-stu-id="4c10a-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="4c10a-303">Kvalitetsorder 3 för 1 av batchnummer b3, serienummer s3</span><span class="sxs-lookup"><span data-stu-id="4c10a-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c10a-304">Rapportera som färdig för 2:1 för batchnummer b4, serienummer s4; och 1 för batchnummer b5, serienummer s5</span><span class="sxs-lookup"><span data-stu-id="4c10a-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="4c10a-305">Kvalitetsorder 4 för 1 av batchnummer b4, serienummer s4</span><span class="sxs-lookup"><span data-stu-id="4c10a-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="4c10a-306">Kvalitetsorder 5 för 1 av batchnummer b5, serienummer s5</span><span class="sxs-lookup"><span data-stu-id="4c10a-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="4c10a-307"><strong>Obs!</strong> batchen kan återanvändas.</span><span class="sxs-lookup"><span data-stu-id="4c10a-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="4c10a-308">Fast kvantitet: 2</span><span class="sxs-lookup"><span data-stu-id="4c10a-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="4c10a-309">Nr</span><span class="sxs-lookup"><span data-stu-id="4c10a-309">No</span></span></td>
<td>
<p><span data-ttu-id="4c10a-310">Batch-nummer: Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="4c10a-311">Serienummer: Ja</span><span class="sxs-lookup"><span data-stu-id="4c10a-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="4c10a-312">Orderkvantitet: 10</span><span class="sxs-lookup"><span data-stu-id="4c10a-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="4c10a-313">Rapportera som färdig för 4:1 för batchnummer b1, serienummer s1; 1 för batchnummer b2, serienummer s2; 1 för batchnummer b3, serienummer s3; samt 1 för batchnummer b4, serienummer s4</span><span class="sxs-lookup"><span data-stu-id="4c10a-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="4c10a-314">Kvalitetsorder 1 för 1 av batchnummer b1, serienummer s1</span><span class="sxs-lookup"><span data-stu-id="4c10a-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="4c10a-315">Kvalitetsorder 2 för 1 av batchnummer b2, serienummer s2</span><span class="sxs-lookup"><span data-stu-id="4c10a-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="4c10a-316">Kvalitetsorder 3 för 1 av batchnummer b3, serienummer s3</span><span class="sxs-lookup"><span data-stu-id="4c10a-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="4c10a-317">Kvalitetsorder 4 för 1 av batchnummer b4, serienummer s4</span><span class="sxs-lookup"><span data-stu-id="4c10a-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="4c10a-318">Kvalitetsorder 5 för 2, utan referens till ett batch- och ett serienummer</span><span class="sxs-lookup"><span data-stu-id="4c10a-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c10a-319">Rapportera som färdig för 6:1 för batchnummer b5, serienummer s5; 1 för batchnummer b6, serienummer s6; 1 för batchnummer b7, serienummer s7; 1 för batchnummer b8, serienummer s8; 1 för batchnummer b9, serienummer s9; och 1 för batchnummer b10, serienummer s10</span><span class="sxs-lookup"><span data-stu-id="4c10a-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="4c10a-320">Inga kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="4c10a-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="4c10a-321">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4c10a-321">Additional resources</span></span>

- [<span data-ttu-id="4c10a-322">Kvalitetshanteringsprocesser</span><span class="sxs-lookup"><span data-stu-id="4c10a-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="4c10a-323">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="4c10a-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="4c10a-324">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="4c10a-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
