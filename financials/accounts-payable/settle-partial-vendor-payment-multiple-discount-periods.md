---
title: "Kvitta en partiell leverantörsbetalning med flera Rabattperioderna"
description: "Den här artikeln går igenom ett scenario där flera delbetalningar görs till en leverantör som erbjuder flera kassarabatter."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 4fd4fdf6150d4160d07d8a9b8027a40d1c22cf7d
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Kvitta en partiell leverantörsbetalning med flera Rabattperioderna

Den här artikeln går igenom ett scenario där flera delbetalningar görs till en leverantör som erbjuder flera kassarabatter. 

Leverantör 3054 erbjuder Fabrikam en kassarabatt på 2 procent, om en faktura betalas inom fem dagar och en kassarabatt på 1 procent, om fakturan betalas inom 14 dagar.

## <a name="invoice"></a>Faktura
28 juni skapa en faktura på 1 000,00 för leverantör av 3054 April. April kan visa den här transaktionen på sidan **Leverantörstransaktioner**.

| Verifikation   | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Fakt- 10060 | 2015/06/28 | 10060   |                                      | 1 000,00                              | -1 000,00 | USD      |

Följande kassarabattdatum och belopp är tillgängliga för denna faktura.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvalutan |
|--------------------|----------------------|--------------------------------|
| 2015/07/03           | 20,00                | 980,00                         |
| 2015/07/12          | 10,00                | 990,00                         |
| 2015/07/25          | 0,00                 | 1 000,00                       |

## <a name="payment-on-july-2"></a>Betalning den 2 juli
Den 2 juli vill April betala 300.00 mot fakturan. Hon skapar en betalning direkt med hjälp av den **betalningsjournal** sida i Leverantörsreskontra. Hon lägger till en rad för leverantör 3054 och anger ett betalningsbelopp på **300,00**. April öppnar sedan sidan **Kvitta transaktioner** så att hon kan välja den faktura som ska kvittas. Hon uppdaterar värdet i fältet **Belopp att kvitta** till **300,00** och noterar att värdet i fältet **Kassarabattbelopp att utnyttja** ändras till **6,12**. Eftersom den här betalningen görs i den första rabattperioden, utnyttjas en rabatt på 2 procent.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 2015/06/28 | 2015/07/28 | 10060   | 1 000,00                       | USD      | 300,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/02 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -6,12     |

Eftersom en kassarabatt är tillgänglig, vill April ändra betalningsbeloppet, så att det totala kvittade beloppet är 300,00 för både betalningen och kassarabatten. Hon ändrar värdet i fältet **Belopp att kvitta** till **294,00** och noterar att värdet i fältet **Kassarabattbelopp att utnyttja** ändras till **6,00**.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 2015/06/28 | 2015/07/28 | 10060   | 1 000,00                       | USD      | 294,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/02 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -6,00     |

April bokför betalningen. På sidan **Leverantörstransaktioner** kan hon visa den här transaktionen. Hon ser att 300,00 har tillämpats för fakturan. Det här beloppet inkluderar en rabatt på 6,00. Därför är det återstående saldot 700,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 2015/06/28 | 10060   |                                      | 1 000,00                              | -700,00 | USD      |
| APP-10060  | 2015/07/02  |         | 294.00                               |                                       | 0,00    | USD      |
| RAB-10060 | 2015/07/02  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Betalning den 8 juli
Den 8 juli gör April en ytterligare betalning mot fakturan. Om du vill ange beloppet öppnar hon sidan **Kvitta transaktioner** och klickar sedan på fliken **Kassarabatt**. Hon ser data och belopp för de två kassarabatterna som är tillgängliga. Eftersom den här betalningen görs i den andra rabattperioden, är en rabatt på 1 procent eller 5,00. Detta belopp beräknas som halva 1 procents rabatten på 1 000,00 eller halva på 10,00.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvalutan |
|--------------------|----------------------|--------------------------------|
| 2015/07/03           | 20,00                | 680,00                         |
| 2015/07/12          | 10,00                | 690,00                         |
| 2015/07/25          | 0,00                 | 700,00                         |

April bestämmer dig för att betala 495,00 och ta kassarabatten 5,00. Därför är det totala beloppet som ska kvittas 500,00.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10060 | 3054    | 2015/06/28 | 2015/07/28 | 10060   | 1 000,00                       | USD      | 495,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/12 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | -6,00     |
| Kassarabattbelopp att utnyttja | -5,00     |

På sidan **Leverantörstransaktioner** ser April att det nya saldot är 200,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 2015/06/28 | 10060   |                                      | 1 000,00                              | -200,00 | USD      |
| APP-10060  | 2015/07/02  |         | 294,00                               |                                       | 0,00    | USD      |
| RAB-10060 | 2015/07/02  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 2015/07/12 |         | 495,00                               |                                       | 0,00    | USD      |
| RAB-10061 | 2015/07/12 |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Betalning den 20 juli
Den 20 juli skapar April en slutbetalning på 200,00. Ingen rabatt utnyttjas, eftersom betalningen görs efter båda rabattperioder. Saldot för fakturan är 0,00.

| Verifikation    | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10060  | 2015/06/28 | 10060   |                                      | 1 000,00                              | -200,00 | USD      |
| APP-10060  | 2015/07/02  |         | 294,00                               |                                       | 0,00    | USD      |
| RAB-10060 | 2015/07/02  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 2015/07/12 |         | 495,00                               |                                       | 0,00    | USD      |
| RAB-10061 | 2015/07/12 |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10062  | 2015/07/20 |         | 200,00                               |                                       | 0,00    | USD      |



