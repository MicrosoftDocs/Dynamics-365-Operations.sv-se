---
title: Bokföringar av leverantörsreskontra
description: I det här avsnittet beskrivs hur bokföringar konfigureras i leverantörsreskontra och ger exempel på bokföringskonfigurationer.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb3ebad31c9f41e405b9fc31a0f71df05fa1cc60
ms.sourcegitcommit: 10b85a09e8a550155a69aa2a8877a7c88b887242
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2022
ms.locfileid: "8014475"
---
# <a name="accounts-payable-posting"></a>Bokföring av leverantörsreskontra

[!include [banner](../includes/banner.md)]

Den primära bokföringsprofilen för modulen **Leverantörsreskontra** är leverantörens bokföringsprofil. Denna bokföringsprofil bestämmer vilket samlingskonto som används när leverantörssaldon bokförs i redovisningen. Ett samlingskonto är ett huvudkonto. Det kallas också för leverantörsreskontra handelkontot.

Mer information finns i [Bokföringsprofiler för leverantör](../accounts-payable/vendor-posting-profiles.md).

Flera bokföringskonfigurationer förutom leverantörsbokföringsprofilen finns i leverantörsreskontra. Följande avsnitt innehåller mer information om dessa andra bokföringskonfigurationer.

## <a name="methods-of-payment-posting-accounts"></a>Bokföringskonton för betalningsmetoder

Betalningsmetoder anger hur en betalning ska bokföras i redovisningen. De styr även hur betalningsutleveransen fungerar. Vanligtvis skapas en betalningsmetod för varje typ av betalning som din organisation gör (till exempel kontant, check, kreditkort, pengaorder och kontantbetalning).

Fälten i avsnittet **Bokföring** på snabbfliken **Allmänt** på sidan **Betalningsmetoder** (**Leverantörsreskontra > Betalningsinställning > Betalningsmetoder**) kontrollerar hur en betalning ska bokföras till huvudboken. Du måste först välja ett värde i fältet **Kontotyp**. Den kontotyp du väljer styr hur fältet **Betalningskonto** fungerar. Vi rekommenderar att du väljer **Bank** i fältet **Kontotyp** och sedan väljer bankkontot i fältet **Betalningskonto**. Fördelen med det här är att systemet bokför betalningen i redovisningen för bankredovisningen, som stöder avstämning och andra kassarelaterade processer. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen om du använder modulen **Kassa- och bankhantering**.

| Bokföringstyp | Kontotyp | Betalningskonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Bank of America | Bankkonto som är kopplat till en tillgång | Debet | Nej | Ange huvudkontot i fältet **Betalningskonto** för varje betalningsmetod. |

Om du inte planerar att använda kassa- och bankhantering bör du välja **Redovisning** i fältet **Kontotyp** och sedan välja huvudkontot i fältet **Betalningskonto**. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen om du använder **inte** Kassa- och bankhantering.

| Bokföringstyp | Kontotyp |Betalningskonto exempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Bank of America | Tillgång | Debet | Nej | Ange huvudkontot i fältet **Betalningskonto** för varje betalningsmetod. |

## <a name="bridging-accounts"></a>Interimskonto

Interimsbokning är en process i två steg som används när betalningar bokförs. Det är en valfri funktion som till exempel kan användas med nollsaldobankkonton. Det kan bidra till en smidigare och lämpligare bankavstämningsprocess. I det första steget bokförs en betalning på ett tillfälligt konto (interimkontot). I det andra steget återförs och bokförs den bokförda posten på bankkontot när betalningen rensar banken. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen för interimsbokning.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Redovisningsjournal | 130725 | Oklara kontanter | Skulder | Debet | Ja | Ange huvudkontot i fältet **Interimskonto** för varje betalningsmetod. |

