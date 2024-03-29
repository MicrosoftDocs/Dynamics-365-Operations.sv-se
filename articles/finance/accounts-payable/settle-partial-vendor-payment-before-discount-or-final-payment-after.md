---
title: Kvitta en delbetalning före rabattdatum och slutbetalning efter rabattdatum
description: Det här avsnittet innehåller en genomgång av ett scenario där flera delbetalningar görs. Vissa av dem inom kassarabattperioden och andra utanför den.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 828c82d88bef1d942af1219505af591d27043fa5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780600"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Kvitta en delbetalning före rabattdatum och slutbetalning efter rabattdatum

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en genomgång av ett scenario där flera delbetalningar görs. Vissa av dem inom kassarabattperioden och andra utanför den.

Fabrikam köper varor från leverantör 3057. Fabrikam får en kassarabatt på 1 procent om fakturan betalas inom 14 dagar. Fakturor måste betalas inom 30 dagar. Leverantören ger också Fabrikam kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för leverantörsreskontra**.

## <a name="invoice-on-june-25"></a>Faktura den 25 juni
Den 25 juni registrerar och bokför April en faktura på 1 000,00 för leverantör 3057. April kan visa den här transaktionen på sidan **Leverantörstransaktioner**.

| Verifikation   | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo   | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Fakt 10020 | Faktura          | 6/25/2020 | 10020   |                                      | 1,000.00                              | -1 000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Delbetalning den 2 juli
Den 2 juli vill April kvitta 300,00 av den här fakturan. Betalningen är berättigad till en rabatt, eftersom Fabrikam får rabatt på delbetalningar. Därför betalar April 297,00 och får en rabatt på 3,00. Hon skapar en betalningsjournal och anger en rad för leverantören 3057. Hon öppnar sedan sidan **Kvitta transaktioner** så att hon kan välja den faktura som ska kvittas.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | Fakt 10020 | 3057    | 6/25/2020 | 7/25/2020 | 10020   | -1 000,00                      | USD      | -297,00          |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -3,00     |

April bokför sedan fakturan. Fakturan har nu ett saldo på 700,00. April kan visa den här transaktionen på sidan **Leverantörstransaktioner**.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt 10020  | Faktura          | 6/25/2020 | 10020   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10020  | Betalning          | 7/1/2020  |         | 297,00                               |                                       | 0,00    | USD      |
| RAB-10020 | Kassarabatt    | 7/1/2020  |         | 3.00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Resterande betalning den 15 juli, Använd kassarabatt = Normal
April betalar resten av fakturan den 15 juli, vilket är efter rabattperioden. På sidan **Kvitta öppna transaktioner** visas inget rabattbelopp i fältet **Beräknad kassarabatt** och värdet i fältet **Kassarabattbelopp** är **0,00**. När April betalar de återstående 700,00, ges ingen ytterligare rabatt.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | Fakt 10020 | 3057    | 6/25/2020 | 7/25/2020 | 10020   | -700,00                        | USD      | -700,00          |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**. April ser att hon redan har tagit emot 3,00 rabatt.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 0,00      |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | -3,00     |
| Kassarabattbelopp att utnyttja | 0,00      |

April bokför sedan betalningen. När hon öppnar sidan **Leverantörstransaktioner** ser hon att fakturan har ett saldo på 0,00. Hon ser också att det finns två betalningar. En betalning på 297,00 och med 3,00 rabatt och den andra betalningen på 700,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt 10020  | Faktura          | 6/25/2020 | 10020   |                                      | 1,000.00                              | 0,00    | USD      |
| APP-10020  | Betalning          | 7/1/2020  |         | 297,00                               |                                       | 0,00    | USD      |
| RAB-10020 | Kassarabatt    | 7/1/2020  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Betalning          | 7/15/2020 |         | 700.00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Resterande betalning den 15 juli, Använd kassarabatt = Alltid
Om leverantören låter April göra en rabatt trots att hon betalar efter rabattdatumet kan hon ändra värdet i fältet **Använd kassarabatt** till **Alltid**. Inställningen **Beräkna kassarabatter för delbetalningar** åsidosätts och rabatten används. Betalningsbeloppet är 693,00 och rabatten är de återstående 7,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|----------|------|------|-----------|-----------|---------|-----------------------|---------------------------------------|----------|------------------|
| Markerad | Alltid            | Fakt 10020 | 3057    | 6/25/2020 | 7/25/2020 | 10020   | 700.00                   |                   | USD      | -693,00          |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 7.00      |
| Använd kassarabatt            | Alltid    |
| Utnyttjad kassarabatt          | -3,00     |
| Kassarabattbelopp att utnyttja | -7,00     |

April bokför sedan betalningen. När hon öppnar sidan **Leverantörstransaktioner** ser hon att fakturan har ett saldo på 0,00. Hon ser också att det finns två betalningar. En betalning på 297,00 med 3,00 rabatt och den andra betalningen på 693,00 med 7,00 rabatt.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt 10020  | Faktura          | 6/25/2020 | 10020   |                                      | 1,000.00                              | 0,00    | USD      |
| APP-10020  | Betalning          | 7/1/2020  |         | 297,00                               |                                       | 0,00    | USD      |
| RAB-10020 | Kassarabatt    | 7/1/2020  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Betalning          | 7/15/2020 |         | 693,00                               |                                       | 0,00    | USD      |
| RAB-10021 | Kassarabatt    | 7/15/2020 |         | 7.00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
