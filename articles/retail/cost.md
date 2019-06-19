---
title: Kostnadskonfiguration för fördelad orderhantering (DOM)
description: I detta avsnitt beskrivs kostnadskonfigurationen för fördelad orderhantering (DOM) i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 80e7a033467c3d94d55f06daa05f99bd27e19a29
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606789"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="e4178-103">Kostnadskonfiguration för fördelad orderhantering (DOM)</span><span class="sxs-lookup"><span data-stu-id="e4178-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4178-104">Organisationer tar med flera kostnadskomponenter i beräkningen för att avgöra vilken plats som är bäst att uppfylla ordern från.</span><span class="sxs-lookup"><span data-stu-id="e4178-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="e4178-105">Några av dessa kostnadskomponenter är leveranskostnad, hanteringskostnad och förpackningskostnad.</span><span class="sxs-lookup"><span data-stu-id="e4178-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="e4178-106">Genom en kombination av dessa kostnader beräknas vilken plats som ska användas för uppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="e4178-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="e4178-107">När den första iterationen av fördelad orderhantering (DOM) i Microsoft Dynamics 365 for Retail optimerade tilldelningen av order för uppfyllelseplatser togs bara avståndet in i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="e4178-107">When the first iteration of distributed order management (DOM) in Microsoft Dynamics 365 for Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="e4178-108">Även om avståndet kan korreleras mot kostnad, är det inte detsamma som kostnad.</span><span class="sxs-lookup"><span data-stu-id="e4178-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="e4178-109">En leverans till nästa dag natten kostar till exempel mer än en tredagarsleverans eller sjudagarsleverans med samma avstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="e4178-110">Med funktionen för kostnadskonfiguration kan återförsäljare definiera och konfigurera ytterligare kostnadskomponenter som ska beräknas och tas hänsyn till när den bästa platsen att uppfylla orderrader fastställs.</span><span class="sxs-lookup"><span data-stu-id="e4178-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="e4178-111">När kostnadskomponenter konfigureras använder DOM-problemlösaren bara dessa kostnadsdefinitioner för att avgöra den bästa platsen för orderuppfyllande.</span><span class="sxs-lookup"><span data-stu-id="e4178-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="e4178-112">Den tar inte hänsyn till avståndskomponenten som kostnad.</span><span class="sxs-lookup"><span data-stu-id="e4178-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="e4178-113">Men om inga kostnadskomponenter har konfigurerats använder inte DOM-problemlösaren avståndskomponenten som en kostnad för att avgöra den bästa platsen för orderuppfyllande.</span><span class="sxs-lookup"><span data-stu-id="e4178-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="e4178-114">Konfigurera kostnadskomponenter</span><span class="sxs-lookup"><span data-stu-id="e4178-114">Set up cost components</span></span>

<span data-ttu-id="e4178-115">Du kan definiera två huvudsakliga typer av kostnadskomponenter i systemet: **Leverans** och **Övrigt**.</span><span class="sxs-lookup"><span data-stu-id="e4178-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="e4178-116">Det går att använda flera beräkningsbaser för båda typerna av kostnadskomponenter, vilket visas i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="e4178-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e4178-117">Typ av kostnadskomponent</span><span class="sxs-lookup"><span data-stu-id="e4178-117">Cost component type</span></span></th>
<th><span data-ttu-id="e4178-118">Beräkningsbas</span><span class="sxs-lookup"><span data-stu-id="e4178-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e4178-119">Leverans</span><span class="sxs-lookup"><span data-stu-id="e4178-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e4178-120">Enkel</span><span class="sxs-lookup"><span data-stu-id="e4178-120">Simple</span></span></li>
<li><span data-ttu-id="e4178-121">Nivåindelad</span><span class="sxs-lookup"><span data-stu-id="e4178-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="e4178-122">Övrigt</span><span class="sxs-lookup"><span data-stu-id="e4178-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e4178-123">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="e4178-123">Sales order</span></span></li>
<li><span data-ttu-id="e4178-124">Försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="e4178-124">Sales line</span></span></li>
<li><span data-ttu-id="e4178-125">Plats</span><span class="sxs-lookup"><span data-stu-id="e4178-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="e4178-126">Kostnadskomponenttypen Leverans</span><span class="sxs-lookup"><span data-stu-id="e4178-126">Shipping cost component type</span></span>

