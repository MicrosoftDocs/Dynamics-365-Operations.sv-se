---
title: Kvitta en leverantörsdelbetalning som har rabatter på kreditfakturor
description: Det här avsnittet innehåller genomgång av ett scenario där en kreditnota kvittas mot en faktura.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e634796c7143c14a872c721f298f3ab28cbddd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827852"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>Kvitta en leverantörsdelbetalning som har rabatter på kreditfakturor

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller genomgång av ett scenario där en kreditnota kvittas mot en faktura.

Fabrikams leverantörer ger kassarabatter på kreditnotor. Leverantör 3050 ger Fabrikam en kassarabatt på en procent, om en faktura betalas inom 14 dagar.

## <a name="invoice-and-credit-memo"></a>Faktura och kreditnota
Den 29 juni skapar April en faktura för 1 000,00 för leverantör 3050. Den 2 juli skapar hon en kreditfaktura för 200,00. Från sidan **Leverantörer** öppnar Anna sidan **Kvitta transaktioner**. Hon kan använda sidan **Kvitta transaktioner** när hon markera både kreditnotan och fakturan för kvittning. En rabatt på 2,00 beräknas på kreditnotan. Därför reduceras det totala värdet på kreditnotan till 198,00.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad                 | Normal            | Fakt 10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070   | -1 000,00                      | USD      | -990,00          |
| Vald och markerad | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 |         | 200,00                         | USD      | 198,00           |

Information om rabatten för kreditnotan visas längst ned på sidan **Kvitta öppna transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 13/7/2015 |
| Kassarabattbelopp         | 2.00      |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 2,00      |

Anna klickar på **Bokför**. Sedan granskar hon den slutförda kvittningen. Anna ser att 198,00 på kreditnotan användes och att en rabatt på 2,00 togs ut. Därför är summan 200,00.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura  | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Vald och markerad | Normal            | Fakt 10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070    | -1 000,00                      | USD      | -200,00          |
| Markerad                 | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

Anna kan granska leverantörstransaktionerna på sidan **Leverantörstransaktioner** genom att markera en leverantör på sidan **Alla leverantörer** och sedan klicka på **Transaktioner** i åtgärdsfönstret. På den här sidan ser Anna att fakturan har saldot -800,00. Hon ser också en kreditfaktura för 198,00 och en rabatt på 2,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt 10070  | Faktura          | 29/6/2015 | 10070   |                                      | 1 000,00                              | -800,00 | USD      |
| Fakt 10071  |                  | 2/7/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| RAB-10071 |  Kassarabatt   | 2/7/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| RAB-10071 |  Kassarabatt   | 2/7/2015  |         |                                      | 2,00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]