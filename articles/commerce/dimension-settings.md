---
title: Använd visningsinställningar för produktdimensioner
description: I det här avsnittet beskrivs visningsinställningarna för produktdimensioner och hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117247"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Använd visningsinställningar för produktdimensioner

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I det här avsnittet beskrivs visningsinställningarna för produktdimensioner och hur du använder dem i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce stöder dimensioner för storlek, utförande och färg för att särskilja produktvarianter. Dimensioner visas vanligtvis som textvärden, till exempel "Small", "Medium" och "Large" för storlekar, och "Svart" och "Brunt" för färger. Om en produkt stöder många variationer kan det dock vara svårt att bläddra bland produktvarianter, eftersom flera val krävs för att visa bilden för varje variant. För att göra det enklare att bläddra i produktvarianter kan version 10.0.20-versionen av Commerce använda bilder och hexadecimala (hex)-koder för att visa dimensioner som tum.

I Commerce-webbplatsskaparen, definieras inställningar på **Platsinställningar \> Tillägg \> Dimensionsinställningar**. I följande bild visas ett exempel på dimensionsinställningar i webbplatsskaparen.

![Exempel på siteinställningar i Commerce webbplatsskaparen](./dev-itpro/media/swatch_site_settings.PNG)

Det finns två dimensionsinställningar:

- **Dimensioner som ska visas som bild** – Ange vilka dimensioner som ska visas som färgrutor på sidor med e-handelswebbplatser, t.ex. produktinformationssidor (PDP) och listor med sökresultat. Alla kombinationer av färg, storlek och stildimensioner kan visas som en färgruta. Om en dimension har valts för visning som en färgruta, kommer återgivning av Commerce-modul att leta efter en tillgänglig konfiguration av en hexkodsfärg. Om ingen hexkod konfigureras söker systemlogiken efter en konfiguration av en bild-URL konfiguration. Text visas om varken en hexkod eller en URL för bilden har konfigurerats.

    I följande bild visas ett exempel där en PDP på en e-handelswebbplats innehåller färg- och storleksrutor. I det här exemplet konfigureras en hexkod för färgdimensionen. Därför visas färgrutor som färger. Det går dock att konfigurera varken en hexkod eller en bild-URL för storleksdimensionen. Därför visas text.

    ![Exempel på färgdimensionen som visas som tum på en detaljsida för e-handelprodukt](./dev-itpro/media/swatch_pdp.png)

- **Dimensioner som ska visas på produktkort** – Ange vilka dimensioner som ska visas på produktkort som visas i listor och på listsidor. Innan en dimension kan visas på ett produktkort måste den här inställningen vara aktiverad för den dimensionen. Även inställningen **dimensionerna som ska visas som bild** bör vara aktiverade. Urvalssättet för färgrutor för produktkort optimeras för färgdimensionen. För andra dimensioner kan det krävas ett visningstillägg för att anpassa urvalsbeteendet.

    I följande bild visas ett exempel där en listsida på en e-handelsplats innehåller produktkort som innehåller färgrutor.

    ![Exempel på färgdimensionen som visas som tum på en listsida för e-handel](./dev-itpro/media/swatch_searchresults.PNG)

Mer information om hur du konfigurerar produktdimensioner så att de visas som färgrutor på webbplatssidor finns i [Konfigurera produktdimensionsvärden så att de visas som färgrutor](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Sökresultatmodul](search-result-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Konfigurera värden för produktdimensioner som ska visas som färgrutor](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
