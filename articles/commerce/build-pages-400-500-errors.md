---
title: Bygg anpassade svarssidor för felstatuskod 4xx/5xx
description: I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 060f5e5616624279711f61f582e6a898c7eb7785
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269554"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="52473-103">Bygg anpassade svarssidor för felstatuskod 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="52473-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="52473-104">I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="52473-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="52473-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="52473-105">Overview</span></span>

<span data-ttu-id="52473-106">Om en begäran misslyckas utfärdar servern HTTP statuskodfelsvar.</span><span class="sxs-lookup"><span data-stu-id="52473-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="52473-107">Statuskoden 404 fångas in och returneras om en sida inte hittas och statuskoden 500 fångas in och returneras om ett serverfel uppstår.</span><span class="sxs-lookup"><span data-stu-id="52473-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="52473-108">I Dynamics 365 Commerce kan programanvändare skapa anpassade statuskodsidor för felsvar som visas för användarna för dessa statuskodfelsvar.</span><span class="sxs-lookup"><span data-stu-id="52473-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="52473-109">Skapa en sida för statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="52473-109">Build a status code error response page</span></span>

<span data-ttu-id="52473-110">Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="52473-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="52473-111">Logga in på i din föredragna webbläsare till Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="52473-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="52473-112">Välj den webbplats som du vill skapa en 4xx/5xx-sida för felstatuskoden för.</span><span class="sxs-lookup"><span data-stu-id="52473-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="52473-113">Skapa mallen</span><span class="sxs-lookup"><span data-stu-id="52473-113">Build the template</span></span>

<span data-ttu-id="52473-114">Börja skapa mallen för sidan med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="52473-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="52473-115">Gå till **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="52473-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="52473-116">Skapa en ny sidmall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="52473-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="52473-117">I dialogrutan **Ny mall** under **Mallnamn**, ange ett namn för den nya mallen och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="52473-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="52473-118">Skapa mallen, baserat på strukturen som du vill att sidan med statuskodfelsvar ska ha.</span><span class="sxs-lookup"><span data-stu-id="52473-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="52473-119">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="52473-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="52473-120">Skapa en sida för statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="52473-120">Build the status code error response page</span></span>

<span data-ttu-id="52473-121">Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="52473-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="52473-122">Gå till **sidor**.</span><span class="sxs-lookup"><span data-stu-id="52473-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="52473-123">Klicka på **Nytt** för att skapa en sida.</span><span class="sxs-lookup"><span data-stu-id="52473-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="52473-124">I dialogrutan **Välj en mall**, välj en mall och sedan under **Sidnamn**, ange ett namn för sida för statuskodfelsvar.</span><span class="sxs-lookup"><span data-stu-id="52473-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="52473-125">Lämna fältet **Sid-URL** tom.</span><span class="sxs-lookup"><span data-stu-id="52473-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="52473-126">Skapa sidan.</span><span class="sxs-lookup"><span data-stu-id="52473-126">Build the page.</span></span>
1. <span data-ttu-id="52473-127">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="52473-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="52473-128">Du kan skapa separata sidor för statuskodfelsvar för 4xx och 5xx statuskodfel.</span><span class="sxs-lookup"><span data-stu-id="52473-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="52473-129">Du kan också använda samma allmänna sida för statuskodfel för båda felkategorierna.</span><span class="sxs-lookup"><span data-stu-id="52473-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="52473-130">Ställa in en omdirigering för sidan med statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="52473-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="52473-131">För att ställa in omdirigering för sidan med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="52473-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="52473-132">Gå till **URL:ar \> Ny \> Ny alias** och välj sidan för statuskodfelsvar som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="52473-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="52473-133">I fältet **Alias** anger du antingen **standard-4xx** eller **standard-5xx**, beroende på sidan för statuskodfelsvar som du konfigurerar en omdirigering för.</span><span class="sxs-lookup"><span data-stu-id="52473-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="52473-134">Dessa alias måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="52473-134">These aliases must be published.</span></span> <span data-ttu-id="52473-135">Annars fungerar inte omdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="52473-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="52473-136">Gör länken genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="52473-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="52473-137">Om du använder en enstaka statuskodsida med felsvar för båda felkategorierna upprepar du proceduren för att länka ett alias för den andra felkategorin till samma sida.</span><span class="sxs-lookup"><span data-stu-id="52473-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52473-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="52473-138">Additional resources</span></span>

[<span data-ttu-id="52473-139">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="52473-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="52473-140">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="52473-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="52473-141">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="52473-141">Create a page URL</span></span>](create-page-url.md)
