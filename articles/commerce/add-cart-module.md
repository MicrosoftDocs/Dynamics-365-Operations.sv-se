---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: abb9909c03577763ff7e6242c9395a58159df6ca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985989"
---
# <a name="cart-module"></a><span data-ttu-id="e932d-103">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e932d-104">Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e932d-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e932d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e932d-105">Overview</span></span>

<span data-ttu-id="e932d-106">En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan.</span><span class="sxs-lookup"><span data-stu-id="e932d-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="e932d-107">Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="e932d-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="e932d-108">Kundvagnsmodulen stöder inloggad kassa och gästkassa.</span><span class="sxs-lookup"><span data-stu-id="e932d-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="e932d-109">Det stöder också en **Tillbaka till shopping**-länk.</span><span class="sxs-lookup"><span data-stu-id="e932d-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="e932d-110">Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.</span><span class="sxs-lookup"><span data-stu-id="e932d-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="e932d-111">I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e932d-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="e932d-112">Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e932d-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exempel på en kundvagnsmodul på webbplatsen Fabrikam](./media/cart2.PNG)

<span data-ttu-id="e932d-114">Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e932d-114">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="e932d-115">I det här exemplet är det en hanteringsavgift för en radartikel.</span><span class="sxs-lookup"><span data-stu-id="e932d-115">In this example, there is a handling fee for a line item.</span></span>

