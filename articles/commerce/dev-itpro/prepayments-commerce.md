---
title: Förskottsbetalningar i Dynamics 365 Commerce
description: Detta ämne ger en översikt över bearbetningen av förskottsbetalningstransaktioner i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780376"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Förskottsbetalningar i Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Detta ämne ger en översikt över bearbetningen av förskottsbetalningstransaktioner i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce bearbetar förskottsbetalningstransaktioner för följande betalningstyper som används i kundreskontra eller handel:

- **Betalning för insättning på kundkonto** – En kund betalar en insättning i kassan (POS). Handel bearbetar insättningsbetalningen som en förskottsbetalningstransaktion. När du bokför transaktionen skapas en betalningsjournal och bokförs på sidan **Bokföringsorder** i Commerce headquarters. Kryssrutan **Verifikation för förskottsbetalningsjournal** på fliken **Betalning** markeras automatiskt för betalningsjournalen. För mer information, inklusive förskottsbetalning och skattespecifik information som är relevant för målregionen, se [Globaliseringsresurser – Lands-/regionspecifikt hjälpinnehåll](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Kundorder som har en insättning** – En kund skapar en kundorder i POS. Kunden kan betala en deposition för beställningen, baserat på standardinsättningsprocenten som är konfigurerad på sidan **Kundorder** i Commerce headquarters (**Handelsparametrar \> Kundorder**). Handel bearbetar insättningsbetalningen för kundorder som en förskottsbetalningstransaktion. När du bokför transaktionen skapas en betalningsjournal och bokförs på sidan **Bokföringsorder**. Kryssrutan **Verifikation för förskottsbetalningsjournal** på fliken **Betalning** markeras automatiskt för betalningsjournalen. Betalningen kvittas och kundfakturan utfärdas automatiskt när ordern plockas eller levereras.
- **Försäljningsorder för kundtjänst** – En kundtjänstrepresentant för callcenter skapar en försäljningsorder på uppdrag av en kund och attributet **förskottsbetalning** anges till **Ja** under betalningsinsamling.

Commerce utför följande uppgifter när en förskottsbetalning bearbetas:

- **Behandla en insättningsbetalning för kundkonto** – En insättningsbetalning som en kund gör överförs till Commerce genom att använda en tjänst som synkroniserar data. Commerce skapar en butik betalningstransaktion för betalningen. När du bokför detaljhandelstransaktionen bokförs en kassajournal eller kundbetalningsjournal. Kryssrutan **Verifikation för förskottsbetalningsjournal** på fliken **Betalning** på sidan **Bokföringsorder** i Commerce headquarters markeras automatiskt för betalningsjournalen. Förskottsbetalningar kan inte bearbetas om betalningsbeloppet är negativt.
- **Behandla en kundorder eller försäljningsorder som har en insättning** – En kund betalar en nödvändig insättning för en kundorder genom att använda Commerce Data Exchange: Realtidstjänst. I Commerce skapas antingen en kundbetalningsjournal eller en kassajournal beroende på vilken betalningsmetod kunden använder. Kryssrutan **Verifikation för förskottsbetalningsjournal** på fliken **Betalning** på sidan **Bokföringsorder** markeras automatiskt för journalen i Commerce headquarters. Om en kund använder flera betalningsmetoder för att göra delbetalningar bearbetar Commerce varje delbetalning, baserat på den betalningsmetod som används.

För kreditkort och digitala kreditkort som har underliggande kreditkortsbetalningsmetoder skickar Commerce en begäran om "hämtar" efter att auktoriseringen lyckades. (Medel tas till innan försäljningsordern faktureras.)

Om du annullerar en kundorder återbetalas förskottsbetalningsbeloppet och en återbetalningsbetalningsjournal bokförs för insättningsbeloppet. Återbetalningsbeloppet beräknas och bokförs baserat på den betalningsmetod som du angav när du bokförde återbetalningsbetalningen. Commerce kan tillämpa en annulleringsavgift, baserat på procenttalet som du ställer in på sidan **Handelsparametrar** i Commerce headquarters.

Om du returnerar en kundorder skapas en returorder och en återbetalningsbetalningsjournal. När du bokför returordern skapar Commerce antingen en kundbetalningsjournal eller en kassajournal, beroende på vilken betalningsmetod som kunden använde för den ursprungliga transaktionen.
