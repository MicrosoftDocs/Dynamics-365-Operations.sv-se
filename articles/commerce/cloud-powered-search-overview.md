---
title: Översikt över molnbaserade sökningar
description: Det här ämnet ger en översikt över den molnbaserade sökningen i Microsoft Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00a3de2515cea341f7529b8cb6cb2caae5e33d22
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415709"
---
# <a name="cloud-powered-search-overview"></a>Översikt över molnbaserade sökningar


[!include [banner](includes/banner.md)]

Det här ämnet ger en översikt över den molnbaserade sökningen i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Produktidentifiering garanterar att kunder snabbt och enkelt kan hitta produkter genom att bläddra bland kategorier, söka och filtrera. Återförsäljare betraktar produktidentifiering som ett primärt verktyg för kundinteraktion i alla kanaler.

Kunderna är vana vid de nästan ögonblickliga svarstiderna för sökmotorer på webben, avancerade näthandelsplatser, sociala appar, automatiska förslag som visas som söktermer, inblandad navigering och markeringar. Om kunderna inte hittar produkten som de letar efter tillräckligt snabbt i en nätbutik tvekar de inte att gå vidare till en annan nätbutik.

Den molnbaserade produktidentifieringen i Dynamics 365 Commerce hjälper återförsäljare att fortsätta att öka konsumenternas lagrings- och konverteringskurser över alla kanaler, både näthandelskanaler och kassakanaler (POS).

Dynamics 365 Commerce sökfunktion har förbättrade funktioner som hjälper återförsäljare att uppnå bättre produktidentifiering. På samma gång ger dessa funktioner den skalbarhet och prestanda som krävs för näthandelstrafiken.

## <a name="browse-and-search"></a>Bläddra och sök

Sökrelevans och prestanda är viktiga faktorer i flerkanalsupplevelse, eftersom produktidentifiering huvudsakligen är en sökfunktion för hämtning av information och innehållsnavigering. En effektiv bläddrings- och sökupplevelse hjälper till att öka konverteringen.

I bilden nedan visas ett exempel på vanliga funktioner för bläddring och sökning.

![Landningssida för sökning](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Facetterad navigering och valöversikt 

Med facetterad navigering kan kunderna lättare bläddra efter innehåll genom att filtrera dem på förfinare som är länkade till termer i en termuppsättning. När en kund har valt och tillämpat förfinare visas en sammanfattning av alternativen. 

Genom att använda facetterad navigering kan du konfigurera olika förfinare för olika termer i en termuppsättning, utan att behöva skapa fler sidor. 

I bilden nedan visas ett exempel där uppblandning av navigering används vid en sökning.

![Valöversikt](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Integrerade automatiska förslag

Aktuell automatisk förslagsfunktion visar bara nyckelord som utlöser en sökning efter det matchande nyckelordet. På grund av nya förbättringar i Dynamics 365 Commerce kunderna ofta upptäcka länkar till produkter innan de har skrivit klart.

Dynamics 365 Commerce stöder också funktioner för nyckelordsmatchningar i olika kategorier. Den här funktionen gör att kunder kan se antalet matchande nyckelord i olika kategorier och utlösa en sökning efter ett nyckelord i andra kategorier.

Följande illustration visar ett exempel där integrerade automatiska förslag används.

![integrerade automatiska förslag](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Sortera

Förbättrad sortering i Dynamics 365 Commerce låter kunderna sortera, söka och bläddra i sökresultat och justera dem efter kriterier, t.ex. pris, produktnamn och produktnummer. Kunder kan också sortera resultat baserat på om en produkt är ny, bästsäljare eller nyligen tillagd.

>[!NOTE]
>De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8. Se till att under **Handelsparametrar > Konfigurationsparametrar** finns en post för "ProductSearch.UseAzureSearch inställd på true". 
![Konfigurationsparametrar för med molndriven sökning](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Hantera SEO-metadata](manage-seo-metadata.md)
