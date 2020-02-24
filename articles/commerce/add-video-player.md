---
title: Modul för videospelare
description: Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025685"
---
# <a name="video-player-module"></a><span data-ttu-id="83520-103">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="83520-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="83520-104">Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="83520-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="83520-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="83520-105">Overview</span></span>

<span data-ttu-id="83520-106">Modulen för videospelare används för att stödja videouppspelning.</span><span class="sxs-lookup"><span data-stu-id="83520-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="83520-107">Den kan läggas till på vilken sida som helst, förutsatt att videoinnehållet överförs till och är tillgängligt i innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="83520-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="83520-108">Videospelarmodulen stöder mediatypen. mp4.</span><span class="sxs-lookup"><span data-stu-id="83520-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="83520-109">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="83520-109">Video player module</span></span>

<span data-ttu-id="83520-110">Videospelaren kan användas för att visa videofilmer på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="83520-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="83520-111">Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge, ljudbeskrivningar och dold textning.</span><span class="sxs-lookup"><span data-stu-id="83520-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="83520-112">Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="83520-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="83520-113">Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.</span><span class="sxs-lookup"><span data-stu-id="83520-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="83520-114">Videospelarmodulen stöder också sekundära ljudspår.</span><span class="sxs-lookup"><span data-stu-id="83520-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="83520-115">När en video laddas upp till CMS kan även ett sekundärt ljudspår laddas upp.</span><span class="sxs-lookup"><span data-stu-id="83520-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="83520-116">Videospelarmodulen kan sedan spela upp det sekundära ljudspåret om en användare väljer det.</span><span class="sxs-lookup"><span data-stu-id="83520-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="83520-117">Exempel på moduler i videopelare i e-handel</span><span class="sxs-lookup"><span data-stu-id="83520-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="83520-118">Visa videoklipp på produktinformationssidor eller på marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="83520-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="83520-119">Reklamfilmer eller videoklipp om policyer på alla marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="83520-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="83520-120">Marknadsföringsvideor som markerar produktegenskaper på produktinformationssidor eller på marknadsföringssidor</span><span class="sxs-lookup"><span data-stu-id="83520-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="83520-121">Egenskaper för videospelarmodul</span><span class="sxs-lookup"><span data-stu-id="83520-121">Video player module properties</span></span>

