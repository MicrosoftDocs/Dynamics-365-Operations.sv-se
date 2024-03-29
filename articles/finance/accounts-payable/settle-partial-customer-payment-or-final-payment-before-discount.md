---
title: Kvitta del- och slutbetalningar helt före rabattdatumet
description: Den här artikeln tillhandahåller scenarier som visar hur du registrerar delbetalningar för en kund och tar kassarabatter inom kassarabattperioden.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
ms.openlocfilehash: a8da366b1e770ea649603ae85d4acc5e377ed9fb
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780562"
---
# <a name="settle-partial-and-final-payments-in-full-before-the-discount-date"></a>Kvitta del- och slutbetalningar helt före rabattdatumet

[!include [banner](../includes/banner.md)]

Den här artikeln tillhandahåller scenarier som visar hur du registrerar delbetalningar för en kund och tar kassarabatter inom kassarabattperioden.

Fabrikam säljer varor till kunden 4028. Fabrikam erbjuder en kassarabatt på 1 procent om fakturan betalas inom 14 dagar. Fakturor måste betalas inom 30 dagar. Fabrikam erbjuder även kassarabatter på delbetalningar. Kvittningsparametrar finns på sidan **Parametrar för kundreskontra**.

## <a name="customer-invoice"></a>Kundfaktura
Den 25 juni registrerar och bokför Arnie en faktura på 1 000,00 för kund 4028. Arnie kan visa den här transaktionen på sidan **Kundtransaktioner**.

| Verifikation   | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Faktura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 1,000.00 | USD      |

Från sidan **Kund** eller **Kundtransaktioner** kan Arnie öppna sidan **Kvitta transaktioner** för att visa datum och belopp av kassarabatter som är tillgängliga för fakturan. Förfallodatumet är 25 juli och en kassarabatt på 10,00 är tillgänglig om fakturan betalas den 9 juli.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 990.00           |

Informationen visas längst ned på sidan **Kvitta transaktioner** för den markerade fakturan.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 10,00     |

Arnie klickar på fliken **Kassarabatt** för att visa rabattbelopp.

| Kassarabattdatum | Kassarabattbelopp | Belopp i transaktionsvaluta |
|--------------------|----------------------|--------------------------------|
| 7/9/2020           | 10,00                | 990.00                         |
| 7/25/2020          | 0,00                 | 1,000.00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Delbetalning genom att använda sidan Ange kundbetalningar
Kund 4028 skickar en betalning på 500,00 den 1 juli. För att ange den här betalningen klickar inte Arnie på **Rader**. I stället registrerar Arnie betalningen genom att skapa en ny betalningsjournal och öppnar sedan sidan **Ange kundbetalningar**. Arnie anger betalningsinformationen och markerar fakturan som har angetts. När Arnie anger **500,00** som belopp anger han även **500,00** i fältet **Belopp att betala** i rutnätet. Eftersom Fabrikam tillåter en kassarabatt på delbetalningar ser Arnie att en delkassarabatt på 5,05 också ska utnyttjas. Beräkningen av den här rabatten är 500,00 ÷ 0,99 × 0,01 = 5,05. (I den här beräkningen delas 500,00 med 0,99 eftersom det är 1 procents rabatt. Därför betalar kunden 99 procent av fakturan. Resultatet multipliceras sedan med rabattprocenten som är 1 procent, eller 0,01. Om kunden utnyttjar hela rabatten på 10,00 kommer beloppet som ska kvittas att vara 990,00.) Rabattinformation visas i rutnätet längst ned på sidan **Ange kundbetalningar**.

| Kassarabattbelopp att utnyttja | Utnyttjad kassarabatt | Belopp att betala |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500.00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Delbetalning genom att använda journalraderna
Istället för att öppna sidan **Ange kundbetalningar** i betalningsjournalen, kan Arnie klicka på **Rader** för att ange en betalning. Betalningsjournalen visas där Arnie registrerar en rad för kund 4028. Arnie öppnar sedan sidan **Kvitta transaktioner** så att han kan välja den faktura som ska kvittas. Arnie markerar fakturan och ändrar värdet i fältet **Belopp att kvitta** till **500,00**. Arnie ser igen att värdet i fältet **Kassarabattbelopp** är **10,00** för hela fakturan, och värdet i **Kassarabattbelopp att utnyttja** är **5,05**. Därför kvittar Arnie 505,05 av den här fakturan.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 500.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 5,05      |

Om kunden vill kvitta exakt halva fakturan, skickar in kunden en betalning på 495,00. I detta fall anger Arnie **495,00** i fältet **Belopp till att kvitta**. Kassarabatten på 5,00 ska också utnyttjas så att det totala kvittade beloppet blir 500,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 495.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 5,00      |

Arnie stänger sidan **Kvitta transaktioner**. En betalningsrad för 495,00 skapas i journalen och sedan bokför Arnie journalen. Arnie kan granska kundtransaktioner på sidan **Kundtransaktioner**. På den här sidan ser Arnie att fakturan har saldot 500,00. Arnie ser också en betalning på 495,00 och en rabatt på 5,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Faktura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 500.00  | USD      |
| ARP-10010  |  Betalning         | 7/1/2020  |         |                                      | 495.00                                | 0,00    | USD      |
| RAB-10010 |  Kassarabatt   | 7/1/2020  |         |                                      | 5.00                                  | 0,00    | USD      |

## <a name="payment-for-the-remaining-amount"></a>Betalning för återstående belopp
Kund 4028 betalar det resterande beloppet på 495,00 den 8 juli vilket infaller under kassarabattperioden. Arnie skapar betalningsjournalen den 8 juli och markerar transaktionen för kvittning. Arnie ser att beloppet som måste kvittas är 495,00. Värdet i fältet **Beräknad kassarabatt** är **5,00**, eftersom rabatten på 5,00 utnyttjades tidigare.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| Markerad summa            | 495,00 |
| Uppskattad kassarabatt | 5,00   |

Information om den valda transaktionen visas i rutnätet på sidan **Kvitta öppna transaktioner**.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 495.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2020 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 5,00      |
| Kassarabattbelopp att utnyttja | 5,00      |

Arnie bokför journalen och granskar kundtransaktioner på sidan **Kundtransaktioner**. Saldot för fakturan är nu 0,00 och Arnie ser de två betalningarna och de två kassarabatterna.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Faktura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10010  | Betalning          | 7/1/2020  |         |                                      | 495.00                                | 0,00    | USD      |
| RAB-10010 | Kassarabatt    | 7/1/2020  |         |                                      | 5.00                                  | 0,00    | USD      |
| ARP-10011  | Betalning          | 7/8/2020  |         |                                      | 495.00                                | 0,00    | USD      |
| RAB-10011 | Kassarabatt    | 7/8/2020  |         |                                      | 5.00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
