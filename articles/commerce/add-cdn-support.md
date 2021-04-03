---
title: Lägga till stöd för ett innehållsleveransnätverk (CDN)
description: I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582729"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="63ebd-103">Lägga till stöd för nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="63ebd-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="63ebd-104">I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="63ebd-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="63ebd-105">När du konfigurerar en näthandelsmiljö i Dynamics 365 Commerce kan du konfigurera den så att den fungerar med ditt CDN-tjänst.</span><span class="sxs-lookup"><span data-stu-id="63ebd-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="63ebd-106">Din anpassade domän kan aktiveras under etableringsprocessen för näthandelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="63ebd-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="63ebd-107">Du kan också använda en servicebegäran för att ställa in den när etableringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="63ebd-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="63ebd-108">Etableringsprocessen för näthandelsmiljön genererar ett värdnamn som associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="63ebd-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="63ebd-109">Det här värdnamnet har följande format, där \<*e-commerce-tenant-name*\> är namnet på din miljö:</span><span class="sxs-lookup"><span data-stu-id="63ebd-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="63ebd-110">&lt;näthandelsinnehavarens-namn&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="63ebd-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="63ebd-111">Värdnamnet eller slutpunkten som genereras under etableringsprocessen har stöd för ett SSL-certifikat (Secure Sockets Layer) för \*commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="63ebd-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="63ebd-112">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="63ebd-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="63ebd-113">Därför måste du avsluta SSL för anpassade domäner i CDN och vidarebefordra trafiken från CDN till värdnamnet eller slutpunkten som skapas av handel.</span><span class="sxs-lookup"><span data-stu-id="63ebd-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="63ebd-114">Dessutom behandlas *statik* (JavaScript eller övergripande formatmallar \[CSS\]-filer) från handel från den slutpunkt som genereras av handel (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="63ebd-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="63ebd-115">Statisk kan endast cachelagras om värdnamnet eller slutpunkten som genereras av handel placeras bakom CDN.</span><span class="sxs-lookup"><span data-stu-id="63ebd-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="63ebd-116">Ställa in SSL</span><span class="sxs-lookup"><span data-stu-id="63ebd-116">Set up SSL</span></span>

<span data-ttu-id="63ebd-117">För att garantera att SSL konfigureras och att statisk cachelagras måste du konfigurera ditt CDN så att det är associerat med det värdnamn som skapas i handel för miljön.</span><span class="sxs-lookup"><span data-stu-id="63ebd-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="63ebd-118">Du måste också cachelagra följande mönster för statisk:</span><span class="sxs-lookup"><span data-stu-id="63ebd-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="63ebd-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="63ebd-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="63ebd-120">När du har etablerat din handelsmiljö med den anpassade domänen som tillhandahålls, eller när du har angett den anpassade domänen för din miljö med hjälp av en servicebegäran, pekar du på den anpassade domänen efter det värdnamn eller den slut punkt som skapas av handel.</span><span class="sxs-lookup"><span data-stu-id="63ebd-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="63ebd-121">Som tidigare nämnts har det genererade värdnamnet eller slutpunkten endast stöd för ett SSL-certifikat för \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="63ebd-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="63ebd-122">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="63ebd-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="63ebd-123">CDN-tjänster</span><span class="sxs-lookup"><span data-stu-id="63ebd-123">CDN services</span></span>

<span data-ttu-id="63ebd-124">Alla CDN-tjänster kan användas med en handelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="63ebd-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="63ebd-125">Nedan följer två exempel:</span><span class="sxs-lookup"><span data-stu-id="63ebd-125">Here are two examples:</span></span>

- <span data-ttu-id="63ebd-126">**Microsoft Azure Front Door Service** – Azure CDN-lösningen.</span><span class="sxs-lookup"><span data-stu-id="63ebd-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="63ebd-127">Mer information om Azure Front Door Service finns i [dokumentationen för Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="63ebd-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="63ebd-128">**Akamai Dynamic Site Accelerator** – mer information finns i [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp)</span><span class="sxs-lookup"><span data-stu-id="63ebd-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="63ebd-129">Inställning av CDN</span><span class="sxs-lookup"><span data-stu-id="63ebd-129">CDN setup</span></span>

<span data-ttu-id="63ebd-130">Inställningen av CDN består av följande allmänna steg:</span><span class="sxs-lookup"><span data-stu-id="63ebd-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="63ebd-131">Lägg till en klientvärd.</span><span class="sxs-lookup"><span data-stu-id="63ebd-131">Add a front-end host.</span></span>
1. <span data-ttu-id="63ebd-132">Konfigurera en serverpool.</span><span class="sxs-lookup"><span data-stu-id="63ebd-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="63ebd-133">Ställ in regler för flöde och cachelagring.</span><span class="sxs-lookup"><span data-stu-id="63ebd-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="63ebd-134">Lägg till en klientvärd</span><span class="sxs-lookup"><span data-stu-id="63ebd-134">Add a front-end host</span></span>

<span data-ttu-id="63ebd-135">Alla CDN-tjänster kan användas, men i det här avsnittet används Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="63ebd-136">Information om hur du ställer in Azure Front Door Service finns i [snabbstart: skapa en Front Door för ett mycket tillgängligt globalt webbprogram](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="63ebd-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="63ebd-137">Konfigurera en serverpool i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="63ebd-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="63ebd-138">För att konfigurera en serverpool i Azure Front Door Service, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="63ebd-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="63ebd-139">Lägg till **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** till en serverpool som en anpassad värd som har en tom servervärdrubrik.</span><span class="sxs-lookup"><span data-stu-id="63ebd-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="63ebd-140">Under **belastningsutjämning** lämna standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="63ebd-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="63ebd-141">I följande bild visas dialogrutan **Lägg till en serverpool** i Azure Front Door Service med serverpoolens värdnamn angivet.</span><span class="sxs-lookup"><span data-stu-id="63ebd-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Lägga till en dialogruta för en serverpool](./media/CDN_BackendPool.png)

<span data-ttu-id="63ebd-143">I följande bild visar dialogrutan **Lägg till en serverpool** i Azure Front Door Service med standardvärden för belastningsutjämning.</span><span class="sxs-lookup"><span data-stu-id="63ebd-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Lägga till en dialogruta för en serverpool fortsatt](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="63ebd-145">Ställ in regler i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="63ebd-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="63ebd-146">Så här skapar du en flödesregel i Azure Front Door Service:</span><span class="sxs-lookup"><span data-stu-id="63ebd-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="63ebd-147">Lägg till en flödesregel.</span><span class="sxs-lookup"><span data-stu-id="63ebd-147">Add a routing rule.</span></span>
1. <span data-ttu-id="63ebd-148">Skriv **Dokument** i fältet **Standard**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="63ebd-149">I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="63ebd-150">I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="63ebd-151">Under **Mönster att matcha**, i det övre fältet anger du **/\***.</span><span class="sxs-lookup"><span data-stu-id="63ebd-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="63ebd-152">Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="63ebd-153">I fältet **Serverpool** välj **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="63ebd-154">I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="63ebd-155">Ange alternativet **URL-omskrivning** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="63ebd-156">Ange alternativet **cachelagring** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="63ebd-157">Så här skapar du en cachelagringsregel i Azure Front Door Service:</span><span class="sxs-lookup"><span data-stu-id="63ebd-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="63ebd-158">Lägg till en cachelagringsregel.</span><span class="sxs-lookup"><span data-stu-id="63ebd-158">Add a caching rule.</span></span>
1. <span data-ttu-id="63ebd-159">Skriv **statisk** i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="63ebd-160">I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="63ebd-161">I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="63ebd-162">Under **Mönster att matcha**, i det övre fältet, **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="63ebd-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="63ebd-163">Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="63ebd-164">I fältet **Serverpool** välj **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="63ebd-165">I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="63ebd-166">Ange alternativet **URL-omskrivning** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="63ebd-167">Ange alternativet **cachelagring** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="63ebd-168">I fältet **Fråga strängcachelagring** välj **cachelagra varje unik URL**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="63ebd-169">I fältgruppen **dynamisk komprimering** välj alternativet **aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="63ebd-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="63ebd-170">I följande bild visas dialogrutan **Lägg till en regel** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan Lägg till en regel](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="63ebd-172">Om den domän som du ska använda redan är aktiv och publicerad, skapar du ett supportärende från panelen **Support** i [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) för att få hjälp med nästa steg.</span><span class="sxs-lookup"><span data-stu-id="63ebd-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="63ebd-173">Mer information finns i [Få support för Finance and Operations-appar eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="63ebd-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="63ebd-174">Om din domän är ny och inte är en befintlig aktiv domän kan du lägga till din anpassade domän i konfigurationen för Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="63ebd-175">Detta gör att webbtrafik kan dirigeras till din webbplats via Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="63ebd-176">Om du vill lägga till den anpassade domänen (t.ex. `www.fabrikam.com`), måste du konfigurera ett kanoniskt namn (CNAME) för domänen.</span><span class="sxs-lookup"><span data-stu-id="63ebd-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="63ebd-177">I följande bild visas dialogrutan **CNAME-konfiguration** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan CNAME-konfiguration](./media/CNAME_Configuration.png)

<span data-ttu-id="63ebd-179">Du kan använda Azure Front Door Service för att hantera certifikatet, eller så kan du använda ditt eget certifikat för den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="63ebd-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="63ebd-180">I följande bild visas dialogrutan **anpassade domän-HTTPS** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="63ebd-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan anpassad domän-HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="63ebd-182">Detaljerad information om hur du lägger till en anpassad domän i din Azure Front Door Service finns i [lägga till en anpassad domän i din Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="63ebd-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="63ebd-183">Din CDN ska nu vara korrekt konfigurerad så att den kan användas med din näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="63ebd-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63ebd-184">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="63ebd-184">Additional resources</span></span>

[<span data-ttu-id="63ebd-185">Implementeringsalternativ för Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="63ebd-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
