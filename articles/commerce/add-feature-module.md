---
title: Funktionsmodul
description: Det här avsnittet innehåller moduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785316"
---
# <a name="feature-module"></a><span data-ttu-id="a121b-103">Funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a121b-104">Det här avsnittet innehåller moduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a121b-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a121b-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a121b-105">Overview</span></span>

<span data-ttu-id="a121b-106">En funktionsmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text.</span><span class="sxs-lookup"><span data-stu-id="a121b-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="a121b-107">En åter försäljare kan t.ex. lägga till en modul på en produktinformationssida för att framhäva produktens funktioner.</span><span class="sxs-lookup"><span data-stu-id="a121b-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="a121b-108">En funktionsmodul drivs av data från innehållshanteringssystemet (CMS).</span><span class="sxs-lookup"><span data-stu-id="a121b-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="a121b-109">Det är en fristående modul som inte är beroende av andra moduler på sidan.</span><span class="sxs-lookup"><span data-stu-id="a121b-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="a121b-110">En funktionsmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).</span><span class="sxs-lookup"><span data-stu-id="a121b-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="a121b-111">Exempel på funktionsmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="a121b-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="a121b-112">En funktionsmodul kan användas på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="a121b-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="a121b-113">För att presentera produktfunktioner på en produktinformationssida</span><span class="sxs-lookup"><span data-stu-id="a121b-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="a121b-114">För att främja produkter på startsidan</span><span class="sxs-lookup"><span data-stu-id="a121b-114">The home page, to promote products</span></span>
- <span data-ttu-id="a121b-115">För att markera en produktkategori på en kategorisida</span><span class="sxs-lookup"><span data-stu-id="a121b-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="a121b-116">Egenskaper för funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-116">Feature module properties</span></span>

