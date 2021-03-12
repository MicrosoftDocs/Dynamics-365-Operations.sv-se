---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 0b4ce8fdb7b598e55db59ddf5a99a0ba46eb6f91
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986014"
---
# <a name="carousel-module"></a><span data-ttu-id="bc558-103">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="bc558-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bc558-104">Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc558-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bc558-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="bc558-105">Overview</span></span>

<span data-ttu-id="bc558-106">En karusellmodul används för att placera flera reklamartiklar (inklusive rika bilder) i en roterande karusellbanderoll som kunder kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="bc558-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="bc558-107">En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="bc558-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="bc558-108">Du kan lägga till innehållsblockmoduler i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="bc558-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="bc558-109">Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.</span><span class="sxs-lookup"><span data-stu-id="bc558-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="bc558-110">Exempel på karusellmoduler i näthandel</span><span class="sxs-lookup"><span data-stu-id="bc558-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="bc558-111">En karusell med flera reklammoduler i kan användas på en startsida.</span><span class="sxs-lookup"><span data-stu-id="bc558-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="bc558-112">En karusell med flera reklammoduler i kan användas på en sida med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="bc558-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="bc558-113">En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.</span><span class="sxs-lookup"><span data-stu-id="bc558-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="bc558-114">Följande bild visar ett exempel på en karusellmodul som används på en startsida.</span><span class="sxs-lookup"><span data-stu-id="bc558-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="bc558-115">Den här karusellmodulen innehåller flera innehållsblockobjekt.</span><span class="sxs-lookup"><span data-stu-id="bc558-115">This carousel module contains multiple content block items.</span></span>

![Exempel på en karusellmodul](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="bc558-117">Egenskaper för karusellmodul</span><span class="sxs-lookup"><span data-stu-id="bc558-117">Carousel module properties</span></span>

| <span data-ttu-id="bc558-118">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="bc558-118">Property name</span></span>             | <span data-ttu-id="bc558-119">Värde</span><span class="sxs-lookup"><span data-stu-id="bc558-119">Value</span></span>                 | <span data-ttu-id="bc558-120">beskrivning</span><span class="sxs-lookup"><span data-stu-id="bc558-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="bc558-121">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="bc558-121">Autoplay</span></span>                  | <span data-ttu-id="bc558-122">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="bc558-122">**True** or **False**</span></span> | <span data-ttu-id="bc558-123">Om värdet är inställt på **Sant** sker övergången mellan objekten i karusellen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bc558-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="bc558-124">Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt.</span><span class="sxs-lookup"><span data-stu-id="bc558-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="bc558-125">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="bc558-125">Slide transition interval</span></span> | <span data-ttu-id="bc558-126">Ett värde i sekunder</span><span class="sxs-lookup"><span data-stu-id="bc558-126">A value in seconds</span></span>    | <span data-ttu-id="bc558-127">Intervallet för övergångar mellan artiklar.</span><span class="sxs-lookup"><span data-stu-id="bc558-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="bc558-128">Övergångstyp</span><span class="sxs-lookup"><span data-stu-id="bc558-128">Transition type</span></span>           | <span data-ttu-id="bc558-129">**Bild** eller **toning**</span><span class="sxs-lookup"><span data-stu-id="bc558-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="bc558-130">Övergångseffekten mellan objekt.</span><span class="sxs-lookup"><span data-stu-id="bc558-130">The transition effect between items.</span></span> |
| <span data-ttu-id="bc558-131">Dölj karusellens flipper</span><span class="sxs-lookup"><span data-stu-id="bc558-131">Hide carousel flipper</span></span>     | <span data-ttu-id="bc558-132">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="bc558-132">**True** or **False**</span></span> | <span data-ttu-id="bc558-133">Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator.</span><span class="sxs-lookup"><span data-stu-id="bc558-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="bc558-134">Tillåt att karusellen stängs</span><span class="sxs-lookup"><span data-stu-id="bc558-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="bc558-135">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="bc558-135">**True** or **False**</span></span> | <span data-ttu-id="bc558-136">Om värdet är inställt på **Sant** kan användare stänga karusellen.</span><span class="sxs-lookup"><span data-stu-id="bc558-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="bc558-137">Lägg till en karusellmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="bc558-137">Add a carousel module to a page</span></span>

<span data-ttu-id="bc558-138">Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="bc558-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bc558-139">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="bc558-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="bc558-140">I dialogrutan **Ny mal** under **Mallnamn**, ange **Karusellmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc558-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="bc558-141">I facket **Brödtext**, lägg till en **standardsida**-modul.</span><span class="sxs-lookup"><span data-stu-id="bc558-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="bc558-142">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="bc558-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="bc558-143">Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.</span><span class="sxs-lookup"><span data-stu-id="bc558-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="bc558-144">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="bc558-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="bc558-145">I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.</span><span class="sxs-lookup"><span data-stu-id="bc558-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="bc558-146">Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="bc558-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="bc558-147">I karusellmodulen, lägg till en innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="bc558-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="bc558-148">Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="bc558-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="bc558-149">Lägg till och konfigurera en annan innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="bc558-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="bc558-150">Ställ in ytterligare egenskaper för karusellmodulen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="bc558-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="bc558-151">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="bc558-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="bc558-152">Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul).</span><span class="sxs-lookup"><span data-stu-id="bc558-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="bc558-153">Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.</span><span class="sxs-lookup"><span data-stu-id="bc558-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="bc558-154">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="bc558-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc558-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bc558-155">Additional resources</span></span>

[<span data-ttu-id="bc558-156">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="bc558-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bc558-157">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="bc558-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="bc558-158">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="bc558-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="bc558-159">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="bc558-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="bc558-160">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="bc558-160">Video player module</span></span>](add-video-player.md)
