---
title: Lägg till en logotyp
description: I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 073c3d6f8d5ee88d51efb41f6b9c1a204b82fa12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980317"
---
# <a name="add-a-logo"></a><span data-ttu-id="628fc-103">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="628fc-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="628fc-104">I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="628fc-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="628fc-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="628fc-105">Overview</span></span>

<span data-ttu-id="628fc-106">När du bygger din webbplats, en av de första sakerna som du förmodligen kommer att göra är att lägga ditt företag eller varumärke logotyp till webbplatsens rubrik.</span><span class="sxs-lookup"><span data-stu-id="628fc-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="628fc-107">Dynamics 365 Commerce online modulbibliotek ger en modul som gör denna uppgift enkel.</span><span class="sxs-lookup"><span data-stu-id="628fc-107">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="628fc-108">Du kan lägga till en logotyp direkt i en mall, layout eller sida.</span><span class="sxs-lookup"><span data-stu-id="628fc-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="628fc-109">På så sätt kan du enkelt ändra logotypen som visas på specifika sidor eller grupper av sidor.</span><span class="sxs-lookup"><span data-stu-id="628fc-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="628fc-110">Det här avsnittet beskriver dock de vanligaste scenariot där du lägger till din logotyp i ett sidhuvud fragment som kan återanvändas på alla sidor på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="628fc-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="628fc-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="628fc-111">Prerequisites</span></span>

<span data-ttu-id="628fc-112">Innan du kan lägga till en logotyp på alla sidor på webbplatsen måste du utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="628fc-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="628fc-113">Överför din logotyp till mediebiblioteket.</span><span class="sxs-lookup"><span data-stu-id="628fc-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="628fc-114">Skapa ett rubrikavsnitt.</span><span class="sxs-lookup"><span data-stu-id="628fc-114">Create a header fragment.</span></span> <span data-ttu-id="628fc-115">Mer information om hur du skapar och använder fragment finns [arbeta med fragment](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="628fc-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="628fc-116">Inkludera rubrikavsnitt i mallen som webbplatsens sidor använder för layoutalternativ och modulalternativ.</span><span class="sxs-lookup"><span data-stu-id="628fc-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="628fc-117">Mer information om hur mallar, se [Arbeta med mallar](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="628fc-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="628fc-118">Lägga till en logotyp i ett rubrikavsnitt</span><span class="sxs-lookup"><span data-stu-id="628fc-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="628fc-119">Gör så här om du vill lägga till en logotyp i rubrikavsnitt för din webbplats.</span><span class="sxs-lookup"><span data-stu-id="628fc-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="628fc-120">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="628fc-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="628fc-121">Markera det sidfragment som du skapade tidigare och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="628fc-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="628fc-122">Expandera modulen rubrik.</span><span class="sxs-lookup"><span data-stu-id="628fc-122">Expand the header module.</span></span>
1. <span data-ttu-id="628fc-123">Ange en bild och en länk för logotypen i egenskapsfönstret för huvudmodulen.</span><span class="sxs-lookup"><span data-stu-id="628fc-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="628fc-124">Spara rubrikfragmentet, slutför redigeringen och publicera det.</span><span class="sxs-lookup"><span data-stu-id="628fc-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="628fc-125">När du har publicerat det uppdaterade rubrikavsnitt visas din logotyp på alla webbplatssidor som använder mallen som innehåller sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="628fc-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="628fc-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="628fc-126">Additional resources</span></span>

[<span data-ttu-id="628fc-127">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="628fc-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="628fc-128">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="628fc-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="628fc-129">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="628fc-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="628fc-130">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="628fc-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="628fc-131">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="628fc-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="628fc-132">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="628fc-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="628fc-133">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="628fc-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

