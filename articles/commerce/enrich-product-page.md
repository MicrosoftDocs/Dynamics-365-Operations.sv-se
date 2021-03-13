---
title: Utöka en produktsida
description: I det här avsnittet beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fcb8eda188a6796282a7a800b87a68dfef9d7d62
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097348"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="ed659-103">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="ed659-103">Enrich a product page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ed659-104">I det här avsnittet beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed659-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ed659-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ed659-105">Overview</span></span>

<span data-ttu-id="ed659-106">Som standard använder webbplatsen en allmän sida för att visa produktdata.</span><span class="sxs-lookup"><span data-stu-id="ed659-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="ed659-107">Den här sidan innehåller grundläggande information om produkten och de kontroller som krävs för att sälja den.</span><span class="sxs-lookup"><span data-stu-id="ed659-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="ed659-108">Du kan dock komplettera den information som kommer från skalningsenhet för handel med ytterligare bilder eller text för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="ed659-108">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="ed659-109">Denna process kallas för att hantera produktsidan.</span><span class="sxs-lookup"><span data-stu-id="ed659-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="ed659-110">I många fall vill du använda särskilda ytterligare innehåll för dina produkter.</span><span class="sxs-lookup"><span data-stu-id="ed659-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="ed659-111">När du går till **Butik och handel** i utvecklingsverktyget visas en lista med produkter från den kanal som har tilldelats till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ed659-111">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="ed659-112">I den här listan visar kolumnen **berikad** om produktsidan för en produkt har berikats.</span><span class="sxs-lookup"><span data-stu-id="ed659-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="ed659-113">Om en bockmarkering visas i kolumnen finns en berikad produktsida för produkten.</span><span class="sxs-lookup"><span data-stu-id="ed659-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="ed659-114">Om ingen bockmarkering visas används produktens standardproduktsida och innehåll.</span><span class="sxs-lookup"><span data-stu-id="ed659-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="ed659-115">Du kan förhandsgranska både de berikade och icke-berikade produktsidorna genom att markera produktnamnet i listan.</span><span class="sxs-lookup"><span data-stu-id="ed659-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="ed659-116">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="ed659-116">Enrich a product page</span></span>

<span data-ttu-id="ed659-117">Om du vill utöka en produktsida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="ed659-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="ed659-118">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="ed659-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="ed659-119">I navigeringsfönstret till vänster, välj **Produkter**.</span><span class="sxs-lookup"><span data-stu-id="ed659-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="ed659-120">Välj en produkt som inte har någon berikad produktsida.</span><span class="sxs-lookup"><span data-stu-id="ed659-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="ed659-121">I åtgärdsfönstret, välj **Berika produktsida**.</span><span class="sxs-lookup"><span data-stu-id="ed659-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="ed659-122">Välj **PDP-mall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed659-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed659-123">I dispositionsträdet för sida till vänster expanderar du platsen **Huvud**.</span><span class="sxs-lookup"><span data-stu-id="ed659-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="ed659-124">Markera knappen med punkter (**...**) för platsen **Huvud** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="ed659-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ed659-125">Välj **Behållare 2** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed659-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed659-126">Markera knappen med punkter för **Behållare 2** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="ed659-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ed659-127">Välj **Funktion** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed659-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed659-128">I fönstret egenskaper till höger i fältet **oformaterad text** anger du den uppdaterade beskrivningen av produkten.</span><span class="sxs-lookup"><span data-stu-id="ed659-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="ed659-129">I fältet **Rubrik** anger du rubriktexten och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed659-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="ed659-130">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="ed659-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ed659-131">I fältet **kommentarer** anger du **Berika en produkt** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed659-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="ed659-132">Välj **Förhandsgranska** om du vill förhandsgranska den berikade produktsidan.</span><span class="sxs-lookup"><span data-stu-id="ed659-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="ed659-133">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="ed659-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="ed659-134">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="ed659-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed659-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ed659-135">Additional resources</span></span>

[<span data-ttu-id="ed659-136">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="ed659-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="ed659-137">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="ed659-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="ed659-138">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="ed659-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="ed659-139">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="ed659-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="ed659-140">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="ed659-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="ed659-141">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="ed659-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="ed659-142">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="ed659-142">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="ed659-143">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="ed659-143">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)
