---
title: Moduler för omdömen och recensioner
description: I denna artikel beskrivs klassificeringar och recensioner som används på produktinformationssidor i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: f5829ccf9fad78e8669f5109d6c15e71af2ca768
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894420"
---
# <a name="ratings-and-reviews-modules"></a>Moduler för omdömen och recensioner

[!include [banner](includes/banner.md)]

I denna artikel beskrivs klassificeringar och recensioner som används på produktinformationssidor (PDP) i Microsoft Dynamics 365 Commerce.

Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, och är också en mekanism för att samla in feedback från kunder om produkter. 

Omdömen visas på produktlistsidor, kategorilistsidor, sökresultatsidor och andra webbplatssidor. 

Omdömeshistogram och produktrecensioner visas på PDP. Knappen **Skriv ett omdöme** låter kunder skicka in omdömen och recensioner om en produkt. Dessa PDP-funktioner styrs av klassificerings- och granskningsmoduler.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Moduler för omdömen och recensioner på PDP 

Tre moduler visar sammanfattningen av omdömen och recensioner i PDP:
- Modulen skriv recension
- Modulen produktrecensionslista
- Modul för omdömeshistogram
 
I bilden nedan visas hur modulerna omdömen och recensioner ser ut på ett PDP.

![Moduler för omdömen och recensioner på en PDP.](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Information om hur du optimerar mallar och layouter i PDP så att du kan dela med dig av konfigurationerna för omdömen och recensioner av moduler mellan flera PDP på din näthandelssajt finns på [Översikt över mallar och layouter](templates-layouts-overview.md).

Följande illustration visar hur dialogrutan **Lägg till modul** presenterar moduler för omdömen och recensioner i Dynamics 365 Commerce.
![Dialogrutan Lägg till modul.](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Modulen skriv recension

Modulen skriv recension inkluderar knappen **Skriv en recension**, där användarna kan logga in, tilldela ett omdöme och skriva en recension av en produkt. Med hjälp av modulen kan du också redigera ett omdöme eller granska de som tidigare har skickat in dem. Den här modulen visas normalt ovanför modulerna omdömeshistogram och produktrecensioner i en PDP.
Bilden nedan visar dialog rutan **Skriv en recension** som visas när en kund väljer **skriva en recension**. Kunden kan använda den här dialogrutan för att skicka ett omdöme och en recension.

![Dialogrutan Skriv en recension.](media/rnr-eCommerce-write-review-module.png)

I följande tabell visas den egenskap för modulen skriv recension som måste konfigureras i utvecklingsverktyget.

| Egenskapsnamn | Värde        | Egenskapsbeskrivning                 |
|---------------|--------------|--------------------------------------|
| Namn          | Skriv recension | Namnet på modulen för skriv en recension. |

### <a name="ratings-histogram-module"></a>Modul för omdömeshistogram

Modulen omdömeshistogram visar ett histogram med omdömet. Den här modulen visas normalt mellan modulen skriv recension och produktrecensionslistan på ett PDP.
Modulen omdömeshistogram kräver ingen konfiguration. Du behöver bara lägga till modulen i PDP-mallen. Följande illustrationer visar hur en PDP-mall ser ut i Dynamics 365 Commerce när moduler för omdömen och recensioner konfigureras för visning på PDP.
![PDP-mall när omdömen och recensioner konfigureras för visning på PDP.](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Modulen produktrecensionslista

I modulen produktrecensionslista visas en lista med produktrecensioner tillsammans med alternativen sortera, filtrera och sidbrytning. Den här modulen visas normalt efter modulen för omdömeshistogram på ett PDP.
I följande tabell visas de egenskaper för modulen produktrecensionslista som måste konfigureras i utvecklingsverktyget.

| Egenskapsnamn              | Värde | Egenskapsbeskrivning |
|----------------------------|-------| ---------------------|
| Recensioner som visas på varje sida | 10    | Antalet recensioner som ska visas i taget på ett PDP. Knapparna **Nästa** och **föregående** inkluderas så att användarna kan förflytta sig genom sidorna i recensioner. |

#### <a name="ratings-histogram--summary-view"></a>Omdömeshistogram – sammanfattningsvy

Modulen produktrecensionslista innehåller en plats där du kan lägga till en modul för ett omdöme i histogram. Följande illustration visar hur du kan lägga till en modul för omdömeshistogram i modulen produktrecensionslista i Dynamics 365 Commerce.

![Lägga till modulen omdömeshistogram i modulen produktrecensionslista.](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]