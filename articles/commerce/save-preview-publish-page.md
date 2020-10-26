---
title: Spara, förhandsgranska och publicera en sida
description: I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: db4866b22060b764fdde3e4a44e99e969133c0a0
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961620"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="8f2c7-103">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f2c7-104">I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="8f2c7-105">Spara en sida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-105">Save a page</span></span>

<span data-ttu-id="8f2c7-106">Om du vill spara en sida måste du ha checkat ut den till dig själv och öppnat den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="8f2c7-107">För att checka ut en sida, välj **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-107">To check out a page, select **Edit** on the command bar.</span></span> <span data-ttu-id="8f2c7-108">När du har redigerat en sida bör du omedelbart spara den för att se till att dina ändringar lagras.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-108">After you've finished editing a page, you should immediately save it to ensure that your changes are stored.</span></span>

<span data-ttu-id="8f2c7-109">När du sparar en sida är ändringarna bara synliga för dig.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-109">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="8f2c7-110">Åtgärden Spara är i första hand avsedd att spara ändringar medan sidan inte är klar att checkas in.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-110">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="8f2c7-111">När du har ändrat sidan rekommenderar vi att du checkar in den, så att ändringarna blir synliga för andra.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-111">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="8f2c7-112">Vid den punkten kan du även checka ut sidan av andra användare som måste ändra den.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-112">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="8f2c7-113">Förhandsgranska en sida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-113">Preview a page</span></span>

<span data-ttu-id="8f2c7-114">I utvecklingsverktyget finns två typer av förhandsgranskningsfunktioner: visuell sidskapare som är "vad du ser är vad du får" (WYSIWYG) i sidredigeraren och ett separat förhandsgranskningsfönster.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-114">The authoring tool offers two kinds of preview features: visual page builder, which is a "what you see is what you get" (WYSIWYG) preview pane in the page editor, and a separate preview window.</span></span>

<span data-ttu-id="8f2c7-115">Medan du använder sidredigeraren visas förhandsgranskningen "vad du ser är vad du få" (WYSIWYG) i mittenfönstret.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-115">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="8f2c7-116">Den här förhandsgranskningen uppdateras automatiskt när du sparar sidan.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-116">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="8f2c7-117">Du kan också uppdatera den manuellt genom att välja **uppdatera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-117">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="8f2c7-118">Förhandsgranskningen visar sidan precis som användarna ser den, men redigeringshjälpare visas ovanpå den.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-118">The preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="8f2c7-119">När du är klar med ändringarna av sidan kanske du vill förhandsgranska den för att se vad kunderna kommer att se.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-119">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="8f2c7-120">Om du vill förhandsgranska en sida väljer du **förhandsgranska** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-120">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="8f2c7-121">Förhandsgranskningen visas i ett separat webbläsarfönster.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-121">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="8f2c7-122">Sidan i förhandsgranskningsfönstret återges på samma sätt som webbplatsens användare kommer att se den.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-122">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="8f2c7-123">Du kan ändra storlek på fönstret för att säkerställa att alla tillgängliga moduler visas korrekt i alla visningsportar.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-123">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="8f2c7-124">Autentisering och korrekta behörigheter krävs för att förhandsgranska opublicerat innehåll.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-124">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="8f2c7-125">Om du till exempel delar URL:en för förhandsgranskningen med någon måste personen ha rätt behörigheter för att få åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-125">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="8f2c7-126">Publicera en sida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-126">Publish a page</span></span>

<span data-ttu-id="8f2c7-127">När sidan är klar är nästa steg att publicera den, så att externa användare kan visa innehållet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-127">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="8f2c7-128">Innan du kan publicera en sida måste du checka in den genom att välja **Slutför redigering** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-128">Before you can publish a page, you must check it in by selecting **Finish editing** on the command bar.</span></span>

<span data-ttu-id="8f2c7-129">Du kan publicera och avpublicera sidor från antingen sidpanelen eller sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-129">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="8f2c7-130">Sidkontrollen visar en lista över sidor och tillåter massåtgärder.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-130">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="8f2c7-131">Sidredigeraren kan bara användas för att publicera eller avpublicera den enda sida som är öppen i den.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-131">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="8f2c7-132">Om du vill publicera en eller flera sidor från sidpanelen markerar du sidorna, kontrollerar att de är incheckade och väljer sedan **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-132">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="8f2c7-133">Sidorna publiceras och du får ett meddelande om åtgärden i redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-133">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="8f2c7-134">Om du vill publicera en enskild sida från sidredigeraren är proceduren densamma.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-134">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="8f2c7-135">När sidan är öppen i sidredigeraren kontrollerar du att den har checkats in och väljer sedan **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-135">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="8f2c7-136">Sida publiceras och du får ett meddelande om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-136">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="8f2c7-137">När du publicerar en sida publiceras bara sidans innehåll.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-137">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="8f2c7-138">Du och andra användare kan gå till sidan och visa den först när en URL har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-138">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="8f2c7-139">URL:en måste publiceras separat.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-139">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f2c7-140">Innan du kan publicera en sida måste alla bilder eller fragment som sid referenserna redan ha publicerats på.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-140">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="8f2c7-141">Spara, förhandsgranska och publicera en startsida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-141">Save, preview, and publish a home page</span></span>

<span data-ttu-id="8f2c7-142">Om du vill spara, förhandsgranska och publicera en startsida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-142">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="8f2c7-143">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="8f2c7-143">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="8f2c7-144">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-144">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="8f2c7-145">Sök och välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-145">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="8f2c7-146">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-146">Select **Edit**.</span></span>
1. <span data-ttu-id="8f2c7-147">Ändra sidan efter behov.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-147">Modify the page as you require.</span></span>
1. <span data-ttu-id="8f2c7-148">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-148">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8f2c7-149">I fältet **kommentarer** anger du en notering om de ändringar som du har gjort och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-149">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="8f2c7-150">Välj **Förhandsgranska** om du vill förhandsgranska din sida.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-150">Select **Preview** to preview your page.</span></span> <span data-ttu-id="8f2c7-151">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-151">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="8f2c7-152">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-152">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="8f2c7-153">Publicera en URL</span><span class="sxs-lookup"><span data-stu-id="8f2c7-153">Publish a URL</span></span>

<span data-ttu-id="8f2c7-154">Gör så här om du vill publicera en URL.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-154">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="8f2c7-155">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="8f2c7-155">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="8f2c7-156">I navigeringsfönstret till vänster, välj **URL:er**.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-156">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="8f2c7-157">Hitta och markera den URL som du vill publicera.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-157">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="8f2c7-158">Klicka på **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-158">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f2c7-159">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8f2c7-159">Additional resources</span></span>

[<span data-ttu-id="8f2c7-160">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-160">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="8f2c7-161">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-161">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="8f2c7-162">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="8f2c7-162">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="8f2c7-163">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="8f2c7-163">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="8f2c7-164">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-164">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="8f2c7-165">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="8f2c7-165">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="8f2c7-166">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="8f2c7-166">Verify page content accessibility</span></span>](verify-accessibility.md)
