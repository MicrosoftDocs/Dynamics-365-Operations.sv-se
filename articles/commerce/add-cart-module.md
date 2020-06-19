---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ba46fd90507a9cf8da92598c8449a2e553da352
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411283"
---
# <a name="cart-module"></a><span data-ttu-id="a2e7e-103">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-103">Cart module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a2e7e-104">Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a2e7e-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a2e7e-105">Overview</span></span>

<span data-ttu-id="a2e7e-106">En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="a2e7e-107">Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="a2e7e-108">Kundvagnsmodulen stöder inloggade utcheckning och gästkassa.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="a2e7e-109">Det stöder också en **Tillbaka till shopping**-länk.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="a2e7e-110">Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="a2e7e-111">I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="a2e7e-112">Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exempel på en kundvagnsmodul](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="a2e7e-114">Egenskaper och platser för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-114">Cart module properties and slots</span></span>

<span data-ttu-id="a2e7e-115">Kundvagnsmodulen har en egenskap för **Rubrik** som kan ställas in på värden som **Shoppingväska** och **Artiklarna i vagnen**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="a2e7e-116">Moduler kan användas i en kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="a2e7e-117">**Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="a2e7e-118">Meddelandena styrs av innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="a2e7e-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="a2e7e-119">Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."</span><span class="sxs-lookup"><span data-stu-id="a2e7e-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="a2e7e-120">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="a2e7e-121">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="a2e7e-122">Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="a2e7e-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="a2e7e-123">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="a2e7e-123">Module properties</span></span>

<span data-ttu-id="a2e7e-124">Följande kundvagnsmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="a2e7e-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="a2e7e-125">**Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="a2e7e-126">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="a2e7e-127">**Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a2e7e-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="a2e7e-128">**Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="a2e7e-129">Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="a2e7e-130">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="a2e7e-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="a2e7e-131">Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="a2e7e-132">Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="a2e7e-133">Lägg till en kundvagnsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="a2e7e-133">Add a cart module to a page</span></span>

<span data-ttu-id="a2e7e-134">Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="a2e7e-135">Gå till **Sidfragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="a2e7e-136">I dialogrutan **Ny sidfragment**, välj modulen **kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="a2e7e-137">Under **sidfragmentets namn**, anger du ett namn på **kundvagnsfragmentet** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="a2e7e-138">Markera platsen **kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="a2e7e-139">I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="a2e7e-140">I facket **kundvagn** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="a2e7e-141">I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="a2e7e-142">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="a2e7e-143">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="a2e7e-144">I dialogrutan **Ny mall** under **Mallnamn** anger du ett namn för mallen.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="a2e7e-145">I dispositionsträdet väljer du platsen **Brödtext** markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="a2e7e-146">I dialogrutan **Välj sidfragment** väljer du det **kundvagnsfragment** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="a2e7e-147">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="a2e7e-148">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="a2e7e-149">I dialogrutan **Välj en mall** väljer du den mall som du skapade, anger sidnamn och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="a2e7e-150">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="a2e7e-151">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="a2e7e-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2e7e-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a2e7e-152">Additional resources</span></span>

[<span data-ttu-id="a2e7e-153">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="a2e7e-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a2e7e-154">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="a2e7e-155">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="a2e7e-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="a2e7e-156">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="a2e7e-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="a2e7e-157">Vagnikonmodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="a2e7e-158">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="a2e7e-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a2e7e-159">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="a2e7e-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a2e7e-160">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="a2e7e-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="a2e7e-161">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="a2e7e-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="a2e7e-162">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="a2e7e-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
