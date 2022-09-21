---
title: Domäner i Dynamics 365 Commerce
description: I denna artikel beskrivs hur domäner hanteras i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 09/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 132aec92d2b3d2765dd6bd261fb4182f8aae679a
ms.sourcegitcommit: dbb997f252377b8884674edd95e66caf8d817816
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2022
ms.locfileid: "9465204"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domäner i Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur domäner hanteras i Microsoft Dynamics 365 Commerce.

Domäner är webbadresser som används för att navigera till Dynamics 365 Commerce webbplatser i en webbläsare. Du kontrollerar hanteringen av din domän med en vald DNS-leverantör (domännamnserver). Domäner refereras till i hela Dynamics 365 Commerce webbplatsskaparen för att koordinera hur en plats kommer att få åtkomst till när den publiceras. I denna artikel beskrivs hur domäner hanteras och refereras under hela livscykeln för webbplatsutveckling och start av Commerce.

> [!NOTE]
> Från och med 6 maj 2022 kommer alla miljöer som skapats i Dynamics 365 Commerce att tillhandahållas med domänen `.dynamics365commerce.ms` som ersätter det tidigare mönstret `.commerce.dynamics.com` Befintliga miljöer som etablerats med domänen `.commerce.dynamics.com` kommer att fortsätta att fungera.

## <a name="provisioning-and-supported-host-names"></a>Etablera och stödja värdnamn

När du etablerar en näthandelsmiljö i [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), används rutan **Värdnamn som stöds** på etableringsskärmen för näthandel för att ange domäner som ska associeras med den distribuerade Commerce-miljön. Dessa domäner blir de kundriktade DNS-namn (domännamnserver) där näthandelssajter värdbaseras. Att ange en domän i detta skede börjar inte att leda till att trafiken för domänen ändras till Dynamics 365 Commerce. Trafik för en domän skickas bara till Commerce-slutpunkten när DNS CNAME-posten uppdateras för att använda Commerce-slutpunkten för domänen.

> [!NOTE]
> Flera domäner kan anges i rutan **värdnamn som stöds** genom att avgränsa dem med semikolon.

I följande bild visas LCS-etableringsskärmen för näthandel med rutan **Värdnamn som stöds** markerad. 

![Etableringsskärmen för LCS-näthandel med rutan **Värdnamn som stöds** markerad.](./media/Domains_ProvisioningeCommerceScreen_publish.png)

Du kan skapa en tjänstbegäran om du vill lägga till fler domäner i en miljö om etableringen redan har genomförts. Om du vill skapa en tjänstbegäran i LCS, inom din miljö, går du till **Support \> Supportproblem** och väljer **Skicka en incident**.

## <a name="commerce-generated-urls"></a>Commerce-genererade URL

Vid etablering av en Dynamics 365 Commerce-näthandelsmiljö genererar Commerce en URL som blir miljöns arbetsadress. Denna URL refereras till i den näthandelssajtlänk som visas i LCS efter det att miljön har etablerats. En Commerce-genererad URL bär formatet `https://<e-commerce tenant name>.dynamics365commerce.ms`, där namnet på näthandelns klientorganisation är det namn som har angetts i LCS för Commerce-miljö.

Du kan också använda namn på produktionsplats värden i en sandbox-miljö. Det här alternativet är praktiskt när du vill kopiera en webbplats från en begränsat miljö till en produktion.

## <a name="site-setup"></a>Inställning av webbplats

När din näthandelsmiljö har etablerats måste du konfigurera din webbplats i Commerce-webbplatsbyggaren för att koppla webbplatsen till arbets-URL:en.

När du först skapar en webbplats i webbplatsskaparen visas dialogrutan **konfigurera plats**.

Bilden nedan visar dialogrutan visar **konfigurera din webbplats** för en webbplats med namnet "standard" när du öppnar webbplatsen för första gången i webbplatsskaparen.

![Dialogrutan **Konfigurera din webbplats**.](./media/Domains_SetupyoursiteScreen.png)

Med hjälp av rutan **Välj en domän** kan du associera ett av de värdnamn som stöds för din webbplats i LCS till webbplatsen i webbplatsskaparen.

Rutan **Sökväg** kan lämnas tom, eller så kan en extra sökvägssträng läggas till som återspeglas i arbets-URL:en. Om du lämnar rutan **Sökväg** tom kopplas den grundläggande Commerce-genererade URL med den webbplats som konfigureras i webbplatsskaparen. Sökvägar måste vara unika för varje plats/domän par. På den markerade platsen och domänen kan endast en plats i miljön använda den tomma sökvägen eller vara associerad med en unik sökvägssträng. Alla strängar som läggs till i fältet **Sökväg** under webbplatsinställningen kommer att bli en delväg till den grundläggande Commerce-genererade URL som används för att komma åt webbplatsen i en webbläsare.

