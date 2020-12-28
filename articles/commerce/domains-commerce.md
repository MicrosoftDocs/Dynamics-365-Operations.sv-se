---
title: Domäner i Dynamics 365 Commerce
description: I det här avsnittet beskrivs hur domäner hanteras i Microsoft Dynamics 365 Commerce.
author: BrShoo
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cb2b003168d32d05387bd45796d313736b11a41f
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517365"
---
# <a name="domains-in-dynamics-365-commerce"></a><span data-ttu-id="31e31-103">Domäner i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="31e31-103">Domains in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="31e31-104">I det här avsnittet beskrivs hur domäner hanteras i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31e31-104">This topic describes how domains are handled in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="31e31-105">Domäner är webbadresser som används för att navigera till Dynamics 365 Commerce webbplatser i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="31e31-105">Domains are web addresses used to navigate to Dynamics 365 Commerce sites in a web browser.</span></span> <span data-ttu-id="31e31-106">Du kontrollerar hanteringen av din domän med en vald DNS-leverantör (domännamnserver).</span><span class="sxs-lookup"><span data-stu-id="31e31-106">You control management of your domain with a chosen Domain Name Server (DNS) provider.</span></span> <span data-ttu-id="31e31-107">Domäner refereras till i hela Dynamics 365 Commerce webbplatsskaparen för att koordinera hur en plats kommer att få åtkomst till när den publiceras.</span><span class="sxs-lookup"><span data-stu-id="31e31-107">Domains are referenced throughout Dynamics 365 Commerce site builder to coordinate how a site will be accessed when published.</span></span> <span data-ttu-id="31e31-108">I det här avsnittet beskrivs hur domäner hanteras och refereras under hela livscykeln för webbplatsutveckling och start av Commerce.</span><span class="sxs-lookup"><span data-stu-id="31e31-108">This topic reviews how domains are handled and referenced throughout the lifecycle of the Commerce site development and launch.</span></span>

## <a name="provisioning-and-supported-host-names"></a><span data-ttu-id="31e31-109">Etablera och stödja värdnamn</span><span class="sxs-lookup"><span data-stu-id="31e31-109">Provisioning and supported host names</span></span>

<span data-ttu-id="31e31-110">När du etablerar en näthandelsmiljö i [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), används rutan **Värdnamn som stöds** på etableringsskärmen för näthandel för att ange domäner som ska associeras med den distribuerade Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="31e31-110">When provisioning an e-commerce environment in [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), the **Supported host names** box on the e-commerce provisioning screen is used to enter domains that will be associated with the deployed Commerce environment.</span></span> <span data-ttu-id="31e31-111">Dessa domäner blir de kundriktade DNS-namn (domännamnserver) där näthandelsplatser värdbaseras.</span><span class="sxs-lookup"><span data-stu-id="31e31-111">These domains will be the customer-facing Domain Name Server (DNS) names where e-commerce websites will be hosted.</span></span> <span data-ttu-id="31e31-112">Att ange en domän i detta skede börjar inte att leda till att trafiken för domänen ändras till Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31e31-112">Entering a domain at this stage does not start diverting traffic for the domain to Dynamics 365 Commerce.</span></span> <span data-ttu-id="31e31-113">Trafik för en domän skickas bara till Commerce-slutpunkten när DNS CNAME-posten uppdateras för att använda Commerce-slutpunkten för domänen.</span><span class="sxs-lookup"><span data-stu-id="31e31-113">Traffic for a domain will only be routed to the Commerce endpoint when the DNS CNAME record is updated to use the Commerce endpoint with the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="31e31-114">Flera domäner kan anges i rutan **värdnamn som stöds** genom att avgränsa dem med semikolon.</span><span class="sxs-lookup"><span data-stu-id="31e31-114">Multiple domains can be entered into the **Supported host names** box by separating them with semi-colons.</span></span>

<span data-ttu-id="31e31-115">I följande bild visas LCS-etableringsskärmen för näthandel med rutan **Värdnamn som stöds** markerad.</span><span class="sxs-lookup"><span data-stu-id="31e31-115">The following illustration shows the LCS e-commerce provisioning screen with the **Supported host names** box highlighted.</span></span> 

![Etableringsskärmen för LCS-näthandel med rutan **Värdnamn som stöds** markerad](./media/Domains_ProvisioningeCommerceScreen.png)

