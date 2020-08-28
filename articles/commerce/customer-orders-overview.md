---
title: Kundorder i Modern POS (MPOS)
description: Det här avsnittet innehåller information om kundorder i Modern POS (MOPS). Kundorder kallas även specialorder. Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden.
author: josaw1
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 87d1217204e0c5cb22f567793b043bf399ca5685
ms.sourcegitcommit: b07434f2bd6db67d8dd712f096329acc902751ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699379"
---
# <a name="customer-orders-in-modern-pos-mpos"></a><span data-ttu-id="d3d71-105">Kundorder i Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="d3d71-105">Customer orders in Modern POS (MPOS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d3d71-106">Det här avsnittet innehåller information om kundorder i Modern POS (MOPS).</span><span class="sxs-lookup"><span data-stu-id="d3d71-106">This topic provides information about customer orders in Modern POS (MPOS).</span></span> <span data-ttu-id="d3d71-107">Kundorder kallas även specialorder.</span><span class="sxs-lookup"><span data-stu-id="d3d71-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="d3d71-108">Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="d3d71-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="d3d71-109">I en handelsvärld kännetecknad av omnikanaler erbjuder många återförsäljare möjlighet till kundorder (eller specialorder) för att uppfylla kraven för olika produkter och utföranden.</span><span class="sxs-lookup"><span data-stu-id="d3d71-109">In an omni-channel commerce world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="d3d71-110">Här följer några vanliga scenarier:</span><span class="sxs-lookup"><span data-stu-id="d3d71-110">Here are some typical scenarios:</span></span>

- <span data-ttu-id="d3d71-111">En kund vill att produkterna ska levereras till en specifik adress på ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="d3d71-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
- <span data-ttu-id="d3d71-112">En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna.</span><span class="sxs-lookup"><span data-stu-id="d3d71-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
- <span data-ttu-id="d3d71-113">En kund vill ha någon annan ska hämta produkterna som kunden har köpt.</span><span class="sxs-lookup"><span data-stu-id="d3d71-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="d3d71-114">Återförsäljare använder också kundorder för att minimera förlorade försäljningar som lagerfel annars kan medföra, detta eftersom varorna kan levereras eller avhämtas vid en annan tidpunkt eller på en annan plats.</span><span class="sxs-lookup"><span data-stu-id="d3d71-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="d3d71-115">Skapa kundorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-115">Set up customer orders</span></span>

<span data-ttu-id="d3d71-116">Här följer några av de parametrar som kan anges på sidan **Handelsparametrar** för att definiera hur kundorder uppfylls:</span><span class="sxs-lookup"><span data-stu-id="d3d71-116">Here are some of the parameters that can be set on the **Commerce parameters** page to define how customer orders are fulfilled:</span></span>

