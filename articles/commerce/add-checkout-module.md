---
title: Kassamodul
description: I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697093"
---
# <a name="checkout-module"></a>Kassamodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.

## <a name="overview"></a>Översikt

En kassamodul är en särskild behållare som är värd för alla moduler som krävs för att skapa en order. En kassamodul kan innehålla moduler som hanterar leveransadress, leveransmetoder, faktureringsinformation, ordersammanfattning och annan information som hör till en kundorder. Det visar ett steg-för-steg-flöde som en kund använder för att registrera all relevant information för att göra inköp.

En kassamodul återger data baserat på kundvagn-ID. Detta kundvagn-ID sparas som en webbläsarcookie. Ett kundvagn-ID krävs för att återge information i kassamodulen, till exempel artiklarna i ordern, totalbeloppet och rabatter.

## <a name="checkout-module-properties"></a>Egenskaper för kassamodul

En kassamodul innehåller en uppsättning moduler inuti den. Med egenskapen bredd kan du ange om artiklarna i kassamodulen ska passa bredden på den eller fylla skärmen.

En kassamodul har flera platser, t.ex. platsen **Kassainformation**, platsen **Ordersammanfattning** och platsen **placera en order**. Varje plats stöder en uppsättning moduler som kommer att visas i en särskild layout på sidan. Till exempel innehåller platsen **kassainformation** alla moduler som krävs för att utlösa en utcheckning, t.ex. moduler för leveransadress och betalningsmetod. Platsen **Ordersammanfattning** visar en ordersammanfattning och stöder åtgärden för placering av ordern. Platsen **placera order** stöder också åtgärden för att placera ordern. Du kan definiera placera order-moduler på två platser för att optimera processen för att placera order från olika plattformar.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduler kan användas i kassamodulen

- **Leveransadress** – i den här modulen kan en kund lägga till eller välja leveransadressen för en order. Om kunden är inloggad visas alla adresser som har sparats för den kunden. Kunden kan sedan välja bland dessa adresser. Kunden kan också lägga till en ny adress. Leveransadressen används för alla artiklar i den order som kräver leverans. Den kan inte anpassas för enskilda radartiklar. Leveransadressformat definieras för varje land eller region och reglerna för land/region tillämpas av den här modulen. Även om modulen inte ger adressvalidering kan adressvalidering implementeras genom anpassning. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.
- **Leveransalternativ** – i den här modulen kan en kund välja ett leveransalternativ för en order. Leveransalternativen baseras på leveransadressen. Om leveransadressen ändras måste leveransalternativen hämtas igen. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.
- **Behållare för kassaavsnitt** – den här modulen är en behållare som du kan placera flera moduler i för att skapa ett avsnitt i kassaflödet. Du kan till exempel placera alla betalningsrelaterade moduler i behållaren så att de visas som ett avsnitt. Den här modulen påverkar endast flödets layout.
- **Presentkort** – i den här modulen kan en kund betala för en order genom att använda ett presentkort. Den stöder bara Microsoft Dynamics 365 Commerce presentkort. Ett eller flera presentkort kan användas på en order. Om saldot på presentkortet inte täcker beloppet i kundvagnen kan presentkortet kombineras med en annan betalningsmetod. Presentkort kan bara lösas in om kunden är inloggad.
- **Förmånspoäng** – i den här modulen kan en kund betala för en order genom att använda förmånspoäng. Den innehåller en sammanfattning av tillgängliga punkter och utgångspunkter, och låter kunden välja hur många poäng som ska lösas in. Om kunden inte är inloggad i eller inte är en förmånsmedlem, eller om det totala beloppet i vagnen är 0 (noll), döljs den här modulen automatiskt.
- **Kreditkort** – i den här modulen kan en kund betala för en order genom att använda ett kreditkort. Om det totala beloppet i vagnen täcks av ett förmånskort eller ett presentkort eller om det är 0 (noll), döljs den här modulen automatiskt. Kreditkortsintegrering tillhandahålls av Adyen betalningsanslutning. Mer information om hur du använder den här anslutningen finns i [Adyen betalningsanslutning](https://).
- **Faktureringsadress** – i den här modulen kan en kund tillhandahålla faktureringsinformation. Den här informationen bearbetas tillsammans med kreditkortsinformationen av Adyen. Modulen innehåller ett alternativ som gör att kunder kan använda sina faktureringsadresser som leveransadress.
- **Kontaktinformation** – i den här modulen kan en kund lägga till eller ändra kontaktinformation (e-postadress) för en order.
- **Placera order** – i den här modulen kan kunden beställa.
- **Innehållsrikt block** – den här modulen innehåller alla meddelanden som styrs av innehållshanteringssystem (CMS). Det kan till exempel innehålla ett meddelande om att "problem med ordern, kontakta 1-800-FABRIKAM." 
- **Ordersammanfattning** – i den här modulen visas kostnadsuppdelning för en order.
- **Orderradartiklar** – i den här modulen visas en sammanfattning av de artiklar som kommer att ingå i en order.

## <a name="retail-server-interaction"></a>Butiksserverinteraktion

Större delen av utcheckningen, t.ex. leveransadress och leveransmetod, lagras i kundvagnen och bearbetas som en del av ordern. Det enda undantaget är kreditkortsinformationen. Den här informationen bearbetas direkt med hjälp av Adyen betalningsanslutning. Betalningen är auktoriserad men debiteras inte.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Lägg till en kassamodul på en ny sida och ställa in de obligatoriska egenskaperna.

Om du vill lägga till en kassamodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Fragment \> Nytt fragment** och namnge det nya fragment **Kassafragment**.
1. Lägg till en kassamodul i fragmentet.
1. Lägg till en rubrik i kassamodulen.
1. På platsen **Kassainformation** lägg till leveransadress, leveransalternativ, behållare för kassaavsnitt och kontaktinformationsmoduler. Det ska nu finnas fyra avsnitt på platsen **Kassainformation**.
1. Lägg till presentkort, förmånspoäng och kreditkortsmoduler i behållarmodulen kassaavsnitt. På så sätt ser du till att alla betalningsmetoder visas tillsammans i ett avsnitt.
1. På platsen **ordersammanfattning**, lägg till ordersammanfattning, placera order och innehållsrika moduler.
1. Lägg till följande text i modulen innehållsrika block: **för frågor om din beställning, kontakta 1-800-FABRIKAM.**
1. På platsen **Placera order**, lägg till modul för placering av order.
1. Välj **Spara**. Vissa moduler kanske inte återges i förhandsgranskningen eftersom de inte har något kundvagnssammanhang.
1. Checka in fragmentet och publicera det.
1. Skapa en mall som använder det nya kassafragmentet.
1. Skapa en kassasida som använder den nya mallen.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
