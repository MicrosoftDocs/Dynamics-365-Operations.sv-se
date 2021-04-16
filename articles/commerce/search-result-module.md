---
title: Sökresultatmodul
description: Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3409e9e99329def55b173eb78cf03db4a6764c92
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794125"
---
# <a name="search-results-module"></a><span data-ttu-id="db80a-103">Sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="db80a-103">Search results module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db80a-104">Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db80a-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="db80a-105">I modulen Sökresultat returneras produktsökningsresultat och en lista över tillämpliga förfiningar för produkterna.</span><span class="sxs-lookup"><span data-stu-id="db80a-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="db80a-106">Sökresultatmoduler på Dynamics 365 Commerce-webbplatser kan användas för att återge sidor för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="db80a-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="db80a-107">Sökresultat som initieras av en användarsökning</span><span class="sxs-lookup"><span data-stu-id="db80a-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="db80a-108">Sökresultat som visar en specifik uppsättning produkter, t.ex. "Shop similar looks" ("sök efter liknande")</span><span class="sxs-lookup"><span data-stu-id="db80a-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="db80a-109">Listor med produkter som tillhör en kategori</span><span class="sxs-lookup"><span data-stu-id="db80a-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="db80a-110">Mer information om kategori- och sökresultatsidor finns i [Standardkategorins landningssida och översikt över sökresultatsidor](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="db80a-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="db80a-111">Följande illustration visar ett exempel på en sökresultatsida för en kategori på Fabrikams webbplats.</span><span class="sxs-lookup"><span data-stu-id="db80a-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Exempel på en sökresultatsida på webbplatsen Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="db80a-113">Egenskaper för sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="db80a-113">Search results module properties</span></span>

<span data-ttu-id="db80a-114">I följande tabell visas egenskaperna för sökresultatmodulerna tillsammans med deras värden och beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="db80a-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="db80a-115">Egenskap</span><span class="sxs-lookup"><span data-stu-id="db80a-115">Property</span></span> | <span data-ttu-id="db80a-116">Värden</span><span class="sxs-lookup"><span data-stu-id="db80a-116">Values</span></span> | <span data-ttu-id="db80a-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="db80a-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="db80a-118">Artiklar per sida</span><span class="sxs-lookup"><span data-stu-id="db80a-118">Items per page</span></span> | <span data-ttu-id="db80a-119">Heltal</span><span class="sxs-lookup"><span data-stu-id="db80a-119">Integer</span></span> | <span data-ttu-id="db80a-120">Antalet objekt som ska visas på respektive sida.</span><span class="sxs-lookup"><span data-stu-id="db80a-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="db80a-121">Tillåt bakåt i PDP</span><span class="sxs-lookup"><span data-stu-id="db80a-121">Allow back on PDP</span></span> | <span data-ttu-id="db80a-122">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="db80a-122">**True** or **False**</span></span> | <span data-ttu-id="db80a-123">Om denna egenskap är inställd på **Sant** kommer navigeringen av säkerhetsdetaljer på produktinformationssidan (PDP) länken "Tillbaka till resultat" när en användare väljer en produkt på sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="db80a-124">Visa förfiningar</span><span class="sxs-lookup"><span data-stu-id="db80a-124">Expand Refiners</span></span> | <span data-ttu-id="db80a-125">**Alla**, **1**, **2**, **3** eller **4**</span><span class="sxs-lookup"><span data-stu-id="db80a-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="db80a-126">Antalet toppförfinare som ska utvidgas när en sida läses in.</span><span class="sxs-lookup"><span data-stu-id="db80a-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="db80a-127">Om egenskapen exempelvis är inställd på **3** expanderas de första tre förfinarna på sidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="db80a-128">Dölj visning av kategorihierarki</span><span class="sxs-lookup"><span data-stu-id="db80a-128">Hide category hierarchy display</span></span> | <span data-ttu-id="db80a-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="db80a-129">**True** or **False**</span></span> | <span data-ttu-id="db80a-130">Om egenskapen har angetts som **Sant** döljs den kategorihierarki som visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="db80a-131">Denna egenskap ska vara **True** om du använder [modulen för navigeringssökväg](add-breadcrumb.md) för att visa kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="db80a-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="db80a-132">Inkludera produktattribut i sökresultat</span><span class="sxs-lookup"><span data-stu-id="db80a-132">Include product attributes in search results</span></span> | <span data-ttu-id="db80a-133">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="db80a-133">**True** or **False**</span></span> | <span data-ttu-id="db80a-134">Om egenskapen anges som **Sant** returneras attributen för produkterna i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="db80a-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="db80a-135">Även om dessa attribut kan visas på en Commerce-webbplats krävs ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="db80a-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="db80a-136">Visa anknytningspriser</span><span class="sxs-lookup"><span data-stu-id="db80a-136">Show affiliation prices</span></span> | <span data-ttu-id="db80a-137">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="db80a-137">**True** or **False**</span></span> | <span data-ttu-id="db80a-138">Om denna egenskap är inställd på **Sant** visas anknytningspriser för produkter i sökresultaten när en inloggad användare bläddrar på sidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="db80a-139">I Dynamics 365 Commerce version 10.0.16 och senare kan konfigurationen **Visa anknytningspriser** användas för att visa anknytningspriser på sidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="db80a-140">Moduler som stöds</span><span class="sxs-lookup"><span data-stu-id="db80a-140">Supported modules</span></span>

