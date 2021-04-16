---
title: Lägga till stöd för ett innehållsleveransnätverk (CDN)
description: I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a56f675b1fb43160625101a067c74e9fcf4f714a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797849"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="f9782-103">Lägga till stöd för nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="f9782-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f9782-104">I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="f9782-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="f9782-105">När du konfigurerar en näthandelsmiljö i Dynamics 365 Commerce kan du konfigurera den så att den fungerar med ditt CDN-tjänst.</span><span class="sxs-lookup"><span data-stu-id="f9782-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="f9782-106">Din anpassade domän kan aktiveras under etableringsprocessen för näthandelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="f9782-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="f9782-107">Du kan också använda en servicebegäran för att ställa in den när etableringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="f9782-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="f9782-108">Etableringsprocessen för näthandelsmiljön genererar ett värdnamn som associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="f9782-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="f9782-109">Det här värdnamnet har följande format, där \<*e-commerce-tenant-name*\> är namnet på din miljö:</span><span class="sxs-lookup"><span data-stu-id="f9782-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="f9782-110">&lt;näthandelsinnehavarens-namn&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="f9782-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="f9782-111">Värdnamnet eller slutpunkten som genereras under etableringsprocessen har stöd för ett SSL-certifikat (Secure Sockets Layer) för \*commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="f9782-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="f9782-112">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="f9782-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="f9782-113">Därför måste du avsluta SSL för anpassade domäner i CDN och vidarebefordra trafiken från CDN till värdnamnet eller slutpunkten som skapas av handel.</span><span class="sxs-lookup"><span data-stu-id="f9782-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="f9782-114">Dessutom behandlas *statik* (JavaScript eller övergripande formatmallar \[CSS\]-filer) från handel från den slutpunkt som genereras av handel (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f9782-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="f9782-115">Statisk kan endast cachelagras om värdnamnet eller slutpunkten som genereras av handel placeras bakom CDN.</span><span class="sxs-lookup"><span data-stu-id="f9782-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="f9782-116">Ställ in SSL</span><span class="sxs-lookup"><span data-stu-id="f9782-116">Set up SSL</span></span>

<span data-ttu-id="f9782-117">När du har etablerat din handelsmiljö med den anpassade domänen som tillhandahålls, eller när du har angett den anpassade domänen för din miljö med hjälp av en servicebegäran, du måste arbeta med Commerce-registreringsteamet för att planera DNS-ändringarna.</span><span class="sxs-lookup"><span data-stu-id="f9782-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="f9782-118">Som tidigare nämnts har det genererade värdnamnet eller slutpunkten endast stöd för ett SSL-certifikat för \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="f9782-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="f9782-119">Det stöder inte SSL för anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="f9782-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="f9782-120">CDN-tjänster</span><span class="sxs-lookup"><span data-stu-id="f9782-120">CDN services</span></span>

<span data-ttu-id="f9782-121">Alla CDN-tjänster kan användas med en handelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="f9782-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="f9782-122">Nedan följer två exempel:</span><span class="sxs-lookup"><span data-stu-id="f9782-122">Here are two examples:</span></span>

- <span data-ttu-id="f9782-123">**Microsoft Azure Front Door Service** – Azure CDN-lösningen.</span><span class="sxs-lookup"><span data-stu-id="f9782-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="f9782-124">Mer information om Azure Front Door Service finns i [dokumentationen för Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="f9782-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="f9782-125">**Akamai Dynamic Site Accelerator** – mer information finns i [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp)</span><span class="sxs-lookup"><span data-stu-id="f9782-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="f9782-126">Inställning av CDN</span><span class="sxs-lookup"><span data-stu-id="f9782-126">CDN setup</span></span>

<span data-ttu-id="f9782-127">Inställningen av CDN består av följande allmänna steg:</span><span class="sxs-lookup"><span data-stu-id="f9782-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="f9782-128">Lägg till en klientvärd.</span><span class="sxs-lookup"><span data-stu-id="f9782-128">Add a front-end host.</span></span>
1. <span data-ttu-id="f9782-129">Konfigurera en serverpool.</span><span class="sxs-lookup"><span data-stu-id="f9782-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="f9782-130">Ställ in regler för dirigering.</span><span class="sxs-lookup"><span data-stu-id="f9782-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="f9782-131">Lägg till en klientvärd</span><span class="sxs-lookup"><span data-stu-id="f9782-131">Add a front-end host</span></span>

