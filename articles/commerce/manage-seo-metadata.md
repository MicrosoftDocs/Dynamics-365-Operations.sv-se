---
title: Hantera SEO-metadata
description: I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794221"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="bbba2-103">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="bbba2-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bbba2-104">I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bbba2-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bbba2-105">SEO-metadata för en plats kan hanteras med hjälp av webbplatskartor och sidmetadata.</span><span class="sxs-lookup"><span data-stu-id="bbba2-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="bbba2-106">Webbplatskartor</span><span class="sxs-lookup"><span data-stu-id="bbba2-106">Site maps</span></span>

<span data-ttu-id="bbba2-107">En webbplatskarta är en maskinläsbar lista, i XML-format, för sidorna på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbba2-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="bbba2-108">Den är avsedd att förbrukas av sökmotorer så att de kan ge bättre sökresultat från din webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbba2-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="bbba2-109">Webbplatskartor kan manuellt förtäras av sökmotorer eller publiceras i en robots.txt-fil.</span><span class="sxs-lookup"><span data-stu-id="bbba2-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="bbba2-110">Dynamics 365 Commerce stöder automatisk generering av webbplatsmappningar.</span><span class="sxs-lookup"><span data-stu-id="bbba2-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="bbba2-111">Webbplatsmappningar uppdateras automatiskt när sidor publiceras och avpubliceras.</span><span class="sxs-lookup"><span data-stu-id="bbba2-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="bbba2-112">Aktivera generering av webbplatskarta</span><span class="sxs-lookup"><span data-stu-id="bbba2-112">Turn on site map generation</span></span>

1. <span data-ttu-id="bbba2-113">Logga in till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="bbba2-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="bbba2-114">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="bbba2-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="bbba2-115">I navigeringsfönstret till vänster, välj **Platshantering**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="bbba2-116">Kontrollera att alternativet **Webbplatskartor aktiverade** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="bbba2-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="bbba2-117">Metadata för sida</span><span class="sxs-lookup"><span data-stu-id="bbba2-117">Page metadata</span></span>

<span data-ttu-id="bbba2-118">Dynamics 365 Commerce gör att du kan hantera SEO-metadata för enskilda sidor.</span><span class="sxs-lookup"><span data-stu-id="bbba2-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="bbba2-119">Du kan visa och ändra denna information i avsnittet **SEO-egenskaper** i en sidbehållare.</span><span class="sxs-lookup"><span data-stu-id="bbba2-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="bbba2-120">Följande egenskaper för SEO-metadata stöds:</span><span class="sxs-lookup"><span data-stu-id="bbba2-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="bbba2-121">Rubrik</span><span class="sxs-lookup"><span data-stu-id="bbba2-121">Title</span></span>
- <span data-ttu-id="bbba2-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bbba2-122">Description</span></span>
- <span data-ttu-id="bbba2-123">SEO-nyckelord</span><span class="sxs-lookup"><span data-stu-id="bbba2-123">SEO keywords</span></span>
- <span data-ttu-id="bbba2-124">Aria-etiketter</span><span class="sxs-lookup"><span data-stu-id="bbba2-124">Aria labels</span></span>
- <span data-ttu-id="bbba2-125">noindex</span><span class="sxs-lookup"><span data-stu-id="bbba2-125">noindex</span></span>
- <span data-ttu-id="bbba2-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="bbba2-126">nofollow</span></span>
- <span data-ttu-id="bbba2-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="bbba2-127">noarchive</span></span>
- <span data-ttu-id="bbba2-128">nocache</span><span class="sxs-lookup"><span data-stu-id="bbba2-128">nocache</span></span>
- <span data-ttu-id="bbba2-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="bbba2-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="bbba2-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="bbba2-130">nosnippet</span></span>
- <span data-ttu-id="bbba2-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="bbba2-131">noImageIndex</span></span>
- <span data-ttu-id="bbba2-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="bbba2-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="bbba2-133">Ändra metadata för sidan</span><span class="sxs-lookup"><span data-stu-id="bbba2-133">Modify page metadata</span></span>

<span data-ttu-id="bbba2-134">Om du vill ändra metadata, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="bbba2-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="bbba2-135">Under **Webbplatser**, välj **Fabrikam** (eller namet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="bbba2-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="bbba2-136">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="bbba2-137">Välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="bbba2-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="bbba2-138">Klicka på **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="bbba2-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="bbba2-139">I fönstret Egenskaper till höger, visa **Standardmetataggar**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="bbba2-140">Om du vill lägga till en ny metatagg väljer du **Lägg till** och anger sedan taggen i fältet.</span><span class="sxs-lookup"><span data-stu-id="bbba2-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="bbba2-141">Om du vill ta bort en befintlig metatagg markerar du papperskorgen till höger om den.</span><span class="sxs-lookup"><span data-stu-id="bbba2-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="bbba2-142">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="bbba2-143">I fältet **kommentarer** anger du **Uppdaterade metataggar** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="bbba2-144">Välj **Förhandsgranska** om du vill förhandsgranska din sida.</span><span class="sxs-lookup"><span data-stu-id="bbba2-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="bbba2-145">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="bbba2-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="bbba2-146">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="bbba2-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbba2-147">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bbba2-147">Additional resources</span></span>

[<span data-ttu-id="bbba2-148">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="bbba2-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="bbba2-149">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="bbba2-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="bbba2-150">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="bbba2-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="bbba2-151">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="bbba2-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="bbba2-152">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="bbba2-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="bbba2-153">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="bbba2-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="bbba2-154">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="bbba2-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="bbba2-155">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="bbba2-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
