---
title: Leveransalternativ
description: Försäljningsordertagare kan använda sidan Leveransalternativ för att upptäcka alternativa orderuppfyllelsealternativ.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 829775e36a2d49ebbab5c719436cff4c92984635
ms.sourcegitcommit: ca7fc46607ae9d07725e1486b43c66d39ec5cdb5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035276"
---
# <a name="delivery-alternatives"></a><span data-ttu-id="4ac7d-103">Leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4ac7d-103">Delivery alternatives</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ac7d-104">Försäljningsordertagare kan använda sidan **Leveransalternativ** för att upptäcka alternativa orderuppfyllelsealternativ.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-104">Sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="4ac7d-105">Sidlayouten **Leveransalternativ** ger en bättre översikt över alla alternativ.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-105">The **Delivery alternatives** page layout gives an overview of all alternative options.</span></span> <span data-ttu-id="4ac7d-106">Den gör även att ordertagare kan leta utanför det det aktuella företaget för orderuppfyllelsemöjligheter.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-106">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="4ac7d-107">De kan nu visa både koncerninterna affärsmöjligheter och affärsmöjligheter från externa leverantörer.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-107">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="4ac7d-108">Genom sorteringsalternativ per leveransdatum, kan försäljningsordertagare visa en intelligent lista med leveransalternativ.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-108">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="4ac7d-109">Dessutom hjälper parametrar dem att bättre hantera föreslagna leveranser.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-109">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="4ac7d-110">Eftersom transporttiden kan påverka leveransdatum, kan försäljningsordertagare utforska de olika transportvalen som transportföretag erbjuder.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-110">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="4ac7d-111">Eftersom detaljerad information visas för varje förslag kan ordertagare fatta välgrundade beslut direkt från sidan **leveransalternativ**.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-111">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="4ac7d-112">Öppna sidan leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4ac7d-112">Open the Delivery alternatives page</span></span>

<span data-ttu-id="4ac7d-113">Du kan öppna sidan **Leveransalternativ** från försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-113">You can open the **Delivery alternatives** page from the sales order line.</span></span>

1. <span data-ttu-id="4ac7d-114">Välj **Produkter och leverans \> Leveransalternativ**.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-114">Select **Products and supply \> Delivery alternatives**.</span></span>
1. <span data-ttu-id="4ac7d-115">Välj **raddetaljer \> leverans \> leveransalternativ.**</span><span class="sxs-lookup"><span data-stu-id="4ac7d-115">Select **Line details \> Delivery \> Delivery alternatives.**</span></span>

<span data-ttu-id="4ac7d-116">Du kan också öppna sidan **leveransalternativ** genom att öppna arbetsytan **försäljningsorderbearbetning och förfrågan** och sedan klicka på **order och favoriter \> försenade orderrader \> leveransalternativ** **Obs!** Du kan endast öppna sidan **leveransalternativ** om båda följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="4ac7d-116">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then selecting **Orders and favorites \> Delayed order lines \> Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

- <span data-ttu-id="4ac7d-117">All obligatorisk försäljningsradinformation fylls i.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-117">All mandatory sales line information is filled in.</span></span>
- <span data-ttu-id="4ac7d-118">Fältet **Leveransdatumkontroll** anges till ett värde som är annat än **ingen**.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-118">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="4ac7d-119">Kontrollmetoder för leveransdatum</span><span class="sxs-lookup"><span data-stu-id="4ac7d-119">Delivery date control methods</span></span>

