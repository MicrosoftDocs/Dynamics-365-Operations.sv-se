---
title: Modul för leveransadress
description: Denna artikel handlar om modulen för leveransadress och förklarar hur du konfigurerar den i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 48e6909b4dac9722830a83ec3a63a58876768d7e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275016"
---
# <a name="shipping-address-module"></a>Modul för leveransadress

[!include [banner](includes/banner.md)]

Denna artikel beskriver modulen för leveransadress och förklarar hur du konfigurerar den i Microsoft Dynamics 365 Commerce.

Leveransadressmodulen låter kunderna lägga till eller välja leveransadressen för en order under kassaflödet. Om kunden är inloggad visas alla adresser som har sparats för den kunden och kunden kan välja bland dem. Kunden kan också lägga till en ny adress. Leveransadressmodulen används för alla artiklar i den order som kräver leverans.

Adressformat för leverans kan definieras i Commerce headquarters för varje land eller region och i modulen för leverans används lands-/regionspecifika regler.

När kunderna anger en leveransadress under kassaflödet kan de välja att spara adressen som en primär adress. Det här alternativet visas bara om kunden är inloggad.

Även om modulen leveransadress inte ger adressvalidering kan denna funktion implementeras genom anpassning.

Följande bild visar ett exempel på en ny leveransadressmodul på en kassasida.

![Exempel på en modul för leveransadresser på en kassasida.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Modulegenskaper

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En valfri rubrik för leveransadressmodulen. |
| Visa adresstyp | **Sant** eller **falskt** | Om den här valfria egenskapen har värdet **True** visas en adresstyp, t.ex. **Start** eller **företag**. Om ingen adresstyp har angetts kommer adressen automatiskt att sparas som **Typ**=**Övriga**. |
| Aktivera automatiskt förslag| **Sant** eller **falskt** | Om den här valfria egenskapen ställs in på **True**, ges automatiska adressförslag. De här förslagen används av Bing Maps. Information om hur du konfigurerar Bing Maps-integrering för din webbplats finns i [modulen Butiksväljare](store-selector.md). Den här funktionen är tillgänglig i Commerce version 10.0.15.|
|Alternativ för automatiskt förslag| Ett nummer| Om automatiska adressförslag har aktiverats kan du ange ytterligare alternativ, till exempel det högsta antalet förslag som ska ges.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till leveransadressmodul på en kassasida och konfigurera de obligatoriska egenskaperna.

En modul för leveransadress kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurerar modulen för leveransadress och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Modul för upphämtningsinformation](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Modul för butiksväljare](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