<span data-ttu-id="db80a-141">Modulen för sökresultat stöder [snabbvisningsmodulen](quick-view-module.md), där användarna kan visa produktinformation och lägga till artiklar i kundvagnen från sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="db80a-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="db80a-142">Lägg till en sökresultatmodul på en kategorisida</span><span class="sxs-lookup"><span data-stu-id="db80a-142">Add a search results module to a category page</span></span>

<span data-ttu-id="db80a-143">För att lägga till en sökresultatmodul på en kategorisida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="db80a-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="db80a-144">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="db80a-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="db80a-145">I dialogrutan **Ny mall** anger du namnet **Sökresultat** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="db80a-146">I fältet **Brödtext** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="db80a-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db80a-147">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db80a-148">I fältet **Huvud** i modulen **Standardsida** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="db80a-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db80a-149">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db80a-150">I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="db80a-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db80a-151">I dialogrutan **Lägg till modul**, välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db80a-152">I egenskapsfönstret för **Navigering** anger du värdet **1** för **Min. träffar**.</span><span class="sxs-lookup"><span data-stu-id="db80a-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="db80a-153">I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="db80a-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db80a-154">I dialogrutan **Lägg till modul** väljer du modulen **Sökresultat** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db80a-155">I egenskapsfönstret **Sökresultat** anger du värdet **1** för **Min. träffar** och anger sedan övriga erforderliga egenskaper för sökresultatmodulen.</span><span class="sxs-lookup"><span data-stu-id="db80a-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="db80a-156">Genom att ange dessa egenskaper i mallen säkerställer du att alla anpassningar till en viss kategorisida automatiskt inkluderar dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="db80a-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="db80a-157">Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.</span><span class="sxs-lookup"><span data-stu-id="db80a-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="db80a-158">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="db80a-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="db80a-159">I dialogrutan **Välj en mall** väljer du den **Sökresultat**-mall som du skapade, anger sedan **Kategorisida** för **Sidnamn** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="db80a-160">Eftersom alla värden har angetts i mallen är sidan klar att publiceras.</span><span class="sxs-lookup"><span data-stu-id="db80a-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="db80a-161">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="db80a-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db80a-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="db80a-162">Additional resources</span></span>

[<span data-ttu-id="db80a-163">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="db80a-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="db80a-164">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="db80a-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="db80a-165">Snabbvisningsmodul</span><span class="sxs-lookup"><span data-stu-id="db80a-165">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
