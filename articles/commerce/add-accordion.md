---
title: Dragspelsmodulen
description: Det här avsnittet handlar om dragspelsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2bb18539f610e5af05f8d9a20a0ba9f34db5c94f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415750"
---
# <a name="accordion-module"></a><span data-ttu-id="2b28f-103">Dragspelsmodulen</span><span class="sxs-lookup"><span data-stu-id="2b28f-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b28f-104">Det här avsnittet handlar om dragspelsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b28f-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2b28f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="2b28f-105">Overview</span></span>

<span data-ttu-id="2b28f-106">Dragspelsmoduler är sådana moduler som används för att organisera informationen eller modulerna på en sida genom att tillhandahålla en komprimerbar kassalådeliknande funktion.</span><span class="sxs-lookup"><span data-stu-id="2b28f-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="2b28f-107">En dragspelsmodul kan användas på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="2b28f-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="2b28f-108">Inne i alla dragspelsmoduler kan du lägga till en eller flera dragspelsartikelmoduler.</span><span class="sxs-lookup"><span data-stu-id="2b28f-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="2b28f-109">Varje dragspelsartikelmodul representerar en komprimerbar kassalåda.</span><span class="sxs-lookup"><span data-stu-id="2b28f-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="2b28f-110">Inne i alla dragspelsartikelmoduler kan du lägga till en eller flera moduler.</span><span class="sxs-lookup"><span data-stu-id="2b28f-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="2b28f-111">Det finns inga begränsningar för vilka typer av moduler som kan läggas till i dragspelsartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="2b28f-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="2b28f-112">Följande bild visar ett exempel på en dragspelsartikelmodul som används för att ordna information på en butikssida med vanliga frågor (FAQ).</span><span class="sxs-lookup"><span data-stu-id="2b28f-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Exempel på en dragspelsmodul](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="2b28f-114">Egenskaper för dragspelsmodul</span><span class="sxs-lookup"><span data-stu-id="2b28f-114">Accordion module properties</span></span>

| <span data-ttu-id="2b28f-115">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2b28f-115">Property name</span></span> | <span data-ttu-id="2b28f-116">Värden</span><span class="sxs-lookup"><span data-stu-id="2b28f-116">Values</span></span> | <span data-ttu-id="2b28f-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2b28f-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="2b28f-118">Rubrik</span><span class="sxs-lookup"><span data-stu-id="2b28f-118">Heading</span></span> | <span data-ttu-id="2b28f-119">Text</span><span class="sxs-lookup"><span data-stu-id="2b28f-119">Text</span></span> | <span data-ttu-id="2b28f-120">Den här egenskapen anger en valfri textrubrik för dragspelsmodul.</span><span class="sxs-lookup"><span data-stu-id="2b28f-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="2b28f-121">Expandera alla</span><span class="sxs-lookup"><span data-stu-id="2b28f-121">Expand All</span></span> | <span data-ttu-id="2b28f-122">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="2b28f-122">**True** or **False**</span></span> | <span data-ttu-id="2b28f-123">Om värdet är inställt på **True** är funktionen visa/dölj aktiverad, så att alla artiklar i dragspelsmodulen kan expanderas och komprimeras.</span><span class="sxs-lookup"><span data-stu-id="2b28f-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="2b28f-124">Interaktionsstil</span><span class="sxs-lookup"><span data-stu-id="2b28f-124">Interaction Style</span></span> | <span data-ttu-id="2b28f-125">**Oberoende** eller **expandera endast en artikel**</span><span class="sxs-lookup"><span data-stu-id="2b28f-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="2b28f-126">Den här egenskapen definierar interaktionstypen för dragspelsartiklar.</span><span class="sxs-lookup"><span data-stu-id="2b28f-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="2b28f-127">Om värdet är inställt på **oberoende** kan varje dragspelsartikel expanderas eller komprimeras separat.</span><span class="sxs-lookup"><span data-stu-id="2b28f-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="2b28f-128">Om värdet är inställt på att **expandera endast en artikel**, kan endast en artikel expanderas åt gången.</span><span class="sxs-lookup"><span data-stu-id="2b28f-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="2b28f-129">När artiklar expanderas, döljs tidigare expanderade artiklar.</span><span class="sxs-lookup"><span data-stu-id="2b28f-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="2b28f-130">Egenskaper för dragspelsartikelmodul</span><span class="sxs-lookup"><span data-stu-id="2b28f-130">Accordion item module properties</span></span>

