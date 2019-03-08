---
title: Kundorder i Retail Modern POS (MPOS)
description: Det här avsnittet innehåller information om kundorder i Retail Modern POS (MPOS). Kundorder kallas även specialorder. Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
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
ms.openlocfilehash: b54f39cc7896871d77f9371e6197bf6dbaac51de
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "336622"
---
# <a name="customer-orders-in-retail-modern-pos-mpos"></a><span data-ttu-id="cde39-105">Kundorder i Retail Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="cde39-105">Customer orders in Retail Modern POS (MPOS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cde39-106">Det här avsnittet innehåller information om kundorder i Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="cde39-106">This topic provides information about customer orders in Retail Modern POS (MPOS).</span></span> <span data-ttu-id="cde39-107">Kundorder kallas även specialorder.</span><span class="sxs-lookup"><span data-stu-id="cde39-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="cde39-108">Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="cde39-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="cde39-109">I en handelsvärld kännetecknad av omnikanaler erbjuder många återförsäljare möjlighet till kundorder (eller specialorder) för att uppfylla kraven för olika produkter och utföranden.</span><span class="sxs-lookup"><span data-stu-id="cde39-109">In an omni-channel retail world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="cde39-110">Här följer några vanliga scenarier:</span><span class="sxs-lookup"><span data-stu-id="cde39-110">Here are some typical scenarios:</span></span>

- <span data-ttu-id="cde39-111">En kund vill att produkterna ska levereras till en specifik adress på ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="cde39-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
- <span data-ttu-id="cde39-112">En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna.</span><span class="sxs-lookup"><span data-stu-id="cde39-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
- <span data-ttu-id="cde39-113">En kund vill ha någon annan ska hämta produkterna som kunden har köpt.</span><span class="sxs-lookup"><span data-stu-id="cde39-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="cde39-114">Återförsäljare använder också kundorder för att minimera förlorade försäljningar som lagerfel annars kan medföra, detta eftersom varorna kan levereras eller avhämtas vid en annan tidpunkt eller på en annan plats.</span><span class="sxs-lookup"><span data-stu-id="cde39-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="cde39-115">Skapa kundorder</span><span class="sxs-lookup"><span data-stu-id="cde39-115">Set up customer orders</span></span>

<span data-ttu-id="cde39-116">Här följer några av de parametrar som kan anges på sidan **Handelsparametrar** för att definiera hur kundorder uppfylls:</span><span class="sxs-lookup"><span data-stu-id="cde39-116">Here are some of the parameters that can be set on the **Retail parameters** page to define how customer orders are fulfilled:</span></span>