- <span data-ttu-id="d3d71-117">**Standardinsättningsprocent** – Ange det belopp som kunden måste betala som en insättning innan en order kan bekräftas.</span><span class="sxs-lookup"><span data-stu-id="d3d71-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="d3d71-118">Standardinsättningsbeloppet anges som en procentandel av ordervärdet.</span><span class="sxs-lookup"><span data-stu-id="d3d71-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="d3d71-119">Beroende på behörighet kan en butiksmedarbetare kringgå beloppet genom att använda funktionen **Insättningsåsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="d3d71-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
- <span data-ttu-id="d3d71-120">**Annulleringsavgift i procent** – Om en avgift ska användas när en kundorder annulleras, ange då avgiftsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="d3d71-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
- <span data-ttu-id="d3d71-121">**Kod för annulleringsavgift** – Om en avgift används när kundorder annulleras, kommer denna avgift att återspeglas under en avgiftskod på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="d3d71-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="d3d71-122">Använd denna parameter om du vill definiera avgiftskoden för annulleringen.</span><span class="sxs-lookup"><span data-stu-id="d3d71-122">Use this parameter to define the cancellation charge code.</span></span>
- <span data-ttu-id="d3d71-123">**Leveransavgiftskod** – Återförsäljare kan debitera en extra avgift för leverans av varor till en kund.</span><span class="sxs-lookup"><span data-stu-id="d3d71-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="d3d71-124">Leveransavgiften återspeglas under en avgiftskod på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="d3d71-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="d3d71-125">Använd denna parameter för att mappa leveransavgiftskoden till fraktkostnader på kundordern.</span><span class="sxs-lookup"><span data-stu-id="d3d71-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
- <span data-ttu-id="d3d71-126">**Återbetala leveransavgifter** – Ange om leveransavgifter som associeras med en kundorder kan återbetalas.</span><span class="sxs-lookup"><span data-stu-id="d3d71-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
- <span data-ttu-id="d3d71-127">**Maxbelopp utan godkännande** – Om leveransavgifter kan återbetalas, ange då maxbelopp för återbetalning av leveransavgifter för returorder.</span><span class="sxs-lookup"><span data-stu-id="d3d71-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="d3d71-128">Om detta värde överskrids krävs åsidosättning utförd av chef för att fortsätta med återbetalningen.</span><span class="sxs-lookup"><span data-stu-id="d3d71-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="d3d71-129">Återbetalning av leveransavgifter kan överstiga det ursprungligen betalade beloppet i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="d3d71-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>

    - <span data-ttu-id="d3d71-130">Avgifter tillämpas på nivån för försäljningsorderrubrik, och när en viss kvantitet av en produktlinje returneras, kan maxbeloppet för återbetalning av leveranskostnader som tillåts för produkterna och kvantiteten inte fastställas på ett sätt som passar alla handelskunder.</span><span class="sxs-lookup"><span data-stu-id="d3d71-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all customers.</span></span>
    - <span data-ttu-id="d3d71-131">Leveransavgifterna infaller efter alla leveransförekomster.</span><span class="sxs-lookup"><span data-stu-id="d3d71-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="d3d71-132">Om en kund returnerar varor flera gånger och återförsäljarens policy anger att återförsäljaren ska stå för kostnaderna för returleveranser, kommer kostnaderna för returleveranser att överstiga de faktiska leveranskostnaderna.</span><span class="sxs-lookup"><span data-stu-id="d3d71-132">If a customer returns products multiple times, and the retailer's policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>
    
- <span data-ttu-id="d3d71-133">**Momsberäkningsbeteende** - **Omräkning** är standardinställningen och den traditionella inställningen för hur moms räknas om när ordern importeras till backoffice.</span><span class="sxs-lookup"><span data-stu-id="d3d71-133">**Tax calculation behavior** - **Recalculate** is the default and traditional setting for how taxes are recalculated when the order is imported into the back office.</span></span> <span data-ttu-id="d3d71-134">**Omberäkna inte** inaktiverar momsomberäkning tills eller om inte beställningen redigeras i backoffice, när omberäkning initieras.</span><span class="sxs-lookup"><span data-stu-id="d3d71-134">**Don't recalculate** disables tax recalculation until or unless the order is edited in the back office, when recalculation is triggered.</span></span> 

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="d3d71-135">Transaktionsflöde för kundorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-135">Transaction flow for customer orders</span></span>

### <a name="create-a-customer-order-in-modern-pos"></a><span data-ttu-id="d3d71-136">Skapa kundorder i Modern POS</span><span class="sxs-lookup"><span data-stu-id="d3d71-136">Create a customer order in Modern POS</span></span>

1. <span data-ttu-id="d3d71-137">Lägg till en kund i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d3d71-137">Add a customer to the transaction.</span></span>
2. <span data-ttu-id="d3d71-138">Lägg till produkter i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="d3d71-138">Add products to the cart.</span></span>
3. <span data-ttu-id="d3d71-139">Klicka på **Skapa kundorder** och välj sedan ordertypen.</span><span class="sxs-lookup"><span data-stu-id="d3d71-139">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="d3d71-140">Ordertypen kan antingen vara **Kundorder** eller **Offert**.</span><span class="sxs-lookup"><span data-stu-id="d3d71-140">The order type can be either **Customer order** or **Quote**.</span></span>
4. <span data-ttu-id="d3d71-141">Klicka på **Leverera val** eller **Leverera alla** om du vill sända produkterna till en adress på kundkontot, ange begärt speditionsdatum och fraktkostnaderna.</span><span class="sxs-lookup"><span data-stu-id="d3d71-141">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5. <span data-ttu-id="d3d71-142">Klicka på **Hämta valda** eller **Hämta alla** för att välja produkter som hämtas från den aktuella butiken eller en annan butik vid ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="d3d71-142">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6. <span data-ttu-id="d3d71-143">Inkassera av insättningsbeloppet, om en deposition krävs.</span><span class="sxs-lookup"><span data-stu-id="d3d71-143">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="d3d71-144">Redigera en befintlig kundorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-144">Edit an existing customer order</span></span>

