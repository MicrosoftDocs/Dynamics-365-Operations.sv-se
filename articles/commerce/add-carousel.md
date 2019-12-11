---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785247"
---
# <a name="carousel-module"></a><span data-ttu-id="b65c9-103">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b65c9-104">Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b65c9-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b65c9-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="b65c9-105">Overview</span></span>

<span data-ttu-id="b65c9-106">En karusellmodul används för att placera flera reklamartiklar i en karusell som kunder kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="b65c9-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="b65c9-107">Det är en särskild behållarmodul som är värd för andra moduler.</span><span class="sxs-lookup"><span data-stu-id="b65c9-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="b65c9-108">En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="b65c9-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="b65c9-109">Du kan lägga till fokus- och funktionsmoduler i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="b65c9-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="b65c9-110">Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.</span><span class="sxs-lookup"><span data-stu-id="b65c9-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="b65c9-111">Exempel på karusellmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="b65c9-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="b65c9-112">En karusell med flera reklammoduler i kan användas på en startsida.</span><span class="sxs-lookup"><span data-stu-id="b65c9-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="b65c9-113">En karusell med flera reklammoduler i kan användas på en sida med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="b65c9-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="b65c9-114">En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.</span><span class="sxs-lookup"><span data-stu-id="b65c9-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="b65c9-115">Egenskaper för karusellmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-115">Carousel module properties</span></span>

| <span data-ttu-id="b65c9-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="b65c9-116">Property name</span></span>             | <span data-ttu-id="b65c9-117">Värde</span><span class="sxs-lookup"><span data-stu-id="b65c9-117">Value</span></span>                                | <span data-ttu-id="b65c9-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b65c9-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="b65c9-119">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="b65c9-119">Autoplay</span></span>                  | <span data-ttu-id="b65c9-120">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="b65c9-120">**True** or **False**</span></span>                | <span data-ttu-id="b65c9-121">Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b65c9-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="b65c9-122">Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt.</span><span class="sxs-lookup"><span data-stu-id="b65c9-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="b65c9-123">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="b65c9-123">Slide transition interval</span></span> | <span data-ttu-id="b65c9-124">Ett värde i sekunder</span><span class="sxs-lookup"><span data-stu-id="b65c9-124">A value in seconds</span></span>                   | <span data-ttu-id="b65c9-125">Intervallet för övergångar mellan artiklar.</span><span class="sxs-lookup"><span data-stu-id="b65c9-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="b65c9-126">Övergång animering</span><span class="sxs-lookup"><span data-stu-id="b65c9-126">Transition animation</span></span>      | <span data-ttu-id="b65c9-127">**Bild** eller **toning**</span><span class="sxs-lookup"><span data-stu-id="b65c9-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="b65c9-128">Övergångseffekten.</span><span class="sxs-lookup"><span data-stu-id="b65c9-128">The transition effect.</span></span> |
| <span data-ttu-id="b65c9-129">Bredd</span><span class="sxs-lookup"><span data-stu-id="b65c9-129">Width</span></span>                     | <span data-ttu-id="b65c9-130">**Passa behållare** eller **Fyll skärm**</span><span class="sxs-lookup"><span data-stu-id="b65c9-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="b65c9-131">Om värdet är inställt på att **passa behållare** begränsas objekten i karusellen till karusellens bredd.</span><span class="sxs-lookup"><span data-stu-id="b65c9-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="b65c9-132">Om värdet är inställt på **Fyll skärm** begränsas inte objekten till karusellens bredd utan kan gå in i helskärmsläge.</span><span class="sxs-lookup"><span data-stu-id="b65c9-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="b65c9-133">Du kan ändra värdet för att uppnå önskad layout.</span><span class="sxs-lookup"><span data-stu-id="b65c9-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="b65c9-134">Lägg till en karusellmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="b65c9-134">Add a carousel module to a page</span></span>

<span data-ttu-id="b65c9-135">Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b65c9-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b65c9-136">Skapa en sidmall som har namnet **karusellmall**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="b65c9-137">Lägg till platsen **Huvud** på standardsida, lägg till en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="b65c9-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="b65c9-138">Lägg till en fokusmodul i karusellmodulen.</span><span class="sxs-lookup"><span data-stu-id="b65c9-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="b65c9-139">Lägg till en funktionsmodul i karusellmodulen.</span><span class="sxs-lookup"><span data-stu-id="b65c9-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="b65c9-140">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="b65c9-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="b65c9-141">Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="b65c9-142">Lägg till platsen **Huvud** på ny sida, lägg till en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="b65c9-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="b65c9-143">Ange egenskapen **Bredd** för karusellmodulen för att **Fylla skärmen**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="b65c9-144">Ange egenskapen **övergångsanimation** till **Bild**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="b65c9-145">Lägg till en fokusmodul i karusellmodulen.</span><span class="sxs-lookup"><span data-stu-id="b65c9-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="b65c9-146">Lägg till en bild och en rubrik i fokusmodulen och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="b65c9-147">Lägg till en funktionsmodul i karusellmodulen.</span><span class="sxs-lookup"><span data-stu-id="b65c9-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="b65c9-148">Lägg till en bild, en rubrik och en textparagraf i funktionsmodulen.</span><span class="sxs-lookup"><span data-stu-id="b65c9-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="b65c9-149">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="b65c9-149">Save and preview the page.</span></span> <span data-ttu-id="b65c9-150">Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul).</span><span class="sxs-lookup"><span data-stu-id="b65c9-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="b65c9-151">Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.</span><span class="sxs-lookup"><span data-stu-id="b65c9-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="b65c9-152">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="b65c9-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b65c9-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b65c9-153">Additional resources</span></span>

[<span data-ttu-id="b65c9-154">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="b65c9-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b65c9-155">Notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="b65c9-156">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b65c9-157">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="b65c9-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="b65c9-158">Funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="b65c9-159">Fokusmodul</span><span class="sxs-lookup"><span data-stu-id="b65c9-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="b65c9-160">Videospelar-modul</span><span class="sxs-lookup"><span data-stu-id="b65c9-160">Video player module</span></span>](add-video-player.md)
