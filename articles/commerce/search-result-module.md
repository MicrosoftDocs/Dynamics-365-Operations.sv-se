---
title: Sökresultatmodul
description: Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.openlocfilehash: 645022000d8746db3793a8a8611ab8f17c7bcc6e
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117143"
---
# <a name="search-results-module"></a><span data-ttu-id="c7a22-103">Sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="c7a22-103">Search results module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c7a22-104">Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c7a22-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c7a22-105">I modulen Sökresultat returneras produktsökningsresultat och en lista över tillämpliga förfiningar för produkterna.</span><span class="sxs-lookup"><span data-stu-id="c7a22-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="c7a22-106">Sökresultatmoduler på Dynamics 365 Commerce-webbplatser kan användas för att återge sidor för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="c7a22-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="c7a22-107">Sökresultat som initieras av en användarsökning</span><span class="sxs-lookup"><span data-stu-id="c7a22-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="c7a22-108">Sökresultat som visar en specifik uppsättning produkter, t.ex. "Shop similar looks" ("sök efter liknande")</span><span class="sxs-lookup"><span data-stu-id="c7a22-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="c7a22-109">Listor med produkter som tillhör en kategori</span><span class="sxs-lookup"><span data-stu-id="c7a22-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="c7a22-110">Mer information om kategori- och sökresultatsidor finns i [Standardkategorins landningssida och översikt över sökresultatsidor](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7a22-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="c7a22-111">Följande illustration visar ett exempel på en sökresultatsida för en kategori på Fabrikams webbplats.</span><span class="sxs-lookup"><span data-stu-id="c7a22-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Exempel på en sökresultatsida på webbplatsen Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="c7a22-113">Egenskaper för sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="c7a22-113">Search results module properties</span></span>

<span data-ttu-id="c7a22-114">I följande tabell visas egenskaperna för sökresultatmodulerna tillsammans med deras värden och beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="c7a22-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="c7a22-115">Egenskap</span><span class="sxs-lookup"><span data-stu-id="c7a22-115">Property</span></span> | <span data-ttu-id="c7a22-116">Värden</span><span class="sxs-lookup"><span data-stu-id="c7a22-116">Values</span></span> | <span data-ttu-id="c7a22-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c7a22-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="c7a22-118">Artiklar per sida</span><span class="sxs-lookup"><span data-stu-id="c7a22-118">Items per page</span></span> | <span data-ttu-id="c7a22-119">Heltal</span><span class="sxs-lookup"><span data-stu-id="c7a22-119">Integer</span></span> | <span data-ttu-id="c7a22-120">Antalet objekt som ska visas på respektive sida.</span><span class="sxs-lookup"><span data-stu-id="c7a22-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="c7a22-121">Tillåt bakåt i PDP</span><span class="sxs-lookup"><span data-stu-id="c7a22-121">Allow back on PDP</span></span> | <span data-ttu-id="c7a22-122">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="c7a22-122">**True** or **False**</span></span> | <span data-ttu-id="c7a22-123">Om denna egenskap är inställd på **Sant** kommer navigeringen av säkerhetsdetaljer på produktinformationssidan (PDP) länken "Tillbaka till resultat" när en användare väljer en produkt på sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="c7a22-124">Visa förfiningar</span><span class="sxs-lookup"><span data-stu-id="c7a22-124">Expand Refiners</span></span> | <span data-ttu-id="c7a22-125">**Alla**, **1**, **2**, **3** eller **4**</span><span class="sxs-lookup"><span data-stu-id="c7a22-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="c7a22-126">Antalet toppförfinare som ska utvidgas när en sida läses in.</span><span class="sxs-lookup"><span data-stu-id="c7a22-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="c7a22-127">Om egenskapen exempelvis är inställd på **3** expanderas de första tre förfinarna på sidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="c7a22-128">Dölj visning av kategorihierarki</span><span class="sxs-lookup"><span data-stu-id="c7a22-128">Hide category hierarchy display</span></span> | <span data-ttu-id="c7a22-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="c7a22-129">**True** or **False**</span></span> | <span data-ttu-id="c7a22-130">Om egenskapen har angetts som **Sant** döljs den kategorihierarki som visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="c7a22-131">Denna egenskap ska vara **True** om du använder [modulen för navigeringssökväg](add-breadcrumb.md) för att visa kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="c7a22-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="c7a22-132">Inkludera produktattribut i sökresultat</span><span class="sxs-lookup"><span data-stu-id="c7a22-132">Include product attributes in search results</span></span> | <span data-ttu-id="c7a22-133">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="c7a22-133">**True** or **False**</span></span> | <span data-ttu-id="c7a22-134">Om egenskapen anges som **Sant** returneras attributen för produkterna i sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="c7a22-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="c7a22-135">Även om dessa attribut kan visas på en Commerce-webbplats krävs ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="c7a22-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="c7a22-136">Visa anknytningspriser</span><span class="sxs-lookup"><span data-stu-id="c7a22-136">Show affiliation prices</span></span> | <span data-ttu-id="c7a22-137">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="c7a22-137">**True** or **False**</span></span> | <span data-ttu-id="c7a22-138">Om denna egenskap är inställd på **Sant** visas anknytningspriser för produkter i sökresultaten när en inloggad användare bläddrar på sidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |
| <span data-ttu-id="c7a22-139">Uppdatera förfiningspanel</span><span class="sxs-lookup"><span data-stu-id="c7a22-139">Update refiner panel</span></span> | <span data-ttu-id="c7a22-140">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="c7a22-140">**True** or **False**</span></span> | <span data-ttu-id="c7a22-141">Om egenskapen har satts till **Sant** uppdateras förfiningspanelen när förfining väljs.</span><span class="sxs-lookup"><span data-stu-id="c7a22-141">If this property is set to **True**, the refiner panel will be updated when refiners are selected.</span></span> <span data-ttu-id="c7a22-142">I det här läget kommer vissa flervalsförfinare att bete sig som envalsförfinare när förfiningspanelen uppdateras.</span><span class="sxs-lookup"><span data-stu-id="c7a22-142">In this mode, some multiple-selection refiners will behave like single-selection refiners when the refiner panel is updated.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="c7a22-143">I  Commerce version 10.0.16 och senare kan konfigurationen **Visa anknytningspriser** användas för att visa anknytningspriser på sidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-143">In the Commerce version 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>
>
> <span data-ttu-id="c7a22-144">I Commerce version 10.0.20 frisläppning och senare kan konfigurationen **Uppdatera förfiningspanel** användas för att uppdatera förfiningspanelen under val av förfining.</span><span class="sxs-lookup"><span data-stu-id="c7a22-144">In the Commerce version 10.0.20 release and later, the **Update refiner panel** configuration can be used to update the refiner panel during refiner selection.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="c7a22-145">Moduler som stöds</span><span class="sxs-lookup"><span data-stu-id="c7a22-145">Supported modules</span></span>

