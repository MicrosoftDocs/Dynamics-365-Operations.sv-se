---
title: Spara, förhandsgranska och publicera en sida
description: I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8c1b82b1b8423c63d442ee581ed0cc8789ee63fd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697898"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="11cdf-103">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="11cdf-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="11cdf-104">I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="11cdf-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="11cdf-105">Spara en sida</span><span class="sxs-lookup"><span data-stu-id="11cdf-105">Save a page</span></span>

<span data-ttu-id="11cdf-106">Om du vill spara en sida måste du ha checkat ut den till dig själv och öppnat den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="11cdf-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="11cdf-107">Du bör spara en sida omedelbart efter att du har ändrat den, så att du kan garantera att ändringarna sparas.</span><span class="sxs-lookup"><span data-stu-id="11cdf-107">You should save a page immediately after you modify it, to help guarantee that your changes are stored.</span></span>

<span data-ttu-id="11cdf-108">När du sparar en sida är ändringarna bara synliga för dig.</span><span class="sxs-lookup"><span data-stu-id="11cdf-108">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="11cdf-109">Åtgärden Spara är i första hand avsedd att spara ändringar medan sidan inte är klar att checkas in.</span><span class="sxs-lookup"><span data-stu-id="11cdf-109">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="11cdf-110">När du har ändrat sidan rekommenderar vi att du checkar in den, så att ändringarna blir synliga för andra.</span><span class="sxs-lookup"><span data-stu-id="11cdf-110">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="11cdf-111">Vid den punkten kan du även checka ut sidan av andra användare som måste ändra den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-111">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="11cdf-112">Förhandsgranska en sida</span><span class="sxs-lookup"><span data-stu-id="11cdf-112">Preview a page</span></span>

<span data-ttu-id="11cdf-113">I utvecklingsverktyget finns två typer av förhandsgranskningsfunktioner: förhandsgranskningsfönstret "vad du ser är vad du får" (WYSIWYG) i sidredigeraren och ett separat förhandsgranskningsfönster.</span><span class="sxs-lookup"><span data-stu-id="11cdf-113">The authoring tool offers two kinds of preview features: a "what you see is what you get" (WYSIWYG) preview pane in the page editor and a separate preview window.</span></span>

<span data-ttu-id="11cdf-114">Medan du använder sidredigeraren visas förhandsgranskningen "vad du ser är vad du få" (WYSIWYG) i mittenfönstret.</span><span class="sxs-lookup"><span data-stu-id="11cdf-114">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="11cdf-115">Den här förhandsgranskningen uppdateras automatiskt när du sparar sidan.</span><span class="sxs-lookup"><span data-stu-id="11cdf-115">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="11cdf-116">Du kan också uppdatera den manuellt genom att välja **uppdatera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-116">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="11cdf-117">Förhandsgranskningen WYSIWYG visar sidan precis som användarna ser den, men redigeringshjälpare visas ovanpå den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-117">The WYSIWYG preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="11cdf-118">När du är klar med ändringarna av sidan kanske du vill förhandsgranska den för att se vad kunderna kommer att se.</span><span class="sxs-lookup"><span data-stu-id="11cdf-118">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="11cdf-119">Om du vill förhandsgranska en sida väljer du **förhandsgranska** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-119">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="11cdf-120">Förhandsgranskningen visas i ett separat webbläsarfönster.</span><span class="sxs-lookup"><span data-stu-id="11cdf-120">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="11cdf-121">Sidan i förhandsgranskningsfönstret återges på samma sätt som webbplatsens användare kommer att se den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-121">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="11cdf-122">Du kan ändra storlek på fönstret för att säkerställa att alla tillgängliga moduler visas korrekt i alla visningsportar.</span><span class="sxs-lookup"><span data-stu-id="11cdf-122">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="11cdf-123">Autentisering och korrekta behörigheter krävs för att förhandsgranska opublicerat innehåll.</span><span class="sxs-lookup"><span data-stu-id="11cdf-123">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="11cdf-124">Om du till exempel delar URL:en för förhandsgranskningen med någon måste personen ha rätt behörigheter för att få åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-124">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="11cdf-125">Publicera en sida</span><span class="sxs-lookup"><span data-stu-id="11cdf-125">Publish a page</span></span>

