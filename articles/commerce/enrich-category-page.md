---
title: Utöka en kategorilandningssida
description: I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.
author: v-chgri
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
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fbcf6ec60723b726e022b4e17bbde4c903e5cb57
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238797"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="00de9-103">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="00de9-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="00de9-104">I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="00de9-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="00de9-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="00de9-105">Overview</span></span>

<span data-ttu-id="00de9-106">näthandel ger en standardsida för kategori landningssidor som används när kategoridata visas.</span><span class="sxs-lookup"><span data-stu-id="00de9-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="00de9-107">En standardkategorisida innehåller obligatoriska element, t.ex. förfinare, kategoriserad produktplacering, sorteringsalternativ, en alternativ sammanfattning och sidbrytningskontroller.</span><span class="sxs-lookup"><span data-stu-id="00de9-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="00de9-108">I stället för att använda standardkategorisidan kanske du vill använda en landningssida med "utökad" kategori som har mer innehåll och fler specifika element.</span><span class="sxs-lookup"><span data-stu-id="00de9-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="00de9-109">Ett typiskt berikande kan innebära att man lägger till kategorispecifikt marknadsföringsinnehåll på kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="00de9-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="00de9-110">Det här innehållet kan omfatta produktplacering i flera kategorier för säljsyfte, redaktionella listor, bilder, videor och annan text.</span><span class="sxs-lookup"><span data-stu-id="00de9-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="00de9-111">Du kan antingen ändra standardkategori sidan eller definiera en annan kategorisida för en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="00de9-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

<span data-ttu-id="00de9-113">I Commerce webbplatsskaparen innehåller sidan **produkter** en lista med kategorier från den kanal som har tilldelats webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="00de9-113">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="00de9-114">Om du har valt statusen **berikad** för en kategorisida har den kategorisidan berikats.</span><span class="sxs-lookup"><span data-stu-id="00de9-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="00de9-115">I annat fall används standardkategorisidan och innehållet för kategorin.</span><span class="sxs-lookup"><span data-stu-id="00de9-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="00de9-116">Du kan förhandsgranska både de berikade och icke-funktionella kategorisidorna för en kategori genom att markera kategorinamnet.</span><span class="sxs-lookup"><span data-stu-id="00de9-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="00de9-117">Om du vill utöka en kategorisida gör du följande.</span><span class="sxs-lookup"><span data-stu-id="00de9-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="00de9-118">På sidan **produkter** väljer du namnet på den kategori som du vill utöka kategorisidan för.</span><span class="sxs-lookup"><span data-stu-id="00de9-118">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="00de9-119">Standardkategorisidan för den valda kategorin öppnas i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="00de9-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="00de9-120">Välj **berika kategorisida**.</span><span class="sxs-lookup"><span data-stu-id="00de9-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="00de9-121">Välj en mall för den berikade kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="00de9-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="00de9-122">Om du bara gör mindre ändringar kan du välja standardkategorisidan.</span><span class="sxs-lookup"><span data-stu-id="00de9-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="00de9-123">Du kan också välja en specifik mall för kategorisidan.</span><span class="sxs-lookup"><span data-stu-id="00de9-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="00de9-124">När du väljer mallen öppnas sidredigeraren och den valda mallen används för att skapa en ny kategori sida för den valda kategorin.</span><span class="sxs-lookup"><span data-stu-id="00de9-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="00de9-125">Sidan är utcheckad till dig och du kan nu göra dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="00de9-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="00de9-126">Moduler som använder kategorispecifikationsdata använder data från den valda kategorin.</span><span class="sxs-lookup"><span data-stu-id="00de9-126">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="00de9-127">Inställningarna för den mall som du väljer avgör vilka ändringar du kan göra.</span><span class="sxs-lookup"><span data-stu-id="00de9-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="00de9-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="00de9-128">Additional resources</span></span>

[<span data-ttu-id="00de9-129">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="00de9-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="00de9-130">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="00de9-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="00de9-131">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="00de9-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="00de9-132">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="00de9-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="00de9-133">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="00de9-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="00de9-134">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="00de9-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="00de9-135">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="00de9-135">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="00de9-136">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="00de9-136">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]