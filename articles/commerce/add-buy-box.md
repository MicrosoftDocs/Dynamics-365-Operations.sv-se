---
title: Modul för inköpsruta
description: Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 35b7027e0f0b680dd82ebfcea754fef1617c0163
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261408"
---
# <a name="buy-box-module"></a>Modul för inköpsruta


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Termen *inköpsruta* syftar vanligtvis på en sida med produktinformation som är "ovanför vikningen" och som är värd för all den viktigaste information som krävs för att göra produktinköp. (Ett område som är "ovanför vikningen" visas när sidan läses in för första gången, så att användarna inte behöver rulla nedåt för att kunna se dem.)

En inköpsruta är en speciell behållare som används för att vara värd för alla moduler som visas i området för inköpsruta på en produktinformationssida.

URL för produktinformationssidan innehåller produkt-ID. All information som krävs för att återge en modul för inköpsruta kommer från detta produkt-ID. Om inget produkt-ID har angetts, återges inte affärsmodulen korrekt på en sida. Därför kan en modul för inköpsruta bara användas på sidor som har produktkontext. Om du vill använda den på en sida som saknar produktkontext (t.ex. en start sida eller en marknadsföringssida), måste du utföra ytterligare anpassningar.

## <a name="buy-box-module-properties-and-slots"></a>Egenskaper och platser för modul för inköpsruta 

På en produktinformationssida är en inköpsruta uppdelad i två områden: ett medieområde till vänster och ett innehållsområde till höger. Som standard är förhållandet mellan bredden för kolumnen medie region och bredden för kolumnen innehålls region 2:1. På mobila enheter staplas de två regionerna så att en region visas under den andra regionen. Teman kan användas för att anpassa kolumnbredder och stackrangordning.

En modul för inköpsruta återger titel, beskrivning, pris och klassificering för en produkt. Kunden kan också välja produktvarianter med olika produktattribut, t.ex. storlek, stil och färg. När en produktvarianten väljs uppdateras andra egenskaper i inköpsrutan (t.ex. produktbeskrivning och bilder) för att avspegla informationen för varianten. 

En mängd väljare tillhandahålls, så att kunder kan ange hur många artiklar som ska köpas. Den högsta kvantiteten som kan köpas kan definieras i webbplatsinställningarna.

Från inköpsrutan kan kunder också utföra åtgärder som att lägga till en produkt i kundvagnen, lägga till en produkt i deras önskelista och välja en plockplats. Dessa åtgärder kan utföras på en produkt eller produktvariant. Om du vill lägga till en produkt i en önskelista måste kunden vara inloggad.

Teman kan användas för att ta bort eller ändra ordningen på produktegenskaper och åtgärdskontroller i inköpsrutan. 

## <a name="module-properties"></a>Modulegenskaper

- **Rubriketikett** – den här egenskapen definierar rubriketiketten för produktrubriken. Om inköpsrutan finns högst upp på sidan ska den här egenskapen ställas in på **h1** för att uppfylla tillgänglighetsstandarder. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduler kan användas i modul för inköpsruta

- **Mediegalleri** – den här modulen används för att visa bilder av en produkt på en produktinformationssida. Det kan stödja en till många bilder. Den stöder också miniatyrbilder. Miniatyrbilderna kan antingen ordnas vågrätt (som en rad under bilden) eller lodrätt (som en kolumn bredvid bilden). Modulen mediegalleri kan läggas till i platsen **media** i modulen inköpsruta. Den stöder för närvarande endast bilder. 
- **Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Användare kan ange en plats för att hitta butiker som finns i närheten. Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).

## <a name="buy-box-module-settings"></a>Inställningar för modul för inköpsruta

Modul för inköpsruta har tre inställningar som kan konfigureras på **Platsinställningar \> Tillägg**:

- **Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager. Den här inventeringen görs för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken. Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras. Information om hur du konfigurerar lagerinställningar i backoffice finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).

- **Lagerkvantitet** – den här egenskapen används för att ange ett buffertnummer för lager. Lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering. När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret. När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Modul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel. Produkt-ID:t från sidan produktinformation används för att hämta all information.

## <a name="add-a-buy-box-module-to-a-page"></a>Lägg till en modul för inköpsruta på en ny sida

Om du vill lägga till en modul för inköpsruta på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa ett fragment med namnet **inköpsrutafragment**och lägg till en modul för inköpsruta.
1. Platsen **Media** för modul för inköpsruta, lägg till en mediagallerimodul.
1. I facket **Butiksväljare** i modul för inköpsruta, lägg till en modul för butiksväljare.
1. Checka in sidan och publicera den.
1. Skapa en mall för en produktinformationssida och ge den namnet **PDP-mall**.
1. Lägg till en standardsida.
1. Lägg till platsen **Huvud** på standardsida, lägg till ett inköpsrutafragment.
1. Spara mallen, slutför redigeringen och publicera den.
1. Använd den mall som du just skapade för att skapa en sida med namnet **PDP-sida**.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till ett inköpsrutafragment.
1. Spara och förhandsgranska sidan. Lägg till frågesträngparametern **?productid=&lt;product id&gt;** till URL för förhandsgranskningssidan. På så sätt används produktkontexten för att läsa in och återge förhandsgranskningssidan.
1. Spara sidan, slutför redigeringen och publicera det. En inköpsruta bör visas på sidan för produktinformation.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul för butiksväljare](store-selector.md)

[Behållarmodul](add-container-module.md)

[Kundvagnsmodul](add-cart-module.md)

[Vagnikonmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)