<span data-ttu-id="31e31-117">Du kan skapa en tjänstbegäran om du vill lägga till fler domäner i en miljö om etableringen redan har genomförts.</span><span class="sxs-lookup"><span data-stu-id="31e31-117">You can create a service request to add additional domains to an environment if provisioning has already occurred.</span></span> <span data-ttu-id="31e31-118">Om du vill skapa en tjänstbegäran i LCS, inom din miljö, går du till **Support \> Supportproblem** och väljer **Skicka en incident**.</span><span class="sxs-lookup"><span data-stu-id="31e31-118">To create a service request in LCS, within your environment go to **Support \> Support issues** and select **Submit an incident**.</span></span>

## <a name="commerce-generated-urls"></a><span data-ttu-id="31e31-119">Commerce-genererade URL</span><span class="sxs-lookup"><span data-stu-id="31e31-119">Commerce-generated URLs</span></span>

<span data-ttu-id="31e31-120">Vid etablering av en Dynamics 365 Commerce-näthandelsmiljö genererar Commerce en URL som blir miljöns arbetsadress.</span><span class="sxs-lookup"><span data-stu-id="31e31-120">When provisioning a Dynamics 365 Commerce e-commerce environment, Commerce will generate a URL that will be the working address for the environment.</span></span> <span data-ttu-id="31e31-121">Denna URL refereras till i den näthandelsplatslänk som visas i LCS efter det att miljön har etablerats.</span><span class="sxs-lookup"><span data-stu-id="31e31-121">This URL is referenced in the e-commerce site link shown in LCS after the environment is provisioned.</span></span> <span data-ttu-id="31e31-122">En Commerce-genererad URL bär formatet `https://<e-commerce tenant name>.commerce.dynamics.com`, där namnet på näthandelns klientorganisation är det namn som har angetts i LCS för Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="31e31-122">A Commerce-generated URL is in the format `https://<e-commerce tenant name>.commerce.dynamics.com`, where the e-commerce tenant name is the name entered in LCS for the Commerce environment.</span></span>

<span data-ttu-id="31e31-123">Du kan också använda namn på produktionsplats värden i en sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="31e31-123">You can use production site host names in a sandbox environment as well.</span></span> <span data-ttu-id="31e31-124">Det här alternativet är praktiskt när du vill kopiera en webbplats från en begränsat miljö till en produktion.</span><span class="sxs-lookup"><span data-stu-id="31e31-124">This option is ideal when you will be copying a site from a sandbox environment to production.</span></span>

## <a name="site-setup"></a><span data-ttu-id="31e31-125">Inställning av webbplats</span><span class="sxs-lookup"><span data-stu-id="31e31-125">Site setup</span></span>

<span data-ttu-id="31e31-126">När din näthandelsmiljö har etablerats måste du ställa in din webbplats i Commerce-webbplatsskaparen för att koppla webbplatsen till arbets-URL:en.</span><span class="sxs-lookup"><span data-stu-id="31e31-126">After your e-commerce environment is provisioned, you must set up your site in Commerce site builder to associate your site to the working URL.</span></span>

<span data-ttu-id="31e31-127">När du först skapar en webbplats i webbplatsskaparen visas dialogrutan **konfigurera plats**.</span><span class="sxs-lookup"><span data-stu-id="31e31-127">When you first set up a site in site builder, the **Setup your Site** dialog box will appear.</span></span>

<span data-ttu-id="31e31-128">Bilden nedan visar dialogrutan visar **konfigurera din webbplats** för en webbplats med namnet "standard" när du öppnar webbplatsen för första gången i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-128">The following illustration shows the **Setup your Site** dialog box for a site named "default" when you access the site for the first time in site builder.</span></span>

![Dialogrutan **Konfigurera din webbplats**](./media/Domains_SetupyoursiteScreen.png)

<span data-ttu-id="31e31-130">Med hjälp av rutan **Välj en domän** kan du associera ett av de värdnamn som stöds för din webbplats i LCS till webbplatsen i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-130">The **Select a domain** box allows you to associate one of the supported host names provided for your site in LCS to your site in site builder.</span></span>

