---
title: Notifieringsmodul
description: Det här avsnittet handlar om notifieringsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785362"
---
# <a name="alert-module"></a><span data-ttu-id="5a4d1-103">Notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5a4d1-104">Det här avsnittet handlar om notifieringsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5a4d1-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5a4d1-105">Overview</span></span>

<span data-ttu-id="5a4d1-106">En notifieringsmodul används för att visa infogade informationsmeddelanden på en sida.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="5a4d1-107">I notifieringsmoduler kan du använda textmeddelanden och länkar.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="5a4d1-108">De kan användas för att visa erbjudanden på hela webbplatsen som visas på alla sidor på en e-handelswebbplats.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="5a4d1-109">Notifieringsmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="5a4d1-110">Exempel på notifieringsmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="5a4d1-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="5a4d1-111">Du kan använda notifieringsmoduler i webbplatsrubriken för att ange reklamerbjudanden eller meddelanden som gäller hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="5a4d1-112">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="5a4d1-112">Here are some examples:</span></span>

<span data-ttu-id="5a4d1-113">"Årlig rea slutar om 10 dagar"</span><span class="sxs-lookup"><span data-stu-id="5a4d1-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="5a4d1-114">"Spara stort med tillbaka till skolan-rea.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-114">"Save big with back to school sale.</span></span> <span data-ttu-id="5a4d1-115">Handla nu."</span><span class="sxs-lookup"><span data-stu-id="5a4d1-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="5a4d1-116">Egenskaper för notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-116">Alert module properties</span></span>

| <span data-ttu-id="5a4d1-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="5a4d1-117">Property name</span></span>  | <span data-ttu-id="5a4d1-118">Värde</span><span class="sxs-lookup"><span data-stu-id="5a4d1-118">Value</span></span>                              | <span data-ttu-id="5a4d1-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5a4d1-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="5a4d1-120">Text</span><span class="sxs-lookup"><span data-stu-id="5a4d1-120">Text</span></span>           | <span data-ttu-id="5a4d1-121">Text</span><span class="sxs-lookup"><span data-stu-id="5a4d1-121">Text</span></span>                               | <span data-ttu-id="5a4d1-122">Textmeddelandet som visas i notifieringsmodulen.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="5a4d1-123">Textjustering</span><span class="sxs-lookup"><span data-stu-id="5a4d1-123">Text alignment</span></span> | <span data-ttu-id="5a4d1-124">**Höger**, **Vänster** eller **Centrera**</span><span class="sxs-lookup"><span data-stu-id="5a4d1-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="5a4d1-125">Ett värde som definierar hur text justeras i notifieringsmodulen.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="5a4d1-126">Avfärda notifiering</span><span class="sxs-lookup"><span data-stu-id="5a4d1-126">Dismiss alert</span></span>  | <span data-ttu-id="5a4d1-127">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="5a4d1-127">**True** or **False**</span></span>              | <span data-ttu-id="5a4d1-128">Om värdet är inställt på **Sant** kan kunden stänga notifieringen.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="5a4d1-129">Länka</span><span class="sxs-lookup"><span data-stu-id="5a4d1-129">Link</span></span>           | <span data-ttu-id="5a4d1-130">URL</span><span class="sxs-lookup"><span data-stu-id="5a4d1-130">URL</span></span>                                | <span data-ttu-id="5a4d1-131">URL:en för en valfri länk.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="5a4d1-132">Lägg till notifieringsmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="5a4d1-132">Add an alert module to a page</span></span> 

<span data-ttu-id="5a4d1-133">Om du vill lägga till en notifieringsmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="5a4d1-134">Skapa en sidmall som har namnet **notifieringsmall**.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="5a4d1-135">Lägg till platsen **Huvud** på standardsida, lägg till notifieringsmodul.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="5a4d1-136">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="5a4d1-137">Använd den notifieringsmall som du just skapade för att skapa en sida med namnet **notifieringssida**.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="5a4d1-138">Lägg till platsen **Huvud** på den nya sidan, lägg till notifieringsmodul.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="5a4d1-139">I inställningarna för notifieringsmodulen anger du notifieringstexten.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="5a4d1-140">Du kan redigera de andra egenskaperna om du vill anpassa notifieringsmodulen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="5a4d1-141">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-141">Save and preview the page.</span></span> <span data-ttu-id="5a4d1-142">Högst upp på sidan ska du se en notifiering med den tillagda texten.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="5a4d1-143">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="5a4d1-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="5a4d1-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5a4d1-144">Additional resources</span></span>

[<span data-ttu-id="5a4d1-145">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="5a4d1-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5a4d1-146">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="5a4d1-147">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="5a4d1-148">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="5a4d1-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="5a4d1-149">Funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="5a4d1-150">Fokusmodul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="5a4d1-151">Videospelar-modul</span><span class="sxs-lookup"><span data-stu-id="5a4d1-151">Video player module</span></span>](add-video-player.md)
