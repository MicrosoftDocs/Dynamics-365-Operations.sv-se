---
title: Fokusmodul
description: Det här avsnittet handlar om fokusmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785408"
---
# <a name="hero-module"></a><span data-ttu-id="af9c7-103">Fokusmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="af9c7-104">Det här avsnittet handlar om fokusmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="af9c7-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="af9c7-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="af9c7-105">Overview</span></span>

<span data-ttu-id="af9c7-106">En fokusmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text.</span><span class="sxs-lookup"><span data-stu-id="af9c7-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="af9c7-107">En återförsäljare kan till exempel lägga till en fokusmodul på startsidan för en näthandelsplats för att marknadsföra en ny produkt och locka kundernas uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="af9c7-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="af9c7-108">En fokusmodul drivs av data från innehållshanteringssystemet (CMS).</span><span class="sxs-lookup"><span data-stu-id="af9c7-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="af9c7-109">Det är en fristående modul som inte är beroende av andra moduler på sidan.</span><span class="sxs-lookup"><span data-stu-id="af9c7-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="af9c7-110">En fokusmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).</span><span class="sxs-lookup"><span data-stu-id="af9c7-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="af9c7-111">Exempel på fokusmodul i e-handel</span><span class="sxs-lookup"><span data-stu-id="af9c7-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="af9c7-112">En fokusmodul kan användas på startsidan för en näthandelsplats för att framhäva erbjudanden och nya produkter.</span><span class="sxs-lookup"><span data-stu-id="af9c7-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="af9c7-113">En fokusmodul kan användas på en produktinformationssida för att visa upp produktinformation.</span><span class="sxs-lookup"><span data-stu-id="af9c7-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="af9c7-114">Flera fokusmoduler kan placeras i en karusellmodul för att framhäva flera produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="af9c7-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="af9c7-115">Egenskaper för fokusmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-115">Hero module properties</span></span>

| <span data-ttu-id="af9c7-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="af9c7-116">Property name</span></span>  | <span data-ttu-id="af9c7-117">Värden</span><span class="sxs-lookup"><span data-stu-id="af9c7-117">Values</span></span> | <span data-ttu-id="af9c7-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="af9c7-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="af9c7-119">Bild</span><span class="sxs-lookup"><span data-stu-id="af9c7-119">Image</span></span>          | <span data-ttu-id="af9c7-120">Bildfil</span><span class="sxs-lookup"><span data-stu-id="af9c7-120">Image file</span></span> | <span data-ttu-id="af9c7-121">En bild kan användas för att presentera en produkt eller ett erbjudande.</span><span class="sxs-lookup"><span data-stu-id="af9c7-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="af9c7-122">En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas.</span><span class="sxs-lookup"><span data-stu-id="af9c7-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="af9c7-123">Rubrik</span><span class="sxs-lookup"><span data-stu-id="af9c7-123">Heading</span></span>        | <span data-ttu-id="af9c7-124">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="af9c7-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="af9c7-125">Varje fokusmodul kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="af9c7-125">Every hero module can have a heading.</span></span> <span data-ttu-id="af9c7-126">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="af9c7-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="af9c7-127">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="af9c7-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="af9c7-128">Stycke</span><span class="sxs-lookup"><span data-stu-id="af9c7-128">Paragraph</span></span>      | <span data-ttu-id="af9c7-129">Stycketext</span><span class="sxs-lookup"><span data-stu-id="af9c7-129">Paragraph text</span></span> | <span data-ttu-id="af9c7-130">Fokusmoduler har stöd för stycketext i RTF-format.</span><span class="sxs-lookup"><span data-stu-id="af9c7-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="af9c7-131">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar.</span><span class="sxs-lookup"><span data-stu-id="af9c7-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="af9c7-132">Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen.</span><span class="sxs-lookup"><span data-stu-id="af9c7-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="af9c7-133">Länka</span><span class="sxs-lookup"><span data-stu-id="af9c7-133">Link</span></span>           | <span data-ttu-id="af9c7-134">Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik**</span><span class="sxs-lookup"><span data-stu-id="af9c7-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="af9c7-135">Fokusmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar.</span><span class="sxs-lookup"><span data-stu-id="af9c7-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="af9c7-136">Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs.</span><span class="sxs-lookup"><span data-stu-id="af9c7-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="af9c7-137">ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="af9c7-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="af9c7-138">Länkar kan konfigureras så att de öppnas på en ny flik.</span><span class="sxs-lookup"><span data-stu-id="af9c7-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="af9c7-139">Textplacering</span><span class="sxs-lookup"><span data-stu-id="af9c7-139">Text placement</span></span> | <span data-ttu-id="af9c7-140">**Högst upp till vänster**, **Högst upp till höger**, **Högst upp i mitten**, **Längst ned till vänster**, **Längst ned till höger**, **Längst ned i mitten**, **Mitten till vänster**, **Mitten till höger** eller **Mitten mitten**</span><span class="sxs-lookup"><span data-stu-id="af9c7-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="af9c7-141">Den här egenskapen definierar bildens placering i förhållande till texten.</span><span class="sxs-lookup"><span data-stu-id="af9c7-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="af9c7-142">Om till exempel **höger** är markerad visas bilden till höger om texten.</span><span class="sxs-lookup"><span data-stu-id="af9c7-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="af9c7-143">Texttema</span><span class="sxs-lookup"><span data-stu-id="af9c7-143">Text theme</span></span>     | <span data-ttu-id="af9c7-144">**Ljus** eller **Mörk**</span><span class="sxs-lookup"><span data-stu-id="af9c7-144">**Light** or **Dark**</span></span> | <span data-ttu-id="af9c7-145">Ett färgschema kan definieras för texten, baserat på bakgrundsbilden.</span><span class="sxs-lookup"><span data-stu-id="af9c7-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="af9c7-146">Om bilden t.ex. har en mörk bakgrund kan ett ljust tema användas för att göra texten mer synlig och för att uppfylla färg kontrastförhållandena för hjälpmedelssyfte.</span><span class="sxs-lookup"><span data-stu-id="af9c7-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="af9c7-147">Toning</span><span class="sxs-lookup"><span data-stu-id="af9c7-147">Gradient</span></span>       | <span data-ttu-id="af9c7-148">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="af9c7-148">**True** or **False**</span></span> | <span data-ttu-id="af9c7-149">En övertoning kan användas på bilden för att uppfylla färgkontrastförhållanden för hjälpmedelssyfte.</span><span class="sxs-lookup"><span data-stu-id="af9c7-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="af9c7-150">Lägg till en fokusmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="af9c7-150">Add a hero module to a new page</span></span>

