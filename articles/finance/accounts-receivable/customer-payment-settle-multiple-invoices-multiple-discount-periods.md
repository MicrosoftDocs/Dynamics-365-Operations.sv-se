---
title: Använd en (1) betalning för att kvitta flera fakturor som omfattar flera rabattperioder
description: Den här artikeln visar hur flera fakturor betalas när varje faktura är kvalificerad för en kassarabatt. Scenarierna i den här artikeln visar hur de utnyttjade kassarabatterna varierar beroende på när betalningen görs.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6bf321a5b0511295f2500f10cdffa9ff6f043bff
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780607"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>Använd en (1) betalning för att kvitta flera fakturor som omfattar flera rabattperioder

[!include [banner](../includes/banner.md)]

Den här artikeln visar hur flera fakturor betalas när varje faktura är kvalificerad för en kassarabatt. Scenarierna i den här artikeln visar hur de utnyttjade kassarabatterna varierar beroende på när betalningen görs.

Fabrikam säljer varor till kunden 4032. Fabrikam erbjuder en kassarabatt på 1 procent om fakturan betalas inom 14 dagar. Fabrikam erbjuder även kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för kundreskontra**.

## <a name="invoices"></a>Fakturor
Kund 4032 har tre fakturor som summerar 3 000,00:

-   Faktura FTI-10040, för 1 000,00, har angetts för den 15 maj. Denna faktura är berättigad till en kassarabatt på 1 procent om fakturan betalas inom 14 dagar.
-   Faktura FTI-10041, för 1 000,00, har angetts för den 25 juni. Denna faktura är berättigad till en kassarabatt på 1 procent om fakturan betalas inom 14 dagar.
-   Faktura FTI-10042, för 1 000,00, har angetts för den 25 juni. Denna faktura är berättigad till en kassarabatt på 2 % om betalningen sker i fem dagar och 1 procent rabatt om betalningen sker i 14 dagar.

## <a name="settle-all-invoices-on-june-29"></a>Kvitta alla fakturor den 29 juni
Om Arnie skapar en betalningsjournal helt för att kvitta dessa fakturor den 29 juni är betalningen 2 970,00. Summan av alla rabattbelopp är 30,00. Arnie skapar en betalning för kund 4032 och öppnar sedan sidan **Kvitta transaktioner**. På sidan **Kvitta transaktioner** väljer Arnie alla tre fakturaraderna för kvittning:

-   Betalningen för faktura FTI-10040 är 1 000,00. Ingen kassarabatt har utnyttjats.
-   Betalningen för faktura FTI-10041 är 990,00. En kassarabatt på 1 procent eller 10,00 utnyttjas.
-   Betalningen för faktura FTI-10042 är 980,00. En kassarabatt på 2 procent eller 20,00 utnyttjas.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum   | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|------|----------|-----------|---------|-----------|-----------|---------|---------------------|---------------------|----------|------------------|
| Markerad     | Normal      | FTI-10040 | 4032    | 5/15/2020 | 6/15/2020 | 10040   | 1,000.00  |                    | USD      | 1,000.00         |
| Markerad     | Normal      | FTI-10041 | 4032    | 6/25/2020 | 7/25/2020 | 10041   | 1,000.00  |                    | USD      | 990.00           |
| Vald och markerad | Normal      | FTI-10042 | 4032    | 6/25/2020 | 7/25/2020 | 10042   | 1,000.00    |              | USD      | 980.00           |

När betalningen har bokförts är kundsaldot 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Kvitta alla fakturor den 1 juli
Om Arnie skapar en betalningsjournal helt för att kvitta dessa fakturor den 1 juli är betalningen 2 980,00. Arnie skapar en betalning för kund 4032 och öppnar sedan sidan **Kvitta transaktioner**. På sidan **Kvitta transaktioner** väljer Arnie alla tre fakturaraderna för kvittning:

-   Betalningen för faktura FTI-10040 är 1 000,00. Ingen kassarabatt har utnyttjats.
-   Betalningen för faktura FTI-10041 är 990,00. En kassarabatt på 1 procent eller 10,00 utnyttjas.
-   Betalningen för faktura FTI-10042 är 990,00. En kassarabatt på 1 procent eller 10,00 utnyttjas. Även om 1 juli infaller efter perioden som kvalificerar för 2 procentsrabatten, sker den fortfarande inom perioden som kvalificerar för 1 procentsrabatten.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|---------|-----------|---------|-----------|-----------|---------|--------------------|------------------|----------|------------------|
| Markerad         | Normal            | FTI-10040 | 4032    | 5/15/2020 | 6/15/2020 | 10040   | 1,000.00         |                | USD      | 1,000.00         |
| Markerad                 | Normal            | FTI-10041 | 4032    | 6/25/2020 | 7/25/2020 | 10041   | 1,000.00  |               | USD      | 990.00           |
| Vald och markerad | Normal            | FTI-10042 | 4032    | 6/25/2020 | 7/25/2020 | 10042   | 1,000.00  |             | USD      | 990.00           |

