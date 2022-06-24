---
title: Mappa kanaler till näthandelsplatser
description: Denna artikel beskriver några av de vanligare kanalmappningsscenarierna i Microsoft Dynamics 365 Commerce som kan extrapoleras för de flesta andra affärsbehov.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 94c43df26e8d6e55a5b6d459b65066d5873e1063
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902773"
---
# <a name="map-channels-to-e-commerce-sites"></a>Mappa kanaler till näthandelsplatser

Denna artikel beskriver några av de vanligare kanalmappningsscenarierna i Microsoft Dynamics 365 Commerce som kan extrapoleras för de flesta andra affärsbehov.

Dynamics 365 Commerce har stöd för många affärsscenarier för mappning av [onlinekanaler](#channels) som har en konfigurerad uppsättning produkter, priser och rabatter till [näthandelsplatsupplevelser](#e-commerce-sites) för kunder.

I denna artikel beskrivs följande scenarier:

- **En kanal med ett språk som har en gemensam näthandelsupplevelse.** Det här scenariot kan till exempel gälla en enskild varumärkeswebbplats som har konfigurerats för den amerikanska-engelska marknaden.
- **En kanal med flera språk som har en enda lokalanpassad näthandelsupplevelse.** Det här scenariot kan till exempel gälla en enskild varumärkeswebbplats som har konfigurerats för Kanada med franskt och engelskt språkstöd. I det här scenariot får användare som väljer olika språk samma webbplatsupplevelse, men den kommer att lokalanpassas till varje användares valda språk.
- **En kanal med flera språk som har en olika näthandelsupplevelse per språk.** Det här scenariot kan till exempel gälla en enskild varumärkeswebbplats som har konfigurerats för Kanada med franskt och engelskt språkstöd. I det här scenariot finns det en unik webbplatsupplevelse för varje språk.
- **Flera kanaler (ett språk och/eller flera språk) som har en enda lokalanpassad webbplatsupplevelse.** Det här scenariot kan till exempel gälla en enskild varumärkeswebbplats som har konfigurerats för Australien och Nya Zeeland. I det här scenariot delar båda länderna samma webbplatsupplevelse på engelska, men varje land konfigureras med olika produkter, valuta, priser, rabatter och leveranssätt.
- **Flera kanaler (ett språk och/eller flera språk) som har olika webbplatsupplevelser per kanal.** Det här scenariot kan till exempel gälla en enskild varumärkeswebbplats som har konfigurerats för Australien, Kanada och Tyskland på flera språk. I det här scenariot har varje land en unik webbplatsupplevelse som konfigureras med olika produkter, valuta, priser, rabatter och leveranssätt.

## <a name="channels"></a>Kanaler

En kanal (även kallad onlinebutik eller onlinekanal) representerar en näthandelsbutik online som används för att mappa produkter, priser, rabatter, språk, betalningsmetoder, leveranssätt, uppfyllelsecenter och andra aspekter av onlineupplevelsen som kommer att vara tillgängliga för dina näthandelskunder. Kanaler skapas och hanteras i Commerce headquarters och mappas till en enda [juridisk person](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). Den juridiska personen är vanligtvis baserad i ett enskilt land som kräver momsrapportering för kanalen och kan bara konfigureras med en enda valuta.

Mer information om kanaler, se [Kanalöversikt](channels-overview.md). Mer information om hur du skapar en onlinekanal finns i [Ställa in en onlinekanal](channel-setup-online.md).

I följande exempelillustrationen från Commerce headquarters visas de onlinestandardkanaler som distribueras med Dynamics 365 Commerce om demodataalternativet har valts.

![Standardkanaler med demodata i Commerce headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Näthandelsplatser

En näthandelsplats innehåller en uppsättning webbplatssidor som kunderna använder när de bläddrar och handlar. Näthandelsplatser hanteras i Commerce-webbplatsbyggaren.

Mer information om hur du skapar och hanterar webbplatser i webbplatsbyggaren finns i [Näthandelsplats – översikt](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Vanliga scenarier för kanalmappning

Dynamics 365 Commerce har stöd för en mängd olika scenarier för kanalmappning. De scenarier för kanalmappning som följer är bara en delmängd av alla möjliga kanalmappningsscenarier. De är avsedda som en guide till hjälp när du planerar unika affärsscenarier. Det fiktiva Adventure Works sportbutik som ingår i Dynamics 365 Commerce-demodata används som ett exempel för varje scenario.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Kanal med ett språk som har en gemensam näthandelsupplevelse

I det mest grundläggande scenariot har en enskild kanal ett enda språk för försäljning på en enda marknad. Ett exempel på detta scenario är Adventure Works digitala sportbutik som bara är inställd för marknaden med amerikansk engelska.

Följande exempelillustration visar en kanalkonfiguration i Commerce headquarters. I den här konfigurationen stöder onlinekanalen bara ett språk (**en-us**), en enda valuta (**USD**) och en enda affärsenhet (**usrt**) som används för momsrapportering.

![Värden för juridisk person, valuta och språk för onlinebutiken Adventure Works som markerats i Commerce headquarters.](media/channel-mapping-3.png)

Den enda onlinekanalen kan mappas till en enda näthandelsplats i webbplatsbyggaren. Information om hur du skapar en ny webbplats och mappar den till en kanal finns i avsnittet [Mappa en kanal till en webbplats i webbplatsbyggaren](#map-a-channel-to-a-site-in-site-builder) i denna artikel.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Kanal med flera språk som har en enda lokalanpassad näthandelsupplevelse

I det här scenariot har en enda kanal stöd för mer än ett språk. Därför kan produktnamn, beskrivningar och attribut lokalanpassas i Commerce headquarters. Om du vill ha en fullständig lokalanpassad webbplatsupplevelse kan marknadsföringsinnehållet på webbplatsen också lokalanpassas i Commerce-webbplatsbyggaren.

Begränsningen i det här scenariot är att en enda kanal bara kan konfigureras med en valuta, en juridisk person och en uppsättning produkter och priser. Den här konfigurationen fungerar bäst för länder som har en gemensam valuta och flera språk (till exempel Kanada som har engelska och franska), en enda juridisk person samt en uppsättning produkter och priser.

Varje språk i en kanal kan konfigureras med sitt eget domännamn. `www.adventure-works.ca`-domänen kan till exempel konfigureras för den engelska versionen för Kanada och `www.adventure-works-fr.ca`-domänen kan konfigureras för den franska versionen för Kanada. Olika språk i en kanal kan också konfigureras i en enda domän, och sedan kan en annan sökväg användas för varje språk. `www.adventure-works.ca`-domänen kan till exempel konfigureras för den engelska versionen för Kanada sedan kan `www.adventure-works.ca/fr`-sökvägen användas för den franska versionen för Kanada. [Geoidentifiering](geo-detection-redirection.md) kan också aktiveras för att automatiskt omdirigera användaren till rätt webbplats, baserat på användarens plats.

Information om hur du aktiverar kunder för manuell växling mellan språk finns i avsnittet [Lägga till och konfigurera webbplatsväljarmodulen](#add-and-configure-the-site-picker-module) i denna artikel. Information om hur du anpassar lokalanpassade sidor och fragment finns i avsnittet [Hantera webbplatsinnehåll som har flera kanaler och språk](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Kanal med flera språk som har en olika näthandelsupplevelse per språk

Du kanske föredrar ett scenario där en enskild kanal har stöd för mer än ett språk, men en helt annan webbplatsupplevelse återges för varje språk. Den rekommenderade metoden när du inför det här scenariot är att använda [sidvarianter](#implement-page-variants-for-each-language) på en enda webbplats.

En annan metod är att skapa en ny näthandelsplats för varje språk i webbplatsbyggaren och sedan mappa varje webbplats till en enda onlinekanal och ett enda språk. Resultatet blir en enda onlinekanal som mappas till flera näthandelsplatser, en för varje språk. Den här metoden för flera webbplatser kräver extra hanteringsresurser, eftersom det finns mer än en webbplats att hantera i webbplatsbyggaren.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Flera kanaler (ett språk och/eller flera språk) som har en enda lokalanpassad webbplatsupplevelse

En varumärkt webbplats kanske kräver flera onlinekanaler per region för att stödja olika valutor, uppsättning produkter och priser för varje kanal på en enda webbplats. Adventure Works-webbplatsen kan till exempel ha en onlinekanal för den kanadensiska marknaden som har flera språk, en kanal för den amerikanska marknaden som har ett språk och en kanal för den tyska marknaden som har ett språk. I det här scenariot konfigureras varje onlinekanal för en regionspecifik juridisk person och kan ha samma uppsättning produkter som andra kanaler har, en delmängd av dessa produkter eller en annan uppsättning produkter. Varje kanal har också sina egna priser i den nationella valutan, momsen, rabatterna och leveranssätten.

I det här scenariot kan varje marknad konfigureras med sitt eget domännamn. `www.adventure-works.com`-domänen kan till exempel konfigureras för den amerikanska marknaden och `www.adventure-works.de`-domänen kan konfigureras för den tyska marknaden. Alternativt kan varje marknad konfigureras till att använda olika sökvägar. `www.adventure-works.com`-domänen kan till exempel konfigureras för den amerikanska marknaden och sedan kan `www.adventure-works.com/de`-sökvägen användas för den tyska marknaden. [Geoidentifiering](geo-detection-redirection.md) kan också aktiveras för att automatiskt omdirigera användare till rätt webbplats, baserat på användarens region.

Du kanske också vill att din webbplats ska innehålla en listrutan där användarna manuellt kan växla till en viss marknad. Mer information finns i avsnittet [Lägga till och konfigurera webbplatsväljarmodulen](#add-and-configure-the-site-picker-module) senare i denna artikel.

Information om hur du konfigurerar flera kanaler på en enda webbplats finns i avsnittet [Konfigurera flera kanaler på en näthandelsplats](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Flera kanaler (ett språk och/eller flera språk) som har olika webbplatsupplevelser per kanal

Du kanske vill ha flera kanaler för ett enskilt varumärke i olika regioner, och du kanske vill att varje region ska ha olika webbplatsupplevelser. Du kan implementera det här scenariot på två sätt:

- Använda [sidvarianter](#implement-page-variants-for-each-language).
- Konfigurera en annan webbplats för varje onlinekanal i webbplatsbyggaren och mappa sedan varje webbplats till en annan onlinekanal och språk. Den här metoden kräver extra hanteringsresurser, eftersom det finns mer än en webbplats att hantera i webbplatsbyggaren.

## <a name="cross-channel-sharing"></a>Aktivera delning mellan kanaler

Delning av flera kanaler är användbart när flera kanaler på en och samma plats kan dela innehåll. En återförsäljare som har flera märken och butiker som grupperas under en enskild plats kan dela visst innehåll bland vissa eller alla av butiker. Delat innehåll kan innehålla sidor med villkor, betalningsvillkor, leveransvillkor och vanliga frågor. Mer information finns i [Aktivera och använda delning i flera kanaler](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Mappa en kanal till en webbplats i webbplatsbyggaren

Det finns flera metoder för att skapa och konfigurera webbplatser för att använda olika onlinekanaler.

### <a name="create-a-new-site"></a>Skapa en ny webbplats

Du kan skapa en helt ny webbplats i webbplatsbyggaren genom att gå till listsidan **Webbplatser** och välja **Ny webbplats**. I dialogrutan **Ny webbplats** som visas kan du sedan välja standardonlinekanal och standardspråk för webbplatsen, enligt exempelillustrationen nedan.

![Skapa en ny kanal i webbplatsbyggaren.](media/channel-mapping-4.png)

Den webbplats du skapar på det här sättet är tom och innehåller inga webbplatssidor (till exempel en startsida, kategorisidor och produktsidor).

Mer information finns i [Skapa en näthandels](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Skapa en ny webbplats genom att använda kopieringsåtgärden för webbplatsen

I stället för att skapa en helt ny, tom webbplats enligt beskrivningen i det föregående avsnittet är det enklare att börja med en kopia av en av de webbplatser som finns i Commerce-modulbiblioteket, till exempel Fabrikam- eller Adventure Works-webbplatsen.

Om du vill kopiera en befintlig webbplats går du till listsidan **Webbplatser** i webbplatsverktyget och väljer **Kopiera webbplats**. I dialogrutan **Kopiera webbplats** som visas kan du sedan välja källwebbplats och ange namnet på destinationswebbplatsen.

Vid den här punkten kan du ännu inte välja standardonlinekanal och standardspråk för webbplatsen. Du kan dock konfigurera dessa egenskaper när kopieringen av webbplatsen har slutförts. När du först väljer webbplats på listsidan **Webbplatser** i webbplatsbyggaren visas dialogrutan **Konfigurera webbplats** där du kan välja standardkanal och standardspråk.

Mer information om webbplatskopiering finns i [Kopiera en näthandelsplats](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Hantera en befintlig webbplatskanal

När en webbplats har konfigurerats med en kanal kan du hantera och uppdatera kanalen inifrån den valda webbplatsen i webbplatsverktyget på **Webbplatsinställningar \> Kanaler**, enligt följande exempelillustration.

![Hantera kanalmappningen i webbplatsbyggaren.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Stöd för flera webbplatser i en enskild klientorganisation

Många varumärkta webbplatser kan samexistera i en enda klientorganisation. I följande exempelillustration visas tre olika varumärkta webbplatser (Adventure Works, Adventure Works Business och Fabrikam), som var och en mappas till olika onlinekanaler.

![Webbplatslista i webbplatsbyggaren.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Konfigurera ett enda domännamn med sökvägar för flera webbplatser

Ett enskilt domännamn kan användas för flera webbplatser, och sökvägar kan sedan användas för separata webbplatser eller språk. `www.mycompany.com`-domänen konfigureras till exempel för två olika näthandelsplatser: en för Fabrikam och en för Adventure Works. I det här fallet kan standardsökvägen (`www.mycompany.com`), även kallad den tomma sökvägen, användas för Fabrikam-webbplatsen och en annan sökväg (`www.mycompany.com/adventureworks` till exempel) kan användas för Adventure Works-webbplatsen. Ett annat alternativ är att använda en anpassad sökväg (till exempel `www.mycompany.com/fabrikam`) i stället för standardsökvägen för Fabrikams webbplats också.

Alternativt kan olika domännamn användas för varje webbplats (till exempel `www.adventure-works.com` och `www.fabrikam.com`). Sökvägar kan sedan användas för olika språk och regioner (till exempel `www.adventure-works.com/fr-ca` för kanadensisk franska).

## <a name="configure-multiple-languages-on-a-site"></a>Konfigurera flera språk på en webbplats

Språk kan konfigureras för näthandelsplatsen i webbplatsbyggaren på **Webbplatsinställningar \> Kanaler**. I följande exempel visas en bild där varje språk har konfigurerats genom att använda de nationella inställningarna för sökvägen, så att varje språk har en unik URL.

![Flera språk konfigurerade på en webbplats.](media/channel-mapping-10.png)

Om du vill lägga till ett nytt kanalspråk går du till **Webbplatsinställningar \> Kanaler** och väljer kanallänken. I fönstret som visas till höger väljer du **Lägg till en språkvariant** för att välja kanalen och språkvarianten som du vill lägga till. Ange sedan sökvägen för den valda kanalen.

### <a name="add-and-configure-the-site-picker-module"></a>Lägga till och konfigurera webbplatsväljarmodulen

När du har konfigurerat en webbplats med flera språk eller kanaler kanske du vill lägga till en språkväljare i sidhuvudet på webbplatsen, så att användarna manuellt kan välja språk och land. [Huvudmodulen](author-header-module.md) i modulbiblioteket har inbyggt stöd så att användare kan välja språk genom att använda [webbplatsväljarmodulen](site-selector.md). Webbplatsväljarmodulen kan läggas till i huvudmodulen i huvudfragmentet.

Mer information om att lägga till och konfigurera webbplatsväljarmodulen finns i [Webbplatsväljarmodul](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implementera sidvarianter för varje språk

I det här scenariot finns det bara en kanal, men det finns flera språk. Du kan ändra utseendet på en sida utifrån det valda språket genom att skapa en sidvariant för den. Du kan sedan lägga till lokalanpassat innehåll till varianten.

När en sida är öppen i webbplatsbyggaren och du väljer länken uppe till höger som visar aktuell kanal och språk, visas en kanal- och språkväljare, så som visas i följande exempelillustration. Om du vill åsidosätta sidan för det aktuella språket väljer du en annan språkvariant och väljer sedan **Ändra**. Du kan även ändra kanalen om du [hanterar en webbplats med flera kanaler och språk](#manage-site-content-that has-multiple-channels-and-languages).

![Ändra språket för en sida i webbplatsbyggaren.](media/channel-mapping-14.png)

Om varianten för den valda sidan eller fragmentet ännu inte har skapats visas ett varningsmeddelande, som visas i följande exempelillustration. I detta fall väljer du länken **Skapa variant av sida** i meddelandetexten. I dialogrutan som visas finns alternativ där du antingen kan börja med en kopia av en befintlig variant eller skapa en helt ny sida från en mall.

![Prompt för att skapa en sidvariant i webbplatsbyggaren](media/channel-mapping-16.png)

Om du inte skapar någon variant återges originalsidan och visar korrekt språk för modulsträngar och produktinformation från Commerce headquarters. Om text som en sidrubrik eller annat marknadsföringsinnehåll har angetts direkt i standardsidmoduler, kvarstår strängarna för denna text på originalspråket.

I stället för att skapa varje sida och fragment manuellt kan du exportera varje sida och fragment till en XLIFF-fil (XML Localization Interchange File Format) som sedan kan skickas för lokalisering. När varje XLIFF har lokalanpassats kan den importeras som en lokalanpassad sidvariant. Om du vill exportera en XLIFF-fil från en sida eller ett fragment i webbplatsbyggaren, eller om du vill importera en XLIFF-fil till en sida eller ett fragment, väljer du **Lokalisering** i kommandofältet. Välj sedan **Exportera XLIFF** eller **Importera XLIFF**, enligt bilden i följande exempel.

![Importera eller exportera en sida eller ett fragment i XLIFF-format.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Hantera webbplatsinnehåll som har flera kanaler och språk

En webbplats med flera kanaler och/eller språk lagrar en unik variant av varje sida och fragment för varje kombination av kanal och språk. Detta gör att sidvarianterna kan innehålla lokalanpassade data, men du får också flexibiliteten att ändra utseendet för en sida för en specifik variant.

Information om hur du arbetar med sidvarianter finns i avsnittet [Implementera sidvarianter för varje språk](#implement-page-variants-for-each-language) i denna artikel.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Konfigurera flera kanaler på en näthandelsplats

Du kan lägga till kanaler på en näthandelsplats i webbplatsbyggaren genom att gå till **Webbplatsinställningar \> Kanaler** och välja **Lägg till en kanal**. I dialogrutan **Lägg till en kanal** som visas kan du sedan välja onlinekanal och standardspråkvariant.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Ställa in en onlinekanal](channel-setup-online.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Konfigurera geografisk identifiering och omdirigering](geo-detection-redirection.md)

[Aktivera och använda delning av flera kanaler](cross-channel-sharing.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Kopiera en näthandelsplats](copy-ecommerce-site.md)

[Webbplatsväljarmodul](site-selector.md)
