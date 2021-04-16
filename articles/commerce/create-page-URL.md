---
title: Skapa URL för webbsida
description: I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98743d8948669f32d3c74e1915c7ed53db81141c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795701"
---
# <a name="create-a-page-url"></a><span data-ttu-id="88e10-103">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="88e10-103">Create a page URL</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="88e10-104">I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="88e10-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

<span data-ttu-id="88e10-105">Den fullständiga eller absoluta URL som pekar mot en sida på din webbplats består av separata delar.</span><span class="sxs-lookup"><span data-stu-id="88e10-105">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="88e10-106">Till exempel URL-adressen `https://www.contoso.com/en-us/contactus` har följande delar:</span><span class="sxs-lookup"><span data-stu-id="88e10-106">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="88e10-107">`https://www.contoso.com`– HTTP-protokollet och platsens domän.</span><span class="sxs-lookup"><span data-stu-id="88e10-107">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="88e10-108">`/en-us`– Platsens språksökväg.</span><span class="sxs-lookup"><span data-stu-id="88e10-108">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="88e10-109">`/contactus`– Den relativa URL-adressen för sidan **kontakta oss**.</span><span class="sxs-lookup"><span data-stu-id="88e10-109">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="88e10-110">En relativ URL kallas också för en URL *instruktion*.</span><span class="sxs-lookup"><span data-stu-id="88e10-110">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="88e10-111">Du upprättar platsens domän och valfri språksökväg när du ställer in platsen.</span><span class="sxs-lookup"><span data-stu-id="88e10-111">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="88e10-112">Du kan lägga till fler domäner och språksökvägar till webbplatsen via sidan onlinebutiker i webbplatsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="88e10-112">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="88e10-113">URL-instruktionen för en sida finns som en fristående enhet i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="88e10-113">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="88e10-114">En sid-URL består av två delar: ett namn som representerar URL-instruktionen och en pekare till en sida på antingen en webbplats eller en extern webbplats.</span><span class="sxs-lookup"><span data-stu-id="88e10-114">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="88e10-115">En sid-URL kan också konfigureras för att fungera som en omdirigering till en annan sida på antingen en webbplats eller en extern plats.</span><span class="sxs-lookup"><span data-stu-id="88e10-115">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="88e10-116">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="88e10-116">Create a page URL</span></span>

<span data-ttu-id="88e10-117">Det finns två sätt att skapa URL:</span><span class="sxs-lookup"><span data-stu-id="88e10-117">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="88e10-118">Automatiskt, när du skapar en sida</span><span class="sxs-lookup"><span data-stu-id="88e10-118">Automatically, when you create a page</span></span>
- <span data-ttu-id="88e10-119">Manuellt, från **URL**-sidan</span><span class="sxs-lookup"><span data-stu-id="88e10-119">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="88e10-120">Skapa en sid-URL när du skapar en sida</span><span class="sxs-lookup"><span data-stu-id="88e10-120">Create a page URL when you create a page</span></span>

<span data-ttu-id="88e10-121">Om du anger ett namn i fältet **URL** när du skapar en ny sida, skapas en sid-URL som pekar mot sidan automatiskt på sidan **URL:er**.</span><span class="sxs-lookup"><span data-stu-id="88e10-121">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="88e10-122">När du har publicerat URL:en och sidan som den pekar mot, kan webbplatsanvändare (dina kunder) komma åt den sida som är kopplad till URL:en.</span><span class="sxs-lookup"><span data-stu-id="88e10-122">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="88e10-123">Om du publicerar en URL utan att publicera sidan som den pekar mot, får webbplatsanvändarna ett 404-fel när de försöker öppna sidan.</span><span class="sxs-lookup"><span data-stu-id="88e10-123">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="88e10-124">Om du publicerar en sida utan att publicera den URL som pekar mot den, går det inte att komma åt sidan via en URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-124">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="88e10-125">Manuellt skapa en sida-URL</span><span class="sxs-lookup"><span data-stu-id="88e10-125">Manually create a page URL</span></span>

<span data-ttu-id="88e10-126">När du skapar nya sidor behöver du inte ange någon sidadress.</span><span class="sxs-lookup"><span data-stu-id="88e10-126">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="88e10-127">Om du lämnar URL-fältet tomt skapas sidan i ett olänkat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="88e10-127">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="88e10-128">I det här fallet kommer kunderna inte att kunna komma åt sidan, även om den publiceras.</span><span class="sxs-lookup"><span data-stu-id="88e10-128">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="88e10-129">Om du vill göra sidan åtkomlig måste du skapa URL:en och länka den till sidan manuellt.</span><span class="sxs-lookup"><span data-stu-id="88e10-129">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="88e10-130">Om du vill skapa en sid-URL för en sida manuellt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="88e10-130">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="88e10-131">Välj **URL** på sidan **Tillgångsstruktur**.</span><span class="sxs-lookup"><span data-stu-id="88e10-131">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="88e10-132">Välj den webbplatssida som du vill associera med URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-132">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="88e10-133">Ange URL-instruktionen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="88e10-133">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="88e10-134">I det här läget är URL-adressen i ett utkast.</span><span class="sxs-lookup"><span data-stu-id="88e10-134">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="88e10-135">Den måste publiceras innan webbplatsanvändare kan komma åt den associerade sidan.</span><span class="sxs-lookup"><span data-stu-id="88e10-135">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="88e10-136">Uppdatera en sid-URL</span><span class="sxs-lookup"><span data-stu-id="88e10-136">Update a page URL</span></span>

