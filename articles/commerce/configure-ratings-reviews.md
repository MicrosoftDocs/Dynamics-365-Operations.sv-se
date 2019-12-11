---
title: Konfigurera omdömen och recensioner
description: I det här avsnittet beskrivs hur du konfigurerar din e-handelsplats så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770491"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="c3cd8-103">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="c3cd8-103">Configure ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c3cd8-104">I det här avsnittet beskrivs hur du konfigurerar din e-handelsplats så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c3cd8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="c3cd8-105">Overview</span></span>

<span data-ttu-id="c3cd8-106">Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, genom att visa vad andra kunder tycker om dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="c3cd8-107">För näthandelsplatser är omdömen och recensioner också en mekanism för att samla in kundernas feedback om produkter.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="c3cd8-108">Omdömen visas på produktlistsidor, kategorilistsidor, sökresultatsidor och andra webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="c3cd8-109">Omdömeshistogram och produktrecensioner visas på produktinformationssidor (PDP).</span><span class="sxs-lookup"><span data-stu-id="c3cd8-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="c3cd8-110">Knappen **Skriv ett omdöme** låter kunder skicka in omdömen och recensioner om en produkt.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="c3cd8-111">Moduler för omdömen och recensioner på PDP</span><span class="sxs-lookup"><span data-stu-id="c3cd8-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="c3cd8-112">Tre moduler visar sammanfattningen av omdömen och recensioner i PDP:</span><span class="sxs-lookup"><span data-stu-id="c3cd8-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="c3cd8-113">Modulen skriv recension</span><span class="sxs-lookup"><span data-stu-id="c3cd8-113">Write review module</span></span>
- <span data-ttu-id="c3cd8-114">Modulen produktrecensionslista</span><span class="sxs-lookup"><span data-stu-id="c3cd8-114">Product reviews list module</span></span>
- <span data-ttu-id="c3cd8-115">Modul för omdömeshistogram</span><span class="sxs-lookup"><span data-stu-id="c3cd8-115">Ratings histogram module</span></span>
 
