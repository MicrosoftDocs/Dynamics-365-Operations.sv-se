---
title: "Kvitta en leverantörsbetalning och hela slutbetalningen före rabattdatumet"
description: "Det här avsnittet innehåller en genomgång av ett scenario där flera delbetalningar görs för en leverantörsfaktura i vilken en kassarabatt har utnyttjats."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8436f7456f7a19320afa83ceb970d9cd0c64ac68
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Kvitta en leverantörsbetalning och hela slutbetalningen före rabattdatumet

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en genomgång av ett scenario där flera delbetalningar görs för en leverantörsfaktura i vilken en kassarabatt har utnyttjats.

Fabrikam köper varor från leverantör 3064. Leverantören ger Fabrikam en kassarabatt på 1 procent fakturan betalas inom 14 dagar. Fakturor måste betalas inom 30 dagar. Leverantören ger också Fabrikam kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för leverantörsreskontra**. Den 25 juni registrerar April en faktura på 1 000,00 för leverantör 3064.

## <a name="vendor-invoice-on-june-25"></a>Leverantörsfaktura den 25 juni
Den 25 juni registrerar och bokför April en faktura på 1 000,00 för leverantör 3064. April kan visa den här transaktionen på sidan **Leverantörstransaktioner**.

| Verifikation   | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Fakt- 10010 | 2015/06/25 | 10010   |                                      | 1 000,00                              | -1 000,00 | USD      |

Från sidan **Leverantörer** öppnar Anna sidan **Kvitta transaktioner**. Hon kan använda sidan **Kvitta transaktioner** för att visa datum och belopp för kassarabatter. Förfallodatumet är 25 juli och en kassarabatt på -10,00 är tillgänglig om fakturan betalas den 9 juli.

| Markera | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Fakt- 10010 | 3064    | 2015/06/25 | 2015/07/25 | 10010   | 1 000,00                       | USD      | 990,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2015 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -10.00    |

April klickar på fliken **Kassarabatt** för att visa rabattbelopp.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvalutan |
|--------------------|----------------------|--------------------------------|
| 2015/07/09           | 10,00                | 990,00                         |
| 2015/07/25          | 0,00                 | 1 000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Delbetalning den 1 juli genom att använda sidan Kvitta transaktioner
April kan skapa en betalningsjournal för den här betalningen, genom att öppna sidan **Betalningsjournal** i Leverantörsreskontra. Hon skapar en ny journal och anger en rad för leverantören 3064. Hon öppnar sedan sidan **Kvitta transaktioner** så att hon kan välja den faktura som ska kvittas. April markerar fakturan och ändrar värdet i fältet **Belopp att kvitta** till **-500,00**. Hon ser igen att värdet i fältet **Kassarabattbelopp** är **-10,00** för hela fakturan, och värdet i **Kassarabattbelopp att utnyttja** är **-5,05**. Därför kvittar April -505,05 av den här fakturan.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 2015/06/25 | 2015/07/25 | 10010   | 1 000,00                       | USD      | -500,00          |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2015 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -5,05     |

April vill infoga exakt halva fakturan. Därför ändrar hon fakturan och ändrar värdet i fältet **Belopp att kvitta** till **-495,00**. Det totala beloppet som ska kvittas är nu 500,00. Det här beloppet inkluderar en kassarabatt på -5,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 2015/06/25 | 2015/07/25 | 10010   | 1 000,00                       | USD      | -495,00          |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2015 |
| Kassarabattbelopp         | -10.00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -5,00     |

April stänger sidan **Kvitta transaktioner**. En betalningsrad för 495,00 skapas i journalen och sedan bokför April journalen. April kan granska leverantörstransaktionerna på sidan **Leverantörstransaktioner**. Hon ser att fakturan har saldot -500,00. Hon ser också en betalning på 495,00 och en kassarabatt på 5,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10010  | Faktura          | 2015/06/25 | 10010   |                                      | 1 000,00                              | -500,00 | USD      |
| APP-10010  | Betalning          | 2015/07/01  |         | 495,00                               |                                       | 0,00    | USD      |
| RAB-10010 | Kassarabatt    | 2015/07/01  |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-amount-paid-on-july-8"></a>Resterande belopp betalas den 8 juli
April betalar resten av fakturan för leverantör 3064 den 8 juli, vilket är efter kassarabattperioden. April skapar betalningsjournalen den 8 juli och markerar transaktionen för kvittning. Hon ser att beloppet som måste kvittas är 495,00. Värdet i fältet **Beräknad kassarabatt** är **-5,00**, eftersom rabatten på 5,00 utnyttjades tidigare.

|                         |        |
|-------------------------|--------|
| Markerad summa            | 495,00 |
| Uppskattad kassarabatt | -5,00  |

Information om den valda transaktionen visas i rutnätet på sidan **Kvitta öppna transaktioner**.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 2015/06/25 | 2015/07/25 | 10010   | 1 000,00                       | USD      | 495,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/09 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 5,00      |
| Kassarabattbelopp att utnyttja | 5,00      |

April bokför betalningsjournalen och granskar leverantörstransaktioner på sidan **Leverantörstransaktioner**. Saldot för fakturan är nu 0,00 och April ser de två betalningarna och de två kassarabatterna.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Fakt- 10010  | Faktura          | 2015/06/25 | 10010   |                                      | 1 000,00                              | 0,00    | USD      |
| APP-10010  |  Betalning         | 2015/07/01  |         | 495.00                               |                                       | 0,00    | USD      |
| RAB-10010 | Kassarabatt    | 2015/07/01  |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10011  | Betalning          | 2015/07/08  |         | 495,00                               |                                       | 0,00    | USD      |
| RAB-10011 | Kassarabatt    | 2015/07/08  |         | 5,00                                 |                                       | 0,00    | USD      |






