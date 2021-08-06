---
title: Modul för butiksväljare
description: Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: b054101d6d177018e54162537cfd756c84b11ae3
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638890"
---
# <a name="store-selector-module"></a>Modul för butiksväljare

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

Kunder kan använda modulen butiksväljare för att hämta en produkt i en vald butik efter ett onlineinköp. I Commerce version 10.0.13 inkluderar modulen butiksväljare ytterligare funktioner som kan visa sidan **Visa en butik** som visar närliggande butiker.

Med modulen butiksväljare kan användarna ange en plats (ort, delstat, adress och så vidare) för att söka efter butiker inom en sökradie. När modulen öppnas använder den kundens webbläsare och söker efter butiker (om medgivande finns).

## <a name="store-selector-module-usage"></a>Användning av modul för butiksväljare

- En modul för butiksväljare kan användas på en produktinformationssida (PDP) för att välja en butik för upphämtning.
- En modul för butiksväljare kan användas på en kundvagnssida för att välja en butik för upphämtning.
- En modul för butiksväljare kan användas på en fristående sida där alla tillgängliga butiker visas.

## <a name="fulfillment-group-setup-in-commerce-headquarters"></a>Konfigurera uppfyllelsegrupper i Commerce-administrationen

För att butiksväljaren ska visa tillgängliga butiker måste uppfyllelsegruppen ha ställts in i Commerce-administrationen. För mer information, se [Konfigurera uppfyllelsegrupper](customer-orders-overview.md#set-up-fulfillment-groups).

Dessutom måste, för varje butik i uppfyllelsegruppen, butiksplatsens latitud och longitud definieras i administrationen.

Följ dessa steg för att ange värden för latitud och longitud för en butiksplats i Commerce-administrationen.

1. Gå till **Lagerhantering \> Inställningar \> Lageruppdelning**.
1. Välj lagrets plats i vänster ruta.
1. På snabbfliken **Adresser** väljer du **Avancerat**.

    ![Exempel på butiksinformation i administrationen.](./media/Store-address.png)

1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Allmänt** anger du värden för **Latitud** och **Longitud**.

    ![Exempel på konfiguration av latitud och longitud i administrationen.](./media/Store-latitude-longitude.png)

1. Klicka på **Spara** i åtgärdsfönstret. 

## <a name="bing-maps-integration"></a>Bing Maps-integrering

Modulen butiks väljare är integrerad med [Bing Maps REST-API:er (Application Programming Interfaces)](/bingmaps/rest-services/) för att använda funktionerna Bing geokodning och automatiska förslag. En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-administration. Geokodnings-API används för att konvertera en plats till latitud- och longitudvärden. Integrationen med API för automatiska förslag används för att visa sökförslag när användare anger platser i sökfältet.

För REST API för automatiska förslag måste du se till att följande URL:er tillåts per din webbplats säkerhetsprinciper för innehåll (CSP). Den här inställningen görs i Commerce webbplatsskapare genom att lägga till tillåtna URL:er för webbplatsens CSP-direktiv (till exempel **img-src**). Mer information finns i [säkerhetsprinciper för innehåll](manage-csp.md). 

- Till direktivet **connect-src** lägger du till **&#42;.bing.com**.
- Till direktivet **img-src** lägger du till **&#42;.virtualearth.net**.
- Till direktivet **script-src** **lägg till &#42;.bing.com, &#42;.virtualearth.net**.
- Till direktivet **script style-src** lägger du till **&#42;.bing.com**.

## <a name="pickup-in-store-mode"></a>upphämta i butiksläge

Modulen för butiksväljare stöder läget **Hämta i butik** som visar en lista över butiker där en produkt är tillgänglig för hämtning. Den visar även butikstider och produktlager för varje butik i listan. Modulen butiksväljare kräver en produktskontext för att återge produkttillgänglighet och för att användaren ska kunna lägga till produkten i vagnen, om produktens leveranssätt är inställt på **hämta** vid den valda butiken. Mer information om [lagerinställning](inventory-settings.md). 

Modulen butiksväljare kan läggas till i en modul för inköpsruta på en PDP för att visa butiker där en produkt är tillgänglig för upphämtning. Den kan också läggas till i en vagnmodul. I det här fallet visar modulen butiksväljare upphämtningsalternativ för varje radartikel i vagnen. Modulen butiksväljare kan också läggas till andra sidor eller moduler via tillägg och anpassningar.

För att detta scenario ska fungera bör produkter konfigureras så att leveranssättet **hämta** används. Annars visas modulen inte på respektive produktsidor. Mer information om hur du konfigurerar leveranssättet finns i [ställa in leveransmetod](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Följande bild visar ett exempel på en modul för butiksväljare som används på ett PDP.

![Exempel på en modul för butiksväljare som används på PDP.](./media/BOPIS.PNG)

> [!NOTE]
> I version 10.0.16 och senare kan en ny funktion aktiveras, detta så att en organisation kan definiera flera olika hämtningslägen för kunder.  Om den här funktionen aktiveras kommer butiksväljaren och andra näthandelsmoduler att förbättras så att konsumenten eventuellt kan välja mellan olika leveransalternativ.  Mer information om den här funktionen finns i [den här dokumentationen](./multiple-pickup-modes.md). 

## <a name="find-stores-mode"></a>Sök efter butiksläge

Modulen butiksväljare stöder också ett läge för **sök butiker**. Detta läge kan användas för att skapa sidan butiksplatser där tillgängliga butiker och information visas. I det här läget fungerar modulen butiksväljare utan produktkontext och kan användas som en fristående modul på alla webbplatssidor. Om de relevanta inställningarna aktiveras för modulen kan användarna välja en butik som primär butik. När en butik väljs som en användares önskade butik, behålls butiks-ID:t i webbläsarcookien. Därför måste användaren acceptera ett meddelande om cookie-tillstånd.

I bilden nedan visas ett exempel på en modul i butiksväljaren som används tillsammans med en kartmodul på en butiksplatssida.

![Exempel på en modul för butiksväljare och en kartmodul på sidan för butiksplatser.](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Återge en karta

Modulen butiksväljare kan användas tillsammans med kartmodulen för att visa butiksplatserna på kartan. Mer information om den här kartmodulen finns i [Kartmodul](map-module.md)

## <a name="store-selector-module-properties"></a>Egenskaper för modul för butiksväljare

| Egenskapsnamn | Värde | beskrivning |
|---------------|-------|-------------|
| Rubrik | Text | Rubriken för modulen. |
| Läge | **Sök efter butiker** eller **Hämta i butik** | **Sök butiker**-läget visar tillgängliga butiker. **Hämta i butik**-läge låter användarna välja en butik för upphämtning. |
| Format | **Dialog** eller **infogad** | Modulen kan återges i antingen infogade eller i en dialogruta. |
| Ange som önskad butik | **Sant** eller **falskt** | När den här egenskapen har angetts till **True** kan användare ange en prioriterad butik. Den här funktionen kräver att användarna accepterar ett meddelande om cookie-tillstånd. |
| Visa alla butiker | **Sant** eller **falskt** | När den här egenskapen har angetts till **True** kan användare förbigå egenskapen **sökradie** och visa alla butiker. |
| Alternativ för automatiska förslag: Max resultat | Antal | Den här egenskapen anger det högsta antalet resultat för automatiska förslag som kan visas via Bing automatiska förslag-API. |
| Sök radie | Antal | Den här egenskapen definierar sökradien för butiker, i mil. Om inget värde anges används standardsökradien 50 mil. |
| Användarvillkor | URL |  Den här egenskapen anger den användarvillkor-URL som krävs för att använda Bing Maps-tjänsten. |

## <a name="site-settings"></a>Platsinställningar

Butiksväljarmodulen följer [inställningarna för Lägg till produkt i kundvagnen](add-cart-settings.md). När en artikel har lagts till i kundvagnen från butiksväljarmodulen ser webbplatsanvändarna lämpliga konfigurerade arbetsflöden.

## <a name="add-a-store-selector-module-to-a-page"></a>Lägg till modulen för butiksväljare till en sida

För **upphämtning i butik**-läge kan modulen bara användas på PDP och kundvagnssidor. Du måste ställa in läget för **upphämtning i butik** i modulens egenskapsfönster.

- Mer information om hur du lägger till en modulen för butiksväljare i en modul för inköpsruta finns i [modul för inköpsruta](add-buy-box.md). 
- Mer information om hur du lägger till en modulen för butiksväljare i en vagnmodul i [vagnmodul](add-cart-module.md)

Om du vill konfigurera modulen för butiksväljaren att visa tillgängliga butiker för en sida för lagringsplatser, som i bilden som visas tidigare i det här avsnittet följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **Marknadsföringsmall** och välj sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en **Marknadsföringsmall**. Under **sidnamn**, ange **Butiksplatser** och klicka sedan på **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare med 2 kolumner** och klicka sedan på **OK**.
1. I modulens egenskapsfönster, ange värdet **Bredd** till **Fyll behållare**.
1. Ställ in värdet för **X-Small visningsport kolumnkonfiguration** till **100%**.
1. Ställ in värdet för **Small visningsport kolumnkonfiguration** till **100%**.
1. Ställ in värdet för **Medium visningsport kolumnkonfiguration** till **33% 67%**.
1. Ställ in värdet för **Large visningsport kolumnkonfiguration** till **33% 67%**.
1. I facket **Behållare med 2 kolumner** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.
1. I modulens egenskapsfönster, ange värdet **Läge** till **Hitta butiker**.
1. Ange värdet **sökradie** i mil.
1. Ange andra egenskaper, t.ex. **Ange som prioriterad butik**, **Visa alla butiker** och **Aktivera automatiskt förslag** efter behov.
1. I facket **Behållare med 2 kolumner** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Karta** och klicka sedan på **OK**.
1. Ange eventuella ytterligare egenskaper efter behov i modulens egenskapsfönster.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
 
## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Guidad visning av PDP](quick-tour-pdp.md)

[Guidad visning av kundvagn och kassa](quick-tour-cart-checkout.md)

[Ställ in leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Hantera Bing-kartor för din organisation](dev-itpro/manage-bing-maps.md)

[Bing Maps REST API:er](/bingmaps/rest-services/)

[Kartmodul](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