| <span data-ttu-id="2b28f-131">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2b28f-131">Property name</span></span> | <span data-ttu-id="2b28f-132">Värden</span><span class="sxs-lookup"><span data-stu-id="2b28f-132">Values</span></span> | <span data-ttu-id="2b28f-133">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2b28f-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="2b28f-134">Befattning</span><span class="sxs-lookup"><span data-stu-id="2b28f-134">Title</span></span> | <span data-ttu-id="2b28f-135">Text</span><span class="sxs-lookup"><span data-stu-id="2b28f-135">Text</span></span> | <span data-ttu-id="2b28f-136">Den här egenskapen anger en rubriktext för dragspelsartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="2b28f-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="2b28f-137">Genom att välja rubrikområdet kan användarna utöka eller komprimera avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2b28f-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="2b28f-138">Expandera som standard</span><span class="sxs-lookup"><span data-stu-id="2b28f-138">Expand by default</span></span> | <span data-ttu-id="2b28f-139">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="2b28f-139">**True** or **False**</span></span> | <span data-ttu-id="2b28f-140">Om värdet är inställt på **True** expanderas dragspelsartikeln som standard när sidan läses in.</span><span class="sxs-lookup"><span data-stu-id="2b28f-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="2b28f-141">Lägg till dragspelsartikelmodul till en sida med vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="2b28f-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="2b28f-142">Om du vill lägga till en dragspelsmodul på en sida för vanliga frågor och ställa in egenskaperna i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2b28f-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="2b28f-143">Gå till **Sidor** och använd Fabrikam-marknadsföringsmallen (eller en mall utan begränsningar) om du vill skapa en ny sida med namnet **Vanliga frågor om butiken**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="2b28f-144">I platsen **Huvud** i **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2b28f-145">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2b28f-146">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2b28f-147">I dialogrutan **Lägg till modul**, välj modulen **Dragspel** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2b28f-148">I egenskapsrutan i dragspelsmodulen väljer du **rubrik** bredvid pennsymbolen.</span><span class="sxs-lookup"><span data-stu-id="2b28f-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="2b28f-149">I dialogrutan **Rubrik** under **Rubriktext**, ange **Vanliga frågor**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="2b28f-150">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-150">Then select **OK**.</span></span>
1. <span data-ttu-id="2b28f-151">Välj egenskapspanelen för dragspelsmodulen, markera kryssrutan **Visa expandera alla** och sedan i fältet **interaktionsstil** väljer du **oberoende**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="2b28f-152">I facket **dragspel** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2b28f-153">I dialogrutan **Lägg till modul** välj modulen **dragspelsartikel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2b28f-154">I egenskapsfönstret på dragspelsartikelmodulen under **Rubrik**, ange rubriktext (till exempel **Hur du returnerar arbete**).</span><span class="sxs-lookup"><span data-stu-id="2b28f-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="2b28f-155">I facket **dragspelsartikeln** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2b28f-156">I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b28f-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2b28f-157">Skriv ett textstycke i egenskapsfönstret för textblockmodulen (till exempel **returerna måste t.ex. ha bearbetats via kundtjänst. Kontakt 1-800-FABRIKAM för returer. Produkter har en policy på 30 dagar. Returer måste initieras inom denna tidsram.**).</span><span class="sxs-lookup"><span data-stu-id="2b28f-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="2b28f-158">På platsen **Dragspel**, lägg till fler dragspelsartikelmoduler.</span><span class="sxs-lookup"><span data-stu-id="2b28f-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="2b28f-159">Lägg till en textblockmodul som innehåller innehåll i varje dragspelsartikelmodul.</span><span class="sxs-lookup"><span data-stu-id="2b28f-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="2b28f-160">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="2b28f-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="2b28f-161">Sidan visar en dragspelsmodul som har det innehåll du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="2b28f-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="2b28f-162">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="2b28f-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b28f-163">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2b28f-163">Additional resources</span></span>

[<span data-ttu-id="2b28f-164">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="2b28f-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2b28f-165">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="2b28f-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2b28f-166">Flikmodul</span><span class="sxs-lookup"><span data-stu-id="2b28f-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="2b28f-167">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="2b28f-167">Text block module</span></span>](add-content-rich-block.md)
