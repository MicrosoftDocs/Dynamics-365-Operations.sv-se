---
title: Textblockmodul
description: Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7dbeb8785641960cc2680335436aea10775759d3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797777"
---
# <a name="text-block-module"></a><span data-ttu-id="194c5-103">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="194c5-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="194c5-104">Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="194c5-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="194c5-105">En textblockmodul är en modul som används för att lägga till textinnehåll.</span><span class="sxs-lookup"><span data-stu-id="194c5-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="194c5-106">Det här innehållet kan vara information och reklam.</span><span class="sxs-lookup"><span data-stu-id="194c5-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="194c5-107">Textblockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="194c5-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="194c5-108">De är fristående moduler som inte är beroende av sidkontext eller andra moduler.</span><span class="sxs-lookup"><span data-stu-id="194c5-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="194c5-109">Exempel på innehållsrika textmoduler i näthandel</span><span class="sxs-lookup"><span data-stu-id="194c5-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="194c5-110">Innehållsrika textblockmoduler kan användas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="194c5-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="194c5-111">För att presentera produktfunktioner på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="194c5-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="194c5-112">För information på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="194c5-112">For informational purposes on any page.</span></span> <span data-ttu-id="194c5-113">De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.</span><span class="sxs-lookup"><span data-stu-id="194c5-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="194c5-114">Om du vill lägga till anpassade meddelanden på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="194c5-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="194c5-115">(t.ex. "gratis frakt för order över 50 $").</span><span class="sxs-lookup"><span data-stu-id="194c5-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="194c5-116">För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").</span><span class="sxs-lookup"><span data-stu-id="194c5-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="194c5-117">Följande bild visar ett exempel på en modul för textblock som används på en startsida.</span><span class="sxs-lookup"><span data-stu-id="194c5-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Exempel på en modul för textblock](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="194c5-119">Egenskaper för textblockmodul</span><span class="sxs-lookup"><span data-stu-id="194c5-119">Text block module properties</span></span>

| <span data-ttu-id="194c5-120">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="194c5-120">Property name</span></span>     | <span data-ttu-id="194c5-121">Värde</span><span class="sxs-lookup"><span data-stu-id="194c5-121">Value</span></span>                                            | <span data-ttu-id="194c5-122">beskrivning</span><span class="sxs-lookup"><span data-stu-id="194c5-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="194c5-123">RTF-format</span><span class="sxs-lookup"><span data-stu-id="194c5-123">Rich text</span></span>         | <span data-ttu-id="194c5-124">RTF-format</span><span class="sxs-lookup"><span data-stu-id="194c5-124">Rich text</span></span>                                        | <span data-ttu-id="194c5-125">Stycketext.</span><span class="sxs-lookup"><span data-stu-id="194c5-125">Paragraph text.</span></span> <span data-ttu-id="194c5-126">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text.</span><span class="sxs-lookup"><span data-stu-id="194c5-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="194c5-127">Anpassat klassnamn</span><span class="sxs-lookup"><span data-stu-id="194c5-127">Custom class name</span></span> | <span data-ttu-id="194c5-128">Ett klassnamn för Överlappande formatmallar (CSS)</span><span class="sxs-lookup"><span data-stu-id="194c5-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="194c5-129">Namnet på en anpassad CSS-klass som en utvecklare använder för att formatera modulen.</span><span class="sxs-lookup"><span data-stu-id="194c5-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="194c5-130">Klassnamnet måste definieras i temapaketet.</span><span class="sxs-lookup"><span data-stu-id="194c5-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="194c5-131">Teckenstorlek</span><span class="sxs-lookup"><span data-stu-id="194c5-131">Font size</span></span>         | <span data-ttu-id="194c5-132">**Small**, **Medium**, **Large** eller **X-Large**</span><span class="sxs-lookup"><span data-stu-id="194c5-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="194c5-133">Teckenstorleken för innehållet.</span><span class="sxs-lookup"><span data-stu-id="194c5-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="194c5-134">Lägg till en textblockmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="194c5-134">Add a text block module to a page</span></span>

<span data-ttu-id="194c5-135">Om du vill lägga till en textblockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="194c5-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="194c5-136">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="194c5-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="194c5-137">I dialogrutan **Ny mall** under **Mallnamn** anger du **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="194c5-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="194c5-138">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="194c5-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="194c5-139">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="194c5-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="194c5-140">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="194c5-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="194c5-141">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="194c5-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="194c5-142">I dialogrutan **Välj en mall** väljer du en **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="194c5-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="194c5-143">Under **sidnamn**, ange **Innehållssida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="194c5-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="194c5-144">I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="194c5-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="194c5-145">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="194c5-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="194c5-146">I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="194c5-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="194c5-147">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="194c5-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="194c5-148">I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="194c5-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="194c5-149">I egenskapsfönstret för textblockmodulen, lägg till text i fältet **RTF**.</span><span class="sxs-lookup"><span data-stu-id="194c5-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="194c5-150">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="194c5-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="194c5-151">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="194c5-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="194c5-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="194c5-152">Additional resources</span></span>

[<span data-ttu-id="194c5-153">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="194c5-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="194c5-154">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="194c5-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="194c5-155">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="194c5-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="194c5-156">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="194c5-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="194c5-157">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="194c5-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]