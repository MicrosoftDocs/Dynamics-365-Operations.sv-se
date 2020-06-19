---
title: Flikmodulen
description: Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.openlocfilehash: 60af9b74f7e647e83229e352a03c09d63d0c7902
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417379"
---
# <a name="tab-module"></a><span data-ttu-id="714fd-103">Flikmodulen</span><span class="sxs-lookup"><span data-stu-id="714fd-103">Tab module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="714fd-104">Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="714fd-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="714fd-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="714fd-105">Overview</span></span>

<span data-ttu-id="714fd-106">Flikmoduler är behållarmoduler som används för att ordna informationen på en webbplatssida på flikar.</span><span class="sxs-lookup"><span data-stu-id="714fd-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="714fd-107">De kan användas på alla sidor där information måste visas på flikar.</span><span class="sxs-lookup"><span data-stu-id="714fd-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="714fd-108">I alla flikmoduler kan du lägga till en eller flera flikartikelmoduler.</span><span class="sxs-lookup"><span data-stu-id="714fd-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="714fd-109">Varje flikartikelmodul representerar en enda flik. I varje modul kan en eller flera moduler läggas till.</span><span class="sxs-lookup"><span data-stu-id="714fd-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="714fd-110">Det finns inga begränsningar för vilka typer av moduler som kan läggas till i flikartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="714fd-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="714fd-111">Följande bild visar ett exempel på en flikmodul på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="714fd-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="714fd-112">I det här exemplet är fliken **leverans** vald.</span><span class="sxs-lookup"><span data-stu-id="714fd-112">In this example, the **Shipping** tab selected.</span></span>

![Exempel på en flikmodul](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="714fd-114">Flikmodulegenskaper</span><span class="sxs-lookup"><span data-stu-id="714fd-114">Tab module properties</span></span>

| <span data-ttu-id="714fd-115">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="714fd-115">Property name</span></span> | <span data-ttu-id="714fd-116">Värden</span><span class="sxs-lookup"><span data-stu-id="714fd-116">Values</span></span> | <span data-ttu-id="714fd-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="714fd-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="714fd-118">Rubrik</span><span class="sxs-lookup"><span data-stu-id="714fd-118">Heading</span></span> | <span data-ttu-id="714fd-119">Text</span><span class="sxs-lookup"><span data-stu-id="714fd-119">Text</span></span> | <span data-ttu-id="714fd-120">Den här egenskapen anger en valfri textrubrik för modulen.</span><span class="sxs-lookup"><span data-stu-id="714fd-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="714fd-121">Aktivt flikindex</span><span class="sxs-lookup"><span data-stu-id="714fd-121">Active Tab Index</span></span> | <span data-ttu-id="714fd-122">Antal</span><span class="sxs-lookup"><span data-stu-id="714fd-122">Number</span></span> | <span data-ttu-id="714fd-123">Den här egenskapen anger vilken flik som ska vara aktiv som standard när en sida läses in.</span><span class="sxs-lookup"><span data-stu-id="714fd-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="714fd-124">Om inget värde anges är det första objektet i den första fliken aktivt som standard.</span><span class="sxs-lookup"><span data-stu-id="714fd-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="714fd-125">Egenskaper för flikartikelmodul</span><span class="sxs-lookup"><span data-stu-id="714fd-125">Tab item module properties</span></span>

| <span data-ttu-id="714fd-126">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="714fd-126">Property name</span></span> | <span data-ttu-id="714fd-127">Värden</span><span class="sxs-lookup"><span data-stu-id="714fd-127">Values</span></span> | <span data-ttu-id="714fd-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="714fd-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="714fd-129">Befattning</span><span class="sxs-lookup"><span data-stu-id="714fd-129">Title</span></span> | <span data-ttu-id="714fd-130">Text</span><span class="sxs-lookup"><span data-stu-id="714fd-130">Text</span></span> | <span data-ttu-id="714fd-131">Den här egenskapen anger en rubriktext för flikartikelmodulen.</span><span class="sxs-lookup"><span data-stu-id="714fd-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="714fd-132">Lägg till en flikmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="714fd-132">Add a tab module to a page</span></span>

<span data-ttu-id="714fd-133">Om du vill lägga till en flikmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="714fd-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="714fd-134">Använd Fabrikam-marknadsföringsmallen (eller en mall utan begränsningar) om du vill skapa en ny sida med namnet **Sida för butikspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="714fd-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="714fd-135">I platsen **Huvud** i **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="714fd-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="714fd-136">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="714fd-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="714fd-137">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="714fd-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="714fd-138">I dialogrutan **Lägg till modul**, välj modulen **Flik** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="714fd-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="714fd-139">I egenskapsrutan i flikmodulen väljer du **rubrik** bredvid pennsymbolen.</span><span class="sxs-lookup"><span data-stu-id="714fd-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="714fd-140">I dialogrutan **Rubrik**, under **Rubriktext**, ange rubriktext (t.ex. **Policyer**).</span><span class="sxs-lookup"><span data-stu-id="714fd-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="714fd-141">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="714fd-141">Then select **OK**.</span></span>
1. <span data-ttu-id="714fd-142">I facket **Flik** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="714fd-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="714fd-143">I dialogrutan **Lägg till modul** välj modulen **Flikartikel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="714fd-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="714fd-144">I egenskapsfönstret på flikartikelmodulen under **Rubrik**, ange rubriktext (till exempel **Leverans**).</span><span class="sxs-lookup"><span data-stu-id="714fd-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="714fd-145">I facket **Flikartikel** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="714fd-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="714fd-146">I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="714fd-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="714fd-147">I egenskapsfönstret för textblockmodulen under **RTF**, ange en paragraf med text.</span><span class="sxs-lookup"><span data-stu-id="714fd-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="714fd-148">På platsen **flik** lägger du till ytterligare flikartikelmoduler som har titlar.</span><span class="sxs-lookup"><span data-stu-id="714fd-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="714fd-149">Lägg till en textblockmodul som innehåller innehåll i varje flikartikelmodul.</span><span class="sxs-lookup"><span data-stu-id="714fd-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="714fd-150">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="714fd-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="714fd-151">På sidan visas en flik som innehåller flikartikelmoduler som har det innehåll du lagt till.</span><span class="sxs-lookup"><span data-stu-id="714fd-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="714fd-152">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="714fd-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="714fd-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="714fd-153">Additional resources</span></span>

[<span data-ttu-id="714fd-154">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="714fd-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="714fd-155">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="714fd-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="714fd-156">Dragspelsmodulen</span><span class="sxs-lookup"><span data-stu-id="714fd-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="714fd-157">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="714fd-157">Text block module</span></span>](add-content-rich-block.md)