1. <span data-ttu-id="d3d71-145">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-145">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="d3d71-146">Hitta och markera den order som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="d3d71-146">Find and select the order to edit.</span></span> <span data-ttu-id="d3d71-147">Klicka på **Redigera** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-147">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="d3d71-148">Hämta en order</span><span class="sxs-lookup"><span data-stu-id="d3d71-148">Pick up an order</span></span>

1. <span data-ttu-id="d3d71-149">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-149">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="d3d71-150">Välj den order som ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="d3d71-150">Select the order to pick up.</span></span> <span data-ttu-id="d3d71-151">Klicka på **Hämtning och paketering** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-151">At the bottom of the page, click **Picking and packing**.</span></span>
3. <span data-ttu-id="d3d71-152">Klicka på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="d3d71-152">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="d3d71-153">Avbryt en order</span><span class="sxs-lookup"><span data-stu-id="d3d71-153">Cancel an order</span></span>

1. <span data-ttu-id="d3d71-154">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-154">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="d3d71-155">Markera ordern som ska avbrytas.</span><span class="sxs-lookup"><span data-stu-id="d3d71-155">Select the order to cancel.</span></span> <span data-ttu-id="d3d71-156">Klicka på **Avbryt** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-156">At the bottom of the page, click **Cancel**.</span></span>

### <a name="create-a-return-order"></a><span data-ttu-id="d3d71-157">Skapa en returorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-157">Create a return order</span></span>

1. <span data-ttu-id="d3d71-158">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-158">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="d3d71-159">Markera den order som du vill returnera, välj fakturan för ordern och välj sedan produktlinje för de varor som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="d3d71-159">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3. <span data-ttu-id="d3d71-160">Klicka på **Returnera order** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="d3d71-160">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="d3d71-161">Asynkront transaktionsflöde för kundorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-161">Asynchronous transaction flow for customer orders</span></span>

<span data-ttu-id="d3d71-162">Kundorder kan skapas från kassaklienten i antingen synkront eller asynkront läge.</span><span class="sxs-lookup"><span data-stu-id="d3d71-162">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="d3d71-163">Aktivera skapande av kundorder i asynkront läge</span><span class="sxs-lookup"><span data-stu-id="d3d71-163">Enable customer orders to be created in asynchronous mode</span></span>

1. <span data-ttu-id="d3d71-164">Klicka på **butik och handel** &gt; **kanalinställning** &gt; **kassainställning** &gt; **kassaprofil** &gt; **funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="d3d71-164">Click **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2. <span data-ttu-id="d3d71-165">I snabbfliken **Allmänt** anger du alternativet för **Skapa kundorder i asynkront läge** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d3d71-165">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="d3d71-166">När alternativet **Skapa kundorder i asynkront läge** är inställt på **Ja**, skapas kundorder alltid i asynkront läge, även om tjänsten för Retail Transaction Service (RTS) är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d3d71-166">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="d3d71-167">Om du anger detta alternativ som **Nej**, skapas kundorder alltid i synkront läge med hjälp av RTS.</span><span class="sxs-lookup"><span data-stu-id="d3d71-167">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="d3d71-168">När kundorder skapas i asynkront läget hämtas och infogas de i Handel genom hämtningsjobb.</span><span class="sxs-lookup"><span data-stu-id="d3d71-168">When customer orders are created in asynchronous mode, they are pulled and inserted into Commerce by Pull (P) jobs.</span></span> <span data-ttu-id="d3d71-169">Motsvarande försäljningsorder skapas när **Synkronisera order** körs antingen manuellt eller via en batchprocess.</span><span class="sxs-lookup"><span data-stu-id="d3d71-169">The corresponding sales orders are created when **Synchronize orders** is run either manually or through a batch process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3d71-170">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d3d71-170">Additional resources</span></span>

[<span data-ttu-id="d3d71-171">Kombinerade kundorder</span><span class="sxs-lookup"><span data-stu-id="d3d71-171">Hybrid customer orders</span></span>](hybrid-customer-orders.md)
