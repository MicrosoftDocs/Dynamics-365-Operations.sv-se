---
title: Annonsbanderollmodul
description: Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a77196be69bb71d917bf84c633199a3af3fbf478
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986039"
---
# <a name="promo-banner-module"></a><span data-ttu-id="69105-103">Annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="69105-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="69105-104">Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69105-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="69105-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="69105-105">Overview</span></span>

<span data-ttu-id="69105-106">Annonsbanderollmoduler används för att visa infogade informationsmeddelanden på en sida.</span><span class="sxs-lookup"><span data-stu-id="69105-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="69105-107">De kan användas för att visa erbjudanden på hela webbplatsen som visas på alla sidor på en näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="69105-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="69105-108">I annonsbanderollmoduler kan du använda textmeddelanden och länkar.</span><span class="sxs-lookup"><span data-stu-id="69105-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="69105-109">Om flera meddelanden läggs till i en annonsbanderollmodul blir det en roterande karusellbanderoll som gör det möjligt för kunder att gå igenom alla meddelanden.</span><span class="sxs-lookup"><span data-stu-id="69105-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="69105-110">Annonsbanderollmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="69105-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="69105-111">Exempel på annonsbanderoller i näthandel</span><span class="sxs-lookup"><span data-stu-id="69105-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="69105-112">Annonsbanderoller kan användas i webbplatshuvudet för att visa erbjudanden som rör hela webbplatsen, som i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="69105-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="69105-113">"Årlig rea slutar om 10 dagar"</span><span class="sxs-lookup"><span data-stu-id="69105-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="69105-114">"Spara stort med tillbaka till skolan-rea.</span><span class="sxs-lookup"><span data-stu-id="69105-114">"Save big with back to school sale.</span></span> <span data-ttu-id="69105-115">Handla nu."</span><span class="sxs-lookup"><span data-stu-id="69105-115">Shop Now."</span></span>

<span data-ttu-id="69105-116">"Shoppa på Thanksgiving-rea!"</span><span class="sxs-lookup"><span data-stu-id="69105-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="69105-117">Följande bild visar ett exempel på en annonsbanderoll.</span><span class="sxs-lookup"><span data-stu-id="69105-117">The following image shows an example of a promo banner.</span></span>

![Exempel på en annonsbannermodul](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="69105-119">Egenskaper för annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="69105-119">Promo banner module properties</span></span>

| <span data-ttu-id="69105-120">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="69105-120">Property name</span></span>             | <span data-ttu-id="69105-121">Värde</span><span class="sxs-lookup"><span data-stu-id="69105-121">Value</span></span>                              | <span data-ttu-id="69105-122">beskrivning</span><span class="sxs-lookup"><span data-stu-id="69105-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="69105-123">Banderollmeddelanden</span><span class="sxs-lookup"><span data-stu-id="69105-123">Banner messages</span></span>           | <span data-ttu-id="69105-124">Text och länkar</span><span class="sxs-lookup"><span data-stu-id="69105-124">Text and links</span></span>                     | <span data-ttu-id="69105-125">En matris med text och länkar.</span><span class="sxs-lookup"><span data-stu-id="69105-125">An array of text and links.</span></span> |
| <span data-ttu-id="69105-126">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="69105-126">Autoplay</span></span>                  | <span data-ttu-id="69105-127">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="69105-127">**True** or **False**</span></span>              | <span data-ttu-id="69105-128">Ett värde som anger om meddelanden markeras automatiskt genom, om flera meddelanden har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="69105-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="69105-129">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="69105-129">Slide transition interval</span></span> | <span data-ttu-id="69105-130">Ett antal millisekunder (MS)</span><span class="sxs-lookup"><span data-stu-id="69105-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="69105-131">Det intervall som används för att flytta mellan meddelanden.</span><span class="sxs-lookup"><span data-stu-id="69105-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="69105-132">Tillåt avstängning</span><span class="sxs-lookup"><span data-stu-id="69105-132">Allow dismiss</span></span>             | <span data-ttu-id="69105-133">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="69105-133">**True** or **False**</span></span>              | <span data-ttu-id="69105-134">Om värdet är inställt på **Sant** kan kunder stänga notifieringen.</span><span class="sxs-lookup"><span data-stu-id="69105-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="69105-135">Visa ikonen karusell</span><span class="sxs-lookup"><span data-stu-id="69105-135">Show carousel flipper</span></span>     | <span data-ttu-id="69105-136">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="69105-136">**True** or **False**</span></span>              | <span data-ttu-id="69105-137">Ett värde som anger om karusell-ikoner ska visas, så att kunder manuellt kan gå igenom flera olika banderollobjekt.</span><span class="sxs-lookup"><span data-stu-id="69105-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="69105-138">Textjustering</span><span class="sxs-lookup"><span data-stu-id="69105-138">Text alignment</span></span>            | <span data-ttu-id="69105-139">**Höger**, **Vänster** eller **Centrera**</span><span class="sxs-lookup"><span data-stu-id="69105-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="69105-140">Textjusteringen i annonsbanderollmodulen.</span><span class="sxs-lookup"><span data-stu-id="69105-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="69105-141">Länka</span><span class="sxs-lookup"><span data-stu-id="69105-141">Link</span></span>                      | <span data-ttu-id="69105-142">En URL</span><span class="sxs-lookup"><span data-stu-id="69105-142">A URL</span></span>                              | <span data-ttu-id="69105-143">URL:en för en valfri länk.</span><span class="sxs-lookup"><span data-stu-id="69105-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="69105-144">Lägg till annonsbanderollmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="69105-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="69105-145">Om du vill lägga till en annonsbanderollmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="69105-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="69105-146">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="69105-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="69105-147">I dialogrutan **Ny mal** under **Mallnamn**, ange **annonsbanderollmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="69105-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="69105-148">Under **Siddisposition**, lägg till en **Standardsida** i facket **Brödtext**.</span><span class="sxs-lookup"><span data-stu-id="69105-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="69105-149">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="69105-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="69105-150">Använd den mall som du just skapade för att skapa en sida med namnet **sida för annonsbanderoll**.</span><span class="sxs-lookup"><span data-stu-id="69105-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="69105-151">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="69105-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="69105-152">I fönstret till höger, ange värdet **Bredd** till **Fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="69105-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="69105-153">Under **Siddisposition**, lägg till en annonsbanderollmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="69105-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="69105-154">Lägg till ett eller flera banderollmeddelanden i inställningarna för banderollmodulen.</span><span class="sxs-lookup"><span data-stu-id="69105-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="69105-155">Varje meddelande kan ha text tillsammans med en länk.</span><span class="sxs-lookup"><span data-stu-id="69105-155">Each message can have text together with a link.</span></span> <span data-ttu-id="69105-156">Du kan redigera de andra egenskaperna om du vill anpassa modulen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="69105-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="69105-157">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="69105-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="69105-158">Högst upp på sidan ska du se en notifiering med den tillagda texten.</span><span class="sxs-lookup"><span data-stu-id="69105-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="69105-159">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="69105-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="69105-160">En annonsbanderoll används vanligtvis i sidhuvud- eller underrubrikfacket.</span><span class="sxs-lookup"><span data-stu-id="69105-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="69105-161">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="69105-161">Additional resources</span></span>

[<span data-ttu-id="69105-162">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="69105-162">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="69105-163">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="69105-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="69105-164">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="69105-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="69105-165">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="69105-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="69105-166">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="69105-166">Video player module</span></span>](add-video-player.md)
