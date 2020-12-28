---
title: Innehållsblockmodul
description: Det här avsnittet handlar om innehållsblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 7a8b1c214ba31b7c47cecbe67bef493f5fa450fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415770"
---
# <a name="content-block-module"></a><span data-ttu-id="9b94a-103">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="9b94a-103">Content block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9b94a-104">Det här avsnittet handlar om innehållsblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9b94a-104">This topic covers content block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9b94a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="9b94a-105">Overview</span></span>

<span data-ttu-id="9b94a-106">En innehållsblockmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text.</span><span class="sxs-lookup"><span data-stu-id="9b94a-106">A content block module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="9b94a-107">En återförsäljare kan till exempel lägga till en innehållsblockmodul på startsidan för en näthandelsplats för att marknadsföra en ny produkt och locka kundernas uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="9b94a-107">For example, a retailer can add a content block module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="9b94a-108">En innehållsblockmodul drivs av data från innehållshanteringssystemet (CMS).</span><span class="sxs-lookup"><span data-stu-id="9b94a-108">A content block module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="9b94a-109">Det är en fristående modul som inte är beroende av andra moduler på sidan.</span><span class="sxs-lookup"><span data-stu-id="9b94a-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="9b94a-110">En innehållsblockmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).</span><span class="sxs-lookup"><span data-stu-id="9b94a-110">A content block module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-content-block-module-in-e-commerce"></a><span data-ttu-id="9b94a-111">Exempel på innehållsblockmoduler i näthandel</span><span class="sxs-lookup"><span data-stu-id="9b94a-111">Examples of content block module in e-Commerce</span></span>

- <span data-ttu-id="9b94a-112">En innehållsblockmodul kan användas på startsidan för en näthandelsplats för att framhäva erbjudanden och nya produkter.</span><span class="sxs-lookup"><span data-stu-id="9b94a-112">A content block module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="9b94a-113">En innehållsblockmodul kan användas på en produktinformationssida för att visa upp produktinformation.</span><span class="sxs-lookup"><span data-stu-id="9b94a-113">A content block module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="9b94a-114">Flera innehållsblockmoduler kan placeras i en karusellmodul för att framhäva flera produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="9b94a-114">Multiple content block modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="content-block-modules-and-themes"></a><span data-ttu-id="9b94a-115">Innehållsblockmoduler och teman</span><span class="sxs-lookup"><span data-stu-id="9b94a-115">Content block modules and themes</span></span>

<span data-ttu-id="9b94a-116">Innehållsblockmoduler kan stödja olika layouter och stilar som baseras på ett tema.</span><span class="sxs-lookup"><span data-stu-id="9b94a-116">Content block modules can support various layouts and styles based on a theme.</span></span> <span data-ttu-id="9b94a-117">Temat Fabrikam har till exempel stöd för tre layoutändringar för en innehållsblockmodul: fokus, funktion och panel.</span><span class="sxs-lookup"><span data-stu-id="9b94a-117">For example, the Fabrikam theme supports three layout variations of a content block module: hero, feature, and tile.</span></span> <span data-ttu-id="9b94a-118">I fokuslayouten visas en bild på bakgrunden med textöverlägg.</span><span class="sxs-lookup"><span data-stu-id="9b94a-118">The hero layout shows an image on the background with text overlay.</span></span> <span data-ttu-id="9b94a-119">I funktionslayouten visas en bild och text sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="9b94a-119">The feature layout shows an image and text side by side.</span></span> <span data-ttu-id="9b94a-120">Med hjälp av panellayouten kan du använda flera innehållsblock i ett panelformat.</span><span class="sxs-lookup"><span data-stu-id="9b94a-120">The tile layout allows multiple content blocks in a tile format.</span></span>

<span data-ttu-id="9b94a-121">Dessutom kan temat visa olika egenskaper för varje layout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-121">In addition, the theme can expose different properties for each layout.</span></span> <span data-ttu-id="9b94a-122">En temautvecklare kan bygga fler layouter med fler stilar med hjälp av innehållsblockmodulen.</span><span class="sxs-lookup"><span data-stu-id="9b94a-122">A theme developer can build more layouts with more styles using the content block module.</span></span>

<span data-ttu-id="9b94a-123">Följande bild visar ett exempel på en innehållsblockmodul med en fokuslayout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-123">The following image shows an example of a content block module with a hero layout.</span></span>

![Exempel på en fokusmodul](./media/Hero.PNG)

<span data-ttu-id="9b94a-125">Följande bild visar ett exempel på en innehållsblockmodul med en funktionslayout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-125">The following image shows an example of a content block module with a feature layout.</span></span>

