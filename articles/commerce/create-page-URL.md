---
title: Skapa URL för webbsida
description: I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ab7325dd4060392ed43e59c1ad48069d294d81c0
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697558"
---
# <a name="create-a-page-url"></a><span data-ttu-id="34047-103">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="34047-103">Create a page URL</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="34047-104">I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="34047-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

## <a name="overview"></a><span data-ttu-id="34047-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="34047-105">Overview</span></span>

<span data-ttu-id="34047-106">Den fullständiga eller absoluta URL som pekar på en sida på din webbplats består av separata delar.</span><span class="sxs-lookup"><span data-stu-id="34047-106">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="34047-107">Till exempel URL-adressen `https://www.contoso.com/en-us/contactus` har följande delar:</span><span class="sxs-lookup"><span data-stu-id="34047-107">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="34047-108">`https://www.contoso.com`– HTTP-protokollet och platsens domän.</span><span class="sxs-lookup"><span data-stu-id="34047-108">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="34047-109">`/en-us`– Platsens språksökväg.</span><span class="sxs-lookup"><span data-stu-id="34047-109">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="34047-110">`/contactus`– Den relativa URL-adressen för sidan **kontakta oss**.</span><span class="sxs-lookup"><span data-stu-id="34047-110">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="34047-111">En relativ URL kallas också för en URL *instruktion*.</span><span class="sxs-lookup"><span data-stu-id="34047-111">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="34047-112">Du upprättar platsens domän och valfri språksökväg när du ställer in platsen.</span><span class="sxs-lookup"><span data-stu-id="34047-112">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="34047-113">Du kan lägga till fler domäner och språksökvägar till webbplatsen via sidan onlinebutiker i webbplatsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="34047-113">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="34047-114">URL-instruktionen för en sida finns som en fristående enhet i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="34047-114">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="34047-115">En sid-URL består av två delar: ett namn som representerar URL-instruktionen och en pekare till en sida på antingen en webbplats eller en extern webbplats.</span><span class="sxs-lookup"><span data-stu-id="34047-115">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="34047-116">En sid-URL kan också konfigureras för att fungera som en omdirigering till en annan sida på antingen en webbplats eller en extern plats.</span><span class="sxs-lookup"><span data-stu-id="34047-116">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="34047-117">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="34047-117">Create a page URL</span></span>

<span data-ttu-id="34047-118">Det finns två sätt att skapa URL:</span><span class="sxs-lookup"><span data-stu-id="34047-118">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="34047-119">Automatiskt, när du skapar en sida</span><span class="sxs-lookup"><span data-stu-id="34047-119">Automatically, when you create a page</span></span>
- <span data-ttu-id="34047-120">Manuellt, från **URL**-sidan</span><span class="sxs-lookup"><span data-stu-id="34047-120">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="34047-121">Skapa en sid-URL när du skapar en sida</span><span class="sxs-lookup"><span data-stu-id="34047-121">Create a page URL when you create a page</span></span>

<span data-ttu-id="34047-122">Om du anger ett namn i fältet **URL** när du skapar en ny sida, skapas en sid-URL som pekar på sidan automatiskt på sidan **URL:er**.</span><span class="sxs-lookup"><span data-stu-id="34047-122">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="34047-123">När du har publicerat URL:en och sidan som den pekar på, kan webbplatsanvändare (dina kunder) komma åt den sida som är kopplad till URL:en.</span><span class="sxs-lookup"><span data-stu-id="34047-123">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="34047-124">Om du publicerar en URL utan att publicera sidan som den pekar på, får webbplatsanvändarna ett 404-fel när de försöker öppna sidan.</span><span class="sxs-lookup"><span data-stu-id="34047-124">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="34047-125">Om du publicerar en sida utan att publicera den URL som pekar på den, går det inte att komma åt sidan via en URL.</span><span class="sxs-lookup"><span data-stu-id="34047-125">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="34047-126">Manuellt skapa en sida-URL</span><span class="sxs-lookup"><span data-stu-id="34047-126">Manually create a page URL</span></span>

<span data-ttu-id="34047-127">När du skapar nya sidor behöver du inte ange någon sidadress.</span><span class="sxs-lookup"><span data-stu-id="34047-127">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="34047-128">Om du lämnar URL-fältet tomt skapas sidan i ett olänkat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="34047-128">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="34047-129">I det här fallet kommer kunderna inte att kunna komma åt sidan, även om den publiceras.</span><span class="sxs-lookup"><span data-stu-id="34047-129">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="34047-130">Om du vill göra sidan åtkomlig måste du skapa URL:en och länka den till sidan manuellt.</span><span class="sxs-lookup"><span data-stu-id="34047-130">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="34047-131">Om du vill skapa en sid-URL för en sida manuellt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="34047-131">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="34047-132">Välj **URL** på sidan **Tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="34047-132">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="34047-133">Välj den webbplatssida som du vill associera med URL.</span><span class="sxs-lookup"><span data-stu-id="34047-133">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="34047-134">Ange URL-instruktionen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="34047-134">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="34047-135">I det här läget är URL-adressen i ett utkast.</span><span class="sxs-lookup"><span data-stu-id="34047-135">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="34047-136">Den måste publiceras innan webbplatsanvändare kan komma åt den associerade sidan.</span><span class="sxs-lookup"><span data-stu-id="34047-136">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="34047-137">Uppdatera en sid-URL</span><span class="sxs-lookup"><span data-stu-id="34047-137">Update a page URL</span></span>

