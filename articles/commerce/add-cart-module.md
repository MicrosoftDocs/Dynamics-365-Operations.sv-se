---
title: Kundvagnsmodul
description: Det här avsnittet handlar om vagnmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5b0ce69f57e6ba691803752280466b41ced7c521
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206497"
---
# <a name="cart-module"></a><span data-ttu-id="5bbb5-103">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5bbb5-104">Det här avsnittet handlar om vagnmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5bbb5-105">En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-105">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="5bbb5-106">Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-106">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="5bbb5-107">Kundvagnsmodulen stöder inloggad kassa och gästkassa.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-107">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="5bbb5-108">Det stöder också en **Tillbaka till shopping**-länk.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-108">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="5bbb5-109">Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-109">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="5bbb5-110">I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-110">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="5bbb5-111">Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-111">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exempel på en kundvagnsmodul på webbplatsen Fabrikam](./media/cart2.PNG)

<span data-ttu-id="5bbb5-113">Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-113">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="5bbb5-114">I det här exemplet är det en hanteringsavgift för en radartikel.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-114">In this example, there is a handling fee for a line item.</span></span>

![Exempel på en kundvagnsmodul med en hanteringsavgift för en radartikel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="5bbb5-116">Egenskaper och platser för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-116">Cart module properties and slots</span></span>

| <span data-ttu-id="5bbb5-117">Egenskap</span><span class="sxs-lookup"><span data-stu-id="5bbb5-117">Property</span></span> | <span data-ttu-id="5bbb5-118">Värden</span><span class="sxs-lookup"><span data-stu-id="5bbb5-118">Values</span></span> | <span data-ttu-id="5bbb5-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5bbb5-119">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="5bbb5-120">Rubrik</span><span class="sxs-lookup"><span data-stu-id="5bbb5-120">Heading</span></span> | <span data-ttu-id="5bbb5-121">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="5bbb5-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="5bbb5-122">En rubrik för kundvagnen, till exempel "Shoppingväska" eller "Artiklarna i vagnen."</span><span class="sxs-lookup"><span data-stu-id="5bbb5-122">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="5bbb5-123">Visa fel av typen Slut i lager</span><span class="sxs-lookup"><span data-stu-id="5bbb5-123">Show out of stock errors</span></span> | <span data-ttu-id="5bbb5-124">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="5bbb5-124">**True** or **False**</span></span> | <span data-ttu-id="5bbb5-125">Om den här egenskapen har angetts till **True** visar sidan för kundvagn fel som är relaterade till lagret.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-125">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="5bbb5-126">Vi rekommenderar att du ställer in den här egenskapen på **True** om lagerkontroller används på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-126">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="5bbb5-127">Visa leveransavgifter för radartiklar</span><span class="sxs-lookup"><span data-stu-id="5bbb5-127">Show shipping charges for line items</span></span> | <span data-ttu-id="5bbb5-128">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="5bbb5-128">**True** or **False**</span></span> | <span data-ttu-id="5bbb5-129">Om den här egenskapen har värdet **True** visar kundvagnsartiklar leveransavgifter om den här informationen är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-129">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="5bbb5-130">Den här funktionen stöds inte i det Fabrikam-temat, eftersom användarna väljer enbart leverans i kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-130">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="5bbb5-131">Den här funktionen kan emellertid aktiveras i andra arbetsflöden om den är tillämplig.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-131">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="5bbb5-132">Visa tillgängliga erbjudanden</span><span class="sxs-lookup"><span data-stu-id="5bbb5-132">Show available promotions</span></span>| <span data-ttu-id="5bbb5-133">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="5bbb5-133">**True** or **False**</span></span> | <span data-ttu-id="5bbb5-134">Om egenskapen har satts till **Sant** visar kundvagnen tillgängliga erbjudanden baserat på artiklarna i vagnen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-134">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="5bbb5-135">Denna funktion finns i Dynamics 365 Commerce version 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-135">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="5bbb5-136">Moduler kan användas i en kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-136">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="5bbb5-137">**Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-137">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="5bbb5-138">Meddelandena styrs av innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="5bbb5-138">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="5bbb5-139">Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."</span><span class="sxs-lookup"><span data-stu-id="5bbb5-139">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="5bbb5-140">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-140">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="5bbb5-141">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-141">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="5bbb5-142">Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb5-142">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="5bbb5-143">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="5bbb5-143">Module properties</span></span>

<span data-ttu-id="5bbb5-144">Följande kundvagnsmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="5bbb5-144">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="5bbb5-145">**Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-145">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="5bbb5-146">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-146">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="5bbb5-147">**Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb5-147">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="5bbb5-148">**Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-148">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="5bbb5-149">Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-149">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bbb5-150">I Dynamics 365 Commerce 10.0.14-versionen och senare sammanställs artiklar i kundvagnen baserat på inställningarna som definieras i online-butikens funktionsprofil i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-150">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="5bbb5-151">Mer information om hur du skapar en funktionsprofil i online och ställer in de egenskaper som krävs för aggregering finns i [skapa en online funktionsprofil](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb5-151">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="5bbb5-152">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="5bbb5-152">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="5bbb5-153">Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-153">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="5bbb5-154">Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-154">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="5bbb5-155">Lägg till en kundvagnsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="5bbb5-155">Add a cart module to a page</span></span>

<span data-ttu-id="5bbb5-156">Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-156">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="5bbb5-157">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-157">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="5bbb5-158">I dialogrutan **Nytt fragment**, välj modulen **Kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-158">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="5bbb5-159">Under **Fragmentets namn**, anger du ett namn på **kundvagnsfragmentet** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-159">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="5bbb5-160">Markera platsen **kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-160">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="5bbb5-161">I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-161">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="5bbb5-162">I facket **kundvagn** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-162">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5bbb5-163">I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-163">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5bbb5-164">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-164">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="5bbb5-165">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-165">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="5bbb5-166">I dialogrutan **Ny mall** under **Mallnamn** anger du ett namn för mallen.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-166">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="5bbb5-167">I dispositionsträdet väljer du platsen **Brödtext** markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-167">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="5bbb5-168">I dialogrutan **Välj fragment** väljer du det **kundvagnsfragment** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-168">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="5bbb5-169">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-169">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="5bbb5-170">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-170">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="5bbb5-171">I dialogrutan **Välj en mall** väljer du den mall som du skapade, anger sidnamn och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-171">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="5bbb5-172">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-172">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="5bbb5-173">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="5bbb5-173">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5bbb5-174">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5bbb5-174">Additional resources</span></span>

[<span data-ttu-id="5bbb5-175">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-175">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="5bbb5-176">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-176">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5bbb5-177">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-177">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5bbb5-178">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="5bbb5-178">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5bbb5-179">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="5bbb5-179">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="5bbb5-180">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="5bbb5-180">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="5bbb5-181">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-181">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5bbb5-182">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="5bbb5-182">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="5bbb5-183">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="5bbb5-183">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="5bbb5-184">Skapa en onlinefunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="5bbb5-184">Create an online functionality profile</span></span>](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]