<span data-ttu-id="31e31-131">Rutan **Sökväg** kan lämnas tom, eller så kan en extra sökvägssträng läggas till som återspeglas i arbets-URL:en.</span><span class="sxs-lookup"><span data-stu-id="31e31-131">The **Path** box can be left blank, or an additional path string can be added that will be reflected in your working URL.</span></span> <span data-ttu-id="31e31-132">Om du lämnar rutan **Sökväg** tom kopplas den grundläggande Commerce-genererade URL med den webbplats som konfigureras i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-132">Leaving the **Path** box blank associates the base Commerce-generated URL with the site being set up in site builder.</span></span> <span data-ttu-id="31e31-133">Sökvägar måste vara unika för varje plats/domän par.</span><span class="sxs-lookup"><span data-stu-id="31e31-133">Paths must be unique for each site/domain pair.</span></span> <span data-ttu-id="31e31-134">På den markerade platsen och domänen kan endast en plats i miljön använda den tomma sökvägen eller vara associerad med en unik sökvägssträng.</span><span class="sxs-lookup"><span data-stu-id="31e31-134">Within the site and domain selected, only one site in the environment can use the blank path or be associated with a unique path string.</span></span> <span data-ttu-id="31e31-135">Alla strängar som läggs till i fältet **Sökväg** under webbplatsinställningen kommer att bli en delväg till den grundläggande Commerce-genererade URL som används för att komma åt webbplatsen i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="31e31-135">Any string added to the **Path** field during site setup will become a subpath of the base Commerce-generated URL used to access the site in a web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="31e31-136">Sökvägen kallas även **matchningssökväg** när en kanal läggs till i konfigurationsavsnittet i **webbplatsinställningar \> kanaler** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-136">The path is also known as the **Match path** when adding a channel in the **Site Settings \> Channels** configuration section of site builder.</span></span>

<span data-ttu-id="31e31-137">Om du till exempel har en webbplats i webbplatsskaparen som kallas "Fabrikam" i en näthandelsklient med namnet "xyz" och du ställer in webbplatsen med en tom sökväg, får du tillgång till det publicerade webbplatsinnehållet i en webbläsare genom att gå direkt till den grundläggande Commerce-genererade URL:en:</span><span class="sxs-lookup"><span data-stu-id="31e31-137">For example, if you have a site in site builder called "fabrikam" in an e-commerce tenant named "xyz," and if you set up the site with a blank path, then you would access the published site content in a web browser by going directly to the base Commerce-generated URL:</span></span>

`https://xyz.commerce.dynamics.com`

<span data-ttu-id="31e31-138">Alternativt, om du har lagt till en sökväg på "Fabrikam" under samma platsinställningar, kommer du åt det publicerade webbplatsinnehållet i en webbläsare med hjälp av följande URL:</span><span class="sxs-lookup"><span data-stu-id="31e31-138">Alternately, if you had added a path of "fabrikam" during this same site's setup, you would access the published site content in a web browser using the following URL:</span></span>

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a><span data-ttu-id="31e31-139">Sidor och URL-adresser</span><span class="sxs-lookup"><span data-stu-id="31e31-139">Pages and URLs</span></span>

<span data-ttu-id="31e31-140">När din webbplats har konfigurerats med en sökväg, bygger alla URL-adresser som är kopplade till sidorna i webbplatsskaparen på arbets-URL:en (den genererade URL-adressen för Commerce eller den URL som genererades tillsammans med sökvägen) för platsen.</span><span class="sxs-lookup"><span data-stu-id="31e31-140">After your site is set up with a path, all URLs associated with pages in site builder will build on the working URL (the Commerce-generated URL, or the Commerce-generated URL plus the path) for the site.</span></span> <span data-ttu-id="31e31-141">Skapa en ny URL i webbplatsskaparen (**URLS /> +Ny**) genom att markera en sida i listan i dialogrutan **Ny URL** och anger URL-sökvägen för den sidan, associeras URL:en med den valda sidan.</span><span class="sxs-lookup"><span data-stu-id="31e31-141">Creating a new URL in site builder (**URLS /> +New**) by selecting a page from the list in the **New URL** dialog box and entering the URL path for that page will associate that URL with the selected page.</span></span> <span data-ttu-id="31e31-142">Värdet för URL-sökvägen läggs sedan till i webbplatsens arbets-URL för att komma åt sidan och betecknas som `./<URL path>` i URL-listan för sidan **URL** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-142">The URL path value then appends to the site's working URL to access the page, and is labeled as `./<URL path>` in the URL list of the **URLs** page in site builder.</span></span>