<span data-ttu-id="34047-138">Om du vill uppdatera målsidan för en sid-URL följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="34047-138">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="34047-139">På sidan **URL** väljer du den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="34047-139">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="34047-140">Markera ellipsknappen i egenskapsrutan till höger (**...**) bredvid fältet för målsidan.</span><span class="sxs-lookup"><span data-stu-id="34047-140">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="34047-141">I dialogrutan väljer du en annan sida och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="34047-141">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="34047-142">Spara och publicera URL.</span><span class="sxs-lookup"><span data-stu-id="34047-142">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="34047-143">Omdirigera en sid-URL</span><span class="sxs-lookup"><span data-stu-id="34047-143">Redirect a page URL</span></span>

<span data-ttu-id="34047-144">Ibland vill du kanske att dina kunder ska kunna visa en annan sida när de begär en viss URL.</span><span class="sxs-lookup"><span data-stu-id="34047-144">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="34047-145">I dessa fall är den bästa och enklaste metoden ofta att ändra sidan som sid-URL:en pekar på.</span><span class="sxs-lookup"><span data-stu-id="34047-145">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="34047-146">Du kan dock ha legitima skäl för att använda HTTP 301- eller 3023-omdirigeringar för att omdirigera begäranden för en URL till en annan URL.</span><span class="sxs-lookup"><span data-stu-id="34047-146">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="34047-147">Om du vill omdirigera en URL till en annan URL följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="34047-147">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="34047-148">På sidan **URL** väljer du den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="34047-148">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="34047-149">I egenskapsrutan till höger, välj **Omdirigera**.</span><span class="sxs-lookup"><span data-stu-id="34047-149">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="34047-150">Välj ett mål för omdirigeringen:</span><span class="sxs-lookup"><span data-stu-id="34047-150">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="34047-151">Om du vill peka på en annan sida på webbplatsen markerar du **Intern URL**, väljer ellipsknappen (**...**) och väljer den URL du vill omdirigera till.</span><span class="sxs-lookup"><span data-stu-id="34047-151">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="34047-152">Om du vill peka på en sida på en extern webbplats väljer du **Extern URL**, och anger sedan full URL-adressen för sidan.</span><span class="sxs-lookup"><span data-stu-id="34047-152">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="34047-153">Se till att du inkluderar protokollet.</span><span class="sxs-lookup"><span data-stu-id="34047-153">Be sure to include the protocol.</span></span> <span data-ttu-id="34047-154">Ange exempelvis `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="34047-154">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="34047-155">Om URL:en redan omdirigeras till en intern URL måste du välja **Rensa urval** innan du kan ange en extern URL.</span><span class="sxs-lookup"><span data-stu-id="34047-155">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="34047-156">Välj en omdirigeringstyp:</span><span class="sxs-lookup"><span data-stu-id="34047-156">Select a redirect type:</span></span>

    - <span data-ttu-id="34047-157">**Permanent omdirigering (301)** – Välj det här alternativet när du vet att innehållet flyttas permanent och inte återgår till föregående URL.</span><span class="sxs-lookup"><span data-stu-id="34047-157">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="34047-158">Sökmotorer tilldelar SEO-värdet (Search Engine Optimization) för den omdirigerade URL:en till den URL som omdirigeras till och uppdaterar posten för att visa den nya URL:en.</span><span class="sxs-lookup"><span data-stu-id="34047-158">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="34047-159">**Tillfällig omdirigering (302)** – Välj det här alternativet om du vill dirigera om trafiken utan att uppdatera sökmotorer.</span><span class="sxs-lookup"><span data-stu-id="34047-159">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="34047-160">Den här metoden används vanligtvis om innehållet kommer att återgå till föregående URL-adress.</span><span class="sxs-lookup"><span data-stu-id="34047-160">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="34047-161">Spara och publicera URL:en när du är klar att implementera omdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="34047-161">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34047-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="34047-162">Additional resources</span></span>

[<span data-ttu-id="34047-163">Anpassa webbplatsnavigeringen</span><span class="sxs-lookup"><span data-stu-id="34047-163">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="34047-164">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="34047-164">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="34047-165">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="34047-165">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="34047-166">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="34047-166">Add languages to your site</span></span>](add-languages-to-site.md)
