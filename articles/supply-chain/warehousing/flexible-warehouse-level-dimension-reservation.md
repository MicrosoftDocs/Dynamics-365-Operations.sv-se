---
title: Flexibel reservationspolicy för dimension på lagernivå
description: I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för företag att sälja batchspårade produkter och köra sin logistik som WMS-aktiverade operationer reservera specifika batchar för kundförsäljningsorder, även om den reservationssekvens som är kopplad till produkterna inte tillåter reservation av specifika batchar.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d75e6a8b48447a33156e03d50e990b8514bacda9
ms.sourcegitcommit: d540998ad6f9c894ca99498c045ae4b86b779806
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "3970713"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="9eb0e-103">Flexibel reservationspolicy för dimension på lagernivå</span><span class="sxs-lookup"><span data-stu-id="9eb0e-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9eb0e-104">När en hierarki för lagerreservationer av typen "batch-under\[plats\]" associeras med produkter kan företag som säljer spårade produkter och kör sin logistik när operationer som har aktiverats för Microsoft Dynamics 365 lagerställehanteringssystem (WMS) inte kan reservera specifika partier för dessa produkter för kundförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span>

<span data-ttu-id="9eb0e-105">På samma sätt kan särskilda ID-nummer inte reserveras för produkter på försäljningsorder när dessa produkter associeras med standardhierarkin för reservationer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-105">In a similar way, specific license plates can't be reserved for products on sales orders when those products are associated with the default reservation hierarchy.</span></span>

<span data-ttu-id="9eb0e-106">I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för dessa företag att reservera specifika batchar eller ID-nummer, även om produkterna är kopplade till reservationshierarkin "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="9eb0e-106">This topic describes the inventory reservation policy that lets these businesses reserve specific batches or license plates, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="9eb0e-107">Lagerreservationshierarki</span><span class="sxs-lookup"><span data-stu-id="9eb0e-107">Inventory reservation hierarchy</span></span>

<span data-ttu-id="9eb0e-108">Det här avsnittet sammanfattar den befintliga lagerreservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-108">This section summarizes the existing inventory reservation hierarchy.</span></span>

<span data-ttu-id="9eb0e-109">Lagerreservationshierarkin avgör att när det gäller lagringsdimensioner har efterfrågeordern de obligatoriska dimensionerna för plats, lager och lagerstatus, medan lagerställelogiken är ansvarig för att tilldela en plats till de begärda kvantiteterna och reservera platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="9eb0e-110">Med andra ord förväntas en efterfrågeorder i interaktionen mellan efterfrågeorder ordern och lagerställeåtgärder för att ange var ordern måste levereras från (dvs. vilken plats och lagerställe).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="9eb0e-111">Lagerstället använder sig av sin logik för att hitta den begärda kvantiteten i dessa lagerlokaler.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="9eb0e-112">Om du vill återspegla affärsverksamhetens driftsmodell, kan spårningsdimensioner (batch- och serienummer) bli mer flexibla.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="9eb0e-113">En hierarki för lagerreservationer kan innehålla scenarier där följande villkor gäller:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="9eb0e-114">Företaget använder sina lageroperationer för att hantera plockning av kvantiteter som har batch- eller serienummer efter det att kvantiteterna har hittats i lagringsutrymmet på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="9eb0e-115">Den här modellen kallas ofta för en *Batch-under\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="9eb0e-116">Den används vanligtvis när en produkts batch- eller serienummer-ID inte är viktig för de kunder som gör efterfrågan från det säljande företaget.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="9eb0e-117">Om batch- eller serienummer är en del av en kundsorderspecifikation och registreras på efterfrågeorder, begränsas lageroperationerna som hittar kvantiteterna i lagerstället till de specifika nummer som krävs och tillåts inte att ändra dem.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="9eb0e-118">Den här modellen kallas en *Batch-ovan\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="9eb0e-119">I dessa scenarier är utmaningen att bara en hierarki med lagerreservationer kan tilldelas varje frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="9eb0e-120">För att WMS ska hantera spårade objekt, efter att hierarkitilldelningen bestämmer när batch- eller serienumret ska reserveras (antingen när efterfrågan beställs eller under lagerplockningsarbetet), kan denna timing inte ändras på ad-hoc-basis.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="9eb0e-121">Flexibel reservation för batchspårade artiklar</span><span class="sxs-lookup"><span data-stu-id="9eb0e-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="9eb0e-122">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="9eb0e-122">Business scenario</span></span>

