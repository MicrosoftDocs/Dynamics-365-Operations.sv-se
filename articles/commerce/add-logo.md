---
title: Lägg till en logotyp
description: I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914636"
---
# <a name="add-a-logo"></a><span data-ttu-id="e18b0-103">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="e18b0-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e18b0-104">I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e18b0-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e18b0-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e18b0-105">Overview</span></span>

<span data-ttu-id="e18b0-106">När du bygger din webbplats, en av de första sakerna som du förmodligen kommer att göra är att lägga ditt företag eller varumärke logotyp till webbplatsens rubrik.</span><span class="sxs-lookup"><span data-stu-id="e18b0-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="e18b0-107">Dynamics 365 Commerce online startpaketet ger en modul som gör denna uppgift enkel.</span><span class="sxs-lookup"><span data-stu-id="e18b0-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="e18b0-108">Du kan lägga till en logotyp direkt i en mall, layout eller sida.</span><span class="sxs-lookup"><span data-stu-id="e18b0-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="e18b0-109">På så sätt kan du enkelt ändra logotypen som visas på specifika sidor eller grupper av sidor.</span><span class="sxs-lookup"><span data-stu-id="e18b0-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="e18b0-110">Det här avsnittet beskriver dock de vanligaste scenariot där du lägger till din logotyp i ett sidhuvud fragment som kan återanvändas på alla sidor på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="e18b0-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e18b0-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e18b0-111">Prerequisites</span></span>

<span data-ttu-id="e18b0-112">Innan du kan lägga till en logotyp på alla sidor på webbplatsen måste du utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="e18b0-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="e18b0-113">Ladda upp din logotyp till Digital Assets Manager, som du kan komma åt från sidan **tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="e18b0-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="e18b0-114">Skapa ett rubrikavsnitt.</span><span class="sxs-lookup"><span data-stu-id="e18b0-114">Create a header fragment.</span></span> <span data-ttu-id="e18b0-115">Mer information om hur du skapar och använder fragment finns [arbeta med fragment](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="e18b0-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="e18b0-116">Inkludera rubrikavsnitt i mallen som webbplatsens sidor använder för layoutalternativ och modulalternativ.</span><span class="sxs-lookup"><span data-stu-id="e18b0-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="e18b0-117">Mer information om hur mallar, se [Arbeta med mallar](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e18b0-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="e18b0-118">Lägga till en logotyp i ett rubrikavsnitt</span><span class="sxs-lookup"><span data-stu-id="e18b0-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="e18b0-119">Gör så här om du vill lägga till en logotyp i rubrikavsnitt för din webbplats.</span><span class="sxs-lookup"><span data-stu-id="e18b0-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="e18b0-120">Välj **fragment** i navigeringsfönstret till vänster och välj sedan det rubrikavsnitt som du skapade.</span><span class="sxs-lookup"><span data-stu-id="e18b0-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="e18b0-121">Välj **Checka ut**.</span><span class="sxs-lookup"><span data-stu-id="e18b0-121">Select **Check out**.</span></span>
3. <span data-ttu-id="e18b0-122">Expandera facket **rubrik** och facket **logotyp**.</span><span class="sxs-lookup"><span data-stu-id="e18b0-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="e18b0-123">Markera knappen med punkter (**...**) för platsen **Logotyp** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="e18b0-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="e18b0-124">Välj logotypmodul.</span><span class="sxs-lookup"><span data-stu-id="e18b0-124">Select the logo module.</span></span>
6. <span data-ttu-id="e18b0-125">Konfigurera logotypmodulen så att den visar din logotyp i fönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="e18b0-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="e18b0-126">Spara rubrikfragmentet, checka in det och publicera det.</span><span class="sxs-lookup"><span data-stu-id="e18b0-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="e18b0-127">När du har publicerat det uppdaterade rubrikavsnitt visas din logotyp på alla webbplatssidor som använder mallen som innehåller sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="e18b0-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e18b0-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e18b0-128">Additional resources</span></span>

[<span data-ttu-id="e18b0-129">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="e18b0-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e18b0-130">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="e18b0-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e18b0-131">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="e18b0-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e18b0-132">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="e18b0-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e18b0-133">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="e18b0-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e18b0-134">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="e18b0-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="e18b0-135">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="e18b0-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

