---
title: Lägga till stöd för nätverk för innehållsleverans
description: I denna artikel beskrivs hur du lägger till ett nätverk för innehållsleverans (CDN) i din Microsoft Dynamics 365 Commerce-miljö.
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
ms.openlocfilehash: 2177eeb6497269d580d2baea87ebb4fcd395223b
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069679"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Lägga till stöd för nätverk för innehållsleverans

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du lägger till ett nätverk för innehållsleverans (CDN) i din Microsoft Dynamics 365 Commerce-miljö.

När du konfigurerar en näthandelsmiljö i Dynamics 365 Commerce kan du konfigurera den så att den fungerar med ditt CDN-tjänst. 

Din anpassade domän kan aktiveras under etableringsprocessen för näthandelsmiljön. Du kan också använda en servicebegäran för att konfigurera den när etableringen har slutförts. Etableringsprocessen för näthandelsmiljön genererar ett värdnamn som associeras med miljön. Det här värdnamnet har följande format, där \<*e-commerce-tenant-name*\> är namnet på din miljö:

&lt;näthandelsinnehavarens-namn&gt;.commerce.dynamics.com

Värdnamnet eller slutpunkten som genereras under etableringsprocessen har stöd för ett SSL-certifikat (Secure Sockets Layer) för \*commerce.dynamics.com. Det stöder inte SSL för anpassade domäner. Därför måste du avsluta SSL för anpassade domäner i CDN och vidarebefordra trafiken från CDN till värdnamnet eller slutpunkten som skapas av handel. 

Dessutom behandlas *statik* (JavaScript eller övergripande formatmallar \[CSS\]-filer) från handel från den slutpunkt som genereras av handel (\*.commerce.dynamics.com). Statisk kan endast cachelagras om värdnamnet eller slutpunkten som genereras av handel placeras bakom CDN.

## <a name="set-up-ssl"></a>Ställ in SSL

När du har etablerat din handelsmiljö med den anpassade domänen som tillhandahålls, eller när du har angett den anpassade domänen för din miljö med hjälp av en servicebegäran, du måste arbeta med Commerce-registreringsteamet för att planera DNS-ändringarna.

Som tidigare nämnts har det genererade värdnamnet eller slutpunkten endast stöd för ett SSL-certifikat för \*.commerce.dynamics.com. Det stöder inte SSL för anpassade domäner.

## <a name="cdn-services"></a>CDN-tjänster

Alla CDN-tjänster kan användas med en handelsmiljö. Nedan följer två exempel:

- **Microsoft Azure Front Door Service** – Azure CDN-lösningen. Mer information om Azure Front Door Service finns i [dokumentationen för Azure Front Door Service](/azure/frontdoor/).
- **Akamai Dynamic Site Accelerator** – mer information finns i [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp)

## <a name="cdn-setup"></a>Inställning av CDN

Inställningen av CDN består av följande allmänna steg:

1. Lägg till en klientvärd.
1. Konfigurera en serverpool.
1. Ställ in regler för dirigering.

### <a name="add-a-front-end-host"></a>Lägg till en klientvärd

Alla CDN-tjänster kan användas, men i exemplet i denna artikel Azure Front Door Service. 

Information om hur du konfigurerar Azure Front Door Service finns i [snabbstart: skapa en Front Door för ett mycket tillgängligt globalt webbprogram](/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Konfigurera en serverpool i Azure Front Door Service

För att konfigurera en serverpool i Azure Front Door Service, följ dessa steg.

1. Lägg till **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** till en serverpool som en anpassad värd som har en servervärdrubrik som är densamma som **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.
1. Under **belastningsutjämning** lämna standardvärdena.
1. Inaktivera hälsokontroller för serverpool.

I följande bild visas dialogrutan **Lägg till en serverpool** i Azure Front Door Service med serverpoolens värdnamn angivet.

![Lägga till en dialogruta för en serverpool.](./media/CDN_BackendPool.png)

I följande bild visar dialogrutan **Lägg till en serverpool** i Azure Front Door Service med standardvärden för belastningsutjämning.

![Lägga till en dialogruta för en serverpool (forts.)](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Se till att du inaktiverar **hälsosonder** när du konfigurerar din egen Azure Front Door-tjänst för Commerce.


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


> [!WARNING]
> Om den domän som du ska använda redan är aktiv och publicerad, skapar du ett supportärende från panelen **Support** i [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) för att få hjälp med nästa steg. Mer information finns i [Få hjälp med appar för ekonomi och drift eller Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Om din domän är ny och inte är en befintlig aktiv domän kan du lägga till din anpassade domän i konfigurationen för Azure Front Door Service. Detta gör att webbtrafik kan dirigeras till din webbplats via Azure Front Door Service. Om du vill lägga till den anpassade domänen (t.ex. `www.fabrikam.com`), måste du konfigurera ett kanoniskt namn (CNAME) för domänen.

I följande bild visas dialogrutan **CNAME-konfiguration** i Azure Front Door Service.

![Dialogrutan CNAME-konfiguration.](./media/CNAME_Configuration.png)

Du kan använda Azure Front Door Service för att hantera certifikatet, eller så kan du använda ditt eget certifikat för den anpassade domänen.

I följande bild visas dialogrutan **anpassade domän-HTTPS** i Azure Front Door Service.

![Dialogrutan HTTPS för anpassad domän.](./media/Custom_Domain_HTTPS.png)

Detaljerad information om hur du lägger till en anpassad domän i din Azure Front Door Service finns i [lägga till en anpassad domän i din Front Door](/azure/frontdoor/front-door-custom-domain).

Din CDN ska nu vara korrekt konfigurerad så att den kan användas med din näthandelssajt.

## <a name="additional-resources"></a>Ytterligare resurser

[Implementeringsalternativ för Content Delivery Network](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