## <a name="partial-settlement-on-june-29"></a>Delkvittning den 29 juni
Kund 4032 kan betala ett delbelopp som till exempel halva av varje faktura. Arnie skapar en betalning för kund 4032 och öppnar sedan sidan **Kvitta transaktioner**. På sidan **Kvitta transaktioner** väljer Arnie alla tre fakturaraderna för kvittning. På varje rad anger Arnie kvittningsbeloppet baserat på instruktionerna som kunden har tillhandahållit. När Arnie väljer en rad ser han rabattbeloppet för raden och det kassarabattsbelopp som utnyttjas. Eftersom kunden betalar halva fakturan ser Arnie att värdet i fältet **Kassarabattbelopp** för FTI-10042 är **20,00**, men värdet i **Utnyttjad kassarabatt** är **10,00**. Betalningsbeloppet är 1 485,00.

| Markera   | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|-------------|-------------------|-----------|---------|-----------|-----------|---------|-----------|------------------|----------|------------------|
| Markerad   | Normal       | FTI-10040 | 4032    | 5/15/2020 | 6/15/2020 | 10040   | 1,000.00        |               | USD      | 500.00           |
| Markerad                 | Normal            | FTI-10041 | 4032    | 6/25/2020 | 7/25/2020 | 10041   | 1,000.00     |     | USD      | 495.00           |
| Vald och markerad | Normal            | FTI-10042 | 4032    | 6/25/2020 | 7/25/2020 | 10042   | 1,000.00     |         | USD      | 490,00           |

Arnie kan även manuellt ange betalningsbeloppet på 1 485,00 innan han öppnar sidan **Kvitta transaktioner**. Om Arnie registrerar betalningsbeloppet manuellt och markerar alla tre transaktioner, men inte justerar värdet i fältet **Kvittningsbelopp** för varje transaktion, får han följande meddelande när sidan stängs:

> Det total beloppet av markerade transaktioner skiljer sig från journalbeloppet. Vill du ändra journalbeloppet?

Om Arnie vill att betalningsbeloppet endast är 1 485,00 klickar han på **Nej** och bokför sedan journalen. Transaktionerna kvittas enligt följande:

1.  Faktura FTI-10040 kvittas fullständigt för 1 000,00 eftersom den registrerades 15 maj och är den äldsta fakturan. Ingen kassarabatt har utnyttjats. Återstående belopp på betalningstransaktionen är 485,00.
2.  Faktura FTI-10041 kvittas inte alls. Fakturor FTI-10041 och FTI-10042 registrerades på samma datum. Men 1 procents rabatt är tillgänglig för faktura FTI-10041, och 2 procents rabatt är tillgänglig för faktura FTI-10042. Eftersom en bättre rabatt är tillgängliga för faktura FTI-10042, kvittas de återstående 485,00 mot faktura FTI-10042.
3.  Faktura FTI-10042 kvittas mot de återstående 485,00. Fabrikam erbjuder delrabatter. I detta fall är rabatten 9,90 (= 485,00 ÷ 0,98 × 0,02). Beloppet (485,00) delas med 0,98, eftersom det finns 2 procents rabatt (därför betalar kunden 98 procent av fakturan.) Resultatet multipliceras sedan med rabattprocenten som är 2 procent. Betalningen på 485,00 plus rabatten på 9,90 motsvarar 494,90. Beloppet för den ursprungliga fakturan var 1 000,00. Därför har transaktionen ett saldo på 505,10 (= 1 000,00 – 494,90).

Arnie kan visa den här informationen på sidan **Kundtransaktioner**.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Faktura          | 5/15/2020 | 10040   | 1,000.00                             |                                       | 0,00     | USD      |
| FTI-10041  | Faktura          | 6/25/2020 | 10041   | 1,000.00                             |                                       | 1,000.00 | USD      |
| FTI-10042  | Faktura          | 6/25/2020 | 10042   | 1,000.00                             |                                       | 505.10   | USD      |
| ARP-10040  | Betalning          | 6/29/2020 |         |                                      | 1 485,00                              | 0,00     | USD      |
| RAB-10040 | Kassarabatt    | 6/29/2020 |         |                                      | 9,90                                  | 0,00     | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