> [!NOTE]
> Sökvägen kallas även **matchningssökväg** när en kanal läggs till i konfigurationsavsnittet i **webbplatsinställningar \> kanaler** i webbplatsskaparen.

Om du till exempel har en webbplats i webbplatsskaparen som kallas "Fabrikam" i en näthandelsklient med namnet "xyz" och du konfigurerar webbplatsen med en tom sökväg, får du tillgång till det publicerade webbplatsinnehållet i en webbläsare genom att gå direkt till den grundläggande Commerce-genererade URL:en:

`https://xyz.dynamics365commerce.ms`

Alternativt, om du har lagt till en sökväg på "Fabrikam" under samma platsinställningar, kommer du åt det publicerade webbplatsinnehållet i en webbläsare med hjälp av följande URL:

`https://xyz.dynamics365commerce.ms/fabrikam`

## <a name="pages-and-urls"></a>Sidor och URL-adresser

När din webbplats har konfigurerats med en sökväg, bygger alla URL-adresser som är kopplade till sidorna i webbplatsskaparen på arbets-URL:en (den genererade URL-adressen för Commerce eller den URL som genererades tillsammans med sökvägen) för platsen. Skapa en ny URL i webbplatsskaparen (**URLS /> +Ny**) genom att markera en sida i listan i dialogrutan **Ny URL** och anger URL-sökvägen för den sidan, associeras URL:en med den valda sidan. Värdet för URL-sökvägen läggs sedan till i webbplatsens arbets-URL för att komma åt sidan och betecknas som `./<URL path>` i URL-listan för sidan **URL** i webbplatsskaparen.

I följande bild visas dialogrutan **Ny URL** i webbplatsskaparen med en URL-exempelsökväg markerad. 

![Dialogrutan **Ny URL** i webbplatsskaparen.](./media/Domains_PageSetup2a.png)

I följande bild visas sidan **URL** i webbplatsskaparen med en URL-exempelsökväg markerad i listan.

