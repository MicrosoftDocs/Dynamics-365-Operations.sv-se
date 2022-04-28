---
title: Översikt över tillägg för Lagersynlighet
description: Detta avsnitt förklarar vad Lagersynlighet är och beskriver dess funktioner.
author: yufeihuang
ms.date: 03/18/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9eb8a135d2415c867c746a1c40a80cdb84819c0e
ms.sourcegitcommit: d475dea4cf13eae2f0ce517542c5173bb9d52c1c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547913"
---
# <a name="inventory-visibility-add-in-overview"></a>Översikt över tillägg för Lagersynlighet

[!include [banner](../includes/banner.md)]

Tillägget för lagersynlighet (kallas även *tjänsten Lagersynlighet*) tillhandahåller en oberoende och mycket skalbar mikrotjänst som möjliggör aktuella lagerändringsposteringar i realtid och synlighetsspårning över alla dina datakällor och kanaler. Den innehåller en plattform där du kan hantera det globala lagret med hjälp av funktioner som innehåller (men inte begränsat till) följande lista:

- Spåra centralt den senaste lagerstatusen (som tillgänglig, beställd, köpt, under transport, returnerad och karantän) över alla dina datakällor, lager och platser genom att ansluta din Supply Chain Management eller tredjeparts logistikdatakällor ( såsom orderhanteringssystem, tredje parts företagsresursplanering \[ERP\]-system, kassa \[POS\] och lagerhanteringssystem) till tjänsten lagersynlighet.
- Fråga om lagerbehållning och underskott, och få omedelbara svar genom att ringa lagersynlighetstjänsten direkt.
- Undvik överförsäljning, särskilt när din efterfrågan kommer från olika kanaler, genom att göra mjuka reservationer i realtid i tjänsten lagersynlighet.
- Hantera utlovade beställningar och kundernas förväntningar bättre genom att tillhandahålla exakta aktuella eller nästa tillgängliga datum, så att funktionen flerkanal tillgängligt att lova (ATP) kan beräkna förväntade datum för orderuppfyllelse.

## <a name="extensibility"></a>Utbyggbarhet

Tjänsten Lagerhantering är mycket utökningsbar eftersom inmatning och utdata inte är begränsade till Microsoft-program. Externa system kan komma åt tjänsten via RESTful application programming interfaces (API). Förutom att använda de "fördefinierade"-mappningar som finns för datakällan och dimensionerna i Supply Chain Management, kan du integrera lagersynlighet med flera tredjepartssystem genom att ställa in ytterligare datakällor, mått på lagerstatus (som kallas för *fysiska mått* i lagertjänst) och lagerdimensioner via konfigurationsprogrammet. På det här sättet kan du växla fråga och ändra flera datakällor och fördefinierade lagerdimensioner.

Eftersom lagersynligheten bygger på kan Microsoft Dataverse dess data dessutom användas för att bygga och integrera med Power Apps. Du kan också använda Power BI för att skapa anpassade instrumentpaneler som uppfyller dina affärskrav.

## <a name="scalability"></a>Skalbarhet

Tjänsten lagersynlighet kan skalas upp eller ned, beroende på datavolymen. Skalbarhetsupplevelsen är oftast sömlös och utförs av Microsofts plattformsteam, baserat på automatisk identifiering och bedömning av din transaktionsdatavolym.

## <a name="feature-highlights"></a>Funktionens höjdpunkter

### <a name="get-a-global-view-of-real-time-inventory"></a>Hämta en global vy över lager i realtid

Lagersynlighet garanterar att du alltid har tillgång till de senaste lagerkvantiteterna, i alla kanaler, platser och lagerställen. Det bästa är om du använder den för att stödja din dagliga verksamhet när du måste erhålla lagerposter. Fysisk lagerbehållning, sålda kvantiteter och inköpta kvantiteter är alla tillgängliga ur rutan. Du kan även konfigurera andra fysiska lagermått (t.ex. returnerade, i karantän och bokförda data) om du behöver, för att kunna visa dessa uppgifter i realtid. Lagersynlighet kan effektivt bearbeta flera miljoner lagerbytesposter. Dessa data kan aggregeras och återspeglas i de senaste lagerkvantiteterna på en gång, per sekund eller per minut, beroende på vilket intervall data har bokförts i. Mer information finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md).

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Mjuk reservation för att undvika överbokning mellan alla orderkanaler

