---
title: Modul för leveransadress
description: Det här avsnittet handlar om modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: aeaa410fde29b285fdbbdd6acac19b0c4e917aa5
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415993"
---
# <a name="shipping-address-module"></a>Modul för leveransadress

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver om modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Leveransadressmodulen låter kunderna lägga till eller välja leveransadressen för en order under kassautcheckningsflödet. Om kunden är inloggad visas alla adresser som har sparats för den kunden och kunden kan välja bland dem. Kunden kan också lägga till en ny adress. Leveransadressmodulen används för alla artiklar i den order som kräver leverans.

Adressformat för leverans kan definieras i Commerce-administration för varje land eller region och i modulen för leverans används lands-/regionspecifika regler.

När kunderna anger en leveransadress under kassautcheckningsflödet kan de välja att spara adressen som en primär adress. Det här alternativet visas bara om kunden är inloggad.

Även om modulen leveransadress inte ger adressvalidering kan denna funktion implementeras genom anpassning.

Följande bild visar ett exempel på en ny leveransadressmodul på en kassasida.

![Exempel på en modul för leveransadresser på en sida i kassan](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Modulegenskaper

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En valfri rubrik för leveransadressmodulen. |
| Visa adresstyp | **Sant** eller **falskt** | Om den här valfria egenskapen har värdet **True** visas en adresstyp, t.ex. **Start** eller **företag**. Om ingen adresstyp har angetts kommer adressen automatiskt att sparas som **Typ**=**Övriga**. |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till leveransadressmodul på en kassasida och ställa in de obligatoriska egenskaperna.

En modul för leveransadress kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurerar modulen för leveransadress och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)