- <span data-ttu-id="cde39-117">**Standardinsättningsprocent** – Ange det belopp som kunden måste betala som en insättning innan en order kan bekräftas.</span><span class="sxs-lookup"><span data-stu-id="cde39-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="cde39-118">Standardinsättningsbeloppet anges som en procentandel av ordervärdet.</span><span class="sxs-lookup"><span data-stu-id="cde39-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="cde39-119">Beroende på behörighet kan en butiksmedarbetare kringgå beloppet genom att använda funktionen **Insättningsåsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="cde39-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
- <span data-ttu-id="cde39-120">**Annulleringsavgift i procent** – Om en avgift ska användas när en kundorder annulleras, ange då avgiftsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="cde39-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
- <span data-ttu-id="cde39-121">**Kod för annulleringsavgift** – Om en avgift används när kundorder annulleras, kommer denna avgift att återspeglas under en avgiftskod på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="cde39-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="cde39-122">Använd denna parameter om du vill definiera avgiftskoden för annulleringen.</span><span class="sxs-lookup"><span data-stu-id="cde39-122">Use this parameter to define the cancellation charge code.</span></span>
- <span data-ttu-id="cde39-123">**Leveransavgiftskod** – Återförsäljare kan debitera en extra avgift för leverans av varor till en kund.</span><span class="sxs-lookup"><span data-stu-id="cde39-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="cde39-124">Leveransavgiften återspeglas under en avgiftskod på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="cde39-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="cde39-125">Använd denna parameter för att mappa leveransavgiftskoden till fraktkostnader på kundordern.</span><span class="sxs-lookup"><span data-stu-id="cde39-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
- <span data-ttu-id="cde39-126">**Återbetala leveransavgifter** – Ange om leveransavgifter som associeras med en kundorder kan återbetalas.</span><span class="sxs-lookup"><span data-stu-id="cde39-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
- <span data-ttu-id="cde39-127">**Maxbelopp utan godkännande** – Om leveransavgifter kan återbetalas, ange då maxbelopp för återbetalning av leveransavgifter för returorder.</span><span class="sxs-lookup"><span data-stu-id="cde39-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="cde39-128">Om detta värde överskrids krävs åsidosättning utförd av chef för att fortsätta med återbetalningen.</span><span class="sxs-lookup"><span data-stu-id="cde39-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="cde39-129">Återbetalning av leveransavgifter kan överstiga det ursprungligen betalade beloppet i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="cde39-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>

    - <span data-ttu-id="cde39-130">Avgifter tillämpas på nivån för försäljningsorderrubrik, och när en viss kvantitet av en produktlinje returneras, kan maxbeloppet för återbetalning av leveranskostnader som tillåts för produkterna och kvantiteten inte fastställas på ett sätt som passar alla butikskunder.</span><span class="sxs-lookup"><span data-stu-id="cde39-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all retail customers.</span></span>
    - <span data-ttu-id="cde39-131">Leveransavgifterna infaller efter alla leveransförekomster.</span><span class="sxs-lookup"><span data-stu-id="cde39-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="cde39-132">Om en kund returnerar varor flera gånger och återförsäljarens policy anger att återförsäljaren ska stå för kostnaderna för returleveranser, kommer kostnaderna för returleveranser att överstiga de faktiska leveranskostnaderna.</span><span class="sxs-lookup"><span data-stu-id="cde39-132">If a customer returns products multiple times, and the retailer's policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="cde39-133">Transaktionsflöde för kundorder</span><span class="sxs-lookup"><span data-stu-id="cde39-133">Transaction flow for customer orders</span></span>

### <a name="create-a-customer-order-in-retail-modern-pos"></a><span data-ttu-id="cde39-134">Skapa kundorder i Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="cde39-134">Create a customer order in Retail Modern POS</span></span>

1. <span data-ttu-id="cde39-135">Lägg till en kund i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="cde39-135">Add a customer to the transaction.</span></span>
2. <span data-ttu-id="cde39-136">Lägg till produkter i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="cde39-136">Add products to the cart.</span></span>
3. <span data-ttu-id="cde39-137">Klicka på **Skapa kundorder** och välj sedan ordertypen.</span><span class="sxs-lookup"><span data-stu-id="cde39-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="cde39-138">Ordertypen kan antingen vara **Kundorder** eller **Offert**.</span><span class="sxs-lookup"><span data-stu-id="cde39-138">The order type can be either **Customer order** or **Quote**.</span></span>
4. <span data-ttu-id="cde39-139">Klicka på **Leverera val** eller **Leverera alla** om du vill sända produkterna till en adress på kundkontot, ange begärt speditionsdatum och fraktkostnaderna.</span><span class="sxs-lookup"><span data-stu-id="cde39-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5. <span data-ttu-id="cde39-140">Klicka på **Hämta valda** eller **Hämta alla** för att välja produkter som hämtas från den aktuella butiken eller en annan butik vid ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="cde39-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6. <span data-ttu-id="cde39-141">Inkassera av insättningsbeloppet, om en deposition krävs.</span><span class="sxs-lookup"><span data-stu-id="cde39-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="cde39-142">Redigera en befintlig kundorder</span><span class="sxs-lookup"><span data-stu-id="cde39-142">Edit an existing customer order</span></span>

