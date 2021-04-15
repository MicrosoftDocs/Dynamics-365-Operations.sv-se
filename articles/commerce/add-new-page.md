---
title: Lägga till en ny webbplatssida
description: I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 4a2ecc3ef3ff3f708cec50e42777b50ec4576e25
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797561"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="2f387-103">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="2f387-103">Add a new site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2f387-104">I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2f387-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2f387-105">När du har skapat mallar och fragment för din webbplats, är nästa steg att börja skapa sidor som använder dem.</span><span class="sxs-lookup"><span data-stu-id="2f387-105">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="2f387-106">Du måste välja en mall eller layout, ett sidnamn och en sidadress för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="2f387-106">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="2f387-107">Mall eller layout</span><span class="sxs-lookup"><span data-stu-id="2f387-107">Template or layout</span></span>

<span data-ttu-id="2f387-108">Du kan använda antingen en mall eller en layout för den nya sidan.</span><span class="sxs-lookup"><span data-stu-id="2f387-108">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="2f387-109">Mer information finns i [Översikt över mallar och layouter](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f387-109">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="2f387-110">Sidnamn</span><span class="sxs-lookup"><span data-stu-id="2f387-110">Page name</span></span>

<span data-ttu-id="2f387-111">Sidnamnet måste vara unikt för sidan.</span><span class="sxs-lookup"><span data-stu-id="2f387-111">The page name must be unique to your page.</span></span> <span data-ttu-id="2f387-112">Den ska vara beskrivande, så att du lätt kan hitta den och andra personer som vet vad sidan är avsedd för.</span><span class="sxs-lookup"><span data-stu-id="2f387-112">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="2f387-113">Välj ett sidnamn noggrant eftersom det inte kan ändras vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="2f387-113">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="2f387-114">Sid-URL</span><span class="sxs-lookup"><span data-stu-id="2f387-114">Page URL</span></span>

<span data-ttu-id="2f387-115">Du kan välja att ange en URL för den nya sidan.</span><span class="sxs-lookup"><span data-stu-id="2f387-115">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="2f387-116">När du skapar en sida kan du ange en sträng som ska användas för att skapa en fullständig URL.</span><span class="sxs-lookup"><span data-stu-id="2f387-116">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="2f387-117">Den här strängen kallas för en relativ URL eller en URL-instruktion.</span><span class="sxs-lookup"><span data-stu-id="2f387-117">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="2f387-118">En fullständig URL genereras sedan utifrån URL-instruktionen och den nya sidan tilldelas den.</span><span class="sxs-lookup"><span data-stu-id="2f387-118">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="2f387-119">Du kan ändra URL-instruktionen senare innan du publicerar sidan.</span><span class="sxs-lookup"><span data-stu-id="2f387-119">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="2f387-120">Mer information finns i [Skapa en sid-URL](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="2f387-120">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2f387-121">Dynamics 365 Commerce kopplas från URL och innehåll.</span><span class="sxs-lookup"><span data-stu-id="2f387-121">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="2f387-122">Med andra ord kan en sida skapas som inte är kopplad till en URL adress, och en URL kan skapas som inte är kopplad till en sida.</span><span class="sxs-lookup"><span data-stu-id="2f387-122">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="2f387-123">Därför kan innehållsbyte ske för en URL-adress och det kräver inte driftstopp och omdirigeringar är enklare att hantera.</span><span class="sxs-lookup"><span data-stu-id="2f387-123">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="2f387-124">Lägga till en ny sida</span><span class="sxs-lookup"><span data-stu-id="2f387-124">Add a new page</span></span>

<span data-ttu-id="2f387-125">Gör så här om du vill lägga till en ny webbplatssida till din webbplats:</span><span class="sxs-lookup"><span data-stu-id="2f387-125">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="2f387-126">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="2f387-126">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="2f387-127">Välj **Ny sida**.</span><span class="sxs-lookup"><span data-stu-id="2f387-127">Select **New Page**.</span></span>
1. <span data-ttu-id="2f387-128">I dialogrutan **Ny sida** väljer du en strukturlistemall och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-128">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="2f387-129">I fältet **Sidnamn** anger du ett sidnamn (till exempel **Min nya sida**).</span><span class="sxs-lookup"><span data-stu-id="2f387-129">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="2f387-130">I fältet **URL** anger du en sträng (URL-instruktion) för att slutföra URL:en (t.ex. **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="2f387-130">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="2f387-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-131">Select **OK**.</span></span> <span data-ttu-id="2f387-132">Sidredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="2f387-132">The page editor appears.</span></span> <span data-ttu-id="2f387-133">Observera att ett sidhuvud och en sidfot läggs till automatiskt på sidan, baserat på den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="2f387-133">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="2f387-134">I siddispositionen väljer du platsen **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2f387-134">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2f387-135">Välj **Behållare** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-135">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="2f387-136">Markera knappen med punkter för **vätskebehållare** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2f387-136">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2f387-137">Välj **Innehållsrikt block** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-137">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="2f387-138">Markera knappen med punkter för **Innehållsrikt block** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2f387-138">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2f387-139">Välj **Artikeln innehållsrikt block** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-139">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="2f387-140">I egenskapsrutan till höger, välj **Paragraf** och ange sedan **Min testtext** i fältet.</span><span class="sxs-lookup"><span data-stu-id="2f387-140">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="2f387-141">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="2f387-141">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="2f387-142">I fältet **kommentarer** anger du **Ny sida tillagd** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f387-142">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="2f387-143">Välj **Förhandsgranska** om du vill förhandsgranska din sida.</span><span class="sxs-lookup"><span data-stu-id="2f387-143">Select **Preview** to preview your page.</span></span> <span data-ttu-id="2f387-144">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="2f387-144">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="2f387-145">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="2f387-145">Select **Publish**.</span></span>
1. <span data-ttu-id="2f387-146">I navigeringssökvägen (navigeringssökvägar), välj **Fabrikam** (eller namnet på platsen).</span><span class="sxs-lookup"><span data-stu-id="2f387-146">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="2f387-147">I navigeringsfönstret till vänster, välj **URL:er**.</span><span class="sxs-lookup"><span data-stu-id="2f387-147">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="2f387-148">Hitta och välj din URL (**mynewpage**) i listan.</span><span class="sxs-lookup"><span data-stu-id="2f387-148">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="2f387-149">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="2f387-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f387-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2f387-150">Additional resources</span></span>

[<span data-ttu-id="2f387-151">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="2f387-151">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="2f387-152">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="2f387-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="2f387-153">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="2f387-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="2f387-154">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="2f387-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="2f387-155">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="2f387-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="2f387-156">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="2f387-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="2f387-157">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="2f387-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="2f387-158">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="2f387-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
