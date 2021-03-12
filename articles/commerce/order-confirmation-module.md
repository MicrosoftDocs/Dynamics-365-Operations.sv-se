---
title: Orderbekräftelsemodulen
description: Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.openlocfilehash: 9d916d2687777403f2b0df7c35171948ad2fb7db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972763"
---
# <a name="order-confirmation-module"></a>Modul för orderbekräftelse

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Orderbekräftelsemodulen används för att visa bekräftelseinformationen när en order har lagts. Denna visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation, upphämtningsalternativ och leveransmetod.

## <a name="order-confirmation-module-properties"></a>Egenskaper för orderbekräftelsemodul

| Egenskapsnamn  | Värden | Beskrivning |
|----------------|--------|-------------|
| Rubrik        | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Orderbekräftelsemodulen kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Kontaktnummer | Text | Ett kontaktnummer kan anges för frågor som är relaterade till order. |
| Visa information om upphämtningstidpunkt | Sant eller falskt | Denna egenskap är tillgänglig i Dynamics 365 Commerce 10.0.15 och senare. När värdet är "true" visas information om tidpunkt för upphämtning om en upphämtningsartikel avses|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Moduler som kan användas på en sida för orderbekräftelse

När du skapar en sida för orderbekräfta kan du lägga till andra relevanta moduler utöver orderbekräftelsemodulen. Nedan följer några exempel:

- **Rekommendationsmodul** – Rekommendationsmodulen kan läggas till på sidan för orderbekräftelse för att föreslå andra produkter till kunden.
- **Marknadsföringsmoduler** – Valfri marknadsföringsmodul kan läggas till på sidan för orderbekräftelse om du vill visa marknadsföringsinnehåll.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Lägg till en orderbekräftelsemodul på en sida

Om du vill lägga till en orderbekräftelsemodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall**, under **Mallnamn**, anger du namnet **Orderbekräftelsemall** och väljer sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** väljer du modulen **Orderbekräftelse** och väljer sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska mallen. Modulen för orderbekräftelse återges inte eftersom den kräver en kontext för orderbekräftelsenumret.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en **Orderbekräftelsemall**. Under **Sidnamn** anger du **Orderbekräftelsesida** och klickar sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** väljer du modulen **Orderbekräftelse** och väljer sedan **OK**.
1. I egenskapsrutan för orderbekräftelsemodulen väljer du **Rubrik** bredvid pennsymbolen.
1. I fältet **Rubriktext** i dialogrutan **Rubrik** anger du rubriktexten **Orderbekräftelse** och väljer sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Presentkortsmodul](add-giftcard.md)
