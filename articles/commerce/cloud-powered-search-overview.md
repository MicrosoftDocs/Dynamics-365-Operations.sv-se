---
title: Översikt över molnbaserade sökningar
description: Denna artikel ger en översikt över den molnbaserade sökningen i Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8a3ab869eb9ddc0e73061bd2363cf9b3962da1e3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850366"
---
# <a name="cloud-powered-search-overview"></a>Översikt över molnbaserade sökningar

[!include [banner](includes/banner.md)]

Denna artikel ger en översikt över den molnbaserade sökningen i Microsoft Dynamics 365 Commerce.

Produktidentifiering garanterar att kunder snabbt och enkelt kan hitta produkter genom att bläddra bland kategorier, söka och filtrera. Återförsäljare anser att produktidentifiering utgör ett primärt verktyg för kundinteraktioner mellan kanaler som drivs via CSU (Cloud Scale Unit), såsom näthandel och kassa (POS).

Kunderna är vana vid de nästan ögonblickliga svarstiderna för sökmotorer på webben, avancerade näthandelssajter, sociala appar, automatiska förslag som visas som söktermer, inblandad navigering och markeringar. Om kunderna inte hittar produkten som de letar efter tillräckligt snabbt i en näthandelsbutik tvekar de inte att gå vidare till en annan näthandelsbutik.

Den molnbaserade produktidentifieringen i Commerce hjälper återförsäljare att fortsätta öka konsumenternas lagrings- och konverteringskurser över alla kanaler som drivs av CSU.

Commerce-sökfunktionen har förbättrade funktioner som hjälper återförsäljare att uppnå en bättre produktidentifiering. På samma gång ger dessa funktioner den skalbarhet och prestanda som krävs för näthandelstrafiken.

## <a name="browse-and-search"></a>Bläddra och sök

Sökrelevans och prestanda är viktiga faktorer i flerkanalsupplevelse, eftersom produktidentifiering huvudsakligen är en sökfunktion för hämtning av information och innehållsnavigering. En effektiv bläddrings- och sökupplevelse hjälper till att öka konverteringen.

I bilden nedan visas ett exempel på vanliga funktioner för bläddring och sökning.

![Landningssida för sökning.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Facetterad navigering och valöversikt 

Med facetterad navigering kan kunderna lättare bläddra efter innehåll genom att filtrera dem på förfinare som är länkade till termer i en termuppsättning. När en kund har valt och tillämpat förfinare visas en sammanfattning av alternativen. 

Genom att använda facetterad navigering kan du konfigurera olika förfinare för olika termer i en termuppsättning, utan att behöva skapa fler sidor. 

I bilden nedan visas ett exempel där uppblandning av navigering används vid en sökning.

![Valöversikt.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Integrerade automatiska förslag

Den nuvarande funktionen för aytomatiska förslag anger nyckelord som utlöser en sökning efter det matchande nyckelordet. På grund av nya förbättringar i Commerce kan kunderna oftaa länkar till produkter innan de har skrivit klart.

Commerce stöder också funktioner för nyckelordsmatchningar i olika kategorier. Den här funktionen gör att kunder kan se antalet matchande nyckelord i olika kategorier och utlösa en sökning efter ett nyckelord i andra kategorier.

Följande illustration visar ett exempel där integrerade automatiska förslag används.

![integrerade automatiska förslag.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Sortera

Förbättrad sortering i Commerce låter kunderna sortera, söka och bläddra bland sökresultat och justera dem efter kriterier såsom t.ex. pris, produktnamn och produktnummer. Kunder kan också sortera resultat baserat på om en produkt är ny, bästsäljare eller nyligen tillagd.

> [!NOTE]
> De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8. Se till att det finns en post för "ProductSearch.UseAzureSearch" märkt "true" i **Commerce Parameters > Configuration Parameters**. 
![Konfigurationsparametrar för molndriven sökning.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Hantera SEO-metadata](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
