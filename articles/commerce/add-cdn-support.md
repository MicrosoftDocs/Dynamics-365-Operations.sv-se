---
title: Lägga till stöd för ett innehållsleveransnätverk (CDN)
description: I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.
author: brianshook
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf5a0da2803f985e6c0c04dd9916977397173d11
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001632"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="4b888-103">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="4b888-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4b888-104">I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="4b888-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="4b888-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4b888-105">Overview</span></span>

<span data-ttu-id="4b888-106">När du ställer in en näthandelsmiljö i Dynamics 365 Commerce kan du konfigurera den så att den fungerar med ditt CDN-tjänst.</span><span class="sxs-lookup"><span data-stu-id="4b888-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="4b888-107">Din anpassade domän kan aktiveras under etableringsprocessen för näthandelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="4b888-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="4b888-108">Du kan också använda en serviceförfrågan för att ställa in den när etableringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="4b888-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="4b888-109">Etableringsprocessen för näthandelsmiljön genererar ett värdnamn som associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="4b888-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="4b888-110">Det här värdnamnet har följande format, där *e-handelsinnehavarens-namn* är namnet på din miljö:</span><span class="sxs-lookup"><span data-stu-id="4b888-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="4b888-111">&lt;e-handelsinnehavarens-namn&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="4b888-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="4b888-112">Värdnamnet eller slutpunkten som genereras under etableringsprocessen har stöd för ett SSL-certifikat (Secure Sockets Layer) för \*commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="4b888-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="4b888-113">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="4b888-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="4b888-114">Därför måste du avsluta SSL för anpassade domäner i CDN och vidarebefordra trafiken från CDN till värdnamnet eller slutpunkten som skapas av handel.</span><span class="sxs-lookup"><span data-stu-id="4b888-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="4b888-115">Dessutom behandlas *statik* (JavaScript eller övergripande formatmallar \[CSS\]-filer) från handel från den slutpunkt som genereras av handel (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="4b888-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="4b888-116">Statisk kan endast cachelagras om värdnamnet eller slutpunkten som genereras av handel placeras bakom CDN.</span><span class="sxs-lookup"><span data-stu-id="4b888-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="4b888-117">Ställa in SSL</span><span class="sxs-lookup"><span data-stu-id="4b888-117">Set up SSL</span></span>

<span data-ttu-id="4b888-118">För att garantera att SSL konfigureras och att statisk cachelagras måste du konfigurera ditt CDN så att det är associerat med det värdnamn som skapas i handel för miljön.</span><span class="sxs-lookup"><span data-stu-id="4b888-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="4b888-119">Du måste också cachelagra följande mönster för statisk:</span><span class="sxs-lookup"><span data-stu-id="4b888-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="4b888-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="4b888-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="4b888-121">När du har etablerat din handelsmiljö med den anpassade domänen som tillhandahålls, eller när du har angett den anpassade domänen för din miljö med hjälp av en serviceförfrågan, pekar du på den anpassade domänen efter det värdnamn eller den slut punkt som skapas av handel.</span><span class="sxs-lookup"><span data-stu-id="4b888-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="4b888-122">Som tidigare nämnts har det genererade värdnamnet eller slutpunkten endast stöd för ett SSL-certifikat för \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="4b888-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="4b888-123">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="4b888-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="4b888-124">CDN-tjänster</span><span class="sxs-lookup"><span data-stu-id="4b888-124">CDN services</span></span>

<span data-ttu-id="4b888-125">Alla CDN-tjänster kan användas med en handelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="4b888-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="4b888-126">Nedan följer två exempel:</span><span class="sxs-lookup"><span data-stu-id="4b888-126">Here are two examples:</span></span>

- <span data-ttu-id="4b888-127">**Microsoft Azure Front Door Service** – Azure CDN-lösningen.</span><span class="sxs-lookup"><span data-stu-id="4b888-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="4b888-128">Mer information om Azure Front Door Service finns i [dokumentationen för Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="4b888-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="4b888-129">**Akamai Dynamic Site Accelerator** – mer information finns i [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp)</span><span class="sxs-lookup"><span data-stu-id="4b888-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="4b888-130">Inställning av CDN</span><span class="sxs-lookup"><span data-stu-id="4b888-130">CDN setup</span></span>

<span data-ttu-id="4b888-131">Inställningen av CDN består av följande allmänna steg:</span><span class="sxs-lookup"><span data-stu-id="4b888-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="4b888-132">Lägg till en klientvärd.</span><span class="sxs-lookup"><span data-stu-id="4b888-132">Add a front-end host.</span></span>
1. <span data-ttu-id="4b888-133">Konfigurera en serverpool.</span><span class="sxs-lookup"><span data-stu-id="4b888-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="4b888-134">Ställ in regler för flöde och cachelagring.</span><span class="sxs-lookup"><span data-stu-id="4b888-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="4b888-135">Lägg till en klientvärd</span><span class="sxs-lookup"><span data-stu-id="4b888-135">Add a front-end host</span></span>

