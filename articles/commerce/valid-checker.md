---
title: Validera butikstransaktioner för utdragsberäkning
description: Den här artikeln beskriver funktionerna för att validera butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4be40189777a37495f185467050b61af47b684d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890525"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Validera butikstransaktioner för utdragsberäkning

[!include [banner](includes/banner.md)]

Den här artikeln beskriver funktionerna för att validera butikstransaktioner i Microsoft Dynamics 365 Commerce. Valideringsprocessen identifierar och markerar transaktioner som orsakar bokföringsfel innan de hämtas av bokföringsprocessen för utdrag.

När du försöker bokföra ett utdrag kan valideringsprocessen misslyckas på grund av inkonsekvent data i handelstransaktionsregistren. Här följer några exempel på faktorer som kan orsaka sådana inkonsekvenser:

- Transaktionssumman i huvudtabellen stämmer inte överens med transaktionssumman på raderna.
- Antalet artiklar som anges i huvudtabellen matchar inte antalet artiklar i transaktionstabellen.
- Moms i huvudtabellen stämmer inte överens med momsbeloppet på raderna. 

Om inkonsekventa transaktioner hämtas i bokföringsprocessen för utdrag, skapas inkonsekventa försäljningsfakturor och betalningsjournaler som skapas kan orsaka att det inte går att bokföra. Processen **Validera butikstransaktioner** förhindrar dessa problem genom att säkerställa att endast transaktioner som passerar transaktionsvalideringsreglerna skickas till beräkningsprocessen för transaktionsutdrag.

Följande illustration visar de återkommande dagtidsprocesserna för transaktionsuppladdning, transaktionsvalidering och beräkning och bokföring av transaktionsutdrag samt dagsavstämningsprocesserna för beräkning och bokföring av bokslut.