Mer information finns i [Ställa in och bearbeta Interimsbetalningar](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Bokföringskonton för kundkassarabatter

Om din organisation får kassarabatter från leverantörer i utbyte mot snabb betalning måste du konfigurera kassarabattkoder och ange hur rabatterna ska bokföras i redovisningen. Det finns flera alternativ för att ange huvudkontot som används för att bokföra en kundkassarabatt.

Mer information finns i [Kassarabatter](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Bokföringskonton för betalningsavgift

Med betalningsavgifter kan du automatiskt lägga till en avgift till en leverantörsbetalning när en uppsättning villkor gäller. Betalningsavgifter kan betalas till leverantören eller så kan de bokföras på ditt bankkonto som en utgift. Nedan följer några exempel:

- En leverantör Debeterar dig 3 procent av betalningssumman om du betalar med kreditkort.
- Dina bankavgifter $1,00 betalning för varje överföring som du bearbetar, och avgiften Debeteras.

När du konfigurerar en leverantörsbetalningsavgift, om du ställer in fältet **Avgift** till **Leverantör** blir fältet **Huvudkonto** inte tillgängligt och systemet använder leverantörens bokföringsprofil för att bokföra avgiften. Om du ställer in fältet **Avgift** till **Redovisning** måste du ställa in fältet **Huvudkonto** på huvudkontot där betalningsavgiften ska bokföras. Detta huvudkonto är vanligtvis ett utgiftskonto. Följande tabell visar ett exempel på bokföringsprofilkonfigurationen för betalningsavgift bokföring..

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Redovisningsjournal | 618190 | Bankavgift | Utgift | Debet | Nej | Om **Redovisning** har valts i fältet **Tillägg** väljer du detta konto i fältet **Huvudkonto** på sidan **Betalningsavgift**. |

Mer information finns i [Definiera leverantörsbetalningsavgifter](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Bokföringskonton för avgiftskod

Om du förutom radartiklar måste spåra inköpsbelopp kan du använda avgiftskoder. Din leverantör kanske till exempel Debeterar dig frakt- och hanteringsavgifter, eller så kan det kosta vissa frakt- och hanteringsavgifter internt. Du kan ange om dessa belopp ska bokföras på utgiftskonton eller läggas till i kostnaden för artiklarna.

Du kan skapa avgiftskoder för Kundreskontra och Leverantörsreskontra. När du konfigurerar en Debeteringskod måste du definiera bokföringen. Bokföringen styr både debetkontot och kreditkontot. När du skapar Debeteringskoder kan du välja den bokföringstyp som används för respektive Debeteringskod. Följande tabell innehåller exempel på typiska avgiftskoder för leverantörsreskontra på sidan **Avgiftskoder**.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Inköpsavgift | Lämna fältet tomt. | Inte tillämpligt | Artikel | Debet | Nej | **Exempel på en inköpsavgift för en artikel:** </p><ul><li>**Debettyp** fält = **Artikel**</li><li>  **Kredittyp** fält = **Kund/Leverantör**.</li><li> Artikelbokföringen använder huvudkontot från lagerbokföringsprofilen. |
| Order, frakt | 600120 | Frakt i | Intäkter | Debet | Nej | **Exempel på frakt som betalas till en leverantör:** </p><ul><li>**Debettyp** fält = **Redovisningskonto**</li><li> **Kredittyp** fält = **Kund/Leverantör**. |
| Rabatt\* | 503160 | Leverantörsrabatt (Contra COGS)| Utgift | Kredit | Nej | **Exempel på en leverantörsrabatt:**</p><ul><li>**Debettyp** fält = **Kund/Leverantör**.</li><li>**Kredittyp** fält = **Redovisningskonto** |

\* För rabattexempel används bokföringen bara när en avgiftskod läggs till i ett inköpsorderhuvud eller en inköpsorderrad. Den avancerade rabattfunktion som finns i Microsoft Dynamics 365 Supply Chain Management ger mer kontroll och automatisering av rabatter. Mer information finns i [Leverantörsrabatter](../../supply-chain//procurement/vendor-rebates.md).

Föregående tabell visar tre typiska exempel på bokföringstyper som kan användas för avgiftskoder. Den bör användas som riktlinje och ett urval exempel. Det ger ingen omfattande lista över alla tänkbara kombinationer eller bokföringstyper som kan användas.

Mer information finns i [Skapa avgiftskoder](../accounts-receivable/create-charges-codes.md).
