---
title: Lägga till stöd för ett innehållsleveransnätverk (CDN)
description: I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.
author: brianshook
manager: annbe
ms.date: 03/02/2020
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
ms.openlocfilehash: 23ac9d8844c2a8ae20bd316c40078319601a3a4d
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096735"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Lägga till stöd för ett innehållsleveransnätverk (CDN)


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett innehållsleveransnätverk (CDN) på Microsoft Dynamics 365 Commerce-miljön.

## <a name="overview"></a>Översikt

När du ställer in en näthandelsmiljö i Dynamics 365 Commerce kan du konfigurera den så att den fungerar med ditt CDN-tjänst. 

Din anpassade domän kan aktiveras under etableringsprocessen för näthandelsmiljön. Du kan också använda en serviceförfrågan för att ställa in den när etableringen har slutförts. Etableringsprocessen för näthandelsmiljön genererar ett värdnamn som associeras med miljön. Det här värdnamnet har följande format, där *e-handelsinnehavarens-namn* är namnet på din miljö:

&lt;e-handelsinnehavarens-namn&gt;.commerce.dynamics.com

Värdnamnet eller slutpunkten som genereras under etableringsprocessen har stöd för ett SSL-certifikat (Secure Sockets Layer) för \*commerce.dynamics.com. Det stöder inte SSL för anpassade domäner. Därför måste du avsluta SSL för anpassade domäner i CDN och vidarebefordra trafiken från CDN till värdnamnet eller slutpunkten som skapas av handel. 

Dessutom behandlas *statik* (JavaScript eller övergripande formatmallar \[CSS\]-filer) från handel från den slutpunkt som genereras av handel (\*.commerce.dynamics.com). Statisk kan endast cachelagras om värdnamnet eller slutpunkten som genereras av handel placeras bakom CDN.

## <a name="set-up-ssl"></a>Ställa in SSL

För att garantera att SSL konfigureras och att statisk cachelagras måste du konfigurera ditt CDN så att det är associerat med det värdnamn som skapas i handel för miljön. Du måste också cachelagra följande mönster för statisk: 

/\_msdyn365/\_scnr/\*

När du har etablerat din handelsmiljö med den anpassade domänen som tillhandahålls, eller när du har angett den anpassade domänen för din miljö med hjälp av en serviceförfrågan, pekar du på den anpassade domänen efter det värdnamn eller den slut punkt som skapas av handel.

Som tidigare nämnts har det genererade värdnamnet eller slutpunkten endast stöd för ett SSL-certifikat för \*.commerce.dynamics.com. Det stöder inte SSL för anpassade domäner.

## <a name="cdn-services"></a>CDN-tjänster

Alla CDN-tjänster kan användas med en handelsmiljö. Nedan följer två exempel:

- **Microsoft Azure Front Door Service** – Azure CDN-lösningen. Mer information om Azure Front Door Service finns i [dokumentationen för Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Akamai Dynamic Site Accelerator** – mer information finns i [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp)

## <a name="cdn-setup"></a>Inställning av CDN

Inställningen av CDN består av följande allmänna steg:

1. Lägg till en klientvärd.
1. Konfigurera en serverpool.
1. Ställ in regler för flöde och cachelagring.

### <a name="add-a-front-end-host"></a>Lägg till en klientvärd

Alla CDN-tjänster kan användas, men i det här avsnittet används Azure Front Door Service. 

Information om hur du ställer in Azure Front Door Service finns i [snabbstart: skapa en Front Door för ett mycket tillgängligt globalt webbprogram](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a>Konfigurera en serverpool i Azure Front Door Service

För att konfigurera en serverpool i Azure Front Door Service, följ dessa steg.

1. Lägg till **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** till en serverpool som en anpassad värd som har en tom servervärdrubrik.
1. Under **hälsosonder** i fältet **sökväg** ange **/keepalive**.
1. I fältet **intervall (sekunder)** anger du **255**.
1. Under **belastningsutjämning** lämna standardvärdena.

I följande bild visas dialogrutan **Lägg till en serverpool** i Azure Front Door Service.

![Lägga till en dialogruta för en serverpool](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a>Ställ in regler i Azure Front Door Service

Så här skapar du en flödesregel i Azure Front Door Service:

1. Lägg till en flödesregel.
1. Skriv **Dokument** i fältet **Standard**.
1. I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.
1. I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.
1. Under **Mönster att matcha**, i det övre fältet anger du **/\***.
1. Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.
1. I fältet **Serverpool** välj **ecom-backend**.
1. I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**. 
1. Ange alternativet **URL-omskrivning** till **inaktiverad**.
1. Ange alternativet **cachelagring** till **inaktiverad**.

Så här skapar du en cachelagringsregel i Azure Front Door Service:

1. Lägg till en cachelagringsregel.
1. Skriv **statisk** i fältet **namn**.
1. I fältet **accepterat protokoll**, välj **HTTP och HTTPS**.
1. I fältet **Klientvärd** ange **dynamics-ecom-tenant-name.azurefd.net**.
1. Under **Mönster att matcha**, i det övre fältet, **/\_msdyn365/\_scnr/\***.
1. Under **Flödesdetaljer**, ange alternativet **Flödestyp** till **Framåt**.
1. I fältet **Serverpool** välj **ecom-backend**.
1. I fältgruppen **Vidarebefordringsprotokoll** välj alternativet **Matcha begäran**.
1. Ange alternativet **URL-omskrivning** till **inaktiverad**.
1. Ange alternativet **cachelagring** till **inaktiverad**.
1. I fältet **Fråga strängcachelagring** välj **cachelagra varje unik URL**.
1. I fältgruppen **dynamisk komprimering** välj alternativet **aktiverad**.

I följande bild visas dialogrutan **Lägg till en regel** i Azure Front Door Service.

![Dialogrutan Lägg till en regel](./media/CDN_CachingRule.png)

När den här inledande konfigurationen har distribuerats måste du lägga till din anpassade domän i konfigurationen för Azure Front Door Service. Om du vill lägga till den anpassade domänen (t.ex. `www.fabrikam.com`), måste du konfigurera ett kanoniskt namn (CNAME) för domänen.

I följande bild visas dialogrutan **CNAME-konfiguration** i Azure Front Door Service.

![Dialogrutan CNAME-konfiguration](./media/CNAME_Configuration.png)

> [!NOTE]
> Om den domän som du ska använda redan är aktiv och publicerad kontaktar du support för att aktivera den här domänen med Azure Front Door Service för att ställa in ett test.

Du kan använda Azure Front Door Service för att hantera certifikatet, eller så kan du använda ditt eget certifikat för den anpassade domänen.

I följande bild visas dialogrutan **anpassade domän-HTTPS** i Azure Front Door Service.

![Dialogrutan anpassad domän-HTTPS](./media/Custom_Domain_HTTPS.png)

Din CDN ska nu vara korrekt konfigurerad så att den kan användas med din näthandelsplats.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Ställ in en kanal för onlinebutik](online-stores.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överföring av URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
