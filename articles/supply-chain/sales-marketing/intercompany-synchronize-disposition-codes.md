---
title: Synkronisera dispositionskoder
description: I det här avsnittet beskrivs synkronisering av dispositionskoder för koncernintern handel
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 27b587e576900f2b7f7fed7ee2a27a282306f0fe
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671770"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Synkronisera koncerninterna dispositionskoder

[!include [banner](../../includes/banner.md)]

För att stödja koncerninterna returer gör Microsoft Dynamics 365 Supply Chain Management att du kan mappa externt definierade dispositionskoder till motsvarande interna dispositionskoder. När en koncernintern kedja ställs in måste dispositionsåtgärderna i de två företagen som mappas till varandra vara desamma. Om de skiljer sig åt misslyckas synkroniseringen.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Om dispositionskoder för treledad direktreturer

Dispositionskoder synkroniseras från den koncerninterna försäljningsorderraden till den ursprungliga försäljningsorderraden. Synkroniseringen har dock bara en omedelbar effekt på den ursprungliga försäljningsorderraden. Det här innebär att tilläggsavgift för rad tas bort baserat på dispositionskoden och tilläggsavgiften som ställs in i företag A. Företag A är det företag som skapar returordern.

I en treledad leveranskedja stöds alla dispositionsuppgifter på den koncerninterna försäljningsorderraden. I fall där produkten returneras till kunden är det dock viktigt att bekräfta att leveransadressen i returordern matchar kundens leveransadress som angetts på den ursprungliga ordern.

> [!NOTE]
> Dispositionskoder finns inte för inköpsorder. Därför måste synkronisering av dispositionskoder från den koncerninterna försäljningsordern till den ursprungliga returordern utföras från försäljningsorder till försäljningsorder.

## <a name="replacing-returned-items"></a>Ersätta returnerade artiklar

När en returnerad artikel ersätts och en ersättningsorder redan har skapats i företag B, kan en dispositionskod inte väljas och ingen ytterligare ersättningsorder skapas i företag A.

## <a name="rules-for-intercompany-direct-deliveries"></a>Regler för koncerninterna direktleveranser

Följande allmänna regler gäller för ursprungliga returorder i scenarier som involverar koncerninterna direktleveranser:

- Om den underliggande dispositionsåtgärden på den ursprungliga försäljningsorderraden är Kreditera och kassera, Kreditera eller Returnera till kund, tillämpas dispositionsåtgärden Kreditera. Åtgärdskoden Returnera till kund anger nettobeloppet till 0 (noll) på den befintliga raden och på den nysynkroniserade raden från den koncerninterna försäljningsordern. Kasseringsrader synkroniseras aldrig. När en rad läggs till en koncernintern försäljningsorder, synkroniseras den aldrig för en försäljningsorder med en positiv kvantitet och dispositionsåtgärden Kassera (exempelvis, Kreditera och kassera eller Ersätt och kassera).
- En underliggande dispositionsåtgärd som Kreditera och ersätt eller Kassera och ersätt åsidosätts inte. Det behandlas som en underliggande dispositionsåtgärd som Kreditera och ersätt eller Kassera och ersätt. Den här regeln gäller även om ingen kassationsrad skapas i företag A och ingen ersättningsorder skapas i företag B (företaget som tog emot den returnerade artikeln). En ersättningsorder skapas bara i företag A när en uppdatering av följesedeln utförs.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
