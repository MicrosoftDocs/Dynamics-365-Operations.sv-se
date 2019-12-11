---
title: Ändra en befintlig webbplatssida
description: I det här avsnittet beskrivs hur du ändrar en befintlig webbplatssida i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ddbef381e9ded18ed1c9226057cac482d4c6e24d
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698382"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="76808-103">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="76808-103">Modify an existing site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="76808-104">I det här avsnittet beskrivs hur du ändrar en befintlig webbplatssida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="76808-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="76808-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="76808-105">Overview</span></span>

<span data-ttu-id="76808-106">När du måste ändra en sida är det första steget att öppna det i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="76808-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="76808-107">Gå till den webbplats som innehåller sidan och leta upp önskad sida i listan med sidor.</span><span class="sxs-lookup"><span data-stu-id="76808-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="76808-108">Om du inte hittar sidan kan du använda redigeringsverktygets funktioner för avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="76808-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="76808-109">Skriv antingen det exakta sidnamnet eller skriv de första bokstäverna i den och sedan en asterisk (\*).</span><span class="sxs-lookup"><span data-stu-id="76808-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="76808-110">En filtrerad lista med sidor visas.</span><span class="sxs-lookup"><span data-stu-id="76808-110">A filtered list of pages appears.</span></span> <span data-ttu-id="76808-111">Du kan använda den här listan för att hitta den sida du vill ha.</span><span class="sxs-lookup"><span data-stu-id="76808-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="76808-112">När du har hittat rätt sida väljer du namnet på sidan så att sidan öppnas i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="76808-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="76808-113">Om sidan visas i sidpanelen kan du markera den och checka ut den innan du öppnar den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="76808-113">If your page is visible in the page inspector, you can select it and check it out before you open it in the page editor.</span></span> <span data-ttu-id="76808-114">På så sätt kan du checka ut flera sidor på samma gång.</span><span class="sxs-lookup"><span data-stu-id="76808-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="76808-115">När sidan har öppnats i sid redigeraren måste du kontrollera att den är utcheckad till dig.</span><span class="sxs-lookup"><span data-stu-id="76808-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="76808-116">Kommandofältet i redigeringsverktyget är dynamiskt, sammanhangskänsligt och tillståndskänsligt.</span><span class="sxs-lookup"><span data-stu-id="76808-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="76808-117">Därför visas endast de åtgärder som du för närvarande kan utföra på sidan.</span><span class="sxs-lookup"><span data-stu-id="76808-117">Therefore, it shows only the actions that you can curently perform on the page.</span></span> <span data-ttu-id="76808-118">Om till exempel sidan inte är utcheckad till dig visas inte knapparna **Spara** och **Checka in** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="76808-118">For example, if the page isn't checked out to you, the **Save** and **Check in** buttons don't appear on the command bar.</span></span> <span data-ttu-id="76808-119">Sidans status visas också till höger om fönstret.</span><span class="sxs-lookup"><span data-stu-id="76808-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="76808-120">Om sidan inte redan är utcheckad till dig väljer du **checka ut** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="76808-120">If the page isn't already checked out to you, select **Check out** on the command bar.</span></span> <span data-ttu-id="76808-121">Kommandofältet ändras med hänsyn till sidans nya status.</span><span class="sxs-lookup"><span data-stu-id="76808-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="76808-122">Du får också ett meddelande om att sidan är utcheckad till dig.</span><span class="sxs-lookup"><span data-stu-id="76808-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="76808-123">Nästa steg är att göra de ändringar du gör.</span><span class="sxs-lookup"><span data-stu-id="76808-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="76808-124">Ofta kommer du att använda siddispositionsträdet till vänster för att söka efter och välja den modul som du vill ändra och sedan göra ändringar i rutan egenskaper till höger.</span><span class="sxs-lookup"><span data-stu-id="76808-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="76808-125">Ändringen kan emellertid ibland innebära att du lägger till eller tar bort modeller eller fragment.</span><span class="sxs-lookup"><span data-stu-id="76808-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="76808-126">Om du vill lägga till ett fragment eller en modul använder du siddispositionsträdet för att hitta den plats där du vill lägga till modulen eller fragmentet. Välj sedan ellipsknappen (**...**) för den platsen.</span><span class="sxs-lookup"><span data-stu-id="76808-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="76808-127">En meny visas som innehåller kommandon för att lägga till en modul eller ett fragment.</span><span class="sxs-lookup"><span data-stu-id="76808-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="76808-128">Om du vill ta bort en modul eller fragment, leta reda på och markera den i siddispositionsträdet, markerar du ellipsknappen och väljer sedan kommandot för att ta bort modulen eller fragmentet.</span><span class="sxs-lookup"><span data-stu-id="76808-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="76808-129">Du kan också visa och redigera egenskaperna för alla moduler som visas i avsnittet "vad du ser är vad du får" (WYSIWYG) förhandsversion genom att markera det direkt.</span><span class="sxs-lookup"><span data-stu-id="76808-129">You can also view and edit the properties for any module that is visible in the "what you see is what you get" (WYSIWYG) preview by selecting it directly.</span></span>