<span data-ttu-id="e4178-127">Det här avsnittet innehåller information om hur du konfigurerar varje kombination av kostnadskomponenttypen **Leverans** och beräkningsbasen för leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="e4178-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="e4178-128">Det innehåller också information om hur DOM-problemlösaren använder olika kombinationer.</span><span class="sxs-lookup"><span data-stu-id="e4178-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="e4178-129">Kostnadskomponenttyp = Leverans och beräkningsbas = Enkel</span><span class="sxs-lookup"><span data-stu-id="e4178-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="e4178-130">Om en kombination kostnadskomponenttypen **Leverans** och beräkningsbasen **Enkel** används, baseras leveranskostnaden för ett leveranssätt antingen på en fast kostnad eller ett avstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="e4178-131">Du måste ställa in följande fält för den här kombinationen:</span><span class="sxs-lookup"><span data-stu-id="e4178-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e4178-132">**Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e4178-133">**Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e4178-134">**Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4178-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e4178-135">Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.</span><span class="sxs-lookup"><span data-stu-id="e4178-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e4178-136">**Aktiv** – Ange om kostnadsfaktorn är aktiv.</span><span class="sxs-lookup"><span data-stu-id="e4178-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e4178-137">DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.</span><span class="sxs-lookup"><span data-stu-id="e4178-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e4178-138">**Företag** – Ange den juridiska person som kostnadsfaktorn har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="e4178-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="e4178-139">Alla rader i beräkningskriterierna måste gälla för samma juridiska person.</span><span class="sxs-lookup"><span data-stu-id="e4178-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="e4178-140">**Leveranssätt** – Ange de leveranssätt som kostnaden har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="e4178-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="e4178-141">**Beräkningstyp** – Ange hur kostnaden ska beräknas för ett specifikt leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="e4178-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="e4178-142">Det går att använda två beräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="e4178-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="e4178-143">**Fast** – En fast kostnad används för leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="e4178-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="e4178-144">Om du väljer den här beräkningstypen definieras den fasta kostnaden med fältet **Kostnad**.</span><span class="sxs-lookup"><span data-stu-id="e4178-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="e4178-145">**Enhet för avstånd** – Kostnaden för leveranssättet beräknas som kostnadsvärdet som anges i fältet **Kostnad** multiplicerat med avståndet mellan leveransadressen och platserna.</span><span class="sxs-lookup"><span data-stu-id="e4178-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="e4178-146">**Kostnad** – Ange det kostnadsvärde som används tillsammans med fältet **Beräkningstyp** för att beräkna kostnaden för ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="e4178-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="e4178-147">Kostnadskomponenttyp = Leverans och beräkningsbas = Nivåindelad</span><span class="sxs-lookup"><span data-stu-id="e4178-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="e4178-148">Om en kombination kostnadskomponenttypen **Leverans** och beräkningsbasen **Nivåindelad** används, baseras leveranskostnaden för ett leveranssätt antingen på en fast kostnad eller ett avstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="e4178-149">I den här kombinationen baseras avståndet på ett nivåindelat intervall med avstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="e4178-150">Du måste ställa in följande fält för den här kombinationen:</span><span class="sxs-lookup"><span data-stu-id="e4178-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e4178-151">**Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e4178-152">**Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e4178-153">**Standardkostnad** – Ange den kostnad som ska användas för ett leveranssätt om avståndet mellan leveransadressen och platsen inte ligger inom något av de nivåindelade avstånden för leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="e4178-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="e4178-154">**Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4178-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e4178-155">Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.</span><span class="sxs-lookup"><span data-stu-id="e4178-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e4178-156">**Aktiv** – Ange om kostnadsfaktorn är aktiv.</span><span class="sxs-lookup"><span data-stu-id="e4178-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e4178-157">DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.</span><span class="sxs-lookup"><span data-stu-id="e4178-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e4178-158">**Företag** – Ange den juridiska person som kostnadsfaktorn har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="e4178-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="e4178-159">Alla rader i beräkningskriterierna måste gälla för samma juridiska person.</span><span class="sxs-lookup"><span data-stu-id="e4178-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="e4178-160">**Leveranssätt** – Ange de leveranssätt som kostnaden har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="e4178-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="e4178-161">**Avståndstyp** – Ange om den nivåindelade avståndsdefinitionen är ett avstånd fågelvägen eller ett vägavstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="e4178-162">**Avståndsenheter** – Ange enheten som det nivåindelade avståndet mäts i.</span><span class="sxs-lookup"><span data-stu-id="e4178-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="e4178-163">**Avstånd från** – Ange startintervallet för det nivåindelade avståndet.</span><span class="sxs-lookup"><span data-stu-id="e4178-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="e4178-164">**Avstånd till** – Ange slutintervallet för det nivåindelade avståndet.</span><span class="sxs-lookup"><span data-stu-id="e4178-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="e4178-165">**Beräkningstyp** – Ange hur kostnaden ska beräknas för ett specifikt leveranssätt och det nivåindelade avståndet.</span><span class="sxs-lookup"><span data-stu-id="e4178-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="e4178-166">Det går att använda två beräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="e4178-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="e4178-167">**Fast** – En fast kostnad används för leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="e4178-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="e4178-168">Om du väljer den här beräkningstypen definieras den fasta kostnaden med fältet **Kostnad**.</span><span class="sxs-lookup"><span data-stu-id="e4178-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="e4178-169">**Enhet för avstånd** – Kostnaden för leveranssättet och det nivåindelade avståndet beräknas som kostnadsvärdet som anges i fältet **Kostnad** multiplicerat med avståndet mellan leveransadressen och platserna.</span><span class="sxs-lookup"><span data-stu-id="e4178-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="e4178-170">**Kostnad** – Ange det kostnadsvärde som används tillsammans med fältet **Beräkningstyp** för att beräkna kostnaden för ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="e4178-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="e4178-171">När du definierar nivåindelade avstånd kontrollerar systemet att inga avstånd saknas eller överlappar.</span><span class="sxs-lookup"><span data-stu-id="e4178-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="e4178-172">Avståndstypen som används för ett leveranssätt måste vara densamma för alla nivåindelade avstånd.</span><span class="sxs-lookup"><span data-stu-id="e4178-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="e4178-173">Kostnadskomponenttypen Övrigt</span><span class="sxs-lookup"><span data-stu-id="e4178-173">Other cost component type</span></span>

