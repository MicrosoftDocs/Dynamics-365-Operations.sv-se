---
title: Bygg anpassade svarssidor för felstatuskod 4xx/5xx
description: I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001158"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="84ce5-103">Bygg anpassade svarssidor för felstatuskod 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="84ce5-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="84ce5-104">I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="84ce5-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="84ce5-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="84ce5-105">Overview</span></span>

<span data-ttu-id="84ce5-106">Om en begäran misslyckas utfärdar servern HTTP statuskodfelsvar.</span><span class="sxs-lookup"><span data-stu-id="84ce5-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="84ce5-107">Statuskoden 404 fångas in och returneras om en sida inte hittas och statuskoden 500 fångas in och returneras om ett serverfel uppstår.</span><span class="sxs-lookup"><span data-stu-id="84ce5-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="84ce5-108">I Dynamics 365 Commerce kan programanvändare skapa anpassade statuskodsidor för felsvar som visas för användarna för dessa statuskodfelsvar.</span><span class="sxs-lookup"><span data-stu-id="84ce5-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="84ce5-109">Skapa en sida för statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="84ce5-109">Build a status code error response page</span></span>

<span data-ttu-id="84ce5-110">Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="84ce5-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="84ce5-111">Logga in på i din föredragna webbläsare till Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="84ce5-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="84ce5-112">Välj den webbplats som du vill skapa en 4xx/5xx-sida för felstatuskoden för.</span><span class="sxs-lookup"><span data-stu-id="84ce5-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="84ce5-113">Skapa mallen</span><span class="sxs-lookup"><span data-stu-id="84ce5-113">Build the template</span></span>

<span data-ttu-id="84ce5-114">Börja skapa mallen för sidan med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="84ce5-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="84ce5-115">Gå till **Mallar \> Ny mall**.</span><span class="sxs-lookup"><span data-stu-id="84ce5-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="84ce5-116">Namnge den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="84ce5-116">Name the new template.</span></span>
1. <span data-ttu-id="84ce5-117">Skapa mallen, baserat på strukturen som du vill att sidan med statuskodfelsvar ska ha.</span><span class="sxs-lookup"><span data-stu-id="84ce5-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="84ce5-118">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="84ce5-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="84ce5-119">Skapa en sida för statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="84ce5-119">Build the status code error response page</span></span>

<span data-ttu-id="84ce5-120">Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="84ce5-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="84ce5-121">Gå till **Sidor \> Ny sida**.</span><span class="sxs-lookup"><span data-stu-id="84ce5-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="84ce5-122">Namnge sidan för statusfelkodsvar men ange **inte** fältet **URL**.</span><span class="sxs-lookup"><span data-stu-id="84ce5-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="84ce5-123">Skapa sidan.</span><span class="sxs-lookup"><span data-stu-id="84ce5-123">Build the page.</span></span>
1. <span data-ttu-id="84ce5-124">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="84ce5-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="84ce5-125">Du kan skapa separata sidor för statuskodfelsvar för 4xx och 5xx statuskodfel.</span><span class="sxs-lookup"><span data-stu-id="84ce5-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="84ce5-126">Du kan också använda samma allmänna sida för statuskodfel för båda felkategorierna.</span><span class="sxs-lookup"><span data-stu-id="84ce5-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="84ce5-127">Ställa in en omdirigering för sidan med statuskodfelsvar</span><span class="sxs-lookup"><span data-stu-id="84ce5-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="84ce5-128">För att ställa in omdirigering för sidan med statuskodfelsvar enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="84ce5-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="84ce5-129">Gå till **URL:ar \> Ny \> Ny alias** och välj sidan för statuskodfelsvar som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="84ce5-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="84ce5-130">I fältet **Alias** anger du antingen **standard-4xx** eller **standard-5xx**, beroende på sidan för statuskodfelsvar som du konfigurerar en omdirigering för.</span><span class="sxs-lookup"><span data-stu-id="84ce5-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="84ce5-131">Dessa alias måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="84ce5-131">These aliases must be published.</span></span> <span data-ttu-id="84ce5-132">Annars fungerar inte omdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="84ce5-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="84ce5-133">Gör länken genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="84ce5-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="84ce5-134">Om du använder en enstaka statuskodsida med felsvar för båda felkategorierna upprepar du proceduren för att länka ett alias för den andra felkategorin till samma sida.</span><span class="sxs-lookup"><span data-stu-id="84ce5-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="84ce5-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="84ce5-135">Additional resources</span></span>

[<span data-ttu-id="84ce5-136">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="84ce5-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="84ce5-137">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="84ce5-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="84ce5-138">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="84ce5-138">Create a page URL</span></span>](create-page-url.md)