<span data-ttu-id="c3cd8-116">I bilden nedan visas hur modulerna omdömen och recensioner ser ut på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduler för omdömen och recensioner på en PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="c3cd8-118">Information om hur du optimerar mallar och layouter i PDP så att du kan dela med dig av konfigurationerna för omdömen och recensioner av moduler mellan flera PDP på din näthandelsplats finns på [Översikt över mallar och layouter](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c3cd8-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="c3cd8-119">Följande illustration visar hur dialogrutan **Lägg till modul** presenterar moduler för omdömen och recensioner i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Dialogrutan Lägg till modul](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="c3cd8-121">Modulen skriv recension</span><span class="sxs-lookup"><span data-stu-id="c3cd8-121">Write review module</span></span>

<span data-ttu-id="c3cd8-122">Modulen skriv recension inkluderar knappen **Skriv en recension**, där användarna kan logga in, tilldela ett omdöme och skriva en recension av en produkt.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="c3cd8-123">Med hjälp av modulen kan du också redigera ett omdöme eller granska de som tidigare har skickat in dem.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="c3cd8-124">Den här modulen visas normalt ovanför modulerna omdömeshistogram och produktrecensioner i en PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="c3cd8-125">Bilden nedan visar dialog rutan **Skriv en recension** som visas när en kund väljer **skriva en recension**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="c3cd8-126">Kunden kan använda den här dialogrutan för att skicka ett omdöme och en recension.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Dialogrutan Skriv en recension](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="c3cd8-128">I följande tabell visas den egenskap för modulen skriv recension som måste konfigureras i utvecklingsverktyget.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="c3cd8-129">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="c3cd8-129">Property name</span></span> | <span data-ttu-id="c3cd8-130">Värde</span><span class="sxs-lookup"><span data-stu-id="c3cd8-130">Value</span></span>        | <span data-ttu-id="c3cd8-131">Egenskapsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="c3cd8-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="c3cd8-132">Namn</span><span class="sxs-lookup"><span data-stu-id="c3cd8-132">Name</span></span>          | <span data-ttu-id="c3cd8-133">Skriv recension</span><span class="sxs-lookup"><span data-stu-id="c3cd8-133">Write review</span></span> | <span data-ttu-id="c3cd8-134">Namnet på modulen för skriv en recension.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="c3cd8-135">Modul för omdömeshistogram</span><span class="sxs-lookup"><span data-stu-id="c3cd8-135">Ratings histogram module</span></span>

<span data-ttu-id="c3cd8-136">Modulen omdömeshistogram visar ett histogram med omdömet.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="c3cd8-137">Den här modulen visas normalt mellan modulen skriv recension och produktrecensionslistan på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="c3cd8-138">Modulen omdömeshistogram kräver ingen konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="c3cd8-139">Du behöver bara lägga till modulen i PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="c3cd8-140">Följande illustrationer visar hur en PDP-mall ser ut i Dynamics 365 Commerce när moduler för omdömen och recensioner konfigureras för visning på PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![PDP-mall när omdömen och recensioner konfigureras för visning på PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="c3cd8-142">Modulen produktrecensionslista</span><span class="sxs-lookup"><span data-stu-id="c3cd8-142">Product reviews list module</span></span>

<span data-ttu-id="c3cd8-143">I modulen produktrecensionslista visas en lista med produktrecensioner tillsammans med alternativen sortera, filtrera och sidbrytning.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="c3cd8-144">Den här modulen visas normalt efter modulen för omdömeshistogram på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="c3cd8-145">I följande tabell visas de egenskaper för modulen produktrecensionslista som måste konfigureras i utvecklingsverktyget.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="c3cd8-146">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="c3cd8-146">Property name</span></span>              | <span data-ttu-id="c3cd8-147">Värde</span><span class="sxs-lookup"><span data-stu-id="c3cd8-147">Value</span></span> | <span data-ttu-id="c3cd8-148">Egenskapsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="c3cd8-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="c3cd8-149">Recensioner som visas på varje sida</span><span class="sxs-lookup"><span data-stu-id="c3cd8-149">Reviews shown on each page</span></span> | <span data-ttu-id="c3cd8-150">10</span><span class="sxs-lookup"><span data-stu-id="c3cd8-150">10</span></span>    | <span data-ttu-id="c3cd8-151">Antalet recensioner som ska visas i taget på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="c3cd8-152">Knapparna **Nästa** och **föregående** inkluderas så att användarna kan förflytta sig genom sidorna i recensioner.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="c3cd8-153">Omdömeshistogram – sammanfattningsvy</span><span class="sxs-lookup"><span data-stu-id="c3cd8-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="c3cd8-154">Modulen produktrecensionslista innehåller en plats där du kan lägga till en modul för ett omdöme i histogram.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="c3cd8-155">Följande illustration visar hur du kan lägga till en modul för omdömeshistogram i modulen produktrecensionslista i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Lägga till modulen omdömeshistogram i modulen produktrecensionslista](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="c3cd8-157">Konfigurera en webbplats att visa omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="c3cd8-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="c3cd8-158">Konfigurationsvärden för omdömen och recensioner, till exempel innehavar-ID, granska textlängd och granska rubriklängd, konfigureras på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="c3cd8-159">Konfigurera en webbplats för visning av värderingar och recensioner enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="c3cd8-160">Gå till **Start \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="c3cd8-161">Välj namnet på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="c3cd8-162">Gå till **Webbplatshantering \> Utbyggbarhet**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="c3cd8-163">I fältet **granska textens maxlängd** anger du det maximala antalet tecken som ska granska text kan ha (t.ex. **1000**).</span><span class="sxs-lookup"><span data-stu-id="c3cd8-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="c3cd8-164">I fältet **granska rubrikens maxlängd** anger du det maximala antalet tecken som ska granska rubriker kan ha (t.ex. **55**).</span><span class="sxs-lookup"><span data-stu-id="c3cd8-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="c3cd8-165">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="c3cd8-166">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurera en webbplats att visa omdömen och recensioner](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="c3cd8-168">Länka en produktvärdering till avsnittet recensioner i ett PDP</span><span class="sxs-lookup"><span data-stu-id="c3cd8-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="c3cd8-169">En produktvärdering visas under produktrubriken högst upp i PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="c3cd8-170">Produktvärderingen kan konfigureras så att den länkas till avsnittet **recensioner** i samma PDP.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="c3cd8-171">Om du vill länka en produktvärdering avsnittet **recensioner** i PDP följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="c3cd8-172">Öppna PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="c3cd8-173">Gå till **Inställningar för behållarmodulen inköpsruta**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="c3cd8-174">Under **inköpsruta**, välj **produktvärderingar** och sedan väljer du kryssrutan **Länka klicka till modulen för fullständig recension**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="c3cd8-175">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Länka en produktvärdering till avsnittet recensioner i ett PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="c3cd8-177">Konfigurera länken till sidan sekretess och policy</span><span class="sxs-lookup"><span data-stu-id="c3cd8-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="c3cd8-178">Konfigurera länken till sidan sekretess och policy genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="c3cd8-179">Gå till **Start \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="c3cd8-180">Välj namnet på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="c3cd8-181">Gå till **Webbplatshantering \> Utbyggbarhet**</span><span class="sxs-lookup"><span data-stu-id="c3cd8-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="c3cd8-182">På sidan **Flöden**, under **RNR sekretess och policy**, välj **Lägg till en länk**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="c3cd8-183">Om en länk redan har angivits och du vill ersätta den markerar du länken.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="c3cd8-184">I dialogrutan **Lägg till en länk** väljer du länken för sidan om sekretess och policy och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="c3cd8-185">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="c3cd8-186">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3cd8-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurera länken till sidan sekretess och policy](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="c3cd8-188">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c3cd8-188">Additional resources</span></span>

[<span data-ttu-id="c3cd8-189">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="c3cd8-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="c3cd8-190">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="c3cd8-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="c3cd8-191">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="c3cd8-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="c3cd8-192">Synkronisera produktklassificeringar i Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="c3cd8-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