| <span data-ttu-id="83520-122">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="83520-122">Property name</span></span>         | <span data-ttu-id="83520-123">Värde</span><span class="sxs-lookup"><span data-stu-id="83520-123">Value</span></span>                               | <span data-ttu-id="83520-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="83520-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="83520-125">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="83520-125">Auto play</span></span>             | <span data-ttu-id="83520-126">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-126">**True** or **False**</span></span>               | <span data-ttu-id="83520-127">När värdet är inställt på **Sant** spelas videon upp automatiskt.</span><span class="sxs-lookup"><span data-stu-id="83520-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="83520-128">Ljud av</span><span class="sxs-lookup"><span data-stu-id="83520-128">Mute</span></span>                  | <span data-ttu-id="83520-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-129">**True** or **False**</span></span>               | <span data-ttu-id="83520-130">När värdet är inställt på **Sant** stängs ljudet av.</span><span class="sxs-lookup"><span data-stu-id="83520-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="83520-131">För den här spelaren är standardvärdet **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="83520-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="83520-132">I webbläsaren Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt.</span><span class="sxs-lookup"><span data-stu-id="83520-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="83520-133">Slinga</span><span class="sxs-lookup"><span data-stu-id="83520-133">Loop</span></span>                  | <span data-ttu-id="83520-134">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-134">**True** or **False**</span></span>               | <span data-ttu-id="83520-135">När värdet är inställt på **Sant** spelas videon upprepat i en slinga.</span><span class="sxs-lookup"><span data-stu-id="83520-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="83520-136">Medier</span><span class="sxs-lookup"><span data-stu-id="83520-136">Media</span></span>                 | <span data-ttu-id="83520-137">Videofilsökväg och namn.</span><span class="sxs-lookup"><span data-stu-id="83520-137">Video file path and name</span></span> | <span data-ttu-id="83520-138">Videofilen som spelas upp av videospelaren.</span><span class="sxs-lookup"><span data-stu-id="83520-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="83520-139">Spela upp på helskärm</span><span class="sxs-lookup"><span data-stu-id="83520-139">Play fullscreen</span></span>       | <span data-ttu-id="83520-140">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-140">**True** or **False**</span></span>               | <span data-ttu-id="83520-141">När värdet är inställt på **Sant** spelas videon upp i helskärmsläge.</span><span class="sxs-lookup"><span data-stu-id="83520-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="83520-142">Utlösare för spela upp och pausa</span><span class="sxs-lookup"><span data-stu-id="83520-142">Play pause trigger</span></span>    | <span data-ttu-id="83520-143">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-143">**True** or **False**</span></span>               | <span data-ttu-id="83520-144">När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon.</span><span class="sxs-lookup"><span data-stu-id="83520-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="83520-145">Kontroller för videospelare</span><span class="sxs-lookup"><span data-stu-id="83520-145">Video player controls</span></span> | <span data-ttu-id="83520-146">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-146">**True** or **False**</span></span>               | <span data-ttu-id="83520-147">När värdet är inställt på **Sant** visas alla videospelarkontroller.</span><span class="sxs-lookup"><span data-stu-id="83520-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="83520-148">Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning.</span><span class="sxs-lookup"><span data-stu-id="83520-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="83520-149">Dölj affischbild</span><span class="sxs-lookup"><span data-stu-id="83520-149">Hide poster image</span></span>     | <span data-ttu-id="83520-150">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="83520-150">**True** or **False**</span></span>               | <span data-ttu-id="83520-151">Ett videoklipp kan ha en affischram.</span><span class="sxs-lookup"><span data-stu-id="83520-151">A video can have a poster frame.</span></span> <span data-ttu-id="83520-152">När värdet för den här egenskapen har angetts till **Sant**döljs affischramen.</span><span class="sxs-lookup"><span data-stu-id="83520-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="83520-153">Masknivå</span><span class="sxs-lookup"><span data-stu-id="83520-153">Mask level</span></span>            | <span data-ttu-id="83520-154">Ett nummer mellan **0** och **100**</span><span class="sxs-lookup"><span data-stu-id="83520-154">A number from **0** through **100**</span></span> | <span data-ttu-id="83520-155">Den mask som används på videon som ska formateras.</span><span class="sxs-lookup"><span data-stu-id="83520-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="83520-156">Lägg till en videospelarmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="83520-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="83520-157">Innan du skapar en videospelarmodul måste du först överföra en video till mediebiblioteket.</span><span class="sxs-lookup"><span data-stu-id="83520-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="83520-158">Om du vill lägga till en modul för videospelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="83520-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="83520-159">Skapa en sidmall som har namnet **videospelarmall**.</span><span class="sxs-lookup"><span data-stu-id="83520-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="83520-160">Lägg till platsen **Huvud** på standardsida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="83520-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="83520-161">Lägg till videospelare och modul för videospelare i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="83520-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="83520-162">Avsluta redigeringen i mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="83520-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="83520-163">Använd den videospelarmall som du skapade för att skapa en sida med namnet **videospelarsida**.</span><span class="sxs-lookup"><span data-stu-id="83520-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="83520-164">Lägg till platsen **Huvud** på den nya sidan, lägg till en modul för videospelare.</span><span class="sxs-lookup"><span data-stu-id="83520-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="83520-165">Välj **Lägg till en video** i egenskapsrutan för videospelarmodulen.</span><span class="sxs-lookup"><span data-stu-id="83520-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="83520-166">I dialogrutan **medieväljare**, välj en video och välj sedan **Överför nytt mediobjekt**.</span><span class="sxs-lookup"><span data-stu-id="83520-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="83520-167">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="83520-167">Save and preview the page.</span></span> <span data-ttu-id="83520-168">Du bör se videomodulerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="83520-168">You should see the video module on the page.</span></span> <span data-ttu-id="83520-169">Du kan ändra ytterligare inställningar om du vill anpassa funktionen för modulen.</span><span class="sxs-lookup"><span data-stu-id="83520-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="83520-170">Avsluta redigeringen av sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="83520-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83520-171">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="83520-171">Additional resources</span></span>

[<span data-ttu-id="83520-172">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="83520-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="83520-173">Annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="83520-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="83520-174">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="83520-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="83520-175">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="83520-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="83520-176">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="83520-176">Content block module</span></span>](add-hero-module.md)
