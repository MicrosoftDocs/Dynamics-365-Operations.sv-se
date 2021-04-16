---
title: Lägga till en logotyp
description: I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797609"
---
# <a name="add-a-logo"></a><span data-ttu-id="8f5bb-103">Lägga till en logotyp</span><span class="sxs-lookup"><span data-stu-id="8f5bb-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f5bb-104">I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8f5bb-105">När du bygger din webbplats, en av de första sakerna som du förmodligen kommer att göra är att lägga ditt företag eller varumärke logotyp till webbplatsens rubrik.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="8f5bb-106">Dynamics 365 Commerce online modulbibliotek ger en modul som gör denna uppgift enkel.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="8f5bb-107">Du kan lägga till en logotyp direkt i en mall, layout eller sida.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="8f5bb-108">På så sätt kan du enkelt ändra logotypen som visas på specifika sidor eller grupper av sidor.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="8f5bb-109">Det här avsnittet beskriver dock de vanligaste scenariot där du lägger till din logotyp i ett sidhuvud fragment som kan återanvändas på alla sidor på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8f5bb-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8f5bb-110">Prerequisites</span></span>

<span data-ttu-id="8f5bb-111">Innan du kan lägga till en logotyp på alla sidor på webbplatsen måste du utföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="8f5bb-112">Överför din logotyp till mediebiblioteket.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="8f5bb-113">Skapa ett rubrikavsnitt.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-113">Create a header fragment.</span></span> <span data-ttu-id="8f5bb-114">Mer information om hur du skapar och använder fragment finns [arbeta med fragment](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="8f5bb-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="8f5bb-115">Inkludera rubrikavsnitt i mallen som webbplatsens sidor använder för layoutalternativ och modulalternativ.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="8f5bb-116">Mer information om hur mallar, se [Arbeta med mallar](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8f5bb-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="8f5bb-117">Lägga till en logotyp i ett rubrikavsnitt</span><span class="sxs-lookup"><span data-stu-id="8f5bb-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="8f5bb-118">Gör så här om du vill lägga till en logotyp i rubrikavsnitt för din webbplats.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="8f5bb-119">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="8f5bb-120">Markera det sidfragment som du skapade tidigare och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="8f5bb-121">Expandera modulen rubrik.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-121">Expand the header module.</span></span>
1. <span data-ttu-id="8f5bb-122">Ange en bild och en länk för logotypen i egenskapsfönstret för huvudmodulen.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="8f5bb-123">Spara rubrikfragmentet, slutför redigeringen och publicera det.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="8f5bb-124">När du har publicerat det uppdaterade rubrikavsnitt visas din logotyp på alla webbplatssidor som använder mallen som innehåller sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f5bb-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8f5bb-125">Additional resources</span></span>

[<span data-ttu-id="8f5bb-126">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="8f5bb-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="8f5bb-127">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="8f5bb-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="8f5bb-128">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="8f5bb-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="8f5bb-129">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="8f5bb-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="8f5bb-130">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="8f5bb-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="8f5bb-131">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="8f5bb-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="8f5bb-132">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="8f5bb-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
