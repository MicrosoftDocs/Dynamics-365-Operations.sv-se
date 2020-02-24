---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025791"
---
# <a name="carousel-module"></a><span data-ttu-id="e9912-103">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="e9912-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e9912-104">Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e9912-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e9912-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e9912-105">Overview</span></span>

<span data-ttu-id="e9912-106">En karusellmodul används för att placera flera reklamartiklar (inklusive rika bilder) i en roterande karusellbanderoll som kunder kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="e9912-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="e9912-107">En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="e9912-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="e9912-108">Du kan lägga till innehållsblockmoduler i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="e9912-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="e9912-109">Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.</span><span class="sxs-lookup"><span data-stu-id="e9912-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="e9912-110">Exempel på karusellmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="e9912-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="e9912-111">En karusell med flera reklammoduler i kan användas på en startsida.</span><span class="sxs-lookup"><span data-stu-id="e9912-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="e9912-112">En karusell med flera reklammoduler i kan användas på en sida med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="e9912-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="e9912-113">En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.</span><span class="sxs-lookup"><span data-stu-id="e9912-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="e9912-114">Egenskaper för karusellmodul</span><span class="sxs-lookup"><span data-stu-id="e9912-114">Carousel module properties</span></span>

| <span data-ttu-id="e9912-115">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="e9912-115">Property name</span></span>             | <span data-ttu-id="e9912-116">Värde</span><span class="sxs-lookup"><span data-stu-id="e9912-116">Value</span></span>                 | <span data-ttu-id="e9912-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e9912-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="e9912-118">Spela upp automatiskt</span><span class="sxs-lookup"><span data-stu-id="e9912-118">Autoplay</span></span>                  | <span data-ttu-id="e9912-119">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e9912-119">**True** or **False**</span></span> | <span data-ttu-id="e9912-120">Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e9912-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="e9912-121">Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt.</span><span class="sxs-lookup"><span data-stu-id="e9912-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="e9912-122">Intervall för bildövergång</span><span class="sxs-lookup"><span data-stu-id="e9912-122">Slide transition interval</span></span> | <span data-ttu-id="e9912-123">Ett värde i sekunder</span><span class="sxs-lookup"><span data-stu-id="e9912-123">A value in seconds</span></span>    | <span data-ttu-id="e9912-124">Intervallet för övergångar mellan artiklar.</span><span class="sxs-lookup"><span data-stu-id="e9912-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="e9912-125">Övergångstyp</span><span class="sxs-lookup"><span data-stu-id="e9912-125">Transition type</span></span>           | <span data-ttu-id="e9912-126">**Bild** eller **toning**</span><span class="sxs-lookup"><span data-stu-id="e9912-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="e9912-127">Övergångseffekten mellan objekt.</span><span class="sxs-lookup"><span data-stu-id="e9912-127">The transition effect between items.</span></span> |
| <span data-ttu-id="e9912-128">Dölj karusellens flipper</span><span class="sxs-lookup"><span data-stu-id="e9912-128">Hide carousel flipper</span></span>     | <span data-ttu-id="e9912-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e9912-129">**True** or **False**</span></span> | <span data-ttu-id="e9912-130">Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator.</span><span class="sxs-lookup"><span data-stu-id="e9912-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="e9912-131">Tillåt att karusellen stängs</span><span class="sxs-lookup"><span data-stu-id="e9912-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="e9912-132">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="e9912-132">**True** or **False**</span></span> | <span data-ttu-id="e9912-133">Om värdet är inställt på **Sant** kan användare stänga karusellen.</span><span class="sxs-lookup"><span data-stu-id="e9912-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="e9912-134">Lägg till en karusellmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="e9912-134">Add a carousel module to a page</span></span>

<span data-ttu-id="e9912-135">Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e9912-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e9912-136">Skapa en sidmall som har namnet **karusellmall**.</span><span class="sxs-lookup"><span data-stu-id="e9912-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="e9912-137">I facket **Brödtext**, lägg till en **standardsida**-modul.</span><span class="sxs-lookup"><span data-stu-id="e9912-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="e9912-138">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="e9912-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="e9912-139">Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.</span><span class="sxs-lookup"><span data-stu-id="e9912-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="e9912-140">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="e9912-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="e9912-141">I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.</span><span class="sxs-lookup"><span data-stu-id="e9912-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="e9912-142">Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="e9912-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="e9912-143">I karusellmodulen, lägg till en innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="e9912-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="e9912-144">Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="e9912-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="e9912-145">Lägg till och konfigurera en annan innehållsblockmodul.</span><span class="sxs-lookup"><span data-stu-id="e9912-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="e9912-146">Ställ in ytterligare egenskaper för karusellmodulen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="e9912-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="e9912-147">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="e9912-147">Save and preview the page.</span></span> <span data-ttu-id="e9912-148">Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul).</span><span class="sxs-lookup"><span data-stu-id="e9912-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="e9912-149">Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.</span><span class="sxs-lookup"><span data-stu-id="e9912-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="e9912-150">Avsluta redigeringen av sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="e9912-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9912-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e9912-151">Additional resources</span></span>

[<span data-ttu-id="e9912-152">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="e9912-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e9912-153">Annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="e9912-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="e9912-154">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="e9912-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="e9912-155">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="e9912-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="e9912-156">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="e9912-156">Video player module</span></span>](add-video-player.md)
