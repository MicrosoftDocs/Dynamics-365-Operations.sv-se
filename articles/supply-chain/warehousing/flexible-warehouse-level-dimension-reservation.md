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
ms.openlocfilehash: 65304216b579b8def493d1e4218174cb9617013d
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652189"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="0ddae-103">Flexibel reservationspolicy för dimension på lagernivå</span><span class="sxs-lookup"><span data-stu-id="0ddae-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ddae-104">När en hierarki för lagerreservationer av typen "batch-under\[plats\]" associeras med produkter kan företag som säljer spårade produkter och kör sin logistik när operationer som har aktiverats för Microsoft Dynamics 365 lagerställehanteringssystem (WMS) inte kan reservera specifika partier för dessa produkter för kundförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="0ddae-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span>

<span data-ttu-id="0ddae-105">På samma sätt kan särskilda ID-nummer inte reserveras för produkter på försäljningsorder när dessa produkter associeras med standardhierarkin för reservationer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-105">In a similar way, specific license plates can't be reserved for products on sales orders when those products are associated with the default reservation hierarchy.</span></span>

<span data-ttu-id="0ddae-106">I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för dessa företag att reservera specifika batchar eller ID-nummer, även om produkterna är kopplade till reservationshierarkin "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="0ddae-106">This topic describes the inventory reservation policy that lets these businesses reserve specific batches or license plates, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="0ddae-107">Lagerreservationshierarki</span><span class="sxs-lookup"><span data-stu-id="0ddae-107">Inventory reservation hierarchy</span></span>

<span data-ttu-id="0ddae-108">Det här avsnittet sammanfattar den befintliga lagerreservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="0ddae-108">This section summarizes the existing inventory reservation hierarchy.</span></span>

<span data-ttu-id="0ddae-109">Lagerreservationshierarkin avgör att när det gäller lagringsdimensioner har efterfrågeordern de obligatoriska dimensionerna för plats, lager och lagerstatus, medan lagerställelogiken är ansvarig för att tilldela en plats till de begärda kvantiteterna och reservera platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="0ddae-110">Med andra ord förväntas en efterfrågeorder i interaktionen mellan efterfrågeorder ordern och lagerställeåtgärder för att ange var ordern måste levereras från (dvs. vilken plats och lagerställe).</span><span class="sxs-lookup"><span data-stu-id="0ddae-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="0ddae-111">Lagerstället använder sig av sin logik för att hitta den begärda kvantiteten i dessa lagerlokaler.</span><span class="sxs-lookup"><span data-stu-id="0ddae-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="0ddae-112">Om du vill återspegla affärsverksamhetens driftsmodell, kan spårningsdimensioner (batch- och serienummer) bli mer flexibla.</span><span class="sxs-lookup"><span data-stu-id="0ddae-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="0ddae-113">En hierarki för lagerreservationer kan innehålla scenarier där följande villkor gäller:</span><span class="sxs-lookup"><span data-stu-id="0ddae-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="0ddae-114">Företaget använder sina lageroperationer för att hantera plockning av kvantiteter som har batch- eller serienummer efter det att kvantiteterna har hittats i lagringsutrymmet på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="0ddae-115">Den här modellen kallas ofta för en *Batch-under\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="0ddae-116">Den används vanligtvis när en produkts batch- eller serienummer-ID inte är viktig för de kunder som gör efterfrågan från det säljande företaget.</span><span class="sxs-lookup"><span data-stu-id="0ddae-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="0ddae-117">Om batch- eller serienummer är en del av en kundsorderspecifikation och registreras på efterfrågeorder, begränsas lageroperationerna som hittar kvantiteterna i lagerstället till de specifika nummer som krävs och tillåts inte att ändra dem.</span><span class="sxs-lookup"><span data-stu-id="0ddae-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="0ddae-118">Den här modellen kallas en *Batch-ovan\[plats\]*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="0ddae-119">I dessa scenarier är utmaningen att bara en hierarki med lagerreservationer kan tilldelas varje frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="0ddae-120">För att WMS ska hantera spårade objekt, efter att hierarkitilldelningen bestämmer när batch- eller serienumret ska reserveras (antingen när efterfrågan beställs eller under lagerplockningsarbetet), kan denna timing inte ändras på ad-hoc-basis.</span><span class="sxs-lookup"><span data-stu-id="0ddae-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="0ddae-121">Flexibel reservation för batchspårade artiklar</span><span class="sxs-lookup"><span data-stu-id="0ddae-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="0ddae-122">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="0ddae-122">Business scenario</span></span>

