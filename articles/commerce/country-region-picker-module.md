---
title: Modul för val av land/region
description: Det här avsnittet beskriver modul för val av land/region och beskriver hur du konfigurerar i Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 1a8eebb589372051272573895a0ae5b4203eef62
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109791"
---
# <a name="countryregion-picker-module"></a>Modul för val av land/region

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver modul för val av land/region och beskriver hur du konfigurerar i Microsoft Dynamics 365 Commerce.

I modulen för val av land/region används funktionen [geografisk identifiering och omdirigering](geo-detection-redirection.md) i Dynamics 365 Commerce för att visas rekommenderade URL:er för kunder som begär en näthandelsplats-URL som inte är associerad med deras land eller region.

En kund i Kanada begär till exempel en webbadress som inte är associerad med Kanada. I det här fallet innehåller modulen för val av land/region en dialogruta där webbplats-URL-adresser som är associerade med Kanada rekommenderas. Följande bild visar ett exempel på dialogrutan för val av land/region.

![Exempel på en dialogruta för val av land/region på en startsida.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Egenskaper för modul för val av land/region

| Egenskapsnamn              | Värde       | beskrivning |
| -------------------------- | ----------- | ----------- |
| Rubrik                    | Text        | Rubriken som visas högst upp i dialogrutan. |
| Underrubrik                 | Text        | Underrubriken som visas under rubriken. |
| Land: Visningssträng    | Text        | Visningsnamnet för ett URL-alternativ (till exempel "Kanada"). |
| Land: Visningsdelsträng | Text        | En valfri visningsdelsträng för ett URL-alternativ (till exempel "engelska" eller "franska"). |
| Land: bild av land     | Medietillgång | En valfri bild som är kopplad till ett URL-alternativ (till exempel en bild av kanadensiska flagga). |
| Land: lands-URL       | Text        | URL-adressen som motsvarar den kanal och det språk som har konfigurerats för landet eller regionen på sidan **Kanaler** i Commerce-webbplatsbyggaren (**Webbplatsinställningar \> Kanaler**). Denna URL måste exakt matcha URL:en som konfigurerats på sidan **Kanaler**. |
| Åtgärdslänk                | Åtgärdslänk | En valfri länk som visas längst ned i dialogrutan. Den här länken kan till exempel peka på en intern sida med en lista över alla länder och regioner som webbplatsen stöder. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Lägga till en modul för val av land/region på en sida

Modulen för val av land/region kan läggas till i huvudmodulen antingen direkt eller via ett delat fragment. Mer information om huvudmoduler finns i [Modul för sidhuvud](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Konfigurera modul för val av land/region i Commerce-webbplatsbyggaren

> [!NOTE]
> De URL-adresser som du rekommenderar till dina kunder måste konfigureras som landsobjekt i modulen för val av land/region.

Följ stegen nedan i Commerce-webbplatsbyggaren för varje URL som du vill visa och rekommendera till kunderna.

1. Välj platsen för modul för val av land/region.
1. Välj **Lägg till land** under **Landslista** i egenskapsrutan.
1. Välj den nya rutan **Land**.
1. Ange ett visningsnamn i fältet **Visningssträng** (till exempel **Kanada**).
1. Valfritt: I fältet **Visningsdelsträng** anger du en visningsdelsträng (till exempel **franska** eller **fr-ca**).
1. Valfritt: Välj en bild från mediebiblioteket.
1. Ange URL:en i fältet **Lands-URL**. Denna URL måste exakt matcha URL:en som visas på sidan **Kanaler** och är mappad till kanalen, inklusive det språk som är associerat med landet eller regionen.
1. Välj **OK**.
1. Upprepa de här stegen för alla andra lands-URL:er som du vill att modulen för val av lands/region ska visa.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera geografisk identifiering och omdirigering](geo-detection-redirection.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[Rubrikmodul](author-header-module.md)

[Webbplatsväljarmodul](site-selector.md)

[Modul för navigeringssökväg](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
