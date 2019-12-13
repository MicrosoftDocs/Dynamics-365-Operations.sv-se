---
title: Modul för inköpsruta
description: Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811151"
---
# <a name="buy-box-module"></a>Modul för inköpsruta

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Termen *inköpsruta* syftar vanligtvis på en sida med produktinformation som är "ovanför vikningen" och som är värd för all den viktigaste information som krävs för att göra produktinköp. (Ett område som är "ovanför vikningen" visas när sidan läses in för första gången, så att användarna inte behöver rulla nedåt för att kunna se dem.)

En inköpsruta är en speciell behållare som används för att vara värd för alla moduler som visas i området för inköpsruta på en produktinformationssida.

URL för produktinformationssidan innehåller produkt-ID. All information som krävs för att återge en modul för inköpsruta kommer från detta produkt-ID. Om inget produkt-ID har angetts, återges inte affärsmodulen korrekt på en sida. Därför kan en modul för inköpsruta inte användas på någon sida som inte har någon produktkontext (t.ex. en startsida eller en marknadsföringssida).

## <a name="buy-box-module-properties-and-slots"></a>Egenskaper och platser för modul för inköpsruta 

Som en behållare styr en modul för inköpsruta grundläggande egenskaper, t.ex. bredden. Inställningen för bredd bestämmer om modulerna i behållaren måste passa i behållaren, eller om de kan fyllas på skärmen.

På en produktinformationssida är en inköpsruta uppdelad i två områden: ett medieområde till vänster och ett innehållsområde till höger. Dessa två regioner representeras av platser i modul för inköpsruta. Varje plats är förkonfigurerad så att endast vissa moduler som stöds av platsen accepteras. Till exempel en platsen **Media** stöder till exempel bara modulen mediegalleri.

Som standard är förhållandet mellan kolumnbredderna för medieområdet och innehållsområdet 2:1. Kolumnernas bredd kan dock åsidosättas av temat. På mobila enheter staplas dessutom de två regionerna så att en region visas under den andra regionen.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduler kan användas i modul för inköpsruta

- **Mediegalleri** – den här modulen används för att visa bilder av en produkt på en produktinformationssida. Det kan stödja en till många bilder. Den stöder också miniatyrbilder. Miniatyrbilderna kan antingen ordnas vågrätt (som en rad under bilden) eller lodrätt (som en kolumn bredvid bilden). Modulen mediegalleri kan läggas till i platsen **media** i modulen inköpsruta. Den stöder för närvarande endast bilder och videor.
- **Produkttitel** – i den här modulen visas titeln på produkten på produktinformationssidan. Som standard används rubriktaggen **H1** men rubriktaggen kan ändras efter behov.
- **Produktklassificeringar** – i den här modulen visas stjärnklassificeringar, baserat på kundvärderingar för en produkt. Modulen för inköpsruta hämtar produktklassificeringen för varje produkt från klassificeringstjänsten.
- **Produktpris** – i den här modulen visas produktpriset. Priset inkluderar genomstrukna pris och rabatter.
- **Produktbeskrivning** – i den här modulen visas beskrivningen för produkten.
- **Produktkonfiguration** – i den här modulen visas produktens storlek, stil och dimensioner. Dimensionsväljare kan staplas lodrätt, eller så att de visas sida vid sida. När en produktvarianten väljs uppdateras andra egenskaper i inköpsrutan (t.ex. produktbeskrivning och bilder) för att avspegla informationen för varianten.
- **Produktkvantitet** – den här modulen används för att konfigurera kvantiteten för produkten. En inställning begränsar kvantiteten av en produkt eller variant som kan läggas till i vagnen.
- **Lägg till i kundvagn** – den här modulen används för att utföra åtgärden "Lägg till i vagnen". Endast en produkt eller en variant kan läggas till i vagnen. Med andra ord kan en huvudprodukt inte läggas till i vagnen. Modulen har egenskapen **gå till vagnen** som kan ställas in för webbplatsförfattaren. När den här egenskapen har angetts till **Sant**tas användaren till vagnsidan varje gång en "Lägg till i vagnen" utlöses. När den har ställts in på **Falsk** kan kunden fortsätta att bläddra på sidan med produktinformation efter att artiklar har lagts till i vagnen.
- **Lägg till i lista** – den här modulen används för att lägga till en artikel i kundens önskelista. Endast en produkt eller en variant kan läggas till en önskelista. Dessutom måste kunden vara inloggad på webbplatsen. Modulen innehåller felhanteringslogik för att säkerställa att båda dessa villkor uppfylls.
- **Hitta i butik** – i den här modulen utlöses flödet "Köp online, hämta i butik".
- **Hämta i butik** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Som standard visar den här modulen butiker som ligger inom en 50 mils radie från kundens plats. Däremot kan sökradien anpassas i modulen. För varje butik görs en inventering om funktionen för inventering är aktiverad och ett lämpligt meddelande om i lager eller slut på lager.
- **Butikssökning av Bing Maps** – Denna modul kan användas inuti modul för hämtning i butik. Den gör att kunderna kan söka efter butiker genom att ange en plats. Bing Maps-API (Application Programming Interface) används för att konvertera den angivna platsen till en latitud och en longitud. Om modulen används visas endast butiker som är nära kundens aktuella plats och kunden kan inte söka efter en annan plats.
- **Innehållsrikt block** – i den här modulen kan det visas ett meddelande om att webbplatsförfattaren eller återförsäljaren vill befordra i inköpsrutan, t.ex. för ärenden med order, kontakta 1-800-FABRIKAM "eller" gratis leverans på order över 100 $." Meddelandena styrs av innehållshanteringssystem (CMS).

