---
title: Modul för videospelare
description: Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3cf7ead9a5340d5db37a87bdf131ba87681d5a82
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817071"
---
# <a name="video-player-module"></a><span data-ttu-id="73e69-103">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="73e69-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="73e69-104">Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73e69-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="73e69-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="73e69-105">Overview</span></span>

<span data-ttu-id="73e69-106">Modulen för videospelare används för att stödja videouppspelning.</span><span class="sxs-lookup"><span data-stu-id="73e69-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="73e69-107">Den kan läggas till på vilken sida som helst, förutsatt att videoinnehållet överförs till och är tillgängligt i innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="73e69-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="73e69-108">Videospelarmodulen stöder mediatypen. mp4.</span><span class="sxs-lookup"><span data-stu-id="73e69-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="73e69-109">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="73e69-109">Video player module</span></span>

<span data-ttu-id="73e69-110">Videospelaren kan användas för att visa videofilmer på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="73e69-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="73e69-111">Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge, ljudbeskrivningar och dold textning.</span><span class="sxs-lookup"><span data-stu-id="73e69-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="73e69-112">Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="73e69-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="73e69-113">Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.</span><span class="sxs-lookup"><span data-stu-id="73e69-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="73e69-114">Videospelarmodulen stöder också sekundära ljudspår.</span><span class="sxs-lookup"><span data-stu-id="73e69-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="73e69-115">När en video laddas upp till CMS kan även ett sekundärt ljudspår laddas upp.</span><span class="sxs-lookup"><span data-stu-id="73e69-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="73e69-116">Videospelarmodulen kan sedan spela upp det sekundära ljudspåret om en användare väljer det.</span><span class="sxs-lookup"><span data-stu-id="73e69-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="73e69-117">Exempel på moduler i videopelare i e-handel</span><span class="sxs-lookup"><span data-stu-id="73e69-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="73e69-118">Visa videoklipp på produktinformationssidor eller på marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="73e69-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="73e69-119">Reklamfilmer eller videoklipp om policyer på alla marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="73e69-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="73e69-120">Marknadsföringsvideor som markerar produktegenskaper på produktinformationssidor eller på marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="73e69-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

<span data-ttu-id="73e69-121">Följande bild visar ett exempel på en modul för videospelare på en startsida.</span><span class="sxs-lookup"><span data-stu-id="73e69-121">The following image shows an example of a video player module on a home page.</span></span>

