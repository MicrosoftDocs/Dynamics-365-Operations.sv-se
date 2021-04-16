---
title: Annonsbanderollmodul
description: Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: be3cc9729b58fce9ebc9885d8cb20b63114362a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796256"
---
# <a name="promo-banner-module"></a><span data-ttu-id="93baf-103">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="93baf-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="93baf-104">Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93baf-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="93baf-105">Annonsbanderollmoduler används för att visa infogade informationsmeddelanden på en sida.</span><span class="sxs-lookup"><span data-stu-id="93baf-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="93baf-106">De kan användas för att visa erbjudanden på hela webbplatsen som visas på alla sidor på en näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="93baf-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="93baf-107">I annonsbanderollmoduler kan du använda textmeddelanden och länkar.</span><span class="sxs-lookup"><span data-stu-id="93baf-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="93baf-108">Om flera meddelanden läggs till i en annonsbanderollmodul blir det en roterande karusellbanderoll som gör det möjligt för kunder att gå igenom alla meddelanden.</span><span class="sxs-lookup"><span data-stu-id="93baf-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="93baf-109">Annonsbanderollmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="93baf-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="93baf-110">Exempel på annonsbanderoller i näthandel</span><span class="sxs-lookup"><span data-stu-id="93baf-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="93baf-111">Annonsbanderoller kan användas i webbplatshuvudet för att visa erbjudanden som rör hela webbplatsen, som i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="93baf-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="93baf-112">"Årlig rea slutar om 10 dagar"</span><span class="sxs-lookup"><span data-stu-id="93baf-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="93baf-113">"Spara stort med tillbaka till skolan-rea.</span><span class="sxs-lookup"><span data-stu-id="93baf-113">"Save big with back to school sale.</span></span> <span data-ttu-id="93baf-114">Handla nu."</span><span class="sxs-lookup"><span data-stu-id="93baf-114">Shop Now."</span></span>

<span data-ttu-id="93baf-115">"Shoppa på Thanksgiving-rea!"</span><span class="sxs-lookup"><span data-stu-id="93baf-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="93baf-116">Följande bild visar ett exempel på en annonsbanderoll.</span><span class="sxs-lookup"><span data-stu-id="93baf-116">The following image shows an example of a promo banner.</span></span>

