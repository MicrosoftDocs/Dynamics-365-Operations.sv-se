---
title: Tillägg för Inventory Visibility – översikt
description: Denna artikel förklarar vad Lagersynlighet är och beskriver dess funktioner.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762818"
---
# <a name="inventory-visibility-add-in-overview"></a>Översikt över tillägg för Lagersynlighet

[!include [banner](../includes/banner.md)]

Tillägget för lagersynlighet (kallas även *tjänsten Lagersynlighet*) tillhandahåller en oberoende och mycket skalbar mikrotjänst som möjliggör aktuella lagerändringsposteringar i realtid och synlighetsspårning över alla dina datakällor och kanaler. Den innehåller en plattform där du kan hantera det globala lagret med hjälp av funktioner som innehåller (men inte begränsat till) följande lista:

- Spåra centralt den senaste lagerstatusen (som tillgänglig, beställd, köpt, under transport, returnerad och karantän) över alla dina datakällor, lager och platser genom att ansluta din Supply Chain Management eller tredjeparts logistikdatakällor ( såsom orderhanteringssystem, tredje parts företagsresursplanering \[ERP\]-system, kassa \[POS\] och lagerhanteringssystem) till tjänsten lagersynlighet.
- Fråga om lagerbehållning och underskott, och få omedelbara svar genom att ringa lagersynlighetstjänsten direkt.
- Undvik överförsäljning, särskilt när din efterfrågan kommer från olika kanaler, genom att göra mjuka reservationer i realtid i tjänsten lagersynlighet.
- Hantera utlovade beställningar och kundernas förväntningar bättre genom att tillhandahålla exakta aktuella eller nästa tillgängliga datum, så att funktionen flerkanal tillgängligt att lova (ATP) kan beräkna förväntade datum för orderuppfyllelse.

## <a name="extensibility"></a>Utbyggbarhet

Tjänsten Lagerhantering är mycket utökningsbar eftersom inmatning och utdata inte är begränsade till Microsoft-program. Externa system kan komma åt tjänsten via RESTful application programming interfaces (API). Förutom att använda de "fördefinierade"-mappningar som finns för datakällan och dimensionerna i Supply Chain Management, kan du integrera lagersynlighet med flera tredjepartssystem genom att konfigurera ytterligare datakällor, mått på lagerstatus (som kallas för *fysiska mått* i lagertjänst) och lagerdimensioner via konfigurationsprogrammet. På det här sättet kan du växla fråga och ändra flera datakällor och fördefinierade lagerdimensioner.

Eftersom lagersynligheten bygger på kan Microsoft Dataverse dess data dessutom användas för att bygga och integrera med Power Apps. Du kan också använda Power BI för att skapa anpassade instrumentpaneler som uppfyller dina affärskrav.

## <a name="scalability"></a>Skalbarhet

Tjänsten lagersynlighet kan skalas upp eller ned, beroende på datavolymen. Skalbarhetsupplevelsen är oftast sömlös och utförs av Microsofts plattformsteam, baserat på automatisk identifiering och bedömning av din transaktionsdatavolym.

Följande bild ger en översikt över ändringarna i lagersynlighet-arkitektur.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title="Lagersynlighet arkitektur" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>Funktionens höjdpunkter

### <a name="get-a-global-view-of-real-time-inventory"></a>Hämta en global vy över lager i realtid

Lagersynlighet garanterar att du alltid har tillgång till de senaste lagerkvantiteterna, i alla kanaler, platser och lagerställen. Det bästa är om du använder den för att stödja din dagliga verksamhet när du måste erhålla lagerposter. Fysisk lagerbehållning, sålda kvantiteter och inköpta kvantiteter är alla tillgängliga ur rutan. Du kan även konfigurera andra fysiska lagermått (t.ex. returnerade, i karantän och bokförda data) om du behöver, för att kunna visa dessa uppgifter i realtid. Lagersynlighet kan effektivt bearbeta flera miljoner lagerbytesposter. Dessa data kan aggregeras och återspeglas i de senaste lagerkvantiteterna på en gång, per sekund eller per minut, beroende på vilket intervall data har bokförts i. Mer information finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Central lagerjustering

Med lagersynlighet kan externa system anropa dess API för att bokföra lagerändringar. Ändringarna börjar gälla omedelbart i lagersynlighet. Därför dras lagerbehållningen omedelbart av.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Mjuk reservation för att undvika överbokning mellan alla orderkanaler

En *mjuk reservation* gör att du kan tilldela eller flagga specifika kvantiteter för att uppfylla en order eller efterfrågan. En mjuk reservation påverkar inte det fysiska lagret, men det drar av från *tillgänglig för reservation* lagerkvantitet och tillhandahåller en uppdaterad kvantitet för framtida orderuppfyllelse. Den här funktionen är användbar om försäljningsbegäranden eller -order kommer till ditt företag från en eller flera kanaler eller datakällor som finns utanför ditt system för postsystem för resursplanering (ERP).