| <span data-ttu-id="a121b-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="a121b-117">Property name</span></span>     | <span data-ttu-id="a121b-118">Värden</span><span class="sxs-lookup"><span data-stu-id="a121b-118">Values</span></span> | <span data-ttu-id="a121b-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a121b-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="a121b-120">Bild</span><span class="sxs-lookup"><span data-stu-id="a121b-120">Image</span></span>             | <span data-ttu-id="a121b-121">Bildfil</span><span class="sxs-lookup"><span data-stu-id="a121b-121">Image file</span></span> | <span data-ttu-id="a121b-122">En bild kan användas för att marknadsföra en produkt eller ett erbjudande.</span><span class="sxs-lookup"><span data-stu-id="a121b-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="a121b-123">En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas.</span><span class="sxs-lookup"><span data-stu-id="a121b-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="a121b-124">Rubrik</span><span class="sxs-lookup"><span data-stu-id="a121b-124">Heading</span></span>           | <span data-ttu-id="a121b-125">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="a121b-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="a121b-126">Varje funktionsmodul kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="a121b-126">Every feature module can have a heading.</span></span> <span data-ttu-id="a121b-127">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="a121b-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="a121b-128">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="a121b-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="a121b-129">Stycke</span><span class="sxs-lookup"><span data-stu-id="a121b-129">Paragraph</span></span>         | <span data-ttu-id="a121b-130">Stycketext</span><span class="sxs-lookup"><span data-stu-id="a121b-130">Paragraph text</span></span> | <span data-ttu-id="a121b-131">Funktionsmoduler har stöd för stycketext i RTF-format.</span><span class="sxs-lookup"><span data-stu-id="a121b-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="a121b-132">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar.</span><span class="sxs-lookup"><span data-stu-id="a121b-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="a121b-133">Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen.</span><span class="sxs-lookup"><span data-stu-id="a121b-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="a121b-134">Länka</span><span class="sxs-lookup"><span data-stu-id="a121b-134">Link</span></span>              | <span data-ttu-id="a121b-135">Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik**</span><span class="sxs-lookup"><span data-stu-id="a121b-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="a121b-136">Funktionsmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar.</span><span class="sxs-lookup"><span data-stu-id="a121b-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="a121b-137">Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs.</span><span class="sxs-lookup"><span data-stu-id="a121b-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="a121b-138">ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="a121b-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="a121b-139">Länkar kan konfigureras så att de öppnas på en ny flik.</span><span class="sxs-lookup"><span data-stu-id="a121b-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="a121b-140">Bildplacering</span><span class="sxs-lookup"><span data-stu-id="a121b-140">Image placement</span></span>   | <span data-ttu-id="a121b-141">**Höger**, **vänster**, **över**eller **under**</span><span class="sxs-lookup"><span data-stu-id="a121b-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="a121b-142">Den här egenskapen definierar bildens placering i förhållande till texten.</span><span class="sxs-lookup"><span data-stu-id="a121b-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="a121b-143">Om till exempel **höger** är markerad visas bilden till höger om texten.</span><span class="sxs-lookup"><span data-stu-id="a121b-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="a121b-144">Storlek på bildkolumn</span><span class="sxs-lookup"><span data-stu-id="a121b-144">Image column size</span></span> | <span data-ttu-id="a121b-145">Ett värde mellan **1** och **12**</span><span class="sxs-lookup"><span data-stu-id="a121b-145">A value from **1** through **12**</span></span> | <span data-ttu-id="a121b-146">Den här egenskapen definierar bildens storlek i förhållande till texten.</span><span class="sxs-lookup"><span data-stu-id="a121b-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="a121b-147">Storleken uttrycks som ett antal kolumner på sidan.</span><span class="sxs-lookup"><span data-stu-id="a121b-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="a121b-148">Det finns 12 kolumner på en sida.</span><span class="sxs-lookup"><span data-stu-id="a121b-148">There are 12 columns on a page.</span></span> <span data-ttu-id="a121b-149">Som standard har bilden och texten samma storlek (sex kolumner vardera).</span><span class="sxs-lookup"><span data-stu-id="a121b-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="a121b-150">Storleken kan dock justeras efter behov.</span><span class="sxs-lookup"><span data-stu-id="a121b-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="a121b-151">Lägg till en funktionsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="a121b-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="a121b-152">Om du vill lägga till en funktionsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a121b-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="a121b-153">Gå till **mallar**och skapa en sidmall med namnet **funktionsmall**.</span><span class="sxs-lookup"><span data-stu-id="a121b-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="a121b-154">Lägg till platsen **Huvud** på standardsida, lägg till en funktionsmodul.</span><span class="sxs-lookup"><span data-stu-id="a121b-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="a121b-155">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="a121b-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="a121b-156">Använd den funktionsmall som du just skapade för att skapa en sida med namnet **funktionssida**.</span><span class="sxs-lookup"><span data-stu-id="a121b-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="a121b-157">I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="a121b-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="a121b-158">I dialogrutan **Lägg till modul**, under **Välj moduler**, välj funktionsmodul och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a121b-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="a121b-159">I dispositionsträdet till vänster väljer du funktionsmodulen.</span><span class="sxs-lookup"><span data-stu-id="a121b-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="a121b-160">I egenskapsrutan till höger, välj egenskapen **Lägg till en bild**.</span><span class="sxs-lookup"><span data-stu-id="a121b-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="a121b-161">Välj antingen en befintlig bild eller överför en ny avbildning.</span><span class="sxs-lookup"><span data-stu-id="a121b-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="a121b-162">Välj **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="a121b-162">Select **Heading**.</span></span>
1. <span data-ttu-id="a121b-163">I dialogrutan **rubrik** lägg till rubriktexten, välj rubrik nivå och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a121b-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="a121b-164">Under **oformaterad text** lägger du till text efter behov.</span><span class="sxs-lookup"><span data-stu-id="a121b-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="a121b-165">Välj **Lägg till åtgärdslänk**.</span><span class="sxs-lookup"><span data-stu-id="a121b-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="a121b-166">I dialogrutan **åtgärdslänk** lägg till länktext, en länk-URL och en ARIA-etikett för länken och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a121b-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="a121b-167">Spara sidan och förhandsgranska ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a121b-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="a121b-168">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="a121b-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a121b-169">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a121b-169">Additional resources</span></span>

[<span data-ttu-id="a121b-170">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="a121b-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a121b-171">Notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="a121b-172">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="a121b-173">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="a121b-174">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="a121b-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="a121b-175">Fokusmodul</span><span class="sxs-lookup"><span data-stu-id="a121b-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="a121b-176">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="a121b-176">Video player module</span></span>](add-video-player.md)
