---
title: Kassamodul
description: I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cb32b014ac35e33db28d3dee03b01dfa43f5d6a5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980516"
---
# <a name="checkout-module"></a>Kassamodul

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.

## <a name="overview"></a>Översikt

En kassamodul är en särskild behållare som är värd för alla moduler som krävs för att skapa en order. Det visar ett steg-för-steg-flöde som en kund använder för att registrera all relevant information för att göra inköp. Den fångar in leveransadress, leveransmetod och faktureringsinformation. Den innehåller också en ordersammanfattning och annan information som är relaterad till en kundorder.

En kassamodul återger data baserat på kundvagn-ID. Detta kundvagn-ID sparas som en webbläsarcookie. Ett kundvagn-ID krävs för att återge information i kassamodulen, till exempel artiklarna i ordern, totalbeloppet och rabatter. 

Följande bild visar ett exempel på en Fabrikam kassamodul på en kassasida.

![Exempel på en kassamodul](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Egenskaper för kassamodul

En betalningsmodul visar en ordersammanfattning och innehåller funktioner för att placera en order. Om du vill samla in all kundinformation som krävs innan en order kan placeras, måste ytterligare moduler läggas till i modulen för kassa. Därför har detaljhandlare flexibilitet att lägga till anpassade moduler i kassaflödet eller att utesluta moduler utifrån deras krav.

| Egenskapsnamn | Värden | beskrivning |
|----------------|--------|-------------|
| Rubrik för kassa | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En rubrik för kassamodulen. |
| Rubrik för orderöversikt | Rubriktext | En rubrik för avsnittet för ordersammanfattning i modulen. |
| Rubrik på vagn radartiklar | Rubriktext | En rubrik för kundvagnsartiklar som visas i modulen för kassa. |
| Visa leveransavgifter på radartiklar | **Sant** eller **falskt** | Om den här egenskapen har värdet **True** de leveranskostnader som är tillämpliga för rader kommer att visas på kundvagnrader. Om funktionen **Huvudtillägg utan proportionell fördelning** aktiveras i Commerce-administration kommer fraktkostnaden tillämpas på rubriknivå, inte på radnivå. Den här funktionen har lagts till i Commerce version 10.0.13. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduler kan användas i kassamodulen

- **Leveransadress** – i den här modulen kan en kund lägga till eller välja leveransadressen för en order. Mer information om den här modulen finns i [Modul för leveransadress](ship-address-module.md).

    Följande bild visar ett exempel på en leveransadressmodul på en kassasida.

    ![Exempel på en leveransadressmodul](./media/ecommerce-shippingaddress.PNG)

- **Leveransalternativ** – i den här modulen kan en kund välja ett leveranssätt för en order. Mer information om den här modulen finns i [Modul för leveransalternativ](delivery-options-module.md).

    Följande bild visar ett exempel på en leveransalternativmodul på en kassasida.
 
    ![Exempel på en leveransalternativmodul](./media/ecommerce-deliveryoptions.PNG)

- **Behållare för kassaavsnitt** – den här modulen är en behållare som du kan placera flera moduler i för att skapa ett avsnitt i kassaflödet. Du kan till exempel placera alla betalningsrelaterade moduler i behållaren så att de visas som ett avsnitt. Den här modulen påverkar endast flödets layout.

- **Presentkort** – i den här modulen kan en kund betala för en order genom att använda ett presentkort. Mer information om den här modulen finns i [Modul för presentkort](add-giftcard.md).

- **Förmånspoäng** – i den här modulen kan en kund betala för en order genom att använda förmånspoäng. Den innehåller en sammanfattning av tillgängliga punkter och utgångspunkter, och låter kunden välja hur många poäng som ska lösas in. Om kunden inte är inloggad i eller inte är en förmånsmedlem, eller om det totala beloppet i vagnen är 0 (noll), döljs den här modulen automatiskt.

- **Betalning** – i den här modulen kan en kund betala för en order genom att använda ett kredit- eller debetkort. Kunder kan även ange en faktureringsadress för betalningsalternativet som de väljer. Mer information om den här modulen finns i [Betalningsmodul](payment-module.md).

    Följande bild visar ett exempel på moduler för presentkort, förmånspoäng och betalningsmoduler på en kassasida.

    ![Exempel på moduler för presentkort, förmånspoäng och betalningsmoduler på en kassasida](./media/ecommerce-payments.PNG)

- **Kontaktinformation** – i den här modulen kan en kund lägga till eller ändra kontaktinformation (e-postadress) för en order.

- **Textblock** – den här modulen innehåller alla meddelanden som styrs av innehållshanteringssystem (CMS). Det kan till exempel innehålla ett meddelande om att "problem med ordern, kontakta 1-800-Fabrikam." 

- **Betalningsvillkor** – i den här modulen visas RTF-format som innehåller villkoren och en kryssruta för kundens inmatning. Kryssrutan är valfri och konfigurerbar. Inmatningen samlas in av modulen och kan användas som en bockmarkering innan orderplacering aktiveras, men den inkluderas inte i order sammanfattningsinformationen. Den här modulen kan läggas till i kassabehållaren, behållare för kassaavsnitt eller villkorsplatsen, beroende på affärsbehov. Om den läggs till i kassabehållaren för platsen för kassan eller i behållarmodulen kassaavsnitt visas det som ett steg i kassaprocessen. Om det har lagts till i villkorsplatsen visas det nära knappen orderplacering.

    Följande bild visar ett exempel på villkor på en kassasida.

    ![Exempel på villkor på en kassasida](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Större delen av kassan, t.ex. leveransadress och leveransmetod, lagras i kundvagnen och bearbetas som en del av ordern. Det enda undantaget är kreditkortsinformationen. Den här informationen bearbetas direkt med hjälp av Adyen betalningsanslutning. Betalningen är auktoriserad men inte debiterad förrän ordern är uppfylld.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Lägg till en kassamodul på en sida och ställa in de obligatoriska egenskaperna.

Om du vill lägga till en kassamodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Nytt fragment**, välj modulen **Kassa**.
1. Under **fragmentets namn**, anger du ett namn på **kassafragmentet** och klickar sedan på **OK**.
1. Markera facket **Kassamodul**.
1. I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.
1. I facket **Kassainformation** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj **Leveransadress**, **Leveransalternativ**, **Behållare för kassaavsnitt** och **Kontaktinformation** Välj sedan **OK**.
1. I modulen **Behållare för kassaavsnitt** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulerna **Presentkort**, **Förmåner** och **Betalning** och välj sedan **OK**. På så sätt ser du till att alla betalsätt visas tillsammans i ett avsnitt.
1. På platsen för **Villkor** lägger du till en modul för **Betalningsvillkor** om det behövs. Konfigurera villkoren och villkorstexten enligt önskemål i modulens egenskapsfönster.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska fragmentet. Vissa moduler som inte har ett kundvagnssammanhang kanske inte återges i förhandsgranskningen.
1. Välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera det.
1. Skapa en mall som använder det nya kassafragmentet.
1. Skapa en kassasida som använder den nya mallen.

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)