<span data-ttu-id="11cdf-126">När sidan är klar är nästa steg att publicera den, så att externa användare kan visa innehållet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-126">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="11cdf-127">Innan du kan publicera en sida måste du checka in den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-127">Before you can publish a page, you must check it in.</span></span>

<span data-ttu-id="11cdf-128">Du kan publicera och avpublicera sidor från antingen sidpanelen eller sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="11cdf-128">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="11cdf-129">Sidkontrollen visar en lista över sidor och tillåter massåtgärder.</span><span class="sxs-lookup"><span data-stu-id="11cdf-129">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="11cdf-130">Sidredigeraren kan bara användas för att publicera eller avpublicera den enda sida som är öppen i den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-130">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="11cdf-131">Om du vill publicera en eller flera sidor från sidpanelen markerar du sidorna, kontrollerar att de är incheckade och väljer sedan **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-131">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="11cdf-132">Sidorna publiceras och du får ett meddelande om åtgärden i redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="11cdf-132">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="11cdf-133">Om du vill publicera en enskild sida från sidredigeraren är proceduren densamma.</span><span class="sxs-lookup"><span data-stu-id="11cdf-133">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="11cdf-134">När sidan är öppen i sidredigeraren kontrollerar du att den har checkats in och väljer sedan **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-134">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="11cdf-135">Sida publiceras och du får ett meddelande om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="11cdf-135">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="11cdf-136">När du publicerar en sida publiceras bara sidans innehåll.</span><span class="sxs-lookup"><span data-stu-id="11cdf-136">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="11cdf-137">Du och andra användare kan gå till sidan och visa den först när en URL har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="11cdf-137">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="11cdf-138">URL:en måste publiceras separat.</span><span class="sxs-lookup"><span data-stu-id="11cdf-138">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11cdf-139">Innan du kan publicera en sida måste alla bilder eller fragment som sid referenserna redan ha publicerats på.</span><span class="sxs-lookup"><span data-stu-id="11cdf-139">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="11cdf-140">Spara, förhandsgranska och publicera en startsida</span><span class="sxs-lookup"><span data-stu-id="11cdf-140">Save, preview, and publish a home page</span></span>

<span data-ttu-id="11cdf-141">Om du vill spara, förhandsgranska och publicera en startsida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="11cdf-141">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="11cdf-142">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="11cdf-142">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="11cdf-143">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-143">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="11cdf-144">Sök och välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="11cdf-144">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="11cdf-145">Välj **Checka ut**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-145">Select **Check Out**.</span></span>
1. <span data-ttu-id="11cdf-146">Ändra sidan efter behov.</span><span class="sxs-lookup"><span data-stu-id="11cdf-146">Modify the page as you require.</span></span>
1. <span data-ttu-id="11cdf-147">Välj **spara**och välj sedan **checka in**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-147">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="11cdf-148">I fältet **kommentarer** anger du en notering om de ändringar som du har gjort och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-148">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="11cdf-149">Välj **Förhandsgranska** om du vill förhandsgranska din sida.</span><span class="sxs-lookup"><span data-stu-id="11cdf-149">Select **Preview** to preview your page.</span></span> <span data-ttu-id="11cdf-150">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="11cdf-150">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="11cdf-151">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-151">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="11cdf-152">Publicera en URL</span><span class="sxs-lookup"><span data-stu-id="11cdf-152">Publish a URL</span></span>

<span data-ttu-id="11cdf-153">Gör så här om du vill publicera en URL.</span><span class="sxs-lookup"><span data-stu-id="11cdf-153">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="11cdf-154">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="11cdf-154">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="11cdf-155">I navigeringsfönstret till vänster, välj **URL:er**.</span><span class="sxs-lookup"><span data-stu-id="11cdf-155">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="11cdf-156">Hitta och markera den URL som du vill publicera.</span><span class="sxs-lookup"><span data-stu-id="11cdf-156">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="11cdf-157">Klicka på **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="11cdf-157">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11cdf-158">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="11cdf-158">Additional resources</span></span>

[<span data-ttu-id="11cdf-159">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="11cdf-159">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="11cdf-160">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="11cdf-160">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="11cdf-161">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="11cdf-161">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="11cdf-162">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="11cdf-162">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="11cdf-163">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="11cdf-163">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="11cdf-164">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="11cdf-164">Enrich a category landing page</span></span>](enrich-category-page.md)

