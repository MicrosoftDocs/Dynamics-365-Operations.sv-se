---
title: Sidor och moduler för kontohantering
description: Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0f963bcf65ae622522fe52fd59996c6ec0ecf17
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817168"
---
# <a name="account-management-pages-and-modules"></a>Sidor och moduler för kontohantering

[!include [banner](includes/banner.md)]

Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Kontohantering refererar till en grupp med sidor som används för att hantera information om användarkonton i Dynamics 365 Commerce. Kontohanteringssidorna omfattar landningssida för kontohantering och sidor för användarprofil, sida för användaradress, sida för orderhistorik, sida för orderinformation, förmånssida och sida för önskelista.

### <a name="account-management-landing-page"></a>Landningssidan Kontohantering

Landningssidan för kontohantering använder följande moduler:

- **Behållare** - alla moduler för landningssida för kontohantering ska placeras i en behållare. 
- **Kontots välkomstpanel** – modulen används för att tillhandahålla ett välkomstmeddelande på sidan kontohantering. Den innehåller egenskaper för rubriken.
- **Allmän panel för konto** – denna modul kan användas för att tillhandahålla rubriker och länkar till kontohanteringssidor, t.ex. "orderhistorik" eller "min profil"-sidorna. Den generiska panelen kan användas för att konfigurera en panel för varje sida. I Fabrikam används den här modulen för länkarna "orderhistorik" och "min profil" på landningssidan för kontohantering.
- **Panel för kontoönskelista** – modulen används för att ge en sammanfattning av artiklarna på kundens önskelista. Det kan till exempel vara "du har tio artiklar i din önskelista." Den inkluderar egenskaper för rubriken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för önskelista. 
- **Panel för kontoadress** – den här modulen används för att tillhandahålla en sammanfattning av användarens adress. Det kan till exempel vara "du har 2 adresser som lagts till i ditt konto". Den inkluderar egenskaper för rubriken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarens adress.
- **Panel för kontoförmån** – den här modulen används för att visa och länka till information om lojalitetsprogram. Den här panelen har två lägen: ett tillstånd visar länkar för att delta i en förmånsprogam om användaren inte redan är medlem. I det andra läget visas länkar som visar sidan med förmånsinformation när användaren redan är medlem. Egenskaper inkluderar rubrik, "registrerings"-länken och "Visa förmån"-länken. Länken "Visa förmån" ska vara konfigurerad för omdirigering till förmånssidan. Länken "Registrera" bör konfigureras för att omdirigeras till en sida där användarna kan delta i förmånsprogrammet. 

### <a name="order-history-page"></a>Sidan för orderhistorik

På sidan för orderhistorik används modulen orderhistorik för att visa alla nya order som användaren har placerat.

### <a name="order-details-page"></a>Sidan Orderdetaljer

Sidan orderdetaljer innehåller detaljerad information för varje order och du öppnar den från sidan orderhistorik. Den använder modulen orderdetaljer, som kräver försäljnings-ID eller transaktions-ID för att hämta orderdetaljer.

### <a name="user-profile-page"></a>Sidan användarprofil

På sidan användarprofil visas information om användarkonton, t.ex. användarens namn och e-postadress. Den använder informationen från användarprofilen och redigeringsmodulerna för användarprofiler. Även om e-postadressen inte kan tas bort, kan den redigera. På sidan användarprofil visas även användarinställningar som gör det möjligt för en användare att anmäla sig eller välja bort vissa funktioner, till exempel anpassning av rekommendationslistor. 

### <a name="user-address-page"></a>Sidan användaradress

På sidan användaradress visas listan med adresser som är associerade med användarkontot. Användaren tillhandahöll antingen dessa adresser i kassan eller lade till dem direkt på den här sidan. Modulen för användaradresser används för att lägga till och redigera adresser, ange den primära adressen och återge befintliga adresser på sidan.

### <a name="wish-list-page"></a>Sidan för önskelista

Sidan önskelista visar en lista över artiklar som har lagts till i kundens önskelista. Den använder modulen önskelista för att återge artiklar i önskelistan.

### <a name="loyalty-page"></a>Förmånssida

Med hjälp av förmånssidan kan kunderna visa deras förmånsdetaljer om de redan har förmånsprogrammedlemmar. De kan också visa de poäng de har fått och löst in i de senaste transaktionerna. Sidan använder modulen för förmånsdetaljer för att visa information om förmånerna. 

Om du vill delta i förmånsprogrammet kan du skapa en marknadsföringssida med modulerna förmånsregistrering och förmånsvillkor. Om användaren inte är medlem i ett förmånsprogram kommer dessa moduler att göra det möjligt för användaren att registrera sig.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
