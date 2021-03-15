---
title: Översikt över standardkategorilandningssida och sida för sökresultat
description: Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2a7eab8e7f5d300930f8a093afff2d848d8a2db7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997859"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Översikt över standardkategorilandningssida och sida för sökresultat

[!include [banner](includes/banner.md)]

Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Microsoft Dynamics 365 Commerce.

## <a name="default-category-landing-page"></a>Standardlandningssida för kategori

Standardlandningssidan för kategori är den sida som webbplatsanvändarna normalt använder när de väljer en kategori i navigeringshierarkin. På kategorisidan kan du bläddra och du kan också sortera och justera de kategoriserade produkterna.

![Standardlandningssida för kategori](./media/SimpleCategoryLandingDressCategory.png)

Den övre delen av startsidan har en rubrik som visar alla produktkategorier och andra sidor som inköpschefen har kategoriserat. Konfigurationen görs som en del av konfigurationen av kanalens navigeringshierarki. Startsidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för köpare.

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

- **Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.
- **Totalt antal** anger det totala antalet produkter som har definierats i en kategori.

## <a name="enrich-a-category-landing-page"></a>Utöka en kategorilandningssida

Om du vill att en kategorilandningssida ska ha en mer skräddarsydd upplevelse för en viss kategori, kan du "utöka" kategorilandningssidan för den kategorin. Du kan till exempel lägga till en marknadsföringsvideo och vissa kategoriberättande för att få köparens uppmärksamhet. Mer information finns i [utöka en kategorilandningssida](enrich-category-page.md).

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Automatiskt föreslå och sökresultatsidor

Webbplatsanvändare kan utforska en webbplats antingen genom att gå till en kategori från navigeringshierarkin eller genom att ange en sökterm i sökfältet.

Så snart användarna börjar skriva i sökfältet, kommer de att uppleva de fördjupade automatiska förslag som föreslår söktermer.

Här följer några av de typer av förslag som kan visas:

- **Nyckelord** används för att hitta artiklar i alla produkter som är utvalda för kanalen.
- **Produkter** tillhandahåller direktlänkar till sidan med produktinformation.
- **Omfattningsförslag för kategorisökning** anger olika kategorier och låter användare söka efter nyckelordet i en viss kategori.

![Integrerade automatiska förslag](./media/ImmersiveAutoSuggestUX.png)

När användarna väljer ett av nyckelorden eller omfattande förslagen på kategorisökning, eller när det inte finns några förslag på sökvillkoren som de anger, omdirigeras de till en sökresultatsida. Användarna kan sedan bläddra, sortera och finjustera listan med sökresultat för att hitta önskad artikel.

![Landningssida för sökning](./media/SearchLanding.png)

Följande komponenter är nödvändiga för en sökresultatsida:

- **Produktplaceringspaneler** visar produkterna för användarens sökning. Som standard sorteras dessa paneler efter den molndrivna sökrelevans som används för användarsökningen.
- **Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar. Inköpschefen konfigurerar dem som en del av konfigurationen av metadata för "kanalkategorier och produktattribut".
- **Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna. Som standard är följande sorteringsalternativ tillgängliga:

    - Pris – lågt till högt
    - Pris – högt till lågt
    - Produktnamn – \[A-Ö\]
    - Produktnamn – \[Ö-A\]
    - Värderingar – låg till hög
    - Värderingar – hög till låg
    - Standardvärde

- **Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.
- **Totalt antal** anger det totala antalet produkter som har definierats i en kategori som matchar sökkriterierna.

>[!NOTE]
>De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8. Se till att under **Handelsparametrar > Konfigurationsparametrar** finns en post för "ProductSearch.UseAzureSearch inställd på true". 
![Konfigurationsparametrar för med molndriven sökning](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över molnbaserade sökningar](cloud-powered-search-overview.md)

[Översikt över startsidan](quick-tour-home-page.md)

[Översikt över sidor med produktinformation](quick-tour-pdp.md)

[Översikt över sidor för kundvagn och kassa](quick-tour-cart-checkout.md)

[Översikt över sidor för kontohantering](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]