1. <span data-ttu-id="cde39-143">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-143">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="cde39-144">Hitta och markera den order som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="cde39-144">Find and select the order to edit.</span></span> <span data-ttu-id="cde39-145">Klicka på **Redigera** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="cde39-146">Hämta en order</span><span class="sxs-lookup"><span data-stu-id="cde39-146">Pick up an order</span></span>

1. <span data-ttu-id="cde39-147">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-147">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="cde39-148">Välj den order som ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="cde39-148">Select the order to pick up.</span></span> <span data-ttu-id="cde39-149">Klicka på **Hämtning och paketering** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-149">At the bottom of the page, click **Picking and packing**.</span></span>
3. <span data-ttu-id="cde39-150">Klicka på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="cde39-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="cde39-151">Avbryt en order</span><span class="sxs-lookup"><span data-stu-id="cde39-151">Cancel an order</span></span>

1. <span data-ttu-id="cde39-152">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-152">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="cde39-153">Markera ordern som ska avbrytas.</span><span class="sxs-lookup"><span data-stu-id="cde39-153">Select the order to cancel.</span></span> <span data-ttu-id="cde39-154">Klicka på **Avbryt** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-154">At the bottom of the page, click **Cancel**.</span></span>

### <a name="create-a-return-order"></a><span data-ttu-id="cde39-155">Skapa en returorder</span><span class="sxs-lookup"><span data-stu-id="cde39-155">Create a return order</span></span>

1. <span data-ttu-id="cde39-156">Klicka på **Hitta en order** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-156">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="cde39-157">Markera den order som du vill returnera, välj fakturan för ordern och välj sedan produktlinje för de varor som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="cde39-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3. <span data-ttu-id="cde39-158">Klicka på **Returnera order** längst ner på sidan.</span><span class="sxs-lookup"><span data-stu-id="cde39-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="cde39-159">Asynkront transaktionsflöde för kundorder</span><span class="sxs-lookup"><span data-stu-id="cde39-159">Asynchronous transaction flow for customer orders</span></span>

<span data-ttu-id="cde39-160">Kundorder kan skapas från kassaklienten i antingen synkront eller asynkront läge.</span><span class="sxs-lookup"><span data-stu-id="cde39-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="cde39-161">Aktivera skapande av kundorder i asynkront läge</span><span class="sxs-lookup"><span data-stu-id="cde39-161">Enable customer orders to be created in asynchronous mode</span></span>

1. <span data-ttu-id="cde39-162">Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofil** &gt; **Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="cde39-162">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2. <span data-ttu-id="cde39-163">I snabbfliken **Allmänt** anger du alternativet för **Skapa kundorder i asynkront läge** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cde39-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="cde39-164">När alternativet **Skapa kundorder i asynkront läge** är inställt på **Ja**, skapas kundorder alltid i asynkront läge, även om tjänsten för Retail Transaction Service (RTS) är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="cde39-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="cde39-165">Om du anger detta alternativ som **Nej**, skapas kundorder alltid i synkront läge med hjälp av RTS.</span><span class="sxs-lookup"><span data-stu-id="cde39-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="cde39-166">När kundorder skapas i asynkront läget hämtas och infogas de i Retail genom hämtningsjobb.</span><span class="sxs-lookup"><span data-stu-id="cde39-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Retail by Pull (P) jobs.</span></span> <span data-ttu-id="cde39-167">Motsvarande försäljningsorder skapas i Retail när **Synkronisera order** körs antingen manuellt eller via en batchprocess.</span><span class="sxs-lookup"><span data-stu-id="cde39-167">The corresponding sales orders are created in Retail when **Synchronize orders** is run either manually or through a batch process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cde39-168">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cde39-168">Additional resources</span></span>

[<span data-ttu-id="cde39-169">Kombinerade kundorder</span><span class="sxs-lookup"><span data-stu-id="cde39-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)
