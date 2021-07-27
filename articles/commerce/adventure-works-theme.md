---
title: Temaöversikt för Adventure Works
description: Detta ämne innehåller en översikt över Adventure Works-temat och en beskrivning av hur det tillämpas på webbplatssidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
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
ms.openlocfilehash: c7557a36a948de5ae877d74bbbdea78821099b82
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479537"
---
# <a name="adventure-works-theme-overview"></a>Temaöversikt för Adventure Works

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Detta ämne innehåller en översikt över Adventure Works-temat och en beskrivning av hur det tillämpas på webbplatssidorna i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce har ett tema för näthandel som kallas Adventure Works. Adventure Works-temat framhäver sport- och fritidsprodukter och är optimerat för en innehållsrik och förbättrad berättandeupplevelse. Det ger ett modernt utseende, nya layouter och animationseffekter när du vill skapa en uppslukande, djup shoppingupplevelse online för näthandelskunder.

Temat Adventure Works ger följande nya arbetsflöden:

- Videospelarmodulen stöder nu rubrik-, styckes- och länkfunktioner för ytterligare berättande.
- Åtgärden Lägg till i kundvagnen anropar minikundvagnen istället för att ange ett meddelande.
- Snabbvisningsmodulen är ett fönster som används i såväl stationära som mobila vyer.
- En tom kundvagn kan nu demonstrera kampanjerbjudanden.

Temat Adventure Works innehåller följande moduler i modulbiblioteket i Commerce:

- Panellistmodul
- Interaktiv funktionsmodul
- Prenumerationsmodul
- Aktiv bildmodul
- Bildlistmodul

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

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Panellistmodul](tile-list-module.md)

[Interaktiv funktionsmodul](interactive-feature-module.md)

[Aktiv bildmodul](active-image-module.md)

[Prenumerationsmodul](subscribe-module.md)

[Bildlistmodul](image-list-module.md)

[Tematillägg](e-commerce-extensibility/theme-module-extensions.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Konfigurera en näthandelsplats för B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