Om du inte använder mjuk reservationer i tjänsten Lagersynlighet, måste du vänta tills ordern synkroniseras till och bearbetas av ERP-systemet för att få en uppdatering av den fysiska lagerkvantiteten. Den här processen har vanligtvis en stor tidsfördröjning. Mjuk reservationer kommer dock omedelbart att påverkas varje gång en försäljningsförfrågan eller order genereras i dina försäljningskanaler. Därför hjälper de till att förhindra överförsäljningssituationer genom att se till att dina flerkanalsorder inte stör varandra när de så småningom når ERP-systemet. Mjuk reservationer ser också till att du kan uppfylla alla order som du har utlovat. Därför hjälper de dig att uppfylla kundernas önskemål och behålla kundlojaliteten. Mer information finns i [Reservationer för Lagersynlighet](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Bekräftelser på omedelbart ATP kvantitet och datum

Synligheten i ditt framtida projekterade lager (inklusive leverans, efterfrågan och projekterade detaljer i lager) är viktigt eftersom det hjälper ditt företag att uppnå följande mål:

- Minimera lagernivåerna för att minska lagerhanteringskostnaderna.
- Underlätta bearbetning av interna order så att försäljare kan beräkna leverans- och leveransdatum, baserat på tillgängligheten för de produkter som beställts.
- Ge insyn i när kunder kan förvänta sig att en artikel som inte finns i lager blir tillgänglig via nästa tillgängliga datum.

ATP-funktionen är lätt att använda i din dagliga beställningsprocess. Viktigast av allt, precis som andra erbjudanden om lagersynlighet, är ATP-funktionen *global och realtid*. Därför kan du konfigurera flera ATP-beräkningsformler för att få fullständiga frågor om lagertillgänglighet som täcker alla dina affärskanaler och datakällor. Mer information finns i [Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>Förallokera ditt lager till viktiga kanaler eller kunder med lagerallokering

Med hjälp av allokeringsfunktionen lagersynlighet kan du skydda och spärra din värdefulla lagerbehållning för viktiga kanaler, kundgrupper eller platser. När lager har fördelats begränsas lagerförbrukningen till den allokerade poolen och de kvantiteter som finns kvar i poolen dras av i närtid för att återspegla den kvantitet som fortfarande är tillgänglig för förbrukning. Mer information finns i [Lagerallokering för Lagersynlighet](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Kompatibilitet med WMS-artiklar

Microsoft strävar efter att tillhandahålla färdig integrering med lagerstyrningsprocesser (WMS), detta så att WMS-kunder också kan dra nytta av fördelarna med lagersynlighetstjänsten. Enligt utgivningscykel 1 2022 (offentlig förhandsvisning i mars) stöder inventeringstjänsten WMS-förfrågningar och ATP. Den mjuka reservationen och allokeringsfunktionen stöds för WMS-kunder i nästa påfyllnad. Mer information finns i [Stöd för lagersynlighet för WMS-artiklar](inventory-visibility-whs-support.md).

I följande bild visas en sammanfattning på hög nivå över befintliga funktioner och hur de kan placeras i dataflödet.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title="Funktionen lagersynlighet – översikt" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Licensiering

Tjänsten Lagersynlighet är tillgänglig i följande versioner:

- **Tillägg för Lagersynlighet för Microsoft Dynamics 365 Supply Chain Management** – För företag som har en giltig Supply Chain Management-licens är lagersynlighet tillgängligt utan extra kostnad. Eftersom lagersynlighet baseras på Microsoft Power Platform det är föremål för Microsoft Power Platform lagringskapaciteten och API-gränser. Din licens för Supply Chain Management bör omfatta standardlagring och API-kapacitet. Om du behöver mer lagrings- och API-kapacitet kan du köpa en yrkeslicens. Mer information om standard-API-allokering och den professionella licensen finns i [Begär gränser och allokeringar](/power-platform/admin/api-request-limits-allocations) och [Licensöversikt för Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Med standardlager- och API-allokeringarna kan du börja testa tillägget lagersynlighet idag. Installationsdetaljer finns i [Installera och ställ in lagersynlighet](inventory-visibility-setup.md). Om din uppskattade API och lagringsanvändning överskrider standardallokeringen, kan du kontakta försäljningsrepresentanten och be dem kontakta plattformsteamet för ett undantag.
- **Lagersynlighetstjänst som en komponent i IOM** – Den här versionen är till Intelligent Order Management kunder eller företag som inte använder Supply Chain Management som ett ERP-system. Licensen ingår i paketet Intelligent Order Management. Mer information finns i [översikt över Intelligent Order Management ](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>Termen lagersynlighet

Det är viktigt att du förstår följande begrepp och termer när du arbetar med tillägget lagersynlighet:

- **Datakällan** – Datakällan representerar det system som dina data kommer från.
- **Dimensioner** – Dimensioner identifierar produktegenskaper. De kan vara lagringsdimensioner (till exempel site eller lagerställe) eller produktdimensioner (till exempel färg, storlek eller stil).
- **Fysiska mått** – Fysiska mått är kvantiteter som mäter olika lagerstatusar, till exempel lagerbehållning, inköpt, behållning eller såld.
- **Beräknade mått** – Beräknade mått är kvantitativa mått som beräknas med en uppsättning fysiska mått. Till exempel beräknat mått *Total tillgänglig* beräknas som *Behållning* + *Inköpt* – *Har beställts* – *Såld*.
- **Partition** – En partition definierar en hierarki för hur lagersynlighet ska fördela mottagna data. Standardpartitionen är för närvarande webbplats och plats.
- **Indexhierarki** – En indexhierarki definierar ytterligare hur du vill söka efter lager och erhålla resultat som har mer granularitet.

För mer information om dessa termer och begrepp, se [Konfigurera lagersynlighet](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
