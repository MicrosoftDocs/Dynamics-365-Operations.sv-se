---
title: Kvitta en delbetalning före rabattdatum med slutbetalning efter rabattdatum
description: Den här artikeln diskuterar effekten av kvittning av betalningar till fakturor för kunder. Scenariot fokuserar på effekterna i reskontran, inte i redovisningen.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f6b4527a9f176857e0cc6ba4665688dc8721ac1
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780550"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>Kvitta en delbetalning före rabattdatum med slutbetalning efter rabattdatum

[!include [banner](../includes/banner.md)]

Den här artikeln diskuterar effekten av kvittning av betalningar till fakturor för kunder. Scenariot fokuserar på effekterna i reskontran, inte i redovisningen.

Fabrikam säljer varor till kunden 4027. Fabrikam erbjuder en kassarabatt på 1 procent om fakturan betalas inom 14 dagar. Fakturor måste betalas inom 30 dagar. Fabrikam erbjuder även kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för kundreskontra**.

## <a name="invoice"></a>Faktura
Den 25 juni registrerar och bokför Arnie en faktura på 1 000,00 för kund 4027. Arnie kan visa denna faktura genom att använda knappen **Transaktioner** på sidan **Kunder**.

| Verifikation   | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Faktura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 1,000.00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Delbetalning före kassarabattdatumet
Den 2 juli betalar kund 4027 en delbetalning på 297,00 för fakturan. Betalningen är berättigad till en kassarabatt, eftersom Fabrikam erbjuder kassarabatter på delbetalningar, och delbetalningen görs för kassarabatten. Därför utnyttjar kund 4027 en kassarabatt 3,00. Arnie registrerar betalningen för kund 4027, genom att använda betalningsjournalen. Arnie öppnar sedan sidan **Kvitta transaktioner** så att han kan välja den faktura som ska kvittas.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 1,000.00                             | USD      | 297,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Om du inte ändrar värdet för **Kvitta transaktioner** till **297,00**, kommer värdet för Kassarabattbelopp att skilja sig. Men 3,00 kommer att utnyttjas som kassarabatt när betalningen bokförs, eftersom kvittningen justerar automatiskt värdet **Belopp att kvitta**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 3,00      |

Arnie bokför den här betalningen. Fakturan har nu ett saldo på 700,00. Följande transaktioner kan ses för kunden.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 700.00  | USD      |
| ARP-10020  |  Betalning         | 7/1/2020  |         |                                      | 297,00                                | 0,00    | USD      |
| RAB-10020 |  Kassarabatt   | 7/1/2020  |         |                                      | 3.00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Återstående betalning efter kassarabattdatumet
Den 11 april betalar kund 4027 resten av fakturan, vilket är efter rabattperioden. På sidan **Kvitta öppna transaktioner** visas inget rabattbelopp i fältet **Beräknad kassarabatt** och värdet i fältet **Kassarabattbelopp** är **0,00**. När kund 4027 betalar de återstående 700,00, ges ingen ytterligare rabatt.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 700.00                               | USD      | 700.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 0,00      |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 3,00      |
| Kassarabattbelopp att utnyttja | 0,00      |

Om Arnie ändrar värdet i fältet **Använd kassarabatt** till **Alltid**, kommer inställningen **Beräkna kassarabatter för delbetalningar** att åsidosättas och kassarabatten utnyttjas. Betalningsbeloppet ändras 693,00 och rabatten är de återstående 7,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|---------------|---------------------|----------|------------------|
| Markerad | Alltid            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 700.00        |                        | USD      | 693,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 7.00      |
| Använd kassarabatt            | Alltid    |
| Utnyttjad kassarabatt          | 3,00      |
| Kassarabattbelopp att utnyttja | 07:00      |

Arnie ändrar värdet i fältet **Använd kassarabatt** tillbaka till **Normal**, eftersom han inte låter den här kunden utnyttja den återstående kassarabatten på 7,00. Arnie bokför sedan betalningen. När Arnie öppnar sidan **Kundtransaktioner** ser han att fakturan har ett saldo på 0,00. Det finns två betalningar. En betalning på 297,00 och med 3,00 kassarabatt och den andra betalningen på 700,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 7/1/2020  |         |                                      | 297,00                                | 0,00    | USD      |
| RAB-10020 |                  | 7/1/2020  |         |                                      | 3.00                                  | 0,00    | USD      |
| ARP-10021  |                  | 7/11/2020 |         |                                      | 700.00                                | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