![Exempel på en videospelar-modul](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a><span data-ttu-id="73e69-123">Egenskaper för videospelarmodul</span><span class="sxs-lookup"><span data-stu-id="73e69-123">Video player module properties</span></span>

| <span data-ttu-id="73e69-124">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="73e69-124">Property name</span></span>         | <span data-ttu-id="73e69-125">Värde</span><span class="sxs-lookup"><span data-stu-id="73e69-125">Value</span></span>                               | <span data-ttu-id="73e69-126">beskrivning</span><span class="sxs-lookup"><span data-stu-id="73e69-126">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="73e69-127">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="73e69-127">Auto play</span></span>             | <span data-ttu-id="73e69-128">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-128">**True** or **False**</span></span>               | <span data-ttu-id="73e69-129">När värdet är inställt på **Sant** spelas videon upp automatiskt.</span><span class="sxs-lookup"><span data-stu-id="73e69-129">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="73e69-130">Ljud av</span><span class="sxs-lookup"><span data-stu-id="73e69-130">Mute</span></span>                  | <span data-ttu-id="73e69-131">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-131">**True** or **False**</span></span>               | <span data-ttu-id="73e69-132">När värdet är inställt på **Sant** stängs ljudet av.</span><span class="sxs-lookup"><span data-stu-id="73e69-132">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="73e69-133">För den här spelaren är standardvärdet **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="73e69-133">For this player, the default value is **False**.</span></span> <span data-ttu-id="73e69-134">I webbläsaren Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt.</span><span class="sxs-lookup"><span data-stu-id="73e69-134">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="73e69-135">Slinga</span><span class="sxs-lookup"><span data-stu-id="73e69-135">Loop</span></span>                  | <span data-ttu-id="73e69-136">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-136">**True** or **False**</span></span>               | <span data-ttu-id="73e69-137">När värdet är inställt på **Sant** spelas videon upprepat i en slinga.</span><span class="sxs-lookup"><span data-stu-id="73e69-137">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="73e69-138">Medier</span><span class="sxs-lookup"><span data-stu-id="73e69-138">Media</span></span>                 | <span data-ttu-id="73e69-139">Videofilsökväg och namn.</span><span class="sxs-lookup"><span data-stu-id="73e69-139">Video file path and name</span></span> | <span data-ttu-id="73e69-140">Videofilen som spelas upp av videospelaren.</span><span class="sxs-lookup"><span data-stu-id="73e69-140">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="73e69-141">Spela upp på helskärm</span><span class="sxs-lookup"><span data-stu-id="73e69-141">Play fullscreen</span></span>       | <span data-ttu-id="73e69-142">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-142">**True** or **False**</span></span>               | <span data-ttu-id="73e69-143">När värdet är inställt på **Sant** spelas videon upp i helskärmsläge.</span><span class="sxs-lookup"><span data-stu-id="73e69-143">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="73e69-144">Utlösare för spela upp och pausa</span><span class="sxs-lookup"><span data-stu-id="73e69-144">Play pause trigger</span></span>    | <span data-ttu-id="73e69-145">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-145">**True** or **False**</span></span>               | <span data-ttu-id="73e69-146">När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon.</span><span class="sxs-lookup"><span data-stu-id="73e69-146">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="73e69-147">Kontroller för videospelare</span><span class="sxs-lookup"><span data-stu-id="73e69-147">Video player controls</span></span> | <span data-ttu-id="73e69-148">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-148">**True** or **False**</span></span>               | <span data-ttu-id="73e69-149">När värdet är inställt på **Sant** visas alla videospelarkontroller.</span><span class="sxs-lookup"><span data-stu-id="73e69-149">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="73e69-150">Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning.</span><span class="sxs-lookup"><span data-stu-id="73e69-150">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="73e69-151">Dölj affischbild</span><span class="sxs-lookup"><span data-stu-id="73e69-151">Hide poster image</span></span>     | <span data-ttu-id="73e69-152">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="73e69-152">**True** or **False**</span></span>               | <span data-ttu-id="73e69-153">Ett videoklipp kan ha en affischram.</span><span class="sxs-lookup"><span data-stu-id="73e69-153">A video can have a poster frame.</span></span> <span data-ttu-id="73e69-154">När värdet för den här egenskapen har angetts till **Sant**döljs affischramen.</span><span class="sxs-lookup"><span data-stu-id="73e69-154">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="73e69-155">Masknivå</span><span class="sxs-lookup"><span data-stu-id="73e69-155">Mask level</span></span>            | <span data-ttu-id="73e69-156">Ett nummer mellan **0** och **100**</span><span class="sxs-lookup"><span data-stu-id="73e69-156">A number from **0** through **100**</span></span> | <span data-ttu-id="73e69-157">Den mask som används på videon som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="73e69-157">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="73e69-158">Lägg till en videospelarmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="73e69-158">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="73e69-159">Innan du skapar en videospelarmodul måste du först överföra en video till mediebiblioteket.</span><span class="sxs-lookup"><span data-stu-id="73e69-159">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="73e69-160">Om du vill lägga till en modul för videospelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="73e69-160">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="73e69-161">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="73e69-161">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="73e69-162">I dialogrutan **Ny mal** under **Mallnamn**, ange **mall för videospelare** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-162">In the **New Template** dialog box, under **Template name**, enter **Video player template**, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-163">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="73e69-163">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73e69-164">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-164">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-165">I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="73e69-165">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73e69-166">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-166">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-167">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="73e69-167">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73e69-168">I dialogrutan **Lägg till modul**, välj modulen **Videospelare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-168">In the **Add Module** dialog box, select the **Video player** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-169">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="73e69-169">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="73e69-170">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="73e69-170">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="73e69-171">I dialogrutan **Välj en mall**, välj den videospelarmall du skapade.</span><span class="sxs-lookup"><span data-stu-id="73e69-171">In the **Choose a template** dialog box, select the video player template that you created.</span></span> <span data-ttu-id="73e69-172">Under **sidnamn**, ange **Videospelarsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-172">Under **Page name**, enter **Video player page**, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-173">I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="73e69-173">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73e69-174">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-174">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-175">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="73e69-175">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73e69-176">I dialogrutan **Lägg till modul**, välj modulen **Videospelare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-176">In the **Add Module** dialog box, select the **Video player** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-177">Välj **Lägg till en video** i egenskapsrutan för videospelarmodulen.</span><span class="sxs-lookup"><span data-stu-id="73e69-177">In the property pane of the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="73e69-178">I dialogrutan **medieväljare**, välj en video och välj sedan **Överför nytt mediobjekt**.</span><span class="sxs-lookup"><span data-stu-id="73e69-178">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="73e69-179">Markera en videofil i Utforskaren och välj sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="73e69-179">In File Explorer, select a video file, and then select **Open**.</span></span>
1. <span data-ttu-id="73e69-180">I dialogrutan **Överför medieartiklar** ange en rubrik och övrig information efter behov och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="73e69-180">In the **Upload Media Item** dialog box, enter a title and other information as needed, and then select **OK**.</span></span>
1. <span data-ttu-id="73e69-181">I dialogrutan **Mediaväljare**, välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="73e69-181">In the **Media Picker** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="73e69-182">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="73e69-182">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="73e69-183">Du bör se videomodulerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="73e69-183">You should see the video module on the page.</span></span> <span data-ttu-id="73e69-184">Du kan ändra ytterligare inställningar om du vill anpassa funktionen för modulen.</span><span class="sxs-lookup"><span data-stu-id="73e69-184">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="73e69-185">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="73e69-185">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="73e69-186">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="73e69-186">Additional resources</span></span>

[<span data-ttu-id="73e69-187">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="73e69-187">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="73e69-188">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="73e69-188">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="73e69-189">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="73e69-189">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="73e69-190">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="73e69-190">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="73e69-191">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="73e69-191">Content block module</span></span>](add-hero-module.md)