En *mjuk reservation* gör att du kan tilldela eller flagga specifika kvantiteter för att uppfylla en order eller efterfrågan. En mjuk reservation påverkar inte det fysiska lagret, men det drar av från *tillgänglig för reservation* lagerkvantitet och tillhandahåller en uppdaterad kvantitet för framtida orderuppfyllelse. Den här funktionen är användbar om försäljningsbegäranden eller -order kommer till ditt företag från en eller flera kanaler eller datakällor som finns utanför ditt system för postsystem för resursplanering (ERP).

Om du inte använder mjuk reservationer i tjänsten Lagersynlighet, måste du vänta tills ordern synkroniseras till och bearbetas av ERP-systemet för att få en uppdatering av den fysiska lagerkvantiteten. Den här processen har vanligtvis en stor tidsfördröjning. Mjuk reservationer kommer dock omedelbart att påverkas varje gång en försäljningsförfrågan eller order genereras i dina försäljningskanaler. Därför hjälper de till att förhindra överförsäljningssituationer genom att se till att dina flerkanalsorder inte stör varandra när de så småningom når ERP-systemet. Mjuk reservationer ser också till att du kan uppfylla alla order som du har utlovat. Därför hjälper de dig att uppfylla kundernas önskemål och behålla kundlojaliteten. Mer information finns i [Reservationer för Lagersynlighet](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-dates-confirmation"></a>Bekräftelser på omedelbart svar från datum för slutdatum

Synligheten i ditt framtida projekterade lager (inklusive leverans, efterfrågan och projekterade detaljer i lager) är viktigt eftersom det hjälper ditt företag att uppnå följande mål:

- Minimera lagernivåerna för att minska lagerhanteringskostnaderna.
- Underlätta bearbetning av interna order så att försäljare kan beräkna leverans- och leveransdatum, baserat på tillgängligheten för de produkter som beställts.
- Ge insyn i när kunder kan förvänta sig att en artikel som inte finns i lager blir tillgänglig via nästa tillgängliga datum.

ATP-funktionen är lätt att använda i din dagliga beställningsprocess. Viktigast av allt, precis som andra erbjudanden om lagersynlighet, är ATP-funktionen *global och realtid*. Därför kan du ställa in flera ATP-beräkningsformler för att få fullständiga frågor om lagertillgänglighet som täcker alla dina affärskanaler och datakällor. Mer information finns i [Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova](inventory-visibility-available-to-promise.md).

### <a name="compatibility-with-advanced-warehouse-management-items"></a>Kompatibilitet med avancerade lagerstyrningsartiklar

Microsoft strävar efter att tillhandahålla fördefinierade integration med avancerad lagerhantering (WHS), så att WHS-kunder också kan dra nytta av fördelarna med Lagersynlighet-tjänsten. Enligt utgivningscykel 1 2022 (offentlig förhandsvisning i mars) stöder inventeringstjänsten WHS-förfrågningar och ATP. Den mjuka reservationen och allokeringsfunktionen stöds för WHS-kunder i nästa cykel. Mer information finns i [Stöd för lagersynlighet för WHS-artiklar](inventory-visibility-whs-support.md).

## <a name="licensing"></a>Licensiering

Tjänsten Lagersynlighet är tillgänglig i följande versioner:

- **Tillägg för Lagersynlighet för Microsoft Dynamics 365 Supply Chain Management** – För företag som har en giltig Supply Chain Management-licens är lagersynlighet tillgängligt utan extra licenskostnad. Du kan börja prova på det idag. Installationsdetaljer finns i [Installera och ställ in lagersynlighet](inventory-visibility-setup.md).
- **Lagersynlighetstjänst som en komponent i IOM** – Den här versionen är till Intelligent Order Management kunder eller företag som inte använder Supply Chain Management som ett ERP-system. Licensen ingår i IOM-bunten. Mer information finns i [översikt över Intelligent Order Management ](/dynamics365/intelligent-order-management/overview).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