<span data-ttu-id="9eb0e-123">I det här scenariot använder ett företag en lagerstrategi där färdiga varor spåras efter batchnummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="9eb0e-124">Det här företaget använder också WMS-arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="9eb0e-125">Eftersom den här arbetsbelastningen har en välutrustad logik för planering och transport av lagerplocknings- och leveransoperationer för batchaktiverade artiklar, associeras de flesta av de färdiga artiklarna med en batch-under\[plats\] lagerreservationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="9eb0e-126">Fördelen med den här typen av driftsinställningar är att beslut (som är effektiva reservationsbeslut) om vilka batchar som ska plockas och var de ska skjutas upp tills lagerplockningsoperationer har startat.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="9eb0e-127">De görs inte när kundens order har placerats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="9eb0e-128">Även om reservationshierarkin "batch-under\[plats\]" "betjänar företagets affärsmål", kräver många av företagets etablerade kunder samma batch som de tidigare köpte när de beställer om produkter.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="9eb0e-129">Därför söker företaget efter flexibilitet på det sätt som reglerna för batchreservation hanteras, så att, beroende på kundernas efterfrågan för samma artikel, uppstår följande problem.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="9eb0e-130">Ett batchnummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte ändras under lageroperationer och/eller tas av andra behov.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="9eb0e-131">Det här beteendet garanterar att det batchnummer som beställs levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="9eb0e-132">Om batchnumret inte är viktigt för kunden, kan lageroperationerna bestämma ett batchnummer under plockningsarbetet efter att registrering och reservation av försäljningsordern har utförts.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="9eb0e-133">Tillåta reservation av en specifik batch på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="9eb0e-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="9eb0e-134">För att tillgodose önskad flexibilitet i batchreservationens beteende för artiklar som är associerade med en "Batch-under\[plats\]" lagerreservationshierarki måste chefer markera kryssrutan **Tillåt reservation av efterfrågeorder** för nivån **Batch-nummer** på sidan **lagerreservationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Göra lagerreservationshierarkin flexibel](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="9eb0e-136">När nivån **Batch-nummer** i hierarkin väljs kommer alla dimensioner över den nivån och upp till nivån **plats** att väljas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="9eb0e-137">(Som standard är alla dimensioner ovanför nivån **plats** förvalda.) Det här beteendet återspeglar logiken där alla dimensioner i intervallet mellan batchnumret och lagerstället också reserveras automatiskt när du har reserverat ett specifikt batchnummer på orderraden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-138">Kryssrutan **Tillåt reservation på efterfrågerorder** gäller bara för de nivåer för reservationshierarkier som ligger under dimensionen lagerställe.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="9eb0e-139">**Batchnummer** och **ID-nummer** är de enda nivåerna i hierarkin som är öppen för den flexibla reservationsprincipen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-139">**Batch number** and **License plate** are the only levels in the hierarchy that are open for the flexible reservation policy.</span></span> <span data-ttu-id="9eb0e-140">Med andra ord kan du inte markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **Plats** eller **Serienummer**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location** or **Serial number** level.</span></span>
>
> <span data-ttu-id="9eb0e-141">Om din reservationshierarki innehåller dimensionen för serienummer (som alltid måste vara under nivån **Batch-nummer**), och om du har aktiverat batch-specifik reservation för batch-numret kommer systemet att fortsätta hantera reservations- och plockningsoperationer för serienummer baserat på de regler som gäller för reservationsprincipen "Serie-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="9eb0e-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="9eb0e-142">Du kan när som helst tillåta batch-specifik reservation för en befintlig "batch-under\[plats\]" reservationshierarki i distributionen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="9eb0e-143">Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="9eb0e-144">Men kryssrutan **Tillåt reservation på efterfrågeorder** kan inte vara avmarkerad om lagertransaktioner för utleveranstyper **Reserverat beställt**, **Fysiskt reserverat** eller **Beställt** finns för en eller flera artiklar som är associerade med den reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-145">Om en artikels befintliga reservationshierarki inte tillåter kommandospecifikation på ordern kan du tilldela om den till en reservationshierarki som tillåter batch-specifikation, förutsatt att hierarkinivåstrukturen är densamma i båda hierarkierna.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="9eb0e-146">Använd funktionen **ändra reservationshierarki för artiklar** för att utföra omtilldelningen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="9eb0e-147">Den här ändringen kan vara relevant när du vill förhindra flexibel batch-reservation för en delmängd av batch-spårade artiklar, men tillåter den för resten av produktportföljen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="9eb0e-148">Oavsett om du har markerat kryssrutan **Tillåt reservation på efterfrågeorder** om du inte vill reservera ett specifikt batchnummer för artikeln på en orderrad, gäller standardoperationslogiken för lagerställe som är giltig för en "Batch-under\[location\]" reservationhierarkin.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="9eb0e-149">Reservera ett specifikt batchnummer för en kundorder</span><span class="sxs-lookup"><span data-stu-id="9eb0e-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="9eb0e-150">När en batch-spårad artikels "Batch-under\[plats\]" lagerreservationshierarki har ställts in för att tillåta reservation av specifika batchnummer på försäljningsorder, kan behandlare av försäljningsorder ta kundorder för samma artikel på något av följande sätt, beroende på kundens begäran:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="9eb0e-151">**Ange orderdetaljer utan att ange ett batchnummer** – det här tillvägagångssättet ska användas när produktens batch-specifikation inte är viktig för kunden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="9eb0e-152">Alla befintliga processer som associeras med hantering av en order av den här typen i systemet förblir oförändradet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="9eb0e-153">Det behövs ingen ytterligare hänsyn till användarna.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="9eb0e-154">**Ange orderdetaljer och reservera ett specifikt batchnummer** – den här metoden bör användas när kunden begär en specifik batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="9eb0e-155">Vanligtvis begär kunder en särskild batch när de ombeställer en produkt som de tidigare har köpt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="9eb0e-156">Denna typ av batch-specifik reservation kallas för *orderallokerad reservation*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="9eb0e-157">Följande regler gäller när kvantiteter bearbetas och ett batchnummer allokeras till en specifik order:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="9eb0e-158">Om du vill tillåta reservation av ett specifikt batchnummer för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="9eb0e-159">I detta intervall ingår vanligtvis dimensionen registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="9eb0e-160">Platsdirektiv används inte när plockningsarbete skapas för en försäljningsrad som använder orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="9eb0e-161">Under lagerbearbetning av arbete för orderallokerade batchar, tillåts varken användaren eller systemet att ändra batchnumret.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="9eb0e-162">(Bearbetningen omfattar undantagshantering.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="9eb0e-163">I följande exempel visas ett komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario-batch-number-allocation"></a><span data-ttu-id="9eb0e-164">Exempel scenario: allokering av batchnummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-164">Example scenario: Batch number allocation</span></span>

<span data-ttu-id="9eb0e-165">För det här exemplet måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a><span data-ttu-id="9eb0e-166">Ställ in en hierarki för lagerreservationer för att tillåta batch-specifika reservationer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="9eb0e-167">Gå till **Lagerstyrning** \> **Inställningar** \> **Lager \> Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="9eb0e-168">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-168">Select **New**.</span></span>
3. <span data-ttu-id="9eb0e-169">I fältet **Namn** anger du ett namn (till exempel **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="9eb0e-170">I fältet **Beskrivning** anger du en beskrivning (till exempel, **Batch under flexibel**).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="9eb0e-171">I fältet **Valda** väljer du **Serienummer** och **Ägare** och väljer sedan vänsterpilen för att flytta dem till fältet **Tillgängliga**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="9eb0e-172">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-172">Select **OK**.</span></span>
7. <span data-ttu-id="9eb0e-173">I raden för dimensionsnivån **Batch-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="9eb0e-174">Nivåerna **Registreringsskylt** och **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för dem.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="9eb0e-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="9eb0e-176">Skapa en ny frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-176">Create a new released product</span></span>

1. <span data-ttu-id="9eb0e-177">Ställ in produktens tre huvuddataparametrar med hjälp av dessa värden:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="9eb0e-178">I fältet **lagringsdimensionsgrupp** välj **Ware**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="9eb0e-179">I fältet **spårningsdimensionsgrupp** välj **Batch-Phy**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="9eb0e-180">I fältet **Reservationshierarki** välj **BatchFlex**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="9eb0e-181">Skapa två batchnummer, t.ex. **B11** och **B22**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="9eb0e-182">Lägg till artikelkvantiteter i lagerbehållning med hjälp av följande värden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="9eb0e-183">Distributionslager</span><span class="sxs-lookup"><span data-stu-id="9eb0e-183">Warehouse</span></span> | <span data-ttu-id="9eb0e-184">Batchnummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-184">Batch number</span></span> | <span data-ttu-id="9eb0e-185">Plats</span><span class="sxs-lookup"><span data-stu-id="9eb0e-185">Location</span></span> | <span data-ttu-id="9eb0e-186">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-186">License plate</span></span> | <span data-ttu-id="9eb0e-187">Antal</span><span class="sxs-lookup"><span data-stu-id="9eb0e-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="9eb0e-188">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-188">24</span></span>        | <span data-ttu-id="9eb0e-189">B11</span><span class="sxs-lookup"><span data-stu-id="9eb0e-189">B11</span></span>          | <span data-ttu-id="9eb0e-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="9eb0e-190">BULK-001</span></span> | <span data-ttu-id="9eb0e-191">Ingen</span><span class="sxs-lookup"><span data-stu-id="9eb0e-191">None</span></span>          | <span data-ttu-id="9eb0e-192">10</span><span class="sxs-lookup"><span data-stu-id="9eb0e-192">10</span></span>       |
    | <span data-ttu-id="9eb0e-193">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-193">24</span></span>        | <span data-ttu-id="9eb0e-194">B11</span><span class="sxs-lookup"><span data-stu-id="9eb0e-194">B11</span></span>          | <span data-ttu-id="9eb0e-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="9eb0e-195">FL-001</span></span>   | <span data-ttu-id="9eb0e-196">LP11</span><span class="sxs-lookup"><span data-stu-id="9eb0e-196">LP11</span></span>          | <span data-ttu-id="9eb0e-197">10</span><span class="sxs-lookup"><span data-stu-id="9eb0e-197">10</span></span>       |
    | <span data-ttu-id="9eb0e-198">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-198">24</span></span>        | <span data-ttu-id="9eb0e-199">B22</span><span class="sxs-lookup"><span data-stu-id="9eb0e-199">B22</span></span>          | <span data-ttu-id="9eb0e-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="9eb0e-200">FL-002</span></span>   | <span data-ttu-id="9eb0e-201">LP22</span><span class="sxs-lookup"><span data-stu-id="9eb0e-201">LP22</span></span>          | <span data-ttu-id="9eb0e-202">10</span><span class="sxs-lookup"><span data-stu-id="9eb0e-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a><span data-ttu-id="9eb0e-203">Ange försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-203">Enter sales order details</span></span>

1. <span data-ttu-id="9eb0e-204">Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="9eb0e-205">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-205">Select **New**.</span></span>
3. <span data-ttu-id="9eb0e-206">I försäljningsorderns rubrik, i fältet **Kundkonto** ange **US-003**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="9eb0e-207">Lägg till en rad för den nya artikeln och ange **10** som kvantitet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="9eb0e-208">Se till att fältet **Lagerställe** anges till **24**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="9eb0e-209">På snabbfliken **försäljningsorderrader** välj **lager** och sedan i gruppen **underhåll** välj **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="9eb0e-210">Sidan **Batch-reservation** visar en lista över batchar som är tillgängliga för reservation för orderraden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="9eb0e-211">I det här exemplet visas ett antal på **20** för batchnummer **B11** och kvantiteten **10** för batchnummer **B22**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="9eb0e-212">Observera att du inte kan komma åt sidan **Batch-reservation** från en rad om den raden är associerad med "Batch-under\[plats\]" reservationshierarki om den inte har ställts in för att tillåta batch-specifik reservation.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-213">Om du vill reservera en specifik batch för en försäljningsorder måste du använda sidan **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="9eb0e-214">Om du anger batchnumret direkt på försäljningsorderraden, kommer systemet att fungera som om du har angett ett specifikt batchvärde för ett objekt som omfattas av "Batch-under\[plats\]" reservationspolicy.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="9eb0e-215">När du sparar raden visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="9eb0e-216">Om du bekräftar att batchnumret ska anges direkt på orderraden hanteras inte raden av den normala lagerstyrningslogiken.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="9eb0e-217">Om du reserverar kvantiteten från sidan **Reservation** kommer ingen specifik batch att reserveras och körningen av lagerställeoperationer för raden följer reglerna som är tillämpliga under reservationspolicyn "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="9eb0e-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="9eb0e-218">Den här sidan fungerar vanligtvis på samma sätt och interagerar med artiklar som har en associerad reservationssekvens för typen "Batch-ovan\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="9eb0e-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="9eb0e-219">Följande undantag gäller emellertid:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="9eb0e-220">Snabbfliken **batchnummer för källrad** visar de batchnummer som har reserverats för orderraden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="9eb0e-221">Batchvärdet i rutnätet visas under hela orderradens uppfyllandecykel, inklusive faserna för lagerbearbetning.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-221">The batch values in the grid will be shown throughout the fulfillment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="9eb0e-222">På snabbfliken **översikt** visas däremot en reservation på ordinarie orderrad (dvs. reservation som görs för dimensionerna över nivån **plats**) i rutnätet upp till punkten när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="9eb0e-223">Arbetsenheten tar över radreservationen och radreservationen visas inte längre på sidan.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="9eb0e-224">Snabbfliken **batchnummer för källrader** används för att garantera att försäljningsorderns handläggare kan visa de batchnummer som har utfästs till kundens order när som helst under livscykeln, upp till fakturering.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="9eb0e-225">Förutom att reservera en viss batch kan han eller hon manuellt välja batchens specifika plats och licensskylt i stället för att låta systemet automatiskt välja dem.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="9eb0e-226">Denna kapacitet är relaterad till designen av mekanismen för orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="9eb0e-227">Som nämnts tidigare, när ett specifikt batchnummer reserveras för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="9eb0e-228">Därför kommer lagerstället att ha samma lagringsdimensioner som har reserverats av de användare som arbetade med ordern, och den kanske inte alltid representerar den placering av artikellagring som är praktiskt eller till och med möjlig för plockningsoperationer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="9eb0e-229">Om orderhandläggarna känner till begränsningarna i lagerställena, kanske de vill välja de specifika platserna och licensskyltarna manuellt när de reserverar en batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="9eb0e-230">I det här fallet måste användaren använda funktionen för **visningsdimensioner** i sidhuvudet och måste lägga till platsen och licensskylten i rutnätet på snabbfliken **översikt**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="9eb0e-231">På sidan **Batch-reservation** välj raden för batch **B11** och välj sedan **reservera rad**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="9eb0e-232">Det finns ingen särskild logik för att tilldela platser och licensskyltarna vid automatisk reservation.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="9eb0e-233">Du kan ange kvantiteten manuellt i fältet **reservation**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="9eb0e-234">Observera att snabbfliken **batchnummer för källrad**, batch **B11** visas som **utfäst**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Utfästa ett specifikt batchnummer på en försäljningsorderrad på sidan batch-reservation](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="9eb0e-236">Det går att utföra reservationer av kvantiteten på en försäljningsorderrad i flera batchar.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="9eb0e-237">På samma sätt kan reservation av samma batch göras mot flera platser och licensskyltar (om licensskyltar är aktiverade för platserna).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="9eb0e-238">Reservation av en specifik batch för kvantiteten på en försäljningsorderrad kan också vara del.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="9eb0e-239">Den totala kvantiteten 100 enheter kan till exempel reserveras så att en specifik batch har allokerats till 20 enheter, medan 80 enheter reserveras på platsen och lagerställenivåer för någon tillgänglig batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="9eb0e-240">I det här fallet hanterar WMS plockningsoperationer med hjälp av två separata arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="9eb0e-241">Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="9eb0e-242">Markera artikeln och välj sedan **hantera lager** \> **visa** \> **transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Order-allokerad reservation som en lagertransaktionstyp](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="9eb0e-244">Granska artikelns lagertransaktioner som hör till försäljningsorderradens reservation.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="9eb0e-245">En transaktion där fältet **Referens** anges till **Försäljningsorder** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="9eb0e-246">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner plats, lagerställe och lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="9eb0e-247">En transaktion där fältet**Referens** anges till **Orderallokerad reservation** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för den specifika batchen och alla lagerdimensioner ovanför.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="9eb0e-248">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner batch-nummer och plats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="9eb0e-249">I det här exemplet är platsen **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="9eb0e-250">Välj i försäljningsorderhuvudet **Lagerställe** \> **Åtgärder** \> **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="9eb0e-251">Orderraden är nu vågad och en last och ett arbete skapas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="9eb0e-252">Granska och bearbeta lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="9eb0e-253">På snabbfliken **Försäljningsorderrader** välj **Lagerställe** \> **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="9eb0e-254">Det arbete som hanterar plockoperationen för batchkvantiteter som har bekräftats till försäljningsorderraden har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="9eb0e-255">Om du vill skapa arbete använder systemet arbetsmallar men inte platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="9eb0e-256">Alla standardinställningar som definieras för arbetsmallar, t.ex. ett maximalt antal plockningsrader eller en specifik måttenhet, används för att bestämma när nytt arbete ska skapas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="9eb0e-257">Reglerna som är kopplade till platsdirektiv för identifiering av plockningsplatser beaktas dock inte eftersom den order som genomförts redan anger alla lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="9eb0e-258">Dessa lagerdimensioner inkluderar dimensionerna på lagerställets lagernivå.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="9eb0e-259">Därför ärver arbetet dessa dimensioner utan att behöva konsultera platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="9eb0e-260">Batchnumret visas inte på plockningsraden (som är fallet för den arbetsrad som skapas för en artikel som har en motsvarande "batch-ovan\[plats\]" reservationshierarki.) I stället visas batchnummer från och alla andra lagringsdimensioner på arbetsradens jobblagertransaktion som refereras från de associerade lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Lagerställets lagertransaktion för arbete som härrör från en reservation som har genomförts av order](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="9eb0e-262">När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på **Order-allokerad reservation** borttagen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="9eb0e-263">Lagertransaktionen där fältet **Referens** anges till **Arbete** innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="9eb0e-264">Lageroperationer kan fortsätta för att hantera utförande av arbetet på vanligt sätt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="9eb0e-265">Men instruktionerna på den mobila enheten instruerar arbetaren att välja ett specifikt batchnummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="9eb0e-266">I lagermiljöer där platser är registreringsskylt – styrs efter att en arbetare har nått en plats som lagrar samma batch på registreringsskyltar, kan han eller hon välja från alla registreringsskyltar som inte redan har reserverats (t.ex. av en annan order-allokerad reservation eller arbete som härrör från en reservation av den typen.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="9eb0e-267">Om det blir opraktiskt att plocka från den plats som anges på arbetsraden, kan lagerställets operatörer använda någon av följande åtgärder för att dirigera om plockning av en viss batch:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="9eb0e-268">Standard är åtgärden **åsidosätta plats** på en mobil enhet (förutsatt att inställningen för lagerarbetare **Tillåt åsidosättning av plockplats** är aktiverad)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="9eb0e-269">Åtgärden **ändra plats** på sidan **information om arbetslista**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="9eb0e-270">Slutför plockningen på den mobila enheten och sätt in arbetet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="9eb0e-271">Kvantiteten **10** för batchnummer **B11** har nu plockats för försäljningsorderraden och placerats på platsen **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="9eb0e-272">I detta skede är den klar att lastas på lastbilen och skickas till kundens adress.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="flexible-license-plate-reservation"></a><span data-ttu-id="9eb0e-273">Flexibel reservation av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-273">Flexible license plate reservation</span></span>

### <a name="business-scenario"></a><span data-ttu-id="9eb0e-274">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="9eb0e-274">Business scenario</span></span>

<span data-ttu-id="9eb0e-275">I det här scenariot använder ett företag lagerstyrnings- och arbetsbearbetning och hanterar belastningsplanering vid nivån för enskilda lastpallar/behållare utanför Supply Chain Management innan arbetet skapas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-275">In this scenario, a company uses warehouse management and work processing, and handles load planning at the level of individual pallets/containers outside Supply Chain Management before work is created.</span></span> <span data-ttu-id="9eb0e-276">Dessa behållare representeras av ID-nummer i lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-276">These containers are represented by license plates in the inventory dimensions.</span></span> <span data-ttu-id="9eb0e-277">Därför måste specifika ID-nummer på försäljnings orderrader innan plockningsarbete utförs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-277">Therefore, for this approach, specific license plates must be pre-assigned to sales order lines before picking work is done.</span></span> <span data-ttu-id="9eb0e-278">Företaget letar efter flexibilitet i hur reservationsreglerna för ID-nummer, så att följande beteende uppstår:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-278">The company is looking for flexibility in the way that the license plate reservation rules are handled, so that the following behaviors occur:</span></span>

- <span data-ttu-id="9eb0e-279">Ett ID-nummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte tas av andra behov.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-279">A license plate can be recorded and reserved when the order is taken by the sales processor, and it can't be taken by other demands.</span></span> <span data-ttu-id="9eb0e-280">Det här beteendet garanterar att det ID-nummer som planerats levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-280">This behavior helps guarantee that the license plate that was planned is shipped to the customer.</span></span>
- <span data-ttu-id="9eb0e-281">Om ID-numret inte redan har tilldelats en försäljningsorderrad kan lagerpersonalen välja ett ID-nummer under plockningsarbete när registrering och reservation av försäljningsorder har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-281">If the license plate isn't already assigned to a sales order line, warehouse personnel can select a license plate during picking work, after sales order registration and reservation are completed.</span></span>

### <a name="turn-on-flexible-license-plate-reservation"></a><span data-ttu-id="9eb0e-282">Aktivera flexibel reservation av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-282">Turn on flexible license plate reservation</span></span>

<span data-ttu-id="9eb0e-283">Innan du kan använda flexibel reservation av ID-nummer måste två funktioner aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-283">Before you can use flexible license plate reservation, two features must be turned on in your system.</span></span> <span data-ttu-id="9eb0e-284">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-284">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="9eb0e-285">Du måste aktivera funktionerna i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-285">You must turn on the features in the following order:</span></span>

1. <span data-ttu-id="9eb0e-286">**Funktionsnamn:** *Flexibel reservation för dimension på distributionslagernivå*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-286">**Feature name:** *Flexible warehouse-level dimension reservation*</span></span>
1. <span data-ttu-id="9eb0e-287">**Funktionsnamn:** *flexibel orderallokerade reservation av ID-nummer*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-287">**Feature name:** *Flexible order-committed license plate reservation*</span></span>

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a><span data-ttu-id="9eb0e-288">Reservera ett specifikt ID-nummer på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="9eb0e-288">Reserve a specific license plate on the sales order</span></span>

<span data-ttu-id="9eb0e-289">Om du vill aktivera reservation av ID-nummer på en order måste du markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **ID-nummer** på sidan **Tillåt reservation av efterfrågeorder** för lagerreservationer för den hierarki som är kopplad till den relevanta artikeln.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-289">To enable license plate reservation on an order, you must select the **Allow reservation on demand order** check box for the **License plate** level on the **Inventory reservation hierarchies** page for the hierarchy that is associated with the relevant item.</span></span>

![Sidan hierarkier för lagerreservationer för en flexibel reservationshierarki för ID-nummer](media/Flexible-LP-reservation-hierarchy.png)

<span data-ttu-id="9eb0e-291">Du kan aktivera reservation av ID-nummer på ordern när som helst i distributionen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-291">You can enable license plate reservation on the order at any point in your deployment.</span></span> <span data-ttu-id="9eb0e-292">Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-292">This change won't affect any reservations or open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="9eb0e-293">Men du kan inte avmarkera kryssrutan **Tillåt reservation på efterfrågeorder** om öppna avgående lagertransaktioner som har en för utleveransstatus *Som har beställts*, *Fysiskt reserverat* eller *Beställt* finns för en eller flera artiklar som är associerade med den reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-293">However, you can't clear the **Allow reservation on demand order** check box if open outbound inventory transactions that have an issue status of *On order*, *Reserved ordered*, or *Reserved physical* exist for one or more items that are associated with that reservation hierarchy.</span></span>

<span data-ttu-id="9eb0e-294">Även om kryssrutan **Tillåt reservation på efterfrågeorder** har markerat nivån **ID-nummer** är det fortfarande möjligt att *inte* reservera ett specifikt ID-nummer på order.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-294">Even if the **Allow reservation on demand order** check box is selected for the **License plate** level, it's still possible *not* to reserve a specific license plate on the order.</span></span> <span data-ttu-id="9eb0e-295">I det här fallet gäller standardlogiken för lageråtgärder som är giltig för den här reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-295">In this case, the default warehouse operations logic that is valid for the reservation hierarchy applies.</span></span>

<span data-ttu-id="9eb0e-296">Om du vill reservera ett visst ID-nummer måste du använda en process med [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). I appen kan du göra denna reservation direkt från en försäljningsorder med hjälp av alternativet **orderallokerade reservation av ID-nummer** för kommandot **Öppna i Excel**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-296">To reserve a specific license plate, you must use an [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md) process.In the application, you can do this reservation directly from a sales order by using the **Order-committed reservations per license plate** option of the **Open in Excel** command.</span></span> <span data-ttu-id="9eb0e-297">I enhets data som öppnas i Excel-tillägget måste du ange följande reservationsrelaterade data och sedan välja **publicera** för att skicka tillbaka data till Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-297">In the entity data that is opened in the Excel add-in, you must enter the following reservation-related data and then select **Publish** to send the data back to Supply Chain Management:</span></span>

- <span data-ttu-id="9eb0e-298">Referens (endast *försäljningsordern* värde stöds.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-298">Reference (Only the *Sales order* value is supported.)</span></span>
- <span data-ttu-id="9eb0e-299">Ordernummer (värdet kan härledas från partiet.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-299">Order number (The value can be derived from the lot.)</span></span>
- <span data-ttu-id="9eb0e-300">Parti-ID</span><span class="sxs-lookup"><span data-stu-id="9eb0e-300">Lot ID</span></span>
- <span data-ttu-id="9eb0e-301">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-301">License plate</span></span>
- <span data-ttu-id="9eb0e-302">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="9eb0e-302">Quantity</span></span>

<span data-ttu-id="9eb0e-303">Om du måste reservera en viss ID-nummer för en spårad artikel, använder du sidan **Batchreservation**, som beskrivs i avsnittet [Ange detaljinformation om försäljningsorder](#sales-order-details).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-303">If you must reserve a specific license plate for a batch-tracked item, use the **Batch reservation** page, as described in the [Enter sales order details](#sales-order-details) section.</span></span>

<span data-ttu-id="9eb0e-304">När försäljningsorderraden som använder en orderallokerad reserverat ID-nummer bearbetas av lagerställe, används inte platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-304">When the sales order line that uses an order-committed license plate reservation is processed by warehouse operations, location directives aren't used.</span></span>

<span data-ttu-id="9eb0e-305">Om en artikel för ett lagerställe består av rader som är lika med en komplett lastpall och har licensskyltar, kan du optimera plockningsprocessen genom att använda ett menyalternativ för mobila enheter där alternativet **Hantera efter ID-nummer** är inställt på *Ja*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-305">If a warehouse work item consists of lines that equal a complete pallet and have license plate–committed quantities, you can optimize the picking process by using a mobile device menu item where the **Handle by license plate** option is set to *Yes*.</span></span> <span data-ttu-id="9eb0e-306">En lagerarbetare kan sedan söka igenom ett ID-nummer för att slutföra en plockning i stället för att behöva skanna artiklarna från ett arbetsställe en i taget.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-306">A warehouse worker can then scan a license plate to complete a pick instead of having to scan the items from the work one by one.</span></span>

![Menyalternativet mobilen där alternativet hantera efter ID-nummer är inställt på Ja](media/Handle-by-LP-menu-item.png)

<span data-ttu-id="9eb0e-308">Eftersom funktionen **Hantera efter ID-nummer** inte stöder arbete som täcker flera lastpallar, är det bättre att ha en separat arbetsuppgift för olika ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-308">Because the **Handle by license plate** functionality doesn't support work that covers multiple pallets, it's better to have a separate work item for different license plates.</span></span> <span data-ttu-id="9eb0e-309">Om du vill använda den här metoden lägger du till fältet **orderallokerade reservation av ID-nummer** som en sidhuvudsbrytning på sidan **arbetsmall**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-309">To use this approach, add the **Order-committed license plate ID** field as a work header break on the **Work template** page.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-310">Värdet för skapande av beställd lagerdimension kommer att tilldelas till plockarbetsraderna och det går inte att visa registreringsskyltens värde direkt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-310">For the order-committed work creation process, an "order-committed inventory dimension" value will be assigned to the picking work lines, and it won't be possible to view the license plate value directly.</span></span> <span data-ttu-id="9eb0e-311">Endast den *användarspecifika* processen stöds när du konfigurerar ett menyalternativ för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-311">Only the *User directed* process is supported when setting up a mobile device menu item.</span></span>

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a><span data-ttu-id="9eb0e-312">Exempelscenario: Ställ in och bearbeta en beställning med utfästa registreringslicenser</span><span class="sxs-lookup"><span data-stu-id="9eb0e-312">Example scenario: Set up and process an order-committed license plate reservation</span></span>

<span data-ttu-id="9eb0e-313">Scenariot visar hur du ställer och bearbeta en beställning med utfästa registreringslicenser.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-313">This scenario shows how to set up and process an order-committed license plate reservation.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="9eb0e-314">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="9eb0e-314">Make demo data available</span></span>

<span data-ttu-id="9eb0e-315">Det här scenariot i detta ämne innehåller värdet och poster som ingår i den standarddemodata som finns för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-315">This scenario refers to values and records that are included in the standard demo data that is provided for Supply Chain Management.</span></span> <span data-ttu-id="9eb0e-316">Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett miljö där demodata är installerat.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-316">If you want to work through the scenario by using the values that are provided here, be sure to work on an environment where the demo data is installed.</span></span> <span data-ttu-id="9eb0e-317">Dessutom måste du välja juridisk person **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-317">Additionally, set the legal entity to **USMF** before you begin.</span></span>

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a><span data-ttu-id="9eb0e-318">Skapa en hierarki för lager reservationer som möjliggör reservation av ID-nummrt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-318">Create an inventory reservation hierarchy that allows for license plate reservation</span></span>

1. <span data-ttu-id="9eb0e-319">Gå till **Lagerstyrning \> Inställningar \> Lager \> Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-319">Go to **Warehouse management \> Setup \> Inventory \> Reservation hierarchy**.</span></span>
1. <span data-ttu-id="9eb0e-320">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-320">Select **New**.</span></span>
1. <span data-ttu-id="9eb0e-321">I fältet **Namn** anger du ett värde (till exempel *FlexibleLP*).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-321">In the **Name** field, enter a value (for example, *FlexibleLP*).</span></span>
1. <span data-ttu-id="9eb0e-322">I fältet **Beskrivning** anger du en värde (till exempel, *Flexibel LP reservation*).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-322">In the **Description** field, enter a value (for example, *Flexible LP reservation*).</span></span>
1. <span data-ttu-id="9eb0e-323">I listan **Valda** välj **Batchnummer**, **Serienummer** och **Ägare**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-323">In the **Selected** list, select **Batch number**, **Serial number**, and **Owner**.</span></span>
1. <span data-ttu-id="9eb0e-324">Välj knappen **Ta bort** ![Bakåtpilen](media/backward-button.png) om du vill flytta fältet till valda poster till listan **Tillgängliga**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-324">Select the **Remove** button ![backward arrow](media/backward-button.png) to move the selected records to the **Available** list.</span></span>
1. <span data-ttu-id="9eb0e-325">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-325">Select **OK**.</span></span>
1. <span data-ttu-id="9eb0e-326">I raden för dimensionsnivån **ID-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-326">In the row for the **License plate** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="9eb0e-327">Nivån **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för den.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-327">The **Location** level is automatically selected, and you can't clear the check box for it.</span></span>
1. <span data-ttu-id="9eb0e-328">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-328">Select **Save**.</span></span>

### <a name="create-two-released-products"></a><span data-ttu-id="9eb0e-329">Skapa två frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-329">Create two released products</span></span>

1. <span data-ttu-id="9eb0e-330">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-330">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="9eb0e-331">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-331">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9eb0e-332">I dialogrutan **Ny frisläppt produkt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-332">In the **New released product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9eb0e-333">**Produktnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-333">**Product number:** *Item1*</span></span>
    - <span data-ttu-id="9eb0e-334">**Artikelnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-334">**Item number:** *Item1*</span></span>
    - <span data-ttu-id="9eb0e-335">**Artikelmodellgrupp:** *FIFO*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-335">**Item model group:** *FIFO*</span></span>
    - <span data-ttu-id="9eb0e-336">**Artikelgrupp:** *Ljud*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-336">**Item group:** *Audio*</span></span>
    - <span data-ttu-id="9eb0e-337">**Lagringsdimensionsgrupp:** *Lager*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-337">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="9eb0e-338">**Spårningsdimensionsgrupp:** *Ingen*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-338">**Tracking dimension group:** *None*</span></span>
    - <span data-ttu-id="9eb0e-339">**Reservationshierarki:** *FlexibleLP*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-339">**Reservation hierarchy:** *FlexibleLP*</span></span>

1. <span data-ttu-id="9eb0e-340">Välj **OK** för att skapa produkt och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-340">Select **OK** to create the product and close the dialog box.</span></span>
1. <span data-ttu-id="9eb0e-341">Den nya produkten öppnas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-341">The new product is opened.</span></span> <span data-ttu-id="9eb0e-342">På snabbfliken **lagerställe** i fältet **enhetssekvensgrupp- ID** anger du *ea*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-342">On the **Warehouse** FastTab, set the **Unit sequence group ID** field to *ea*.</span></span>
1. <span data-ttu-id="9eb0e-343">Upprepa föregående steg för att skapa en andra produkt som har samma inställningar, men ställ in fält **produktnummer** och **artikelnummer** på *Artikel2*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-343">Repeat the previous steps to create a second product that has the same settings, but set the **Product number** and **Item number** fields to *Item2*.</span></span>
1. <span data-ttu-id="9eb0e-344">I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Visa**, väljer du **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-344">On the Action Pane, on the **Manage inventory** tab, in the **View** group, select **On-hand inventory**.</span></span> <span data-ttu-id="9eb0e-345">Välj sedan **justering av kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-345">Then select **Quantity adjustment**.</span></span>
1. <span data-ttu-id="9eb0e-346">Justera lagerbehållningen för de nya artiklarna enligt vad som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-346">Adjust the on-hand inventory of the new items as specified in the following table.</span></span>

    | <span data-ttu-id="9eb0e-347">Artikel</span><span class="sxs-lookup"><span data-stu-id="9eb0e-347">Item</span></span>  | <span data-ttu-id="9eb0e-348">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="9eb0e-348">Warehouse</span></span> | <span data-ttu-id="9eb0e-349">Plats</span><span class="sxs-lookup"><span data-stu-id="9eb0e-349">Location</span></span> | <span data-ttu-id="9eb0e-350">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-350">License plate</span></span> | <span data-ttu-id="9eb0e-351">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="9eb0e-351">Quantity</span></span> |
    |-------|-----------|----------|---------------|----------|
    | <span data-ttu-id="9eb0e-352">Artikel1</span><span class="sxs-lookup"><span data-stu-id="9eb0e-352">Item1</span></span> | <span data-ttu-id="9eb0e-353">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-353">24</span></span>        | <span data-ttu-id="9eb0e-354">FL-010</span><span class="sxs-lookup"><span data-stu-id="9eb0e-354">FL-010</span></span>   | <span data-ttu-id="9eb0e-355">LP01</span><span class="sxs-lookup"><span data-stu-id="9eb0e-355">LP01</span></span>          | <span data-ttu-id="9eb0e-356">10</span><span class="sxs-lookup"><span data-stu-id="9eb0e-356">10</span></span>       |
    | <span data-ttu-id="9eb0e-357">Artikel1</span><span class="sxs-lookup"><span data-stu-id="9eb0e-357">Item1</span></span> | <span data-ttu-id="9eb0e-358">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-358">24</span></span>        | <span data-ttu-id="9eb0e-359">FL-011</span><span class="sxs-lookup"><span data-stu-id="9eb0e-359">FL-011</span></span>   | <span data-ttu-id="9eb0e-360">LP02</span><span class="sxs-lookup"><span data-stu-id="9eb0e-360">LP02</span></span>          | <span data-ttu-id="9eb0e-361">10</span><span class="sxs-lookup"><span data-stu-id="9eb0e-361">10</span></span>       |
    | <span data-ttu-id="9eb0e-362">Artikel2</span><span class="sxs-lookup"><span data-stu-id="9eb0e-362">Item2</span></span> | <span data-ttu-id="9eb0e-363">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-363">24</span></span>        | <span data-ttu-id="9eb0e-364">FL-010</span><span class="sxs-lookup"><span data-stu-id="9eb0e-364">FL-010</span></span>   | <span data-ttu-id="9eb0e-365">LP01</span><span class="sxs-lookup"><span data-stu-id="9eb0e-365">LP01</span></span>          | <span data-ttu-id="9eb0e-366">5</span><span class="sxs-lookup"><span data-stu-id="9eb0e-366">5</span></span>        |
    | <span data-ttu-id="9eb0e-367">Artikel2</span><span class="sxs-lookup"><span data-stu-id="9eb0e-367">Item2</span></span> | <span data-ttu-id="9eb0e-368">24</span><span class="sxs-lookup"><span data-stu-id="9eb0e-368">24</span></span>        | <span data-ttu-id="9eb0e-369">FL-011</span><span class="sxs-lookup"><span data-stu-id="9eb0e-369">FL-011</span></span>   | <span data-ttu-id="9eb0e-370">LP02</span><span class="sxs-lookup"><span data-stu-id="9eb0e-370">LP02</span></span>          | <span data-ttu-id="9eb0e-371">5</span><span class="sxs-lookup"><span data-stu-id="9eb0e-371">5</span></span>        |

    > [!NOTE]
    > <span data-ttu-id="9eb0e-372">Du måste skapa de två ID-numren och använda platser som tillåter blandade artiklar t.ex. *FL-010* och *FL-011*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-372">You must create the two license plates and use locations that allow for mixed items, such as *FL-010* and *FL-011*.</span></span>

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a><span data-ttu-id="9eb0e-373">Skapa en försäljningsorder och reservera ett specifikt ID-nummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-373">Create a sales order and reserve a specific license plate</span></span>

1. <span data-ttu-id="9eb0e-374">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-374">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="9eb0e-375">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-375">Select **New**.</span></span>
1. <span data-ttu-id="9eb0e-376">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-376">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9eb0e-377">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-377">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="9eb0e-378">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-378">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="9eb0e-379">Välj **OK** för att stänga dialogrutan **Skapa försäljningsorder** och öppna den nya försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-379">Select **OK** to close the **Create sales order** dialog box and open the new sales order.</span></span>
1. <span data-ttu-id="9eb0e-380">På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-380">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="9eb0e-381">**Artikelnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-381">**Item number:** *Item1*</span></span>
    - <span data-ttu-id="9eb0e-382">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-382">**Quantity:** *10*</span></span>

1. <span data-ttu-id="9eb0e-383">Lägg till en andra försäljningsorderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-383">Add a second sales order line that has the following settings:</span></span>

    - <span data-ttu-id="9eb0e-384">**Artikelnummer:** *Artikel2*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-384">**Item number:** *Item2*</span></span>
    - <span data-ttu-id="9eb0e-385">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-385">**Quantity:** *5*</span></span>

1. <span data-ttu-id="9eb0e-386">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-386">Select **Save**.</span></span>
1. <span data-ttu-id="9eb0e-387">På snabbfliken **Radinformation** på fliken **Inställningar** gör en anteckning av värdet **Parti-ID** för varje rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-387">On the **Line details** FastTab, on the **Setup** tab, make a note of the **Lot ID** value for each line.</span></span> <span data-ttu-id="9eb0e-388">Dessa värden kommer att krävas vid reservation av specifika ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-388">These values will be required during reservation of specific license plates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-389">Om du vill reservera ett visst ID-nummer måste du använda dataentiteten **orderallokerade reservation av ID-nummer**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-389">To reserve a specific license plate, you must use the **Order-committed reservations per license plate** data entity.</span></span> <span data-ttu-id="9eb0e-390">För att reservera en batchspårad artikel på ett visst ID-nummer kan du också använda sidan **Batchreservation**, som beskrivs i avsnittet [Ange detaljinformation om försäljningsorder](#sales-order-details).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-390">To reserve a batch-tracked item on a specific license plate, you can also use the **Batch reservation** page, as described in the [Enter sales order details](#sales-order-details) section.</span></span>
    >
    > <span data-ttu-id="9eb0e-391">Om du anger ID-numret direkt på försäljningsorderraden och bekräftar den i systemet, används inte bearbetning av lagerstyrning för raden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-391">If you enter the license plate directly on the sales order line and confirm it to the system, warehouse management processing won't be used for the line.</span></span>

1. <span data-ttu-id="9eb0e-392">Välj **Öppna i Microsoft Office**, välj **orderallokerade reservation av ID-nummer** och hämta filen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-392">Select **Open in Microsoft Office**, select **Order-committed reservations per license plate**, and download the file.</span></span>
1. <span data-ttu-id="9eb0e-393">Öppna den nedladdade filen i Excel och välj **skrivskyddet** för att tillåta att Excel-tillägget körs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-393">Open the downloaded file in Excel, and select **Enable editing** to enable the Excel add-in to run.</span></span>
1. <span data-ttu-id="9eb0e-394">Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-394">If you're running the Excel add-in for the first time, select **Trust this Add-in**.</span></span>
1. <span data-ttu-id="9eb0e-395">Om du uppmanas att logga in klickar du på **Logga in** och loggar sedan in med samma inloggningsuppgifter som du använde för att logga in på Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-395">If you're prompted to sign in, select **Sign in**, and then sign in by using the same credentials that you used to sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="9eb0e-396">Om du vill reservera en artikel på ett visst ID-nummer i Excel-tillägget väljer du **Ny** för att lägga till en reservationsrad och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-396">To reserve an item on a specific license plate, in the Excel add-in, select **New** to add a reservation line, and then set the following values:</span></span>

    - <span data-ttu-id="9eb0e-397">**Parti-ID:** ange värdet **parti-ID** som du hittade för försäljningsorderraden för *Artikel1*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-397">**Lot ID:** Enter the **Lot ID** value that you found for the sales order line for *Item1*.</span></span>
    - <span data-ttu-id="9eb0e-398">**ID-nummer:** *LP02*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-398">**License plate:** *LP02*</span></span>
    - <span data-ttu-id="9eb0e-399">**ReservedInventoryQuantity:** *10*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-399">**ReservedInventoryQuantity:** *10*</span></span>

1. <span data-ttu-id="9eb0e-400">Välj **Ny** för att lägga till en till reservationsrad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-400">Select **New** to add another reservation line, and set the following values:</span></span>

    - <span data-ttu-id="9eb0e-401">**Parti-ID:** ange värdet **parti-ID** som du hittade för försäljningsorderraden för *Artikel2*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-401">**Lot ID:** Enter the **Lot ID** value you found for the sales order line for *Item2*.</span></span>
    - <span data-ttu-id="9eb0e-402">**ID-nummer:** *LP02*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-402">**License plate:** *LP02*</span></span>
    - <span data-ttu-id="9eb0e-403">**ReservedInventoryQuantity:** *5*</span><span class="sxs-lookup"><span data-stu-id="9eb0e-403">**ReservedInventoryQuantity:** *5*</span></span>

1. <span data-ttu-id="9eb0e-404">I Excel-tillägget väljer du **publicera** för att skicka tillbaka informationen till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-404">In the Excel add-in, select **Publish** to send the data back to Supply Chain Management.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-405">Reservationsraden kommer endast att visas i systemet om publiceringen slutförts utan fel.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-405">The reservation line will appear in the system only if publishing is completed without errors.</span></span>

1. <span data-ttu-id="9eb0e-406">Gå tillbaka till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-406">Go back to Supply Chain Management.</span></span> 
1. <span data-ttu-id="9eb0e-407">Om du vill granska artikelns reservation väljer du snabbfliken **försäljningsorderrader** på menyn **Lager** välj **Underhåll \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-407">To review the item's reservation, on the **Sales order lines** FastTab, on the **Inventory** menu, select **Maintain \> Reservation**.</span></span> <span data-ttu-id="9eb0e-408">Observera att för försäljningsorderraden för *Aritikel1* är lagret på *10* reserverat och för försäljningsorderraden för *Artikel2* är lagret på *5* reserverat.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-408">Notice that, for the sales order line for *Item1*, inventory of *10* is reserved, and for the sales order line for *Item2*, inventory of *5* is reserved.</span></span>
1. <span data-ttu-id="9eb0e-409">Om du vill granska lagertransaktioner som är relaterade till reservationen för försäljningsorderraden på snabbfliken **försäljningsorderrader** väljer du menyn **Lager** och **Visa \> Transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-409">To review inventory transactions that are related to the sales order line reservation, on the **Sales order lines** FastTab, on the **Inventory** menu, select **View \> Transactions**.</span></span> <span data-ttu-id="9eb0e-410">Observera att det finns två transaktioner som är relaterade till reservationen: en där fältet **Referens** anges till *Försäljningsorder* och en där fältet **Referens** anges till *Orderallokerad reservation*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-410">Notice that there are two transactions that are related to the reservation: one where the **Reference** field is set to *Sales order* and one where the **Reference** field is set to *Order-committed reservation*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-411">En transaktion där fältet **Referens** anges till *Försäljningsorder* representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats** (plats, lagerställe och lagerstatus).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-411">A transaction where the **Reference** field is set to *Sales order* represents the order line reservation for inventory dimensions that are above the **Location** level (site, warehouse, and inventory status).</span></span> <span data-ttu-id="9eb0e-412">En transaktion där fältet **referens** är inställt på *Orderallokerad reservation* representerar orderradreservationen för den specifika ID-numret och platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-412">A transaction where the **Reference** field is set to *Order-committed reservation* represents the order line reservation for the specific license plate and location.</span></span>

1. <span data-ttu-id="9eb0e-413">För att frisläppa försäljningsorder i åtgärdsfönstret väljer du **Lagerställe** i gruppen **Åtgärder** välj **Släpp till distributionslager**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-413">To release the sales order, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a><span data-ttu-id="9eb0e-414">Granska och bearbeta lagerställearbete med ett orderallokerat ID-nummer tilldelat</span><span class="sxs-lookup"><span data-stu-id="9eb0e-414">Review and process warehouse work with order-committed license plates assigned</span></span>

1. <span data-ttu-id="9eb0e-415">På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Arbetsinformation**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-415">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Work details**.</span></span>

    <span data-ttu-id="9eb0e-416">När reservation görs för en specifik batch, använder systemet inte platsdirektiv när det skapar arbetet för försäljningsordern som använder reservation av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-416">As when reservation is done for a specific batch, the system doesn't use location directives when it creates the work for the sales order that uses license plate reservation.</span></span> <span data-ttu-id="9eb0e-417">Eftersom den orderallokerade reservationen anger alla lagerdimensioner, inklusive lagerstället, behöver inte platsdirektiven användas eftersom dessa lagerdimensioner bara registrerats i arbetet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-417">Because the order-committed reservation specifies all the inventory dimensions, including the location, location directives don't have to be used, because those inventory dimensions are just entered in the work.</span></span> <span data-ttu-id="9eb0e-418">De visas i avsnittet **från lagerdimensioner** på sidan **Arbetslagertransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-418">They are shown in the **From inventory dimensions** section on the **Work inventory transactions** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-419">När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på *Order-allokerad reservation* borttagen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-419">After the work is created, the item's inventory transaction where the **Reference** field is set to *Order-committed reservation* is removed.</span></span> <span data-ttu-id="9eb0e-420">Lagertransaktionen där fältet **Referens** anges till *Arbete* innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-420">The inventory transaction where the **Reference** field is set to *Work* now holds the physical reservation for all the quantity's inventory dimensions.</span></span>

1. <span data-ttu-id="9eb0e-421">Slutför plockning och placera arbetet på den mobila enheten med hjälp av ett menyalternativ där kryssrutan **Hantera efter ID-nummer** är markerad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-421">On the mobile device, finish picking and putting the work by using a menu item where the **Handle by license plate** check box is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eb0e-422">Med hjälp av funktionen **Hantera efter ID-nummer** kan du bearbeta hela ID-numret.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-422">The **Handle by license plate** functionality helps you process the whole license plate.</span></span> <span data-ttu-id="9eb0e-423">Om du måste bearbeta en del av ID-numret kan du inte använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-423">If you must process part of the license plate, you can't use this functionality.</span></span>
    >
    > <span data-ttu-id="9eb0e-424">Vi rekommenderar att du har separat arbete skapat för varje ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-424">We recommend that you have separate work generated for each license plate.</span></span> <span data-ttu-id="9eb0e-425">Om du vill uppnå det här resultatet använder du funktionen **Arbetsuppgiftshuvudet delas** på sidan **arbetsmall**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-425">To achieve this result, use the **Work header breaks** feature on the **Work template** page.</span></span>

    <span data-ttu-id="9eb0e-426">ID-nummer *LP02* plockas nu för försäljningsorderrader och placeras på platsen *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-426">License plate *LP02* is now picked for sales order lines and put to the *Baydoor* location.</span></span> <span data-ttu-id="9eb0e-427">I detta skede är den klar att lastas och skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-427">At this point, it's ready to be loaded and dispatched to the customer.</span></span>

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="9eb0e-428">Hantering av undantag av lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="9eb0e-428">Exception handling of warehouse work that has order-committed batch numbers</span></span>

<span data-ttu-id="9eb0e-429">Orderallokerade batchnummer för lagerarbete för plockning är underställt samma standardundantagshantering och åtgärder för lagerställe som normalt arbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-429">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="9eb0e-430">I allmänhet kan öppna arbete eller arbetsrad avbrytas, den kan avbrytas eftersom en användarplats är full, det kan tas bort och kan uppdateras på grund av en rörelse.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-430">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="9eb0e-431">På samma sätt kan plockad kvantitet av arbete som redan har slutförts minskas, eller så kan arbetet återföras.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-431">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="9eb0e-432">Följande nyckelregel används för alla dessa undantagsåtgärder: det batchnummer som har reserverats för kunden kan aldrig ersättas med ett annat batchnummer, men dess lagringsdimensioner (plats och registreringsskylt) kan ändras genom antingen manuell uppdatering av användaren eller automatiska uppdateringar i systemet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-432">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="9eb0e-433">Den automatiska uppdateringen baseras på samma slumpmässiga tilldelning av lagringsdimensioner som används när en specifik batch automatiskt reserverades men inga lagringsdimensioner har angetts.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-433">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="9eb0e-434">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="9eb0e-434">Example scenario</span></span>

<span data-ttu-id="9eb0e-435">Ett exempel på det här scenariot är en situation där arbetet med tidigare slutfört arbete avbryts med funktionen **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-435">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="9eb0e-436">I det här exemplet förutsätts det att du redan har utfört stegen som beskrivs i [exempelscenario: allokering av batchnummer](#Example-batch-allocation).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-436">This example assumes that you've already completed the steps that are described in [Example scenario: Batch number allocation](#Example-batch-allocation).</span></span> <span data-ttu-id="9eb0e-437">Det fortsätter från det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-437">It continues from that example.</span></span>

1. <span data-ttu-id="9eb0e-438">Gå till **Lagerstyrning** \> **Laster** \> **Aktiva laster**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-438">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="9eb0e-439">Välj den last som skapades i samband med leveransen av din försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-439">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="9eb0e-440">På snabbfliken **Läs in orderrader** väljer du **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-440">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="9eb0e-441">På sidan **minska plockad kvantitet** i fältet **Flytta till plats** väljer du **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-441">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="9eb0e-442">I fältet **Flytta till registreringsskylt** väljer du **LP33**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-442">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="9eb0e-443">I rutnätet skriver du **Lagerkvantitet där plockning ska hävas** anger du **10**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-443">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="9eb0e-444">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-444">Select **OK**.</span></span>

<span data-ttu-id="9eb0e-445">Här är resultaten av åtgärden för ej plockning:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-445">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="9eb0e-446">Status för det tidigare avslutade arbetet är inställd på **annullerat**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-446">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="9eb0e-447">Nytt arbete för typen **lagerrörelse** skapas för det ej plockade antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-447">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="9eb0e-448">Det här arbetet motsvarar flyttningen från platsen **Baydoor** till registreringsskylten **LP33** på plats **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-448">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="9eb0e-449">Status är inställt på **Stängd**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-449">The status is set to **Closed**.</span></span>
- <span data-ttu-id="9eb0e-450">Systemet omreserverar batchnumret som ursprungligen beställdes och tilldelar plats- och registreingsskylt-ID.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-450">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="9eb0e-451">(Den här processen motsvarar att köra funktionen **reservera rad** för orderraden för ett givet batchnummer).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-451">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="9eb0e-452">Som ett resultat visas batch **B11** som genomförd på snabbfliken **batchnummer för källrad** på sidan **Batch-reservation** och fältet **Reservation** innehåller antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-452">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="9eb0e-453">Dessutom är fältet **plats** inställt **FL-001** och fältet **registreringsskylt** är inställt på **LP11**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-453">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="9eb0e-454">(Du kan lägga till dessa fält i rutnätet om de inte visas.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-454">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="9eb0e-455">Följande register ger en översikt som visar hur systemet hanterar den beställda batchreservationen för specifika lageråtgärder.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-455">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="9eb0e-456">Om du vill tolka innehållet i tabellerna antar du att varje lageråtgärd körs i samband med befintligt lagerarbete som har sitt ursprung i en batchorder som har genomförts med order, eller att körningen av varje lageråtgärd påverkar arbete av den typen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-456">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-457">I dessa register visar kolumnen "Batchkvantitet är tillgänglig" om en batchkvantitet är tillgänglig utöver kvantiteten som antingen redan har reserverats för den aktuella orderallokerade reservationen eller redan har reserverats för det lagerställearbete som härstammar från reservationer av den typen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-457">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="9eb0e-458">Åsidosätt plockplatsen på det öppna arbetet</span><span class="sxs-lookup"><span data-stu-id="9eb0e-458">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-459">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-459">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-460">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-460">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-461">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-461">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-462">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-462">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-463">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-463">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-464">Alternativet <strong>Tillåt åsidosättning av plockplats</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-464">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="9eb0e-465">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-465">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-466">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerställeappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-466">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-467">Välj <strong>föreslå</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-467">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="9eb0e-468">Bekräfta den nya platsen som föreslås baserat på tillgängligheten för batchkvantitet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-468">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-469">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-469">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="9eb0e-470">Platsen på plockraden uppdateras till den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-470">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="9eb0e-471">(Om platsen är registreringsskyltkontrollerad, tilldelas en slumpmässig registreringsskylt till arbetslagertransaktionen och arbetaren kan välja från registreringsskylt som har den tillgängliga kvantiteten.)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-471">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="9eb0e-472">Om kvantiteten finns på fler än en registreringsskylt på den nya platsen, delas den ursprungliga plockningsraden på flera rader för att matcha varje registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-472">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-473">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-473">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-474">Nr</span><span class="sxs-lookup"><span data-stu-id="9eb0e-474">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-475">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerställeappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-475">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-476">Ange en plats manuellt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-476">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-477">Åtgärden <strong>åsidosätta plats</strong> är inte möjlig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-477">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="9eb0e-478">Den misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-478">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="9eb0e-479">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-479">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="9eb0e-480">Full knapp – dela en arbetsrad på grund av spill på användarplatsen</span><span class="sxs-lookup"><span data-stu-id="9eb0e-480">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-481">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-481">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-482">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-482">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-483">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-483">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-484">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-484">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-485">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-485">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9eb0e-486">Alternativet <strong>Tillåt delning av arbete</strong> är aktiverat på menyalternativet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-486">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="9eb0e-487">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-487">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-488">Välj menyalternativet <strong>Full</strong> i lagerställeappen när du bearbetar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-488">Select the <strong>Full</strong> menu item on the warehouse app when you process picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-489">I fältet <strong>Plockkvantitet</strong> ange den delkvantitet för att ange den fullständiga kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-489">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-490">I det aktuella arbetet uppdateras kvantiteten till den resterande kvantiteten som måste plockas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-490">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="9eb0e-491">Nytt arbete för plockad kvantitet skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-491">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="9eb0e-492">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-492">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="9eb0e-493">Minska den plockade kvantiteten färdigt arbete (från en last)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-493">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-494">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-494">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-495">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-495">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-496">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-496">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-497">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-497">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-498">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-498">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-499">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-499">Not applicable</span></span></td>
<td><span data-ttu-id="9eb0e-500">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-500">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-501">Öppna sidan <strong>minska plockad kvantitet</strong> kvantitet från lastraden.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-501">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="9eb0e-502">Ange den fulla kvantitet att häva plockning.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-502">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="9eb0e-503">Välj en "flytta till" plats/registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-503">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="9eb0e-504">Arbete som är kopplat till lastraden avbryts.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-504">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="9eb0e-505">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-505">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-506">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-506">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-507">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-507">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-508">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-508">No</span></span></td>
<td><span data-ttu-id="9eb0e-509">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-509">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-510">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-510">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-511">Kvantiteten reserveras för samma batch och för samma plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) som angavs under hävning av plockningen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-511">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="9eb0e-512">Flytta en artikel inom ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="9eb0e-512">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-513">Den här lageråtgärden kan bara användas i rörelse av typen **Process för att skapa arbete**, inte för rörelse per mall.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-513">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-514">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-514">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-515">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-515">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-516">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-516">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-517">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-517">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-518">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-518">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-519">Alternativet <strong>Tillåt flyttning av lager med associerat arbete</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-519">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="9eb0e-520">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-520">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-521">Starta en rörelse på lagerställeappen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-521">Start a movement on the warehouse app.</span></span></li>
<li><span data-ttu-id="9eb0e-522">Ange "från-" och "till"-platser.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-522">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-523">För allt befintligt arbete som påverkas av flyttningen uppdateras plockplatsen till den nya "till"-platsen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-523">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="9eb0e-524">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-524">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-525">Alla befintliga reservationer som påverkas av flyttningen av kvantiteten från den angivna platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-525">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-526">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-526">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-527">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-527">No</span></span></td>
<td><span data-ttu-id="9eb0e-528">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-528">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-529">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-529">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-530">Alla befintliga reservationer som påverkas av antalet transporter från den angivna platsen reserveras för samma batch och för den nya "till"-platsen och registreringsskylten (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-530">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="9eb0e-531">Återför den plockade kvantiteten färdigt arbete (från en last eller en påfyllnad)</span><span class="sxs-lookup"><span data-stu-id="9eb0e-531">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-532">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-532">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-533">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-533">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-534">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-534">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-535">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-535">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-536">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-536">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="9eb0e-537">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-537">Not applicable</span></span></td>
<td><span data-ttu-id="9eb0e-538">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-538">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-539">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-539">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="9eb0e-540">Välj alternativet <strong>Lämna artiklar på aktuell plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-540">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-541">Allt arbete som är kopplat till lasten avbryts.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-541">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="9eb0e-542">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-542">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-543">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-543">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-544">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-544">No</span></span></td>
<td><span data-ttu-id="9eb0e-545">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-545">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-546">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-546">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-547">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten lämnades vid återföring.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-547">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-548">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-548">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-549">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-549">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="9eb0e-550">Välj alternativet <strong>Tilldela artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-550">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-551">Aktuellt arbete är annullerat.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-551">The current work is canceled.</span></span></li>
<li><span data-ttu-id="9eb0e-552">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-552">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-553">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-553">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-554">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-554">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-555">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-555">No</span></span></td>
<td><span data-ttu-id="9eb0e-556">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-556">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-557">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-557">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-558">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten tilldelades till vid återföring.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-558">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-559">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-559">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-560">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-560">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="9eb0e-561">Välj alternativet <strong>Flytta artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-561">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-562">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-562">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="9eb0e-563">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-563">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-564">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-564">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-565">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-565">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="9eb0e-566">Välj alternativet <strong>Flytta artiklar baserat på platsdirektiv</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-566">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-567">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-567">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="9eb0e-568">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-568">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="9eb0e-569">Kort plockning av en kvantitet – registrera kvantiteten som fysiskt inte finns på plats/registreringsskylt medan du utför plockningsarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-569">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-570">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-570">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-571">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-571">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-572">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-572">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-573">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-573">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-574">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-574">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-575">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-575">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="9eb0e-576">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-576">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-577">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-577">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-578">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-578">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-579">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-579">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-580">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-580">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-581">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-581">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-582">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-582">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-583">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-583">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-584">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-584">No</span></span></td>
<td><span data-ttu-id="9eb0e-585">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-585">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-586">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-586">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="9eb0e-587">Det aktuella arbetet förblir öppet.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-587">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-588">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-588">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-589">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-589">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="9eb0e-590">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-590">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-591">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-591">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-592">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-592">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-593">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-593">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-594">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-594">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-595">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-595">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-596">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-596">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-597">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-597">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-598">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-598">No</span></span></td>
<td><span data-ttu-id="9eb0e-599">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-599">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-600">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-600">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-601">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen tas bort.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-601">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-602">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej/Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-602">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="9eb0e-603">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-603">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="9eb0e-604">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-604">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-605">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-605">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-606">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-606">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-607">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-607">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="9eb0e-608">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-608">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-609">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-609">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="9eb0e-610">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-610">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-611">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-611">The put line is canceled.</span></span></li>
<li><span data-ttu-id="9eb0e-612">En ny plockrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-612">A new pick line is created.</span></span> <span data-ttu-id="9eb0e-613">Den använder den plats/registreringsskylt som användaren har valt.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-613">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="9eb0e-614">En ny placeringsrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-614">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9eb0e-615">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-615">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-616">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-616">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-617">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-617">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="9eb0e-618">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-618">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="9eb0e-619">Nr</span><span class="sxs-lookup"><span data-stu-id="9eb0e-619">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-620">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-620">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-621">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-621">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-622">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-622">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-623">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-623">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="9eb0e-624">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-624">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-625">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-625">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="9eb0e-626">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-626">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="9eb0e-627">Nr</span><span class="sxs-lookup"><span data-stu-id="9eb0e-627">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-628">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-628">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-629">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-629">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-630">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-630">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="9eb0e-631">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-631">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-632">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-632">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="9eb0e-633">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-633">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-634">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-634">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9eb0e-635">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-635">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="9eb0e-636">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen/registreringsskylten tas bort.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-636">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-637">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Automatisk</strong>, <strong>Justera lager</strong> = <strong>Ja/Nej</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja/Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-637">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="9eb0e-638">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-638">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-639">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-639">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="9eb0e-640">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-640">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="9eb0e-641">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med automatisk omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-641">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-642">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-642">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="9eb0e-643">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-643">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="9eb0e-644">Ändra lagerstatus</span><span class="sxs-lookup"><span data-stu-id="9eb0e-644">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0e-645">Den här lageråtgärden kan utföras från flera startpunkter.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-645">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="9eb0e-646">I exemplet som visas här används åtgärden **Ändring av lagerstatus** på sidan **Behållning efter plats**.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-646">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9eb0e-647">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="9eb0e-647">Key setup parameter</span></span></th>
<th><span data-ttu-id="9eb0e-648">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="9eb0e-648">Batch quantity is available</span></span></th>
<th><span data-ttu-id="9eb0e-649">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="9eb0e-649">Key user steps</span></span></th>
<th><span data-ttu-id="9eb0e-650">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="9eb0e-650">Warehouse work</span></span></th>
<th><span data-ttu-id="9eb0e-651">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="9eb0e-651">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-652">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> är fältet <strong>ta bort reservationer och markeringar</strong> inställt på <strong>Reservationer</strong> eller <strong>Markeringar och reservationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-652">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="9eb0e-653">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-653">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-654">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-654">Select a specific location.</span></span></li>
<li><span data-ttu-id="9eb0e-655">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-655">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="9eb0e-656">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-656">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="9eb0e-657">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-657">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-658">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-658">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-659">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-659">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-660">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-660">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="9eb0e-661">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-661">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="9eb0e-662">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-662">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-663">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-663">No</span></span></td>
<td><span data-ttu-id="9eb0e-664">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-664">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-665">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-665">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9eb0e-666">Reservationen tas bort.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-666">The reservation is removed.</span></span></li>
<li><span data-ttu-id="9eb0e-667">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-667">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="9eb0e-668">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-668">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="9eb0e-669">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> anges fältet <strong>Ta bort reservationer och markeringar</strong> till <strong>Ingen</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-669">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="9eb0e-670">Ja</span><span class="sxs-lookup"><span data-stu-id="9eb0e-670">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9eb0e-671">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-671">Select a specific location.</span></span></li>
<li><span data-ttu-id="9eb0e-672">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="9eb0e-672">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="9eb0e-673">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-673">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="9eb0e-674">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-674">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="9eb0e-675">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-675">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="9eb0e-676">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-676">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="9eb0e-677">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-677">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9eb0e-678">Nej</span><span class="sxs-lookup"><span data-stu-id="9eb0e-678">No</span></span></td>
<td><span data-ttu-id="9eb0e-679">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-679">See the previous row.</span></span></td>
<td><span data-ttu-id="9eb0e-680">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-680">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="9eb0e-681">Ändringar i lagerstatus är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-681">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="9eb0e-682">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="9eb0e-682">Limitations</span></span>

- <span data-ttu-id="9eb0e-683">Den flexibla funktionen för dimensionsreservation på lagernivå stöder inte följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="9eb0e-683">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="9eb0e-684">Hantering av fångstvikt</span><span class="sxs-lookup"><span data-stu-id="9eb0e-684">Catch weight management</span></span>
    - <span data-ttu-id="9eb0e-685">Fysiskt negativt lager</span><span class="sxs-lookup"><span data-stu-id="9eb0e-685">Physical negative inventory</span></span>
    - <span data-ttu-id="9eb0e-686">Reservation mot beställda leveranser</span><span class="sxs-lookup"><span data-stu-id="9eb0e-686">Reservation against ordered supply</span></span>
    - <span data-ttu-id="9eb0e-687">Överföringsorder och plockning av råmaterial</span><span class="sxs-lookup"><span data-stu-id="9eb0e-687">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="9eb0e-688">Behållarens konsolideringsregel för paketering av direktivenhet har begränsningar.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-688">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="9eb0e-689">För orderallokerade reservationer rekommenderar vi att du inte använder uppbyggnadsmallar för behållare där fältet **Packa efter enhet för direktiv** är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-689">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="9eb0e-690">I den aktuella designen används inte platsdirektiv när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-690">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="9eb0e-691">Det innebär att endast den minsta enheten i enhetssekvensgruppen (lagerenheten) används under påfyllnadssteget skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="9eb0e-691">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
