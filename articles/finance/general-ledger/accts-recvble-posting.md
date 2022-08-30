---
title: Bokföring av kundreskontra
description: I den här artikeln beskrivs hur bokföringar konfigureras i kundreskontra och ger exempel på bokföringskonfigurationer.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d679595a1f702c4e3ade138a87c817d245fcf79
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324342"
---
# <a name="accounts-receivable-posting"></a>Bokföring av kundreskontra

[!include [banner](../includes/banner.md)]

Den primära bokföringsprofilen för modulen **Kundreskontra** är kundens bokföringsprofil. Denna bokföringsprofil bestämmer vilket samlingskonto som används när kundsaldon bokförs i redovisningen. Ett samlingskonto är ett huvudkonto. Det kallas också för kundreskontra handelskontot.

Rapporten **Avstämning kund mot huvudbok** kan användas efter bokföring för att stämma av saldona för kund- och redovisningskonton. Rapporten använder den information som finns i samlingskontot för kundbokföringsprofilen. Den använder inte samlingskontot från redovisningen som skapas för dokumentet. Om du ändrar kundbokföringsprofilen eller kundgruppen som tilldelas kunden efter att du har bokfört transaktioner, kan rapporten visa differenser mellan kunden och redovisningskontosaldot. Om du bara vill visa de rader som har differenser, och alla rader som kundkontona och redovisningskontot är båda noll för, väljer du parametern **Bara differenser** när du skriver ut rapporten.

Mer information finns i [Bokföringsprofiler för kund](../accounts-receivable/customer-posting-profiles.md).

Flera bokföringskonfigurationer förutom kundbokföringsprofilen finns i kundreskontra. Följande avsnitt innehåller mer information om dessa andra bokföringskonfigurationer.

## <a name="posting-accounts-for-methods-of-payment"></a>Bokföringskonton för betalningsmetoder

Betalningsmetoder anger hur en betalning ska bokföras i redovisningen. De styr även hur betalningsutleveransen fungerar. Vanligtvis skapas en betalningsmetod för varje typ av betalning som din organisation godkänner (till exempel kontant, check, kreditkort, pengaorder och överföring).

Fälten avsnittet **Bokföra** på snabbfliken **Allmänt** kontrollerar hur en betalning bokförs i redovisningen. Du måste först välja ett värde i fältet **Kontotyp**. Den kontotyp du väljer styr hur fältet **Betalningskonto** fungerar. Vi rekommenderar att du väljer **Bank** i fältet **Kontotyp** och sedan väljer bankkontot i fältet **Betalningskonto**. Fördelen med det här är att systemet bokför betalningen i redovisningen för bankredovisningen, som stöder avstämning och andra kassarelaterade processer. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen om du använder modulen **Kassa- och bankhantering**.

| Bokföringstyp | Kontotyp | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Bank of Contoso | Bankkonto som är kopplat till en tillgång | Kredit | Nej | Ange huvudkontot i fältet **Betalningskonto** för varje betalningsmetod. |

Om du inte planerar att använda kassa- och bankhantering bör du välja **Redovisning** i fältet **Kontotyp** och sedan välja huvudkontot i fältet **Betalningskonto**. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen om du använder inte Kassa- och bankhantering.

| Bokföringstyp | Kontotyp | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Bank of Contoso | Tillgång | Kredit | Nej | Ange huvudkontot i fältet **Betalningskonto** för varje betalningsmetod. |

## <a name="bridging-accounts"></a>Interimskonto

Interimsbokning är en process i två steg som används när betalningar bokförs. Det är en valfri funktion som till exempel kan användas med nollsaldobankkonton. Det kan bidra till en smidigare och lämpligare bankavstämningsprocess. I det första steget bokförs en betalning på ett tillfälligt konto (interimkontot). I det andra steget återförs och bokförs den bokförda posten på bankkontot när betalningen rensar banken. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen för interimsbokning.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Redovisningsjournal | 130725 | Oklara kontanter | Skulder | Debet | Ja | Ange huvudkontot i fältet **Interimskonto** för varje betalningsmetod. |

