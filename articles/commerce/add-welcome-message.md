---
title: Lägg till ett välkomstmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.
author: psimolin
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4e9deeeaf491b77700ba0833e429f05d376a4392
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914526"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="2555d-103">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="2555d-103">Add a welcome message</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2555d-104">I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2555d-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="2555d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="2555d-105">Overview</span></span>

<span data-ttu-id="2555d-106">Ett välkomstmeddelande på din e-handelswebbplats kan informera besökare om pågående försäljning, webbplatsuppdateringar eller tillgänglighet för säsongsinsamlingar.</span><span class="sxs-lookup"><span data-stu-id="2555d-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="2555d-107">Välkomstmeddelandet ställs in med hjälp av notifieringsmodul.</span><span class="sxs-lookup"><span data-stu-id="2555d-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="2555d-108">Aviseringsmodulen ska läggas till platsen **Fel- och informationsmeddelande** för huvudfragment.</span><span class="sxs-lookup"><span data-stu-id="2555d-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="2555d-109">I notifieringsmodulen kan du ange den text som visas, textfärgen och justeringen.</span><span class="sxs-lookup"><span data-stu-id="2555d-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="2555d-110">Du kan också ange om besökare på webbplatsen kan stänga meddelandet.</span><span class="sxs-lookup"><span data-stu-id="2555d-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="2555d-111">När ett välkomstmeddelande läggs till i ett delat rubrikavsnitt visas det på alla sidor som använder mallen där det delade rubrikavsnittet används.</span><span class="sxs-lookup"><span data-stu-id="2555d-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="2555d-112">Gör så här om du vill lägga till ett välkomstmeddelande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="2555d-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="2555d-113">I Dynamics 365 Commerce gå till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2555d-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="2555d-114">Välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="2555d-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="2555d-115">Välj det rubrikavsnitt som meddelandet ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="2555d-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="2555d-116">Expandera **fel-/informationsmeddelanden** i dispositionsträdet.</span><span class="sxs-lookup"><span data-stu-id="2555d-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="2555d-117">Välj notifieringsmodul.</span><span class="sxs-lookup"><span data-stu-id="2555d-117">Select the alert module.</span></span>

    <span data-ttu-id="2555d-118">Om det inte redan finns en notifieringsregel väljer du ellipsknappen-knappen (**...**) bredvid **fel-/informationsmeddelanden** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2555d-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="2555d-119">Markera notifieringsmodulen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2555d-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="2555d-120">I egenskapsfönstret till höger, på fliken **Data** välj **Lägg till datakälla** och sedan **Innehåll**.</span><span class="sxs-lookup"><span data-stu-id="2555d-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="2555d-121">I fältet **Inmatningstext** ange texten för välkomstmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="2555d-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="2555d-122">Spara rubrikfragmentet, checka in det och publicera det.</span><span class="sxs-lookup"><span data-stu-id="2555d-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="2555d-123">Välkomstmeddelandet visas nu överst på varje webbplatssida där det valda rubrikavsnittet används.</span><span class="sxs-lookup"><span data-stu-id="2555d-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2555d-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2555d-124">Additional resources</span></span>

[<span data-ttu-id="2555d-125">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="2555d-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="2555d-126">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="2555d-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="2555d-127">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="2555d-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="2555d-128">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="2555d-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="2555d-129">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="2555d-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="2555d-130">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="2555d-130">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="2555d-131">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="2555d-131">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

