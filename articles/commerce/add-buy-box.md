---
title: Modul för inköpsruta
description: Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 6556ee8acf1e24a9f6ceddb622960cb3ac891852
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761307"
---
# <a name="buy-box-module"></a>Modul för inköpsruta

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet handlar om moduler för inköpsruta och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Termen *inköpsruta* syftar vanligtvis på en sida med produktinformation som är "ovanför vikningen" och som är värd för all den viktigaste information som krävs för att göra produktinköp. (Ett område som är "ovanför vikningen" visas när sidan läses in för första gången, så att användarna inte behöver rulla nedåt för att kunna se dem.)

En inköpsruta är en speciell behållare som används för att vara värd för alla moduler som visas i området för inköpsruta på en produktinformationssida.

URL för produktinformationssidan innehåller produkt-ID. All information som krävs för att återge en modul för inköpsruta kommer från detta produkt-ID. Om inget produkt-ID har angetts, återges inte affärsmodulen korrekt på en sida. Därför kan en modul för inköpsruta bara användas på sidor som har produktkontext. Om du vill använda den på en sida som saknar produktkontext (t.ex. en start sida eller en marknadsföringssida), måste du utföra ytterligare anpassningar.

Följande bild visar ett exempel på en modul för inköpsruta på en produktinformationssida.

![Exempel på en modul för inköpsruta](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Egenskaper och platser för modul för inköpsruta 

På en produktinformationssida är en inköpsruta uppdelad i två områden: ett medieområde till vänster och ett innehållsområde till höger. Som standard är förhållandet mellan bredden för kolumnen medie region och bredden för kolumnen innehålls region 2:1. På mobila enheter staplas de två regionerna så att en region visas under den andra regionen. Teman kan användas för att anpassa kolumnbredder och stackrangordning.

En modul för inköpsruta återger titel, beskrivning, pris och klassificering för en produkt. Kunden kan också välja produktvarianter med olika produktattribut, t.ex. storlek, stil och färg. När en produktvarianten väljs uppdateras andra egenskaper i inköpsrutan (t.ex. produktbeskrivning och bilder) för att avspegla informationen för varianten. 

En mängd väljare tillhandahålls, så att kunder kan ange hur många artiklar som ska köpas. Den högsta kvantiteten som kan köpas kan definieras i webbplatsinställningarna.

Från inköpsrutan kan kunder också utföra åtgärder som att lägga till en produkt i kundvagnen, lägga till en produkt i deras önskelista och välja en plockplats. Dessa åtgärder kan utföras på en produkt eller produktvariant. Om du vill lägga till en produkt i en önskelista måste kunden vara inloggad.

Teman kan användas för att ta bort eller ändra ordningen på produktegenskaper och åtgärdskontroller i inköpsrutan. 

## <a name="module-properties"></a>Modulegenskaper

- **Rubriketikett** – den här egenskapen definierar rubriketiketten för produktrubriken. Om inköpsrutan finns högst upp på sidan ska den här egenskapen ställas in på **h1** för att uppfylla tillgänglighetsstandarder. 

- **Aktivera rekommendationer för "Köp liknande utseende"** – med den här egenskapen kan köprutan för att visa länkar till produkter som liknar det objekt som för närvarande visas. Den här funktionen är tillgänglig i Commerce version 10.0.13 och senare.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduler kan användas i modul för inköpsruta

- **Mediegalleri** – den här modulen används för att visa bilder av en produkt på en produktinformationssida. Mer information om den här modulen finns i [Modul för mediegalleri](media-gallery-module.md).
- **Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Användare kan ange en plats för att hitta butiker som finns i närheten. Mer information om den här modulen finns i [Modul för butiksväljare](store-selector.md).
- **Social delning** – denna modul kan läggas till i köprutan köp så att användarna kan dela produktinformation på sociala medier. Mer information finns i avsnittet [modulen social delning](social-share-module.md).

## <a name="buy-box-module-settings"></a>Inställningar för modul för inköpsruta

Följande köpboxmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:

- **Kvantitetsbegränsning för kundvagn** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).
- **Lägg till i kundvagn** - den här egenskapen används för att ange funktionen när en artikel har lagts till i vagnen. De möjliga värdena är **Navigera till kundvagn**, **Navigera inte i kundvagn** och **Visa meddelanden**. När värdet är inställt på **Navigera till kundvagn** skickas användarna till kundvagnssidan när de har lagt till en artikel. När värdet är inställt på **Navigera inte till kundvagn** skickas användarna inte till kundvagnssidan när de har lagt till en artikel. När värdet är inställt på **Visa meddelanden** visas användarna ett bekräftelsemeddelande och du kan fortsätta att bläddra på sidan produktinformation. 

    I följande bild visas ett exempel på ett bekräftelsemeddelande om tillägg till kundvagnen på Fabrikam webbplats.

    ![Exempel på en meddelandemodul](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Modul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för Commerce Scale Unit. Produkt-ID:t från sidan produktinformation används för att hämta all information.

## <a name="add-a-buy-box-module-to-a-page"></a>Lägg till en modul för inköpsruta på en ny sida

Om du vill lägga till en modul för inköpsruta på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Nytt fragment**, välj modulen **inköpsruta**.
1. Under **Fragmentets namn**, anger du ett namn på **inköpsrutafragmentet** och klickar sedan på **OK**.
1. I platsen för modul för inköpsruta väljer du **Mediagalleriet**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** välj modulen **Mediagalleriet** och sedan **OK**.
1. I platsen för modul för inköpsruta väljer du **butiksväljare**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.
1. Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **PDP-mall** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Välj fragment** väljer du det **inköpsrutafragment** som du skapade tidigare och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en **PDP-mall**. Under **sidnamn**, ange **PDP-sida** och klicka sedan på **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Välj fragment** väljer du det **inköpsrutafragment** som du skapade tidigare och väljer sedan **OK**.
1. Spara och förhandsgranska sidan. Lägg till frågesträngparametern **?productid=&lt;product id&gt;** till URL för förhandsgranskningssidan. På så sätt används produktkontexten för att läsa in och återge förhandsgranskningssidan.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. En inköpsruta bör visas på sidan för produktinformation.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul för butiksväljare](store-selector.md)

[Modul för mediegalleri](media-gallery-module.md)

[Behållarmodul](add-container-module.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)

[Modul för social delning](social-share-module.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)
