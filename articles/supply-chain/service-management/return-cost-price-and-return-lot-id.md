---
title: Retursjälvkostnad och returparti-ID
description: Vill du eventuellt att kostnaden för de returnerade produkterna lika med kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden. Det gör du med hjälp av **returparti-ID**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b420c0716823f587ea3f349a5d654ace23d84f41
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219279"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="d1eb8-104">Retursjälvkostnad och returparti-ID</span><span class="sxs-lookup"><span data-stu-id="d1eb8-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="d1eb8-105">Kostnaden för produkter som returneras till lagret beräknas med hjälp av den aktuella kostnaden för produkter.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="d1eb8-106">Vill du eventuellt att kostnaden för de returnerade produkterna lika med kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="d1eb8-107">Det gör du med hjälp av fältet **returparti-ID** på snabbfliken **radinformation** i formuläret **försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="d1eb8-108">Tänk på följande scenario:</span><span class="sxs-lookup"><span data-stu-id="d1eb8-108">For example, consider the following scenario.</span></span> <span data-ttu-id="d1eb8-109">Du fakturerar en kund.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-109">You invoice a customer.</span></span> <span data-ttu-id="d1eb8-110">Kunden returnerar sedan de levererade produkterna till dig.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="d1eb8-111">Du returnerar produkterna till lagret.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-111">You return the products to stock.</span></span> <span data-ttu-id="d1eb8-112">I det här fallet när du krediterar kunden för returnerade produkter beräknas kostnaden för dessa produkter genom att använda den aktuella kostnaden för produkter.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="d1eb8-113">Men om du använder fältet **returparti-ID** beräknas kostnaden för de returnerade produkterna med hjälp av kostnaden på fakturan för den ursprungliga försäljningen till kunden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="d1eb8-114">Om du vill använda en annan kostnad än den aktuella kostnaden för returer för en kund använder du någon av följande metoder.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="d1eb8-115">Metod 1: Ange retursjälvkostnaden manuellt</span><span class="sxs-lookup"><span data-stu-id="d1eb8-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="d1eb8-116">Som standard när du lägger till objekt mot en returorder returneras artiklarna till lagret till den aktuella självkostnaden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="d1eb8-117">Följ dessa steg om du vill ange en annan retursjälvkostnaden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="d1eb8-118">Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="d1eb8-119">I **åtgärdsrutan** i gruppen **Ny** klickar du på **Returorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="d1eb8-120">I formuläret **Skapa returorder** välj ett kundkonto och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="d1eb8-121">I formuläret **returorder - RMA-nummer: %1, %2** välj ett objekt och ange en negativ kvantitet i fältet **kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="d1eb8-122">Klicka på **Radinformation**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="d1eb8-123">På fliken **Allmänt** ange ett värde i fältet **Retursjälvkostnad**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="d1eb8-124">Det här värdet används när varorna har returnerats till lagret.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="d1eb8-125">Om du inte anger ett värde, används det aktuella självkostnaden när varorna har returnerats till lagret.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="d1eb8-126">Metod 2: Generera automatiskt självkostnaden baserat på kundfakturarad</span><span class="sxs-lookup"><span data-stu-id="d1eb8-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="d1eb8-127">Detta är det bästa sättet att skapa returrader.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="d1eb8-128">Kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden, skapa en returorder och anger en försäljningsrad ska returneras.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="d1eb8-129">Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="d1eb8-130">I **åtgärdsrutan** i gruppen **Ny** klickar du på **Returorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="d1eb8-131">I formuläret **Skapa returorder** välj ett kundkonto och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="d1eb8-132">I formuläret **returorder - RMA-nummer: %1, %2** i **åtgärdsfönstret**, klickar du på **söka efter försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="d1eb8-133">I formuläret **söka efter försäljningsorder**, välj fakturaraden som returneras och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="d1eb8-134">På snabbfliken **Radinformation** klickar du på fliken **allmänt** och fältet **returparti-ID** visar värdet från den ursprungliga försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="d1eb8-135">Dessutom kan fältet **Retursjälvkostnad** visa kostnadsvärdet från den ursprungliga försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="d1eb8-136">Exempel på kostnadsberäkning</span><span class="sxs-lookup"><span data-stu-id="d1eb8-136">Cost calculation example</span></span>

