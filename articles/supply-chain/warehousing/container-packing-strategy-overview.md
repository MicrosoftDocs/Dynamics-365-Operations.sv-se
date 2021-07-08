---
title: Förpackningsstrategier för behållare
description: I det här avsnittet beskrivs skillnaderna mellan förpackningsstrategier för behållare, samt exempel.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292771"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="9a1f9-103">Förpackningsstrategier för behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-103">Container packing strategies</span></span>

<span data-ttu-id="9a1f9-104">En *förpackningsstrategi för behållare* är en strategi som du kan använda för att definiera artikelallokeringar mellan behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="9a1f9-105">I det här avsnittet beskrivs skillnaderna mellan *förpacka i alla öppna behållare* och *förpacka i enbart aktuella behållare*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="9a1f9-106">**Förpacka i alla öppna behållare** – Systemet måste kontrollera alla öppna behållare som redan har skapats under cykeln för skapande av behållare för att säkerställa att artikeln får plats i en av dem.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="9a1f9-107">Under förpackning kontrollerar systemet varje artikel för att avgöra om den får plats i någon av de tidigare skapade behållarna.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="9a1f9-108">Om artikeln inte får plats i en befintlig behållare skapas en ny behållare automatiskt och fortsätter tills den är färdig med att packa hela ordern.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="9a1f9-109">Till exempel, *n* beställda artiklar kräver skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="9a1f9-110">I värsta fall, varje gång systemet behandlar ett objekt som inte passar i någon befintlig behållare, kommer det att göra totalt (\[(*n* – 1) × (*n* + 1)\] ÷ 2) kontrollerar för att utvärdera om artikeln passar in i befintliga behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="9a1f9-111">**Packa endast till aktuell behållare** – Systemet måste endast kontrollera den senast skapade behållaren för att säkerställa att artikeln passar in i den.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="9a1f9-112">Under förpackning kontrollerar systemet varje artikel för att avgöra om den får plats i den senast skapade behållarna.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="9a1f9-113">Om artikeln inte får plats i den behållaren skapar systemet en ny behållare automatiskt och fortsätter tills den är färdig med att packa hela ordern.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="9a1f9-114">Till exempel, *n* beställda artiklar kräver skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="9a1f9-115">I det aktuella fallet görs en total kontroll av artikeln (*n* – 1) för att bedöma om artikeln får plats i behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="9a1f9-116">Exempel på flödet för förpackningsstrategier för behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="9a1f9-117">Du kan konfigurera följande artiklar för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="9a1f9-118">Artikel</span><span class="sxs-lookup"><span data-stu-id="9a1f9-118">Item</span></span> | <span data-ttu-id="9a1f9-119">Fysiska dimensioner (bredd × djup × höjd)</span><span class="sxs-lookup"><span data-stu-id="9a1f9-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="9a1f9-120">Vikt</span><span class="sxs-lookup"><span data-stu-id="9a1f9-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="9a1f9-121">HDMI-kabel 6'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-121">HDMI Cable 6'</span></span> | <span data-ttu-id="9a1f9-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-122">1 × 1 × 1</span></span> | <span data-ttu-id="9a1f9-123">1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-123">1</span></span> |
| <span data-ttu-id="9a1f9-124">HDMI-kabel 12'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-124">HDMI Cable 12'</span></span> | <span data-ttu-id="9a1f9-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-125">2 × 1 × 1</span></span> | <span data-ttu-id="9a1f9-126">1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-126">1</span></span> |
| <span data-ttu-id="9a1f9-127">HDMI-kabel 18'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-127">HDMI Cable 18'</span></span> | <span data-ttu-id="9a1f9-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-128">3 × 1 × 1</span></span> | <span data-ttu-id="9a1f9-129">2</span><span class="sxs-lookup"><span data-stu-id="9a1f9-129">2</span></span> |

