---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5bc2227e08dbbf5f76a37180114e5affff131658
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797897"
---
# <a name="carousel-module"></a><span data-ttu-id="90308-103">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="90308-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="90308-104">Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="90308-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="90308-105">En karusellmodul används för att placera flera reklamartiklar (inklusive rika bilder) i en roterande karusellbanderoll som kunder kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="90308-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="90308-106">En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="90308-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="90308-107">Du kan lägga till innehållsblockmoduler i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="90308-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="90308-108">Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.</span><span class="sxs-lookup"><span data-stu-id="90308-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="90308-109">Exempel på karusellmoduler i näthandel</span><span class="sxs-lookup"><span data-stu-id="90308-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="90308-110">En karusell med flera reklammoduler i kan användas på en startsida.</span><span class="sxs-lookup"><span data-stu-id="90308-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="90308-111">En karusell med flera reklammoduler i kan användas på en sida med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="90308-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="90308-112">En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.</span><span class="sxs-lookup"><span data-stu-id="90308-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="90308-113">Följande bild visar ett exempel på en karusellmodul som används på en startsida.</span><span class="sxs-lookup"><span data-stu-id="90308-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="90308-114">Den här karusellmodulen innehåller flera innehållsblockobjekt.</span><span class="sxs-lookup"><span data-stu-id="90308-114">This carousel module contains multiple content block items.</span></span>

![Exempel på en karusellmodul](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="90308-116">Egenskaper för karusellmodul</span><span class="sxs-lookup"><span data-stu-id="90308-116">Carousel module properties</span></span>

| <span data-ttu-id="90308-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="90308-117">Property name</span></span>             | <span data-ttu-id="90308-118">Värde</span><span class="sxs-lookup"><span data-stu-id="90308-118">Value</span></span>                 | <span data-ttu-id="90308-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="90308-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="90308-120">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="90308-120">Autoplay</span></span>                  | <span data-ttu-id="90308-121">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="90308-121">**True** or **False**</span></span> | <span data-ttu-id="90308-122">Om värdet är inställt på **Sant** sker övergången mellan objekten i karusellen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="90308-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="90308-123">Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt.</span><span class="sxs-lookup"><span data-stu-id="90308-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="90308-124">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="90308-124">Slide transition interval</span></span> | <span data-ttu-id="90308-125">Ett värde i sekunder</span><span class="sxs-lookup"><span data-stu-id="90308-125">A value in seconds</span></span>    | <span data-ttu-id="90308-126">Intervallet för övergångar mellan artiklar.</span><span class="sxs-lookup"><span data-stu-id="90308-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="90308-127">Övergångstyp</span><span class="sxs-lookup"><span data-stu-id="90308-127">Transition type</span></span>           | <span data-ttu-id="90308-128">**Bild** eller **toning**</span><span class="sxs-lookup"><span data-stu-id="90308-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="90308-129">Övergångseffekten mellan objekt.</span><span class="sxs-lookup"><span data-stu-id="90308-129">The transition effect between items.</span></span> |
| <span data-ttu-id="90308-130">Dölj karusellens flipper</span><span class="sxs-lookup"><span data-stu-id="90308-130">Hide carousel flipper</span></span>     | <span data-ttu-id="90308-131">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="90308-131">**True** or **False**</span></span> | <span data-ttu-id="90308-132">Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator.</span><span class="sxs-lookup"><span data-stu-id="90308-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="90308-133">Tillåt att karusellen stängs</span><span class="sxs-lookup"><span data-stu-id="90308-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="90308-134">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="90308-134">**True** or **False**</span></span> | <span data-ttu-id="90308-135">Om värdet är inställt på **Sant** kan användare stänga karusellen.</span><span class="sxs-lookup"><span data-stu-id="90308-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="90308-136">Lägg till en karusellmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="90308-136">Add a carousel module to a page</span></span>

<span data-ttu-id="90308-137">Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="90308-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="90308-138">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="90308-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="90308-139">I dialogrutan **Ny mal** under **Mallnamn**, ange **Karusellmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="90308-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="90308-140">I facket **Brödtext**, lägg till en **standardsida**-modul.</span><span class="sxs-lookup"><span data-stu-id="90308-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="90308-141">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="90308-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="90308-142">Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.</span><span class="sxs-lookup"><span data-stu-id="90308-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="90308-143">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="90308-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="90308-144">I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.</span><span class="sxs-lookup"><span data-stu-id="90308-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="90308-145">Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="90308-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="90308-146">I karusellmodulen, lägg till en innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="90308-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="90308-147">Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="90308-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="90308-148">Lägg till och konfigurera en annan innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="90308-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="90308-149">Ställ in ytterligare egenskaper för karusellmodulen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="90308-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="90308-150">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="90308-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="90308-151">Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul).</span><span class="sxs-lookup"><span data-stu-id="90308-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="90308-152">Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.</span><span class="sxs-lookup"><span data-stu-id="90308-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="90308-153">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="90308-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="90308-154">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="90308-154">Additional resources</span></span>

[<span data-ttu-id="90308-155">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="90308-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="90308-156">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="90308-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="90308-157">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="90308-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="90308-158">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="90308-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="90308-159">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="90308-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]