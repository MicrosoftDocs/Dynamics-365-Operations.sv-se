---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025707"
---
# <a name="header-module"></a>Modul för sidhuvud


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

I Dynamics 365 Commerce består ett sidhuvud av flera moduler, t.ex. rubrik, navigeringsmeny, sökning, annonsbanderoll och moduler för godkännande. 

Modulen rubrik innehåller en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen, en vagnsymbol, en önskelista-symbol, inloggningsalternativ och sökfältet. En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet). Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).

## <a name="properties-of-a-header-module"></a>Egenskaper för sidhuvudmodul

En sidhuvudmodul stöder egenskaperna **logotypbild**, **logotyplänk** och **länkar till mitt konto**. 

Egenskaperna **logotypbild** och **logotyplänk** används för att definiera en logotyp på sidan. Mer information finns i [Lägg till en logotyp](add-logo.md). 

Egenskapen **länkar till mitt konto** kan användas för att definiera kontosidor som webbplatsägaren vill visa snabblänkar för i rubriken.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduler som är tillgängliga i en sidhuvudmodul

Följande moduler kan användas i en sidhuvudmodul:

- **Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar. Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Commerce. Navigeringsmenyn har egenskapen **navigeringskälla** som används för att ange navigeringsmenyobjekt och statiska menyalternativ i Retail Server som en källa. Om statiska menyalternativ anges som källa kan relativa länkar till andra sidor på webbplatsen tillhandahållas. Konfigurerade artiklar visas sedan som sidhuvudnavigering. 
- **Sökfält** – Sökmodulen låter användarna ange söktermer så att de kan söka efter produkter. URL-adressen till standardsöksidan och parametrarna för sökning måste ges i tillägg till **Webbplatsinställningar \> Tillägg**. Sökmodulen har egenskaper som gör att du kan hindra sökknappen eller etiketten efter behov. Sökmodulen stöder också automatiska förslag, t.ex. produkt, nyckelord och kategorisökningsresultat.

## <a name="create-a-header-module-for-a-page"></a>Skapa en sidhuvudmodul för en sida

Gör så här om du vill skapa en sidhuvudmodul.

1. Skapa ett fragment med namnet **sidhuvudfragment**och lägg till en modul för behållare.
1. I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.
1. Lägg till moduler för annonsbanderoll och cookies i behållarmodulen.
1. Lägg till en annan behållarmodul till fragmentet och ställ in egenskapen **bredd** till **fyll behållare**.
1. Lägg till en sidhuvudmodul till den andra behållarmodulen.
1. I facket **Navigeringsmeny** i sidhuvudmodulen, lägg till en modul för navigeringsmeny. 
1. Konfigurera egenskaperna för modulen för navigeringmenyn i egenskapsfönstret för modulen navigering.
1. Lägg till facket **sök** i sidhuvudmodulens sökmotor. 
1. Konfigurera egenskaperna för sökmodulen för navigeringmenyn i egenskapsfönstret för sökmodulen. 
1. Spara sidfragmentet, slutför redigeringen och publicera det. 

Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.

1. I facket **Huvud** lägger du till standardsidan, lägg till sidhuvudfragmentet som innehåller sidhuvudmodulen i rubriken.
1. Spara mallen, slutför redigeringen och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