<span data-ttu-id="4ac7d-120">Kontrollmetod för leveransdatum bestämmer hur systemet upprättar leveransdatum, hur leveransalternativ beräknas och vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-120">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="4ac7d-121">Observera att leveransdatumkontroll beaktar kalendrar.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-121">Note that delivery date control takes calendars into consideration.</span></span> <span data-ttu-id="4ac7d-122">Därför kan följande kalendrar påverka det förslagna inleveransdatumet: lagerställekalender, transportkalender, leverantörskalender och kundkalender.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-122">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="4ac7d-123">I följande tabell beskrivs respektive metod för leveransdatumkontroll.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-123">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4ac7d-124"><strong>Metod</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-124"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="4ac7d-125"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-125"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4ac7d-126"><strong>None</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-126"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4ac7d-127">Leveransalternativ för försäljningsrader stöds inte.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-127">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="4ac7d-128">Det här alternativet inaktiverar leveransdatumkontroll.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-128">This option turns off delivery date control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4ac7d-129"><strong>Produktionstid för försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-129"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4ac7d-130">Leveransalternativ beräknas utifrån fördefinierad produktionstid för försäljning.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-130">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="4ac7d-131">Transportdagar beräknas baserat på leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-131">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="4ac7d-132">Leveransalternativ inkluderar lagerställen som har lagerbehållning och tillgång-/efterfrågeorder.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-132">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4ac7d-133"><strong>ATP</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-133"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4ac7d-134">Leveransalternativ beräknas utifrån logiken disponibelt att lova (ATP).</span><span class="sxs-lookup"><span data-stu-id="4ac7d-134">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="4ac7d-135">Aktuell tillgänglighet och förväntad framtida tillgänglighet kan användas.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-135">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="4ac7d-136">Transportdagar beräknas baserat på leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-136">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="4ac7d-137">Leveransalternativ inkluderar lagerställen som har lagerbehållning och tillgång-/efterfrågeorder.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-137">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4ac7d-138"><strong>ATP + utleveransmarginal</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-138"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4ac7d-139">Leveransalternativ för beräknas för ATP-metoden men utleveransmarginalen tas med i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-139">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4ac7d-140"><strong>CTP</strong></span><span class="sxs-lookup"><span data-stu-id="4ac7d-140"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4ac7d-141">Leveransalternativ beräknas utifrån logiken capable to promise (CTP).</span><span class="sxs-lookup"><span data-stu-id="4ac7d-141">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="4ac7d-142">MPS-nedbrytningen används för att bestämma tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-142">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="4ac7d-143">Observera att CTP åtminstone förskjuter leveransdatum till produktionstiden för försäljning.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-143">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="4ac7d-144">Transportdagar beräknas baserat på leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-144">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="4ac7d-145">Leveransalternativ inkluderar förslag för följande lagerställen:</span><span class="sxs-lookup"><span data-stu-id="4ac7d-145">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="4ac7d-146">Aktuellt lagerställe</span><span class="sxs-lookup"><span data-stu-id="4ac7d-146">Current warehouse</span></span></li>
<li><span data-ttu-id="4ac7d-147">Standardlagerställe</span><span class="sxs-lookup"><span data-stu-id="4ac7d-147">Default warehouse</span></span></li>
<li><span data-ttu-id="4ac7d-148">Alla lagerställen som har tillgänglig lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="4ac7d-148">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="4ac7d-149">Alla lagerställen som har leveransorder</span><span class="sxs-lookup"><span data-stu-id="4ac7d-149">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="4ac7d-150">Alla lagerställen som har aktiva strukturlisteversioner</span><span class="sxs-lookup"><span data-stu-id="4ac7d-150">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="4ac7d-151">Visa information om leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4ac7d-151">View information about delivery alternatives</span></span>

<span data-ttu-id="4ac7d-152">Det här avsnittet innehåller information om leveransalternativ som finns på alla snabbflikar på sidan **leveransalternativ**.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-152">This section describes the information about delivery alternatives that is available on each FastTab of the **Delivery alternatives** page.</span></span>

### <a name="the-product-fasttab"></a><span data-ttu-id="4ac7d-153">Snabbfliken produkt</span><span class="sxs-lookup"><span data-stu-id="4ac7d-153">The Product FastTab</span></span>

<span data-ttu-id="4ac7d-154">Den här snabbfliken visar en sammanfattning av produkten och information om den aktuella försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-154">This FastTab shows a summary of the product and details of the current sales line.</span></span>

