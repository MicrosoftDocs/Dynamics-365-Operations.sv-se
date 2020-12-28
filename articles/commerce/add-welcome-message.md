---
title: Lägg till ett välkomstmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.
author: psimolin
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: d2a125b4e71016ad620f128af2e3c9f29aa04f4c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415784"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="26779-103">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="26779-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="26779-104">I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="26779-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="26779-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="26779-105">Overview</span></span>

<span data-ttu-id="26779-106">Ett välkomstmeddelande på din näthandelswebbplats kan informera besökare om pågående försäljning, webbplatsuppdateringar eller tillgänglighet för säsongsinsamlingar.</span><span class="sxs-lookup"><span data-stu-id="26779-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="26779-107">Välkomstmeddelandet ställs in med hjälp av notifieringsmodul.</span><span class="sxs-lookup"><span data-stu-id="26779-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="26779-108">Aviseringsmodulen ska läggas till platsen **Fel- och informationsmeddelande** för huvudfragment.</span><span class="sxs-lookup"><span data-stu-id="26779-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="26779-109">I notifieringsmodulen kan du ange den text som visas, textfärgen och justeringen.</span><span class="sxs-lookup"><span data-stu-id="26779-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="26779-110">Du kan också ange om besökare på webbplatsen kan stänga meddelandet.</span><span class="sxs-lookup"><span data-stu-id="26779-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="26779-111">När ett välkomstmeddelande läggs till i ett delat rubrikavsnitt visas det på alla sidor som använder mallen där det delade rubrikavsnittet används.</span><span class="sxs-lookup"><span data-stu-id="26779-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="26779-112">Gör så här om du vill lägga till ett välkomstmeddelande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="26779-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="26779-113">I Commerce webbplatsskaparen, gå till din webbplats.</span><span class="sxs-lookup"><span data-stu-id="26779-113">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="26779-114">Välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="26779-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="26779-115">Välj det rubrikavsnitt som meddelandet ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="26779-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="26779-116">Expandera **fel-/informationsmeddelanden** i dispositionsträdet.</span><span class="sxs-lookup"><span data-stu-id="26779-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="26779-117">Markera notifieringsmodulen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="26779-117">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="26779-118">Om det inte redan finns en notifieringsregel väljer du först ellipsknappen-knappen (**...**) bredvid **fel-/informationsmeddelanden** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="26779-118">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="26779-119">I egenskapsfönstret till höger, på fliken **Data** välj **Lägg till datakälla** och sedan **Innehåll**.</span><span class="sxs-lookup"><span data-stu-id="26779-119">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="26779-120">I fältet **Inmatningstext** ange texten för välkomstmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="26779-120">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="26779-121">Välj **Spara**, välj **Slutför redigering** för att checka in rubrikavsnittet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="26779-121">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="26779-122">Välkomstmeddelandet visas nu överst på varje webbplatssida där det valda rubrikavsnittet används.</span><span class="sxs-lookup"><span data-stu-id="26779-122">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="26779-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="26779-123">Additional resources</span></span>

[<span data-ttu-id="26779-124">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="26779-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="26779-125">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="26779-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="26779-126">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="26779-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="26779-127">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="26779-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="26779-128">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="26779-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="26779-129">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="26779-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="26779-130">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="26779-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

