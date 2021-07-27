---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e0238e9d464fc1d44cbc5091638ac7270d5b6ae3
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479314"
---
# <a name="cart-icon-module"></a>Ikon för kundvagnsmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen. Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över. Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan. Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen. Detta minskar antalet sidnavigeringer och gör utcheckningen snabbare. 

Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.

![Exempel på en modul för kundvagnsikon.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen. Den här funktionen stöds endast för portar i skrivbordsvy.

## <a name="module-properties-in-the-adventure-works-theme"></a>Modulegenskaper i Adventure Works-temat

I temat Adventure Works innehåller modulen för kundvagnsikon ytterligare två platser för minivagnen. Dessa platser ingår som ett moduldefinitionstillägg.

- **Erbjudanden för tom kundvagn** – Denna plats tar en innehållsblocksmodul. När kundvagnen är tom visas den angivna innehållsblocksmodulen. Modulen för innehållsblock kan användas för erbjudanden, marknadsföringsinnehåll och länkar till kategorisidor som hjälp för kunderna att fortsätta handla.
- **Kampanjinnehåll** – Den här platsen kan användas för kampanjerbjudanden, t.ex. "Fri frakt på order över $100." Innehållsblock, textblock och moduler för bildlistor kan användas på platsen för erbjudandeinnehåll.

Bilden nedan visar ett exempel på en ikonmodul för kundvagn i Adventure Works-temat som visar erbjudandeinnehåll i minivagnen.

![Exempel på en modul för kundvagnsikon i adventure works-temat](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Platser i Adventure Works-temat finns tillgängliga från och med Dynamics 365 Commerce-version 10.0.20.

## <a name="add-a-cart-icon-module-to-a-page"></a>Lägg till en vagnikonmodul på en ny sida

Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
