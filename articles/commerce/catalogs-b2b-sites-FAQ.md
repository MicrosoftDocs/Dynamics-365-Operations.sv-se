---
title: Commerce-kataloger för Vanliga frågor och svar om B2B
description: Denna artikel ger svar på vanliga frågor om Microsoft Dynamics 365 Commerce-kataloger.
author: ashishmsft
ms.date: 07/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 68c648c5caf2667f413b236dc437fc2c74c40d07
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168996"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Commerce-kataloger för Vanliga frågor och svar om B2B

[!include [banner](includes/banner.md)]

Denna artikel ger svar på vanliga frågor om Microsoft Dynamics 365 Commerce [B2B-kataloger (business-to-business)](catalogs-b2b-sites.md).

### <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Varför kan jag inte konfigurera en katalogspecifik navigeringshierarki eller se ett alternativ att koppla en kundhierarki?

Säkerställ att funktionen **Aktivera användning av flera kataloger i butikskanaler** är aktiverad på arbetsytan **Funktionshantering** i Commerce headquarters, samt att din miljö är Commerce-version 10.0.27 eller senare. Kontrollera att du har valt **B2B** under **Katalogtyp**.

### <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Kan jag visa den katalogspecifika hierarkin och kategorisidorna i Commerce-webbplatsverktyget?

Ja, användare av Commerce-webbplatsverktyget som har tillgång till sidan **Produkter** i webbplatsverktyget kan välja en katalog och visa den katalogspecifika hierarkin. Från sidan **Produkter** kan användarna också se en kategorisida för en viss kategori i katalogen. Mer information finns i [utöka en kategorilandningssida](enrich-category-page.md). Om du vill ha en specifik navigeringshierarki som gäller för en katalog rekommenderar vi att du har en unik och unik navigeringshierarki för katalogen.

### <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Kan en B2B-köpare göra inköp från flera kataloger i en enda kassa?

Ja köp från flera kataloger i en enda kassa är tillåtet. B2B-köpare kan använda katalogindikatorn i vagnen för att ta reda på vilka artiklar som har lagts till i vilka kataloger.

### <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Om en B2B-köpare handlar samma artikel från olika kataloger, hur ser det ut då?

Även om en viss användare kanske har tillgång till flera kataloger vid en viss tidpunkt, är det avse att produkter i dessa kataloger är ömsesidigt uteslutande. Med andra ord bör samma produkt inte ingå i mer än en katalog för en viss användare.

Om en situation uppstår där samma produkt tillhör flera kataloger kommer systemet att underhålla flera vagnrader för den produkten. Det kommer att finnas en separat rad för varje katalog. Samma produkt från två olika kataloger kopplas inte när du checka ut.

### <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>När en B2B-köpare handlar, finns det någon validering av katalogtillgänglighet?

Ja. En B2B-köpare kommer endast att kunna gå till kassan om alla artiklar i vagnen kommer från giltiga kataloger. Om några kundvagnsartiklar kommer från utgångna eller ifall katalogerna har förfallit, tas de bort och användaren meddelas.

### <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Är sökning och produktinsamling (inklusive relaterade och rekommenderade produktsamlingar) katalogspecifika under shoppingupplevelsen?

Ja. Så snart en användare har valt en viss katalog blir hela shoppingen katalogspecifik. Denna upptäckt av produkter innefattar bland annat sökförslag, sökresultat, kategoriresultat, rekommendationer, priser, attribut och rekommenderade produkter (till exempel nya, mest sålda, populära, ofta köpta tillsammans och relaterade produkter).

### <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Kan ett B2B-köpare handla från standardsortimentet (catalogID=0)?

Nej, en B2B-köpare får inte handla från standardsortimentet. Det sortimentet är endast avsett för anonym webbsökning. Om en B2B-köpare saknar katalogtilldelningar (i väntan på uppdateringar från deras administration), kommer de inte att kunna se några kataloger som de kan välja mellan, och ingen kategorihierarki kommer att vara synlig.

### <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>Kan marknadsföringsinnehåll granskas för en produkt som är specifik för en katalog?

För närvarande stöds produktberikande endast på webbplats- och kanalnivå. Med andra ord: Om en produkt är berikad och delas över flera kataloger, kommer motsvarande berikade produktinformationssida (PDP) för den produkten att återges på samma sätt i alla kataloger för en viss webbplats. 

### <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>Har katalogsupport för både B2B- (business-to-consumer) och B2C-onlinekanaler (business-to-consumer)?

Commerce-kataloger är för närvarande endast avsedda för B2B-onlinekanaler.

### <a name="a-new-customer-was-added-to-the-customer-hierarchy-or-a-new-hierarchy-was-associated-with-the-catalog-but-the-catalog-is-not-available-to-the-user-why"></a>En ny kund har lagts till i kundhierarkin, eller också har en ny hierarki kopplats till katalogen, men katalogen är inte tillgänglig för användaren. Varför?

Kontrollera att du körde **1010**-jobb efter att du kopplat den nya kunden till en befintlig kundhierarki samt när du skapade den nya kundhierarkin. Katalogerna som är kopplade till kundhierarkin visas bara när **1010**-jobbet har slutförts. Om katalogen också är ny måste du kontrollera att du har kört **1150**-(katalog)jobbet samt **1010**-jobben. Precis som med alla nya kataloger bör du låta datan synkroniseras till kanalen och sökindexet. Om ett jobb har statusen "Verkställt" ("Applied") innebär det att datan synkroniseras till kanaldatabasen, men att ytterligare tid krävs för att datan ska synkroniseras till sökindexet. 

### <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Kan vi konfigurera katalogspecifika mer-/korsförsäljningsartiklar?

För närvarande stöds endast funktioner för relaterade produkter. Däremot är artikelkonfigurationer för merförsäljning och korsförsäljning tillgängliga för kundtjänster.

Följande funktioner stöds bara för kundtjänster:

- Katalog källkoder
- Använd käll-ID för att spåra kostnader och svarsfrekvenser
- Katalogspecifik order och artikelskript
- Katalogsidaanalys
- Katalogförfrågningar
- Betalningstidsplaner
- Gratisprodukter baserade på källkoder

### <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Kan vi använda katalogkällkoder för B2B-order via näthandelsportalen?

Nej Katalogkällkoder stöds bara för kundtjänstkanaler.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa handelskataloger för B2B-webbplatser](catalogs-b2b-sites.md)

[Katalogväljarmodul](catalog-picker.md)

[Utvidgningar av handelskataloger för B2B-anpassningar](catalogs-b2b-sites-dev.md)