<span data-ttu-id="af9c7-151">Om du vill lägga till en fokusmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="af9c7-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="af9c7-152">Gå till **mallar**och skapa en sidmall med namnet **fokusmall**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="af9c7-153">Lägg till platsen **Huvud** på standardsida, lägg till fokusmodul.</span><span class="sxs-lookup"><span data-stu-id="af9c7-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="af9c7-154">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="af9c7-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="af9c7-155">Använd den fokusmall som du just skapade för att skapa en sida med namnet **fokussida**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="af9c7-156">I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="af9c7-157">I dialogrutan **Lägg till modul**, under **Välj moduler**, välj fokusmodul och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="af9c7-158">I dispositionsträdet till vänster väljer du fokusmodulen.</span><span class="sxs-lookup"><span data-stu-id="af9c7-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="af9c7-159">I egenskapsrutan till höger, välj egenskapen **Lägg till en bild**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="af9c7-160">Välj antingen en befintlig bild eller överför en ny avbildning.</span><span class="sxs-lookup"><span data-stu-id="af9c7-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="af9c7-161">Välj **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-161">Select **Heading**.</span></span>
1. <span data-ttu-id="af9c7-162">I dialogrutan **rubrik** lägg till rubriktexten, välj rubrik nivå och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="af9c7-163">Under **oformaterad text** lägger du till text efter behov.</span><span class="sxs-lookup"><span data-stu-id="af9c7-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="af9c7-164">Välj **Lägg till åtgärdslänk**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="af9c7-165">I dialogrutan **åtgärdslänk** lägg till länktext, en länk-URL och en ARIA-etikett för länken och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="af9c7-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="af9c7-166">Spara sidan och förhandsgranska ändringarna.</span><span class="sxs-lookup"><span data-stu-id="af9c7-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="af9c7-167">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="af9c7-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="af9c7-168">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="af9c7-168">Additional resources</span></span>

[<span data-ttu-id="af9c7-169">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="af9c7-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="af9c7-170">Notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="af9c7-171">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="af9c7-172">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="af9c7-173">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="af9c7-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="af9c7-174">Funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="af9c7-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="af9c7-175">Videospelar-modul</span><span class="sxs-lookup"><span data-stu-id="af9c7-175">Video player module</span></span>](add-video-player.md)
