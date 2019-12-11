---
title: Innehållsrik blockmodul
description: Det här avsnittet handlar om innehållsrika blockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785431"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="dbc6d-103">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="dbc6d-104">Det här avsnittet handlar om innehållsrika blockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dbc6d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="dbc6d-105">Overview</span></span>

<span data-ttu-id="dbc6d-106">En innehållsrik blockmodul är en speciell behållare som en eller flera innehållsrika blockobjekt kan placeras i.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="dbc6d-107">Innehållsrika blockmoduler används för textinnehåll på en sida.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="dbc6d-108">Det här innehållet kan vara både information och reklam.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="dbc6d-109">Innehållsrika blockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="dbc6d-110">De är fristående moduler som inte är beroende av sidkontext eller andra moduler.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="dbc6d-111">Exempel på innehållsrika blockmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="dbc6d-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="dbc6d-112">Innehållsrika blockmoduler kan användas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="dbc6d-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="dbc6d-113">För att presentera produktfunktioner på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="dbc6d-114">För information på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-114">For informational purposes on any page.</span></span> <span data-ttu-id="dbc6d-115">De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="dbc6d-116">Om du vill lägga till anpassade meddelanden på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="dbc6d-117">(t.ex. "gratis frakt för order över 50 $").</span><span class="sxs-lookup"><span data-stu-id="dbc6d-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="dbc6d-118">För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").</span><span class="sxs-lookup"><span data-stu-id="dbc6d-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="dbc6d-119">Egenskaper för innehållsrika blockmoduler</span><span class="sxs-lookup"><span data-stu-id="dbc6d-119">Content rich block module properties</span></span>

| <span data-ttu-id="dbc6d-120">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="dbc6d-120">Property name</span></span>     | <span data-ttu-id="dbc6d-121">Värde</span><span class="sxs-lookup"><span data-stu-id="dbc6d-121">Value</span></span>                                 | <span data-ttu-id="dbc6d-122">Egenskap</span><span class="sxs-lookup"><span data-stu-id="dbc6d-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="dbc6d-123">Antal kolumner</span><span class="sxs-lookup"><span data-stu-id="dbc6d-123">Number of columns</span></span> | <span data-ttu-id="dbc6d-124">Ett nummer mellan **1** och **4**</span><span class="sxs-lookup"><span data-stu-id="dbc6d-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="dbc6d-125">Antalet kolumner i det innehållsrika blocket.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="dbc6d-126">Det kan finnas upp till fyra kolumner.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="dbc6d-127">Bredd</span><span class="sxs-lookup"><span data-stu-id="dbc6d-127">Width</span></span>             | <span data-ttu-id="dbc6d-128">**Fyll behållare** eller **Fyll skärm**</span><span class="sxs-lookup"><span data-stu-id="dbc6d-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="dbc6d-129">Om värdet är inställt på att **Fylla behållare** begränsas behållaren till behållarens bredd.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="dbc6d-130">Om värdet är inställt på **Fyll skärm** begränsas inte objekten till behållarens bredd utan kan gå in i helskärmsläge.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="dbc6d-131">Du kan ändra värdet för att uppnå önskad layout.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="dbc6d-132">Egenskaper för innehållsrika blockobjektmoduler</span><span class="sxs-lookup"><span data-stu-id="dbc6d-132">Content rich block item module properties</span></span>

| <span data-ttu-id="dbc6d-133">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="dbc6d-133">Property name</span></span> | <span data-ttu-id="dbc6d-134">Värde</span><span class="sxs-lookup"><span data-stu-id="dbc6d-134">Value</span></span>          | <span data-ttu-id="dbc6d-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dbc6d-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="dbc6d-136">Stycke</span><span class="sxs-lookup"><span data-stu-id="dbc6d-136">Paragraph</span></span>     | <span data-ttu-id="dbc6d-137">Stycketext</span><span class="sxs-lookup"><span data-stu-id="dbc6d-137">Paragraph text</span></span> | <span data-ttu-id="dbc6d-138">Texten som medföljer varje innehållsrikt blockobjekt.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="dbc6d-139">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="dbc6d-140">Lägg till en innehållsrik blockmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="dbc6d-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="dbc6d-141">Om du vill lägga till en innehållsrik blockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="dbc6d-142">Skapa en sidmall som har namnet **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="dbc6d-143">Lägg till platsen **Huvud** på standardsida, lägg till en innehållsrik blockmodul.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="dbc6d-144">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="dbc6d-145">Använd den innehållsmall som du just skapade för att skapa en sida med namnet **Innehållssida**.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="dbc6d-146">Lägg till platsen **Huvud** på ny sida, lägg till en innehållsrik blockmodul.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="dbc6d-147">I egenskaperna för innehållsrika blockmodulen ange antalet kolumner till **2**.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="dbc6d-148">I innehållsrik blockmodul, välj **Lägg till en modul** och lägg till ett innehållsrikt blockobjekt (t.ex., **objekt1**).</span><span class="sxs-lookup"><span data-stu-id="dbc6d-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="dbc6d-149">Lägg till stycketext i det nya innehållsrika blockobjektet.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="dbc6d-150">I innehållsrik blockmodul, välj **Lägg till en modul** och lägg till ett innehållsrikt blockobjekt (t.ex., **objekt2**).</span><span class="sxs-lookup"><span data-stu-id="dbc6d-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="dbc6d-151">Lägg till stycketext i det nya innehållsrika blockobjektet.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="dbc6d-152">Spara sidan och förhandsgranska ändringarna.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="dbc6d-153">Två RTF-block bör visas i en vy med två spalter.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="dbc6d-154">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="dbc6d-155">Om du lägger till ett tredje innehållsrikt blockobjekt kommer det att staplas nedanför de två objekt som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="dbc6d-156">Genom att ändra antalet kolumner och objekt i behållaren kan du uppnå olika layouter för textinnehåll.</span><span class="sxs-lookup"><span data-stu-id="dbc6d-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbc6d-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dbc6d-157">Additional resources</span></span>

[<span data-ttu-id="dbc6d-158">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="dbc6d-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dbc6d-159">Notifieringsmodul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="dbc6d-160">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="dbc6d-161">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="dbc6d-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="dbc6d-162">Funktionsmodul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="dbc6d-163">Fokusmodul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="dbc6d-164">Videospelar-modul</span><span class="sxs-lookup"><span data-stu-id="dbc6d-164">Video player module</span></span>](add-video-player.md)

