---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: f399e4c5618b65b781fdd3ec835e841614579313
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269738"
---
# <a name="carousel-module"></a><span data-ttu-id="586a5-103">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="586a5-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="586a5-104">Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="586a5-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="586a5-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="586a5-105">Overview</span></span>

<span data-ttu-id="586a5-106">En karusellmodul används för att placera flera reklamartiklar (inklusive rika bilder) i en roterande karusellbanderoll som kunder kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="586a5-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="586a5-107">En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="586a5-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="586a5-108">Du kan lägga till innehållsblockmoduler i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="586a5-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="586a5-109">Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.</span><span class="sxs-lookup"><span data-stu-id="586a5-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="586a5-110">Exempel på karusellmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="586a5-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="586a5-111">En karusell med flera reklammoduler i kan användas på en startsida.</span><span class="sxs-lookup"><span data-stu-id="586a5-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="586a5-112">En karusell med flera reklammoduler i kan användas på en sida med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="586a5-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="586a5-113">En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.</span><span class="sxs-lookup"><span data-stu-id="586a5-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="586a5-114">Egenskaper för karusellmodul</span><span class="sxs-lookup"><span data-stu-id="586a5-114">Carousel module properties</span></span>

| <span data-ttu-id="586a5-115">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="586a5-115">Property name</span></span>             | <span data-ttu-id="586a5-116">Värde</span><span class="sxs-lookup"><span data-stu-id="586a5-116">Value</span></span>                 | <span data-ttu-id="586a5-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="586a5-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="586a5-118">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="586a5-118">Autoplay</span></span>                  | <span data-ttu-id="586a5-119">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="586a5-119">**True** or **False**</span></span> | <span data-ttu-id="586a5-120">Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="586a5-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="586a5-121">Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt.</span><span class="sxs-lookup"><span data-stu-id="586a5-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="586a5-122">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="586a5-122">Slide transition interval</span></span> | <span data-ttu-id="586a5-123">Ett värde i sekunder</span><span class="sxs-lookup"><span data-stu-id="586a5-123">A value in seconds</span></span>    | <span data-ttu-id="586a5-124">Intervallet för övergångar mellan artiklar.</span><span class="sxs-lookup"><span data-stu-id="586a5-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="586a5-125">Övergångstyp</span><span class="sxs-lookup"><span data-stu-id="586a5-125">Transition type</span></span>           | <span data-ttu-id="586a5-126">**Bild** eller **toning**</span><span class="sxs-lookup"><span data-stu-id="586a5-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="586a5-127">Övergångseffekten mellan objekt.</span><span class="sxs-lookup"><span data-stu-id="586a5-127">The transition effect between items.</span></span> |
| <span data-ttu-id="586a5-128">Dölj karusellens flipper</span><span class="sxs-lookup"><span data-stu-id="586a5-128">Hide carousel flipper</span></span>     | <span data-ttu-id="586a5-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="586a5-129">**True** or **False**</span></span> | <span data-ttu-id="586a5-130">Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator.</span><span class="sxs-lookup"><span data-stu-id="586a5-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="586a5-131">Tillåt att karusellen stängs</span><span class="sxs-lookup"><span data-stu-id="586a5-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="586a5-132">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="586a5-132">**True** or **False**</span></span> | <span data-ttu-id="586a5-133">Om värdet är inställt på **Sant** kan användare stänga karusellen.</span><span class="sxs-lookup"><span data-stu-id="586a5-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="586a5-134">Lägg till en karusellmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="586a5-134">Add a carousel module to a page</span></span>

<span data-ttu-id="586a5-135">Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="586a5-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="586a5-136">Skapa en ny sidmall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="586a5-136">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="586a5-137">I dialogrutan **Ny mal** under **Mallnamn**, ange **Karusellmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="586a5-137">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="586a5-138">I facket **Brödtext**, lägg till en **standardsida**-modul.</span><span class="sxs-lookup"><span data-stu-id="586a5-138">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="586a5-139">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="586a5-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="586a5-140">Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.</span><span class="sxs-lookup"><span data-stu-id="586a5-140">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="586a5-141">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="586a5-141">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="586a5-142">I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.</span><span class="sxs-lookup"><span data-stu-id="586a5-142">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="586a5-143">Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="586a5-143">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="586a5-144">I karusellmodulen, lägg till en innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="586a5-144">Add a content block module to the carousel module.</span></span> <span data-ttu-id="586a5-145">Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="586a5-145">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="586a5-146">Lägg till och konfigurera en annan innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="586a5-146">Add and configure another content block module.</span></span>
1. <span data-ttu-id="586a5-147">Ställ in ytterligare egenskaper för karusellmodulen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="586a5-147">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="586a5-148">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="586a5-148">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="586a5-149">Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul).</span><span class="sxs-lookup"><span data-stu-id="586a5-149">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="586a5-150">Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.</span><span class="sxs-lookup"><span data-stu-id="586a5-150">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="586a5-151">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="586a5-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="586a5-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="586a5-152">Additional resources</span></span>

[<span data-ttu-id="586a5-153">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="586a5-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="586a5-154">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="586a5-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="586a5-155">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="586a5-155">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="586a5-156">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="586a5-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="586a5-157">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="586a5-157">Video player module</span></span>](add-video-player.md)
