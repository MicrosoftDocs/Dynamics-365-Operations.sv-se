---
title: Översikt över molnbaserade sökningar
description: Denna artikel ger en översikt över den molnbaserade sökningen i Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273677"
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

Sorteringsfunktioner möjliggör att kunderna sorterar, söker och bläddrar i kategoriresultat och justera dem efter kriterier, t.ex. pris, produktnamn och produktnummer. Om du aktiverar [produktrekommendationer](product-recommendations.md) i din miljö kan kunderna också sortera resultaten utifrån avancerade sorteringskriterier som ny, säljande och populär.


> [!NOTE]
> De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8. Se till att det finns en post för "ProductSearch.UseAzureSearch" märkt "true" i **Commerce Parameters > Configuration Parameters**. 
![Konfigurationsparametrar för molndriven sökning.](./media/CloudPoweredSearchConfigurationParameters.png)
>Avancerade sorteringsalternativ som nya, mest sålda och trendade alternativ finns i Commerce SSK-versionen 9.35+ och Dynamics 365 Commerce 10.0.20 utgåva.  


## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Hantera SEO-metadata](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