<span data-ttu-id="31e31-143">I följande bild visas dialogrutan **Ny URL** i webbplatsskaparen med en URL-exempelsökväg markerad.</span><span class="sxs-lookup"><span data-stu-id="31e31-143">The following illustration shows the **New URL** dialog box in site builder with an example URL path highlighted.</span></span> 

![Dialogruta **Ny URL** dialogruta i webbplatsskaparen](./media/Domains_PageSetup2a.png)

<span data-ttu-id="31e31-145">I följande bild visas sidan **URL** i webbplatsskaparen med en URL-exempelsökväg markerad i listan.</span><span class="sxs-lookup"><span data-stu-id="31e31-145">The following illustration shows the **URLs** page in site builder with an example URL highlighted in the list.</span></span>

![Kör användarflödesalternativ i policyflöde](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a><span data-ttu-id="31e31-147">Domäner i webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="31e31-147">Domains in site builder</span></span>

<span data-ttu-id="31e31-148">De värden för värdnamn som stöds är tillgängliga för att associeras som en domän när en webbplats konfigureras.</span><span class="sxs-lookup"><span data-stu-id="31e31-148">The supported host names values are available to be associated as a domain when setting up a site.</span></span> <span data-ttu-id="31e31-149">När du väljer ett värde för värdnamn som stöds som domän, visas den valda domänen som refereras till i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="31e31-149">When selecting a supported host name value as the domain, you will see the chosen domain referenced throughout site builder.</span></span> <span data-ttu-id="31e31-150">Den här domänen är bara en referens inom Commerce-miljön, men den här domänen kommer inte att vidarebefordras till någon direkt trafik Dynamics 365 Commerce .</span><span class="sxs-lookup"><span data-stu-id="31e31-150">This domain is only a reference within the Commerce environment, live traffic for that domain will not yet be forwarded to Dynamics 365 Commerce.</span></span>

<span data-ttu-id="31e31-151">Om du arbetar med webbplatser i webbplatsskaparen, om du har två webbplatser inställda med två olika domäner, kan du lägga till attributet **?domain=** till din arbets-URL för att få åtkomst till det publicerade webbplatsinnehållet i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="31e31-151">When working with sites in site builder, if you have two sites set up with two different domains, you can append the **?domain=** attribute to your working URL to access the published site content in a browser.</span></span>

<span data-ttu-id="31e31-152">Till exempel miljön "xyz" för att få åtkomst till det publicerade webbplats innehållet i en webbläsare: en med domänen `www.fabrikam.com` och den andra med domänen `www.constoso.com`.</span><span class="sxs-lookup"><span data-stu-id="31e31-152">For example, environment "xyz" has been provisioned, and two sites have been created and associated in site builder: one with the domain `www.fabrikam.com` and the other with the domain `www.constoso.com`.</span></span> <span data-ttu-id="31e31-153">Varje webbplats skapades med en tom sökväg.</span><span class="sxs-lookup"><span data-stu-id="31e31-153">Each site was set up using a blank path.</span></span> <span data-ttu-id="31e31-154">Dessa två webbplatser kan sedan öppnas i en webbläsare enligt följande med hjälp av attributet **?domain=**:</span><span class="sxs-lookup"><span data-stu-id="31e31-154">These two sites could then be accessed in a web browser as follows using the **?domain=** attribute:</span></span>
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

<span data-ttu-id="31e31-155">Om ingen frågesträng för domän har angetts i en miljö med flera domäner, använder Commerce den första domän som du har angett.</span><span class="sxs-lookup"><span data-stu-id="31e31-155">When a domain query string is not given in an environment with multiple domains provided, Commerce uses the first domain you provided.</span></span> <span data-ttu-id="31e31-156">Om t.ex. sökvägen "Fabrikam" tillhandahölls först under webbplatskonfigurationen kan URL:en `https://xyz.commerce.dynamics.com` användas för åtkomst till den publicerade webbplatsens innehållsplatsen för `www.fabrikam.com` .</span><span class="sxs-lookup"><span data-stu-id="31e31-156">For example, if the path "fabrikam" was provided first during site setup, the URL `https://xyz.commerce.dynamics.com` could be used to access the published site content site for `www.fabrikam.com`.</span></span>

## <a name="traffic-forwarding-in-production"></a><span data-ttu-id="31e31-157">Vidarebefordran av trafik i produktion</span><span class="sxs-lookup"><span data-stu-id="31e31-157">Traffic forwarding in production</span></span>

<span data-ttu-id="31e31-158">Du kan simulera flera domäner med hjälp av parametrar för domänfrågor i själva commerce.dynamics.com slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="31e31-158">You can simulate multiple domains using domain query string parameters on the commerce.dynamics.com endpoint itself.</span></span> <span data-ttu-id="31e31-159">När du behöver gå in i produktionen måste du vidarebefordra trafiken för din anpassade domän till slutpunkten `<e-commerce tenant name>.commerce.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="31e31-159">But when you need to go live in production, you must forward the traffic for your custom domain to the `<e-commerce tenant name>.commerce.dynamics.com` endpoint.</span></span>

<span data-ttu-id="31e31-160">Slutpunkten `<e-commerce tenant name>.commerce.dynamics.com` stöder inte anpassade domän Secure Sockets Layers (SSL), så du måste konfigurera anpassade domäner med hjälp av Front Door Service eller ett CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="31e31-160">The `<e-commerce tenant name>.commerce.dynamics.com` endpoint does not support custom domain Secure Sockets Layers (SSLs), so you must set up custom domains using a front door service or content delivery network (CDN).</span></span> 

<span data-ttu-id="31e31-161">Om du vill ställa in anpassade domäner med hjälp av en Front Door Service eller CDN har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="31e31-161">To set up custom domains using a front door service or CDN, you have two options:</span></span>

- <span data-ttu-id="31e31-162">Konfigurera en Front Door Service som Azure Front Door för att hantera klienttrafik och ansluta till din Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="31e31-162">Set up a front door service like Azure Front Door to handle front-end traffic and connect to your Commerce environment.</span></span> <span data-ttu-id="31e31-163">Detta ger bättre kontroll över hantering av domäner och certifikat samt mer detaljerade säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="31e31-163">This provides greater control over domain and certificate management and more granular security policies.</span></span>
- <span data-ttu-id="31e31-164">Använd den inlevererade Azure Front Door-instansen.</span><span class="sxs-lookup"><span data-stu-id="31e31-164">Use the Commerce-supplied Azure Front Door instance.</span></span> <span data-ttu-id="31e31-165">Detta kräver samordning av åtgärden med Dynamics 365 Commerce-teamet för domänverifiering och för att hämta SSL-certifikat för din produktionsdomän.</span><span class="sxs-lookup"><span data-stu-id="31e31-165">This requires coordinating action with the Dynamics 365 Commerce team for domain verification and obtaining SSL certificates for your production domain.</span></span>

<span data-ttu-id="31e31-166">Information om hur du ställer in en CDN-tjänst direkt finns i [lägga till stöd för ett Content Delivery Network (CDN)](add-cdn-support.md) .</span><span class="sxs-lookup"><span data-stu-id="31e31-166">For information about how to set up a CDN service directly, see [Add support for a content delivery network (CDN)](add-cdn-support.md).</span></span>

<span data-ttu-id="31e31-167">Om du vill använda en Commerce-tillhandahållen Azure Front Door-instans måste du skapa en service förfrågan för CDN-inställningar hjälp från det inbyggda Commerce-integrationsteamet.</span><span class="sxs-lookup"><span data-stu-id="31e31-167">To use the Commerce-supplied Azure Front Door instance, you must create a service request for CDN setup assistance from the Commerce onboarding team.</span></span> 

- <span data-ttu-id="31e31-168">Du måste ange företagsnamn, produktionsdomän, miljö-ID och namnet på klientorganisationen för näthandel för produktionen.</span><span class="sxs-lookup"><span data-stu-id="31e31-168">You will need to provide your company name, the production domain, environment ID, and production e-commerce tenant name.</span></span> 
- <span data-ttu-id="31e31-169">Du måste bekräfta om detta är en befintlig domän (som används för en för tillfället aktiv plats) eller en ny domän.</span><span class="sxs-lookup"><span data-stu-id="31e31-169">You will need to confirm if this is an existing domain (used for a currently active site) or a new domain.</span></span> 
- <span data-ttu-id="31e31-170">För en ny domän kan domänverifiering och SSL-certifikat uppnås i ett enda steg.</span><span class="sxs-lookup"><span data-stu-id="31e31-170">For a new domain, the domain verification and SSL certificate can be achieved in a single step.</span></span> 
- <span data-ttu-id="31e31-171">För en domän som betjänar en befintlig webbplats, finns det en multistegsprocess som krävs för att upprätta domän verifieringen och SSL-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="31e31-171">For a domain serving an existing website, there is a multistep process required to establish the domain verification and SSL certificate.</span></span> <span data-ttu-id="31e31-172">Denna process har ett servicenivåavtal (7 arbetsdagar) för en domän att vara aktivt, eftersom det innehåller flera sekventiella steg.</span><span class="sxs-lookup"><span data-stu-id="31e31-172">This process has a 7-working-day service level agreement (SLA) for a domain to go live, because it includes multiple sequential steps.</span></span>

<span data-ttu-id="31e31-173">Om du vill skapa en tjänstbegäran i LCS, inom din miljö, går du till **Support \> Supportproblem** och väljer **Skicka en incident**.</span><span class="sxs-lookup"><span data-stu-id="31e31-173">To create a service request in LCS, within your environment go to **Support \> Support issues** and select **Submit an incident**.</span></span>

> [!NOTE]
> <span data-ttu-id="31e31-174">Anpassade domäner med SSL stöds endast i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="31e31-174">Custom domains with SSL are only supported on production environments.</span></span> <span data-ttu-id="31e31-175">För miljöer utan produktion som sandbox-miljö och acceptanstest för användare (UAT) använder du den URL som genereras för att komma åt publicerat innehåll i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="31e31-175">For non-production environments such as sandbox and user acceptance testing (UAT), use the Commerce-generated URL to access published content in a web browser.</span></span>

## <a name="ssl-certificate-process"></a><span data-ttu-id="31e31-176">SSL-certifikatprocess</span><span class="sxs-lookup"><span data-stu-id="31e31-176">SSL certificate process</span></span>

<span data-ttu-id="31e31-177">När en serviceförfrågan lämnas in, kommer Commerce-teamet att koordinera följande steg med dig.</span><span class="sxs-lookup"><span data-stu-id="31e31-177">When a service request is filed, the Commerce team will coordinate the following steps with you.</span></span>

<span data-ttu-id="31e31-178">För nya domäner:</span><span class="sxs-lookup"><span data-stu-id="31e31-178">For new domains:</span></span>
- <span data-ttu-id="31e31-179">Commerce-teamet ställer in Azure Front Door-instansen (Commerce-värdbaserad).</span><span class="sxs-lookup"><span data-stu-id="31e31-179">The Commerce team will set up the Azure Front Door instance (Commerce-hosted).</span></span>
- <span data-ttu-id="31e31-180">Commerce-teamet kommer sedan att tillhandahålla CNAME-posten för att ange den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="31e31-180">The Commerce team will then provide the CNAME record to point your custom domain.</span></span>
- <span data-ttu-id="31e31-181">När posten CNAME har uppdaterats kan Commerce-värdbaserad Azure Front Door -instans verifiera domänens ägare och hämta SSL-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="31e31-181">After the CNAME record is updated, the Commerce-hosted Azure Front Door instance will be able to verify the domain ownership and get the SSL certificate.</span></span>

<span data-ttu-id="31e31-182">För befintliga/aktiva domäner:</span><span class="sxs-lookup"><span data-stu-id="31e31-182">For existing/active domains:</span></span>
- <span data-ttu-id="31e31-183">Commerce-teamet instruerar dig att lägga till en `afdverify.<custom-domain>` CNAME-post som ska förse din domän-DNS-provider.</span><span class="sxs-lookup"><span data-stu-id="31e31-183">The Commerce team will instruct you to add an `afdverify.<custom-domain>` CNAME record to provide to your domain DNS provider.</span></span>
- <span data-ttu-id="31e31-184">När det är klart kommer Commerce-teamet att lägga till domänen i Azure Front Door-instansen och ange att ytterligare DNS TXT-poster ska läggas till i DNS för domänen.</span><span class="sxs-lookup"><span data-stu-id="31e31-184">When complete, the Commerce team will add the domain to the Azure Front Door instance and provide additional DNS TXT records to be added to the DNS for the domain.</span></span>
- <span data-ttu-id="31e31-185">När TXT-posterna har slutförts kommer Commerce-teamet att slutföra de Azure Front Door-uppdateringarna för den domän som ska ställa in SSL-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="31e31-185">After the TXT records are completed, the Commerce team will complete the Azure Front Door updates for the domain that will set up the SSL certificate.</span></span>

## <a name="apex-domains"></a><span data-ttu-id="31e31-186">Apex-domäner</span><span class="sxs-lookup"><span data-stu-id="31e31-186">Apex domains</span></span>

<span data-ttu-id="31e31-187">Den Commerce-tillhandahållna Azure Front Door-instansen stöder inte apex-domäner (rotdomäner som inte innehåller underdomäner).</span><span class="sxs-lookup"><span data-stu-id="31e31-187">The Commerce-supplied Azure Front Door instance does not support apex domains (root domains that do not contain subdomains).</span></span> <span data-ttu-id="31e31-188">Apex-domäner kräver en IP-adress för att kunna matcha och Commerce Azure Front Door-instans finns endast med virtuella slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="31e31-188">Apex domains require an IP address to resolve, and the Commerce Azure Front Door instance exists with virtual endpoints only.</span></span> <span data-ttu-id="31e31-189">Om du vill använda en apex-domän har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="31e31-189">To use an apex domain, you have two options:</span></span>

- <span data-ttu-id="31e31-190">**Alternativ 1** - Använd din DNS-provider för att omdirigera apex-domänen till en "www"-domän.</span><span class="sxs-lookup"><span data-stu-id="31e31-190">**Option 1** - Use your DNS provider to redirect the apex domain to a "www" domain.</span></span> <span data-ttu-id="31e31-191">Fabrikam.com omdirigeras till exempel till den `www.fabrikam.com` där `www.fabrikam.com` är CNAME-posten som pekar mot den Commerce-värdbaserade Azure Front Door-instansen.</span><span class="sxs-lookup"><span data-stu-id="31e31-191">For example, fabrikam.com redirects to `www.fabrikam.com` where `www.fabrikam.com` is the CNAME record that points to the Commerce-hosted Azure Front Door instance.</span></span>

- <span data-ttu-id="31e31-192">**Alternativ 2** - Ställ in en CDN/Front Door-instans som värd för apex-domänen.</span><span class="sxs-lookup"><span data-stu-id="31e31-192">**Option 2** - Set up a CDN/front door instance on your own to host the apex domain.</span></span>

> [!NOTE]
> <span data-ttu-id="31e31-193">Om du använder Azure Front Door måste du också ställa in en Azure DNS i samma prenumeration.</span><span class="sxs-lookup"><span data-stu-id="31e31-193">If you are using Azure Front Door, you must also set up an Azure DNS in the same subscription.</span></span> <span data-ttu-id="31e31-194">Apex-domänen som finns på Azure DNS kan peka mot din Azure Front Door som en aliaspost.</span><span class="sxs-lookup"><span data-stu-id="31e31-194">The apex domain hosted on Azure DNS can point to your Azure Front Door as an alias record.</span></span> <span data-ttu-id="31e31-195">Detta är det enda problemet, eftersom apex-domäner alltid måste peka mot en IP-adress.</span><span class="sxs-lookup"><span data-stu-id="31e31-195">This is the only work around, as apex domains must always point to an IP address.</span></span>

  ## <a name="additional-resources"></a><span data-ttu-id="31e31-196">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="31e31-196">Additional resources</span></span>

  [<span data-ttu-id="31e31-197">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="31e31-197">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

  [<span data-ttu-id="31e31-198">Ställ in en kanal för onlinebutik</span><span class="sxs-lookup"><span data-stu-id="31e31-198">Set up an online store channel</span></span>](online-stores.md)

  [<span data-ttu-id="31e31-199">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="31e31-199">Create an e-commerce site</span></span>](create-ecommerce-site.md)

  [<span data-ttu-id="31e31-200">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="31e31-200">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

  [<span data-ttu-id="31e31-201">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="31e31-201">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

  [<span data-ttu-id="31e31-202">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="31e31-202">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

  [<span data-ttu-id="31e31-203">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="31e31-203">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

  [<span data-ttu-id="31e31-204">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="31e31-204">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

  [<span data-ttu-id="31e31-205">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="31e31-205">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

  [<span data-ttu-id="31e31-206">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="31e31-206">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

  [<span data-ttu-id="31e31-207">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="31e31-207">Enable location-based store detection</span></span>](enable-store-detection.md)