<span data-ttu-id="f9782-132">Alla CDN-tjänster kan användas, men i det här avsnittet används Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f9782-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="f9782-133">Information om hur du ställer in Azure Front Door Service finns i [snabbstart: skapa en Front Door för ett mycket tillgängligt globalt webbprogram](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="f9782-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="f9782-134">Konfigurera en serverpool i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="f9782-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="f9782-135">För att konfigurera en serverpool i Azure Front Door Service, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f9782-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="f9782-136">Lägg till **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** till en serverpool som en anpassad värd som har en servervärdrubrik som är densamma som **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="f9782-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="f9782-137">Under **belastningsutjämning** lämna standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="f9782-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="f9782-138">Inaktivera hälsokontroller för serverpool.</span><span class="sxs-lookup"><span data-stu-id="f9782-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="f9782-139">I följande bild visas dialogrutan **Lägg till en serverpool** i Azure Front Door Service med serverpoolens värdnamn angivet.</span><span class="sxs-lookup"><span data-stu-id="f9782-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Lägga till en dialogruta för en serverpool](./media/CDN_BackendPool.png)

<span data-ttu-id="f9782-141">I följande bild visar dialogrutan **Lägg till en serverpool** i Azure Front Door Service med standardvärden för belastningsutjämning.</span><span class="sxs-lookup"><span data-stu-id="f9782-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Lägga till en dialogruta för en serverpool fortsatt](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="f9782-143">Se till att du inaktiverar **hälsosonder** när du ställer in din egen Azure Front Door-tjänst för Commerce.</span><span class="sxs-lookup"><span data-stu-id="f9782-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="f9782-144">Ställ in regler i Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="f9782-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="f9782-145">Så här skapar du en flödesregel i Azure Front Door Service:</span><span class="sxs-lookup"><span data-stu-id="f9782-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="f9782-146">Lägg till en flödesregel.</span><span class="sxs-lookup"><span data-stu-id="f9782-146">Add a routing rule.</span></span>
1. <span data-ttu-id="f9782-147">Skriv **Dokument** i fältet **Standard**.</span><span class="sxs-lookup"><span data-stu-id="f9782-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="f9782-148">I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="f9782-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="f9782-149">I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="f9782-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="f9782-150">Under **Mönster att matcha**, i det övre fältet anger du **/\***.</span><span class="sxs-lookup"><span data-stu-id="f9782-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="f9782-151">Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.</span><span class="sxs-lookup"><span data-stu-id="f9782-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="f9782-152">I fältet **Serverpool** välj **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="f9782-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="f9782-153">I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.</span><span class="sxs-lookup"><span data-stu-id="f9782-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="f9782-154">Ange alternativet **URL-omskrivning** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="f9782-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="f9782-155">Ange alternativet **cachelagring** till **inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="f9782-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="f9782-156">Om den domän som du ska använda redan är aktiv och publicerad, skapar du ett supportärende från panelen **Support** i [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) för att få hjälp med nästa steg.</span><span class="sxs-lookup"><span data-stu-id="f9782-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="f9782-157">Mer information finns i [Få support för Finance and Operations-appar eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="f9782-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="f9782-158">Om din domän är ny och inte är en befintlig aktiv domän kan du lägga till din anpassade domän i konfigurationen för Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f9782-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="f9782-159">Detta gör att webbtrafik kan dirigeras till din webbplats via Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f9782-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="f9782-160">Om du vill lägga till den anpassade domänen (t.ex. `www.fabrikam.com`), måste du konfigurera ett kanoniskt namn (CNAME) för domänen.</span><span class="sxs-lookup"><span data-stu-id="f9782-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="f9782-161">I följande bild visas dialogrutan **CNAME-konfiguration** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f9782-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan CNAME-konfiguration](./media/CNAME_Configuration.png)

<span data-ttu-id="f9782-163">Du kan använda Azure Front Door Service för att hantera certifikatet, eller så kan du använda ditt eget certifikat för den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="f9782-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="f9782-164">I följande bild visas dialogrutan **anpassade domän-HTTPS** i Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f9782-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Dialogrutan anpassad domän-HTTPS](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="f9782-166">Detaljerad information om hur du lägger till en anpassad domän i din Azure Front Door Service finns i [lägga till en anpassad domän i din Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="f9782-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="f9782-167">Din CDN ska nu vara korrekt konfigurerad så att den kan användas med din näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="f9782-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9782-168">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f9782-168">Additional resources</span></span>

[<span data-ttu-id="f9782-169">Implementeringsalternativ för Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="f9782-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
