---
title: Textblockmodul
description: Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025607"
---
# <a name="text-block-module"></a><span data-ttu-id="d114a-103">Textblockmodul</span><span class="sxs-lookup"><span data-stu-id="d114a-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d114a-104">Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d114a-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d114a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d114a-105">Overview</span></span>

<span data-ttu-id="d114a-106">En textblockmodul är en modul som används för att lägga till textinnehåll.</span><span class="sxs-lookup"><span data-stu-id="d114a-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="d114a-107">Det här innehållet kan vara information och reklam.</span><span class="sxs-lookup"><span data-stu-id="d114a-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="d114a-108">Textblockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="d114a-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="d114a-109">De är fristående moduler som inte är beroende av sidkontext eller andra moduler.</span><span class="sxs-lookup"><span data-stu-id="d114a-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="d114a-110">Exempel på innehållsrika textmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="d114a-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="d114a-111">Innehållsrika textblockmoduler kan användas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d114a-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="d114a-112">För att presentera produktfunktioner på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="d114a-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="d114a-113">För information på vilken sida som helst.</span><span class="sxs-lookup"><span data-stu-id="d114a-113">For informational purposes on any page.</span></span> <span data-ttu-id="d114a-114">De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.</span><span class="sxs-lookup"><span data-stu-id="d114a-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="d114a-115">Om du vill lägga till anpassade meddelanden på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="d114a-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="d114a-116">(t.ex. "gratis frakt för order över 50 $").</span><span class="sxs-lookup"><span data-stu-id="d114a-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="d114a-117">För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").</span><span class="sxs-lookup"><span data-stu-id="d114a-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="d114a-118">Egenskaper för textblockmodul</span><span class="sxs-lookup"><span data-stu-id="d114a-118">Text block module properties</span></span>

| <span data-ttu-id="d114a-119">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="d114a-119">Property name</span></span>     | <span data-ttu-id="d114a-120">Value</span><span class="sxs-lookup"><span data-stu-id="d114a-120">Value</span></span>                                            | <span data-ttu-id="d114a-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d114a-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="d114a-122">RTF-format</span><span class="sxs-lookup"><span data-stu-id="d114a-122">Rich text</span></span>         | <span data-ttu-id="d114a-123">RTF-format</span><span class="sxs-lookup"><span data-stu-id="d114a-123">Rich text</span></span>                                        | <span data-ttu-id="d114a-124">Stycketext.</span><span class="sxs-lookup"><span data-stu-id="d114a-124">Paragraph text.</span></span> <span data-ttu-id="d114a-125">Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text.</span><span class="sxs-lookup"><span data-stu-id="d114a-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="d114a-126">Anpassat klassnamn</span><span class="sxs-lookup"><span data-stu-id="d114a-126">Custom class name</span></span> | <span data-ttu-id="d114a-127">Ett klassnamn för Överlappande formatmallar (CSS)</span><span class="sxs-lookup"><span data-stu-id="d114a-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="d114a-128">Namnet på en anpassad CSS-klass som en utvecklare använder för att formatera modulen.</span><span class="sxs-lookup"><span data-stu-id="d114a-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="d114a-129">Klassnamnet måste definieras i temapaketet.</span><span class="sxs-lookup"><span data-stu-id="d114a-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="d114a-130">Teckenstorlek</span><span class="sxs-lookup"><span data-stu-id="d114a-130">Font size</span></span>         | <span data-ttu-id="d114a-131">**Small**, **Medium**, **Large** eller **X-Large**</span><span class="sxs-lookup"><span data-stu-id="d114a-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="d114a-132">Teckenstorleken för innehållet.</span><span class="sxs-lookup"><span data-stu-id="d114a-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="d114a-133">Lägg till en textblockmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="d114a-133">Add a text block module to a page</span></span>

<span data-ttu-id="d114a-134">Om du vill lägga till en textblockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d114a-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d114a-135">Skapa en sidmall som har namnet **Innehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="d114a-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="d114a-136">I facket **Brödtext**, lägg till en **standardsida**-modul.</span><span class="sxs-lookup"><span data-stu-id="d114a-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="d114a-137">Avsluta redigeringen i mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="d114a-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="d114a-138">Använd den innehållsmall som du just skapade för att skapa en sida med namnet **Innehållssida**.</span><span class="sxs-lookup"><span data-stu-id="d114a-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="d114a-139">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="d114a-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="d114a-140">I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="d114a-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="d114a-141">I textblockmodulen, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="d114a-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="d114a-142">I egenskapsfönstret för textblockmodulen, lägg till text i fältet **RTF**.</span><span class="sxs-lookup"><span data-stu-id="d114a-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="d114a-143">Avsluta redigeringen av sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="d114a-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d114a-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d114a-144">Additional resources</span></span>

[<span data-ttu-id="d114a-145">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="d114a-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d114a-146">Annonsbanderollmodul</span><span class="sxs-lookup"><span data-stu-id="d114a-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="d114a-147">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="d114a-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="d114a-148">Innehållsblockmodul</span><span class="sxs-lookup"><span data-stu-id="d114a-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="d114a-149">Modul för videospelare</span><span class="sxs-lookup"><span data-stu-id="d114a-149">Video player module</span></span>](add-video-player.md)