### <a name="the-delivery-alternatives-fasttab"></a><span data-ttu-id="4ac7d-155">Snabbfliken leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4ac7d-155">The Delivery alternatives FastTab</span></span>

<span data-ttu-id="4ac7d-156">Den här snabbfliken visar en lista med leveransalternativ som sorteras efter inleveransdatum.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-156">This FastTab shows a list of delivery alternatives that is sorted by receipt date.</span></span> <span data-ttu-id="4ac7d-157">Du kan välja vilka alternativ som du vill basera förslagen på ovanför listan.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-157">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="4ac7d-158">Du kan också välja leveranssätt som bestämmer transportdagar.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-158">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="4ac7d-159">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4ac7d-159">The following options are available:</span></span>

- <span data-ttu-id="4ac7d-160">**Inkludera andra produktvarianter** - det här alternativet är tillgängligt för produkter som har produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-160">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="4ac7d-161">Det innehåller leveransalternativ till andra varianter av produkten.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-161">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="4ac7d-162">Det här alternativet är inte tillgängligt för CTP.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-162">This option isn't available for CTP.</span></span>
- <span data-ttu-id="4ac7d-163">**Inkludera delkvantitet** - som standard inkluderas endast förslag som uppfyller hela kvantiteten på försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-163">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="4ac7d-164">Välj detta alternativ om du vill inkludera förslag som bara delvis uppfyller orderraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-164">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="4ac7d-165">Det här alternativet är användbart när kunden begär ett tidigare leveransdatum och tar emot en delleverans.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-165">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
- <span data-ttu-id="4ac7d-166">**Inkludera senare datum** - Som standard visas endast förslag som passar bättre (tidigare) än aktuellt datum på försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-166">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="4ac7d-167">Välj det här alternativet om du vill inkludera senare datum.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-167">Select this option to include later dates.</span></span> <span data-ttu-id="4ac7d-168">Det här alternativet kan vara användbart i situationer där andra parametrar än datumet har prioritet.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-168">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="4ac7d-169">En viss leverantör eller lagerställe kan exempelvis prioriteras.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-169">For example, a specific vendor or warehouse might be preferred.</span></span>
- <span data-ttu-id="4ac7d-170">**Leveranssätt** - Välj föredraget leveranssätt för att optimera transporttiden och kostnader.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-170">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="4ac7d-171">Du kommer ommedelbart att se effekten av föreslagna leveransalternativ.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-171">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="4ac7d-172">Därför är det enkelt att jämföra alternativen.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-172">Therefore, it's easy to compare the alternatives.</span></span>
- <span data-ttu-id="4ac7d-173">**Inkludera anskaffning** - när upphandling väljs föreslagna leverans alternativ innehåller alternativ för att anskaffa både från externa leverantörer och andra företag inom företaget (koncernintern).</span><span class="sxs-lookup"><span data-stu-id="4ac7d-173">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="4ac7d-174">Alternativet **Inkludera anskaffning** stöds för för ATP och ATP + leveransdatumkontroll för utleveransmarginal.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-174">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="4ac7d-175">Anskaffningsalternativ från standardinköpsleverantören för produkten och alla godkända leverantörer för produkten ingår.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-175">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
- <span data-ttu-id="4ac7d-176">Beräkningen baseras på inköpsproduktionstiden för externa leverantörer.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-176">For external vendors, the calculation is based on the purchase lead time.</span></span>
- <span data-ttu-id="4ac7d-177">För koncerninterna beaktar beräkningen vad som finns tillgängligt från källföretaget utifrån leveransdatumkontroll i företaget källa.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-177">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
- <span data-ttu-id="4ac7d-178">**Leveranstypen** (relevant för inköp)</span><span class="sxs-lookup"><span data-stu-id="4ac7d-178">**Delivery type** (Relevant for procurement)</span></span>
  - <span data-ttu-id="4ac7d-179">**Lager** - produkter levereras från lagerkälla till plats/lagerstället på försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-179">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="4ac7d-180">De har levererats från detta lagerställe till kunden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-180">They are then shipped from that warehouse to the customer.</span></span>
  - <span data-ttu-id="4ac7d-181">**Direktleverans** - produkter levereras direkt från lagerställets källa till kunden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-181">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="the-availability-information-fasttab"></a><span data-ttu-id="4ac7d-182">Snabbfliken Tillgänglighetsinformation</span><span class="sxs-lookup"><span data-stu-id="4ac7d-182">The Availability information FastTab</span></span>