<span data-ttu-id="76808-130">När du är klar med ändringarna och förhandsgranskningen av effekten ska du checka in sidan genom att välja **Checka in** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="76808-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Check in** on the command bar.</span></span> 

<span data-ttu-id="76808-131">Om du vill publicera ändringarna direkt väljer du **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="76808-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="76808-132">Den senaste incheckade versionen av sidan som du ändrade publiceras och blir tillgänglig för externa användare som visar webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="76808-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="76808-133">Exempel: ändra videon på startsidan</span><span class="sxs-lookup"><span data-stu-id="76808-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="76808-134">Följande exempel visar hur du ändrar startsidan genom att ändra videon som visas i videospelarmodulen.</span><span class="sxs-lookup"><span data-stu-id="76808-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="76808-135">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="76808-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="76808-136">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="76808-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="76808-137">Sök och välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="76808-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="76808-138">Klicka på **utcheckning** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="76808-138">On the command bar, select **Check Out**.</span></span>
1. <span data-ttu-id="76808-139">I siddispositionen, välj platsen **Huvud**.</span><span class="sxs-lookup"><span data-stu-id="76808-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="76808-140">Under **Huvud** för vätskebehållare under huvudplatsen.</span><span class="sxs-lookup"><span data-stu-id="76808-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="76808-141">Leta reda på och markera videospelarmodulen.</span><span class="sxs-lookup"><span data-stu-id="76808-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="76808-142">I egenskapsrutan till höger, välj egenskapen **video**.</span><span class="sxs-lookup"><span data-stu-id="76808-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="76808-143">Tillgångsväljaren visas.</span><span class="sxs-lookup"><span data-stu-id="76808-143">The asset picker appears.</span></span>
1. <span data-ttu-id="76808-144">Markera en tillgänglig videoresurs i tillgångsväljaren eller välj **överför ny tillgång** om du vill överföra en ny videotillgång.</span><span class="sxs-lookup"><span data-stu-id="76808-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="76808-145">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="76808-145">Select **OK**.</span></span>
1. <span data-ttu-id="76808-146">Välj **spara**och välj sedan **checka in**.</span><span class="sxs-lookup"><span data-stu-id="76808-146">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="76808-147">I fältet **kommentarer** anger du **Ändrade videon** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="76808-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="76808-148">Välj **Förhandsgranska** om du vill förhandsgranska den uppdaterade sidan.</span><span class="sxs-lookup"><span data-stu-id="76808-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="76808-149">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="76808-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="76808-150">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="76808-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76808-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="76808-151">Additional resources</span></span>

[<span data-ttu-id="76808-152">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="76808-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="76808-153">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="76808-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="76808-154">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="76808-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="76808-155">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="76808-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="76808-156">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="76808-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="76808-157">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="76808-157">Enrich a category landing page</span></span>](enrich-category-page.md)