![Kör användarflödesalternativ i policyflöde.](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domäner i webbplatsskaparen

De värden för värdnamn som stöds är tillgängliga för att associeras som en domän när en webbplats konfigureras. När du väljer ett värde för värdnamn som stöds som domän, visas den valda domänen som refereras till i webbplatsskaparen. Den här domänen är bara en referens inom Commerce-miljön, men den här domänen kommer inte att vidarebefordras till någon direkt trafik Dynamics 365 Commerce .

Om du arbetar med webbplatser i webbplatsskaparen, om du har två webbplatser inställda med två olika domäner, kan du lägga till attributet **?domain=** till din arbets-URL för att få åtkomst till det publicerade webbplatsinnehållet i en webbläsare.

Till exempel miljön "xyz" för att få åtkomst till det publicerade webbplats innehållet i en webbläsare: en med domänen `www.fabrikam.com` och den andra med domänen `www.constoso.com`. Varje webbplats skapades med en tom sökväg. Dessa två webbplatser kan sedan öppnas i en webbläsare enligt följande med hjälp av attributet **?domain=**:
- `https://xyz.dynamics365commerce.ms?domain=www.fabrikam.com`
- `https://xyz.dynamics365commerce.ms?domain=www.contoso.com`

Om ingen frågesträng för domän har angetts i en miljö med flera domäner, använder Commerce den första domän som du har angett. Om t.ex. sökvägen "Fabrikam" tillhandahölls först under webbplatskonfigurationen kan URL:en `https://xyz.dynamics365commerce.ms` användas för åtkomst till den publicerade webbplatsens innehållsplatsen för `www.fabrikam.com` .

## <a name="traffic-forwarding-in-production"></a>Vidarebefordran av trafik i produktion

Du kan simulera flera domäner med hjälp av parametrar för domänfrågor i själva commerce.dynamics.com slutpunkt. När du behöver gå in i produktionen måste du vidarebefordra trafiken för din anpassade domän till slutpunkten `<e-commerce tenant name>.dynamics365commerce.ms`.

Slutpunkten `<e-commerce tenant name>.dynamics365commerce.ms` stöder inte anpassade domän Secure Sockets Layers (SSL), så du måste konfigurera anpassade domäner med hjälp av Front Door Service eller ett CDN (Content Delivery Network). 

Om du vill konfigurera anpassade domäner med hjälp av en Front Door Service eller CDN har du två alternativ:

- Konfigurera en Front Door Service som Azure Front Door för att hantera klienttrafik och ansluta till din Commerce-miljö. Detta ger bättre kontroll över hantering av domäner och certifikat samt mer detaljerade säkerhetsprinciper.

- Använd den inlevererade Azure Front Door-instansen. Detta kräver samordning av åtgärden med Dynamics 365 Commerce-teamet för domänverifiering och för att hämta SSL-certifikat för din produktionsdomän.

> [!NOTE]
> Om du använder en extern CDN- eller ytterdörrstjänst, se till att förfrågan landar på Commerce-plattformen med det värdnamn som tillhandahålls av Commerce, men med X-Forwarded-Host (XFH)-huvudet\<custom-domain\>. Om till exempel din Commerce-slutpunkt är `xyz.dynamics365commerce.ms` och den anpassade domänen är `www.fabrikam.com`, ska värdrubriken för den vidarebefordrade begäran vara `xyz.dynamics365commerce.ms` och XFH-rubiken ska vara `www.fabrikam.com`.

Information om hur du konfigurerar en CDN-tjänst direkt finns i [lägga till stöd för ett Content Delivery Network (CDN)](add-cdn-support.md) .

Om du vill använda en Commerce-tillhandahållen Azure Front Door-instans måste du skapa en service begäran för CDN-inställningar hjälp från det inbyggda Commerce-integreringsteamet. 

- Du måste ange företagsnamn, produktionsdomän, miljö-ID och namnet på klientorganisationen för näthandel för produktionen. 
- Du måste bekräfta om detta är en befintlig domän (som används för en för tillfället aktiv plats) eller en ny domän. 
- För en ny domän kan domänverifiering och SSL-certifikat uppnås i ett enda steg. 
- För en domän som betjänar en befintlig webbplats, finns det en multistegsprocess som krävs för att upprätta domän verifieringen och SSL-certifikatet. Denna process har ett servicenivåavtal (7 arbetsdagar) för en domän att vara aktivt, eftersom det innehåller flera sekventiella steg.

Om du vill skapa en tjänstbegäran i LCS, inom din miljö, går du till **Support \> Supportproblem** och väljer **Skicka en incident**.

> [!NOTE]
> Anpassade domäner med SSL stöds endast i produktionsmiljöer. För miljöer utan produktion som sandbox-miljö och acceptanstest för användare (UAT) använder du den URL som genereras för att komma åt publicerat innehåll i en webbläsare.

## <a name="ssl-certificate-process"></a>SSL-certifikatprocess

När en servicebegäran lämnas in, kommer Commerce-teamet att koordinera följande steg med dig.

För nya domäner:
- Commerce-teamet konfigurerar Azure Front Door-instansen (Commerce-värdbaserad).
- Commerce-teamet kommer sedan att tillhandahålla CNAME-posten för att ange den anpassade domänen.
- När posten CNAME har uppdaterats kan Commerce-värdbaserad Azure Front Door -instans verifiera domänens ägare och hämta SSL-certifikatet.

För befintliga/aktiva domäner:
- Commerce-teamet instruerar dig att lägga till en `afdverify.<custom-domain>` CNAME-post som ska förse din domän-DNS-provider.
- När det är klart kommer Commerce-teamet att lägga till domänen i Azure Front Door-instansen och ange att ytterligare DNS TXT-poster ska läggas till i DNS för domänen.
- När TXT-posterna har slutförts kommer Commerce-teamet att slutföra de Azure Front Door-uppdateringarna för den domän som ska konfigurera SSL-certifikatet.

## <a name="apex-domains"></a>Apex-domäner

Den Commerce-tillhandahållna Azure Front Door-instansen stöder inte apex-domäner (rotdomäner som inte innehåller underdomäner). Apex-domäner kräver en IP-adress för att kunna matcha och Commerce Azure Front Door-instans finns endast med virtuella slutpunkter. Om du vill använda en apex-domän har du följande alternativ:

- **Alternativ 1** – Använd din DNS-provider för att omdirigera apex-domänen till en "www"-domän. Fabrikam.com omdirigeras till exempel till den `www.fabrikam.com` där `www.fabrikam.com` är CNAME-posten som pekar mot den Commerce-värdbaserade Azure Front Door-instansen.

- **Alternativ 2** – Om din DNS-leverantör har stöd för ALIAS-poster kan du peka a dns-domänen mot slutpunkten Azure Front Door, vilket säkerställer att IP-ändringen av slutpunkten återspeglas. Du måste själv vara värd för Azure Front Door-instans.
  
- **Alternativ 3** – Om din DNS-leverantör inte stöder ALIAS-poster måste du ändra din DNS-leverantör till Azure DNS och vara värd för både Azure DNS och instansen Azure Front Door-instans själv.

> [!NOTE]
> Om du använder Azure Front Door måste du också konfigurera en Azure DNS i samma prenumeration. Apex-domänen som finns på Azure DNS kan peka mot din Azure Front Door som en aliaspost. Detta är det enda problemet, eftersom apex-domäner alltid måste peka mot en IP-adress.
  
Om du har frågor om A-domäner kan du kontakta [Microsoft Support](https://support.microsoft.com/).

  ## <a name="additional-resources"></a>Ytterligare resurser

  [Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

  [Ställ in en kanal för onlinebutik](./channel-setup-online.md)

  [Skapa en näthandelssajt](create-ecommerce-site.md)

  [Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

  [Hantera robots.txt-filer](manage-robots-txt-files.md)

  [Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

  [Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

  [Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

  [Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

  [Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

  [Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
