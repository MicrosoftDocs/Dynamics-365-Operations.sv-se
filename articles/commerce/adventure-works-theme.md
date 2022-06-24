---
title: Temaöversikt för Adventure Works
description: Denna artikel innehåller en översikt över Adventure Works-temat och en beskrivning av hur detta tillämpas på webbplatssidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4f13d6c1c4b0e2764c22dc3d7311c726fac7989d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874997"
---
# <a name="adventure-works-theme-overview"></a>Temaöversikt för Adventure Works

[!include [banner](includes/banner.md)]

Denna artikel innehåller en översikt över Adventure Works-temat och en beskrivning av hur detta tillämpas på webbplatssidorna i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce har ett tema för näthandel som kallas Adventure Works. Adventure Works-temat framhäver sport- och fritidsprodukter och är optimerat för en innehållsrik och förbättrad berättandeupplevelse. Det ger ett modernt utseende, nya layouter och animationseffekter när du vill skapa en uppslukande, djup shoppingupplevelse online för näthandelskunder.

## <a name="trial-environments-in-commerce"></a>Utvärderingsmiljöer i Commerce

Om du vill se hur Adventure Works-tema ser ut när det distribueras för B2C (Business-to-consumer) och B2B-webbplatser (business-to-business) besöker du följande utvärderingssidor:

- [Adventure Works B2C-webbplats](https://www.adventure-works.com/)
- [Adventure Works B2B-webbplats](https://www.adventure-works.com/business)

## <a name="theme-capabilities"></a>Tema-funktioner

Temat Adventure Works ger följande nya funktioner:

- Videospelarmodulen stöder nu rubrik-, styckes- och länkfunktioner för ytterligare berättande.
- Det finns bättre innehållsomställning genom animeringen.
- Åtgärden Lägg till i kundvagnen anropar minikundvagnen istället för att ange ett meddelande.
- Snabbvisningsmodulen är ett fönster som används i såväl stationära som mobila vyer.
- Det finns nya layouter för webbplatssidorna. 
- Marknadsföringsinnehåll kan konfigureras för vagnen och minivagnen när de är tomma.
- I vagnen kan du visa kampanjmeddelanden som "Gratis frakt på order över $50."
- Beskrivningskort visas på sök- och kategorisidor.

Temat Adventure Works innehåller följande moduler i modulbiblioteket i Commerce:

- [Panellistemodul](tile-list-module.md)
- [Interaktiv funktionsmodul](interactive-feature-module.md)
- [Aktiv bildmodul](active-image-module.md)
- [Prenumerationsmodul](subscribe-module.md)
- [Bildlistemodul](image-list-module.md)

Temat Adventure Works är ytterst responsivt och ger dig en optimerad upplevelsevy för datorer, mobiler och surfplattor.

> [!IMPORTANT]
> Adventure Works-temat och de nya modulerna finns tillgängliga från och med Dynamics 365 Commerce-version 10.0.20.

I följande illustration visas ett exempel på en startsida där temat Adventure Works används.

![Exempel på en startsida där temat Adventure Works används](./media/aw_b2c.PNG)

I följande illustration visas ett exempel på en listsida där temat Adventure Works används.

![Exempel på en listsida där temat Adventure Works används](./media/Aw_list.PNG)

I följande illustration visas ett exempel på en produktdetaljsida (PDP) där temat Adventure Works används.

![Exempel på en produktdetaljsida (PDP) där temat Adventure Works används](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Använd Adventure Works-tema för B2B-webbplatser

Adventure Works-temat är också ett referenstema för B2B-webbplatser (business-to-business). Alla B2B-moduler och -arbetsflöden presenteras i ett Adventure Works-tema. Information om hur du konfigurerar en B2B-webbplats finns i [Konfiguration för B2B-webbplats](./b2b/set-up-b2b-site.md).

I följande illustration visas ett exempel på en B2B-startsida där temat Adventure Works används.

![Exempel på en B2B-startsida där temat Adventure Works används](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Tematillägg

Adventure Works-temat innehåller flera tematillägg, till exempel tilläggen **Visningstillägg** och **Moduldefinition**. Adventure Works-temat kan användas som referenstema för att bygga liknande tillägg. Listsidan i Adventure Works-temat har till exempel implementerats som ett visningstillägg med en vågrät förbättring. (Som motsats används en förbättring för det vänstra fönstret i Fabrikam-temat.)

På samma sätt innefattar andra moduler moduldefinitionstillägg. [Modulen för kundvagnsikon](cart-icon-module.md) omfattar till exempel två extra platser för **Kundvagnen är tom** samt **Kampanjinnehåll** som implementeras genom att använda tillägg för moduldefinition. Dessutom har en ny egenskap för **Mobillogotyp** lagts till i sidhuvudmodulen som stöd för en logotyp på mobila visningsområden. Denna egenskap implementeras som ett definitionstillägg för sidhuvudmodulen.

Mer information om tematillägg finns i [Tematillägg](e-commerce-extensibility/theme-module-extensions.md).

## <a name="install-the-adventure-works-theme"></a>Installera Adventure Works-tema

Information om hur du installerar tema Adventure Works finns i [Installera temat Adventure Works](install-adventure-works.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Panellistemodul](tile-list-module.md)

[Interaktiv funktionsmodul](interactive-feature-module.md)

[Aktiv bildmodul](active-image-module.md)

[Prenumerationsmodul](subscribe-module.md)

[Bildlistmodul](image-list-module.md)

[Tematillägg](e-commerce-extensibility/theme-module-extensions.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Konfigurera en näthandelsplats för B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