<span data-ttu-id="d1eb8-137">När du använder fältet **returparti-ID** på en returorderrad för att ange retursjälvkostnaden, används kostnaden på returorderraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="d1eb8-138">Om du använder funktionen för lagerstängning eller omberäkning justeras kostnaden på den ursprungliga försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="d1eb8-139">Kostnaden på returorderraden justeras automatiskt så att den avspeglar samma kostnad per styck.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="d1eb8-140">Skapa och släppa en produkt som heter Test.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="d1eb8-141">I formuläret **Information om frisläppt produkt** anger du följande information:</span><span class="sxs-lookup"><span data-stu-id="d1eb8-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="d1eb8-142">På fliken **hantera kostnader** i fältet **artikelgrupp** väljer du gruppen **delar**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="d1eb8-143">På snabbfliken **Allmänt** i fältet **Artikelmodellgrupp**, välj **DEF**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="d1eb8-144">På snabbfliken **Köp** i fältet **Pris** ange 10,00 som artikelns självkostnad.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="d1eb8-145">I **Åtgärdsfönstret**, klicka på **Dimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="d1eb8-146">I fältet **lagringsdimensionsgrupp** väljer du **Endast plats och lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="d1eb8-147">I fältet **spårningsdimensionsgrupp** väljer du **Inga aktiva spårningsdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="d1eb8-148">Skapa en inköpsorder för 10 delar av testartikel på 6,00 per styck och bokföra en faktura för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="d1eb8-149">Skapa en andra inköpsorder för 10 delar av testartikel på 8,00 per styck och bokföra en faktura för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="d1eb8-150">Bokföra en faktura för en försäljningsorder att sälja fem delar av testartikeln.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="d1eb8-151">I det här fallet kostade försäljningsorderraden 35,00 (5 enheter \*7,00 genomsnittlig kostnad per styck).</span><span class="sxs-lookup"><span data-stu-id="d1eb8-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="d1eb8-152">Skapa en ny returorder för kunden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-152">Create a return order for the customer.</span></span> <span data-ttu-id="d1eb8-153">I formuläret **söka efter försäljningsorder**, välj fakturaraden och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="d1eb8-154">I formuläret **returorder - RMA-nummer: %1, %2** kontrollerar du att en returorder skapas för att returnera testartikeln.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="d1eb8-155">Returorderns kvantiteten anges till -5,00.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="d1eb8-156">Fältet **returparti-ID** visar ett parti-ID.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="d1eb8-157">Detta parti-ID hämtas från den ursprungliga försäljningsordern för artikeln som har sålts till kunden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="d1eb8-158">Dessutom kan fältet **Retursjälvkostnad** visa självkostnaden från den ursprungliga försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="d1eb8-159">Registrera inleverans av returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="d1eb8-160">Bokför en följesedel för de returnerade artiklarna.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="d1eb8-161">Bokför en faktura för returordern.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-161">Post an invoice for the return order.</span></span> <span data-ttu-id="d1eb8-162">På listsidan **alla försäljningsorder**, välj en försäljningsorder för vilken ordertypen är **returnerad order**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="d1eb8-163">Öppna formuläret **Lagertransaktioner**</span><span class="sxs-lookup"><span data-stu-id="d1eb8-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="d1eb8-164">Kontrollera returen kostnadsberäknats till 7,00 per enhet med hjälp av värdet i fältet **Retursjälvkostnad** för totalt 35,00 i fältet **kostnadsbelopp**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="d1eb8-165">Du kan öppna formuläret **lagertransaktioner** från formuläret **returorder - RMA-nummer: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="d1eb8-166">Klicka på rutnätet **Rader**, klicka på **Lager** \> **Transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="d1eb8-167">I Hantering av lager och lagerplatser använd formuläret **stängning och justering** när du vill köra proceduren **3. Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="d1eb8-168">Åtgärden justerar kostnaden på de ursprungliga försäljningsrader som har kostnadsberäknats till -35,00 (5 enheter \*7,00) till -30.00 (5 enheter \*6,00).</span><span class="sxs-lookup"><span data-stu-id="d1eb8-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="d1eb8-169">Detta beror på att lagermodellgruppen använder Först in, först ut (FIFO) och 6,00 per enhet är FIFO-kostnaden från den inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="d1eb8-170">Dessutom justerar åtgärden kostnaden på returförsäljningsraden för att matcha kostnaden per styck på den ursprungliga försäljningsraden.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="d1eb8-171">Därför justeras kostnaderna för returraden från 35,00 till 30,00.</span><span class="sxs-lookup"><span data-stu-id="d1eb8-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]