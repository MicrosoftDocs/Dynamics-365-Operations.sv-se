---
title: Utöka en produktsida
description: I det här avsnittet beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d9c0f329d21cdda5c36a39a8c602d5925b720f52
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945753"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="507d8-103">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="507d8-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="507d8-104">I det här avsnittet beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="507d8-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="507d8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="507d8-105">Overview</span></span>

<span data-ttu-id="507d8-106">Som standard använder webbplatsen en allmän sida för att visa produktdata.</span><span class="sxs-lookup"><span data-stu-id="507d8-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="507d8-107">Den här sidan innehåller grundläggande information om produkten och de kontroller som krävs för att sälja den.</span><span class="sxs-lookup"><span data-stu-id="507d8-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="507d8-108">Du kan dock komplettera den information som kommer från detaljhandelsservern med ytterligare bilder eller text för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="507d8-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="507d8-109">Denna process kallas för att hantera produktsidan.</span><span class="sxs-lookup"><span data-stu-id="507d8-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="507d8-110">I många fall vill du använda särskilda ytterligare innehåll för dina produkter.</span><span class="sxs-lookup"><span data-stu-id="507d8-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="507d8-111">När du går till **detaljhandel** i utvecklingsverktyget visas en lista med produkter från den kanal som har tilldelats till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="507d8-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="507d8-112">I den här listan visar kolumnen **berikad** om produktsidan för en produkt har berikats.</span><span class="sxs-lookup"><span data-stu-id="507d8-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="507d8-113">Om en bockmarkering visas i kolumnen finns en berikad produktsida för produkten.</span><span class="sxs-lookup"><span data-stu-id="507d8-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="507d8-114">Om ingen bockmarkering visas används produktens standardproduktsida och innehåll.</span><span class="sxs-lookup"><span data-stu-id="507d8-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="507d8-115">Du kan förhandsgranska både de berikade och icke-berikade produktsidorna genom att markera produktnamnet i listan.</span><span class="sxs-lookup"><span data-stu-id="507d8-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="507d8-116">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="507d8-116">Enrich a product page</span></span>

<span data-ttu-id="507d8-117">Om du vill utöka en produktsida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="507d8-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="507d8-118">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="507d8-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="507d8-119">I navigeringsfönstret till vänster, välj **Produkter**.</span><span class="sxs-lookup"><span data-stu-id="507d8-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="507d8-120">Välj en produkt som inte har någon berikad produktsida.</span><span class="sxs-lookup"><span data-stu-id="507d8-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="507d8-121">I åtgärdsfönstret, välj **Berika produktsida**.</span><span class="sxs-lookup"><span data-stu-id="507d8-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="507d8-122">Välj **PDP-mall**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="507d8-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="507d8-123">I dispositionsträdet för sida till vänster expanderar du platsen **Huvud**.</span><span class="sxs-lookup"><span data-stu-id="507d8-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="507d8-124">Markera knappen med punkter (**...**) för platsen **Huvud** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="507d8-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="507d8-125">Välj **Behållare 2**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="507d8-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="507d8-126">Markera knappen med punkter för **Behållare 2** och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="507d8-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="507d8-127">Välj **Funktion**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="507d8-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="507d8-128">I fönstret egenskaper till höger i fältet **oformaterad text** anger du den uppdaterade beskrivningen av produkten.</span><span class="sxs-lookup"><span data-stu-id="507d8-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="507d8-129">I fältet **Rubrik** anger du rubriktexten och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="507d8-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="507d8-130">Välj **spara**och välj sedan **checka in**.</span><span class="sxs-lookup"><span data-stu-id="507d8-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="507d8-131">I fältet **kommentarer** anger du **Berika en produkt** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="507d8-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="507d8-132">Välj **Förhandsgranska** om du vill förhandsgranska den berikade produktsidan.</span><span class="sxs-lookup"><span data-stu-id="507d8-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="507d8-133">När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="507d8-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="507d8-134">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="507d8-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="507d8-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="507d8-135">Additional resources</span></span>

[<span data-ttu-id="507d8-136">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="507d8-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="507d8-137">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="507d8-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="507d8-138">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="507d8-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="507d8-139">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="507d8-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="507d8-140">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="507d8-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="507d8-141">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="507d8-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="507d8-142">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="507d8-142">Verify page content accessibility</span></span>](verify-accessibility.md)
