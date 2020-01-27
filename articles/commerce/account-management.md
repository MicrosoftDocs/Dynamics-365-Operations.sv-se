---
title: Sidor och moduler för kontohantering
description: Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
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
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885819"
---
# <a name="account-management-pages-and-modules"></a>Sidor och moduler för kontohantering

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Kontohantering refererar till en grupp med sidor som används för att hantera information om användarkonton i Dynamics 365 Commerce. Kontohanteringssidorna omfattar landningssida för kontohantering och sidor för användarprofil, sida för användaradress, sida för orderhistorik, sida för orderinformation, förmånssida och sida för önskelista.

### <a name="account-management-landing-page"></a>Landningssidan Kontohantering

Landningssidan för kontohantering använder följande moduler:

- **Innehållsplacering** – den här modulen är en behållarmodul som innehåller alla moduler på landningssidan för kontohantering.
- **Kontots välkomstobjekt** – modulen används för att tillhandahålla ett välkomstmeddelande på sidan kontohantering. Det inkluderar egenskaper för rubriken och panelstorleken. Egenskapen **panelstorlek** definierar modulens bredd i modulen innehållsplacering. Värdena sträcker sig från **1** till **12**, där **12** representerar den fulla bredden på behållaren för innehållsplacering.
- **Artikel för placering av kontoorder** – Den här modulen används för att ge en översikt över antalet order som har placerats av användarkontot. Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan orderhistorik.
- **Artikel för placering av kontoorder** – den här modulen används för att tillhandahålla en sammanfattning av användarprofilen. Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarprofil.
- **Artikel för kontoönskelista** – modulen används för att ge en sammanfattning av artiklarna på kundens önskelista. Det kan till exempel vara "du har tio artiklar i din önskelista." Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för önskelista.
- **Artikel för kontoadress** – den här modulen används för att tillhandahålla en sammanfattning av användarens adress. Det kan till exempel vara "du har 2 adresser som lagts till i ditt konto". Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarens adress.
- **Artikeln kontoförmån** – den här modulen används för att visa och länka till information om lojalitetsprogram. Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer" och länken "bli en medlem". Länken "Visa detaljer" ska vara konfigurerad för omdirigering till förmånssidan. Länken "bli en medlem" bör konfigureras för att omdirigeras till en sida där användarna kan delta i förmånsprogrammet.

### <a name="order-history-page"></a>Sidan för orderhistorik

På sidan för orderhistorik används modulen orderhistorik för att visa alla nya order som användaren har placerat.

### <a name="order-details-page"></a>Sidan Orderdetaljer

Sidan orderdetaljer innehåller detaljerad information för varje order och du öppnar den från sidan orderhistorik. Den använder modulen orderdetaljer, som kräver försäljnings-ID eller transaktions-ID för att hämta orderdetaljer.

### <a name="user-profile-page"></a>Sidan användarprofil

På sidan användarprofil visas information om användarkonton, t.ex. användarens namn och e-postadress. Den använder modulen användarprofil. Även om e-postadressen inte kan tas bort, kan den redigera. På sidan användarprofil visas även användarinställningar som gör det möjligt för en användare att anmäla sig eller välja bort vissa funktioner, till exempel anpassning av rekommendationslistor. 

### <a name="user-address-page"></a>Sidan användaradress

På sidan användaradress visas listan med adresser som är associerade med användarkontot. Användaren tillhandahöll antingen dessa adresser i kassan eller lade till dem direkt på den här sidan. Modulen för användaradresser används för att lägga till och redigera adresser, ange den primära adressen och återge befintliga adresser på sidan.

### <a name="wish-list-page"></a>Sidan för önskelista

Sidan önskelista visar en lista över artiklar som har lagts till i kundens önskelista. Den använder modulen önskelista för att återge artiklar i önskelistan.

### <a name="loyalty-page"></a>Förmånssida

Med hjälp av förmånssidan kan kunderna ansluta sig till ett förmånsprogram eller, om de redan har förmånsprogrammedlemmar, visa sina programuppgifter. De kan också visa de poäng de har fått och löst in i de senaste transaktionerna.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