<span data-ttu-id="9a1f9-130">Du kan även ställa in följande låda som ska användas för förpackning.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="9a1f9-131">Behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-131">Container</span></span> | <span data-ttu-id="9a1f9-132">Fysiska dimensioner (längd × bredd × höjd)</span><span class="sxs-lookup"><span data-stu-id="9a1f9-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="9a1f9-133">Vikt</span><span class="sxs-lookup"><span data-stu-id="9a1f9-133">Weight</span></span> | <span data-ttu-id="9a1f9-134">Volym</span><span class="sxs-lookup"><span data-stu-id="9a1f9-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="9a1f9-135">Mellanlåda</span><span class="sxs-lookup"><span data-stu-id="9a1f9-135">Medium Box</span></span> | <span data-ttu-id="9a1f9-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="9a1f9-136">6 × 3 × 2</span></span> | <span data-ttu-id="9a1f9-137">10</span><span class="sxs-lookup"><span data-stu-id="9a1f9-137">10</span></span> | <span data-ttu-id="9a1f9-138">100</span><span class="sxs-lookup"><span data-stu-id="9a1f9-138">100</span></span> |

<span data-ttu-id="9a1f9-139">Slutligen ställer du in en order med följande produkter och kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="9a1f9-140">Försäljningsorderrad</span><span class="sxs-lookup"><span data-stu-id="9a1f9-140">Sales order line</span></span> | <span data-ttu-id="9a1f9-141">Antal</span><span class="sxs-lookup"><span data-stu-id="9a1f9-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="9a1f9-142">HDMI-kabel 12'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-142">HDMI Cable 12'</span></span> | <span data-ttu-id="9a1f9-143">9</span><span class="sxs-lookup"><span data-stu-id="9a1f9-143">9</span></span> |
| <span data-ttu-id="9a1f9-144">HDMI-kabel 18'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-144">HDMI Cable 18'</span></span> | <span data-ttu-id="9a1f9-145">8</span><span class="sxs-lookup"><span data-stu-id="9a1f9-145">8</span></span> |
| <span data-ttu-id="9a1f9-146">HDMI-kabel 6'</span><span class="sxs-lookup"><span data-stu-id="9a1f9-146">HDMI Cable 6'</span></span> | <span data-ttu-id="9a1f9-147">13</span><span class="sxs-lookup"><span data-stu-id="9a1f9-147">13</span></span> |

