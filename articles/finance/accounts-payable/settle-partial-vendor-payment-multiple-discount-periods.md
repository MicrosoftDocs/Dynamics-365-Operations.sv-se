---
title: Kvitta en delleverantörsbetalning som har flera rabattperioder
description: Den här artikeln går igenom ett scenario där flera delbetalningar görs till en leverantör som erbjuder flera kassarabatter.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da69d61c657ddc168a27a97fe16909d5f60eb4fd
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778048"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Kvitta en delleverantörsbetalning som har flera rabattperioder

[!include [banner](../includes/banner.md)]

Den här artikeln går igenom ett scenario där flera delbetalningar görs till en leverantör som erbjuder flera kassarabatter. 

Leverantör 3054 erbjuder Fabrikam en kassarabatt på 2 procent, om en faktura betalas inom fem dagar och en kassarabatt på 1 procent, om fakturan betalas inom 14 dagar.

## <a name="invoice"></a>Faktura
Den 28 juni skapar April en faktura för 1 000,00 för leverantör 3054. April kan visa den här transaktionen på sidan **Leverantörstransaktioner**.

| Verifikation   | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Fakt- 10060 | 6/28/2020 | 10060   |                                      | 1,000.00                              | -1 000,00 | USD      |

Följande kassarabattdatum och belopp är tillgängliga för denna faktura.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvaluta |
|--------------------|----------------------|--------------------------------|
| 7/3/2020           | 20.00                | 980.00                         |
| 7/12/2020          | 10,00                | 990.00                         |
| 7/25/2020          | 0,00                 | 1,000.00                       |

## <a name="payment-on-july-2"></a>Betalning den 2 juli
Den 2 juli vill April betala 300,00 mot den här fakturan. Hon skapar en enstaka betalning genom att använda sidan **Betalningsjournal** i Leverantörsreskontra. Hon lägger till en rad för leverantör 3054 och anger ett betalningsbelopp på **300,00**. April öppnar sedan sidan **Kvitta transaktioner** så att hon kan välja den faktura som ska kvittas. Hon uppdaterar värdet i fältet **Belopp att kvitta** till **300,00** och noterar att värdet i fältet **Kassarabattbelopp att utnyttja** ändras till **6,12**. Eftersom den här betalningen görs i den första rabattperioden, utnyttjas en rabatt på 2 procent.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 300,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/02/2020 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -6,12     |

Eftersom en kassarabatt är tillgänglig, vill April ändra betalningsbeloppet, så att det totala kvittade beloppet är 300,00 för både betalningen och kassarabatten. Hon ändrar värdet i fältet **Belopp att kvitta** till **294,00** och noterar att värdet i fältet **Kassarabattbelopp att utnyttja** ändras till **6,00**.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 294.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/02/2020 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -6,00     |

April bokför betalningen. På sidan **Leverantörstransaktioner** kan hon visa den här transaktionen. Hon ser att 300,00 har tillämpats för fakturan. Det här beloppet inkluderar en rabatt på 6,00. Därför är det återstående saldot 700,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294.00                               |                                       | 0,00    | USD      |
| RAB-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Betalning den 8 juli
Den 8 juli gör April en ytterligare betalning mot fakturan. För att ange beloppet öppnar hon sidan **Kvitta transaktioner** och klickar på fliken **Kassarabatt**. Hon ser datum och belopp för de två två kassarabatter som är tillgängliga. Eftersom den här betalningen görs i den andra rabattperioden, är en rabatt på 1 procent eller 5,00. Detta belopp beräknas som halva 1 procents rabatten på 1 000,00 eller halva på 10,00.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvaluta |
|--------------------|----------------------|--------------------------------|
| 7/3/2020           | 20.00                | 680,00                         |
| 7/12/2020          | 10,00                | 690,00                         |
| 7/25/2020          | 0,00                 | 700.00                         |

April bestämmer dig för att betala 495,00 och ta kassarabatten 5,00. Därför är det totala beloppet som ska kvittas 500,00.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 495.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/12/2020 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | -6,00     |
| Kassarabattbelopp att utnyttja | -5,00     |

På sidan **Leverantörstransaktioner** ser April att det nya saldot är 200,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294.00                               |                                       | 0,00    | USD      |
| RAB-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2020 |         | 495.00                               |                                       | 0,00    | USD      |
| RAB-10061 | 7/12/2020 |         | 5.00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Betalning den 20 juli
Den 20 juli skapar April en slutbetalning på 200,00. Ingen rabatt utnyttjas, eftersom betalningen görs efter båda rabattperioder. Saldot för fakturan är 0,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294.00                               |                                       | 0,00    | USD      |
| RAB-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2020 |         | 495.00                               |                                       | 0,00    | USD      |
| RAB-10061 | 7/12/2020 |         | 5.00                                 |                                       | 0,00    | USD      |
| APP-10062  | 7/20/2020 |         | 200.00                               |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
