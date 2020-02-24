---
title: Kassamodul
description: I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025401"
---
# <a name="checkout-module"></a>Kassamodul


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en kassamodul på en sida och ställer in de obligatoriska egenskaperna.

## <a name="overview"></a>Översikt

En kassamodul är en särskild behållare som är värd för alla moduler som krävs för att skapa en order. Det visar ett steg-för-steg-flöde som en kund använder för att registrera all relevant information för att göra inköp. Den fångar in leveransadress, leveransmetod och faktureringsinformation. Den innehåller också en ordersammanfattning och annan information som är relaterad till en kundorder.

En kassamodul återger data baserat på kundvagn-ID. Detta kundvagn-ID sparas som en webbläsarcookie. Ett kundvagn-ID krävs för att återge information i kassamodulen, till exempel artiklarna i ordern, totalbeloppet och rabatter.

## <a name="checkout-module-properties"></a>Egenskaper för kassamodul

En betalningsmodul visar en ordersammanfattning och innehåller funktioner för att placera en order. Om du vill samla in all kundinformation som krävs innan en order kan placeras, måste ytterligare moduler läggas till i modulen för utcheckning. Därför har detaljhandlare flexibilitet att lägga till anpassade moduler i kassaflödet eller att utesluta moduler utifrån deras krav.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduler kan användas i kassamodulen

- **Leveransadress** – i den här modulen kan en kund lägga till eller välja leveransadressen för en order. Om kunden är inloggad visas alla adresser som har sparats för den kunden. Kunden kan sedan välja bland dessa adresser. Kunden kan också lägga till en ny adress. Leveransadressen används för alla artiklar i den order som kräver leverans. Den kan inte anpassas för enskilda radartiklar. Leveransadressformat definieras för varje land eller region och reglerna för land/region tillämpas av den här modulen. Även om modulen inte ger adressvalidering kan adressvalidering implementeras genom anpassning. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.
- **Leveransalternativ** – i den här modulen kan en kund välja ett leveransalternativ för en order. Leveransalternativen baseras på leveransadressen. Om leveransadressen ändras måste leveransalternativen hämtas igen. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.
- **Behållare för kassaavsnitt** – den här modulen är en behållare som du kan placera flera moduler i för att skapa ett avsnitt i kassaflödet. Du kan till exempel placera alla betalningsrelaterade moduler i behållaren så att de visas som ett avsnitt. Den här modulen påverkar endast flödets layout.
- **Presentkort** – i den här modulen kan en kund betala för en order genom att använda ett presentkort. Den stöder bara Microsoft Dynamics 365 Commerce presentkort. Ett eller flera presentkort kan användas på en order. Om saldot på presentkortet inte täcker beloppet i kundvagnen kan presentkortet kombineras med en annan betalningsmetod. Presentkort kan bara lösas in om kunden är inloggad.
- **Förmånspoäng** – i den här modulen kan en kund betala för en order genom att använda förmånspoäng. Den innehåller en sammanfattning av tillgängliga punkter och utgångspunkter, och låter kunden välja hur många poäng som ska lösas in. Om kunden inte är inloggad i eller inte är en förmånsmedlem, eller om det totala beloppet i vagnen är 0 (noll), döljs den här modulen automatiskt.
- **Betalning** – i den här modulen kan en kund betala för en order genom att använda ett kreditkort. Om det totala beloppet i vagnen täcks av ett förmånskort eller ett presentkort eller om det är 0 (noll), döljs den här modulen automatiskt. Kreditkortsintegrering tillhandahålls av Adyen betalningsanslutning för den här modulen. Mer information om hur du använder den här anslutningen finns i [Dynamics 365-betalningskoppling för Adyen](dev-itpro/adyen-connector.md).
- **Faktureringsadress** – i den här modulen kan en kund tillhandahålla faktureringsinformation. Den här informationen bearbetas tillsammans med kreditkortsinformationen av Adyen. Modulen innehåller ett alternativ som gör att kunder kan använda sina faktureringsadresser som leveransadress.
- **Kontaktinformation** – i den här modulen kan en kund lägga till eller ändra kontaktinformation (e-postadress) för en order.
- **Textblock** – den här modulen innehåller alla meddelanden som styrs av innehållshanteringssystem (CMS). Det kan till exempel innehålla ett meddelande om att "problem med ordern, kontakta 1-800-Fabrikam." 

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Större delen av utcheckningen, t.ex. leveransadress och leveransmetod, lagras i kundvagnen och bearbetas som en del av ordern. Det enda undantaget är kreditkortsinformationen. Den här informationen bearbetas direkt med hjälp av Adyen betalningsanslutning. Betalningen är auktoriserad men debiteras inte.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Lägg till en kassamodul på en ny sida och ställa in de obligatoriska egenskaperna.

Om du vill lägga till en kassamodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Fragment \> Nytt fragment** och namnge det nya fragment **Kassafragment**.
1. Lägg till en kassamodul i fragmentet.
1. Lägg till en rubrik i kassamodulen.
1. Lägg till leveransadress, leveransalternativ, behållare för kassaavsnitt och kontaktinformationsmoduler. 
1. Lägg till presentkort, förmånspoäng och betalningsmoduler i behållarmodulen kassaavsnitt. På så sätt ser du till att alla betalningsmetoder visas tillsammans i ett avsnitt.
1. Spara och förhandsgranska fragmentet. Vissa moduler som inte har ett kundvagnssammanhang kanske inte återges i förhandsgranskningen.
1. Avsluta redigeringen i fragmentet och publicera det.
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