<span data-ttu-id="c7a22-146">Modulen för sökresultat stöder [snabbvisningsmodulen](quick-view-module.md), där användarna kan visa produktinformation och lägga till artiklar i kundvagnen från sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="c7a22-146">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="c7a22-147">Lägg till en sökresultatmodul på en kategorisida</span><span class="sxs-lookup"><span data-stu-id="c7a22-147">Add a search results module to a category page</span></span>

<span data-ttu-id="c7a22-148">För att lägga till en sökresultatmodul på en kategorisida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c7a22-148">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="c7a22-149">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="c7a22-149">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c7a22-150">I dialogrutan **Ny mall** anger du namnet **Sökresultat** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-150">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="c7a22-151">I fältet **Brödtext** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-151">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c7a22-152">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-152">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c7a22-153">I fältet **Huvud** i modulen **Standardsida** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-153">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c7a22-154">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-154">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c7a22-155">I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-155">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c7a22-156">I dialogrutan **Lägg till modul**, välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-156">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c7a22-157">I egenskapsfönstret för **Navigering** anger du värdet **1** för **Min. träffar**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-157">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="c7a22-158">I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-158">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c7a22-159">I dialogrutan **Lägg till modul** väljer du modulen **Sökresultat** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-159">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c7a22-160">I egenskapsfönstret **Sökresultat** anger du värdet **1** för **Min. träffar** och anger sedan övriga erforderliga egenskaper för sökresultatmodulen.</span><span class="sxs-lookup"><span data-stu-id="c7a22-160">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="c7a22-161">Genom att ange dessa egenskaper i mallen säkerställer du att alla anpassningar till en viss kategorisida automatiskt inkluderar dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="c7a22-161">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="c7a22-162">Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.</span><span class="sxs-lookup"><span data-stu-id="c7a22-162">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="c7a22-163">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="c7a22-163">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="c7a22-164">I dialogrutan **Välj en mall** väljer du den **Sökresultat**-mall som du skapade, anger sedan **Kategorisida** för **Sidnamn** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a22-164">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="c7a22-165">Eftersom alla värden har angetts i mallen är sidan klar att publiceras.</span><span class="sxs-lookup"><span data-stu-id="c7a22-165">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="c7a22-166">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="c7a22-166">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7a22-167">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c7a22-167">Additional resources</span></span>

[<span data-ttu-id="c7a22-168">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="c7a22-168">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="c7a22-169">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="c7a22-169">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c7a22-170">Snabbvisningsmodul</span><span class="sxs-lookup"><span data-stu-id="c7a22-170">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
