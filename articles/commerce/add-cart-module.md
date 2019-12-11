---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696771"
---
# <a name="cart-module"></a>Kundvagnsmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En kundvagnsmodul är en behållare som används för att vara värd för alla moduler som krävs för att visa upp artiklar i vagnen. Den innehåller till exempel alla artiklar som har lagts till i vagnen, ordersammanfattningen och kampanjkoderna.

Kundvagnsmodulen återger data baserat på kundvagn-ID. Kundvagn-ID är en webbläsarcookie som finns tillgänglig på hela webbplatsen.

## <a name="cart-module-properties-and-slots"></a>Egenskaper och platser för kundvagnsmodul

Som en behållare styr en kundvagnsmodul grundläggande egenskaper, t.ex. rubriken och bredden. Rubriken är normalt text, t.ex. **Shoppingväska**, **Din kundvagn** eller **Artiklarna i vagnen**. Inställningen för bredd bestämmer om modulerna i behållaren måste passa i behållaren, eller om de kan fyllas på skärmen.

Kundvagnssidan delas upp i flera regioner: artiklar i vagnen, ordersammanfattning och kassa och "Sök i butik"-funktionen. Varje region mappas till en plats i kundvagnsmodulen, och varje plats accepterar en fördefinierad uppsättning moduler.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduler kan användas i en kundvagnsmodul

- **Vagnradartiklar** – i den här modulen visas en översikt över alla artiklar som har lagts till i vagnen. Informationen inkluderar produkttitel, valda dimensioner, pris, kvantitet och rabatter. Den här modulen stöder också åtgärder som "ta bort från kundvagn" och "Lägg till i listan". För varje radartikel finns det ett alternativ för att leverera artikeln eller plocka den från butiken. Det här alternativet måste konfigureras separat i modul för hämtning i butik.
- **Ordersammanfattning** – i den här modulen visas en ordersammanfattning. Informationen omfattar delsumma, frakt, moms och besparingar. En rubrik kan konfigureras för den här modulen.
- **Kampanjkod** – i den här modulen kan kunder lösa in kampanjkoder. En kampanjkod kan användas eller tas bort.
- **Utcheckning** – den här modulen initierar utcheckningen och dirigerar om användaren till kassasidan. Tre länkar måste konfigureras för den här modulen:

    - **Utcheckning** – den här länken tvingar kunder att logga in om de inte redan är inloggade.
    - **Gästutcheckning** – med den här länken kan anonyma kunder göra beställningar. Den visas bara när kunder inte är inloggade.
    - **Tillbaka till shopping** – med den här länken kan kunderna gå till startsidan eller någon annan sida, så att de kan fortsätta handla.

- **Innehållsrikt block** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen. Meddelandena styrs av innehållshanteringssystem (CMS). Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."
- **Hämta i butik** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Som standard visar den här modulen butiker som ligger inom en 50 mils radie från kundens plats. Däremot kan sökradien anpassas i modulen. För varje butik görs en inventering om funktionen för inventering är aktiverad och ett lämpligt meddelande om i lager eller slut på lager.
- **Butikssökning av Bing Maps** – Denna modul kan användas inuti modul för hämtning i butik. Den gör att kunderna kan söka efter butiker genom att ange en plats. Bing Maps-API (Application Programming Interface) används för att konvertera den platsen som kunden har angett till en latitud och en longitud. Om modulen inte används visas endast butiker som är nära kundens aktuella plats och kunden kan inte söka efter en annan plats.

## <a name="cart-module-settings"></a>Inställningar för kundvagnsmodul

Kundvagnsmoduler har tre inställningar som kan konfigureras:

- **Maximal kvantitet** – det högsta antalet artiklar som kan läggas till i kundvagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager. Den här inventeringen görs både för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken. Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras.
- **Lagerkvantitet** – lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering. Därför kan en buffert definieras för lagret. När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret. När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.

## <a name="retail-server-interaction"></a>Butiksserverinteraktion

Kundvagnsmodulen hämtar produktinformation med hjälp av API:er för butiksservrar. Vagn-ID från webbläsarcookien används för att hämta all produktinformation från butiksservern.

## <a name="add-a-cart-module-to-a-page"></a>Lägg till en kundvagnsmodul på en ny sida

Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa ett fragment med namnet **vagnfragment**och lägg till en kundvagnsmodul.
1. På platsen **kundvagnsartiklar** i kundvagnsmodulen, lägg till artiklar för kundvagnsmodulen.
1. På platsen **Ordersammanfattning**, lägg till ordersammanfattningsmodul.
1. På platsen **kampanjkod** lägger du till modulen för kampanjkod.
1. På platsen **Kassa**, lägg till en kassamodul.
1. På platsen **Hitta i butik**, lägg till en hämtning i en butiksmodul.
1. I modulen hämta i butik, välj platsen **Butikssökning** lägg till butikssökning i modulen Bing Maps.
1. Checka in fragmentet och publicera det.
1. Skapa en mall med namnet **vagnmall** och lägg till det vagnfragment som du precis skapade i den.
1. Spara mallen, checka in den och publicera den.
1. Skapa en sida som använder den nya mallen.
1. Spara och förhandsgranska sidan.
1. Checka in sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
