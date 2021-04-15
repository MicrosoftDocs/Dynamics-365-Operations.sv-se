---
title: Skapa dynamiska näthandelssidor baserade på URL-parametrar
description: I detta ämne beskrivs hur du ställer in en Microsoft Dynamics 365 Commerce-näthandelssida som kan använda dynamiskt innehåll baserat på URL-parametrar.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8f59b80880e6947e1b45c110df0e78d4bdd57c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795821"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="f31bc-103">Skapa dynamiska näthandelssidor baserade på URL-parametrar</span><span class="sxs-lookup"><span data-stu-id="f31bc-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f31bc-104">I detta ämne beskrivs hur du ställer in en Microsoft Dynamics 365 Commerce-näthandelssida som kan använda dynamiskt innehåll baserat på URL-parametrar.</span><span class="sxs-lookup"><span data-stu-id="f31bc-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="f31bc-105">En näthandelssida kan konfigureras till att använda olika typer av innehåll, baserat på ett segment i URL-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="f31bc-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="f31bc-106">Därför kallas sidan för en "dynamisk" sida.</span><span class="sxs-lookup"><span data-stu-id="f31bc-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="f31bc-107">Segmentet används som en parameter för att hämta sidinnehållet.</span><span class="sxs-lookup"><span data-stu-id="f31bc-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="f31bc-108">En sida kallad **blog\_viewer** skapas exempelvis och kopplas till webbadressen (URL) `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="f31bc-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="f31bc-109">Denna sida kan sedan användas för att visa annat innehåll, baserat på det sista segmentet i URL-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="f31bc-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="f31bc-110">Det sista segmentet i webbadressen (URL) `https://fabrikam.com/blog/article-1` är **artikel-1**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="f31bc-111">Separata anpassade sidor som åsidosätter den dynamiska sidan kan också associeras med segment i URL-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="f31bc-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="f31bc-112">En sida kallad **blog\_summary** skapas exempelvis och kopplas till webbadressen (URL) `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="f31bc-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="f31bc-113">När denna URL begärs kommer den **blog\_summary**-sida som associeras med **/about-this-blog**-parametern att returneras istället för **blog\_viewer**-sidan.</span><span class="sxs-lookup"><span data-stu-id="f31bc-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="f31bc-114">Funktionerna för värd, hämtning och visning av dynamiskt sidinnehåll implementeras med hjälp av en anpassad modul.</span><span class="sxs-lookup"><span data-stu-id="f31bc-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="f31bc-115">Mer information finns i [Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="f31bc-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="f31bc-116">Ställa in en dynamisk sida för näthandel</span><span class="sxs-lookup"><span data-stu-id="f31bc-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="f31bc-117">Om du vill konfigurera en dynamisk e-handelssida måste du skapa den dynamiska sidan, skapa bas-webbadressen (URL) och konfigurera flödet till den dynamiska sidan.</span><span class="sxs-lookup"><span data-stu-id="f31bc-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="f31bc-118">Skapa sidan som ska användas för dynamiskt innehåll</span><span class="sxs-lookup"><span data-stu-id="f31bc-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="f31bc-119">Följ stegen i [Lägg till en ny webbplatssida](add-new-page.md) om du vill skapa en sida som använder dynamiskt innehåll.</span><span class="sxs-lookup"><span data-stu-id="f31bc-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="f31bc-120">Den sida du skapar kräver implementering av en modul där det sista segmentet i URL-sökvägen används för att hämta innehåll från en extern datakälla.</span><span class="sxs-lookup"><span data-stu-id="f31bc-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="f31bc-121">Mer information om anpassad modulutveckling finns i [Utvidgningar av onlinekanaler](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="f31bc-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="f31bc-122">Skapa bas-URL för den dynamiska sidan</span><span class="sxs-lookup"><span data-stu-id="f31bc-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="f31bc-123">Skapa bas-URL för den dynamiska sidan i Commerce-webbplatsbyggaren genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f31bc-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f31bc-124">Gå till **URLs** och välj sedan **Ny \> Ny URL**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="f31bc-125">I dialogrutan **Skapa ny URL** väljer du **Intern sida**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="f31bc-126">Under **URL-sökväg** anger du den sökväg som ska fungera som rot för den dynamiska sidan (i detta exempel **/blog**).</span><span class="sxs-lookup"><span data-stu-id="f31bc-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="f31bc-127">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-127">Then select **Next**.</span></span>
1. <span data-ttu-id="f31bc-128">I dialogrutan **Välj en sida** väljer du den sida som du skapade som dynamisk sida innan du väljer **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="f31bc-129">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="f31bc-130">Konfigurera flödet till den dynamiska sidan</span><span class="sxs-lookup"><span data-stu-id="f31bc-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="f31bc-131">Följ dessa steg om du vill konfigurera flödet till den dynamiska sidan i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="f31bc-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f31bc-132">Gå till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="f31bc-133">Under **PParameteriserade URL-sökvägar** väljer du **Lägg till** och anger sedan den URL-sökväg som du angav när du skapade URL:en (i detta exempel **/blog**).</span><span class="sxs-lookup"><span data-stu-id="f31bc-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="f31bc-134">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-134">Select **Save and publish**.</span></span>

<span data-ttu-id="f31bc-135">När flödet har konfigurerats kommer alla förfrågningar till den parameteriserade URL-sökvägen att returnera den sida som är kopplad till URL:en.</span><span class="sxs-lookup"><span data-stu-id="f31bc-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="f31bc-136">Om en begäran innehåller ytterligare ett segment returneras den associerade sidan, och sidinnehållet hämtas med segmentet som en parameter.</span><span class="sxs-lookup"><span data-stu-id="f31bc-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="f31bc-137">`https://fabrikam.com/blog/article-1` kommer exempelvis att returnera sidan **blog\_summary**, och sidinnehållet kommer att hämtas genom att använda parametern **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="f31bc-138">Åsidosätta en parameteriserad URL med en anpassad sida</span><span class="sxs-lookup"><span data-stu-id="f31bc-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="f31bc-139">Om du vill åsidosätta en parameteriserad URL med en anpassad sida i Commerce-webbplatsbyggaren gör du så här.</span><span class="sxs-lookup"><span data-stu-id="f31bc-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f31bc-140">Gå till **URLs** och välj sedan **Ny \> Ny URL**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="f31bc-141">I dialogrutan **Skapa ny URL** väljer du **Intern sida**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="f31bc-142">Under **URL-sökväg** anger du den sökväg som omfattar det segment som ska åsidosättas (i detta exempel **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="f31bc-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="f31bc-143">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-143">Then select **Next**.</span></span>
1. <span data-ttu-id="f31bc-144">I dialogrutan **Välj en sida** väljer du den anpassade sidan och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="f31bc-145">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-145">Select **Publish**.</span></span>
1. <span data-ttu-id="f31bc-146">Om den anpassade sidan ännu inte har publicerats går du till **Sidor** pch väljer den anpassade sidan och sedan **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="f31bc-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="f31bc-147">När den anpassade sidan har publiceras visas den istället för den dynamiska sidan som har parameteriserat innehåll.</span><span class="sxs-lookup"><span data-stu-id="f31bc-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f31bc-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f31bc-148">Additional resources</span></span>

[<span data-ttu-id="f31bc-149">Ändra en befintlig webbplatssida</span><span class="sxs-lookup"><span data-stu-id="f31bc-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f31bc-150">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="f31bc-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f31bc-151">Välj sidlayouter</span><span class="sxs-lookup"><span data-stu-id="f31bc-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f31bc-152">Hantera SEO-metadata</span><span class="sxs-lookup"><span data-stu-id="f31bc-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="f31bc-153">Spara, förhandsgranska och publicera en sida</span><span class="sxs-lookup"><span data-stu-id="f31bc-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f31bc-154">Utöka en produktsida</span><span class="sxs-lookup"><span data-stu-id="f31bc-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="f31bc-155">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="f31bc-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="f31bc-156">Kontrollera tillgängligheten för sidinnehåll</span><span class="sxs-lookup"><span data-stu-id="f31bc-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="f31bc-157">Utbyggbarhet för onlinekanal</span><span class="sxs-lookup"><span data-stu-id="f31bc-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