<span data-ttu-id="4b888-136">Alla CDN-tjänster kan användas, men i det här avsnittet används Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="4b888-137">Information om hur du ställer in Azure Front Door Service finns i [snabbstart: skapa en Front Door för ett mycket tillgängligt globalt webbprogram](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="4b888-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="4b888-138">Konfigurera en serverpool i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="4b888-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="4b888-139">För att konfigurera en serverpool i Azure Front Door Service, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4b888-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="4b888-140">Lägg till **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** till en serverpool som en anpassad värd som har en tom servervärdrubrik.</span><span class="sxs-lookup"><span data-stu-id="4b888-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="4b888-141">Under **hälsosonder** i fältet **sökväg** ange **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="4b888-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="4b888-142">I fältet **intervall (sekunder)** anger du **255**.</span><span class="sxs-lookup"><span data-stu-id="4b888-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="4b888-143">Under **belastningsutjämning** lämna standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="4b888-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="4b888-144">I följande bild visas dialogrutan **Lägg till en serverpool** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Lägga till en dialogruta för en serverpool](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="4b888-146">Ställ in regler i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="4b888-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="4b888-147">Så här skapar du en flödesregel i Azure Front Door Service:</span><span class="sxs-lookup"><span data-stu-id="4b888-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="4b888-148">Lägg till en flödesregel.</span><span class="sxs-lookup"><span data-stu-id="4b888-148">Add a routing rule.</span></span>
1. <span data-ttu-id="4b888-149">Skriv **Dokument** i fältet **Standard**.</span><span class="sxs-lookup"><span data-stu-id="4b888-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="4b888-150">I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="4b888-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="4b888-151">I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="4b888-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="4b888-152">Under **Mönster att matcha**, i det övre fältet anger du **/\***.</span><span class="sxs-lookup"><span data-stu-id="4b888-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="4b888-153">Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.</span><span class="sxs-lookup"><span data-stu-id="4b888-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="4b888-154">I fältet **Serverpool** välj **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="4b888-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="4b888-155">I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.</span><span class="sxs-lookup"><span data-stu-id="4b888-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="4b888-156">Ange alternativet **URL-omskrivning** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4b888-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="4b888-157">Ange alternativet **cachelagring** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4b888-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="4b888-158">Så här skapar du en cachelagringsregel i Azure Front Door Service:</span><span class="sxs-lookup"><span data-stu-id="4b888-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="4b888-159">Lägg till en cachelagringsregel.</span><span class="sxs-lookup"><span data-stu-id="4b888-159">Add a caching rule.</span></span>
1. <span data-ttu-id="4b888-160">Skriv **statisk** i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="4b888-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="4b888-161">I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="4b888-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="4b888-162">I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="4b888-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="4b888-163">Under **Mönster att matcha**, i det övre fältet, **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="4b888-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="4b888-164">Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.</span><span class="sxs-lookup"><span data-stu-id="4b888-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="4b888-165">I fältet **Serverpool** välj **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="4b888-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="4b888-166">I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.</span><span class="sxs-lookup"><span data-stu-id="4b888-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="4b888-167">Ange alternativet **URL-omskrivning** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4b888-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="4b888-168">Ange alternativet **cachelagring** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4b888-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="4b888-169">I fältet **Fråga strängcachelagring** välj **cachelagra varje unik URL**.</span><span class="sxs-lookup"><span data-stu-id="4b888-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="4b888-170">I fältgruppen **dynamisk komprimering** välj alternativet **aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4b888-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="4b888-171">I följande bild visas dialogrutan **Lägg till en regel** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan Lägg till en regel](./media/CDN_CachingRule.png)

<span data-ttu-id="4b888-173">När den här inledande konfigurationen har distribuerats måste du lägga till din anpassade domän i konfigurationen för Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="4b888-174">Om du vill lägga till den anpassade domänen (t.ex. `www.fabrikam.com`), måste du konfigurera ett kanoniskt namn (CNAME) för domänen.</span><span class="sxs-lookup"><span data-stu-id="4b888-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="4b888-175">I följande bild visas dialogrutan **CNAME-konfiguration** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan CNAME-konfiguration](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="4b888-177">Om den domän som du ska använda redan är aktiv och publicerad kontaktar du support för att aktivera den här domänen med Azure Front Door Service för att ställa in ett test.</span><span class="sxs-lookup"><span data-stu-id="4b888-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="4b888-178">Du kan använda Azure Front Door Service för att hantera certifikatet, eller så kan du använda ditt eget certifikat för den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="4b888-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="4b888-179">I följande bild visas dialogrutan **anpassade domän-HTTPS** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="4b888-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan anpassad domän-HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="4b888-181">Din CDN ska nu vara korrekt konfigurerad så att den kan användas med din näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="4b888-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b888-182">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4b888-182">Additional resources</span></span>

[<span data-ttu-id="4b888-183">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="4b888-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="4b888-184">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="4b888-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="4b888-185">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="4b888-185">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4b888-186">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="4b888-186">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4b888-187">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="4b888-187">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="4b888-188">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="4b888-188">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="4b888-189">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="4b888-189">Enable location-based store detection</span></span>](enable-store-detection.md)
