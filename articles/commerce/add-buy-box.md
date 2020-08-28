---
title: Modul för inköpsruta
description: Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3fe5c1eb5808ef778aeda29442fa884556671296
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686680"
---
# <a name="buy-box-module"></a><span data-ttu-id="3a1e3-103">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="3a1e3-103">Buy box module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3a1e3-104">Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-104">This topic covers buy box modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3a1e3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="3a1e3-105">Overview</span></span>

<span data-ttu-id="3a1e3-106">Termen *inköpsruta* syftar vanligtvis på en sida med produktinformation som är "ovanför vikningen" och som är värd för all den viktigaste information som krävs för att göra produktinköp.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-106">The term *buy box* typically refers to the area of a product details page that is "above the fold," and that hosts all the most important information that is required to make a product purchase.</span></span> <span data-ttu-id="3a1e3-107">(Ett område som är "ovanför vikningen" visas när sidan läses in för första gången, så att användarna inte behöver rulla nedåt för att kunna se dem.)</span><span class="sxs-lookup"><span data-stu-id="3a1e3-107">(An area that is "above the fold" is visible when the page is first loaded, so that users don't have to scroll down to see it.)</span></span>

<span data-ttu-id="3a1e3-108">En inköpsruta är en speciell behållare som används för att vara värd för alla moduler som visas i området för inköpsruta på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-108">A buy box module is special container that is used to host all the modules that are shown in the buy box area of a product details page.</span></span>

<span data-ttu-id="3a1e3-109">URL för produktinformationssidan innehåller produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-109">The URL of a product details page includes the product ID.</span></span> <span data-ttu-id="3a1e3-110">All information som krävs för att återge en modul för inköpsruta kommer från detta produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-110">All the information that is required to render a buy box module is derived from this product ID.</span></span> <span data-ttu-id="3a1e3-111">Om inget produkt-ID har angetts, återges inte affärsmodulen korrekt på en sida.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-111">If a product ID isn't provided, the buy box module won't be rendered correctly on a page.</span></span> <span data-ttu-id="3a1e3-112">Därför kan en modul för inköpsruta bara användas på sidor som har produktkontext.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-112">Therefore, a buy box module can be used only on pages that have product context.</span></span> <span data-ttu-id="3a1e3-113">Om du vill använda den på en sida som saknar produktkontext (t.ex. en start sida eller en marknadsföringssida), måste du utföra ytterligare anpassningar.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-113">To use it on a page that doesn't have product context (for example, a home page or a marketing page), you must do additional customizations.</span></span>

<span data-ttu-id="3a1e3-114">Följande bild visar ett exempel på en modul för inköpsruta på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-114">The following image shows an example of a buy box module on a product details page.</span></span>

