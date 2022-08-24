---
title: Modul för val av land/region
description: Denna artikel beskriver plockmodul för land/region och beskriver hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 203a8e17e075f15b7ae3cceb98d24ced75539a01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270302"
---
# <a name="countryregion-picker-module"></a>Modul för val av land/region

[!include [banner](includes/banner.md)]

Denna artikel beskriver plockmodul för land/region och beskriver hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.

I modulen för val av land/region används funktionen [geografisk identifiering och omdirigering](geo-detection-redirection.md) i Dynamics 365 Commerce för att visa rekommenderade webbplatser för kunder som begär en näthandelsplats-URL som inte är associerad med deras land eller region.

En kund i Kanada begär till exempel en webbadress (URL) som är associerad med ett annat land än Kanada. I det här fallet innehåller modulen för val av land/region en dialogruta där webbplats-URL-adresser som är associerade med Kanada rekommenderas. 

## <a name="how-it-works"></a>Hur det fungerar

När geografisk identifiering och omdirigering aktiveras för en webbplats och en kund begär en URL till webbplatsen, används det land som upptäcks för kunden och den webbadress som dene begärt för att avgöra om webbadressen mappas till landet där kunden finns. Mappningen mellan URL-adresser och länder definieras på sidan **Kanaler** under **Webbplatsinställningar** i Commerce-webbplatsbyggaren. 

Om begärd URL inte matchar någon URL som är mappad till kundens land, returneras listan med en eller flera URL-adresser som är mappade till det landet i svaret. Väljaren för land/region jämför varje URL i den listan med de URL-adresser som har konfigurerats i lands-/regionmodulen. För varje exakt matchning som hittas visar väljaren för land/region visningsrubriken, underrubriken och bilden för URL:en, och hyperlänkar dessa element med hjälp av URL-adressen.

När en kund väljer ett alternativ i väljaren för land/region förs denne till den hyperlänkade URL-adressen. Denna URL har skrivits till webbplatscookien **\_msdyn365\_\_\_\_** så att den kan användas som kundens webbplatsinställning. Nästa gång kunden begär URL-adressen som inte är associerad med deras land eller region omdirigeras han eller hon automatiskt till önskat land. Därför rekommenderar vi att du även använder [väljarmodulen för webbplats](site-selector.md) på din näthandelsplats, detta så att kunderna kan åsidosätta eller uppdatera sin webbplatsinställning. 

Om en kund stänger dialogrutan för land-/regionval skrivs ingen cookie, och kunden förblir på aktuell webbplats. 

Följande bild visar ett exempel på dialogrutan för val av land/region.

![Exempel på en dialogruta för val av land/region på en startsida.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Egenskaper för modul för val av land/region

| Egenskapsnamn              | Värde       | beskrivning                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Rubrik                    | Text        | Rubriken som visas högst upp i dialogrutan.       |
| Underrubrik                 | Text        | Underrubriken som visas under rubriken.               |
| Land: Visningssträng    | Text        | Visningsnamnet för ett URL-alternativ (till exempel "Kanada").   |
| Land: Visningsdelsträng | Text        | En valfri visningsdelsträng för ett URL-alternativ (till exempel "engelska" eller "franska"). |
| Land: bild av land     | Medietillgång | En valfri bild som är kopplad till ett URL-alternativ (till exempel en bild av kanadensiska flagga). |
| Land: lands-URL       | Text        | Webbadressen för det land/den region som konfigureras. Denna URL måste exakt matcha den URL du angett för landet/regionen på sidan **Kanaler** under **Webbplatsinställningar** Commerce-webbplatsbyggaren. Webbadressens domän måste vara den anpassade domän som angetts i fältet **Matchande domän** på sidan **Kanaler**, inte den aktiva adressen för den webbplats som Commerce tillhandahåller när du skapar din näthandelsmiljö (till exempel webbadressen `https://<yourcompany>.commerce.dynamics.com/`). |
| Åtgärdslänk                | Åtgärdslänk | En valfri länk som visas längst ned i dialogrutan. Den här länken kan till exempel peka på en intern sida med en lista över alla länder och regioner som webbplatsen stöder. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Lägga till en modul för val av land/region på en sida

Modulen för val av land/region kan läggas till i huvudmodulen antingen direkt eller via ett delat fragment. Mer information om huvudmoduler finns i [Modul för sidhuvud](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Konfigurera modul för val av land/region i Commerce-webbplatsbyggaren

> [!NOTE]
> De URL-adresser som du rekommenderar till dina kunder måste konfigureras som landsobjekt i modulen för val av land/region.

Följ stegen nedan i webbplatsbyggaren för Commerce för respektive URL som du vill visa och rekommendera till kunderna.

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