<span data-ttu-id="e4178-174">Det här avsnittet innehåller information om hur du konfigurerar varje kombination av kostnadskomponenttypen **Övrigt** och en annan kostnadstyp för kostnader som inte är leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="e4178-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="e4178-175">Det innehåller också information om hur DOM-problemlösaren använder olika kombinationer.</span><span class="sxs-lookup"><span data-stu-id="e4178-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="e4178-176">Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="e4178-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="e4178-177">En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Försäljningsorder** används för att definiera kostnader på försäljningsordernivå som inte är leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="e4178-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="e4178-178">Du måste ställa in följande fält för den här kombinationen:</span><span class="sxs-lookup"><span data-stu-id="e4178-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e4178-179">**Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e4178-180">**Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e4178-181">**Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4178-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e4178-182">Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.</span><span class="sxs-lookup"><span data-stu-id="e4178-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e4178-183">**Aktiv** – Ange om kostnadsfaktorn är aktiv.</span><span class="sxs-lookup"><span data-stu-id="e4178-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e4178-184">DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.</span><span class="sxs-lookup"><span data-stu-id="e4178-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e4178-185">**Kostnad** – Ange kostnadsvärdet för en kostnad på försäljningsordernivå som inte är leveranskostnad.</span><span class="sxs-lookup"><span data-stu-id="e4178-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="e4178-186">Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="e4178-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="e4178-187">En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Försäljningsrad** används för att definiera kostnader på försäljningsorderradnivå som inte är leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="e4178-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="e4178-188">Du måste ställa in följande fält för den här kombinationen:</span><span class="sxs-lookup"><span data-stu-id="e4178-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e4178-189">**Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e4178-190">**Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e4178-191">**Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4178-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e4178-192">Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.</span><span class="sxs-lookup"><span data-stu-id="e4178-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e4178-193">**Aktiv** – Ange om kostnadsfaktorn är aktiv.</span><span class="sxs-lookup"><span data-stu-id="e4178-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e4178-194">DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.</span><span class="sxs-lookup"><span data-stu-id="e4178-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e4178-195">**Kostnad** – Ange kostnadsvärdet för en kostnad på försäljningsorderradnivå som inte är leveranskostnad.</span><span class="sxs-lookup"><span data-stu-id="e4178-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="e4178-196">Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Plats</span><span class="sxs-lookup"><span data-stu-id="e4178-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="e4178-197">En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Plats** används för att definiera kostnader som inte är leveranskostnader för en grupp med platser eller en enskild plats.</span><span class="sxs-lookup"><span data-stu-id="e4178-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="e4178-198">Du måste ställa in följande fält för den här kombinationen:</span><span class="sxs-lookup"><span data-stu-id="e4178-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e4178-199">**Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e4178-200">**Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.</span><span class="sxs-lookup"><span data-stu-id="e4178-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e4178-201">**Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4178-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e4178-202">Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.</span><span class="sxs-lookup"><span data-stu-id="e4178-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e4178-203">**Aktiv** – Ange om kostnadsfaktorn är aktiv.</span><span class="sxs-lookup"><span data-stu-id="e4178-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e4178-204">DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.</span><span class="sxs-lookup"><span data-stu-id="e4178-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e4178-205">**Uppfyllelsegrupp** – Ange den grupp med platser som kostnaden som inte är en leveranskostnad definieras för.</span><span class="sxs-lookup"><span data-stu-id="e4178-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="e4178-206">**Uppfyllelseplats** – Ange den plats som kostnaden som inte är en leveranskostnad definieras för.</span><span class="sxs-lookup"><span data-stu-id="e4178-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4178-207">Du kan inte ange en uppfyllelsegrupp och en uppfyllelseplats på samma rad för platsbaserade beräkningskriterier.</span><span class="sxs-lookup"><span data-stu-id="e4178-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="e4178-208">**Kostnad** – Ange kostnadsvärdet för en kostnad som inte är leveranskostnad på uppfyllelsegruppnivå eller uppfyllelseplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="e4178-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4178-209">Om att DOM ska ta hänsyn till dessa kostnader under körning måste du lägga till kostnadsfaktorn i relevant uppfyllelseprofil.</span><span class="sxs-lookup"><span data-stu-id="e4178-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>
