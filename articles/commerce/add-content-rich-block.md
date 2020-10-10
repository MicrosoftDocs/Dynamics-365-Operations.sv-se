---
title: Textblockmodul
description: Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817388"
---
# <a name="text-block-module"></a><span data-ttu-id="54b1f-103">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="54b1f-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="54b1f-104">Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="54b1f-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="54b1f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="54b1f-105">Overview</span></span>

<span data-ttu-id="54b1f-106">En textblockmodul är en modul som används för att lägga till textinnehåll.</span><span class="sxs-lookup"><span data-stu-id="54b1f-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="54b1f-107">Det här innehållet kan vara information och reklam.</span><span class="sxs-lookup"><span data-stu-id="54b1f-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="54b1f-108">Textblockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="54b1f-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="54b1f-109">De är fristående moduler som inte är beroende av sidkontext eller andra moduler.</span><span class="sxs-lookup"><span data-stu-id="54b1f-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="54b1f-110">Exempel på innehållsrika textmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="54b1f-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="54b1f-111">Innehållsrika textblockmoduler kan användas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="54b1f-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="54b1f-112">För att presentera produktfunktioner på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="54b1f-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="54b1f-113">För information på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="54b1f-113">For informational purposes on any page.</span></span> <span data-ttu-id="54b1f-114">De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.</span><span class="sxs-lookup"><span data-stu-id="54b1f-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="54b1f-115">Om du vill lägga till anpassade meddelanden på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="54b1f-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="54b1f-116">(t.ex. "gratis frakt för order över 50 $").</span><span class="sxs-lookup"><span data-stu-id="54b1f-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="54b1f-117">För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").</span><span class="sxs-lookup"><span data-stu-id="54b1f-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="54b1f-118">Följande bild visar ett exempel på en modul för textblock som används på en startsida.</span><span class="sxs-lookup"><span data-stu-id="54b1f-118">The following image shows an example of a text block module that is used on a home page.</span></span>

![Exempel på en modul för textblock](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="54b1f-120">Egenskaper för textblockmodul</span><span class="sxs-lookup"><span data-stu-id="54b1f-120">Text block module properties</span></span>

| <span data-ttu-id="54b1f-121">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="54b1f-121">Property name</span></span>     | <span data-ttu-id="54b1f-122">Värde</span><span class="sxs-lookup"><span data-stu-id="54b1f-122">Value</span></span>                                            | <span data-ttu-id="54b1f-123">beskrivning</span><span class="sxs-lookup"><span data-stu-id="54b1f-123">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="54b1f-124">RTF-format</span><span class="sxs-lookup"><span data-stu-id="54b1f-124">Rich text</span></span>         | <span data-ttu-id="54b1f-125">RTF-format</span><span class="sxs-lookup"><span data-stu-id="54b1f-125">Rich text</span></span>                                        | <span data-ttu-id="54b1f-126">Stycketext.</span><span class="sxs-lookup"><span data-stu-id="54b1f-126">Paragraph text.</span></span> <span data-ttu-id="54b1f-127">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text.</span><span class="sxs-lookup"><span data-stu-id="54b1f-127">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="54b1f-128">Anpassat klassnamn</span><span class="sxs-lookup"><span data-stu-id="54b1f-128">Custom class name</span></span> | <span data-ttu-id="54b1f-129">Ett klassnamn för Överlappande formatmallar (CSS)</span><span class="sxs-lookup"><span data-stu-id="54b1f-129">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="54b1f-130">Namnet på en anpassad CSS-klass som en utvecklare använder för att formatera modulen.</span><span class="sxs-lookup"><span data-stu-id="54b1f-130">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="54b1f-131">Klassnamnet måste definieras i temapaketet.</span><span class="sxs-lookup"><span data-stu-id="54b1f-131">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="54b1f-132">Teckenstorlek</span><span class="sxs-lookup"><span data-stu-id="54b1f-132">Font size</span></span>         | <span data-ttu-id="54b1f-133">**Small**, **Medium**, **Large** eller **X-Large**</span><span class="sxs-lookup"><span data-stu-id="54b1f-133">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="54b1f-134">Teckenstorleken för innehållet.</span><span class="sxs-lookup"><span data-stu-id="54b1f-134">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="54b1f-135">Lägg till en textblockmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="54b1f-135">Add a text block module to a page</span></span>

<span data-ttu-id="54b1f-136">Om du vill lägga till en textblockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="54b1f-136">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="54b1f-137">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="54b1f-137">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="54b1f-138">I dialogrutan **Ny mall** under **Mallnamn** anger du **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-138">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="54b1f-139">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-139">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54b1f-140">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-140">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="54b1f-141">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="54b1f-141">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="54b1f-142">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="54b1f-142">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="54b1f-143">I dialogrutan **Välj en mall** väljer du en **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-143">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="54b1f-144">Under **sidnamn**, ange **Innehållssida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-144">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="54b1f-145">I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-145">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54b1f-146">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-146">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="54b1f-147">I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-147">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="54b1f-148">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-148">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54b1f-149">I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-149">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="54b1f-150">I egenskapsfönstret för textblockmodulen, lägg till text i fältet **RTF**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-150">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="54b1f-151">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="54b1f-151">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="54b1f-152">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="54b1f-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54b1f-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="54b1f-153">Additional resources</span></span>

[<span data-ttu-id="54b1f-154">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="54b1f-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="54b1f-155">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="54b1f-155">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="54b1f-156">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="54b1f-156">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="54b1f-157">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="54b1f-157">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="54b1f-158">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="54b1f-158">Video player module</span></span>](add-video-player.md)