![Exempel på en annonsbannermodul](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="93baf-118">Egenskaper för annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="93baf-118">Promo banner module properties</span></span>

| <span data-ttu-id="93baf-119">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="93baf-119">Property name</span></span>             | <span data-ttu-id="93baf-120">Värde</span><span class="sxs-lookup"><span data-stu-id="93baf-120">Value</span></span>                              | <span data-ttu-id="93baf-121">beskrivning</span><span class="sxs-lookup"><span data-stu-id="93baf-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="93baf-122">Banderollmeddelanden</span><span class="sxs-lookup"><span data-stu-id="93baf-122">Banner messages</span></span>           | <span data-ttu-id="93baf-123">Text och länkar</span><span class="sxs-lookup"><span data-stu-id="93baf-123">Text and links</span></span>                     | <span data-ttu-id="93baf-124">En matris med text och länkar.</span><span class="sxs-lookup"><span data-stu-id="93baf-124">An array of text and links.</span></span> |
| <span data-ttu-id="93baf-125">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="93baf-125">Autoplay</span></span>                  | <span data-ttu-id="93baf-126">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="93baf-126">**True** or **False**</span></span>              | <span data-ttu-id="93baf-127">Ett värde som anger om meddelanden markeras automatiskt genom, om flera meddelanden har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="93baf-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="93baf-128">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="93baf-128">Slide transition interval</span></span> | <span data-ttu-id="93baf-129">Ett antal millisekunder (MS)</span><span class="sxs-lookup"><span data-stu-id="93baf-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="93baf-130">Det intervall som används för att flytta mellan meddelanden.</span><span class="sxs-lookup"><span data-stu-id="93baf-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="93baf-131">Tillåt avstängning</span><span class="sxs-lookup"><span data-stu-id="93baf-131">Allow dismiss</span></span>             | <span data-ttu-id="93baf-132">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="93baf-132">**True** or **False**</span></span>              | <span data-ttu-id="93baf-133">Om värdet är inställt på **Sant** kan kunder stänga notifieringen.</span><span class="sxs-lookup"><span data-stu-id="93baf-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="93baf-134">Visa ikonen karusell</span><span class="sxs-lookup"><span data-stu-id="93baf-134">Show carousel flipper</span></span>     | <span data-ttu-id="93baf-135">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="93baf-135">**True** or **False**</span></span>              | <span data-ttu-id="93baf-136">Ett värde som anger om karusell-ikoner ska visas, så att kunder manuellt kan gå igenom flera olika banderollobjekt.</span><span class="sxs-lookup"><span data-stu-id="93baf-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="93baf-137">Textjustering</span><span class="sxs-lookup"><span data-stu-id="93baf-137">Text alignment</span></span>            | <span data-ttu-id="93baf-138">**Höger**, **Vänster** eller **Centrera**</span><span class="sxs-lookup"><span data-stu-id="93baf-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="93baf-139">Textjusteringen i annonsbanderollmodulen.</span><span class="sxs-lookup"><span data-stu-id="93baf-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="93baf-140">Länka</span><span class="sxs-lookup"><span data-stu-id="93baf-140">Link</span></span>                      | <span data-ttu-id="93baf-141">En URL</span><span class="sxs-lookup"><span data-stu-id="93baf-141">A URL</span></span>                              | <span data-ttu-id="93baf-142">URL:en för en valfri länk.</span><span class="sxs-lookup"><span data-stu-id="93baf-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="93baf-143">Lägg till annonsbanderollmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="93baf-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="93baf-144">Om du vill lägga till en annonsbanderollmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="93baf-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="93baf-145">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="93baf-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="93baf-146">I dialogrutan **Ny mal** under **Mallnamn**, ange **annonsbanderollmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="93baf-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="93baf-147">Under **Siddisposition**, lägg till en **Standardsida** i facket **Brödtext**.</span><span class="sxs-lookup"><span data-stu-id="93baf-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="93baf-148">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="93baf-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="93baf-149">Använd den mall som du just skapade för att skapa en sida med namnet **sida för annonsbanderoll**.</span><span class="sxs-lookup"><span data-stu-id="93baf-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="93baf-150">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="93baf-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="93baf-151">I fönstret till höger, ange värdet **Bredd** till **Fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="93baf-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="93baf-152">Under **Siddisposition**, lägg till en annonsbanderollmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="93baf-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="93baf-153">Lägg till ett eller flera banderollmeddelanden i inställningarna för banderollmodulen.</span><span class="sxs-lookup"><span data-stu-id="93baf-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="93baf-154">Varje meddelande kan ha text tillsammans med en länk.</span><span class="sxs-lookup"><span data-stu-id="93baf-154">Each message can have text together with a link.</span></span> <span data-ttu-id="93baf-155">Du kan redigera de andra egenskaperna om du vill anpassa modulen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="93baf-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="93baf-156">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="93baf-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="93baf-157">Högst upp på sidan ska du se en notifiering med den tillagda texten.</span><span class="sxs-lookup"><span data-stu-id="93baf-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="93baf-158">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="93baf-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="93baf-159">En annonsbanderoll används vanligtvis i sidhuvud- eller underrubrikfacket.</span><span class="sxs-lookup"><span data-stu-id="93baf-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="93baf-160">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="93baf-160">Additional resources</span></span>

[<span data-ttu-id="93baf-161">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="93baf-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="93baf-162">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="93baf-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="93baf-163">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="93baf-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="93baf-164">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="93baf-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="93baf-165">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="93baf-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]