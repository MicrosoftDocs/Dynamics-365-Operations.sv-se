---
title: Hantera SEO-metadata
description: I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00942befef9f9b6a878766bbbb5341426e31db2c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252616"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="7aeec-103">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="7aeec-103">Manage SEO metadata</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7aeec-104">I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7aeec-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7aeec-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="7aeec-105">Overview</span></span>

<span data-ttu-id="7aeec-106">SEO-metadata för en plats kan hanteras med hjälp av webbplatskartor och sidmetadata.</span><span class="sxs-lookup"><span data-stu-id="7aeec-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="7aeec-107">Webbplatskartor</span><span class="sxs-lookup"><span data-stu-id="7aeec-107">Site maps</span></span>

<span data-ttu-id="7aeec-108">En webbplatskarta är en maskinläsbar lista, i XML-format, för sidorna på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="7aeec-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="7aeec-109">Den är avsedd att förbrukas av sökmotorer så att de kan ge bättre sökresultat från din webbplats.</span><span class="sxs-lookup"><span data-stu-id="7aeec-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="7aeec-110">Webbplatskartor kan manuellt förtäras av sökmotorer eller publiceras i en robots.txt-fil.</span><span class="sxs-lookup"><span data-stu-id="7aeec-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="7aeec-111">Dynamics 365 Commerce stöder automatisk generering av webbplatsmappningar.</span><span class="sxs-lookup"><span data-stu-id="7aeec-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="7aeec-112">Webbplatsmappningar uppdateras automatiskt när sidor publiceras och avpubliceras.</span><span class="sxs-lookup"><span data-stu-id="7aeec-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="7aeec-113">Aktivera generering av webbplatskarta</span><span class="sxs-lookup"><span data-stu-id="7aeec-113">Turn on site map generation</span></span>

1. <span data-ttu-id="7aeec-114">Logga in till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="7aeec-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="7aeec-115">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="7aeec-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7aeec-116">I navigeringsfönstret till vänster, välj **Platshantering**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="7aeec-117">Kontrollera att alternativet **Webbplatskartor aktiverade** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="7aeec-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="7aeec-118">Metadata för sida</span><span class="sxs-lookup"><span data-stu-id="7aeec-118">Page metadata</span></span>

<span data-ttu-id="7aeec-119">Dynamics 365 Commerce gör att du kan hantera SEO-metadata för enskilda sidor.</span><span class="sxs-lookup"><span data-stu-id="7aeec-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="7aeec-120">Du kan visa och ändra denna information i avsnittet **SEO-egenskaper** i en sidbehållare.</span><span class="sxs-lookup"><span data-stu-id="7aeec-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="7aeec-121">Följande egenskaper för SEO-metadata stöds:</span><span class="sxs-lookup"><span data-stu-id="7aeec-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="7aeec-122">Rubrik</span><span class="sxs-lookup"><span data-stu-id="7aeec-122">Title</span></span>
- <span data-ttu-id="7aeec-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7aeec-123">Description</span></span>
- <span data-ttu-id="7aeec-124">SEO-nyckelord</span><span class="sxs-lookup"><span data-stu-id="7aeec-124">SEO keywords</span></span>
- <span data-ttu-id="7aeec-125">Aria-etiketter</span><span class="sxs-lookup"><span data-stu-id="7aeec-125">Aria labels</span></span>
- <span data-ttu-id="7aeec-126">noindex</span><span class="sxs-lookup"><span data-stu-id="7aeec-126">noindex</span></span>
- <span data-ttu-id="7aeec-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="7aeec-127">nofollow</span></span>
- <span data-ttu-id="7aeec-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="7aeec-128">noarchive</span></span>
- <span data-ttu-id="7aeec-129">nocache</span><span class="sxs-lookup"><span data-stu-id="7aeec-129">nocache</span></span>
- <span data-ttu-id="7aeec-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="7aeec-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="7aeec-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="7aeec-131">nosnippet</span></span>
- <span data-ttu-id="7aeec-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="7aeec-132">noImageIndex</span></span>
- <span data-ttu-id="7aeec-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="7aeec-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="7aeec-134">Ändra metadata för sidan</span><span class="sxs-lookup"><span data-stu-id="7aeec-134">Modify page metadata</span></span>

<span data-ttu-id="7aeec-135">Om du vill ändra metadata, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="7aeec-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="7aeec-136">Under **Webbplatser**, välj **Fabrikam** (eller namet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="7aeec-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7aeec-137">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="7aeec-138">Välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="7aeec-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="7aeec-139">Klicka på **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="7aeec-139">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="7aeec-140">I fönstret Egenskaper till höger, visa **Standardmetataggar**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="7aeec-141">Om du vill lägga till en ny metatagg väljer du **Lägg till** och anger sedan taggen i fältet.</span><span class="sxs-lookup"><span data-stu-id="7aeec-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="7aeec-142">Om du vill ta bort en befintlig metatagg markerar du papperskorgen till höger om den.</span><span class="sxs-lookup"><span data-stu-id="7aeec-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="7aeec-143">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-143">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7aeec-144">I fältet **kommentarer** anger du **Uppdaterade metataggar** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="7aeec-145">Välj **Förhandsgranska** om du vill förhandsgranska din sida.</span><span class="sxs-lookup"><span data-stu-id="7aeec-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="7aeec-146">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="7aeec-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="7aeec-147">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="7aeec-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7aeec-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7aeec-148">Additional resources</span></span>

[<span data-ttu-id="7aeec-149">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="7aeec-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="7aeec-150">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="7aeec-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="7aeec-151">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="7aeec-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="7aeec-152">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="7aeec-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="7aeec-153">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="7aeec-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="7aeec-154">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="7aeec-154">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="7aeec-155">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="7aeec-155">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="7aeec-156">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="7aeec-156">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]