## <a name="buy-box-module-settings"></a>Inställningar för modul för inköpsruta

Modul för inköpsruta har tre inställningar som kan konfigureras:

- **Maximal kvantitet** – det högsta antalet artiklar som kan läggas till i kundvagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager. Den här inventeringen görs både för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken. Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras.
- **Lagerkvantitet** – lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering. Därför kan en buffert definieras för lagret. När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret. När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.

## <a name="retail-server-interaction"></a>Butiksserverinteraktion

Modul för inköpsruta hämtar produktinformation med hjälp av API:er för butiksservrar. Produkt-ID:t från sidan produktinformation används för att hämta all information.

## <a name="add-a-buy-box-module-to-a-page"></a>Lägg till en modul för inköpsruta på en ny sida

Om du vill lägga till en modul för inköpsruta på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa ett fragment med namnet **inköpsrutafragment**och lägg till en modul för inköpsruta.
1. Platsen **Media** för modul för inköpsruta, lägg till en mediagallerimodul.
1. På platsen **Innehåll** i modul för inköpsruta, lägg till följande moduler: produkttitel, produktklassificering, produktpris, produktbeskrivning, produktkonfiguration, lägg till i vagn, lägg till i önskelistan och hitta i butik. Du kan ordna om modulerna på platsen **innehåll** för att uppnå önskad layout.
1. Välj modulen hitta i butik. På platsen inne i modulen lägger du till en modul för hämtning i butik.
1. På platsen inne i modulen lägger du till en modul för hämtning i butik, lägg till butikssökning i modulen Bing Maps.
1. Checka in sidan och publicera den.
1. Skapa en mall för en produktinformationssida och ge den namnet **PDP-mall**.
1. Lägg till en standardsida.
1. Lägg till platsen **Huvud** på standardsida, lägg till ett inköpsrutafragment.
1. Spara mallen, checka in den och publicera den.
1. Använd den mall som du just skapade för att skapa en sida med namnet **PDP-sida**.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till ett inköpsrutafragment.
1. Spara och förhandsgranska sidan. Lägg till frågesträngparametern **?productid=&lt;product id&gt;** till URL för förhandsgranskningssidan. På så sätt används produktkontexten för att läsa in och återge förhandsgranskningssidan.
1. Checka in sidan och publicera den. En inköpsruta bör visas på sidan för produktinformation.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