<span data-ttu-id="4ac7d-183">Information om denna snabbflik som rör den valda leveransalternativraden.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-183">Information on this FastTab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="4ac7d-184">Följande information visas beroende på Leveransdatumkontroll för försäljningsraden:</span><span class="sxs-lookup"><span data-stu-id="4ac7d-184">The following information is shown, depending on the delivery date control for the sales line:</span></span>

- <span data-ttu-id="4ac7d-185">**Produktionstid för försäljning**</span><span class="sxs-lookup"><span data-stu-id="4ac7d-185">**Sales lead time**</span></span>
  - <span data-ttu-id="4ac7d-186">**Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-186">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="4ac7d-187">**Parametrar** - visar lagerenhet och produktionstid för försäljning.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-187">**Parameters** - Show the inventory unit and sales lead time.</span></span>

- <span data-ttu-id="4ac7d-188">**ATP and ATP + Utleveransmarginal**</span><span class="sxs-lookup"><span data-stu-id="4ac7d-188">**ATP and ATP + Issue margin**</span></span>
  - <span data-ttu-id="4ac7d-189">**Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-189">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="4ac7d-190">**Parametrar** - visar lagerenhet och produktionstid för försäljning.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-190">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="4ac7d-191">**Framtida tillgänglighet** – visar en grafisk representation av nuvarande och framtida tillgänglighet för den valda siten och lagerstället **alternativ leverans**.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-191">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="4ac7d-192">Om du klickar på kolumnerna i diagrammet får du mer detaljerad information om produktens framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-192">You can select the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="4ac7d-193">Bilden visar en lista över relevanta efterfråge- och leveransorder inom tidsgränsen för ATP.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-193">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

- <span data-ttu-id="4ac7d-194">**CTP**</span><span class="sxs-lookup"><span data-stu-id="4ac7d-194">**CTP**</span></span>
  - <span data-ttu-id="4ac7d-195">**Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-195">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="4ac7d-196">**Parametrar** - visar lagerenhet och produktionstid för försäljning.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-196">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="4ac7d-197">**Nedbrytning** - visar leveransnedbrytning av den valda leveransen.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-197">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="4ac7d-198">Du kan använda **inställningar** för att ändra fälten och lagerdimensioner som ska visas i nedbrytningen.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-198">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="the-impact-of-selected-alternative-fasttab"></a><span data-ttu-id="4ac7d-199">Snabbfliken Effekten av valt alternativ</span><span class="sxs-lookup"><span data-stu-id="4ac7d-199">The Impact of selected alternative FastTab</span></span>

<span data-ttu-id="4ac7d-200">Den här snabbfliken markerar effekten av valt alternativ.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-200">This FastTab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="4ac7d-201">Om du klickar på **OK**, uppdateras försäljningsraden med de markerade värdena i markerade kolumner.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-201">If you select **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="4ac7d-202">Observera att, om kvantiteten på valt alternativ är mindre än kvantiteten på försäljningsraden har en leveransplan skapats och orderraden delas upp på två rader: en rad för den valda kvantiteten och en rad för den återstående kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-202">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="4ac7d-203">Du kan också uppdatera den kommersiella raden så att den matchar planens rader och påverkar priserna.</span><span class="sxs-lookup"><span data-stu-id="4ac7d-203">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ac7d-204">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4ac7d-204">Additional resources</span></span>

[<span data-ttu-id="4ac7d-205">Orderlöfte</span><span class="sxs-lookup"><span data-stu-id="4ac7d-205">Order promising</span></span>](delivery-dates-available-promise-calculations.md)
