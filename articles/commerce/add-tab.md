---
title: Flikmodulen
description: Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8375c33bd6ffd3004cfc9d7b686d9a0edc77cdef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209237"
---
# <a name="tab-module"></a><span data-ttu-id="8b5f3-103">Flikmodul</span><span class="sxs-lookup"><span data-stu-id="8b5f3-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8b5f3-104">Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8b5f3-105">Flikmoduler är behållarmoduler som används för att ordna informationen på en webbplatssida på flikar.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="8b5f3-106">De kan användas på alla sidor där information måste visas på flikar.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="8b5f3-107">I alla flikmoduler kan du lägga till en eller flera flikartikelmoduler.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="8b5f3-108">Varje flikartikelmodul representerar en enda flik. I varje modul kan en eller flera moduler läggas till.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="8b5f3-109">Det finns inga begränsningar för vilka typer av moduler som kan läggas till i flikartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="8b5f3-110">Följande bild visar ett exempel på en flikmodul på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="8b5f3-111">I det här exemplet är fliken **leverans** vald.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-111">In this example, the **Shipping** tab selected.</span></span>

![Exempel på en flikmodul](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="8b5f3-113">Flikmodulegenskaper</span><span class="sxs-lookup"><span data-stu-id="8b5f3-113">Tab module properties</span></span>

| <span data-ttu-id="8b5f3-114">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="8b5f3-114">Property name</span></span> | <span data-ttu-id="8b5f3-115">Värden</span><span class="sxs-lookup"><span data-stu-id="8b5f3-115">Values</span></span> | <span data-ttu-id="8b5f3-116">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b5f3-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="8b5f3-117">Rubrik</span><span class="sxs-lookup"><span data-stu-id="8b5f3-117">Heading</span></span> | <span data-ttu-id="8b5f3-118">Text</span><span class="sxs-lookup"><span data-stu-id="8b5f3-118">Text</span></span> | <span data-ttu-id="8b5f3-119">Den här egenskapen anger en valfri textrubrik för modulen.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="8b5f3-120">Aktivt flikindex</span><span class="sxs-lookup"><span data-stu-id="8b5f3-120">Active Tab Index</span></span> | <span data-ttu-id="8b5f3-121">Antal</span><span class="sxs-lookup"><span data-stu-id="8b5f3-121">Number</span></span> | <span data-ttu-id="8b5f3-122">Den här egenskapen anger vilken flik som ska vara aktiv som standard när en sida läses in.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="8b5f3-123">Om inget värde anges är det första objektet i den första fliken aktivt som standard.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="8b5f3-124">Egenskaper för flikartikelmodul</span><span class="sxs-lookup"><span data-stu-id="8b5f3-124">Tab item module properties</span></span>

| <span data-ttu-id="8b5f3-125">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="8b5f3-125">Property name</span></span> | <span data-ttu-id="8b5f3-126">Värden</span><span class="sxs-lookup"><span data-stu-id="8b5f3-126">Values</span></span> | <span data-ttu-id="8b5f3-127">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b5f3-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="8b5f3-128">Befattning</span><span class="sxs-lookup"><span data-stu-id="8b5f3-128">Title</span></span> | <span data-ttu-id="8b5f3-129">Text</span><span class="sxs-lookup"><span data-stu-id="8b5f3-129">Text</span></span> | <span data-ttu-id="8b5f3-130">Den här egenskapen anger en rubriktext för flikartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="8b5f3-131">Lägg till en flikmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="8b5f3-131">Add a tab module to a page</span></span>

<span data-ttu-id="8b5f3-132">Om du vill lägga till en flikmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="8b5f3-133">Använd Fabrikam-marknadsföringsmallen (eller en mall utan begränsningar) om du vill skapa en ny sida med namnet **Sida för butikspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="8b5f3-134">I platsen **Huvud** i **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b5f3-135">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b5f3-136">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b5f3-137">I dialogrutan **Lägg till modul**, välj modulen **Flik** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b5f3-138">I egenskapsrutan i flikmodulen väljer du **rubrik** bredvid pennsymbolen.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="8b5f3-139">I dialogrutan **Rubrik**, under **Rubriktext**, ange rubriktext (t.ex. **Policyer**).</span><span class="sxs-lookup"><span data-stu-id="8b5f3-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="8b5f3-140">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-140">Then select **OK**.</span></span>
1. <span data-ttu-id="8b5f3-141">I facket **Flik** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b5f3-142">I dialogrutan **Lägg till modul** välj modulen **Flikartikel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b5f3-143">I egenskapsfönstret på flikartikelmodulen under **Rubrik**, ange rubriktext (till exempel **Leverans**).</span><span class="sxs-lookup"><span data-stu-id="8b5f3-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="8b5f3-144">I facket **Flikartikel** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b5f3-145">I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b5f3-146">I egenskapsfönstret för textblockmodulen under **RTF**, ange en paragraf med text.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="8b5f3-147">På platsen **flik** lägger du till ytterligare flikartikelmoduler som har titlar.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="8b5f3-148">Lägg till en textblockmodul som innehåller innehåll i varje flikartikelmodul.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="8b5f3-149">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="8b5f3-150">På sidan visas en flik som innehåller flikartikelmoduler som har det innehåll du lagt till.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="8b5f3-151">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="8b5f3-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b5f3-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8b5f3-152">Additional resources</span></span>

[<span data-ttu-id="8b5f3-153">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="8b5f3-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8b5f3-154">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="8b5f3-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8b5f3-155">Dragspelsmodul</span><span class="sxs-lookup"><span data-stu-id="8b5f3-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="8b5f3-156">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="8b5f3-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]