<span data-ttu-id="0ddae-123">I det här scenariot använder ett företag en lagerstrategi där färdiga varor spåras efter batchnummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="0ddae-124">Det här företaget använder också WMS-arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="0ddae-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="0ddae-125">Eftersom den här arbetsbelastningen har en välutrustad logik för planering och transport av lagerplocknings- och leveransoperationer för batchaktiverade artiklar, associeras de flesta av de färdiga artiklarna med en batch-under\[plats\] lagerreservationshierarki.</span><span class="sxs-lookup"><span data-stu-id="0ddae-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="0ddae-126">Fördelen med den här typen av driftsinställningar är att beslut (som är effektiva reservationsbeslut) om vilka batchar som ska plockas och var de ska skjutas upp tills lagerplockningsoperationer har startat.</span><span class="sxs-lookup"><span data-stu-id="0ddae-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="0ddae-127">De görs inte när kundens order har placerats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="0ddae-128">Även om reservationshierarkin "batch-under\[plats\]" "betjänar företagets affärsmål", kräver många av företagets etablerade kunder samma batch som de tidigare köpte när de beställer om produkter.</span><span class="sxs-lookup"><span data-stu-id="0ddae-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="0ddae-129">Därför söker företaget efter flexibilitet på det sätt som reglerna för batchreservation hanteras, så att, beroende på kundernas efterfrågan för samma artikel, uppstår följande problem.</span><span class="sxs-lookup"><span data-stu-id="0ddae-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="0ddae-130">Ett batchnummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte ändras under lageroperationer och/eller tas av andra behov.</span><span class="sxs-lookup"><span data-stu-id="0ddae-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="0ddae-131">Det här beteendet garanterar att det batchnummer som beställs levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="0ddae-132">Om batchnumret inte är viktigt för kunden, kan lageroperationerna bestämma ett batchnummer under plockningsarbetet efter att registrering och reservation av försäljningsordern har utförts.</span><span class="sxs-lookup"><span data-stu-id="0ddae-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="0ddae-133">Tillåta reservation av en specifik batch på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="0ddae-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="0ddae-134">För att tillgodose önskad flexibilitet i batchreservationens beteende för artiklar som är associerade med en "Batch-under\[plats\]" lagerreservationshierarki måste chefer markera kryssrutan **Tillåt reservation av efterfrågeorder** för nivån **Batch-nummer** på sidan **lagerreservationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Göra lagerreservationshierarkin flexibel](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="0ddae-136">När nivån **Batch-nummer** i hierarkin väljs kommer alla dimensioner över den nivån och upp till nivån **plats** att väljas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="0ddae-137">(Som standard är alla dimensioner ovanför nivån **plats** förvalda.) Det här beteendet återspeglar logiken där alla dimensioner i intervallet mellan batchnumret och lagerstället också reserveras automatiskt när du har reserverat ett specifikt batchnummer på orderraden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="0ddae-138">Kryssrutan **Tillåt reservation på efterfrågerorder** gäller bara för de nivåer för reservationshierarkier som ligger under dimensionen lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0ddae-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="0ddae-139">**Batchnummer** och **ID-nummer** är de enda nivåerna i hierarkin som är öppen för den flexibla reservationsprincipen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-139">**Batch number** and **License plate** are the only levels in the hierarchy that are open for the flexible reservation policy.</span></span> <span data-ttu-id="0ddae-140">Med andra ord kan du inte markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **Plats** eller **Serienummer**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location** or **Serial number** level.</span></span>
>
> <span data-ttu-id="0ddae-141">Om din reservationshierarki innehåller dimensionen för serienummer (som alltid måste vara under nivån **Batch-nummer**), och om du har aktiverat batch-specifik reservation för batch-numret kommer systemet att fortsätta hantera reservations- och plockningsoperationer för serienummer baserat på de regler som gäller för reservationsprincipen "Serie-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="0ddae-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="0ddae-142">Du kan när som helst tillåta batch-specifik reservation för en befintlig "batch-under\[plats\]" reservationshierarki i distributionen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="0ddae-143">Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="0ddae-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="0ddae-144">Men kryssrutan **Tillåt reservation på efterfrågeorder** kan inte vara avmarkerad om lagertransaktioner för utleveranstyper **Reserverat beställt**, **Fysiskt reserverat** eller **Beställt** finns för en eller flera artiklar som är associerade med den reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="0ddae-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="0ddae-145">Om en artikels befintliga reservationshierarki inte tillåter kommandospecifikation på ordern kan du tilldela om den till en reservationshierarki som tillåter batch-specifikation, förutsatt att hierarkinivåstrukturen är densamma i båda hierarkierna.</span><span class="sxs-lookup"><span data-stu-id="0ddae-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="0ddae-146">Använd funktionen **ändra reservationshierarki för artiklar** för att utföra omtilldelningen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="0ddae-147">Den här ändringen kan vara relevant när du vill förhindra flexibel batch-reservation för en delmängd av batch-spårade artiklar, men tillåter den för resten av produktportföljen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="0ddae-148">Oavsett om du har markerat kryssrutan **Tillåt reservation på efterfrågeorder** om du inte vill reservera ett specifikt batchnummer för artikeln på en orderrad, gäller standardoperationslogiken för lagerställe som är giltig för en "Batch-under\[location\]" reservationhierarkin.</span><span class="sxs-lookup"><span data-stu-id="0ddae-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="0ddae-149">Reservera ett specifikt batchnummer för en kundorder</span><span class="sxs-lookup"><span data-stu-id="0ddae-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="0ddae-150">När en batch-spårad artikels "Batch-under\[plats\]" lagerreservationshierarki har ställts in för att tillåta reservation av specifika batchnummer på försäljningsorder, kan behandlare av försäljningsorder ta kundorder för samma artikel på något av följande sätt, beroende på kundens begäran:</span><span class="sxs-lookup"><span data-stu-id="0ddae-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="0ddae-151">**Ange orderdetaljer utan att ange ett batchnummer** – det här tillvägagångssättet ska användas när produktens batch-specifikation inte är viktig för kunden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="0ddae-152">Alla befintliga processer som associeras med hantering av en order av den här typen i systemet förblir oförändradet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="0ddae-153">Det behövs ingen ytterligare hänsyn till användarna.</span><span class="sxs-lookup"><span data-stu-id="0ddae-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="0ddae-154">**Ange orderdetaljer och reservera ett specifikt batchnummer** – den här metoden bör användas när kunden begär en specifik batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="0ddae-155">Vanligtvis begär kunder en särskild batch när de ombeställer en produkt som de tidigare har köpt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="0ddae-156">Denna typ av batch-specifik reservation kallas för *orderallokerad reservation*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="0ddae-157">Följande regler gäller när kvantiteter bearbetas och ett batchnummer allokeras till en specifik order:</span><span class="sxs-lookup"><span data-stu-id="0ddae-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="0ddae-158">Om du vill tillåta reservation av ett specifikt batchnummer för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="0ddae-159">I detta intervall ingår vanligtvis dimensionen registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="0ddae-160">Platsdirektiv används inte när plockningsarbete skapas för en försäljningsrad som använder orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="0ddae-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="0ddae-161">Under lagerbearbetning av arbete för orderallokerade batchar, tillåts varken användaren eller systemet att ändra batchnumret.</span><span class="sxs-lookup"><span data-stu-id="0ddae-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="0ddae-162">(Bearbetningen omfattar undantagshantering.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="0ddae-163">I följande exempel visas ett komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="0ddae-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario-batch-number-allocation"></a><span data-ttu-id="0ddae-164">Exempel scenario: allokering av batchnummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-164">Example scenario: Batch number allocation</span></span>

<span data-ttu-id="0ddae-165">För det här exemplet måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="0ddae-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a><span data-ttu-id="0ddae-166">Ställ in en hierarki för lagerreservationer för att tillåta batch-specifika reservationer</span><span class="sxs-lookup"><span data-stu-id="0ddae-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="0ddae-167">Gå till **Lagerstyrning** \> **Inställningar** \> **Lager \> Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="0ddae-168">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-168">Select **New**.</span></span>
3. <span data-ttu-id="0ddae-169">I fältet **Namn** anger du ett namn (till exempel **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="0ddae-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="0ddae-170">I fältet **Beskrivning** anger du en beskrivning (till exempel, **Batch under flexibel**).</span><span class="sxs-lookup"><span data-stu-id="0ddae-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="0ddae-171">I fältet **Valda** väljer du **Serienummer** och **Ägare** och väljer sedan vänsterpilen för att flytta dem till fältet **Tillgängliga**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="0ddae-172">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-172">Select **OK**.</span></span>
7. <span data-ttu-id="0ddae-173">I raden för dimensionsnivån **Batch-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="0ddae-174">Nivåerna **Registreringsskylt** och **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för dem.</span><span class="sxs-lookup"><span data-stu-id="0ddae-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="0ddae-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="0ddae-176">Skapa en ny frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="0ddae-176">Create a new released product</span></span>

1. <span data-ttu-id="0ddae-177">Ställ in produktens tre huvuddataparametrar med hjälp av dessa värden:</span><span class="sxs-lookup"><span data-stu-id="0ddae-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="0ddae-178">I fältet **lagringsdimensionsgrupp** välj **Ware**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="0ddae-179">I fältet **spårningsdimensionsgrupp** välj **Batch-Phy**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="0ddae-180">I fältet **Reservationshierarki** välj **BatchFlex**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="0ddae-181">Skapa två batchnummer, t.ex. **B11** och **B22**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="0ddae-182">Lägg till artikelkvantiteter i lagerbehållning med hjälp av följande värden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="0ddae-183">Distributionslager</span><span class="sxs-lookup"><span data-stu-id="0ddae-183">Warehouse</span></span> | <span data-ttu-id="0ddae-184">Batchnummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-184">Batch number</span></span> | <span data-ttu-id="0ddae-185">Plats</span><span class="sxs-lookup"><span data-stu-id="0ddae-185">Location</span></span> | <span data-ttu-id="0ddae-186">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-186">License plate</span></span> | <span data-ttu-id="0ddae-187">Antal</span><span class="sxs-lookup"><span data-stu-id="0ddae-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="0ddae-188">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-188">24</span></span>        | <span data-ttu-id="0ddae-189">B11</span><span class="sxs-lookup"><span data-stu-id="0ddae-189">B11</span></span>          | <span data-ttu-id="0ddae-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="0ddae-190">BULK-001</span></span> | <span data-ttu-id="0ddae-191">Ingen</span><span class="sxs-lookup"><span data-stu-id="0ddae-191">None</span></span>          | <span data-ttu-id="0ddae-192">10</span><span class="sxs-lookup"><span data-stu-id="0ddae-192">10</span></span>       |
    | <span data-ttu-id="0ddae-193">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-193">24</span></span>        | <span data-ttu-id="0ddae-194">B11</span><span class="sxs-lookup"><span data-stu-id="0ddae-194">B11</span></span>          | <span data-ttu-id="0ddae-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="0ddae-195">FL-001</span></span>   | <span data-ttu-id="0ddae-196">LP11</span><span class="sxs-lookup"><span data-stu-id="0ddae-196">LP11</span></span>          | <span data-ttu-id="0ddae-197">10</span><span class="sxs-lookup"><span data-stu-id="0ddae-197">10</span></span>       |
    | <span data-ttu-id="0ddae-198">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-198">24</span></span>        | <span data-ttu-id="0ddae-199">B22</span><span class="sxs-lookup"><span data-stu-id="0ddae-199">B22</span></span>          | <span data-ttu-id="0ddae-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="0ddae-200">FL-002</span></span>   | <span data-ttu-id="0ddae-201">LP22</span><span class="sxs-lookup"><span data-stu-id="0ddae-201">LP22</span></span>          | <span data-ttu-id="0ddae-202">10</span><span class="sxs-lookup"><span data-stu-id="0ddae-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a><span data-ttu-id="0ddae-203">Ange försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="0ddae-203">Enter sales order details</span></span>

1. <span data-ttu-id="0ddae-204">Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="0ddae-205">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-205">Select **New**.</span></span>
3. <span data-ttu-id="0ddae-206">I försäljningsorderns rubrik, i fältet **Kundkonto** ange **US-003**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="0ddae-207">Lägg till en rad för den nya artikeln och ange **10** som kvantitet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="0ddae-208">Se till att fältet **Lagerställe** anges till **24**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="0ddae-209">På snabbfliken **försäljningsorderrader** välj **lager** och sedan i gruppen **underhåll** välj **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="0ddae-210">Sidan **Batch-reservation** visar en lista över batchar som är tillgängliga för reservation för orderraden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="0ddae-211">I det här exemplet visas ett antal på **20** för batchnummer **B11** och kvantiteten **10** för batchnummer **B22**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="0ddae-212">Observera att du inte kan komma åt sidan **Batch-reservation** från en rad om den raden är associerad med "Batch-under\[plats\]" reservationshierarki om den inte har ställts in för att tillåta batch-specifik reservation.</span><span class="sxs-lookup"><span data-stu-id="0ddae-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-213">Om du vill reservera en specifik batch för en försäljningsorder måste du använda sidan **Batch-reservation**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="0ddae-214">Om du anger batchnumret direkt på försäljningsorderraden, kommer systemet att fungera som om du har angett ett specifikt batchvärde för ett objekt som omfattas av "Batch-under\[plats\]" reservationspolicy.</span><span class="sxs-lookup"><span data-stu-id="0ddae-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="0ddae-215">När du sparar raden visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="0ddae-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="0ddae-216">Om du bekräftar att batchnumret ska anges direkt på orderraden hanteras inte raden av den normala lagerstyrningslogiken.</span><span class="sxs-lookup"><span data-stu-id="0ddae-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="0ddae-217">Om du reserverar kvantiteten från sidan **Reservation** kommer ingen specifik batch att reserveras och körningen av lagerställeoperationer för raden följer reglerna som är tillämpliga under reservationspolicyn "Batch-under\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="0ddae-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="0ddae-218">Den här sidan fungerar vanligtvis på samma sätt och interagerar med artiklar som har en associerad reservationssekvens för typen "Batch-ovan\[plats\]".</span><span class="sxs-lookup"><span data-stu-id="0ddae-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="0ddae-219">Följande undantag gäller emellertid:</span><span class="sxs-lookup"><span data-stu-id="0ddae-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="0ddae-220">Snabbfliken **batchnummer för källrad** visar de batchnummer som har reserverats för orderraden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="0ddae-221">Batchvärdet i rutnätet visas under hela orderradens uppfyllandecykel, inklusive faserna för lagerbearbetning.</span><span class="sxs-lookup"><span data-stu-id="0ddae-221">The batch values in the grid will be shown throughout the fulfillment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="0ddae-222">På snabbfliken **översikt** visas däremot en reservation på ordinarie orderrad (dvs. reservation som görs för dimensionerna över nivån **plats**) i rutnätet upp till punkten när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="0ddae-223">Arbetsenheten tar över radreservationen och radreservationen visas inte längre på sidan.</span><span class="sxs-lookup"><span data-stu-id="0ddae-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="0ddae-224">Snabbfliken **batchnummer för källrader** används för att garantera att försäljningsorderns handläggare kan visa de batchnummer som har utfästs till kundens order när som helst under livscykeln, upp till fakturering.</span><span class="sxs-lookup"><span data-stu-id="0ddae-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="0ddae-225">Förutom att reservera en viss batch kan han eller hon manuellt välja batchens specifika plats och licensskylt i stället för att låta systemet automatiskt välja dem.</span><span class="sxs-lookup"><span data-stu-id="0ddae-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="0ddae-226">Denna kapacitet är relaterad till designen av mekanismen för orderallokerad batch-reservation.</span><span class="sxs-lookup"><span data-stu-id="0ddae-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="0ddae-227">Som nämnts tidigare, när ett specifikt batchnummer reserveras för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="0ddae-228">Därför kommer lagerstället att ha samma lagringsdimensioner som har reserverats av de användare som arbetade med ordern, och den kanske inte alltid representerar den placering av artikellagring som är praktiskt eller till och med möjlig för plockningsoperationer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="0ddae-229">Om orderhandläggarna känner till begränsningarna i lagerställena, kanske de vill välja de specifika platserna och licensskyltarna manuellt när de reserverar en batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="0ddae-230">I det här fallet måste användaren använda funktionen för **visningsdimensioner** i sidhuvudet och måste lägga till platsen och licensskylten i rutnätet på snabbfliken **översikt**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="0ddae-231">På sidan **Batch-reservation** välj raden för batch **B11** och välj sedan **reservera rad**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="0ddae-232">Det finns ingen särskild logik för att tilldela platser och licensskyltarna vid automatisk reservation.</span><span class="sxs-lookup"><span data-stu-id="0ddae-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="0ddae-233">Du kan ange kvantiteten manuellt i fältet **reservation**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="0ddae-234">Observera att snabbfliken **batchnummer för källrad**, batch **B11** visas som **utfäst**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Utfästa ett specifikt batchnummer på en försäljningsorderrad på sidan batch-reservation](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="0ddae-236">Det går att utföra reservationer av kvantiteten på en försäljningsorderrad i flera batchar.</span><span class="sxs-lookup"><span data-stu-id="0ddae-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="0ddae-237">På samma sätt kan reservation av samma batch göras mot flera platser och licensskyltar (om licensskyltar är aktiverade för platserna).</span><span class="sxs-lookup"><span data-stu-id="0ddae-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="0ddae-238">Reservation av en specifik batch för kvantiteten på en försäljningsorderrad kan också vara del.</span><span class="sxs-lookup"><span data-stu-id="0ddae-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="0ddae-239">Den totala kvantiteten 100 enheter kan till exempel reserveras så att en specifik batch har allokerats till 20 enheter, medan 80 enheter reserveras på platsen och lagerställenivåer för någon tillgänglig batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="0ddae-240">I det här fallet hanterar WMS plockningsoperationer med hjälp av två separata arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="0ddae-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="0ddae-241">Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="0ddae-242">Markera artikeln och välj sedan **hantera lager** \> **visa** \> **transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Order-allokerad reservation som en lagertransaktionstyp](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="0ddae-244">Granska artikelns lagertransaktioner som hör till försäljningsorderradens reservation.</span><span class="sxs-lookup"><span data-stu-id="0ddae-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="0ddae-245">En transaktion där fältet **Referens** anges till **Försäljningsorder** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="0ddae-246">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner plats, lagerställe och lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="0ddae-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="0ddae-247">En transaktion där fältet**Referens** anges till **Orderallokerad reservation** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för den specifika batchen och alla lagerdimensioner ovanför.</span><span class="sxs-lookup"><span data-stu-id="0ddae-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="0ddae-248">Enligt artikelns hierarki för lagerreservationer är dessa dimensioner batch-nummer och plats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="0ddae-249">I det här exemplet är platsen **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="0ddae-250">Välj i försäljningsorderhuvudet **Lagerställe** \> **Åtgärder** \> **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="0ddae-251">Orderraden är nu vågad och en last och ett arbete skapas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="0ddae-252">Granska och bearbeta lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="0ddae-253">På snabbfliken **Försäljningsorderrader** välj **Lagerställe** \> **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="0ddae-254">Det arbete som hanterar plockoperationen för batchkvantiteter som har bekräftats till försäljningsorderraden har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0ddae-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="0ddae-255">Om du vill skapa arbete använder systemet arbetsmallar men inte platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="0ddae-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="0ddae-256">Alla standardinställningar som definieras för arbetsmallar, t.ex. ett maximalt antal plockningsrader eller en specifik måttenhet, används för att bestämma när nytt arbete ska skapas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="0ddae-257">Reglerna som är kopplade till platsdirektiv för identifiering av plockningsplatser beaktas dock inte eftersom den order som genomförts redan anger alla lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="0ddae-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="0ddae-258">Dessa lagerdimensioner inkluderar dimensionerna på lagerställets lagernivå.</span><span class="sxs-lookup"><span data-stu-id="0ddae-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="0ddae-259">Därför ärver arbetet dessa dimensioner utan att behöva konsultera platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="0ddae-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="0ddae-260">Batchnumret visas inte på plockningsraden (som är fallet för den arbetsrad som skapas för en artikel som har en motsvarande "batch-ovan\[plats\]" reservationshierarki.) I stället visas batchnummer från och alla andra lagringsdimensioner på arbetsradens jobblagertransaktion som refereras från de associerade lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="0ddae-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Lagerställets lagertransaktion för arbete som härrör från en reservation som har genomförts av order](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="0ddae-262">När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på **Order-allokerad reservation** borttagen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="0ddae-263">Lagertransaktionen där fältet **Referens** anges till **Arbete** innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0ddae-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="0ddae-264">Lageroperationer kan fortsätta för att hantera utförande av arbetet på vanligt sätt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="0ddae-265">Men instruktionerna på den mobila enheten instruerar arbetaren att välja ett specifikt batchnummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="0ddae-266">I lagermiljöer där platser är registreringsskylt – styrs efter att en arbetare har nått en plats som lagrar samma batch på registreringsskyltar, kan han eller hon välja från alla registreringsskyltar som inte redan har reserverats (t.ex. av en annan order-allokerad reservation eller arbete som härrör från en reservation av den typen.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="0ddae-267">Om det blir opraktiskt att plocka från den plats som anges på arbetsraden, kan lagerställets operatörer använda någon av följande åtgärder för att dirigera om plockning av en viss batch:</span><span class="sxs-lookup"><span data-stu-id="0ddae-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="0ddae-268">Standard är åtgärden **åsidosätta plats** på en mobil enhet (förutsatt att inställningen för lagerarbetare **Tillåt åsidosättning av plockplats** är aktiverad)</span><span class="sxs-lookup"><span data-stu-id="0ddae-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="0ddae-269">Åtgärden **ändra plats** på sidan **information om arbetslista**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="0ddae-270">Slutför plockningen på den mobila enheten och sätt in arbetet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="0ddae-271">Kvantiteten **10** för batchnummer **B11** har nu plockats för försäljningsorderraden och placerats på platsen **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="0ddae-272">I detta skede är den klar att lastas på lastbilen och skickas till kundens adress.</span><span class="sxs-lookup"><span data-stu-id="0ddae-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="flexible-license-plate-reservation"></a><span data-ttu-id="0ddae-273">Flexibel reservation av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-273">Flexible license plate reservation</span></span>

### <a name="business-scenario"></a><span data-ttu-id="0ddae-274">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="0ddae-274">Business scenario</span></span>

<span data-ttu-id="0ddae-275">I det här scenariot använder ett företag lagerstyrnings- och arbetsbearbetning och hanterar belastningsplanering vid nivån för enskilda lastpallar/behållare utanför Supply Chain Management innan arbetet skapas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-275">In this scenario, a company uses warehouse management and work processing, and handles load planning at the level of individual pallets/containers outside Supply Chain Management before work is created.</span></span> <span data-ttu-id="0ddae-276">Dessa behållare representeras av ID-nummer i lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="0ddae-276">These containers are represented by license plates in the inventory dimensions.</span></span> <span data-ttu-id="0ddae-277">Därför måste specifika ID-nummer på försäljnings orderrader innan plockningsarbete utförs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-277">Therefore, for this approach, specific license plates must be pre-assigned to sales order lines before picking work is done.</span></span> <span data-ttu-id="0ddae-278">Företaget letar efter flexibilitet i hur reservationsreglerna för ID-nummer, så att följande beteende uppstår:</span><span class="sxs-lookup"><span data-stu-id="0ddae-278">The company is looking for flexibility in the way that the license plate reservation rules are handled, so that the following behaviors occur:</span></span>

- <span data-ttu-id="0ddae-279">Ett ID-nummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte tas av andra behov.</span><span class="sxs-lookup"><span data-stu-id="0ddae-279">A license plate can be recorded and reserved when the order is taken by the sales processor, and it can't be taken by other demands.</span></span> <span data-ttu-id="0ddae-280">Det här beteendet garanterar att det ID-nummer som planerats levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-280">This behavior helps guarantee that the license plate that was planned is shipped to the customer.</span></span>
- <span data-ttu-id="0ddae-281">Om ID-numret inte redan har tilldelats en försäljningsorderrad kan lagerpersonalen välja ett ID-nummer under plockningsarbete när registrering och reservation av försäljningsorder har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0ddae-281">If the license plate isn't already assigned to a sales order line, warehouse personnel can select a license plate during picking work, after sales order registration and reservation are completed.</span></span>

### <a name="turn-on-flexible-license-plate-reservation"></a><span data-ttu-id="0ddae-282">Aktivera flexibel reservation av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-282">Turn on flexible license plate reservation</span></span>

<span data-ttu-id="0ddae-283">Innan du kan använda flexibel reservation av ID-nummer måste två funktioner aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="0ddae-283">Before you can use flexible license plate reservation, two features must be turned on in your system.</span></span> <span data-ttu-id="0ddae-284">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-284">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="0ddae-285">Du måste aktivera funktionerna i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="0ddae-285">You must turn on the features in the following order:</span></span>

1. <span data-ttu-id="0ddae-286">**Funktionsnamn:** *Flexibel reservation för dimension på distributionslagernivå*</span><span class="sxs-lookup"><span data-stu-id="0ddae-286">**Feature name:** *Flexible warehouse-level dimension reservation*</span></span>
1. <span data-ttu-id="0ddae-287">**Funktionsnamn:** *flexibel orderallokerade reservation av ID-nummer*</span><span class="sxs-lookup"><span data-stu-id="0ddae-287">**Feature name:** *Flexible order-committed license plate reservation*</span></span>

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a><span data-ttu-id="0ddae-288">Reservera ett specifikt ID-nummer på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="0ddae-288">Reserve a specific license plate on the sales order</span></span>

<span data-ttu-id="0ddae-289">Om du vill aktivera reservation av ID-nummer på en order måste du markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **ID-nummer** på sidan **Tillåt reservation av efterfrågeorder** för lagerreservationer för den hierarki som är kopplad till den relevanta artikeln.</span><span class="sxs-lookup"><span data-stu-id="0ddae-289">To enable license plate reservation on an order, you must select the **Allow reservation on demand order** check box for the **License plate** level on the **Inventory reservation hierarchies** page for the hierarchy that is associated with the relevant item.</span></span>

![Sidan hierarkier för lagerreservationer för en flexibel reservationshierarki för ID-nummer](media/Flexible-LP-reservation-hierarchy.png)

<span data-ttu-id="0ddae-291">Du kan aktivera reservation av ID-nummer på ordern när som helst i distributionen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-291">You can enable license plate reservation on the order at any point in your deployment.</span></span> <span data-ttu-id="0ddae-292">Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="0ddae-292">This change won't affect any reservations or open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="0ddae-293">Men du kan inte avmarkera kryssrutan **Tillåt reservation på efterfrågeorder** om öppna avgående lagertransaktioner som har en för utleveransstatus *Som har beställts*, *Fysiskt reserverat* eller *Beställt* finns för en eller flera artiklar som är associerade med den reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="0ddae-293">However, you can't clear the **Allow reservation on demand order** check box if open outbound inventory transactions that have an issue status of *On order*, *Reserved ordered*, or *Reserved physical* exist for one or more items that are associated with that reservation hierarchy.</span></span>

<span data-ttu-id="0ddae-294">Även om kryssrutan **Tillåt reservation på efterfrågeorder** har markerat nivån **ID-nummer** är det fortfarande möjligt att *inte* reservera ett specifikt ID-nummer på order.</span><span class="sxs-lookup"><span data-stu-id="0ddae-294">Even if the **Allow reservation on demand order** check box is selected for the **License plate** level, it's still possible *not* to reserve a specific license plate on the order.</span></span> <span data-ttu-id="0ddae-295">I det här fallet gäller standardlogiken för lageråtgärder som är giltig för den här reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="0ddae-295">In this case, the default warehouse operations logic that is valid for the reservation hierarchy applies.</span></span>

<span data-ttu-id="0ddae-296">Om du vill reservera ett visst ID-nummer måste du använda en process med [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). I appen kan du göra denna reservation direkt från en försäljningsorder med hjälp av alternativet **orderallokerade reservation av ID-nummer** för kommandot **Öppna i Excel**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-296">To reserve a specific license plate, you must use an [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md) process.In the application, you can do this reservation directly from a sales order by using the **Order-committed reservations per license plate** option of the **Open in Excel** command.</span></span> <span data-ttu-id="0ddae-297">I enhets data som öppnas i Excel-tillägget måste du ange följande reservationsrelaterade data och sedan välja **publicera** för att skicka tillbaka data till Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="0ddae-297">In the entity data that is opened in the Excel add-in, you must enter the following reservation-related data and then select **Publish** to send the data back to Supply Chain Management:</span></span>

- <span data-ttu-id="0ddae-298">Referens (endast *försäljningsordern* värde stöds.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-298">Reference (Only the *Sales order* value is supported.)</span></span>
- <span data-ttu-id="0ddae-299">Ordernummer (värdet kan härledas från partiet.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-299">Order number (The value can be derived from the lot.)</span></span>
- <span data-ttu-id="0ddae-300">Parti-ID</span><span class="sxs-lookup"><span data-stu-id="0ddae-300">Lot ID</span></span>
- <span data-ttu-id="0ddae-301">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-301">License plate</span></span>
- <span data-ttu-id="0ddae-302">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="0ddae-302">Quantity</span></span>

<span data-ttu-id="0ddae-303">Om du måste reservera en viss ID-nummer för en spårad artikel, använder du sidan **Batchreservation**, som beskrivs i avsnittet [Ange detaljinformation om försäljningsorder](#sales-order-details).</span><span class="sxs-lookup"><span data-stu-id="0ddae-303">If you must reserve a specific license plate for a batch-tracked item, use the **Batch reservation** page, as described in the [Enter sales order details](#sales-order-details) section.</span></span>

<span data-ttu-id="0ddae-304">När försäljningsorderraden som använder en orderallokerad reserverat ID-nummer bearbetas av lagerställe, används inte platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="0ddae-304">When the sales order line that uses an order-committed license plate reservation is processed by warehouse operations, location directives aren't used.</span></span>

<span data-ttu-id="0ddae-305">Om en artikel för ett lagerställe består av rader som är lika med en komplett lastpall och har licensskyltar, kan du optimera plockningsprocessen genom att använda ett menyalternativ för mobila enheter där alternativet **Hantera efter ID-nummer** är inställt på *Ja*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-305">If a warehouse work item consists of lines that equal a complete pallet and have license plate–committed quantities, you can optimize the picking process by using a mobile device menu item where the **Handle by license plate** option is set to *Yes*.</span></span> <span data-ttu-id="0ddae-306">En lagerarbetare kan sedan söka igenom ett ID-nummer för att slutföra en plockning i stället för att behöva skanna artiklarna från ett arbetsställe en i taget.</span><span class="sxs-lookup"><span data-stu-id="0ddae-306">A warehouse worker can then scan a license plate to complete a pick instead of having to scan the items from the work one by one.</span></span>

![Menyalternativet mobilen där alternativet hantera efter ID-nummer är inställt på Ja](media/Handle-by-LP-menu-item.png)

<span data-ttu-id="0ddae-308">Eftersom funktionen **Hantera efter ID-nummer** inte stöder arbete som täcker flera lastpallar, är det bättre att ha en separat arbetsuppgift för olika ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-308">Because the **Handle by license plate** functionality doesn't support work that covers multiple pallets, it's better to have a separate work item for different license plates.</span></span> <span data-ttu-id="0ddae-309">Om du vill använda den här metoden lägger du till fältet **orderallokerade reservation av ID-nummer** som en sidhuvudsbrytning på sidan **arbetsmall**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-309">To use this approach, add the **Order-committed license plate ID** field as a work header break on the **Work template** page.</span></span>

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a><span data-ttu-id="0ddae-310">Exempelscenario: Ställ in och bearbeta en beställning med utfästa registreringslicenser</span><span class="sxs-lookup"><span data-stu-id="0ddae-310">Example scenario: Set up and process an order-committed license plate reservation</span></span>

<span data-ttu-id="0ddae-311">Scenariot visar hur du ställer och bearbeta en beställning med utfästa registreringslicenser.</span><span class="sxs-lookup"><span data-stu-id="0ddae-311">This scenario shows how to set up and process an order-committed license plate reservation.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="0ddae-312">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="0ddae-312">Make demo data available</span></span>

<span data-ttu-id="0ddae-313">Det här scenariot i detta ämne innehåller värdet och poster som ingår i den standarddemodata som finns för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0ddae-313">This scenario refers to values and records that are included in the standard demo data that is provided for Supply Chain Management.</span></span> <span data-ttu-id="0ddae-314">Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett miljö där demodata är installerat.</span><span class="sxs-lookup"><span data-stu-id="0ddae-314">If you want to work through the scenario by using the values that are provided here, be sure to work on an environment where the demo data is installed.</span></span> <span data-ttu-id="0ddae-315">Dessutom måste du välja juridisk person **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="0ddae-315">Additionally, set the legal entity to **USMF** before you begin.</span></span>

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a><span data-ttu-id="0ddae-316">Skapa en hierarki för lager reservationer som möjliggör reservation av ID-nummrt</span><span class="sxs-lookup"><span data-stu-id="0ddae-316">Create an inventory reservation hierarchy that allows for license plate reservation</span></span>

1. <span data-ttu-id="0ddae-317">Gå till **Lagerstyrning \> Inställningar \> Lager \> Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-317">Go to **Warehouse management \> Setup \> Inventory \> Reservation hierarchy**.</span></span>
1. <span data-ttu-id="0ddae-318">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-318">Select **New**.</span></span>
1. <span data-ttu-id="0ddae-319">I fältet **Namn** anger du ett värde (till exempel *FlexibleLP*).</span><span class="sxs-lookup"><span data-stu-id="0ddae-319">In the **Name** field, enter a value (for example, *FlexibleLP*).</span></span>
1. <span data-ttu-id="0ddae-320">I fältet **Beskrivning** anger du en värde (till exempel, *Flexibel LP reservation*).</span><span class="sxs-lookup"><span data-stu-id="0ddae-320">In the **Description** field, enter a value (for example, *Flexible LP reservation*).</span></span>
1. <span data-ttu-id="0ddae-321">I listan **Valda** välj **Batchnummer**, **Serienummer** och **Ägare**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-321">In the **Selected** list, select **Batch number**, **Serial number**, and **Owner**.</span></span>
1. <span data-ttu-id="0ddae-322">Välj knappen **Ta bort** ![Bakåtpilen](media/backward-button.png) om du vill flytta fältet till valda poster till listan **Tillgängliga**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-322">Select the **Remove** button ![backward arrow](media/backward-button.png) to move the selected records to the **Available** list.</span></span>
1. <span data-ttu-id="0ddae-323">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-323">Select **OK**.</span></span>
1. <span data-ttu-id="0ddae-324">I raden för dimensionsnivån **ID-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-324">In the row for the **License plate** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="0ddae-325">Nivån **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för den.</span><span class="sxs-lookup"><span data-stu-id="0ddae-325">The **Location** level is automatically selected, and you can't clear the check box for it.</span></span>
1. <span data-ttu-id="0ddae-326">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-326">Select **Save**.</span></span>

### <a name="create-two-released-products"></a><span data-ttu-id="0ddae-327">Skapa två frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="0ddae-327">Create two released products</span></span>

1. <span data-ttu-id="0ddae-328">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-328">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="0ddae-329">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0ddae-329">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0ddae-330">I dialogrutan **Ny frisläppt produkt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="0ddae-330">In the **New released product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="0ddae-331">**Produktnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="0ddae-331">**Product number:** *Item1*</span></span>
    - <span data-ttu-id="0ddae-332">**Artikelnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="0ddae-332">**Item number:** *Item1*</span></span>
    - <span data-ttu-id="0ddae-333">**Artikelmodellgrupp:** *FIFO*</span><span class="sxs-lookup"><span data-stu-id="0ddae-333">**Item model group:** *FIFO*</span></span>
    - <span data-ttu-id="0ddae-334">**Artikelgrupp:** *Ljud*</span><span class="sxs-lookup"><span data-stu-id="0ddae-334">**Item group:** *Audio*</span></span>
    - <span data-ttu-id="0ddae-335">**Lagringsdimensionsgrupp:** *Lager*</span><span class="sxs-lookup"><span data-stu-id="0ddae-335">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="0ddae-336">**Spårningsdimensionsgrupp:** *Ingen*</span><span class="sxs-lookup"><span data-stu-id="0ddae-336">**Tracking dimension group:** *None*</span></span>
    - <span data-ttu-id="0ddae-337">**Reservationshierarki:** *FlexibleLP*</span><span class="sxs-lookup"><span data-stu-id="0ddae-337">**Reservation hierarchy:** *FlexibleLP*</span></span>

1. <span data-ttu-id="0ddae-338">Välj **OK** för att skapa produkt och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0ddae-338">Select **OK** to create the product and close the dialog box.</span></span>
1. <span data-ttu-id="0ddae-339">Den nya produkten öppnas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-339">The new product is opened.</span></span> <span data-ttu-id="0ddae-340">På snabbfliken **lagerställe** i fältet **enhetssekvensgrupp- ID** anger du *ea*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-340">On the **Warehouse** FastTab, set the **Unit sequence group ID** field to *ea*.</span></span>
1. <span data-ttu-id="0ddae-341">Upprepa föregående steg för att skapa en andra produkt som har samma inställningar, men ställ in fält **produktnummer** och **artikelnummer** på *Artikel2*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-341">Repeat the previous steps to create a second product that has the same settings, but set the **Product number** and **Item number** fields to *Item2*.</span></span>
1. <span data-ttu-id="0ddae-342">I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Visa**, väljer du **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-342">On the Action Pane, on the **Manage inventory** tab, in the **View** group, select **On-hand inventory**.</span></span> <span data-ttu-id="0ddae-343">Välj sedan **justering av kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-343">Then select **Quantity adjustment**.</span></span>
1. <span data-ttu-id="0ddae-344">Justera lagerbehållningen för de nya artiklarna enligt vad som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0ddae-344">Adjust the on-hand inventory of the new items as specified in the following table.</span></span>

    | <span data-ttu-id="0ddae-345">Artikel</span><span class="sxs-lookup"><span data-stu-id="0ddae-345">Item</span></span>  | <span data-ttu-id="0ddae-346">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="0ddae-346">Warehouse</span></span> | <span data-ttu-id="0ddae-347">Plats</span><span class="sxs-lookup"><span data-stu-id="0ddae-347">Location</span></span> | <span data-ttu-id="0ddae-348">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-348">License plate</span></span> | <span data-ttu-id="0ddae-349">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="0ddae-349">Quantity</span></span> |
    |-------|-----------|----------|---------------|----------|
    | <span data-ttu-id="0ddae-350">Artikel1</span><span class="sxs-lookup"><span data-stu-id="0ddae-350">Item1</span></span> | <span data-ttu-id="0ddae-351">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-351">24</span></span>        | <span data-ttu-id="0ddae-352">FL-010</span><span class="sxs-lookup"><span data-stu-id="0ddae-352">FL-010</span></span>   | <span data-ttu-id="0ddae-353">LP01</span><span class="sxs-lookup"><span data-stu-id="0ddae-353">LP01</span></span>          | <span data-ttu-id="0ddae-354">10</span><span class="sxs-lookup"><span data-stu-id="0ddae-354">10</span></span>       |
    | <span data-ttu-id="0ddae-355">Artikel1</span><span class="sxs-lookup"><span data-stu-id="0ddae-355">Item1</span></span> | <span data-ttu-id="0ddae-356">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-356">24</span></span>        | <span data-ttu-id="0ddae-357">FL-011</span><span class="sxs-lookup"><span data-stu-id="0ddae-357">FL-011</span></span>   | <span data-ttu-id="0ddae-358">LP02</span><span class="sxs-lookup"><span data-stu-id="0ddae-358">LP02</span></span>          | <span data-ttu-id="0ddae-359">10</span><span class="sxs-lookup"><span data-stu-id="0ddae-359">10</span></span>       |
    | <span data-ttu-id="0ddae-360">Artikel2</span><span class="sxs-lookup"><span data-stu-id="0ddae-360">Item2</span></span> | <span data-ttu-id="0ddae-361">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-361">24</span></span>        | <span data-ttu-id="0ddae-362">FL-010</span><span class="sxs-lookup"><span data-stu-id="0ddae-362">FL-010</span></span>   | <span data-ttu-id="0ddae-363">LP01</span><span class="sxs-lookup"><span data-stu-id="0ddae-363">LP01</span></span>          | <span data-ttu-id="0ddae-364">5</span><span class="sxs-lookup"><span data-stu-id="0ddae-364">5</span></span>        |
    | <span data-ttu-id="0ddae-365">Artikel2</span><span class="sxs-lookup"><span data-stu-id="0ddae-365">Item2</span></span> | <span data-ttu-id="0ddae-366">24</span><span class="sxs-lookup"><span data-stu-id="0ddae-366">24</span></span>        | <span data-ttu-id="0ddae-367">FL-011</span><span class="sxs-lookup"><span data-stu-id="0ddae-367">FL-011</span></span>   | <span data-ttu-id="0ddae-368">LP02</span><span class="sxs-lookup"><span data-stu-id="0ddae-368">LP02</span></span>          | <span data-ttu-id="0ddae-369">5</span><span class="sxs-lookup"><span data-stu-id="0ddae-369">5</span></span>        |

    > [!NOTE]
    > <span data-ttu-id="0ddae-370">Du måste skapa de två ID-numren och använda platser som tillåter blandade artiklar t.ex. *FL-010* och *FL-011*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-370">You must create the two license plates and use locations that allow for mixed items, such as *FL-010* and *FL-011*.</span></span>

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a><span data-ttu-id="0ddae-371">Skapa en försäljningsorder och reservera ett specifikt ID-nummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-371">Create a sales order and reserve a specific license plate</span></span>

1. <span data-ttu-id="0ddae-372">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-372">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="0ddae-373">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-373">Select **New**.</span></span>
1. <span data-ttu-id="0ddae-374">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="0ddae-374">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="0ddae-375">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="0ddae-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="0ddae-376">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="0ddae-376">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="0ddae-377">Välj **OK** för att stänga dialogrutan **Skapa försäljningsorder** och öppna den nya försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="0ddae-377">Select **OK** to close the **Create sales order** dialog box and open the new sales order.</span></span>
1. <span data-ttu-id="0ddae-378">På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0ddae-378">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="0ddae-379">**Artikelnummer:** *Artikel1*</span><span class="sxs-lookup"><span data-stu-id="0ddae-379">**Item number:** *Item1*</span></span>
    - <span data-ttu-id="0ddae-380">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="0ddae-380">**Quantity:** *10*</span></span>

1. <span data-ttu-id="0ddae-381">Lägg till en andra försäljningsorderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0ddae-381">Add a second sales order line that has the following settings:</span></span>

    - <span data-ttu-id="0ddae-382">**Artikelnummer:** *Artikel2*</span><span class="sxs-lookup"><span data-stu-id="0ddae-382">**Item number:** *Item2*</span></span>
    - <span data-ttu-id="0ddae-383">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="0ddae-383">**Quantity:** *5*</span></span>

1. <span data-ttu-id="0ddae-384">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-384">Select **Save**.</span></span>
1. <span data-ttu-id="0ddae-385">På snabbfliken **Radinformation** på fliken **Inställningar** gör en anteckning av värdet **Parti-ID** för varje rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-385">On the **Line details** FastTab, on the **Setup** tab, make a note of the **Lot ID** value for each line.</span></span> <span data-ttu-id="0ddae-386">Dessa värden kommer att krävas vid reservation av specifika ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-386">These values will be required during reservation of specific license plates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-387">Om du vill reservera ett visst ID-nummer måste du använda dataentiteten **orderallokerade reservation av ID-nummer**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-387">To reserve a specific license plate, you must use the **Order-committed reservations per license plate** data entity.</span></span> <span data-ttu-id="0ddae-388">För att reservera en batchspårad artikel på ett visst ID-nummer kan du också använda sidan **Batchreservation**, som beskrivs i avsnittet [Ange detaljinformation om försäljningsorder](#sales-order-details).</span><span class="sxs-lookup"><span data-stu-id="0ddae-388">To reserve a batch-tracked item on a specific license plate, you can also use the **Batch reservation** page, as described in the [Enter sales order details](#sales-order-details) section.</span></span>
    >
    > <span data-ttu-id="0ddae-389">Om du anger ID-numret direkt på försäljningsorderraden och bekräftar den i systemet, används inte bearbetning av lagerstyrning för raden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-389">If you enter the license plate directly on the sales order line and confirm it to the system, warehouse management processing won't be used for the line.</span></span>

1. <span data-ttu-id="0ddae-390">Välj **Öppna i Microsoft Office**, välj **orderallokerade reservation av ID-nummer** och hämta filen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-390">Select **Open in Microsoft Office**, select **Order-committed reservations per license plate**, and download the file.</span></span>
1. <span data-ttu-id="0ddae-391">Öppna den nedladdade filen i Excel och välj **skrivskyddet** för att tillåta att Excel-tillägget körs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-391">Open the downloaded file in Excel, and select **Enable editing** to enable the Excel add-in to run.</span></span>
1. <span data-ttu-id="0ddae-392">Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-392">If you're running the Excel add-in for the first time, select **Trust this Add-in**.</span></span>
1. <span data-ttu-id="0ddae-393">Om du uppmanas att logga in klickar du på **Logga in** och loggar sedan in med samma inloggningsuppgifter som du använde för att logga in på Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0ddae-393">If you're prompted to sign in, select **Sign in**, and then sign in by using the same credentials that you used to sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="0ddae-394">Om du vill reservera en artikel på ett visst ID-nummer i Excel-tillägget väljer du **Ny** för att lägga till en reservationsrad och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="0ddae-394">To reserve an item on a specific license plate, in the Excel add-in, select **New** to add a reservation line, and then set the following values:</span></span>

    - <span data-ttu-id="0ddae-395">**Parti-ID:** ange värdet **parti-ID** som du hittade för försäljningsorderraden för *Artikel1*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-395">**Lot ID:** Enter the **Lot ID** value that you found for the sales order line for *Item1*.</span></span>
    - <span data-ttu-id="0ddae-396">**ID-nummer:** *LP02*</span><span class="sxs-lookup"><span data-stu-id="0ddae-396">**License plate:** *LP02*</span></span>
    - <span data-ttu-id="0ddae-397">**ReservedInventoryQuantity:** *10*</span><span class="sxs-lookup"><span data-stu-id="0ddae-397">**ReservedInventoryQuantity:** *10*</span></span>

1. <span data-ttu-id="0ddae-398">Välj **Ny** för att lägga till en till reservationsrad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="0ddae-398">Select **New** to add another reservation line, and set the following values:</span></span>

    - <span data-ttu-id="0ddae-399">**Parti-ID:** ange värdet **parti-ID** som du hittade för försäljningsorderraden för *Artikel2*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-399">**Lot ID:** Enter the **Lot ID** value you found for the sales order line for *Item2*.</span></span>
    - <span data-ttu-id="0ddae-400">**ID-nummer:** *LP02*</span><span class="sxs-lookup"><span data-stu-id="0ddae-400">**License plate:** *LP02*</span></span>
    - <span data-ttu-id="0ddae-401">**ReservedInventoryQuantity:** *5*</span><span class="sxs-lookup"><span data-stu-id="0ddae-401">**ReservedInventoryQuantity:** *5*</span></span>

1. <span data-ttu-id="0ddae-402">I Excel-tillägget väljer du **publicera** för att skicka tillbaka informationen till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0ddae-402">In the Excel add-in, select **Publish** to send the data back to Supply Chain Management.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-403">Reservationsraden kommer endast att visas i systemet om publiceringen slutförts utan fel.</span><span class="sxs-lookup"><span data-stu-id="0ddae-403">The reservation line will appear in the system only if publishing is completed without errors.</span></span>

1. <span data-ttu-id="0ddae-404">Gå tillbaka till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0ddae-404">Go back to Supply Chain Management.</span></span> 
1. <span data-ttu-id="0ddae-405">Om du vill granska artikelns reservation väljer du snabbfliken **försäljningsorderrader** på menyn **Lager** välj **Underhåll \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-405">To review the item's reservation, on the **Sales order lines** FastTab, on the **Inventory** menu, select **Maintain \> Reservation**.</span></span> <span data-ttu-id="0ddae-406">Observera att för försäljningsorderraden för *Aritikel1* är lagret på *10* reserverat och för försäljningsorderraden för *Artikel2* är lagret på *5* reserverat.</span><span class="sxs-lookup"><span data-stu-id="0ddae-406">Notice that, for the sales order line for *Item1*, inventory of *10* is reserved, and for the sales order line for *Item2*, inventory of *5* is reserved.</span></span>
1. <span data-ttu-id="0ddae-407">Om du vill granska lagertransaktioner som är relaterade till reservationen för försäljningsorderraden på snabbfliken **försäljningsorderrader** väljer du menyn **Lager** och **Visa \> Transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-407">To review inventory transactions that are related to the sales order line reservation, on the **Sales order lines** FastTab, on the **Inventory** menu, select **View \> Transactions**.</span></span> <span data-ttu-id="0ddae-408">Observera att det finns två transaktioner som är relaterade till reservationen: en där fältet **Referens** anges till *Försäljningsorder* och en där fältet **Referens** anges till *Orderallokerad reservation*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-408">Notice that there are two transactions that are related to the reservation: one where the **Reference** field is set to *Sales order* and one where the **Reference** field is set to *Order-committed reservation*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-409">En transaktion där fältet **Referens** anges till *Försäljningsorder* representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats** (plats, lagerställe och lagerstatus).</span><span class="sxs-lookup"><span data-stu-id="0ddae-409">A transaction where the **Reference** field is set to *Sales order* represents the order line reservation for inventory dimensions that are above the **Location** level (site, warehouse, and inventory status).</span></span> <span data-ttu-id="0ddae-410">En transaktion där fältet **referens** är inställt på *Orderallokerad reservation* representerar orderradreservationen för den specifika ID-numret och platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-410">A transaction where the **Reference** field is set to *Order-committed reservation* represents the order line reservation for the specific license plate and location.</span></span>

1. <span data-ttu-id="0ddae-411">För att frisläppa försäljningsorder i åtgärdsfönstret väljer du **Lagerställe** i gruppen **Åtgärder** välj **Släpp till distributionslager**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-411">To release the sales order, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a><span data-ttu-id="0ddae-412">Granska och bearbeta lagerställearbete med ett orderallokerat ID-nummer tilldelat</span><span class="sxs-lookup"><span data-stu-id="0ddae-412">Review and process warehouse work with order-committed license plates assigned</span></span>

1. <span data-ttu-id="0ddae-413">På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Arbetsinformation**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-413">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Work details**.</span></span>

    <span data-ttu-id="0ddae-414">När reservation görs för en specifik batch, använder systemet inte platsdirektiv när det skapar arbetet för försäljningsordern som använder reservation av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-414">As when reservation is done for a specific batch, the system doesn't use location directives when it creates the work for the sales order that uses license plate reservation.</span></span> <span data-ttu-id="0ddae-415">Eftersom den orderallokerade reservationen anger alla lagerdimensioner, inklusive lagerstället, behöver inte platsdirektiven användas eftersom dessa lagerdimensioner bara registrerats i arbetet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-415">Because the order-committed reservation specifies all the inventory dimensions, including the location, location directives don't have to be used, because those inventory dimensions are just entered in the work.</span></span> <span data-ttu-id="0ddae-416">De visas i avsnittet **från lagerdimensioner** på sidan **Arbetslagertransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-416">They are shown in the **From inventory dimensions** section on the **Work inventory transactions** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-417">När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på *Order-allokerad reservation* borttagen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-417">After the work is created, the item's inventory transaction where the **Reference** field is set to *Order-committed reservation* is removed.</span></span> <span data-ttu-id="0ddae-418">Lagertransaktionen där fältet **Referens** anges till *Arbete* innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0ddae-418">The inventory transaction where the **Reference** field is set to *Work* now holds the physical reservation for all the quantity's inventory dimensions.</span></span>

1. <span data-ttu-id="0ddae-419">Slutför plockning och placera arbetet på den mobila enheten med hjälp av ett menyalternativ där kryssrutan **Hantera efter ID-nummer** är markerad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-419">On the mobile device, finish picking and putting the work by using a menu item where the **Handle by license plate** check box is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddae-420">Med hjälp av funktionen **Hantera efter ID-nummer** kan du bearbeta hela ID-numret.</span><span class="sxs-lookup"><span data-stu-id="0ddae-420">The **Handle by license plate** functionality helps you process the whole license plate.</span></span> <span data-ttu-id="0ddae-421">Om du måste bearbeta en del av ID-numret kan du inte använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-421">If you must process part of the license plate, you can't use this functionality.</span></span>
    >
    > <span data-ttu-id="0ddae-422">Vi rekommenderar att du har separat arbete skapat för varje ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="0ddae-422">We recommend that you have separate work generated for each license plate.</span></span> <span data-ttu-id="0ddae-423">Om du vill uppnå det här resultatet använder du funktionen **Arbetsuppgiftshuvudet delas** på sidan **arbetsmall**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-423">To achieve this result, use the **Work header breaks** feature on the **Work template** page.</span></span>

    <span data-ttu-id="0ddae-424">ID-nummer *LP02* plockas nu för försäljningsorderrader och placeras på platsen *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="0ddae-424">License plate *LP02* is now picked for sales order lines and put to the *Baydoor* location.</span></span> <span data-ttu-id="0ddae-425">I detta skede är den klar att lastas och skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-425">At this point, it's ready to be loaded and dispatched to the customer.</span></span>

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="0ddae-426">Hantering av undantag av lageställearbete som har orderallokerade batchnummer</span><span class="sxs-lookup"><span data-stu-id="0ddae-426">Exception handling of warehouse work that has order-committed batch numbers</span></span>

<span data-ttu-id="0ddae-427">Orderallokerade batchnummer för lagerarbete för plockning är underställt samma standardundantagshantering och åtgärder för lagerställe som normalt arbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-427">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="0ddae-428">I allmänhet kan öppna arbete eller arbetsrad avbrytas, den kan avbrytas eftersom en användarplats är full, det kan tas bort och kan uppdateras på grund av en rörelse.</span><span class="sxs-lookup"><span data-stu-id="0ddae-428">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="0ddae-429">På samma sätt kan plockad kvantitet av arbete som redan har slutförts minskas, eller så kan arbetet återföras.</span><span class="sxs-lookup"><span data-stu-id="0ddae-429">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="0ddae-430">Följande nyckelregel används för alla dessa undantagsåtgärder: det batchnummer som har reserverats för kunden kan aldrig ersättas med ett annat batchnummer, men dess lagringsdimensioner (plats och registreringsskylt) kan ändras genom antingen manuell uppdatering av användaren eller automatiska uppdateringar i systemet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-430">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="0ddae-431">Den automatiska uppdateringen baseras på samma slumpmässiga tilldelning av lagringsdimensioner som används när en specifik batch automatiskt reserverades men inga lagringsdimensioner har angetts.</span><span class="sxs-lookup"><span data-stu-id="0ddae-431">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="0ddae-432">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="0ddae-432">Example scenario</span></span>

<span data-ttu-id="0ddae-433">Ett exempel på det här scenariot är en situation där arbetet med tidigare slutfört arbete avbryts med funktionen **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-433">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="0ddae-434">I det här exemplet förutsätts det att du redan har utfört stegen som beskrivs i [exempelscenario: allokering av batchnummer](#Example-batch-allocation).</span><span class="sxs-lookup"><span data-stu-id="0ddae-434">This example assumes that you've already completed the steps that are described in [Example scenario: Batch number allocation](#Example-batch-allocation).</span></span> <span data-ttu-id="0ddae-435">Det fortsätter från det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-435">It continues from that example.</span></span>

1. <span data-ttu-id="0ddae-436">Gå till **Lagerstyrning** \> **Laster** \> **Aktiva laster**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-436">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="0ddae-437">Välj den last som skapades i samband med leveransen av din försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="0ddae-437">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="0ddae-438">På snabbfliken **Läs in orderrader** väljer du **minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-438">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="0ddae-439">På sidan **minska plockad kvantitet** i fältet **Flytta till plats** väljer du **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-439">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="0ddae-440">I fältet **Flytta till registreringsskylt** väljer du **LP33**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-440">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="0ddae-441">I rutnätet skriver du **Lagerkvantitet där plockning ska hävas** anger du **10**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-441">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="0ddae-442">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-442">Select **OK**.</span></span>

<span data-ttu-id="0ddae-443">Här är resultaten av åtgärden för ej plockning:</span><span class="sxs-lookup"><span data-stu-id="0ddae-443">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="0ddae-444">Status för det tidigare avslutade arbetet är inställd på **annullerat**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-444">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="0ddae-445">Nytt arbete för typen **lagerrörelse** skapas för det ej plockade antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-445">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="0ddae-446">Det här arbetet motsvarar flyttningen från platsen **Baydoor** till registreringsskylten **LP33** på plats **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-446">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="0ddae-447">Status är inställt på **Stängd**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-447">The status is set to **Closed**.</span></span>
- <span data-ttu-id="0ddae-448">Systemet omreserverar batchnumret som ursprungligen beställdes och tilldelar plats- och registreingsskylt-ID.</span><span class="sxs-lookup"><span data-stu-id="0ddae-448">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="0ddae-449">(Den här processen motsvarar att köra funktionen **reservera rad** för orderraden för ett givet batchnummer).</span><span class="sxs-lookup"><span data-stu-id="0ddae-449">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="0ddae-450">Som ett resultat visas batch **B11** som genomförd på snabbfliken **batchnummer för källrad** på sidan **Batch-reservation** och fältet **Reservation** innehåller antalet **10** för batchnummer **B11**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-450">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="0ddae-451">Dessutom är fältet **plats** inställt **FL-001** och fältet **registreringsskylt** är inställt på **LP11**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-451">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="0ddae-452">(Du kan lägga till dessa fält i rutnätet om de inte visas.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-452">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="0ddae-453">Följande register ger en översikt som visar hur systemet hanterar den beställda batchreservationen för specifika lageråtgärder.</span><span class="sxs-lookup"><span data-stu-id="0ddae-453">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="0ddae-454">Om du vill tolka innehållet i tabellerna antar du att varje lageråtgärd körs i samband med befintligt lagerarbete som har sitt ursprung i en batchorder som har genomförts med order, eller att körningen av varje lageråtgärd påverkar arbete av den typen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-454">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="0ddae-455">I dessa register visar kolumnen "Batchkvantitet är tillgänglig" om en batchkvantitet är tillgänglig utöver kvantiteten som antingen redan har reserverats för den aktuella orderallokerade reservationen eller redan har reserverats för det lagerställearbete som härstammar från reservationer av den typen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-455">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="0ddae-456">Åsidosätt plockplatsen på det öppna arbetet</span><span class="sxs-lookup"><span data-stu-id="0ddae-456">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-457">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-457">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-458">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-458">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-459">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-459">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-460">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-460">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-461">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-461">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-462">Alternativet <strong>Tillåt åsidosättning av plockplats</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0ddae-462">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="0ddae-463">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-463">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-464">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerställeappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-464">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="0ddae-465">Välj <strong>föreslå</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-465">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="0ddae-466">Bekräfta den nya platsen som föreslås baserat på tillgängligheten för batchkvantitet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-466">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-467">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="0ddae-467">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="0ddae-468">Platsen på plockraden uppdateras till den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-468">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="0ddae-469">(Om platsen är registreringsskyltkontrollerad, tilldelas en slumpmässig registreringsskylt till arbetslagertransaktionen och arbetaren kan välja från registreringsskylt som har den tillgängliga kvantiteten.)</span><span class="sxs-lookup"><span data-stu-id="0ddae-469">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="0ddae-470">Om kvantiteten finns på fler än en registreringsskylt på den nya platsen, delas den ursprungliga plockningsraden på flera rader för att matcha varje registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-470">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-471">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="0ddae-471">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-472">Nr</span><span class="sxs-lookup"><span data-stu-id="0ddae-472">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-473">Välj menyalternativ <strong>Åsidosätt plats</strong> i lagerställeappen när du startar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-473">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="0ddae-474">Ange en plats manuellt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-474">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-475">Åtgärden <strong>åsidosätta plats</strong> är inte möjlig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-475">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="0ddae-476">Den misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="0ddae-476">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="0ddae-477">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-477">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="0ddae-478">Full knapp – dela en arbetsrad på grund av spill på användarplatsen</span><span class="sxs-lookup"><span data-stu-id="0ddae-478">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-479">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-479">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-480">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-480">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-481">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-481">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-482">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-482">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-483">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-483">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0ddae-484">Alternativet <strong>Tillåt delning av arbete</strong> är aktiverat på menyalternativet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-484">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="0ddae-485">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="0ddae-485">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-486">Välj menyalternativet <strong>Full</strong> i lagerställeappen när du bearbetar plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-486">Select the <strong>Full</strong> menu item on the warehouse app when you process picking work.</span></span></li>
<li><span data-ttu-id="0ddae-487">I fältet <strong>Plockkvantitet</strong> ange den delkvantitet för att ange den fullständiga kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="0ddae-487">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-488">I det aktuella arbetet uppdateras kvantiteten till den resterande kvantiteten som måste plockas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-488">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="0ddae-489">Nytt arbete för plockad kvantitet skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-489">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="0ddae-490">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-490">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="0ddae-491">Minska den plockade kvantiteten färdigt arbete (från en last)</span><span class="sxs-lookup"><span data-stu-id="0ddae-491">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-492">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-492">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-493">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-493">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-494">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-494">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-495">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-495">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-496">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-496">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-497">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-497">Not applicable</span></span></td>
<td><span data-ttu-id="0ddae-498">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-498">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-499">Öppna sidan <strong>minska plockad kvantitet</strong> kvantitet från lastraden.</span><span class="sxs-lookup"><span data-stu-id="0ddae-499">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="0ddae-500">Ange den fulla kvantitet att häva plockning.</span><span class="sxs-lookup"><span data-stu-id="0ddae-500">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="0ddae-501">Välj en "flytta till" plats/registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-501">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="0ddae-502">Arbete som är kopplat till lastraden avbryts.</span><span class="sxs-lookup"><span data-stu-id="0ddae-502">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="0ddae-503">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-503">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-504">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-504">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-505">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-505">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-506">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-506">No</span></span></td>
<td><span data-ttu-id="0ddae-507">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-507">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-508">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-508">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-509">Kvantiteten reserveras för samma batch och för samma plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) som angavs under hävning av plockningen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-509">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="0ddae-510">Flytta en artikel inom ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="0ddae-510">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="0ddae-511">Den här lageråtgärden kan bara användas i rörelse av typen **Process för att skapa arbete**, inte för rörelse per mall.</span><span class="sxs-lookup"><span data-stu-id="0ddae-511">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-512">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-512">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-513">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-513">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-514">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-514">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-515">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-515">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-516">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-516">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-517">Alternativet <strong>Tillåt flyttning av lager med associerat arbete</strong> är aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0ddae-517">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="0ddae-518">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-518">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-519">Starta en rörelse på lagerställeappen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-519">Start a movement on the warehouse app.</span></span></li>
<li><span data-ttu-id="0ddae-520">Ange "från-" och "till"-platser.</span><span class="sxs-lookup"><span data-stu-id="0ddae-520">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="0ddae-521">För allt befintligt arbete som påverkas av flyttningen uppdateras plockplatsen till den nya "till"-platsen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-521">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="0ddae-522">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-522">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-523">Alla befintliga reservationer som påverkas av flyttningen av kvantiteten från den angivna platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-523">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-524">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-524">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-525">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-525">No</span></span></td>
<td><span data-ttu-id="0ddae-526">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-526">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-527">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-527">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-528">Alla befintliga reservationer som påverkas av antalet transporter från den angivna platsen reserveras för samma batch och för den nya "till"-platsen och registreringsskylten (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="0ddae-528">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="0ddae-529">Återför den plockade kvantiteten färdigt arbete (från en last eller en påfyllnad)</span><span class="sxs-lookup"><span data-stu-id="0ddae-529">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-530">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-530">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-531">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-531">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-532">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-532">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-533">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-533">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-534">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-534">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="0ddae-535">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-535">Not applicable</span></span></td>
<td><span data-ttu-id="0ddae-536">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-536">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-537">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-537">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="0ddae-538">Välj alternativet <strong>Lämna artiklar på aktuell plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="0ddae-538">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-539">Allt arbete som är kopplat till lasten avbryts.</span><span class="sxs-lookup"><span data-stu-id="0ddae-539">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="0ddae-540">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-540">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-541">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-541">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-542">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-542">No</span></span></td>
<td><span data-ttu-id="0ddae-543">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-543">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-544">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-544">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-545">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten lämnades vid återföring.</span><span class="sxs-lookup"><span data-stu-id="0ddae-545">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-546">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-546">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-547">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-547">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="0ddae-548">Välj alternativet <strong>Tilldela artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="0ddae-548">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-549">Aktuellt arbete är annullerat.</span><span class="sxs-lookup"><span data-stu-id="0ddae-549">The current work is canceled.</span></span></li>
<li><span data-ttu-id="0ddae-550">Nytt arbete för lagerrrörelse skapas och stängs.</span><span class="sxs-lookup"><span data-stu-id="0ddae-550">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-551">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-551">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-552">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-552">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-553">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-553">No</span></span></td>
<td><span data-ttu-id="0ddae-554">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-554">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-555">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-555">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-556">Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten tilldelades till vid återföring.</span><span class="sxs-lookup"><span data-stu-id="0ddae-556">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-557">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-557">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-558">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-558">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="0ddae-559">Välj alternativet <strong>Flytta artiklar till denna plats</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="0ddae-559">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-560">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="0ddae-560">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="0ddae-561">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-561">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-562">Ja/Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-562">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-563">Öppna sidan <strong>Återför arbete</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-563">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="0ddae-564">Välj alternativet <strong>Flytta artiklar baserat på platsdirektiv</strong> på sidan begäran.</span><span class="sxs-lookup"><span data-stu-id="0ddae-564">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-565">Återföring stöds inte.</span><span class="sxs-lookup"><span data-stu-id="0ddae-565">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="0ddae-566">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-566">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="0ddae-567">Kort plockning av en kvantitet – registrera kvantiteten som fysiskt inte finns på plats/registreringsskylt medan du utför plockningsarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-567">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-568">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-568">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-569">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-569">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-570">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-570">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-571">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-571">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-572">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-572">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-573">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-573">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="0ddae-574">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-574">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-575">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-575">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-576">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-576">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-577">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-577">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-578">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-578">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="0ddae-579">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-579">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-580">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-580">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-581">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-581">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-582">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-582">No</span></span></td>
<td><span data-ttu-id="0ddae-583">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-583">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="0ddae-584">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="0ddae-584">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="0ddae-585">Det aktuella arbetet förblir öppet.</span><span class="sxs-lookup"><span data-stu-id="0ddae-585">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-586">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-586">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-587">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-587">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="0ddae-588">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-588">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-589">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-589">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-590">I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-590">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-591">I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-591">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-592">Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-592">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="0ddae-593">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-593">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-594">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen reserveras för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-594">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-595">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-595">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-596">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-596">No</span></span></td>
<td><span data-ttu-id="0ddae-597">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-597">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-598">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-598">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-599">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen tas bort.</span><span class="sxs-lookup"><span data-stu-id="0ddae-599">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-600">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej/Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-600">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="0ddae-601">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0ddae-601">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="0ddae-602">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-602">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-603">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-603">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-604">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-604">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-605">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-605">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="0ddae-606">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="0ddae-606">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-607">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="0ddae-607">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="0ddae-608">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-608">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="0ddae-609">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-609">The put line is canceled.</span></span></li>
<li><span data-ttu-id="0ddae-610">En ny plockrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-610">A new pick line is created.</span></span> <span data-ttu-id="0ddae-611">Den använder den plats/registreringsskylt som användaren har valt.</span><span class="sxs-lookup"><span data-stu-id="0ddae-611">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="0ddae-612">En ny placeringsrad har skapats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-612">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="0ddae-613">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-613">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-614">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-614">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-615">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-615">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="0ddae-616">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0ddae-616">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="0ddae-617">Nr</span><span class="sxs-lookup"><span data-stu-id="0ddae-617">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-618">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-618">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-619">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-619">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-620">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-620">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-621">Den korta plock åtgärden misslyckas och ett fel genereras.</span><span class="sxs-lookup"><span data-stu-id="0ddae-621">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="0ddae-622">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="0ddae-622">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-623">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-623">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="0ddae-624">Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0ddae-624">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="0ddae-625">Nr</span><span class="sxs-lookup"><span data-stu-id="0ddae-625">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-626">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-626">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-627">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-627">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-628">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-628">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="0ddae-629">Välj plats/registreringsskylt i listan.</span><span class="sxs-lookup"><span data-stu-id="0ddae-629">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="0ddae-630">I det aktuella arbetet inträffar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="0ddae-630">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="0ddae-631">Plockraden är stängd och plockad kvantitet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-631">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="0ddae-632">Placeringsraden har annullerats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-632">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="0ddae-633">En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</span><span class="sxs-lookup"><span data-stu-id="0ddae-633">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0ddae-634">Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen/registreringsskylten tas bort.</span><span class="sxs-lookup"><span data-stu-id="0ddae-634">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-635">Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Automatisk</strong>, <strong>Justera lager</strong> = <strong>Ja/Nej</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja/Nej</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-635">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="0ddae-636">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="0ddae-636">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-637">Välj menyalternativet <strong>Kort plockning</strong> i lagerställeappen när du utför plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-637">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="0ddae-638">I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</span><span class="sxs-lookup"><span data-stu-id="0ddae-638">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="0ddae-639">I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med automatisk omallokering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-639">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-640">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="0ddae-640">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="0ddae-641">Korta plockningar som inbegriper automatisk omfördelning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="0ddae-641">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="0ddae-642">Ändra lagerstatus</span><span class="sxs-lookup"><span data-stu-id="0ddae-642">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="0ddae-643">Den här lageråtgärden kan utföras från flera startpunkter.</span><span class="sxs-lookup"><span data-stu-id="0ddae-643">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="0ddae-644">I exemplet som visas här används åtgärden **Ändring av lagerstatus** på sidan **Behållning efter plats**.</span><span class="sxs-lookup"><span data-stu-id="0ddae-644">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0ddae-645">Viktig inställningsparameter</span><span class="sxs-lookup"><span data-stu-id="0ddae-645">Key setup parameter</span></span></th>
<th><span data-ttu-id="0ddae-646">Batchkvantitet är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0ddae-646">Batch quantity is available</span></span></th>
<th><span data-ttu-id="0ddae-647">Viktiga användarsteg</span><span class="sxs-lookup"><span data-stu-id="0ddae-647">Key user steps</span></span></th>
<th><span data-ttu-id="0ddae-648">Lagerarbete</span><span class="sxs-lookup"><span data-stu-id="0ddae-648">Warehouse work</span></span></th>
<th><span data-ttu-id="0ddae-649">Orderallokerad batchreservation</span><span class="sxs-lookup"><span data-stu-id="0ddae-649">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-650">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> är fältet <strong>ta bort reservationer och markeringar</strong> inställt på <strong>Reservationer</strong> eller <strong>Markeringar och reservationer</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-650">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="0ddae-651">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-651">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-652">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-652">Select a specific location.</span></span></li>
<li><span data-ttu-id="0ddae-653">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="0ddae-653">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="0ddae-654">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-654">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="0ddae-655">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-655">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-656">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-656">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="0ddae-657">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-657">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-658">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-658">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="0ddae-659">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="0ddae-659">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="0ddae-660">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0ddae-660">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-661">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-661">No</span></span></td>
<td><span data-ttu-id="0ddae-662">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-662">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-663">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-663">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="0ddae-664">Reservationen tas bort.</span><span class="sxs-lookup"><span data-stu-id="0ddae-664">The reservation is removed.</span></span></li>
<li><span data-ttu-id="0ddae-665">Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="0ddae-665">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="0ddae-666">En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0ddae-666">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="0ddae-667">På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> anges fältet <strong>Ta bort reservationer och markeringar</strong> till <strong>Ingen</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-667">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="0ddae-668">Ja</span><span class="sxs-lookup"><span data-stu-id="0ddae-668">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0ddae-669">Välj en specifik plats.</span><span class="sxs-lookup"><span data-stu-id="0ddae-669">Select a specific location.</span></span></li>
<li><span data-ttu-id="0ddae-670">Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</span><span class="sxs-lookup"><span data-stu-id="0ddae-670">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="0ddae-671">Välj <strong>Ändring av lagerstatus</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-671">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="0ddae-672">Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</span><span class="sxs-lookup"><span data-stu-id="0ddae-672">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="0ddae-673">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-673">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="0ddae-674">Kvantiteten har reserverats för samma batch.</span><span class="sxs-lookup"><span data-stu-id="0ddae-674">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="0ddae-675">Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0ddae-675">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0ddae-676">Nej</span><span class="sxs-lookup"><span data-stu-id="0ddae-676">No</span></span></td>
<td><span data-ttu-id="0ddae-677">Se föregående rad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-677">See the previous row.</span></span></td>
<td><span data-ttu-id="0ddae-678">Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</span><span class="sxs-lookup"><span data-stu-id="0ddae-678">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="0ddae-679">Ändringar i lagerstatus är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="0ddae-679">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="0ddae-680">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="0ddae-680">Limitations</span></span>

- <span data-ttu-id="0ddae-681">Den flexibla funktionen för dimensionsreservation på lagernivå stöder inte följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="0ddae-681">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="0ddae-682">Hantering av fångstvikt</span><span class="sxs-lookup"><span data-stu-id="0ddae-682">Catch weight management</span></span>
    - <span data-ttu-id="0ddae-683">Fysiskt negativt lager</span><span class="sxs-lookup"><span data-stu-id="0ddae-683">Physical negative inventory</span></span>
    - <span data-ttu-id="0ddae-684">Reservation mot beställda leveranser</span><span class="sxs-lookup"><span data-stu-id="0ddae-684">Reservation against ordered supply</span></span>
    - <span data-ttu-id="0ddae-685">Överföringsorder och plockning av råmaterial</span><span class="sxs-lookup"><span data-stu-id="0ddae-685">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="0ddae-686">Behållarens konsolideringsregel för paketering av direktivenhet har begränsningar.</span><span class="sxs-lookup"><span data-stu-id="0ddae-686">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="0ddae-687">För orderallokerade reservationer rekommenderar vi att du inte använder uppbyggnadsmallar för behållare där fältet **Packa efter enhet för direktiv** är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="0ddae-687">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="0ddae-688">I den aktuella designen används inte platsdirektiv när lagerarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="0ddae-688">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="0ddae-689">Det innebär att endast den minsta enheten i enhetssekvensgruppen (lagerenheten) används under påfyllnadssteget skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="0ddae-689">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
