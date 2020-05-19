---
title: Flexibel reservationspolicy för dimension på lagernivå
description: I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för företag att sälja batchspårade produkter och köra sin logistik som WMS-aktiverade operationer reservera specifika batchar för kundförsäljningsorder, även om den reservationssekvens som är kopplad till produkterna inte tillåter reservation av specifika batchar.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 6c462a87494c434a6047542d448a85b3bce9f769
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346478"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="408d8-103">Flexibel reservationspolicy för dimension på lagernivå</span><span class="sxs-lookup"><span data-stu-id="408d8-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="408d8-104">När en hierarki för lagerreservationer av typen "batch-under\[plats\]" associeras med produkter kan företag som säljer spårade produkter och kör sin logistik när operationer som har aktiverats för Microsoft Dynamics 365 lagerställehanteringssystem (WMS) inte kan reservera specifika partier för dessa produkter för kundförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="408d8-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="408d8-105">I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för dessa företag att reservera specifika batchar, även om produkterna är kopplade till reservationshierarkin "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="408d8-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="408d8-106">Lagerreservationshierarki</span><span class="sxs-lookup"><span data-stu-id="408d8-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="408d8-107">Det här avsnittet sammanfattar den befintliga lagerreservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="408d8-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="408d8-108">Den fokuserar på hur batchspårade och seriespårade artiklar hanteras.</span><span class="sxs-lookup"><span data-stu-id="408d8-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="408d8-109">Lagerreservationshierarkin avgör att när det gäller lagringsdimensioner har efterfrågeordern de obligatoriska dimensionerna för plats, lager och lagerstatus, medan lagerställelogiken är ansvarig för att tilldela en plats till de begärda kvantiteterna och reservera platsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="408d8-110">Med andra ord förväntas en efterfrågeorder i interaktionen mellan efterfrågeorder ordern och lagerställeåtgärder för att ange var ordern måste levereras från (dvs. vilken plats och lagerställe).</span><span class="sxs-lookup"><span data-stu-id="408d8-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="408d8-111">Lagerstället använder sig av sin logik för att hitta den begärda kvantiteten i dessa lagerlokaler.</span><span class="sxs-lookup"><span data-stu-id="408d8-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="408d8-112">Om du vill återspegla affärsverksamhetens driftsmodell, kan spårningsdimensioner (batch- och serienummer) bli mer flexibla.</span><span class="sxs-lookup"><span data-stu-id="408d8-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="408d8-113">En hierarki för lagerreservationer kan innehålla scenarier där följande villkor gäller:</span><span class="sxs-lookup"><span data-stu-id="408d8-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="408d8-114">Företaget använder sina lageroperationer för att hantera plockning av kvantiteter som har batch- eller serienummer efter det att kvantiteterna har hittats i lagringsutrymmet på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="408d8-115">Den här modellen kallas ofta för en *Batch-under\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="408d8-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="408d8-116">Den används vanligtvis när en produkts batch- eller serienummer-ID inte är viktig för de kunder som gör efterfrågan från det säljande företaget.</span><span class="sxs-lookup"><span data-stu-id="408d8-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="408d8-117">Om batch- eller serienummer är en del av en kundsorderspecifikation och registreras på efterfrågeorder, begränsas lageroperationerna som hittar kvantiteterna i lagerstället till de specifika nummer som krävs och tillåts inte att ändra dem.</span><span class="sxs-lookup"><span data-stu-id="408d8-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="408d8-118">Den här modellen kallas en *Batch-ovan\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="408d8-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="408d8-119">I dessa scenarier är utmaningen att bara en hierarki med lagerreservationer kan tilldelas varje frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="408d8-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="408d8-120">För att WMS ska hantera spårade objekt, efter att hierarkitilldelningen bestämmer när batch- eller serienumret ska reserveras (antingen när efterfrågan beställs eller under lagerplockningsarbetet), kan denna timing inte ändras på ad-hoc-basis.</span><span class="sxs-lookup"><span data-stu-id="408d8-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="408d8-121">Flexibel reservation för batchspårade artiklar</span><span class="sxs-lookup"><span data-stu-id="408d8-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="408d8-122">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="408d8-122">Business scenario</span></span>