![Exempel på en kundvagnsmodul med en hanteringsavgift för en radartikel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="e932d-117">Egenskaper och platser för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-117">Cart module properties and slots</span></span>

| <span data-ttu-id="e932d-118">Egenskap</span><span class="sxs-lookup"><span data-stu-id="e932d-118">Property</span></span> | <span data-ttu-id="e932d-119">Värden</span><span class="sxs-lookup"><span data-stu-id="e932d-119">Values</span></span> | <span data-ttu-id="e932d-120">beskrivning</span><span class="sxs-lookup"><span data-stu-id="e932d-120">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="e932d-121">Rubrik</span><span class="sxs-lookup"><span data-stu-id="e932d-121">Heading</span></span> | <span data-ttu-id="e932d-122">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="e932d-122">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="e932d-123">En rubrik för kundvagnen, till exempel "Shoppingväska" eller "Artiklarna i vagnen."</span><span class="sxs-lookup"><span data-stu-id="e932d-123">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="e932d-124">Visa fel av typen Slut i lager</span><span class="sxs-lookup"><span data-stu-id="e932d-124">Show out of stock errors</span></span> | <span data-ttu-id="e932d-125">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e932d-125">**True** or **False**</span></span> | <span data-ttu-id="e932d-126">Om den här egenskapen har angetts till **True** visar sidan för kundvagn fel som är relaterade till lagret.</span><span class="sxs-lookup"><span data-stu-id="e932d-126">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="e932d-127">Vi rekommenderar att du ställer in den här egenskapen på **True** om lagerkontroller används på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e932d-127">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="e932d-128">Visa leveransavgifter för radartiklar</span><span class="sxs-lookup"><span data-stu-id="e932d-128">Show shipping charges for line items</span></span> | <span data-ttu-id="e932d-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e932d-129">**True** or **False**</span></span> | <span data-ttu-id="e932d-130">Om den här egenskapen har värdet **True** visar kundvagnsartiklar leveransavgifter om den här informationen är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e932d-130">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="e932d-131">Den här funktionen stöds inte i det Fabrikam-temat, eftersom användarna väljer enbart leverans i kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="e932d-131">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="e932d-132">Den här funktionen kan emellertid aktiveras i andra arbetsflöden om den är tillämplig.</span><span class="sxs-lookup"><span data-stu-id="e932d-132">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="e932d-133">Visa tillgängliga erbjudanden</span><span class="sxs-lookup"><span data-stu-id="e932d-133">Show available promotions</span></span>| <span data-ttu-id="e932d-134">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e932d-134">**True** or **False**</span></span> | <span data-ttu-id="e932d-135">Om egenskapen har satts till **Sant** visar kundvagnen tillgängliga erbjudanden baserat på artiklarna i vagnen.</span><span class="sxs-lookup"><span data-stu-id="e932d-135">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="e932d-136">Denna funktion finns i Dynamics 365 Commerce version 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="e932d-136">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="e932d-137">Moduler kan användas i en kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-137">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="e932d-138">**Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen.</span><span class="sxs-lookup"><span data-stu-id="e932d-138">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="e932d-139">Meddelandena styrs av innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="e932d-139">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="e932d-140">Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."</span><span class="sxs-lookup"><span data-stu-id="e932d-140">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="e932d-141">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="e932d-141">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="e932d-142">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="e932d-142">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="e932d-143">Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="e932d-143">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="e932d-144">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="e932d-144">Module properties</span></span>

<span data-ttu-id="e932d-145">Följande kundvagnsmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="e932d-145">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="e932d-146">**Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="e932d-146">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="e932d-147">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="e932d-147">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="e932d-148">**Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e932d-148">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="e932d-149">**Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**.</span><span class="sxs-lookup"><span data-stu-id="e932d-149">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="e932d-150">Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e932d-150">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e932d-151">I Dynamics 365 Commerce 10.0.14-versionen och senare sammanställs artiklar i kundvagnen baserat på inställningarna som definieras i online-butikens funktionsprofil i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="e932d-151">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="e932d-152">Mer information om hur du skapar en funktionsprofil i online och ställer in de egenskaper som krävs för aggregering finns i [skapa en online funktionsprofil](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="e932d-152">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="e932d-153">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="e932d-153">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="e932d-154">Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="e932d-154">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="e932d-155">Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="e932d-155">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="e932d-156">Lägg till en kundvagnsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="e932d-156">Add a cart module to a page</span></span>

<span data-ttu-id="e932d-157">Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e932d-157">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e932d-158">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="e932d-158">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="e932d-159">I dialogrutan **Nytt fragment**, välj modulen **Kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="e932d-159">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="e932d-160">Under **Fragmentets namn**, anger du ett namn på **kundvagnsfragmentet** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e932d-160">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="e932d-161">Markera platsen **kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="e932d-161">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="e932d-162">I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.</span><span class="sxs-lookup"><span data-stu-id="e932d-162">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="e932d-163">I facket **kundvagn** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="e932d-163">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e932d-164">I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e932d-164">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="e932d-165">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="e932d-165">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="e932d-166">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="e932d-166">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="e932d-167">I dialogrutan **Ny mall** under **Mallnamn** anger du ett namn för mallen.</span><span class="sxs-lookup"><span data-stu-id="e932d-167">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="e932d-168">I dispositionsträdet väljer du platsen **Brödtext** markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="e932d-168">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="e932d-169">I dialogrutan **Välj fragment** väljer du det **kundvagnsfragment** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e932d-169">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e932d-170">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="e932d-170">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="e932d-171">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="e932d-171">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="e932d-172">I dialogrutan **Välj en mall** väljer du den mall som du skapade, anger sidnamn och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e932d-172">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="e932d-173">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="e932d-173">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="e932d-174">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="e932d-174">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e932d-175">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e932d-175">Additional resources</span></span>

[<span data-ttu-id="e932d-176">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-176">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="e932d-177">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="e932d-177">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e932d-178">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-178">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="e932d-179">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="e932d-179">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="e932d-180">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="e932d-180">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="e932d-181">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="e932d-181">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="e932d-182">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-182">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e932d-183">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="e932d-183">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="e932d-184">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="e932d-184">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="e932d-185">Skapa en onlinefunktionsprofil</span><span class="sxs-lookup"><span data-stu-id="e932d-185">Create an online functionality profile</span></span>](online-functionality-profile.md)