<span data-ttu-id="9a1f9-148">I följande tabell sammanfattas hur skapande av behållare fungerar när du använder *förpacka i alla öppna behållare* och när du använder strategin *förpacka endast i aktuell behållare*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="9a1f9-149">Packa i alla öppna behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-149">Pack into all open containers</span></span> | <span data-ttu-id="9a1f9-150">Packa i aktuell behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="9a1f9-151">HDMI-kabel 12':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="9a1f9-152">Skapa en ny behållare CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-153">Sätt 9 ea i behållare CONT001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="9a1f9-154">HDMI-kabel 12':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="9a1f9-155">Skapa en ny behållare CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-156">Sätt 9 ea i behållare CONT001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="9a1f9-157">HDMI-kabel 18':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="9a1f9-158">Kontrollera om artikeln får plats i behållaren CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-159">Skapa en ny behållare CONT0002.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="9a1f9-160">Sätt 5 ea i behållare CONT0002.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="9a1f9-161">Skapa en ny behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-162">Sätt 3 ea i behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="9a1f9-163">HDMI-kabel 18':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="9a1f9-164">Kontrollera om artikeln får plats i behållaren CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-165">Skapa en ny behållare CONT0002.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="9a1f9-166">Sätt 5 ea i behållare CONT0002.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="9a1f9-167">Skapa en ny behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-168">Sätt 3 ea i behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="9a1f9-169">HDMI-kabel 6':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="9a1f9-170">Kontrollera om artikeln får plats i behållaren CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-171">Sätt 1 ea i behållare CONT0001.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="9a1f9-172">Kontrollera om artikeln får plats i behållaren CONT0002.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="9a1f9-173">Kontrollera om artikeln får plats i behållaren CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-174">Sätt 4 ea i behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-175">Skapa en ny behållare CONT0004.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="9a1f9-176">Sätt 8 ea i behållare CONT0004.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="9a1f9-177">HDMI-kabel 6':</span><span class="sxs-lookup"><span data-stu-id="9a1f9-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="9a1f9-178">Kontrollera om artikeln får plats i behållaren CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-179">Sätt 4 ea i behållare CONT0003.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="9a1f9-180">Skapa en ny behållare CONT0004.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="9a1f9-181">Sätt 9 ea i behållare CONT0004.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="9a1f9-182">Exempelscenario: Packa enstaka order per behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="9a1f9-183">Det här avsnittet innehåller ett scenario där systemet har ställts in för konsolidering av flera order till en försändelse.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="9a1f9-184">Därför sker skapande av behållare från försäljningsordern för att säkerställa att varje order som innehåller flera produkter förpackas i en egen behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="9a1f9-185">Med den här funktionen kan du hantera scenarier där du bara får packa en försäljningsorder i varje behållare, så att distributionscentret kan direktutlevera fullständiga behållare mellan butiker.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="9a1f9-186">Förutom butiksscenarier (order per butik och leverans till ett distributionscenter för direktutleverans) används den här metoden också för resurssnåla leveranskedjor (försäljningsorder per just-in-time-produktionsrad).</span><span class="sxs-lookup"><span data-stu-id="9a1f9-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="9a1f9-187">I det här scenariot visas hur du kan minska antalet behållare som utvärderas under förpackning med hjälp av *Förpacka endast i aktuell behållare* bara för att skapa behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9a1f9-188">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9a1f9-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="9a1f9-189">Aktivera funktionen Konsolidera försändelser i systemet</span><span class="sxs-lookup"><span data-stu-id="9a1f9-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="9a1f9-190">I det här scenariot används funktionen *Konsolidera försändelser*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="9a1f9-191">Om den funktionen inte redan är tillgänglig i systemet måste du aktivera den med hjälp av [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a1f9-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="9a1f9-192">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="9a1f9-192">Make demo data available</span></span>

<span data-ttu-id="9a1f9-193">Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="9a1f9-194">Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="9a1f9-195">Inspektera eller skapa behållartyper</span><span class="sxs-lookup"><span data-stu-id="9a1f9-195">Inspect or create container types</span></span>

<span data-ttu-id="9a1f9-196">Om du vill inspektera dina behållartyper, eller om du behöver skapa nya behållartyper, följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-197">Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållartyper**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="9a1f9-198">Se till att var och en av följande behållartyper är tillgänglig i dina demodata.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="9a1f9-199">Redigera eller skapa behållartyper efter behov.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="9a1f9-200">Behållartyp 1:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-200">Container type 1:</span></span>

        - <span data-ttu-id="9a1f9-201">**Behållartypkod:** *Kartong-stor*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="9a1f9-202">**Beskrivning:** *Stor kartong*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="9a1f9-203">**Högsta nettovikt:** *100*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="9a1f9-204">**Volym:** *400*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="9a1f9-205">**Längd:** *4*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-205">**Length:** *4*</span></span>
        - <span data-ttu-id="9a1f9-206">**Bredd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-206">**Width:** *10*</span></span>
        - <span data-ttu-id="9a1f9-207">**Höjd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-207">**Height:** *10*</span></span>

    - <span data-ttu-id="9a1f9-208">Behållartyp 2:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-208">Container type 2:</span></span>

        - <span data-ttu-id="9a1f9-209">**Behållartypkod:** *Kartong-Medel*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="9a1f9-210">**Beskrivning:** *Medelstor kartong*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="9a1f9-211">**Högsta nettovikt:** *50*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="9a1f9-212">**Volym:** *200*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="9a1f9-213">**Längd:** *2*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-213">**Length:** *2*</span></span>
        - <span data-ttu-id="9a1f9-214">**Bredd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-214">**Width:** *10*</span></span>
        - <span data-ttu-id="9a1f9-215">**Höjd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-215">**Height:** *10*</span></span>

    - <span data-ttu-id="9a1f9-216">Behållartyp 3:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-216">Container type 3:</span></span>

        - <span data-ttu-id="9a1f9-217">**Behållartypkod:** *Kartong-liten*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="9a1f9-218">**Beskrivning:** *Liten kartong*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="9a1f9-219">**Högsta nettovikt:** *20*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="9a1f9-220">**Volym:** *100*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="9a1f9-221">**Längd:** *1*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-221">**Length:** *1*</span></span>
        - <span data-ttu-id="9a1f9-222">**Bredd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-222">**Width:** *10*</span></span>
        - <span data-ttu-id="9a1f9-223">**Höjd:** *10*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="9a1f9-224">Inspektera eller skapa behållargrupper</span><span class="sxs-lookup"><span data-stu-id="9a1f9-224">Inspect or create container groups</span></span>

<span data-ttu-id="9a1f9-225">Om du vill inspektera dina behållargrupper, eller om du behöver skapa nya behållargrupper, följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-226">Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållargrupper**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="9a1f9-227">Se till att var och en av följande behållargrupper är tillgänglig i dina demodata.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="9a1f9-228">Om den inte är tillgänglig väljer du **Ny** för att skapa den.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="9a1f9-229">**Behållargrupp-ID:** *kartonger*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="9a1f9-230">**Beskrivning:** *Kartongstorlekar*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="9a1f9-231">I snabbfliken **Detaljer** för behållargrupp *Lådor* se till att följande rader finns.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="9a1f9-232">Om de inte har det markerar du **Ny** om du vill lägga till dem.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="9a1f9-233">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-233">Line 1:</span></span>

        - <span data-ttu-id="9a1f9-234">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="9a1f9-235">**Behållartyp:** *Kartong-stor*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="9a1f9-236">**Utnyttjandegrad för fraktbehållare:** *100*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="9a1f9-237">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-237">Line 2:</span></span>

        - <span data-ttu-id="9a1f9-238">**Löpnummer:** *2*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="9a1f9-239">**Behållartyp:** *Kartong-Medel*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="9a1f9-240">**Utnyttjandegrad för fraktbehållare:** *100*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="9a1f9-241">Rad 3:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-241">Line 3:</span></span>

        - <span data-ttu-id="9a1f9-242">**Löpnummer:** *3*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="9a1f9-243">**Behållartyp:** *Kartong-liten*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="9a1f9-244">**Utnyttjandegrad för fraktbehållare:** *100*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="9a1f9-245">Skapa en ny behållarversionsmall</span><span class="sxs-lookup"><span data-stu-id="9a1f9-245">Create a new container build template</span></span>

<span data-ttu-id="9a1f9-246">Så här skapar du en ny behållarversionsmall:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-247">Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Mall för behållarversion**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="9a1f9-248">Välj **Ny** om du vill skapa en behållarversionsmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="9a1f9-249">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="9a1f9-250">**ID för behållarmall:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="9a1f9-251">**Behållargrupp-ID:** *kartonger*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="9a1f9-252">**Basfrågetyper:** *Försäljningsallokeringsrad*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="9a1f9-253">**Kod för påfyllnadssteg:** *234*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="9a1f9-254">**Tillåt delade plockningar:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="9a1f9-255">**Förpackningsstrategi för behållare:** *Packa endast i aktuell behållare*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="9a1f9-256">**Packa efter direktivenhet:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="9a1f9-257">Medan raden för den nya mallen fortfarande är markerad väljer du **Redigera från** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="9a1f9-258">En dialogruta för standard frågeredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="9a1f9-259">På fliken **Sortera**, välj **Lägg till** en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="9a1f9-260">**Tabell:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="9a1f9-261">**Härlett register:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="9a1f9-262">**Fält:** *Ordernummer*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="9a1f9-263">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9a1f9-264">Om du vill undvika att behandla alla andra öppna behållare och påskynda processen genom att kontrollera en behållare i taget kan du bara använda *förpacka i aktuell behållare* förutom att sortera efter ordernummer.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="9a1f9-265">Den här kombinationen fungerar som en arbetsbrytning i en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="9a1f9-266">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="9a1f9-267">Medan raden för den nya mallen fortfarande är markerad väljer du **Blandade begränsningar för behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="9a1f9-268">Du lägger nu till en begränsning som placerar artiklar från en enskild order i en enda behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="9a1f9-269">Artiklar från alla andra order kommer att förvaras i en separat behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="9a1f9-270">Välj **Ny** om du vill skapa en blandad begränsning med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="9a1f9-271">**Register:** *Försäljningsorder*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="9a1f9-272">**Fält markeras:** *SalesId* (Fältet visas som *Försäljningsorder* i rutnätet.)</span><span class="sxs-lookup"><span data-stu-id="9a1f9-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="9a1f9-273">Välj **OK** för att lägga till begränsning.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="9a1f9-274">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="9a1f9-275">Ställa in en påfyllnadsmall för skapande av behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="9a1f9-276">Så här ställer du in en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-277">Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="9a1f9-278">I listruta ange fältet **Malltyp för påfyllnad** till *Leverans*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="9a1f9-279">Välj mallen **63 skapa behållare** i listan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="9a1f9-280">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9a1f9-281">På snabbfliken **Metoder** i kolumnen **Valda metoder** hittar du följande rad:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="9a1f9-282">**Metodnamn:** *skapande av behållare*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="9a1f9-283">**Namn:** *skapande av behållare*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="9a1f9-284">Ställ in fältet **Kod för påfyllnadssteg** för den här raden till *234*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="9a1f9-285">Ställ in en arbetsmall</span><span class="sxs-lookup"><span data-stu-id="9a1f9-285">Set up a work template</span></span>

<span data-ttu-id="9a1f9-286">Så här ställer du in en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-287">Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="9a1f9-288">Ställ in fältet **Arbetsordertyp** till *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="9a1f9-289">I rutnätet **Översikt** välj arbetsmallen som ska användas för packning av enstaka beställningar per behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="9a1f9-290">För detta scenario, välj mallen **63 välj till behållare**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="9a1f9-291">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="9a1f9-292">En dialogruta för standard frågeredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="9a1f9-293">Ange något av följande rader på fliken **Sortering**:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="9a1f9-294">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-294">Line 1:</span></span>

        - <span data-ttu-id="9a1f9-295">**Tabell:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-296">**Härlett register:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-297">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="9a1f9-298">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="9a1f9-299">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-299">Line 2:</span></span>

        - <span data-ttu-id="9a1f9-300">**Tabell:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-301">**Härlett register:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-302">**Fält:** *Ordernummer*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="9a1f9-303">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="9a1f9-304">Rad 3:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-304">Line 3:</span></span>

        - <span data-ttu-id="9a1f9-305">**Tabell:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-306">**Härlett register:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="9a1f9-307">**Fält:** *Behållar-ID*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="9a1f9-308">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="9a1f9-309">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="9a1f9-310">Följande meddelande kan visas: "gruppering återställs, fortsätt?"</span><span class="sxs-lookup"><span data-stu-id="9a1f9-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="9a1f9-311">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="9a1f9-312">När mallen **63 välj till behållare** fortfarande är markerad, välj **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="9a1f9-313">Du använder nu inställningar för att bryta arbetet så att varje behållare i ordern kopplas till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="9a1f9-314">Markera kryssrutan **Gruppera efter det här fältet** för varje rad på sidan **Avbrott i arbetshuvud** (**Leverans-ID**, **Ordernummer** och **Behållar-ID**).</span><span class="sxs-lookup"><span data-stu-id="9a1f9-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="9a1f9-315">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="9a1f9-316">Ange policyer för leveranskonsolidering</span><span class="sxs-lookup"><span data-stu-id="9a1f9-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="9a1f9-317">Så här ställer du in en konsolideringspolicy för leveranser.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-318">Gå till **Warehouse managements \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="9a1f9-319">I listfönstret, ange **Policytyp** i fältet till *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="9a1f9-320">Välj **Standard** policy i listan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="9a1f9-321">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9a1f9-322">På snabbfliken **Konsolideringsfält**, i listan **Valda fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Ordernummer*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="9a1f9-323">Välj knappen **Ta bort** ![Vänsterpil](media/backward-button.png) om du vill flytta fältet till listan **Resterande fält**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="9a1f9-324">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="9a1f9-325">Ställ in fysiska produktdimensioner för produkten</span><span class="sxs-lookup"><span data-stu-id="9a1f9-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="9a1f9-326">Ställ in fysiska dimensioner för de produkter som ska användas i det här scenariot genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-327">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="9a1f9-328">Välj produkten där fältet **Artikelnummer** är inställt på *A0001*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="9a1f9-329">I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="9a1f9-330">På sidan **Fysiska dimensioner** bör du se följande rad i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="9a1f9-331">**Enhet:** *st*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="9a1f9-332">**Bruttovikt:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="9a1f9-333">**Bredd:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="9a1f9-334">**Djup:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="9a1f9-335">**Höjd:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="9a1f9-336">**Volym:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="9a1f9-337">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-337">Close the page.</span></span>
1. <span data-ttu-id="9a1f9-338">Välj produkten där fältet **Artikelnummer** är inställt på *A0002*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="9a1f9-339">I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="9a1f9-340">På sidan **Fysiska dimensioner** bör du se följande rad i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="9a1f9-341">**Enhet:** *st*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="9a1f9-342">**Bruttovikt:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="9a1f9-343">**Bredd:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="9a1f9-344">**Djup:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="9a1f9-345">**Höjd:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="9a1f9-346">**Volym:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="9a1f9-347">Skapa försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="9a1f9-347">Create sales order 1</span></span>

<span data-ttu-id="9a1f9-348">Följ dessa steg för att skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-349">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="9a1f9-350">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a1f9-351">En dialogruta visas där du kan skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="9a1f9-352">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-352">Set the following values:</span></span>

    - <span data-ttu-id="9a1f9-353">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="9a1f9-354">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="9a1f9-355">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="9a1f9-356">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-356">The new sales order is opened.</span></span> <span data-ttu-id="9a1f9-357">På snabbfliken **Försäljningsorderrader**, lägg till följande försäljningsrader:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="9a1f9-358">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-358">Line 1:</span></span>

        - <span data-ttu-id="9a1f9-359">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="9a1f9-360">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="9a1f9-361">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-361">Line 2:</span></span>

        - <span data-ttu-id="9a1f9-362">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="9a1f9-363">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="9a1f9-364">Markera den första raden och välj sedan **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="9a1f9-365">På sidan **Reservation** väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="9a1f9-366">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-366">Then close the page.</span></span>
1. <span data-ttu-id="9a1f9-367">Upprepa de två föregående stegen för den andra raden.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="9a1f9-368">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="9a1f9-369">Skapa försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="9a1f9-369">Create sales order 2</span></span>

<span data-ttu-id="9a1f9-370">Följ dessa steg för att skapa en andra försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-371">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="9a1f9-372">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a1f9-373">En dialogruta visas där du kan skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="9a1f9-374">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-374">Set the following values:</span></span>

    - <span data-ttu-id="9a1f9-375">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="9a1f9-376">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="9a1f9-377">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="9a1f9-378">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-378">The new sales order is opened.</span></span> <span data-ttu-id="9a1f9-379">På snabbfliken **Försäljningsorderrader**, lägg till följande försäljningsrader:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="9a1f9-380">Rad 1:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-380">Line 1:</span></span>

        - <span data-ttu-id="9a1f9-381">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="9a1f9-382">**Kvantitet:** *4*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="9a1f9-383">Rad 2:</span><span class="sxs-lookup"><span data-stu-id="9a1f9-383">Line 2:</span></span>

        - <span data-ttu-id="9a1f9-384">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="9a1f9-385">**Kvantitet:** *4*</span><span class="sxs-lookup"><span data-stu-id="9a1f9-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="9a1f9-386">Markera den första raden och välj sedan **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="9a1f9-387">På sidan **Reservation** väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="9a1f9-388">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-388">Then close the page.</span></span>
1. <span data-ttu-id="9a1f9-389">Upprepa de två föregående stegen för den andra raden.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="9a1f9-390">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="9a1f9-391">Skapa last</span><span class="sxs-lookup"><span data-stu-id="9a1f9-391">Create the load</span></span>

<span data-ttu-id="9a1f9-392">Skapa en beläggning för varje orderuppsättning som du har skapat för scenariot och sedan släppa den till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="9a1f9-393">Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="9a1f9-394">På fliken **Försäljningsrader** letar du upp och markerar alla försäljningsorderrader från försäljningsordern som du skapat för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="9a1f9-395">I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="9a1f9-396">De markerade orderraderna läggs till i en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="9a1f9-397">I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *40' behållare*.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="9a1f9-398">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="9a1f9-399">I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du just skapat.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="9a1f9-400">Välj **Frisläpp \> frisläpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="9a1f9-401">I dialogrutan **Släpp till lagerställe** välj **OK** om du vill frisläppa den valda beläggningen till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="9a1f9-402">Kontrollera försändelser och behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-402">Verify the shipments and containers</span></span>

<span data-ttu-id="9a1f9-403">I följande procedur kan du kontrollera försändelser som har skapats.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="9a1f9-404">Använd den när du vill granska den order du skapat för det här scenariot för att se till att du får de förväntade resultaten.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="9a1f9-405">Gå till **Warehouse management \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="9a1f9-406">Sök efter och välj den försändelse som skapades för inläsningen som du just frisläppde.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="9a1f9-407">Öppna fliken arbetsflöde i åtgärdsfönstret **Transport** och välj **Visa behållare**.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="9a1f9-408">Bekräfta att artiklarna från försäljningsorderna var behållare i två olika behållare.</span><span class="sxs-lookup"><span data-stu-id="9a1f9-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a1f9-409">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9a1f9-409">Additional resources</span></span>

- [<span data-ttu-id="9a1f9-410">Skapande av behållare</span><span class="sxs-lookup"><span data-stu-id="9a1f9-410">Containerization</span></span>](wave-containerization.md)
