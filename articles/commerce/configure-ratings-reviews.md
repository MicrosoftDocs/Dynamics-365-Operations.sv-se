---
title: Konfigurera omdömen och recensioner
description: I det här avsnittet beskrivs hur du konfigurerar din e-handelsplats så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0aac4b680590a95f465d33950f2933c4a4582e54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002207"
---
# <a name="configure-ratings-and-reviews"></a>Konfigurera omdömen och recensioner


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar din e-handelsplats så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, genom att visa vad andra kunder tycker om dessa produkter. För näthandelsplatser är omdömen och recensioner också en mekanism för att samla in kundernas feedback om produkter. 

Omdömen visas på produktlistsidor, kategorilistsidor, sökresultatsidor och andra webbplatssidor. Omdömeshistogram och produktrecensioner visas på produktinformationssidor (PDP). Knappen **Skriv ett omdöme** låter kunder skicka in omdömen och recensioner om en produkt.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Moduler för omdömen och recensioner på PDP 

Tre moduler visar sammanfattningen av omdömen och recensioner i PDP:

- Modulen skriv recension
- Modulen produktrecensionslista
- Modul för omdömeshistogram
 
I bilden nedan visas hur modulerna omdömen och recensioner ser ut på ett PDP.

![Moduler för omdömen och recensioner på en PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Information om hur du optimerar mallar och layouter i PDP så att du kan dela med dig av konfigurationerna för omdömen och recensioner av moduler mellan flera PDP på din näthandelsplats finns på [Översikt över mallar och layouter](templates-layouts-overview.md).

Följande illustration visar hur dialogrutan **Lägg till modul** presenterar moduler för omdömen och recensioner i Dynamics 365 Commerce.

![Dialogrutan Lägg till modul](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Modulen skriv recension

Modulen skriv recension inkluderar knappen **Skriv en recension**, där användarna kan logga in, tilldela ett omdöme och skriva en recension av en produkt. Med hjälp av modulen kan du också redigera ett omdöme eller granska de som tidigare har skickat in dem. Den här modulen visas normalt ovanför modulerna omdömeshistogram och produktrecensioner i en PDP.

Bilden nedan visar dialog rutan **Skriv en recension** som visas när en kund väljer **skriva en recension**. Kunden kan använda den här dialogrutan för att skicka ett omdöme och en recension.

![Dialogrutan Skriv en recension](media/rnr-eCommerce-write-review-module.png)

I följande tabell visas den egenskap för modulen skriv recension som måste konfigureras i utvecklingsverktyget.

| Egenskapsnamn | Värde        | Egenskapsbeskrivning                 |
|---------------|--------------|--------------------------------------|
| Namn          | Skriv recension | Namnet på modulen för skriv en recension. |

### <a name="ratings-histogram-module"></a>Modul för omdömeshistogram

Modulen omdömeshistogram visar ett histogram med omdömet. Den här modulen visas normalt mellan modulen skriv recension och produktrecensionslistan på ett PDP.

Modulen omdömeshistogram kräver ingen konfiguration. Du behöver bara lägga till modulen i PDP-mallen. 

Följande illustrationer visar hur en PDP-mall ser ut i Dynamics 365 Commerce när moduler för omdömen och recensioner konfigureras för visning på PDP.

![PDP-mall när omdömen och recensioner konfigureras för visning på PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Modulen produktrecensionslista

I modulen produktrecensionslista visas en lista med produktrecensioner tillsammans med alternativen sortera, filtrera och sidbrytning. Den här modulen visas normalt efter modulen för omdömeshistogram på ett PDP.

I följande tabell visas de egenskaper för modulen produktrecensionslista som måste konfigureras i utvecklingsverktyget.

| Egenskapsnamn              | Värde | Egenskapsbeskrivning |
|----------------------------|-------| ---------------------|
| Recensioner som visas på varje sida | 10    | Antalet recensioner som ska visas i taget på ett PDP. Knapparna **Nästa** och **föregående** inkluderas så att användarna kan förflytta sig genom sidorna i recensioner. |

#### <a name="ratings-histogram--summary-view"></a>Omdömeshistogram – sammanfattningsvy

Modulen produktrecensionslista innehåller en plats där du kan lägga till en modul för ett omdöme i histogram. Följande illustration visar hur du kan lägga till en modul för omdömeshistogram i modulen produktrecensionslista i Dynamics 365 Commerce.

![Lägga till modulen omdömeshistogram i modulen produktrecensionslista](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Konfigurera en webbplats att visa omdömen och recensioner

Konfigurationsvärden för omdömen och recensioner, till exempel innehavar-ID, granska textlängd och granska rubriklängd, konfigureras på webbplatsnivå. 

Konfigurera en webbplats för visning av värderingar och recensioner enligt följande instruktioner. 

1. Gå till **Start \> Webbplatser**.
1. Välj namnet på webbplatsen. 
1. Gå till **Webbplatshantering \> Utbyggbarhet**. 
1. I fältet **granska textens maxlängd** anger du det maximala antalet tecken som ska granska text kan ha (t.ex. **1000**). 
1. I fältet **granska rubrikens maxlängd** anger du det maximala antalet tecken som ska granska rubriker kan ha (t.ex. **55**). 
1. Välj **Spara och publicera**. 

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Konfigurera en webbplats att visa omdömen och recensioner](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Länka en produktvärdering till avsnittet recensioner i ett PDP

En produktvärdering visas under produktrubriken högst upp i PDP. Produktvärderingen kan konfigureras så att den länkas till avsnittet **recensioner** i samma PDP. 

Om du vill länka en produktvärdering avsnittet **recensioner** i PDP följer du stegen nedan.

1. Öppna PDP-mallen. 
1. Gå till **Inställningar för behållarmodulen inköpsruta**.
1. Under **inköpsruta**, välj **produktvärderingar** och sedan väljer du kryssrutan **Länka klicka till modulen för fullständig recension**.

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Länka en produktvärdering till avsnittet recensioner i ett PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Konfigurera länken till sidan sekretess och policy

Konfigurera länken till sidan sekretess och policy genom att följa dessa steg.

1. Gå till **Start \> Webbplatser**.
1. Välj namnet på webbplatsen. 
1. Gå till **Webbplatshantering \> Utbyggbarhet**
1. På sidan **Flöden**, under **RNR sekretess och policy**, välj **Lägg till en länk**. Om en länk redan har angivits och du vill ersätta den markerar du länken. 
1. I dialogrutan **Lägg till en länk** väljer du länken för sidan om sekretess och policy och välj sedan **OK**. 
1. Välj **Spara och publicera**. 

Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.

![Konfigurera länken till sidan sekretess och policy](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Synkronisera produktklassificeringar i Dynamics 365 Retail](sync-product-ratings.md)
