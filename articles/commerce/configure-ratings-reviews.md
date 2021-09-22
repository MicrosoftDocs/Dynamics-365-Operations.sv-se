---
title: Konfigurera omdömen och recensioner
description: I det här avsnittet beskrivs hur du konfigurerar din näthandelssajt så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7ac91dd1d3dfffbf98733bbd8fe8beda538250da
ms.sourcegitcommit: 81bc42551e6c9af6ad38908afb606ee1f8d3c44b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2021
ms.locfileid: "7473559"
---
# <a name="configure-ratings-and-reviews"></a>Konfigurera omdömen och recensioner

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar din näthandelssajt så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.

Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, genom att visa vad andra kunder tycker om dessa produkter. För näthandelssajter är omdömen och recensioner också en mekanism för att samla in kundernas feedback om produkter. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Konfigurera en webbplats att visa omdömen och recensioner

Konfigurationsvärden för omdömen och recensioner, till exempel innehavar-ID, granska textlängd och granska rubriklängd, konfigureras på webbplatsnivå. 

Konfigurera en webbplats för visning av värderingar och recensioner enligt följande instruktioner. 

1. Gå till **Start \> Webbplatser**.
1. Välj namnet på webbplatsen. 
1. Gå till **Webbplatsinställningar \> Tillägg**. 
1. I fältet **granska textens maxlängd** anger du det maximala antalet tecken som ska granska text kan ha (t.ex. **1000**). 
1. I fältet **granska rubrikens maxlängd** anger du det maximala antalet tecken som ska granska rubriker kan ha (t.ex. **55**). 
1. Välj **Spara och publicera**. 

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Konfigurera en webbplats att visa omdömen och recensioner.](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Länka en produktvärdering till avsnittet recensioner i ett PDP

En produktvärdering visas under produktrubriken högst upp i PDP. Produktvärderingen kan konfigureras så att den länkas till avsnittet **recensioner** i samma PDP. 

Om du vill länka en produktvärdering avsnittet **recensioner** i PDP följer du stegen nedan.

1. Öppna PDP-mallen. 
1. Gå till **Inställningar för behållarmodulen inköpsruta**.
1. Under **inköpsruta**, välj **produktvärderingar** och sedan väljer du kryssrutan **Länka klicka till modulen för fullständig recension**.

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Länka en produktvärdering till avsnittet Recensioner på en PDP (produktdetaljsida).](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Konfigurera länken till sidan sekretess och policy

Konfigurera länken till sidan sekretess och policy genom att följa dessa steg.

1. Gå till **Start \> Webbplatser**.
1. Välj namnet på webbplatsen. 
1. Gå till **Webbplatsinställningar \> Tillägg**.
1. På sidan **Flöden**, under **RNR sekretess och policy**, välj **Lägg till en länk**. Om en länk redan har angivits och du vill ersätta den markerar du länken. 
1. I dialogrutan **Lägg till en länk** väljer du länken för sidan om sekretess och policy och välj sedan **OK**. 
1. Välj **Spara och publicera**. 

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Konfigurera länken till sidan för sekretess och policy.](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Konfigurera klassificeringar och recensioner av moduler på produktinformationssidor

Information om hur du konfigurerar modulen värderingar och recensioner på produktinformationssidor finns [Moduler för omdömen och moduler](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera klassificeringar och recensioner av moduler på produktinformationssidor](ratings-reviews-modules.md)

[Synkronisera produktklassificeringar i Dynamics 365 Retail](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