![Exempel på en modul för inköpsruta](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a><span data-ttu-id="3a1e3-116">Egenskaper och platser för modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="3a1e3-116">Buy box module properties and slots</span></span> 

<span data-ttu-id="3a1e3-117">På en produktinformationssida är en inköpsruta uppdelad i två områden: ett medieområde till vänster och ett innehållsområde till höger.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-117">On a product details page, a buy box is divided into two regions: a media region on the left and a content region on the right.</span></span> <span data-ttu-id="3a1e3-118">Som standard är förhållandet mellan bredden för kolumnen medie region och bredden för kolumnen innehålls region 2:1.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-118">By default, the ratio of the width of the media region column to the width of the content region column is 2:1.</span></span> <span data-ttu-id="3a1e3-119">På mobila enheter staplas de två regionerna så att en region visas under den andra regionen.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-119">On mobile devices, the two regions are stacked so that one region appears below the other region.</span></span> <span data-ttu-id="3a1e3-120">Teman kan användas för att anpassa kolumnbredder och stackrangordning.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-120">Themes can be used to customize the column widths and stacking rank.</span></span>

<span data-ttu-id="3a1e3-121">En modul för inköpsruta återger titel, beskrivning, pris och klassificering för en produkt.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-121">A buy box module renders the title, description, price, and ratings of a product.</span></span> <span data-ttu-id="3a1e3-122">Kunden kan också välja produktvarianter med olika produktattribut, t.ex. storlek, stil och färg.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-122">It also lets customers select product variants that have different product attributes, such as size, style, and color.</span></span> <span data-ttu-id="3a1e3-123">När en produktvarianten väljs uppdateras andra egenskaper i inköpsrutan (t.ex. produktbeskrivning och bilder) för att avspegla informationen för varianten.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-123">When a product variant is selected, other properties in the buy box (for example, the product description and images) are updated to reflect the variant information.</span></span> 

<span data-ttu-id="3a1e3-124">En mängd väljare tillhandahålls, så att kunder kan ange hur många artiklar som ska köpas.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-124">A quantity selector is provided, so that customers can specify the quantity of items to purchase.</span></span> <span data-ttu-id="3a1e3-125">Den högsta kvantiteten som kan köpas kan definieras i webbplatsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-125">The maximum quantity that can be purchased can be defined in the site settings.</span></span>

<span data-ttu-id="3a1e3-126">Från inköpsrutan kan kunder också utföra åtgärder som att lägga till en produkt i kundvagnen, lägga till en produkt i deras önskelista och välja en plockplats.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-126">From the buy box, customers can also perform actions such as adding a product to the cart, adding a product to their wishlist, and selecting a pickup location.</span></span> <span data-ttu-id="3a1e3-127">Dessa åtgärder kan utföras på en produkt eller produktvariant.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-127">These actions can be performed on a product or a product variant.</span></span> <span data-ttu-id="3a1e3-128">Om du vill lägga till en produkt i en önskelista måste kunden vara inloggad.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-128">To add a product to a wishlist, the customer must be signed in.</span></span>

<span data-ttu-id="3a1e3-129">Teman kan användas för att ta bort eller ändra ordningen på produktegenskaper och åtgärdskontroller i inköpsrutan.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-129">Themes can be used to remove or change the order of buy box product properties and action controls.</span></span> 

## <a name="module-properties"></a><span data-ttu-id="3a1e3-130">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="3a1e3-130">Module properties</span></span>

- <span data-ttu-id="3a1e3-131">**Rubriketikett** – den här egenskapen definierar rubriketiketten för produktrubriken.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-131">**Heading tag** – This property defines the heading tag for the product title.</span></span> <span data-ttu-id="3a1e3-132">Om inköpsrutan finns högst upp på sidan ska den här egenskapen ställas in på **h1** för att uppfylla tillgänglighetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-132">If the buy box is at the top of the page, this property should be set to **h1** to meet accessibility standards.</span></span> 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a><span data-ttu-id="3a1e3-133">Moduler kan användas i modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="3a1e3-133">Modules that can be used in a buy box module</span></span>

- <span data-ttu-id="3a1e3-134">**Mediegalleri** – den här modulen används för att visa bilder av en produkt på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-134">**Media gallery** – This module is used to showcase images of a product on a product details page.</span></span> <span data-ttu-id="3a1e3-135">Mer information om den här modulen finns i [Modul för mediegalleri](media-gallery-module.md).</span><span class="sxs-lookup"><span data-stu-id="3a1e3-135">For more information about this module, see [Media gallery module](media-gallery-module.md).</span></span>
- <span data-ttu-id="3a1e3-136">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-136">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="3a1e3-137">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-137">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="3a1e3-138">Mer information om den här modulen finns i [Modul för butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="3a1e3-138">For more information about this module, see [Store selector module](store-selector.md).</span></span>

## <a name="buy-box-module-settings"></a><span data-ttu-id="3a1e3-139">Inställningar för modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="3a1e3-139">Buy box module settings</span></span>

<span data-ttu-id="3a1e3-140">Följande köpboxmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="3a1e3-140">The following buy box module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="3a1e3-141">**Kvantitetsbegränsning för kundvagn** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-141">**Cart line quantity limit** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="3a1e3-142">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-142">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="3a1e3-143">**Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3a1e3-143">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="3a1e3-144">**Lägg till i kundvagn** - den här egenskapen används för att ange funktionen när en artikel har lagts till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-144">**Add to cart** - This property is used to specify the behavior after an item is added to the cart.</span></span> <span data-ttu-id="3a1e3-145">De möjliga värdena är **Navigera till kundvagn**, **Navigera inte i kundvagn** och **Visa meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-145">The possible values are **Navigate to cart**, **Do not navigate to cart**, and **Show notifications**.</span></span> <span data-ttu-id="3a1e3-146">När värdet är inställt på **Navigera till kundvagn** skickas användarna till kundvagnssidan när de har lagt till en artikel.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-146">When the value is set to **Navigate to cart**, users are sent to the cart page after they add an item.</span></span> <span data-ttu-id="3a1e3-147">När värdet är inställt på **Navigera inte till kundvagn** skickas användarna inte till kundvagnssidan när de har lagt till en artikel.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-147">When the value is set to **Do not navigate to cart**, users aren't sent to the cart page after they add an item.</span></span> <span data-ttu-id="3a1e3-148">När värdet är inställt på **Visa meddelanden** visas användarna ett bekräftelsemeddelande och du kan fortsätta att bläddra på sidan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-148">When the value is set to **Show notifications**, users are shown a confirmation notification and can continue to browse on the product details page.</span></span> 

    <span data-ttu-id="3a1e3-149">I följande bild visas ett exempel på ett bekräftelsemeddelande om tillägg till kundvagnen på Fabrikam webbplats.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-149">The following image shows an example of an "added to cart" confirmation notification on the Fabrikam site.</span></span>

    ![Exempel på en meddelandemodul](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="3a1e3-151">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="3a1e3-151">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="3a1e3-152">Modul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-152">The buy box module retrieves product information by using Commerce Scale Unit application programming interfaces (APIs).</span></span> <span data-ttu-id="3a1e3-153">Produkt-ID:t från sidan produktinformation används för att hämta all information.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-153">The product ID from the product details page is used to retrieve all information.</span></span>

## <a name="add-a-buy-box-module-to-a-page"></a><span data-ttu-id="3a1e3-154">Lägg till en modul för inköpsruta på en ny sida</span><span class="sxs-lookup"><span data-stu-id="3a1e3-154">Add a buy box module to a page</span></span>

<span data-ttu-id="3a1e3-155">Om du vill lägga till en modul för inköpsruta på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-155">To add a buy box module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3a1e3-156">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-156">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="3a1e3-157">I dialogrutan **Nytt sidfragment**, välj modulen **inköpsruta**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-157">In the **New page fragment** dialog box, select the **Buybox** module.</span></span>
1. <span data-ttu-id="3a1e3-158">Under **sidfragmentets namn**, anger du ett namn på **inköpsrutafragmentet** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-158">Under **Page fragment name**, enter the name **Buy box fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-159">I platsen för modul för inköpsruta väljer du **Mediagalleriet**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-159">In the **Media Gallery** slot of the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3a1e3-160">I dialogrutan **Lägg till modul** välj modulen **Mediagalleriet** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-160">In the **Add Module** dialog box, select the **Media gallery** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-161">I platsen för modul för inköpsruta väljer du **butiksväljare**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-161">In the **Store selector** slot of the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3a1e3-162">I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-162">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-163">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-163">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3a1e3-164">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-164">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3a1e3-165">I dialogrutan **Ny mal** under **Mallnamn**, ange **PDP-mall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-165">In the **New Template** dialog box, under **Template name**, enter **PDP template**, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-166">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-166">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3a1e3-167">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-167">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-168">I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-168">In the **Main** slot of the default page, select the ellipsis (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="3a1e3-169">I dialogrutan **Välj sidfragment** väljer du det **inköpsrutafragment** som du skapade tidigare och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-169">In the **Select page fragment** dialog box, select the **Buy box fragment** fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-170">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-170">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3a1e3-171">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-171">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="3a1e3-172">I dialogrutan **Välj en mall** väljer du en **PDP-mall**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-172">In the **Choose a template** dialog box, select the **PDP template** template.</span></span> <span data-ttu-id="3a1e3-173">Under **sidnamn**, ange **PDP-sida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-173">Under **Page name**, enter **PDP page**, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-174">I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-174">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="3a1e3-175">I dialogrutan **Välj sidfragment** väljer du det **inköpsrutafragment** som du skapade tidigare och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-175">In the **Select page fragment** dialog box, select the **Buy box fragment** fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="3a1e3-176">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-176">Save and preview the page.</span></span> <span data-ttu-id="3a1e3-177">Lägg till frågesträngparametern **?productid=&lt;product id&gt;** till URL för förhandsgranskningssidan.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-177">Add the **?productid=&lt;product id&gt;** query string parameter to the URL of the preview page.</span></span> <span data-ttu-id="3a1e3-178">På så sätt används produktkontexten för att läsa in och återge förhandsgranskningssidan.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-178">In that way, the product context is used to load and render the preview page.</span></span>
1. <span data-ttu-id="3a1e3-179">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-179">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="3a1e3-180">En inköpsruta bör visas på sidan för produktinformation.</span><span class="sxs-lookup"><span data-stu-id="3a1e3-180">A buy box should appear on the product details page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3a1e3-181">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3a1e3-181">Additional resources</span></span>

[<span data-ttu-id="3a1e3-182">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="3a1e3-182">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3a1e3-183">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="3a1e3-183">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="3a1e3-184">Modul för mediegalleri</span><span class="sxs-lookup"><span data-stu-id="3a1e3-184">Media gallery module</span></span>](media-gallery-module.md)

[<span data-ttu-id="3a1e3-185">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="3a1e3-185">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3a1e3-186">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="3a1e3-186">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3a1e3-187">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="3a1e3-187">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="3a1e3-188">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="3a1e3-188">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3a1e3-189">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="3a1e3-189">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="3a1e3-190">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="3a1e3-190">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="3a1e3-191">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="3a1e3-191">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="3a1e3-192">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="3a1e3-192">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
