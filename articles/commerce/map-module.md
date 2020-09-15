---
title: Kartmodul
description: Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "3647050"
---
# <a name="map-module"></a>Kartmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En kartmodul visar platserna för butikerna i en interaktiv karta som återges med hjälp av [Bing Maps-V8 webbkontroll](https://docs.microsoft.com/bingmaps/v8-web-control/). En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-administration. I kartmoduler finns olika vyer, till exempel väg, flyg och gata som användarna kan välja för att visa kartplatser. De tillåter också interaktioner som att zooma in och använda användarens plats.

En kartmodul arbetar tillsammans med modulen butiksväljare för att fastställa geografiska platser för butiker som måste återges på en karta. Butiksväljare och kartmoduler interagerar när en användare väljer en butik i en av dessa moduler på en webbplatssida. Kartmoduler kan utökas för andra scenarier, förutom interaktion med modulerna för butiksväljare. Det krävs emellertid att modulen anpassas.

Kartmodulen introducerades i Commerce version 10.0.13.

Följande bild visar ett exempel på en kartmodul som används på en sida för butiksväljare.

![Exempel på en modul för butiksväljare](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Modulegenskaper

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Rubrik | Text | Rubriken för modulen. |
| Kartnålsalternativ: standardikon | Bild | Symbolbilden för kartnål som används för butiker som visas på en karta. |
| Kartnålsalternativ: aktiv ikon | Bild | Symbolbilden för kartnål som används för butiker som väljs på en karta. |
| Kartnålsalternativ: färg på standardikon | Teckensträng | Texten eller det hexadecimala värdet för färgen på kartnålssymboler på en karta. |
| Kartnålsalternativ: färg aktiv ikon | Teckensträng | Texten eller det hexadecimala värdet för färgen på den valda kartnålssymboler på en karta. |
| Visa index | **Sant** eller **falskt** | Om den här egenskapen har värdet **sant** visas ett index för varje kartnål som anger att en butik ska visa ett index. Det här indexet matchar indexet i listvyn som visas i modulen butiksväljare. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Lägg till tillåtna mappnings-URL:er till direktiven för webbplatsinnehållets säkerhetsprincip

För att kartmodulen ska samverka med Bing Maps måste du se till att följande mappnings-URL:er tillåts (kallas också "vitlistade") per webbplatsinnehållets säkerhetsprincip (CSP). Den här inställningen görs i Commerce webbplatsskapare genom att lägga till tillåtna URL:er till olika webbplatsers CSP-direktiv (till exempel **img-src**). Mer information finns i [säkerhetsprinciper för innehåll](manage-csp.md). 

- Till direktivet **connect-src** lägger du till **&#42;.bing.com**.
- Till direktivet **img-src** lägger du till **&#42;.virtualearth.net**.
- Till direktivet **script-src** lägger du till **&#42;.bing.com, &#42;.virtualearth.net**.
- Till direktivet **script style-src** lägger du till **&#42;.bing.com**.

## <a name="add-a-map-module-to-a-page"></a>Lägg till en kartmodul på en ny sida

Mer information om hur du konfigurerar en kartmodul på en sida finns i [modulen butiksväljare](store-selector.md). 
 
## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Modul för butiksväljare](store-selector.md)

[Hantera Bing-kartor för din organisation](./dev-itpro/manage-bing-maps.md)

[Bing Maps V8 webbkontroll](https://docs.microsoft.com/bingmaps/v8-web-control/)