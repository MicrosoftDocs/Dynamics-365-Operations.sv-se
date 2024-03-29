---
title: Modul för sidhuvud
description: Denna artikel handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 63c298f36f64f2e107d3df3c0c5f3b6445546aa1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275796"
---
# <a name="header-module"></a>Modul för sidhuvud

[!include [banner](includes/banner.md)]

Denna artikel handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.

I Dynamics 365 Commerce konfigureras ett sidrubrik som ett fragment som innehåller modulerna rubrik, annonsbanderoll och cookie-samtycke. 

Modulen rubrik innehåller en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen, en vagnmodul, en önskelista-symbol, inloggningsalternativ och sökfältet. En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet). Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).

Följande bild visar ett exempel på en rubrikmodul på en startsida.

![Exempel på en rubrikmodul.](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Egenskaper för sidhuvudmodul

En sidhuvudmodul stöder egenskaperna **logotypbild**, **logotyplänk** och **länkar till mitt konto**. 

Egenskaperna **logotypbild** och **logotyplänk** används för att definiera en logotyp på sidan. Mer information finns i [Lägg till en logotyp](add-logo.md). 

Egenskapen **länkar till mitt konto** kan användas för att definiera kontosidor som webbplatsägaren vill visa snabblänkar för i rubriken.

## <a name="modules-that-are-available-within-a-header-module"></a>Moduler som är tillgängliga i en sidhuvudmodul

Följande moduler kan användas i en sidhuvudmodul:

- **Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar. Mer information finns i [Modulen navigeringsmeny](nav-menu-module.md).

- **Sökfält** – Sökmodulen låter användarna ange söktermer så att de kan söka efter produkter. URL-adressen till standardsöksidan och parametrarna för sökning måste ges i tillägg till **Webbplatsinställningar \> Tillägg**. Sökmodulen har egenskaper som gör att du kan hindra sökknappen eller etiketten efter behov. Sökmodulen stöder också automatiska förslag, t.ex. produkt, nyckelord och kategorisökningsresultat.

- **Vagnikon** – modulen kundvagn representerar vagnikonen, som visar antalet artiklar i vagnen vid en given tidpunkt. Mer information finns i avsnittet [modulen vagnikonen](cart-icon-module.md).

- **Webbplatsväljare** – modulen webbplatsväljare gör det möjligt för användarna att bläddra mellan olika fördefinierade webbplatser, baserat på marknad, regioner och nationella inställningar. Mer information finns i avsnittet [modulen webbplatsväljare](site-selector.md).

- **Butiksväljare** – modulen butiksväljare kan inkluderas i huvudmodulens plats för butiksväljare. Användarna kan då bläddra bland och söka efter butiker i närheten. Användare kan också ange en prioriterad butik. Denna butik visas sedan i rubriken. Om modulen för butiksväljaren är inkluderad i huvudmodulen, måste egenskapen **Läge** ställas in för att **Hitta butiker**. Mer information finns i avsnittet [modulen butiksväljare](store-selector.md).

> [!NOTE]
> - Stöd för användning av modulen för kundvagnikon i sidhuvudmoduler finns att tillgå från och med Dynamics 365 Commerce-version 10.0.11.
> - Stöd för användning av modulen för webbplatsväljare i sidhuvudmoduler finns att tillgå från och med Dynamics 365 Commerce-version 10.0.14.
> - Stöd för användning av modulen för butiksväljare i sidhuvudmoduler finns att tillgå från och med Dynamics 365 Commerce-version 10.0.15.

## <a name="header-module-in-the-adventure-works-theme"></a>Huvudmodulen i Adventure Works-temat

Sidhuvudmodulen har stöd för egenskapen **Mobillogotyp** i Adventure Works-temat. Med denna egenskap kan en logotyp anges för mobila vyer. Egenskapen **Mobillogotyp** finns som moduldefinitionstillägg.

> [!IMPORTANT]
> Adventure Works-temat finns tillgängligt från och med Dynamics 365 Commerce-version 10.0.20.

## <a name="create-a-header-fragment-for-a-page"></a>Skapa ett huvudfragment för en sida

Gör så här om du vill skapa ett huvudfragment.

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Välj ett nytt fragment** väljer du modul för **Behållare**, anger ett namn på fragmentet och väljer sedan **OK**.
1. Välj platsen **standardenhet** och sedan i egenskapsfönstret till höger, ange egenskapen **Bredd** till **Fyll skärm**.
1. I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** välj **Cookie-samtycke**, **Huvud** och **Kampanjbanderoll** och välj sedan **OK**.
1. I egenskapsfönstret i modulen **Kampanjbanderoll** välj **Lägg till meddelande** och välj sedan **Meddelande**.
1. I dialogrutan **Meddelande** lägg till text och länkar för säljinnehåll och välj sedan **OK**.
1. I egenskapsfönstret för modulen **Cookie-samtycke** lägg till och konfigurera text och en länk till webbplatsens sekretesspolicy.
1. I platsen för rubrikmodul väljer du **Navigeringsmeny**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** välj modulen **Navigeringsmeny** och sedan **OK**.
1. I egenskapsrutan för modulen navigeringsmeny under **källa för navigeringsmeny**, väljer du **butiksserver**.
1. I egenskapspanelen för navigeringsmenymodulen under **Statiska menyobjekt**, välj **Lägg till menyobjekt** och välj sedan **Menyobjekt**. 
1. I dialogrutan **Menyobjekt** under **Menyobjekttext** ange "kontakt."
1. I dialogrutan **Menyobjekt** under **Länkmål för menyobjekt** välj **Lägg till en länk**.
1. I dialogrutan **Lägg till en länk** väljer du URL för webbplatsens sida "Kontakter" och välj sedan **OK**.  
1. I dialogrutan **Menyobjekt** väljer du **OK**.
1. I platsen för rubrikmodul väljer du **Sök**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Sök** och klicka sedan på **OK**.
1. Konfigurera egenskaperna efter behov i egenskapsfönstret för sökmodulen.
1. I platsen för rubrikmodul väljer du **Kundvagnsikon**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Kundvagnsikon** och klicka sedan på **OK**.
1. Konfigurera egenskaperna efter behov i egenskapsfönstret för modulen för kundvagnsikon. Om du vill att kundvagnsikonen ska visa en kundvagnssammanfattning (även kallad en minikundvagn) när användarna hovrar över den väljer du **Visa minikundvagnen**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.

Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.

1. På platsen **Rubrik** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Modul med kampanjbanderoll](add-alert.md)

[Modulen navigeringsmeny](nav-menu-module.md) 

[Cookie-medgivande](cookie-consent-module.md)

[Modul för sidfot](author-footer-module.md)

[Modul för webbplatsväljare](site-selector.md)

[Modul för butiksväljare](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
