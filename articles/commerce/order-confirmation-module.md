---
title: Orderinformationsmodul
description: Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6610d2abe0a1b03ddd763f9a65fc1dab42f1da1b
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015190"
---
# <a name="order-details-module"></a>Orderinformationsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Orderinformationsmodul används för att visa bekräftelseinformationen när en order har placerats. Det visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation och leveransmetoden.

## <a name="order-details-module-properties"></a>Egenskaper för orderdetaljmodul

| Egenskapsnamn  | Värden | beskrivning |
|----------------|--------|-------------|
| Rubrik        | Rubriktext och rubriktagg ( **H1** , **H2** , **H3** , **H4** , **H5** eller **H6** ) | Orderdetaljmodulen kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Kontaktnummer | Text | Ett kontaktnummer kan anges för frågor som är relaterade till order. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduler som kan användas på en sida för orderinformation

När du skapar en sida för orderinformation kan du lägga till andra relevanta moduler utöver orderinformationsmodulen. Nedan följer några exempel:

- **Rekommendationsmodul** – modulen rekommendationer kan läggs till på sidan för orderinformation för att föreslå andra produkter till kunden.
- **Marknadsföringsmoduler** – valfri marknadsföringsmodul kan läggas till på sidan orderinformation om du vill visa marknadsföringsinnehåll.

## <a name="add-an-order-details-module-to-a-page"></a>Lägg till orderdetaljmodul till en sida

Om du vill lägga till en orderdetaljmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn** , ange ett namn **Orderinformationsmall** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen ( **...** ) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** , välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen ( **...** ) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** välj modulen **orderinformation** och sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska mallen. Orderinformationsmodulen kommer inte återges eftersom den kräver en kontext för orderbekräftelsenumret.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en **Orderinnehållsmall**. Under **Sidnamn** , ange **Orderinnehållsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen ( **...** ) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** välj modulen **orderinformation** och sedan **OK**.
1. I egenskapsrutan i dragspelsmodulen väljer du **rubrik** bredvid pennsymbolen.
1. I fältet **Rubriktext** i dialogrutan **Rubrik** ange rubriktext **Orderdetaljer** och välj sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Presentkortsmodul](add-giftcard.md)