<span data-ttu-id="88e10-137">Om du vill uppdatera målsidan för en sid-URL följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="88e10-137">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="88e10-138">På sidan **URL** väljer du den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="88e10-138">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="88e10-139">Markera ellipsknappen i egenskapsrutan till höger (**...**) bredvid fältet för målsidan.</span><span class="sxs-lookup"><span data-stu-id="88e10-139">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="88e10-140">I dialogrutan väljer du en annan sida och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="88e10-140">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="88e10-141">Spara och publicera URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-141">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="88e10-142">Omdirigera en sid-URL</span><span class="sxs-lookup"><span data-stu-id="88e10-142">Redirect a page URL</span></span>

<span data-ttu-id="88e10-143">Ibland vill du kanske att dina kunder ska kunna visa en annan sida när de begär en viss URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-143">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="88e10-144">I dessa fall är den bästa och enklaste metoden ofta att ändra sidan som sid-URL:en pekar mot.</span><span class="sxs-lookup"><span data-stu-id="88e10-144">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="88e10-145">Du kan dock ha legitima skäl för att använda HTTP 301- eller 3023-omdirigeringar för att omdirigera begäranden för en URL till en annan URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-145">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="88e10-146">Om du vill omdirigera en URL till en annan URL följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="88e10-146">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="88e10-147">På sidan **URL** väljer du den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="88e10-147">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="88e10-148">I egenskapsrutan till höger, välj **Omdirigera**.</span><span class="sxs-lookup"><span data-stu-id="88e10-148">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="88e10-149">Välj ett mål för omdirigeringen:</span><span class="sxs-lookup"><span data-stu-id="88e10-149">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="88e10-150">Om du vill peka mot en annan sida på webbplatsen markerar du **Intern URL**, väljer ellipsknappen (**...**) och väljer den URL du vill omdirigera till.</span><span class="sxs-lookup"><span data-stu-id="88e10-150">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="88e10-151">Om du vill peka mot en sida på en extern webbplats väljer du **Extern URL**, och anger sedan full URL-adressen för sidan.</span><span class="sxs-lookup"><span data-stu-id="88e10-151">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="88e10-152">Se till att du inkluderar protokollet.</span><span class="sxs-lookup"><span data-stu-id="88e10-152">Be sure to include the protocol.</span></span> <span data-ttu-id="88e10-153">Ange exempelvis `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="88e10-153">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="88e10-154">Om URL:en redan omdirigeras till en intern URL måste du välja **Rensa urval** innan du kan ange en extern URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-154">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="88e10-155">Välj en omdirigeringstyp:</span><span class="sxs-lookup"><span data-stu-id="88e10-155">Select a redirect type:</span></span>

    - <span data-ttu-id="88e10-156">**Permanent omdirigering (301)** – Välj det här alternativet när du vet att innehållet flyttas permanent och inte återgår till föregående URL.</span><span class="sxs-lookup"><span data-stu-id="88e10-156">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="88e10-157">Sökmotorer tilldelar SEO-värdet (Search Engine Optimization) för den omdirigerade URL:en till den URL som omdirigeras till och uppdaterar posten för att visa den nya URL:en.</span><span class="sxs-lookup"><span data-stu-id="88e10-157">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="88e10-158">**Tillfällig omdirigering (302)** – Välj det här alternativet om du vill dirigera om trafiken utan att uppdatera sökmotorer.</span><span class="sxs-lookup"><span data-stu-id="88e10-158">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="88e10-159">Den här metoden används vanligtvis om innehållet kommer att återgå till föregående URL-adress.</span><span class="sxs-lookup"><span data-stu-id="88e10-159">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="88e10-160">Spara och publicera URL:en när du är klar att implementera omdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="88e10-160">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88e10-161">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88e10-161">Additional resources</span></span>

[<span data-ttu-id="88e10-162">Anpassa webbplatsnavigeringen</span><span class="sxs-lookup"><span data-stu-id="88e10-162">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="88e10-163">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="88e10-163">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="88e10-164">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="88e10-164">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="88e10-165">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="88e10-165">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