<span data-ttu-id="408d8-123">I det här scenariot använder ett företag en lagerstrategi där färdiga varor spåras efter batchnummer.</span><span class="sxs-lookup"><span data-stu-id="408d8-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="408d8-124">Det här företaget använder också WMS-arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="408d8-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="408d8-125">Eftersom den här arbetsbelastningen har en välutrustad logik för planering och transport av lagerplocknings- och leveransoperationer för batchaktiverade artiklar, associeras de flesta av de färdiga artiklarna med en batch-under\[plats\] lagerreservationshierarki.</span><span class="sxs-lookup"><span data-stu-id="408d8-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="408d8-126">Fördelen med den här typen av driftsinställningar är att beslut (som är effektiva reservationsbeslut) om vilka batchar som ska plockas och var de ska skjutas upp tills lagerplockningsoperationer har startat.</span><span class="sxs-lookup"><span data-stu-id="408d8-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="408d8-127">De görs inte när kundens order har placerats.</span><span class="sxs-lookup"><span data-stu-id="408d8-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="408d8-128">Även om reservationshierarkin "batch-under\[plats\]" "betjänar företagets affärsmål", kräver många av företagets etablerade kunder samma batch som de tidigare köpte när de beställer om produkter.</span><span class="sxs-lookup"><span data-stu-id="408d8-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="408d8-129">Därför söker företaget efter flexibilitet på det sätt som reglerna för batchreservation hanteras, så att, beroende på kundernas efterfrågan för samma artikel, uppstår följande problem.</span><span class="sxs-lookup"><span data-stu-id="408d8-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="408d8-130">Ett batchnummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte ändras under lageroperationer och/eller tas av andra behov.</span><span class="sxs-lookup"><span data-stu-id="408d8-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="408d8-131">Det här beteendet garanterar att det batchnummer som beställs levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="408d8-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="408d8-132">Om batchnumret inte är viktigt för kunden, kan lageroperationerna bestämma ett batchnummer under plockningsarbetet efter att registrering och reservation av försäljningsordern har utförts.</span><span class="sxs-lookup"><span data-stu-id="408d8-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="408d8-133">Tillåta reservation av en specifik batch på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="408d8-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="408d8-134">För att tillgodose önskad flexibilitet i batchreservationens beteende för artiklar som är associerade med en "Batch-under\[plats\]" lagerreservationshierarki måste chefer markera kryssrutan **Tillåt reservation av efterfrågeorder** för nivån **Batch-nummer** på sidan **lagerreservationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="408d8-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Göra lagerreservationshierarkin flexibel](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="408d8-136">När nivån **Batch-nummer** i hierarkin väljs kommer alla dimensioner över den nivån och upp till nivån **plats** att väljas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="408d8-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="408d8-137">(Som standard är alla dimensioner ovanför nivån **plats** förvalda.) Det här beteendet återspeglar logiken där alla dimensioner i intervallet mellan batchnumret och lagerstället också reserveras automatiskt när du har reserverat ett specifikt batchnummer på orderraden.</span><span class="sxs-lookup"><span data-stu-id="408d8-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="408d8-138">Kryssrutan **Tillåt reservation på efterfrågerorder** gäller bara för de nivåer för reservationshierarkier som ligger under dimensionen lagerställe.</span><span class="sxs-lookup"><span data-stu-id="408d8-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="408d8-139">**Batchnummer** är den enda nivå i hierarkin som är öppen för den flexibla reservationsprincipen.</span><span class="sxs-lookup"><span data-stu-id="408d8-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="408d8-140">Med andra ord kan du inte markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **plats**, **ID-nummer** eller **serienummer**.</span><span class="sxs-lookup"><span data-stu-id="408d8-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="408d8-141">Om din reservationshierarki innehåller dimensionen för serienummer (som alltid måste vara under nivån **Batch-nummer**), och om du har aktiverat batch-specifik reservation för batch-numret kommer systemet att fortsätta hantera reservations- och plockningsoperationer för serienummer baserat på de regler som gäller för reservationsprincipen "Serie-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="408d8-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="408d8-142">Du kan när som helst tillåta batch-specifik reservation för en befintlig "batch-under\[plats\]" reservationshierarki i distributionen.</span><span class="sxs-lookup"><span data-stu-id="408d8-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="408d8-143">Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="408d8-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="408d8-144">Men kryssrutan **Tillåt reservation på efterfrågeorder** kan inte vara avmarkerad om lagertransaktioner för utleveranstyper **Reserverat beställt**, **Fysiskt reserverat** eller **Beställt** finns för en eller flera artiklar som är associerade med den reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="408d8-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="408d8-145">Om en artikels befintliga reservationshierarki inte tillåter kommandospecifikation på ordern kan du tilldela om den till en reservationshierarki som tillåter batch-specifikation, förutsatt att hierarkinivåstrukturen är densamma i båda hierarkierna.</span><span class="sxs-lookup"><span data-stu-id="408d8-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="408d8-146">Använd funktionen **ändra reservationshierarki för artiklar** för att utföra omtilldelningen.</span><span class="sxs-lookup"><span data-stu-id="408d8-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="408d8-147">Den här ändringen kan vara relevant när du vill förhindra flexibel batch-reservation för en delmängd av batch-spårade artiklar, men tillåter den för resten av produktportföljen.</span><span class="sxs-lookup"><span data-stu-id="408d8-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="408d8-148">Oavsett om du har markerat kryssrutan **Tillåt reservation på efterfrågeorder** om du inte vill reservera ett specifikt batchnummer för artikeln på en orderrad, gäller standardoperationslogiken för lagerställe som är giltig för en "Batch-under\[location\]" reservationhierarkin.</span><span class="sxs-lookup"><span data-stu-id="408d8-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="408d8-149">Reservera ett specifikt batchnummer för en kundorder</span><span class="sxs-lookup"><span data-stu-id="408d8-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="408d8-150">När en batch-spårad artikels "Batch-under\[plats\]" lagerreservationshierarki har ställts in för att tillåta reservation av specifika batchnummer på försäljningsorder, kan behandlare av försäljningsorder ta kundorder för samma artikel på något av följande sätt, beroende på kundens begäran:</span><span class="sxs-lookup"><span data-stu-id="408d8-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="408d8-151">**Ange orderdetaljer utan att ange ett batchnummer** – det här tillvägagångssättet ska användas när produktens batch-specifikation inte är viktig för kunden.</span><span class="sxs-lookup"><span data-stu-id="408d8-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="408d8-152">Alla befintliga processer som associeras med hantering av en order av den här typen i systemet förblir oförändradet.</span><span class="sxs-lookup"><span data-stu-id="408d8-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="408d8-153">Det behövs ingen ytterligare hänsyn till användarna.</span><span class="sxs-lookup"><span data-stu-id="408d8-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="408d8-154">**Ange orderdetaljer och reservera ett specifikt batchnummer** – den här metoden bör användas när kunden begär en specifik batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="408d8-155">Vanligtvis begär kunder en särskild batch när de ombeställer en produkt som de tidigare har köpt.</span><span class="sxs-lookup"><span data-stu-id="408d8-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="408d8-156">Denna typ av batch-specifik reservation kallas för *orderallokerad reservation*.</span><span class="sxs-lookup"><span data-stu-id="408d8-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="408d8-157">Följande regler gäller när kvantiteter bearbetas och ett batchnummer allokeras till en specifik order:</span><span class="sxs-lookup"><span data-stu-id="408d8-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="408d8-158">Om du vill tillåta reservation av ett specifikt batchnummer för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="408d8-159">I detta intervall ingår vanligtvis dimensionen registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="408d8-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="408d8-160">Platsdirektiv används inte när plockningsarbete skapas för en försäljningsrad som använder orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="408d8-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="408d8-161">Under lagerbearbetning av arbete för orderallokerade batchar, tillåts varken användaren eller systemet att ändra batchnumret.</span><span class="sxs-lookup"><span data-stu-id="408d8-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="408d8-162">(Bearbetningen omfattar undantagshantering.)</span><span class="sxs-lookup"><span data-stu-id="408d8-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="408d8-163">I följande exempel visas ett komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="408d8-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="408d8-164">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="408d8-164">Example scenario</span></span>

<span data-ttu-id="408d8-165">För det här exemplet måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="408d8-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="408d8-166">Ställ in en hierarki för lagerreservationer för att tillåta batch-specifika reservationer</span><span class="sxs-lookup"><span data-stu-id="408d8-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="408d8-167">Gå till **Lagerstyrning** \> **Inställningar** \> **Lager \> Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="408d8-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="408d8-168">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="408d8-168">Select **New**.</span></span>
3. <span data-ttu-id="408d8-169">I fältet **Namn** anger du ett namn (till exempel **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="408d8-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="408d8-170">I fältet **Beskrivning** anger du en beskrivning (till exempel, **Batch under flexibel**).</span><span class="sxs-lookup"><span data-stu-id="408d8-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="408d8-171">I fältet **Valda** väljer du **Serienummer** och **Ägare** och väljer sedan vänsterpilen för att flytta dem till fältet **Tillgängliga**.</span><span class="sxs-lookup"><span data-stu-id="408d8-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="408d8-172">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="408d8-172">Select **OK**.</span></span>
7. <span data-ttu-id="408d8-173">I raden för dimensionsnivån **Batch-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**.</span><span class="sxs-lookup"><span data-stu-id="408d8-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="408d8-174">Nivåerna **Registreringsskylt** och **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för dem.</span><span class="sxs-lookup"><span data-stu-id="408d8-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="408d8-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="408d8-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="408d8-176">Skapa en ny frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="408d8-176">Create a new released product</span></span>

1. <span data-ttu-id="408d8-177">Ställ in produktens tre huvuddataparametrar med hjälp av dessa värden:</span><span class="sxs-lookup"><span data-stu-id="408d8-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="408d8-178">I fältet **lagringsdimensionsgrupp** välj **Ware**.</span><span class="sxs-lookup"><span data-stu-id="408d8-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="408d8-179">I fältet **spårningsdimensionsgrupp** välj **Batch-Phy**.</span><span class="sxs-lookup"><span data-stu-id="408d8-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="408d8-180">I fältet **Reservationshierarki** välj **BatchFlex**.</span><span class="sxs-lookup"><span data-stu-id="408d8-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="408d8-181">Skapa två batchnummer, t.ex. **B11** och **B22**.</span><span class="sxs-lookup"><span data-stu-id="408d8-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="408d8-182">Lägg till artikelkvantiteter i lagerbehållning med hjälp av följande värden.</span><span class="sxs-lookup"><span data-stu-id="408d8-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="408d8-183">Distributionslager</span><span class="sxs-lookup"><span data-stu-id="408d8-183">Warehouse</span></span> | <span data-ttu-id="408d8-184">Batchnummer</span><span class="sxs-lookup"><span data-stu-id="408d8-184">Batch number</span></span> | <span data-ttu-id="408d8-185">Plats</span><span class="sxs-lookup"><span data-stu-id="408d8-185">Location</span></span> | <span data-ttu-id="408d8-186">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="408d8-186">License plate</span></span> | <span data-ttu-id="408d8-187">Antal</span><span class="sxs-lookup"><span data-stu-id="408d8-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="408d8-188">24</span><span class="sxs-lookup"><span data-stu-id="408d8-188">24</span></span>        | <span data-ttu-id="408d8-189">B11</span><span class="sxs-lookup"><span data-stu-id="408d8-189">B11</span></span>          | <span data-ttu-id="408d8-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="408d8-190">BULK-001</span></span> | <span data-ttu-id="408d8-191">Ingen</span><span class="sxs-lookup"><span data-stu-id="408d8-191">None</span></span>          | <span data-ttu-id="408d8-192">10</span><span class="sxs-lookup"><span data-stu-id="408d8-192">10</span></span>       |
    | <span data-ttu-id="408d8-193">24</span><span class="sxs-lookup"><span data-stu-id="408d8-193">24</span></span>        | <span data-ttu-id="408d8-194">B11</span><span class="sxs-lookup"><span data-stu-id="408d8-194">B11</span></span>          | <span data-ttu-id="408d8-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="408d8-195">FL-001</span></span>   | <span data-ttu-id="408d8-196">LP11</span><span class="sxs-lookup"><span data-stu-id="408d8-196">LP11</span></span>          | <span data-ttu-id="408d8-197">10</span><span class="sxs-lookup"><span data-stu-id="408d8-197">10</span></span>       |
    | <span data-ttu-id="408d8-198">24</span><span class="sxs-lookup"><span data-stu-id="408d8-198">24</span></span>        | <span data-ttu-id="408d8-199">B22</span><span class="sxs-lookup"><span data-stu-id="408d8-199">B22</span></span>          | <span data-ttu-id="408d8-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="408d8-200">FL-002</span></span>   | <span data-ttu-id="408d8-201">LP22</span><span class="sxs-lookup"><span data-stu-id="408d8-201">LP22</span></span>          | <span data-ttu-id="408d8-202">10</span><span class="sxs-lookup"><span data-stu-id="408d8-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="408d8-203">Ange försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="408d8-203">Enter sales order details</span></span>

1. <span data-ttu-id="408d8-204">Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="408d8-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="408d8-205">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="408d8-205">Select **New**.</span></span>
3. <span data-ttu-id="408d8-206">I försäljningsorderns rubrik, i fältet **Kundkonto** ange **US-003**.</span><span class="sxs-lookup"><span data-stu-id="408d8-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="408d8-207">Lägg till en rad för den nya artikeln och ange **10** som kvantitet.</span><span class="sxs-lookup"><span data-stu-id="408d8-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="408d8-208">Se till att fältet **Lagerställe** anges till **24**.</span><span class="sxs-lookup"><span data-stu-id="408d8-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="408d8-209">På snabbfliken **försäljningsorderrader** välj **lager** och sedan i gruppen **underhåll** välj **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="408d8-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="408d8-210">Sidan **Batch-reservation** visar en lista över batchar som är tillgängliga för reservation för orderraden.</span><span class="sxs-lookup"><span data-stu-id="408d8-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="408d8-211">I det här exemplet visas ett antal på **20** för batchnummer **B11** och kvantiteten **10** för batchnummer **B22**.</span><span class="sxs-lookup"><span data-stu-id="408d8-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="408d8-212">Observera att du inte kan komma åt sidan **Batch-reservation** från en rad om den raden är associerad med "Batch-under\[plats\]" reservationshierarki om den inte har ställts in för att tillåta batch-specifik reservation.</span><span class="sxs-lookup"><span data-stu-id="408d8-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="408d8-213">Om du vill reservera en specifik batch för en försäljningsorder måste du använda sidan **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="408d8-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="408d8-214">Om du anger batchnumret direkt på försäljningsorderraden, kommer systemet att fungera som om du har angett ett specifikt batchvärde för ett objekt som omfattas av "Batch-under\[plats\]" reservationspolicy.</span><span class="sxs-lookup"><span data-stu-id="408d8-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="408d8-215">När du sparar raden visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="408d8-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="408d8-216">Om du bekräftar att batchnumret ska anges direkt på orderraden hanteras inte raden av den normala lagerstyrningslogiken.</span><span class="sxs-lookup"><span data-stu-id="408d8-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="408d8-217">Om du reserverar kvantiteten från sidan **Reservation** kommer ingen specifik batch att reserveras och körningen av lagerställeoperationer för raden följer reglerna som är tillämpliga under reservationspolicyn "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="408d8-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="408d8-218">Den här sidan fungerar vanligtvis på samma sätt och interagerar med artiklar som har en associerad reservationssekvens för typen "Batch-ovan\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="408d8-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="408d8-219">Följande undantag gäller emellertid:</span><span class="sxs-lookup"><span data-stu-id="408d8-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="408d8-220">Snabbfliken **batchnummer för källrad** visar de batchnummer som har reserverats för orderraden.</span><span class="sxs-lookup"><span data-stu-id="408d8-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="408d8-221">Batchvärdet i rutnätet visas under hela orderradens uppfyllandecykel, inklusive faserna för lagerbearbetning.</span><span class="sxs-lookup"><span data-stu-id="408d8-221">The batch values in the grid will be shown throughout the fulfilment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="408d8-222">På snabbfliken **översikt** visas däremot en reservation på ordinarie orderrad (dvs. reservation som görs för dimensionerna över nivån **plats**) i rutnätet upp till punkten när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="408d8-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="408d8-223">Arbetsenheten tar över radreservationen och radreservationen visas inte längre på sidan.</span><span class="sxs-lookup"><span data-stu-id="408d8-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="408d8-224">Snabbfliken **batchnummer för källrader** används för att garantera att försäljningsorderns handläggare kan visa de batchnummer som har utfästs till kundens order när som helst under livscykeln, upp till fakturering.</span><span class="sxs-lookup"><span data-stu-id="408d8-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="408d8-225">Förutom att reservera en viss batch kan han eller hon manuellt välja batchens specifika plats och licensskylt i stället för att låta systemet automatiskt välja dem.</span><span class="sxs-lookup"><span data-stu-id="408d8-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="408d8-226">Denna kapacitet är relaterad till designen av mekanismen för orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="408d8-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="408d8-227">Som nämnts tidigare, när ett specifikt batchnummer reserveras för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="408d8-228">Därför kommer lagerstället att ha samma lagringsdimensioner som har reserverats av de användare som arbetade med ordern, och den kanske inte alltid representerar den placering av artikellagring som är praktiskt eller till och med möjlig för plockningsoperationer.</span><span class="sxs-lookup"><span data-stu-id="408d8-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="408d8-229">Om orderhandläggarna känner till begränsningarna i lagerställena, kanske de vill välja de specifika platserna och licensskyltarna manuellt när de reserverar en batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="408d8-230">I det här fallet måste användaren använda funktionen för **visningsdimensioner** i sidhuvudet och måste lägga till platsen och licensskylten i rutnätet på snabbfliken **översikt**.</span><span class="sxs-lookup"><span data-stu-id="408d8-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="408d8-231">På sidan **Batch-reservation** välj raden för batch **B11** och välj sedan **reservera rad**.</span><span class="sxs-lookup"><span data-stu-id="408d8-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="408d8-232">Det finns ingen särskild logik för att tilldela platser och licensskyltarna vid automatisk reservation.</span><span class="sxs-lookup"><span data-stu-id="408d8-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="408d8-233">Du kan ange kvantiteten manuellt i fältet **reservation**.</span><span class="sxs-lookup"><span data-stu-id="408d8-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="408d8-234">Observera att snabbfliken **batchnummer för källrad**, batch **B11** visas som **utfäst**.</span><span class="sxs-lookup"><span data-stu-id="408d8-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Utfästa ett specifikt batchnummer på en försäljningsorderrad på sidan batch-reservation](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="408d8-236">Det går att utföra reservationer av kvantiteten på en försäljningsorderrad i flera batchar.</span><span class="sxs-lookup"><span data-stu-id="408d8-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="408d8-237">På samma sätt kan reservation av samma batch göras mot flera platser och licensskyltar (om licensskyltar är aktiverade för platserna).</span><span class="sxs-lookup"><span data-stu-id="408d8-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="408d8-238">Reservation av en specifik batch för kvantiteten på en försäljningsorderrad kan också vara del.</span><span class="sxs-lookup"><span data-stu-id="408d8-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="408d8-239">Den totala kvantiteten 100 enheter kan till exempel reserveras så att en specifik batch har allokerats till 20 enheter, medan 80 enheter reserveras på platsen och lagerställenivåer för någon tillgänglig batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="408d8-240">I det här fallet hanterar WMS plockningsoperationer med hjälp av två separata arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="408d8-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="408d8-241">Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="408d8-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="408d8-242">Markera artikeln och välj sedan **hantera lager** \> **visa** \> **transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="408d8-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Order-allokerad reservation som en lagertransaktionstyp](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="408d8-244">Granska artikelns lagertransaktioner som hör till försäljningsorderradens reservation.</span><span class="sxs-lookup"><span data-stu-id="408d8-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="408d8-245">En transaktion där fältet **Referens** anges till **Försäljningsorder** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats**.</span><span class="sxs-lookup"><span data-stu-id="408d8-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="408d8-246">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner plats, lagerställe och lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="408d8-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="408d8-247">En transaktion där fältet**Referens** anges till **Orderallokerad reservation** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för den specifika batchen och alla lagerdimensioner ovanför.</span><span class="sxs-lookup"><span data-stu-id="408d8-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="408d8-248">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner batch-nummer och plats.</span><span class="sxs-lookup"><span data-stu-id="408d8-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="408d8-249">I det här exemplet är platsen **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="408d8-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="408d8-250">Välj i försäljningsorderhuvudet **Lagerställe** \> **Åtgärder** \> **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="408d8-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="408d8-251">Orderraden är nu vågad och en last och ett arbete skapas.</span><span class="sxs-lookup"><span data-stu-id="408d8-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="408d8-252">Granska och bearbeta lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="408d8-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="408d8-253">På snabbfliken **Försäljningsorderrader** välj **Lagerställe** \> **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="408d8-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="408d8-254">Det arbete som hanterar plockoperationen för batchkvantiteter som har bekräftats till försäljningsorderraden har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="408d8-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="408d8-255">Om du vill skapa arbete använder systemet arbetsmallar men inte platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="408d8-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="408d8-256">Alla standardinställningar som definieras för arbetsmallar, t.ex. ett maximalt antal plockningsrader eller en specifik måttenhet, används för att bestämma när nytt arbete ska skapas.</span><span class="sxs-lookup"><span data-stu-id="408d8-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="408d8-257">Reglerna som är kopplade till platsdirektiv för identifiering av plockningsplatser beaktas dock inte eftersom den order som genomförts redan anger alla lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="408d8-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="408d8-258">Dessa lagerdimensioner inkluderar dimensionerna på lagerställets lagernivå.</span><span class="sxs-lookup"><span data-stu-id="408d8-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="408d8-259">Därför ärver arbetet dessa dimensioner utan att behöva konsultera platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="408d8-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="408d8-260">Batchnumret visas inte på plockningsraden (som är fallet för den arbetsrad som skapas för en artikel som har en motsvarande "batch-ovan\[plats\]" reservationshierarki.) I stället visas batchnummer från och alla andra lagringsdimensioner på arbetsradens jobblagertransaktion som refereras från de associerade lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="408d8-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Lagerställets lagertransaktion för arbete som härrör från en reservation som har genomförts av order](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="408d8-262">När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på **Order-allokerad reservation** borttagen.</span><span class="sxs-lookup"><span data-stu-id="408d8-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="408d8-263">Lagertransaktionen där fältet **Referens** anges till **Arbete** innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="408d8-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="408d8-264">Lageroperationer kan fortsätta för att hantera utförande av arbetet på vanligt sätt.</span><span class="sxs-lookup"><span data-stu-id="408d8-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="408d8-265">Men instruktionerna på den mobila enheten instruerar arbetaren att välja ett specifikt batchnummer.</span><span class="sxs-lookup"><span data-stu-id="408d8-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="408d8-266">I lagermiljöer där platser är registreringsskylt – styrs efter att en arbetare har nått en plats som lagrar samma batch på registreringsskyltar, kan han eller hon välja från alla registreringsskyltar som inte redan har reserverats (t.ex. av en annan order-allokerad reservation eller arbete som härrör från en reservation av den typen.)</span><span class="sxs-lookup"><span data-stu-id="408d8-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="408d8-267">Om det blir opraktiskt att plocka från den plats som anges på arbetsraden, kan lagerställets operatörer använda någon av följande åtgärder för att dirigera om plockning av en viss batch:</span><span class="sxs-lookup"><span data-stu-id="408d8-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="408d8-268">Standard är åtgärden **åsidosätta plats** på en mobil enhet (förutsatt att inställningen för lagerarbetare **Tillåt åsidosättning av plockplats** är aktiverad)</span><span class="sxs-lookup"><span data-stu-id="408d8-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="408d8-269">Åtgärden **ändra plats** på sidan **information om arbetslista**.</span><span class="sxs-lookup"><span data-stu-id="408d8-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="408d8-270">Slutför plockningen på den mobila enheten och sätt in arbetet.</span><span class="sxs-lookup"><span data-stu-id="408d8-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="408d8-271">Kvantiteten **10** för batchnummer **B11** har nu plockats för försäljningsorderraden och placerats på platsen **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="408d8-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="408d8-272">I detta skede är den klar att lastas på lastbilen och skickas till kundens adress.</span><span class="sxs-lookup"><span data-stu-id="408d8-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a><span data-ttu-id="408d8-273">Hantering av undantag av lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="408d8-273">Exception handling of warehouse work thas has order-committed batch numbers</span></span>

<span data-ttu-id="408d8-274">Orderallokerade batchnummer för lagerarbete för plockning är underställt samma standardundantagshantering och åtgärder för lagerställe som normalt arbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="408d8-275">I allmänhet kan öppna arbete eller arbetsrad avbrytas, den kan avbrytas eftersom en användarplats är full, det kan tas bort och kan uppdateras på grund av en rörelse.</span><span class="sxs-lookup"><span data-stu-id="408d8-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="408d8-276">På samma sätt kan plockad kvantitet av arbete som redan har slutförts minskas, eller så kan arbetet återföras.</span><span class="sxs-lookup"><span data-stu-id="408d8-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="408d8-277">Följande nyckelregel används för alla dessa undantagsåtgärder: det batchnummer som har reserverats för kunden kan aldrig ersättas med ett annat batchnummer, men dess lagringsdimensioner (plats och registreringsskylt) kan ändras genom antingen manuell uppdatering av användaren eller automatiska uppdateringar i systemet.</span><span class="sxs-lookup"><span data-stu-id="408d8-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="408d8-278">Den automatiska uppdateringen baseras på samma slumpmässiga tilldelning av lagringsdimensioner som används när en specifik batch automatiskt reserverades men inga lagringsdimensioner har angetts.</span><span class="sxs-lookup"><span data-stu-id="408d8-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="408d8-279">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="408d8-279">Example scenario</span></span>

<span data-ttu-id="408d8-280">Ett exempel på det här scenariot är en situation där arbetet med tidigare slutfört arbete avbryts med funktionen **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="408d8-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="408d8-281">I det här exemplet fortsätter det föregående exemplet i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="408d8-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="408d8-282">Gå till **Lagerstyrning** \> **Laster** \> **Aktiva laster**.</span><span class="sxs-lookup"><span data-stu-id="408d8-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="408d8-283">Välj den last som skapades i samband med leveransen av din försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="408d8-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="408d8-284">På snabbfliken **Läs in orderrader** väljer du **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="408d8-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="408d8-285">På sidan **minska plockad kvantitet** i fältet **Flytta till plats** väljer du **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="408d8-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="408d8-286">I fältet **Flytta till registreringsskylt** väljer du **LP33**.</span><span class="sxs-lookup"><span data-stu-id="408d8-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="408d8-287">I rutnätet skriver du **Lagerkvantitet där plockning ska hävas** anger du **10**.</span><span class="sxs-lookup"><span data-stu-id="408d8-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="408d8-288">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="408d8-288">Select **OK**.</span></span>

<span data-ttu-id="408d8-289">Här är resultaten av åtgärden för ej plockning:</span><span class="sxs-lookup"><span data-stu-id="408d8-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="408d8-290">Status för det tidigare avslutade arbetet är inställd på **annullerat**.</span><span class="sxs-lookup"><span data-stu-id="408d8-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="408d8-291">Nytt arbete för typen **lagerrörelse** skapas för det ej plockade antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="408d8-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="408d8-292">Det här arbetet motsvarar flyttningen från platsen **Baydoor** till registreringsskylten **LP33** på plats **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="408d8-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="408d8-293">Status är inställt på **Stängd**.</span><span class="sxs-lookup"><span data-stu-id="408d8-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="408d8-294">Systemet omreserverar batchnumret som ursprungligen beställdes och tilldelar plats- och registreingsskylt-ID.</span><span class="sxs-lookup"><span data-stu-id="408d8-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="408d8-295">(Den här processen motsvarar att köra funktionen **reservera rad** för orderraden för ett givet batchnummer).</span><span class="sxs-lookup"><span data-stu-id="408d8-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="408d8-296">Som ett resultat visas batch **B11** som genomförd på snabbfliken **batchnummer för källrad** på sidan **Batch-reservation** och fältet **Reservation** innehåller antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="408d8-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="408d8-297">Dessutom är fältet **plats** inställt **FL-001** och fältet **registreringsskylt** är inställt på **LP11**.</span><span class="sxs-lookup"><span data-stu-id="408d8-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="408d8-298">(Du kan lägga till dessa fält i rutnätet om de inte visas.)</span><span class="sxs-lookup"><span data-stu-id="408d8-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="408d8-299">Följande register ger en översikt som visar hur systemet hanterar den beställda batchreservationen för specifika lageråtgärder.</span><span class="sxs-lookup"><span data-stu-id="408d8-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="408d8-300">Om du vill tolka innehållet i tabellerna antar du att varje lageråtgärd körs i samband med befintligt lagerarbete som har sitt ursprung i en batchorder som har genomförts med order, eller att körningen av varje lageråtgärd påverkar arbete av den typen.</span><span class="sxs-lookup"><span data-stu-id="408d8-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="408d8-301">I dessa register visar kolumnen "Batchkvantitet är tillgänglig" om en batchkvantitet är tillgänglig utöver kvantiteten som antingen redan har reserverats för den aktuella orderallokerade reservationen eller redan har reserverats för det lagerställearbete som härstammar från reservationer av den typen.</span><span class="sxs-lookup"><span data-stu-id="408d8-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="408d8-302">Åsidosätt plockplatsen på det öppna arbetet</span><span class="sxs-lookup"><span data-stu-id="408d8-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-303">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-304">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-305">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-305">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-306">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-306">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-307">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-308">Alternativet <strong>Tillåt åsidosättning av plockplats</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="408d8-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="408d8-309">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-310">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerstyrningsappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-310">Select the <strong>Override location</strong> menu item on the warehousing app when you start picking work.</span></span></li>
<li><span data-ttu-id="408d8-311">Välj <strong>föreslå</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="408d8-312">Bekräfta den nya platsen som föreslås baserat på tillgängligheten för batchkvantitet.</span><span class="sxs-lookup"><span data-stu-id="408d8-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-313">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="408d8-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="408d8-314">Platsen på plockraden uppdateras till den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="408d8-315">(Om platsen är registreringsskyltkontrollerad, tilldelas en slumpmässig registreringsskylt till arbetslagertransaktionen och arbetaren kan välja från registreringsskylt som har den tillgängliga kvantiteten.)</span><span class="sxs-lookup"><span data-stu-id="408d8-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="408d8-316">Om kvantiteten finns på fler än en registreringsskylt på den nya platsen, delas den ursprungliga plockningsraden på flera rader för att matcha varje registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="408d8-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-317">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="408d8-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-318">Nr</span><span class="sxs-lookup"><span data-stu-id="408d8-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-319">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerstyrningsappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-319">Select the <strong>Override location</strong> menu item on the warehousing app when you start picking work.</span></span></li>
<li><span data-ttu-id="408d8-320">Ange en plats manuellt.</span><span class="sxs-lookup"><span data-stu-id="408d8-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-321">Åtgärden <strong>åsidosätta plats</strong> är inte möjlig.</span><span class="sxs-lookup"><span data-stu-id="408d8-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="408d8-322">Den misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="408d8-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="408d8-323">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="408d8-324">Full knapp – dela en arbetsrad på grund av spill på användarplatsen</span><span class="sxs-lookup"><span data-stu-id="408d8-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-325">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-326">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-327">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-327">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-328">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-328">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-329">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="408d8-330">Alternativet <strong>Tillåt delning av arbete</strong> är aktiverat på menyalternativet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="408d8-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="408d8-331">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="408d8-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-332">Välj menyalternativet <strong>Full</strong> i lagerstyrningsappen när du bearbetar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-332">Select the <strong>Full</strong> menu item on the warehousing app when you process picking work.</span></span></li>
<li><span data-ttu-id="408d8-333">I fältet <strong>Plockkvantitet</strong> ange den delkvantitet för att ange den fullständiga kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="408d8-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-334">I det aktuella arbetet uppdateras kvantiteten till den resterande kvantiteten som måste plockas.</span><span class="sxs-lookup"><span data-stu-id="408d8-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="408d8-335">Nytt arbete för plockad kvantitet skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="408d8-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="408d8-336">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="408d8-337">Minska den plockade kvantiteten färdigt arbete (från en last)</span><span class="sxs-lookup"><span data-stu-id="408d8-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-338">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-339">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-340">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-340">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-341">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-341">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-342">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-343">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-343">Not applicable</span></span></td>
<td><span data-ttu-id="408d8-344">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-345">Öppna sidan <strong>minska plockad kvantitet</strong> kvantitet från lastraden.</span><span class="sxs-lookup"><span data-stu-id="408d8-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="408d8-346">Ange den fulla kvantitet att häva plockning.</span><span class="sxs-lookup"><span data-stu-id="408d8-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="408d8-347">Välj en "flytta till" plats/registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="408d8-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="408d8-348">Arbete som är kopplat till lastraden avbryts.</span><span class="sxs-lookup"><span data-stu-id="408d8-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="408d8-349">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="408d8-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-350">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-351">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-352">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-352">No</span></span></td>
<td><span data-ttu-id="408d8-353">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-353">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-354">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-354">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-355">Kvantiteten reserveras för samma batch och för samma plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) som angavs under hävning av plockningen.</span><span class="sxs-lookup"><span data-stu-id="408d8-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="408d8-356">Flytta en artikel inom ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="408d8-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="408d8-357">Den här lageråtgärden kan bara användas i rörelse av typen **Process för att skapa arbete**, inte för rörelse per mall.</span><span class="sxs-lookup"><span data-stu-id="408d8-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-358">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-359">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-360">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-360">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-361">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-361">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-362">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-363">Alternativet <strong>Tillåt flyttning av lager med associerat arbete</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="408d8-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="408d8-364">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-365">Starta en rörelse på lagerstyrningsappen.</span><span class="sxs-lookup"><span data-stu-id="408d8-365">Start a movement on the warehousing app.</span></span></li>
<li><span data-ttu-id="408d8-366">Ange "från-" och "till"-platser.</span><span class="sxs-lookup"><span data-stu-id="408d8-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="408d8-367">För allt befintligt arbete som påverkas av flyttningen uppdateras plockplatsen till den nya "till"-platsen.</span><span class="sxs-lookup"><span data-stu-id="408d8-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="408d8-368">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="408d8-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-369">Alla befintliga reservationer som påverkas av flyttningen av kvantiteten från den angivna platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-370">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-371">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-371">No</span></span></td>
<td><span data-ttu-id="408d8-372">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-372">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-373">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-373">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-374">Alla befintliga reservationer som påverkas av antalet transporter från den angivna platsen reserveras för samma batch och för den nya "till"-platsen och registreringsskylten (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="408d8-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="408d8-375">Återför den plockade kvantiteten färdigt arbete (från en last eller en påfyllnad)</span><span class="sxs-lookup"><span data-stu-id="408d8-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-376">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-377">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-378">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-378">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-379">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-379">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-380">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="408d8-381">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-381">Not applicable</span></span></td>
<td><span data-ttu-id="408d8-382">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-383">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="408d8-384">Välj alternativet <strong>Lämna artiklar på aktuell plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="408d8-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-385">Allt arbete som är kopplat till lasten avbryts.</span><span class="sxs-lookup"><span data-stu-id="408d8-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="408d8-386">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-387">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-388">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-388">No</span></span></td>
<td><span data-ttu-id="408d8-389">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-389">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-390">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-390">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-391">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten lämnades vid återföring.</span><span class="sxs-lookup"><span data-stu-id="408d8-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-392">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-393">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="408d8-394">Välj alternativet <strong>Tilldela artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="408d8-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-395">Aktuellt arbete är annullerat.</span><span class="sxs-lookup"><span data-stu-id="408d8-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="408d8-396">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="408d8-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-397">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-398">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-399">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-399">No</span></span></td>
<td><span data-ttu-id="408d8-400">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-400">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-401">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-401">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-402">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten tilldelades till vid återföring.</span><span class="sxs-lookup"><span data-stu-id="408d8-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-403">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-404">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="408d8-405">Välj alternativet <strong>Flytta artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="408d8-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-406">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="408d8-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="408d8-407">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-408">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-409">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="408d8-410">Välj alternativet <strong>Flytta artiklar baserat på platsdirektiv</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="408d8-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-411">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="408d8-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="408d8-412">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="408d8-413">Kort plockning av en kvantitet – registrera kvantiteten som fysiskt inte finns på plats/registreringsskylt medan du utför plockningsarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-414">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-415">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-416">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-416">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-417">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-417">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-418">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-419">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="408d8-420">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-421">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-421">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-422">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-423">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-424">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="408d8-425">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="408d8-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-426">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-427">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-428">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-428">No</span></span></td>
<td><span data-ttu-id="408d8-429">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="408d8-430">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="408d8-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="408d8-431">Det aktuella arbetet förblir öppet.</span><span class="sxs-lookup"><span data-stu-id="408d8-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-432">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-433">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="408d8-434">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-435">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-435">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-436">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-437">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-438">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="408d8-439">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="408d8-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-440">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-441">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-442">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-442">No</span></span></td>
<td><span data-ttu-id="408d8-443">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-443">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-444">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-444">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-445">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen tas bort.</span><span class="sxs-lookup"><span data-stu-id="408d8-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-446">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej/Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="408d8-447">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="408d8-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="408d8-448">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-449">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-449">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-450">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-451">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="408d8-452">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="408d8-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-453">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="408d8-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="408d8-454">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="408d8-455">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="408d8-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="408d8-456">En ny plockrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="408d8-456">A new pick line is created.</span></span> <span data-ttu-id="408d8-457">Den använder den plats/registreringsskylt som användaren har valt.</span><span class="sxs-lookup"><span data-stu-id="408d8-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="408d8-458">En ny placeringsrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="408d8-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="408d8-459">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="408d8-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-460">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-461">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="408d8-462">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="408d8-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="408d8-463">Nr</span><span class="sxs-lookup"><span data-stu-id="408d8-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-464">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-464">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-465">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-466">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-467">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="408d8-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="408d8-468">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="408d8-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-469">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="408d8-470">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="408d8-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="408d8-471">Nr</span><span class="sxs-lookup"><span data-stu-id="408d8-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-472">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-472">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-473">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-474">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="408d8-475">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="408d8-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="408d8-476">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="408d8-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="408d8-477">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="408d8-478">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="408d8-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="408d8-479">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="408d8-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="408d8-480">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen/registreringsskylten tas bort.</span><span class="sxs-lookup"><span data-stu-id="408d8-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-481">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Automatisk</strong>, <strong>Justera lager</strong> = <strong>Ja/Nej</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja/Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="408d8-482">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="408d8-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-483">Välj menyalternativet <strong>Kort plockning</strong> i lagerstyrningsappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-483">Select the <strong>Shortpick</strong> menu item on the warehousing app when you run picking work.</span></span></li>
<li><span data-ttu-id="408d8-484">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="408d8-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="408d8-485">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med automatisk omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-486">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="408d8-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="408d8-487">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="408d8-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="408d8-488">Ändra lagerstatus</span><span class="sxs-lookup"><span data-stu-id="408d8-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="408d8-489">Den här lageråtgärden kan utföras från flera startpunkter.</span><span class="sxs-lookup"><span data-stu-id="408d8-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="408d8-490">I exemplet som visas här används åtgärden **Ändring av lagerstatus** på sidan **Behållning efter plats**.</span><span class="sxs-lookup"><span data-stu-id="408d8-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="408d8-491">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="408d8-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="408d8-492">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="408d8-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="408d8-493">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="408d8-493">Key user steps</span></span></th>
<th><span data-ttu-id="408d8-494">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="408d8-494">Warehouse work</span></span></th>
<th><span data-ttu-id="408d8-495">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="408d8-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-496">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> är fältet <strong>ta bort reservationer och markeringar</strong> inställt på <strong>Reservationer</strong> eller <strong>Markeringar och reservationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="408d8-497">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-498">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="408d8-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="408d8-499">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="408d8-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="408d8-500">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="408d8-501">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-502">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="408d8-503">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-504">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="408d8-505">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="408d8-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="408d8-506">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="408d8-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="408d8-507">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-507">No</span></span></td>
<td><span data-ttu-id="408d8-508">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-508">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-509">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="408d8-510">Reservationen tas bort.</span><span class="sxs-lookup"><span data-stu-id="408d8-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="408d8-511">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="408d8-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="408d8-512">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="408d8-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="408d8-513">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> anges fältet <strong>Ta bort reservationer och markeringar</strong> till <strong>Ingen</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="408d8-514">Ja</span><span class="sxs-lookup"><span data-stu-id="408d8-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="408d8-515">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="408d8-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="408d8-516">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="408d8-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="408d8-517">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="408d8-518">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="408d8-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="408d8-519">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="408d8-520">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="408d8-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="408d8-521">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="408d8-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="408d8-522">Nej</span><span class="sxs-lookup"><span data-stu-id="408d8-522">No</span></span></td>
<td><span data-ttu-id="408d8-523">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="408d8-523">See the previous row.</span></span></td>
<td><span data-ttu-id="408d8-524">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="408d8-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="408d8-525">Ändringar i lagerstatus är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="408d8-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="408d8-526">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="408d8-526">Limitations</span></span>

- <span data-ttu-id="408d8-527">Den flexibla funktionen för dimensionsreservation på lagernivå stöder inte följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="408d8-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="408d8-528">Hantering av fångstvikt</span><span class="sxs-lookup"><span data-stu-id="408d8-528">Catch weight management</span></span>
    - <span data-ttu-id="408d8-529">Fysiskt negativt lager</span><span class="sxs-lookup"><span data-stu-id="408d8-529">Physical negative inventory</span></span>
    - <span data-ttu-id="408d8-530">Reservation mot beställda leveranser</span><span class="sxs-lookup"><span data-stu-id="408d8-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="408d8-531">Överföringsorder och plockning av råmaterial</span><span class="sxs-lookup"><span data-stu-id="408d8-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="408d8-532">Behållarens konsolideringsregel för paketering av direktivenhet har begränsningar.</span><span class="sxs-lookup"><span data-stu-id="408d8-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="408d8-533">För orderallokerade reservationer rekommenderar vi att du inte använder uppbyggnadsmallar för behållare där fältet **Packa efter enhet för direktiv** är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="408d8-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="408d8-534">I den aktuella designen används inte platsdirektiv när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="408d8-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="408d8-535">Det innebär att endast den minsta enheten i enhetssekvensgruppen (lagerenheten) används under påfyllnadssteget skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="408d8-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