![Exempel på funktionsmoduler](./media/Feature.PNG)

## <a name="content-block-module-properties"></a><span data-ttu-id="9b94a-127">Egenskaper för innehållsblockmoduler</span><span class="sxs-lookup"><span data-stu-id="9b94a-127">Content block module properties</span></span>

| <span data-ttu-id="9b94a-128">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="9b94a-128">Property name</span></span>  | <span data-ttu-id="9b94a-129">Värden</span><span class="sxs-lookup"><span data-stu-id="9b94a-129">Values</span></span> | <span data-ttu-id="9b94a-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b94a-130">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="9b94a-131">Bild</span><span class="sxs-lookup"><span data-stu-id="9b94a-131">Image</span></span>          | <span data-ttu-id="9b94a-132">Bildfil</span><span class="sxs-lookup"><span data-stu-id="9b94a-132">Image file</span></span> | <span data-ttu-id="9b94a-133">En bild kan användas för att presentera en produkt eller ett erbjudande.</span><span class="sxs-lookup"><span data-stu-id="9b94a-133">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="9b94a-134">En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas.</span><span class="sxs-lookup"><span data-stu-id="9b94a-134">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="9b94a-135">Rubrik</span><span class="sxs-lookup"><span data-stu-id="9b94a-135">Heading</span></span>        | <span data-ttu-id="9b94a-136">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="9b94a-136">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="9b94a-137">Varje fokusmodul kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="9b94a-137">Every hero module can have a heading.</span></span> <span data-ttu-id="9b94a-138">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="9b94a-138">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="9b94a-139">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="9b94a-139">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="9b94a-140">Stycke</span><span class="sxs-lookup"><span data-stu-id="9b94a-140">Paragraph</span></span>      | <span data-ttu-id="9b94a-141">Stycketext</span><span class="sxs-lookup"><span data-stu-id="9b94a-141">Paragraph text</span></span> | <span data-ttu-id="9b94a-142">Fokusmoduler har stöd för stycketext i RTF-format.</span><span class="sxs-lookup"><span data-stu-id="9b94a-142">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="9b94a-143">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar.</span><span class="sxs-lookup"><span data-stu-id="9b94a-143">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="9b94a-144">Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen.</span><span class="sxs-lookup"><span data-stu-id="9b94a-144">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="9b94a-145">Länka</span><span class="sxs-lookup"><span data-stu-id="9b94a-145">Link</span></span>           | <span data-ttu-id="9b94a-146">Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik**</span><span class="sxs-lookup"><span data-stu-id="9b94a-146">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="9b94a-147">Fokusmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar.</span><span class="sxs-lookup"><span data-stu-id="9b94a-147">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="9b94a-148">Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs.</span><span class="sxs-lookup"><span data-stu-id="9b94a-148">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="9b94a-149">ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="9b94a-149">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="9b94a-150">Länkar kan konfigureras så att de öppnas på en ny flik.</span><span class="sxs-lookup"><span data-stu-id="9b94a-150">Links can be configured so that they are opened on a new tab.</span></span> |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a><span data-ttu-id="9b94a-151">Egenskaper för innehållsblockmoduler som visas av Fabrikam-temat</span><span class="sxs-lookup"><span data-stu-id="9b94a-151">Content block module properties exposed by the Fabrikam theme</span></span> 

