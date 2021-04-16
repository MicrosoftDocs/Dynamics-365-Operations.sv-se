---
title: Utöka en kategorilandningssida
description: I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5e18439fc0e91619cade33b83b87be0d5c4d1040
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799021"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="4e7fd-103">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="4e7fd-103">Enrich a category landing page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4e7fd-104">I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4e7fd-105">näthandel ger en standardsida för kategori landningssidor som används när kategoridata visas.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-105">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="4e7fd-106">En standardkategorisida innehåller obligatoriska element, t.ex. förfinare, kategoriserad produktplacering, sorteringsalternativ, en alternativ sammanfattning och sidbrytningskontroller.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-106">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="4e7fd-107">I stället för att använda standardkategorisidan kanske du vill använda en landningssida med "utökad" kategori som har mer innehåll och fler specifika element.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-107">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="4e7fd-108">Ett typiskt berikande kan innebära att man lägger till kategorispecifikt marknadsföringsinnehåll på kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-108">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="4e7fd-109">Det här innehållet kan omfatta produktplacering i flera kategorier för säljsyfte, redaktionella listor, bilder, videor och annan text.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-109">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="4e7fd-110">Du kan antingen ändra standardkategori sidan eller definiera en annan kategorisida för en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-110">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

<span data-ttu-id="4e7fd-112">I Commerce webbplatsskaparen innehåller sidan **produkter** en lista med kategorier från den kanal som har tilldelats webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-112">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="4e7fd-113">Om du har valt statusen **berikad** för en kategorisida har den kategorisidan berikats.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-113">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="4e7fd-114">I annat fall används standardkategorisidan och innehållet för kategorin.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-114">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="4e7fd-115">Du kan förhandsgranska både de berikade och icke-funktionella kategorisidorna för en kategori genom att markera kategorinamnet.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-115">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="4e7fd-116">Om du vill utöka en kategorisida gör du följande.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-116">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="4e7fd-117">På sidan **produkter** väljer du namnet på den kategori som du vill utöka kategorisidan för.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-117">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="4e7fd-118">Standardkategorisidan för den valda kategorin öppnas i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-118">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="4e7fd-119">Välj **berika kategorisida**.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-119">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="4e7fd-120">Välj en mall för den berikade kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-120">Select a template for the enriched category page.</span></span> <span data-ttu-id="4e7fd-121">Om du bara gör mindre ändringar kan du välja standardkategorisidan.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-121">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="4e7fd-122">Du kan också välja en specifik mall för kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-122">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="4e7fd-123">När du väljer mallen öppnas sidredigeraren och den valda mallen används för att skapa en ny kategori sida för den valda kategorin.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-123">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="4e7fd-124">Sidan är utcheckad till dig och du kan nu göra dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-124">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="4e7fd-125">Moduler som använder kategorispecifikationsdata använder data från den valda kategorin.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-125">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="4e7fd-126">Inställningarna för den mall som du väljer avgör vilka ändringar du kan göra.</span><span class="sxs-lookup"><span data-stu-id="4e7fd-126">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e7fd-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4e7fd-127">Additional resources</span></span>

[<span data-ttu-id="4e7fd-128">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="4e7fd-128">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="4e7fd-129">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="4e7fd-129">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="4e7fd-130">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="4e7fd-130">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4e7fd-131">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="4e7fd-131">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4e7fd-132">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="4e7fd-132">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4e7fd-133">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="4e7fd-133">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="4e7fd-134">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="4e7fd-134">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="4e7fd-135">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="4e7fd-135">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
