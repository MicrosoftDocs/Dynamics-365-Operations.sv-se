---
title: "Kvitta en delvis kundbetalning före rabattdatumet med en slutlig betalning efter rabattdatumet"
description: "Den här artikeln diskuterar effekten av kvittning av betalningar till fakturor för kunder. Scenariot fokuserar på effekterna i reskontran, inte i redovisningen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: f3234bf607ef9ce1643226894716b975a2c2a7b9
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-customer-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Kvitta en delvis kundbetalning före rabattdatumet med en slutlig betalning efter rabattdatumet

Den här artikeln diskuterar effekten av kvittning av betalningar till fakturor för kunder. Scenariot fokuserar på effekterna i reskontran, inte i redovisningen.

Fabrikam säljer varor till kunden 4027. Fabrikam erbjuder en kassarabatt på 1 procent om fakturan är betald 14 dagar. Fakturor måste betalas inom 30 dagar. Fabrikam erbjuder även kassarabatter på delbetalningar. Kvittning parametrar finns i den **parametrar för kundreskontra** sida.

## <a name="invoice"></a>Faktura
Den 25 juni Arnie registrerar och bokför en faktura för 1 000,00 för kund 4027. Arnie kan visa fakturan med de **transaktioner** knappen i den **kunder** sida.

| Verifikation   | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Faktura          | 2015/06/25 | 10020   | 1 000,00                             |                                       | 1 000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Delbetalning före kassarabattdatumet
Den 2 juli betalar kund 4027 en delbetalning på 297,00 för fakturan. Betalningen är berättigad till en kassarabatt, eftersom Fabrikam erbjuder kassarabatter på delbetalningar, och delbetalningen görs för kassarabatten. Därför utnyttjar kund 4027 en kassarabatt 3,00. Arnie registrerar betalningen för kund 4027, genom att använda betalningsjournalen. Arnie öppnar sedan sidan **Kvitta transaktioner** så att han kan välja den faktura som ska kvittas.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10020 | 4027    | 2015/06/25 | 2015/07/25 | 10020   | 1 000,00                             | USD      | 297,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Om du inte ändrar värdet för **Kvitta transaktioner** till **297,00**, kommer värdet för Kassarabattbelopp att skilja sig. Dock 3,00 anses kassarabatten när betalningen bokförs eftersom kvittning justeras automatiskt den ** kvittningsbeloppet ** värde åt dig.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 7/09/2015 |
| Kassarabattbelopp         | 10,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 3,00      |

Arnie bokför den här betalningen. Fakturan har nu ett saldo på 700,00. Följande transaktioner kan ses för kunden.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 2015/06/25 | 10020   | 1 000,00                             |                                       | 700,00  | USD      |
| ARP-10020  |  Betalning         | 2015/07/01  |         |                                      | 297,00                                | 0,00    | USD      |
| RAB-10020 |  Kassarabatt   | 2015/07/01  |         |                                      | 3,00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Återstående betalning efter kassarabattdatumet
Den 11 april betalar kund 4027 resten av fakturan, vilket är efter rabattperioden. På sidan **Kvitta öppna transaktioner** visas inget rabattbelopp i fältet **Beräknad kassarabatt** och värdet i fältet **Kassarabattbelopp** är **0,00**. När kund 4027 betalar de återstående 700,00, ges ingen ytterligare rabatt.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10020 | 4027    | 2015/06/25 | 2015/07/25 | 10020   | 700,00                               | USD      | 700,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/09 |
| Kassarabattbelopp         | 0,00      |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 3,00      |
| Kassarabattbelopp att utnyttja | 0,00      |

Om Arnie ändrar värdet i fältet **Använd kassarabatt** till **Alltid**, kommer inställningen **Beräkna kassarabatter för delbetalningar** att åsidosättas och kassarabatten utnyttjas. Betalningsbeloppet ändras 693,00 och rabatten är de återstående 7,00.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Markerad | Alltid            | FTI-10020 | 4027    | 2015/06/25 | 2015/07/25 | 10020   | 700,00                               |                                       | USD      | 693,00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/09 |
| Kassarabattbelopp         | 07:00      |
| Använd kassarabatt            | Alltid    |
| Utnyttjad kassarabatt          | 3,00      |
| Kassarabattbelopp att utnyttja | 07:00      |

Arnie ändrar värdet i fältet **Använd kassarabatt** tillbaka till **Normal**, eftersom han inte låter den här kunden utnyttja den återstående kassarabatten på 7,00. Arnie bokför sedan betalningen. När han öppnar sidan **Kundtransaktioner** ser han att fakturan har ett saldo på 0,00. Han ser också att det finns två betalningar. En betalning på 297,00 och med 3,00 kassarabatt och den andra betalningen på 700,00.

| Verifikation    | transaktionstyp | Datum      | Faktura | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 2015/06/25 | 10020   | 1 000,00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 2015/07/01  |         |                                      | 297,00                                | 0,00    | USD      |
| RAB-10020 |                  | 2015/07/01  |         |                                      | 3,00                                  | 0,00    | USD      |
| ARP-10021  |                  | 2015/07/11 |         |                                      | 700,00                                | 0,00    | USD      |