![Illustration som visar de återkommande dagtidsprocesserna för transaktionsuppladdning, transaktionsvalidering och beräkning och bokföring av transaktionsutdrag samt dagsavstämningsprocesserna för beräkning och bokföring av bokslut.](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Valideringsregler för butikstransaktioner

Batchprocessen **Validera butikstransaktioner** kontrollerar att handelstransaktionsregistren är konsekventa grundat på följande valideringsregler.

> [!NOTE]
> Valideringsregler läggs även fortsättningsvis till i efterföljande versioner.

### <a name="transaction-header-validation-rules"></a>Valideringsregler för transaktionshuvud

Följande tabell visar valideringsregler för transaktionshuvud som kontrolleras mot butikstransaktionshuvudet innan dessa transaktioner skickas till utdragsbokföring.

| Regel | Beskrivning |
|-------|-------------|
| Affärsdatum | Den här regeln validerar att transaktionens affärsdatum är associerat med en öppen räkenskapsperiod i redovisningen. |
| Valutaavrundning | Den här regeln validerar att transaktionsbeloppen avrundas enligt valutaavrundningsregeln. |
| Kundkonto | Den här regeln validerar att kunden som används i transaktionen finns i databasen. |
| Rabattbelopp | Den här regeln validerar att rabattbeloppet i huvudet är lika med summan av radernas rabattbelopp. |
| Bokföringsstatus för skattedokument (Brasilien) | Den här regeln validerar att skattedokumentet går att bokföra. |
| Bruttobelopp | Den här regeln validerar att bruttobeloppet i transaktionshuvudet motsvarar transaktionsradernas nettobelopp, inklusive moms, plus avgifter. |
| Netto | Den här regeln validerar att nettobeloppet i transaktionshuvudet motsvarar transaktionsradernas nettobelopp, exklusive moms, plus avgifter. |
| Netto + moms | Den här regeln validerar att bruttobeloppet i transaktionshuvudet motsvarar transaktionsradernas nettobelopp, exklusive moms, plus alla skatter och avgifter. |
| Antal artiklar | Den här regeln validerar att antalet artiklar som anges i transaktionshuvudet motsvarar kvantiteternas summa på transaktionsraderna. |
| Betalningsbelopp | Den här regeln validerar att betalningsbeloppet i transaktionshuvudet motsvarar summan av alla betalningstransaktioner. |
| Beräkning av momsbefrielse | Den här regeln validerar att summan av det beräknade beloppet och avgiftsradernas momsbefrielsebelopp är lika med det ursprungliga beräknade beloppet. |
| Pris inklusive moms | Den här regeln validerar att flaggan **Moms inkluderad i priset** är konsekvent i transaktionshuvudet och momstransaktionerna. |
| Transaktion inte tom | Den här regeln validerar att transaktionen innehåller rader och att minst en rad inte är annullerad. |
| Under-/överbetalning | Den här regeln validerar att skillnaden mellan bruttobeloppet och betalningsbeloppet inte överskrider konfigurationen för maximal underbetalning/överbetalning. |

### <a name="transaction-line-validation-rules"></a>Valideringsregler för transaktionsrader

Följande tabell visar valideringsregler för transaktionsrader som kontrolleras mot butikstransaktionernas radinformation innan dessa transaktioner skickas till utdragsbokföring.

| Regel | Beskrivning |
|-------|-------------|
| Streckkod | Den här regeln validerar att alla artikelstreckkoder som används på transaktionsraderna finns i databasen. |
| Avgiftsrader | Den här regeln validerar att summan av det beräknade beloppet och avgiftsradernas momsbefrielsebelopp är lika med det ursprungliga beräknade beloppet. |
| Presentkortsreturer | Den här regeln validerar att det inte finns presentkortsreturer i transaktionen. |
| Artikelvariant | Den här regeln validerar att alla artiklar och varianter som används på transaktionsraderna finns i databasen. |
| Radrabatt | Den här regeln validerar att radrabattbeloppet motsvarar rabattransaktionernas summa. |
| Radmoms | Den här regeln validerar att radmomsbeloppet motsvarar momstransaktionernas summa. |
| Negativt pris | Den här regeln validerar att negativa priser inte används på transaktionsraderna. |
| Serienummer kontrollerat | Den här regeln validerar att serienumret finns på transaktionsraden för artiklar som kontrolleras med serienummer. |
| Serienummerdimension | Den här regeln validerar att inget serienummer anges om artikelns serienummerdimension är inaktiv. |
| Inkonsekvent förtecken | Den här regeln validerar att kvantitetens och nettobeloppets förtecken är samma på alla transaktionsrader. |
| Momsbefrielse | Den här regeln validerar att radartikelprisets summa och momsbefrielsebeloppet är lika med det ursprungliga priset. |
| Momsgruppstilldelning | Den här regeln validerar att kombinationen momsgrupp och artikelskattegrupp ger en giltig skatteskärningspunkt. |
| Måttkonverteringar | Den här regeln validerar att måttenheten för alla rader har en giltig konvertering till lagermåttet. |

## <a name="enable-the-store-transaction-validation-process"></a>Aktivera valideringsprocessen för butikstransaktioner

Konfigurera jobbet **Validera butikstransaktioner** för periodiska körningar i Commerce-administration (**Retail och Commerce \> Retail och Commerce IT \> Kassabokföring**). Batchjobbet tidsplaneras grundat på butikens organisationshierarki. Vi rekommenderar att du konfigurerar den här batchprocessen att köra med samma frekvens som batchjobben **P-jobb** och **Beräkning av transaktionsutdrag**.

## <a name="results-of-the-validation-process"></a>Valideringsprocessens resultat

Det går att visa resultatet av batchprocessen **Validera butikstransaktioner** för varje butikstransaktion. Fältet **Valideringsstatus** för transaktionsposten är inställd på **Slutförd**, **Fel** eller **Ingen**. Fältet **Senaste valideringstid** visar datumet för den senaste valideringskörningen.

Följande tabell beskriver varje valideringsstatus.

| Valideringsstatus | Beskrivning |
|-------------------|-------------|
| Slutförd | Alla aktiverade valideringsregler godkända. |
| Fel | En aktiverad valideringsregel har identifierat ett fel. Det går att visa mer information om felet genom att välja **Valideringsfel** i åtgärdsfönstret. |
| Ingen | Transaktionstypen kräver inte att valideringsregler används. |

![Sidan Butikstransaktioner visar fältet Valideringsstatus och knappen Valideringsfel.](./media/valid-checker-validation-status-errors.png)

Endast transaktioner som har valideringsstatus **Slutförd** hämtas till transaktionsutdragen. Visa transaktioner med statusen **Fel** genom att granska panelen **Valideringsfel för hämtköp** på arbetsytan **Butiksekonomi**.

![Paneler på arbetsytan Butiksekonomi.](./media/valid-checker-cash-carry-validation-failures.png)

Mer information om att korrigera valideringsfel för hämtköp finns i [Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering](edit-cash-trans.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
