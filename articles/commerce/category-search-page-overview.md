---
title: Översikt över standardkategorilandningssida och sida för sökresultat
description: Denna artikel ger en överblick över målsidan för standardkategori och sökresultatsida i Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/30/2020
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
ms.openlocfilehash: 1f2e4eb8825dd690f926f7f0bdfc39f1eb5fb83c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276384"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Översikt över standardkategorilandningssida och sida för sökresultat

[!include [banner](includes/banner.md)]

Denna artikel ger en överblick över målsidan för standardkategori och sökresultatsidan i Microsoft Dynamics 365 Commerce.

## <a name="default-category-landing-page"></a>Standardlandningssida för kategori

Standardlandningssidan för kategori är den sida som webbplatsanvändarna normalt använder när de väljer en kategori i navigeringshierarkin. På kategorisidan kan du bläddra och du kan också sortera och justera de kategoriserade produkterna.

![Standardlandningssida för kategori.](./media/SimpleCategoryLandingDressCategory.png)

Den övre delen av startsidan har en rubrik som visar alla produktkategorier och andra sidor som inköpschefen har kategoriserat. Konfigurationen görs som en del av konfigurationen av kanalens navigeringshierarki. Sidans nedre del har en sidfot som innehåller snabblänkar till olika artiklar som kan vara intressanta för köpare.

Följande komponenter är nödvändiga för en kategori:

- **Produkt placeringspaneler** visar de produkter som inköpschefen har definierat i en kategori som en del av konfigurationen av navigeringshierarkin.
- **Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar. Inköpschefen konfigurerar dem som en del av konfigurationen av metadata som är relaterade till kanalkategorier och produktattribut.
- **Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna. Som standard är följande sorteringsalternativ tillgängliga:

    - Pris – lågt till högt
    - Pris – högt till lågt
    - Produktnamn – \[A-Ö\]
    - Produktnamn – \[Ö-A\]
    - Värderingar – låg till hög
    - Värderingar – hög till låg

- **Avancerade sorteringsalternativ** används av besökare på webbplatsen för att sortera produkterna med intelligenta kriterier. Genom att aktivera: [Produktrekommendationer](product-recommendations.md) är följande sorteringsalternativ tillgängliga. Mer information finns i artikeln [Typer av produktrekommendationer](product-recommendations.md#types-of-product-recommendations).

    - Nya
    - Bästsäljare
    - Trend

- **Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.
- **Totalt antal** anger det totala antalet produkter som har definierats i en kategori.

## <a name="enrich-a-category-landing-page"></a>Utöka en kategorilandningssida

Om du vill att en kategorilandningssida ska ha en mer skräddarsydd upplevelse för en viss kategori, kan du "utöka" kategorilandningssidan för den kategorin. Du kan till exempel lägga till en marknadsföringsvideo och vissa kategoriberättande för att få köparens uppmärksamhet. Mer information finns i [utöka en kategorilandningssida](enrich-category-page.md).

![Utökad kategorilandningssida.](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Automatiskt föreslå och sökresultatsidor

Webbplatsanvändare kan utforska en webbplats antingen genom att gå till en kategori från navigeringshierarkin eller genom att ange en sökterm i sökfältet.

Så snart användarna börjar skriva i sökfältet, kommer de att uppleva de fördjupade automatiska förslag som föreslår söktermer.

Här följer några av de typer av förslag som kan visas:

- **Nyckelord** används för att hitta artiklar i alla produkter som är utvalda för kanalen.
- **Produkter** tillhandahåller direktlänkar till sidan med produktinformation.
- **Omfattningsförslag för kategorisökning** anger olika kategorier och låter användare söka efter nyckelordet i en viss kategori.

![Integrerade automatiska förslag.](./media/ImmersiveAutoSuggestUX.png)

När användarna väljer ett av nyckelorden eller omfattande förslagen på kategorisökning, eller när det inte finns några förslag på sökvillkoren som de anger, omdirigeras de till en sökresultatsida. Användarna kan sedan bläddra, sortera och finjustera listan med sökresultat för att hitta önskad artikel.

![Landningssida för sökning.](./media/SearchLanding.png)

Följande komponenter är nödvändiga för en sökresultatsida:

- **Produktplaceringspaneler** visar produkterna för användarens sökning. Som standard sorteras dessa paneler efter den molndrivna sökrelevans som används för användarsökningen.
- **Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar. Inköpschefen konfigurerar dem som en del av konfigurationen av metadata för "kanalkategorier och produktattribut".
- **Standard sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna. Som standard är följande sorteringsalternativ tillgängliga:

    - Pris – lågt till högt
    - Pris – högt till lågt
    - Produktnamn – \[A-Ö\]
    - Produktnamn – \[Ö-A\]
    - Värderingar – låg till hög
    - Värderingar – hög till låg
    - Standardvärde 
    
    > [!NOTE]
    > Om värden för **Visningsordning** definieras för produkterna i navigeringshierarki, sortering som standard på en kategorisida respekterar de värden som definieras i **Visningsordning**. I annat fall sorteras sorteringen efter **produktnummer**.)
    
- **Avancerade sorteringsalternativ** används av besökare på webbplatsen för att sortera produkterna med intelligenta kriterier. Genom att aktivera: [Produktrekommendationer](product-recommendations.md) är följande sorteringsalternativ tillgängliga. Mer information finns i artikeln [Typer av produktrekommendationer](product-recommendations.md#types-of-product-recommendations).

    - Nya
    - Bästsäljare
    - Trend

- **Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.
- **Totalt antal** anger det totala antalet produkter som har definierats i en kategori som matchar sökkriterierna.

>[!NOTE]
>De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8. Se till att under **Handelsparametrar > Konfigurationsparametrar** finns en post för "ProductSearch.UseAzureSearch inställd på true". 
![Konfigurationsparametrar för molndriven sökning.](./media/CloudPoweredSearchConfigurationParameters.png)

>Om du vill använda avancerade sorteringsalternativ, till exempel nya, mest sålda och populära måste du aktivera [produktrekommendationer](product-recommendations.md) för din miljö. Avancerade sorteringsalternativ finns i Commerce SDK version 9.35+ och Handel version 10.0.20.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över molnbaserade sökningar](cloud-powered-search-overview.md)

[Översikt över startsidan](quick-tour-home-page.md)

[Översikt över sidor med produktinformation](quick-tour-pdp.md)

[Översikt över sidor för kundvagn och kassa](quick-tour-cart-checkout.md)

[Översikt över sidor för kontohantering](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
