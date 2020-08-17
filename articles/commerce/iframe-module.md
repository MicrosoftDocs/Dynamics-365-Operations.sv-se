---
title: Iframe-modul
description: Det här avsnittet handlar om iframe-modulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0616a772a416a7c9d9756a840c93b8601c08c3d0
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "3647051"
---
# <a name="iframe-module"></a><span data-ttu-id="504b3-103">Iframe-modul</span><span class="sxs-lookup"><span data-stu-id="504b3-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="504b3-104">Det här avsnittet handlar om iframe-modulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="504b3-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="504b3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="504b3-105">Overview</span></span>

<span data-ttu-id="504b3-106">En iframe-modul innehåller en iframe (infogad ram) som är värd för det externa innehållet på en webbplats.</span><span class="sxs-lookup"><span data-stu-id="504b3-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="504b3-107">Det kan till exempel användas för att vara värd för ett YouTube-video eller PDF-filgranskare på valfri webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="504b3-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="504b3-108">En iframe-modul kräver en mål-URL.</span><span class="sxs-lookup"><span data-stu-id="504b3-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="504b3-109">Sedan lagras innehållet på målsidan i ett HTML **iframe**-element.</span><span class="sxs-lookup"><span data-stu-id="504b3-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="504b3-110">Externa URL:er måste finnas i listan över tillåtna (även kallat "vit lista") per webbplatsens innehålls säkerhetsprincip (CSP).</span><span class="sxs-lookup"><span data-stu-id="504b3-110">External URLs must be on the allow list (also known as a "whitelist") per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="504b3-111">För iframe-innehåll ska URL:er tillåtas genom att använda direktivet **frame-ancestor**.</span><span class="sxs-lookup"><span data-stu-id="504b3-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="504b3-112">Mer information finns i [hantera säkerhetsprinciper för innehåll (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="504b3-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

<span data-ttu-id="504b3-113">I följande bild visas exempel på iframe-moduler som visar externa videoklipp på webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="504b3-113">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Exempel på iframe-moduler som visar externa videoklipp](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="504b3-115">Egenskaper för iframe-modul</span><span class="sxs-lookup"><span data-stu-id="504b3-115">Iframe module properties</span></span>

| <span data-ttu-id="504b3-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="504b3-116">Property name</span></span>             | <span data-ttu-id="504b3-117">Värde</span><span class="sxs-lookup"><span data-stu-id="504b3-117">Value</span></span>                 | <span data-ttu-id="504b3-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="504b3-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="504b3-119">Rubrik</span><span class="sxs-lookup"><span data-stu-id="504b3-119">Heading</span></span> | <span data-ttu-id="504b3-120">Text</span><span class="sxs-lookup"><span data-stu-id="504b3-120">Text</span></span> | <span data-ttu-id="504b3-121">Rubriken för modulen.</span><span class="sxs-lookup"><span data-stu-id="504b3-121">The heading for the module.</span></span> |
| <span data-ttu-id="504b3-122">Mål-URL</span><span class="sxs-lookup"><span data-stu-id="504b3-122">Target URL</span></span> | <span data-ttu-id="504b3-123">URL</span><span class="sxs-lookup"><span data-stu-id="504b3-123">URL</span></span> | <span data-ttu-id="504b3-124">URL:en som finns i modulen.</span><span class="sxs-lookup"><span data-stu-id="504b3-124">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="504b3-125">Höjd</span><span class="sxs-lookup"><span data-stu-id="504b3-125">Height</span></span> | <span data-ttu-id="504b3-126">Antal eller procent</span><span class="sxs-lookup"><span data-stu-id="504b3-126">Number or percentage</span></span> | <span data-ttu-id="504b3-127">Modulens höjd, i bildpunkter eller som ett procenttal.</span><span class="sxs-lookup"><span data-stu-id="504b3-127">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="504b3-128">Till exempel kommer värdet **100** att behandlas som ett antal bildpunkter och värdet **100 %** behandlas som en procentsats.</span><span class="sxs-lookup"><span data-stu-id="504b3-128">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="504b3-129">Aria-etikett</span><span class="sxs-lookup"><span data-stu-id="504b3-129">Aria label</span></span> | <span data-ttu-id="504b3-130">Text</span><span class="sxs-lookup"><span data-stu-id="504b3-130">Text</span></span> | <span data-ttu-id="504b3-131">En ARIA-etikett (Accessible Rich Internet Applications) kan definieras för hjälpmedelsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="504b3-131">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="504b3-132">Lägg till iframe-modul till en sida</span><span class="sxs-lookup"><span data-stu-id="504b3-132">Add an iframe module to a page</span></span>

<span data-ttu-id="504b3-133">Om du vill lägga till en iframe-modul på en sida för att visa en extern video följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="504b3-133">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="504b3-134">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="504b3-134">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="504b3-135">I dialogrutan **Ny mal** under **Mallnamn**, ange **Marknadsföringsmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="504b3-135">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="504b3-136">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="504b3-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="504b3-137">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="504b3-137">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="504b3-138">I dialogrutan **Välj en mall** väljer du en **Marknadsföringsmall**.</span><span class="sxs-lookup"><span data-stu-id="504b3-138">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="504b3-139">Under **sidnamn**, ange **Marknadsföringssida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="504b3-139">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="504b3-140">I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="504b3-140">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="504b3-141">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="504b3-141">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="504b3-142">I modulens egenskapsfönster, ange värdet **Bredd** till **Fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="504b3-142">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="504b3-143">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="504b3-143">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="504b3-144">I dialogrutan **Lägg till modul**, välj modulen **iframe** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="504b3-144">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="504b3-145">I modulens egenskapsfönster, ange värdet **Mål-URL** till en extern URL för en video.</span><span class="sxs-lookup"><span data-stu-id="504b3-145">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="504b3-146">Ange andra egenskaper **rubrik** och **höjd**, efter behov.</span><span class="sxs-lookup"><span data-stu-id="504b3-146">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="504b3-147">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="504b3-147">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="504b3-148">Gå till marknadsföringssidan på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="504b3-148">Go to the marketing page on your site.</span></span> <span data-ttu-id="504b3-149">Du bör se att videon återges i iframe-modulen.</span><span class="sxs-lookup"><span data-stu-id="504b3-149">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="504b3-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="504b3-150">Additional resources</span></span>

[<span data-ttu-id="504b3-151">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="504b3-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="504b3-152">Hantera säkerhetspolicy för innehåll (CSP)</span><span class="sxs-lookup"><span data-stu-id="504b3-152">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
