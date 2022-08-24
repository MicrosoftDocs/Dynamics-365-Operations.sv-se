---
title: Ikon för kundvagnsmodul
description: Denna artikel handlar om kundvagnsikonmodulen och beskriver hur du lägger till denna på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: e35b0ee5341b8b5531ad2c80c868ca4c07ebd315
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280514"
---
# <a name="cart-icon-module"></a>Ikon för kundvagnsmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om kundvagnsikonmodulen och beskriver hur du lägger till denna på webbsidorna i Microsoft Dynamics 365 Commerce.

Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen. Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över. Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan. Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen. Detta minskar antalet sidnavigeringer och gör kassan snabbare. 

Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.

![Exempel på en modul för kundvagnsikon.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa minivagn** – När den här egenskapen är inställd på **True**, en vagnöversikt (minivagn) visas när användare håller muspekaren över vagnikonen. Den här funktionen stöds endast för portar i skrivbordsvy.
- **Tillåt anonym kassa** – När denna egenskap ställs in på **True**, minivagnen tillåter användare som inte är inloggade att göra en gästkassa. Den här egenskapen är tillgänglig i versionen Commerce version 10.0.21 som en del av paketet Commerce-modulbibliotek.
- **Order av artiklar** – Denna egenskap styr i vilken ordning artiklar visas i vagnen. När alternativet **Nya objekt har lagts till överst på listan** väljs, nya artiklar som läggs till i vagnen visas högst upp i listan över minivagnartiklar. När standardalternativet **Nya objekt har lagts till överst på listan** väljs, nya artiklar som läggs till i vagnen visas högst upp i listan över minivagnartiklar. Den här egenskapen är tillgänglig i versionen Commerce version 10.0.21 som en del av paketet Commerce-modulbibliotek.

> [!IMPORTANT]
> Egenskaperna **Tillåt anonym kassa** och **Order av artiklar** är tillgängliga från version 10.0.21 av Commerce. De kräver att paketversion 9.31 för Commerce-modulens bibliotek är installerad.

## <a name="module-properties-and-slots-in-the-adventure-works-theme"></a>Modulegenskaper och platser i Adventure Works-temat

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