| <span data-ttu-id="9b94a-152">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="9b94a-152">Property name</span></span>  | <span data-ttu-id="9b94a-153">Värden</span><span class="sxs-lookup"><span data-stu-id="9b94a-153">Values</span></span> | <span data-ttu-id="9b94a-154">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b94a-154">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="9b94a-155">Textplacering</span><span class="sxs-lookup"><span data-stu-id="9b94a-155">Text placement</span></span> | <span data-ttu-id="9b94a-156">**Vänster**, **Höger**, **Centrera**</span><span class="sxs-lookup"><span data-stu-id="9b94a-156">**Left**, **Right**, **Center**</span></span> | <span data-ttu-id="9b94a-157">Den här egenskapen definierar placeringen av texten på bilden.</span><span class="sxs-lookup"><span data-stu-id="9b94a-157">This property defines the position of the text on the image.</span></span> <span data-ttu-id="9b94a-158">Det gäller endast fokuslayout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-158">It only applies to the hero layout.</span></span> |
| <span data-ttu-id="9b94a-159">Texttema</span><span class="sxs-lookup"><span data-stu-id="9b94a-159">Text theme</span></span>     | <span data-ttu-id="9b94a-160">**Ljus** eller **Mörk**</span><span class="sxs-lookup"><span data-stu-id="9b94a-160">**Light** or **Dark**</span></span> | <span data-ttu-id="9b94a-161">Ett färgschema kan definieras för texten, baserat på bakgrundsbilden.</span><span class="sxs-lookup"><span data-stu-id="9b94a-161">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="9b94a-162">Om bilden t.ex. har en mörk bakgrund kan ett ljust tema användas för att göra texten mer synlig och för att uppfylla färg kontrastförhållandena för hjälpmedelssyfte.</span><span class="sxs-lookup"><span data-stu-id="9b94a-162">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> <span data-ttu-id="9b94a-163">Det gäller endast fokuslayout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-163">It only applies to the hero layout.</span></span>|
| <span data-ttu-id="9b94a-164">Bildplacering</span><span class="sxs-lookup"><span data-stu-id="9b94a-164">Image placement</span></span>       | <span data-ttu-id="9b94a-165">**Vänster**, **höger**</span><span class="sxs-lookup"><span data-stu-id="9b94a-165">**Left**,  **Right**</span></span> | <span data-ttu-id="9b94a-166">Den här egenskapen anger om bilden ska placeras till vänster eller till höger om texten.</span><span class="sxs-lookup"><span data-stu-id="9b94a-166">This property specifies if the image should be to the left or right of the text.</span></span> <span data-ttu-id="9b94a-167">Det gäller endast funktionslayout.</span><span class="sxs-lookup"><span data-stu-id="9b94a-167">It only applies to the feature layout.</span></span>  |

## <a name="add-a-content-block-module-to-a-new-page"></a><span data-ttu-id="9b94a-168">Lägg till en innehållsblockmodul till en ny sida</span><span class="sxs-lookup"><span data-stu-id="9b94a-168">Add a content block module to a new page</span></span>

<span data-ttu-id="9b94a-169">Om du vill lägga till en fokusmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9b94a-169">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="9b94a-170">Gå till **mallar** och skapa en sidmall med namnet **innehållsblockmall**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-170">Go to **Templates**, and create a page template that is named **Content block template**.</span></span>
1. <span data-ttu-id="9b94a-171">Lägg till platsen **Huvud** på standardsida, lägg till fokusmodul.</span><span class="sxs-lookup"><span data-stu-id="9b94a-171">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="9b94a-172">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="9b94a-172">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="9b94a-173">Använd den fokusmall som du just skapade för att skapa en sida med namnet **innehållsblocksida**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-173">Use the hero template that you just created to create a page that is named **Content block page**.</span></span>
1. <span data-ttu-id="9b94a-174">I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-174">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9b94a-175">I dialogrutan **Lägg till modul**, under **Välj moduler**, välj fokusmodul och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-175">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="9b94a-176">I dispositionsträdet till vänster väljer du innehållsblockmodulen.</span><span class="sxs-lookup"><span data-stu-id="9b94a-176">In the outline tree on the left, select the content block module.</span></span>
1. <span data-ttu-id="9b94a-177">I egenskapsrutan till höger, välj egenskapen **Lägg till en bild**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-177">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="9b94a-178">Välj antingen en befintlig bild eller överför en ny avbildning.</span><span class="sxs-lookup"><span data-stu-id="9b94a-178">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="9b94a-179">Välj **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-179">Select **Heading**.</span></span>
1. <span data-ttu-id="9b94a-180">I dialogrutan **rubrik** lägg till rubriktexten, välj rubrik nivå och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-180">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="9b94a-181">Under **oformaterad text** lägger du till text efter behov.</span><span class="sxs-lookup"><span data-stu-id="9b94a-181">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="9b94a-182">Välj **Markera länk**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-182">Select **Add Link**.</span></span>
1. <span data-ttu-id="9b94a-183">I dialogrutan **länk** lägg till länktext, en länk-URL och en ARIA-etikett för länken och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-183">In the **Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="9b94a-184">Välj layout **fokus**.</span><span class="sxs-lookup"><span data-stu-id="9b94a-184">Select the **Hero** layout.</span></span>
1. <span data-ttu-id="9b94a-185">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="9b94a-185">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="9b94a-186">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="9b94a-186">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="9b94a-187">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9b94a-187">Additional resources</span></span>

[<span data-ttu-id="9b94a-188">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="9b94a-188">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9b94a-189">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="9b94a-189">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="9b94a-190">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="9b94a-190">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="9b94a-191">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="9b94a-191">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="9b94a-192">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="9b94a-192">Video player module</span></span>](add-video-player.md)
