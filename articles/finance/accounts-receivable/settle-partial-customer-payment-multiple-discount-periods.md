---
title: Kvitta en delkundsbetalning som har flera rabattperioder
description: Det inlägg visar hur delvisa kundbetalningar kvittas om det finns flera rabattperioder.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 21600c0815da99314dcbb8f123449c2ae93a3c1a
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027490"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Kvitta en delkundsbetalning som har flera rabattperioder

[!include [banner](../includes/banner.md)]

Det inlägg visar hur delvisa kundbetalningar kvittas om det finns flera rabattperioder.

Fabrikam erbjuder kunden 4031 två kassarabattperioder. Kunden får en kassarabatt på 2 procent, om en faktura betalas inom fem dagar och en kassarabatt på 1 procent, om fakturan betalas inom 14 dagar. Fabrikam erbjuder även kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för kundreskontra**.

## <a name="invoice"></a>Faktura
Den 25:e juni registrerar och bokför Arnie en faktura på 1 000,00 för kund 4031. När han granskar kassarabatter för den här fakturan ser Arnie att kund 4031 ska få 20,00 rabatt om fakturan betalas senast den 30 juni. Om fakturan betalas den 9 juli får kunden 10,00 rabatt.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvalutan |
|--------------------|----------------------|--------------------------------|
| 2015/06/30          | 20,00                | 980,00                         |
| 2015/07/09           | 10,00                | 990,00                         |
| 2015/07/25          | 0,00                 | 1 000,00                       |

Arnie kan visa den här transaktionen på sidan **Kundtransaktioner**.

| Verifikation   | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Faktura          | 2015/06/25 | 10030   | 1 000,00                             |                                       | 1 000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Delbetalning före kassarabattdatumet
Den 28 juni gör kund 4031 en delbetalning på 294,00. Eftersom 28 juni infaller inom den första kassarabattperioden, får kunden en rabatt på 6,00. På sidan **Kvitta transaktioner** är värdet för **Kassarabattbelopp** 20,00 och värdet för **Kassarabattbelopp att utnyttja** 6,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10030 | 4031    | 2015/06/25 | 2015/07/25 | 10030   | 1 000,00                       | USD      | 294,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Om du inte ändrar värdet för **Kvitta transaktioner** till **294,00**, kommer värdet för **Kassarabattbelopp** att skilja sig. Men 6,00 kommer att utnyttjas som kassarabatt när betalningen bokförs, eftersom kvittningen justerar automatiskt värdet för **Belopp att kvitta**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/06/30 |
| Kassarabattbelopp         | 20,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 6,00      |

När Arnie har bokfört betalningen är fakturasaldot 700,00.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Delbetalning före det andra kassarabattdatumet
Kunden betalar resten av fakturabeloppet den 8 juli. En rabatt på 7,00 utnyttjas (1 procent), eftersom betalningen gjordes inom den andra kassarabattperioden.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10030 | 4031    | 2015/06/25 | 2015/07/25 | 10030   | 700,00                               |                                       | USD      | 693,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/09 |
| Kassarabattbelopp         | 30,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 6,00      |
| Kassarabattbelopp att utnyttja | 07:00      |

Fakturasaldot är nu 0,00. Arnie kan visa den här informationen på sidan **Kundtransaktioner**.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Faktura          | 2015/06/25 | 10030   | 1 000,00                             |                                       | 0,00    | USD      |
| ARP-10030  |  Betalning         | 2015/06/28 |         |                                      | 294,00                                | 0,00    | USD      |
| RAB-10030 |  Kassarabatt   | 2015/06/28 |         |                                      | 6,00                                  | 0,00    | USD      |
| ARP-10031  |  Betalning         | 2015/07/08  |         |                                      | 693,00                                | 0,00    | USD      |
| RAB-1031  |  Kassarabatt   | 2015/07/08  |         |                                      | 07:00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]