Mer information finns i [Ställa in och bearbeta Interimsbetalningar](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Bokföringskonton för kundkassarabatter

Om din organisation erbjuder kassarabatter till kunder i utbyte mot snabb betalning måste du konfigurera kassarabattkoder och ange hur rabatterna ska bokföras i redovisningen. Det finns flera alternativ för att ange huvudkontot som används för att bokföra en kundkassarabatt.

Mer information finns i [Kassarabatter](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Bokföringskonton för betalningsavgift

Med betalningsavgifter kan du automatiskt lägga till en avgift till en kundbetalning när en uppsättning villkor gäller. Betalningsavgifter kan tas ut av kunden, eller så kan de bokföras på ditt bankkonto som en utgift. Nedan följer några exempel:

- Du debiterar kunderna 3 procent av betalningssumman om de betalar med kreditkort.
- Dina bankavgifter $1,00 betalning för varje överföring som du bearbetar, och avgiften debiteras.

När du konfigurerar en kundbetalningsavgift, om du ställer in fältet **Avgift** till **kund** blir fältet **Huvudkonto** inte tillgängligt och systemet använder kundens bokföringsprofil för att bokföra avgiften. Om du ställer in fältet **Avgift** till **Redovisning** måste du ställa in fältet **Huvudkonto** på huvudkontot där betalningsavgiften ska bokföras. Detta huvudkonto är vanligtvis ett utgiftskonto. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen för betalningsavgift bokföring..

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Redovisningsjournal | 618190 | Bankavgift | Utgift | Debet | Nej |  Om **Redovisning** har valts i fältet **Tillägg** väljer du detta konto i fältet **Huvudkonto** för betalningsavgift. |

Mer information finns i [upprätta kundens betalningsavgifter](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Bokföra konton för avgiftskoder

Om du förutom radartiklar måste spåra försäljningsbelopp kan du använda avgiftskoder. Du kanske till exempel debiterar frakt- och hanteringsavgifter till dina kunder, eller så kan det kosta vissa frakt- och hanteringsavgifter internt. Du kan ange om dessa belopp ska bokföras på utgiftskonton eller läggas till i kostnaden för artiklarna.

Du kan skapa avgiftskoder för Kundreskontra och Leverantörsreskontra. När du konfigurerar en Debeteringskod måste du definiera bokföringen. Bokföringen styr både debetkontot och kreditkontot. För varje debiteringskod som du skapar kan du välja vilken bokföringstyp som används. Följande tabell visar typiska exempel på debiteringskoder för kundreskontra.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Betalningsavgift | 411400 | Intäkt – Avgifter | Intäkter | Kredit | Nej | **Exempel på otillräckliga medel:** Debetkonto för kund/leverantör och kreditredovisning |
| Order, frakt | 403500 | Intäkt – Frakt | Intäkter | Kredit | Nej | **Exempel på frakt som debiteras en kund:** Debitera kund /leverantör och kreditredovisningskonto |
| Rabatt\* | 403200 | Rabatt | Intäkter | Debet | Nej | **Exempel på otillräckliga medel:** Konto för debetredovisning och kredit kund/leverantör |

\* För rabattexempel används bokföringen bara när en avgiftskod läggs till i ett inköpsorderhuvud eller en inköpsorderrad. Den avancerade rabattfunktion som finns i Microsoft Dynamics 365 Supply Chain Management ger mer kontroll och automatisering av rabatter. Mer information finns i [Kundrabatter](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

Föregående tabell visar tre typiska exempel på bokföringstyper som kan användas för avgiftskoder. Den bör användas som riktlinje och ett exempel. Det ger ingen omfattande lista över alla tänkbara kombinationer eller bokföringstyper som kan användas.

Mer information finns i [Skapa avgiftskoder](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Bokföringskonton för provisioner

Du kan om du vill konfigurera systemet för att beräkna provisioner för en försäljare eller en grupp säljare på en given försäljningsorder. Om du aktiverar dessa funktioner måste du konfigurera bokföringskontot som används för att beräkna provisionen. Denna konfiguration görs på sidan för **Kommissionsbokföring** i modulen **Försäljning och marknadsföring**.

Mer information finns i [Ställa in regler för försäljningsprovision](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
