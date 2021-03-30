---
title: Kontrollera tillgängligheten för sidinnehåll
description: I det här avsnittet beskrivs hur du kontrollerar tillgängligheten för sidinnehåll i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 186044fc7a360f227cecffb39bad0e225245dd4d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210981"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="5fcc1-103">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="5fcc1-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5fcc1-104">I det här avsnittet beskrivs hur du kontrollerar tillgängligheten för sidinnehåll i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5fcc1-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5fcc1-105">Overview</span></span>

<span data-ttu-id="5fcc1-106">När du är klar med att ändra en sida bör du se till att innehållet är tillgängligt för alla på webben.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="5fcc1-107">I handelsredigeringsverktyg kan du enkelt kontrollera tillgängligheten för sidans innehåll med hjälp av den integrerade [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="5fcc1-108">Den här tjänsten verifierar sidans innehåll mot de senaste [tillgänglighetsriktlinjerna för World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="5fcc1-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="5fcc1-109">[Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integreringen måste vara aktiverad på klient- eller platsnivå innan du kan använda den.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="5fcc1-110">Aktivera Microsoft Accessibility Insights för alla webbplatser i din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="5fcc1-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="5fcc1-111">Gör så här om [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integrering för alla Commerce-webbplatser i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5fcc1-112">För att komma åt klientinställningar måste du vara inloggad på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="5fcc1-113">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="5fcc1-114">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="5fcc1-115">Under **innehavarinställningar** väljer du **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="5fcc1-116">Ställ in alternativet **Hjälpmedelskontroll** till **på**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="5fcc1-117">Aktivera Microsoft Accessibility Insights för en enskild webbplats</span><span class="sxs-lookup"><span data-stu-id="5fcc1-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="5fcc1-118">Gör så här om [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integrering för en enda Commerce-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="5fcc1-119">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="5fcc1-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="5fcc1-120">I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="5fcc1-121">Under **Webbplatsinställningar** väljer du **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="5fcc1-122">Ställ in alternativet **Hjälpmedelskontroll** till **på**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="5fcc1-123">Kontrollera tillgängligheten för innehållet på startsidan</span><span class="sxs-lookup"><span data-stu-id="5fcc1-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="5fcc1-124">Om du vill använda den integrerade tjänsten [Microsoft Accessibility Insights](https://accessibilityinsights.io/) för att skanna och verifiera innehållet på din startsida i Commerce.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="5fcc1-125">Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="5fcc1-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="5fcc1-126">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="5fcc1-127">Sök och välj startsidan för att öppna den i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="5fcc1-128">Klicka på **Hjälpmedelskontroll** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="5fcc1-129">Sidan **Hjälpmedelskontroll** visas.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="5fcc1-130">När skanningen är klar granskar du innehållet i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="5fcc1-131">Om några kontroller misslyckades markerar du varje objekt som har misslyckats för att expandera det så att du kan visa mer information.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="5fcc1-132">Om du vill stänga rapporten när du är klar med granskningen bläddrar du längst ned på sidan **Hjälpmedelskontroll** och väljer **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fcc1-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5fcc1-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5fcc1-133">Additional resources</span></span>

[<span data-ttu-id="5fcc1-134">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="5fcc1-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="5fcc1-135">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="5fcc1-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="5fcc1-136">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="5fcc1-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="5fcc1-137">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="5fcc1-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="5fcc1-138">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="5fcc1-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="5fcc1-139">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="5fcc1-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="5fcc1-140">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="5fcc1-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="5fcc1-141">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="5fcc1-141">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]