---
title: Dubbel rapportering
description: I det här avsnittet får du hjälp med ett exempel som visar hur du kan uppfylla kraven för både IFRS-rapportering (International Financial Reporting Standard) och lagstadgad rapportering i Tillgångsleasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c96730bea52a69f672f8936ebbcb24449940636
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713401"
---
# <a name="dual-reporting"></a>Dubbel rapportering

[!include [banner](../includes/banner.md)]

I det här avsnittet får du hjälp med ett exempel som visar hur du kan uppfylla kraven för både IFRS-rapportering (International Financial Reporting Standard) och lagstadgad rapportering i Tillgångsleasing. Det är viktigt att känna till bokföringsskikt i Microsoft Dynamics 365 Finance och det gör att exemplet blir lättare att förstå.

## <a name="example"></a>Exempel

I följande exempel redovisas en leasing enligt italiensk lagstadgad rapportering med hjälp av både kontantmetoden och IFRS-rapporteringsmetoder. Företaget måste upprätta tre räkenskapsböcker för både de italienska lagstadgade kraven och IFRS 16-kraven. En bok krävs för IFRS 16, en bok krävs för lagstadgade krav, och en bok krävs för att automatiskt återföra lagstadgade bokföringar. Räkenskapsböckerna ställs in på det sätt som visas i följande tabeller.

**IFRS 16-räkenskapsbok**

IFRS 16-boken har ställts in så att den överensstämmer med IFRS 16-redovisningsstandarden. Alla transaktioner som bokförs i den här boken kommer att bokföras i ett anpassat skikt.

| Namn                                    | Beskrivning    |
|-----------------------------------------|----------------|
| Typ av bok                               | IFRS 16        |
| Bokbeskrivning                        | IFRS 16        |
| Bokföringsskikt                           | Anpassat skikt 1 |
| Leasingtyp                              | Finance        |
| Ramverk för redovisning                    | IFRS 16        |
| Inställning av leasingperiod/livslängd         | 0,00           |
| Inställning av aktuellt värde/tillgångens verkliga värde | 0,00           |
| Korttidströskel                    | 12             |
| Lågvärdeströskel                     | 5,000.00       |
| Betala till leverantör                           | Nej             |

**Lagstadgad räkenskapsbok**

Den lagstadgade räkenskapsboken är kontantmetodsbok där företaget redovisar leasingkostnaden som det kontantbelopp som betalas varje månad som hyra. Boken skapar inte någon tillgång med nyttjanderätt (ROU) eller leasingskuld.

| Namn                                    | Beskrivning |
|-----------------------------------------|-------------|
| Typ av bok                               | Lagstadgad   |
| Bokbeskrivning                        | Lokal GAAP  |
| Bokföringsskikt                           | Aktuella     |
| Leasingtyp                              | Automatisk   |
| Ramverk för redovisning                    | Kontantunderlag  |
| Inställning av leasingperiod/livslängd         | 0,00        |
| Inställning av aktuellt värde/tillgångens verkliga värde | 0,00        |
| Korttidströskel                    | 0           |
| Lågvärdeströskel                     | 0           |
| Betala till leverantör                           | Nej          |

**Lagstadgad återföringsbok**

Den lagstadgade återföringsboken ställs in på samma sätt som den lagstadgade räkenskapsboken.

| Namn                                    | Beskrivning                    |
|-----------------------------------------|--------------------------------|
| Boktyp                               | Lagstadgad – återföring           |
| Bokbeskrivning                        | Räkenskapsbok för att återföra den lagstadgade räkenskapsboken |
| Bokföringsskikt                           | Anpassat skikt 1                 |
| Leasingtyp                              | Automatisk                      |
| Ramverk för redovisning                    | Kontantunderlag                     |
| Inställning av leasingperiod/livslängd         | 0,00                           |
| Inställning av aktuellt värde/tillgångens verkliga värde | 0,00                           |
| Korttidströskel                    | 0                              |
| Lågvärdeströskel                     | 0                              |
| Betala till leverantör                           | Nej                             |

I det här exemplet har en leasing skapats med följande inställningar på flikarna **Allmänt** och **Betalningsplanrader**.

**Fliken Allmänt**

| Fält                      | Värde            |
|----------------------------|------------------|
| Marginell låneränta | 5 %               |
| Startdatum          | 1/1/2020         |
| Leasinggrupp                | Byggnader        |
| Leverantör                     | 1001             |
| Tillgångens verkliga värde    | 245,000          |
| Tillgångens livslängd          | 120              |
| Typ av annuitet               | Vanlig annuitet |
| Intervall för sammanslagning       | Månatlig          |

**Fliken Betalningsplanrader**

| Fält             | Värde      |
|-------------------|------------|
| Startdatum        | 1/1/2020   |
| Periodintervall   | Månader     |
| Perioder           | 24         |
| Slutdatum          | 12/31/2020 |
| Lönefrekvens | Månatlig    |
| Betalningsbelopp    | 1 000      |

Om du vill redovisa denna leasing inom två ramverk använder du ett aktuellt bokföringsskikt och ett anpassat bokföringsskikt. Följande tabell visar ett exempel på varje journalpost som måste visa ekonomin rättvist enligt respektive rapporteringsstandard. En detaljerad beskrivning av varje journalpost för den första månaden av leasingen tillhandahålls efteråt.

<table>
<thead>
<tr>
<th rowspan='3'>Kontonummer</th>
<th rowspan='3'>Beskrivning</th>
<th colspan='3'>Lagstadgad räkenskapsbok (aktuellt skikt)</th>
<th rowspan='3'>Summa aktuellt skikt</th>
<th>Återföringsbok (anpassat skikt)</th>
<th colspan='4'>IFRS 16-bok (anpassat skikt)</th>
<th rowspan='3'>Summa aktuellt skikt + anpassat skikt</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Leasingkostnad</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Bankavgift</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Momsutgift</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Clearingkonto</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Leverantörsreskontra</td>
<td></td>
<td>-1 008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Tillgång med nyttjanderätt</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Finansiell leasingskyldighet</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22 794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21 888,87</td>
</tr>
<tr>
<td>8</td>
<td>Räntekostnad</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Kontanter</td>
<td></td>
<td></td>
<td>-1 008,00</td>
<td>-1 008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1 008,00</td>
</tr>
<tr>
<td>10</td>
<td>Avskrivningsutgift</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Ackumulerad avskrivning</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Som tabellen ovan visar måste tre böcker rapportera enligt både lagstadgad rapportering och IFRS-rapportering.

- Den lagstadgade boken registrerar leasingbetalningen enligt reglerna för kontantredovisning enligt det aktuella skiktet.
- Den lagstadgade återföringsboken återför de lagstadgade journalposterna.
- IFRS 16-boken skapar de journalposter som krävs enligt IFRS 16.

Du behöver bara ange en leasing en gång. Du kan sedan öppna sidan **Böcker** för att visa du alla böcker som är associerade till leasingen.

> [!NOTE]
> När du skapar böckerna måste alla tre vara associerade med samma leasingpost.

Den första journalposten registrerar leasingkostnaden enligt den lagstadgade boken. Du kan skapa betalningarna antingen i en batch eller genom att välja betalningsplanen i den lagstadgade boken.

I det här exemplet skapas följande journalpost för den lagstadgade boken från betalningsplanen.

### <a name="lease-payment--1312020--je-100"></a>Leasingbetalning – 1/31/2020 – JE 100

| Kontotyp | Kontonummer | Skikt   | Kontobeskrivning | Debet    | Kredit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 1              | Aktuella | Leasingkostnad       | 1,000.00 |          |
| Ledger       | 4              | Aktuella | Clearingkonto    |          | 1,000.00 |

En ansvarig för leverantörsreskontra använder Dynamics 365-standardfunktioner för att skapa en faktura för att betala för leasingen utanför tillgångsleasing. I stället för att välja **Leasingkostnad** som debetkonto väljer leverantörsreskontraansvarig ett clearingkonto för att generera följande post.

### <a name="ap-process--1312020--je-110"></a>AP-process – 1/31/2020 – JE 110

| Kontotyp | Kontonummer | Skikt   | Kontobeskrivning | Debet    | Kredit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 4              | Aktuella | Clearingkonto    | 1,000.00 |          |
| Ledger       | 2              | Aktuella | Bankavgift            | 3.00     |          |
| Ledger       | 3              | Aktuella | Momsutgift         | 5.00     |          |
| Leverantör       | 5              | Aktuella | Leverantörsreskontra    |          | 1,008.00 |

När utdraget utfärdas till leverantören följer du den vanliga betalningsprocessen. Under den här processen skapas följande journalpost.

### <a name="cash-payment--1312020--je-120"></a>Kontantbetalning – 1/31/2020 – JE 120

| Kontotyp | Kontonummer | Skikt   | Kontobeskrivning | Debet    | Kredit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Leverantör       | 5              | Aktuella | Leverantörsreskontra    | 1,008.00 |          |
| Bank         | 9              | Aktuella | Kontanter                |          | 1,008.00 |

I det här skedet har du rapporterat den här leasingen fullständigt enligt lagstadgade rapporteringsbehov och kan generera en råbalans med hjälp av det aktuella skiktet. Systemet returnerar en råbalans med följande siffror.

<table>
<thead>
<tr>
<th rowspan='3'>Kontonummer</th>
<th rowspan='3'>Beskrivning</th>
<th colspan='3'>Lagstadgad räkenskapsbok (aktuellt skikt)</th>
<th rowspan='3'>Summa aktuellt skikt</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Leasingkostnad</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Bankavgift</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Momsutgift</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Clearingkonto</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Leverantörsreskontra</td>
<td></td>
<td>-1 008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Tillgång med nyttjanderätt</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Finansiell leasingskyldighet</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Räntekostnad</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Kontanter</td>
<td></td>
<td></td>
<td>-1 008,00</td>
<td>-1 008,00</td>
</tr>
<tr>
<td>10</td>
<td>Avskrivningsutgift</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Ackumulerad avskrivning</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Om du vill använda IFRS 16 siffror för att köra samma råbalans måste de lagstadgade redovisningsjournalposterna återföras och IFRS 16-journalposterna måste bokföras. För att återföra de lagstadgade journalposterna inkluderar det här exemplet en lagstadgad återföringsbok som har samma inställningar som den lagstadgade boken men en motsatt bokföringsprofil. Till exempel, den lagstadgade boken *debiterade* ett konto för leasingkostnader, men återföringsboken kommer att *kreditera* det här kontot. Dessa relationer är lätta att definiera i bokföringskontona för tillgångsleasing på sidan med **parametrar för tillgångsleasing** (**Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**).

När samma process som användes för den lagstadgade boken används för återföringsboken, skapas följande journalpost. Skillnaden är att återföringsboken bokför återföringstransaktionerna från den lagstadgade boken. Återföringsposterna görs också i det anpassade skiktet. När en råbalans körs på det aktuella skiktet inkluderas inte återföringsjournalposterna.

### <a name="lease-payment--1312020--je-130"></a>Leasingbetalning – 1/31/2020 – JE 130

| Kontotyp | Kontonummer | Skikt  | Kontobeskrivning | Debet    | Kredit   |
|--------------|----------------|--------|---------------------|----------|----------|
| Ledger       | 4              | Anpassat | Clearingkonto    | 1,000.00 |          |
| Ledger       | 1              | Anpassat | Leasingkostnad       |          | 1,000.00 |

Nu när du har eliminerat lagstadgade journalposter ska du bokföras alla de journalposter som IFRS 16 kräver i IFRS 16-boken. Dessa poster inkluderar den första redovisningen av tillgången med nyttjanderätt och skulden, samt posten med ränta och avskrivning.

### <a name="initial-recognition--112020--je-140"></a>Första redovisningstillfälle – 1/1/2020 – JE 140

| Kontotyp | Kontonummer | Skikt  | Kontobeskrivning      | Debet     | Kredit    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Ledger       | 6              | Anpassat | Tillgång med nyttjanderätt                | 22,793.90 |           |
| Ledger       | 7              | Anpassat | Finansiell leasingskyldighet |           | 22,793.90 |

Leasingbetalningen bokförs som övriga leasingbetalningar. Anledningen till att du använder clearingkontot är att säkerställa att kontanter endast krediteras en gång.

### <a name="lease-payment--1312020--je-150"></a>Leasingbetalning – 1/31/2020 – JE 150

| Kontotyp | Kontonummer | Skikt  | Kontobeskrivning      | Debet    | Kredit   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Ledger       | 7              | Anpassat | Finansiell leasingskyldighet | 1,000.00 |          |
| Ledger       | 4              | Anpassat | Clearingkonto         |          | 1,000.00 |

Journalposten för räntekostnad genereras från planen för amortering av skulder.

### <a name="interest-expense--1312020--je-160"></a>Räntekostnad – 1/31/2020 – JE 160

| Kontotyp | Kontonummer | Skikt  | Kontobeskrivning      | Debet | Kredit |
|--------------|----------------|--------|--------------------------|-------|--------|
| Ledger       | 8              | Anpassat | Räntekostnad         | 94.97 |        |
| Ledger       | 7              | Anpassat | Finansiell leasingskyldighet |       | 94.97  |

Journalposten för avskrivningskostnad genereras från planen för avskrivning av tillgång.

### <a name="depreciation-expense--1312020--je-170"></a>Avskrivningsutgift – 1/31/2020 – JE 170

| Kontotyp | Kontonummer | Skikt  | Kontobeskrivning      | Debet  | Kredit |
|--------------|----------------|--------|--------------------------|--------|--------|
| Ledger       | 10             | Anpassat | Avskrivningsutgift     | 949.75 |        |
| Ledger       | 11             | Anpassat | Ackumulerad avskrivning |        | 949.75 |

När alla dessa journalposter har skapats och bokförts visas följande "anpassat skikt 1"-värden. Lägg märke till att den sista kolumnen innehåller bankavgiften, kostnad för mervärdesskatt (moms) och en minskning av kontanter från det föregående skiktet, men att den inte innehåller lagstadgade rapporteringsjournalposter. Därför får du verkliga funktioner för dubbla rapporter. I det här skedet behöver företaget bara köra råbalansen och kombinera det aktuella skiktet och det anpassade skiktet för att skapa en IFRS råbalans.

| Kontonr | beskrivning              | Lagstadgad bok\-Aktuellt skikt\-JE\-100\-Dr \(Cr\) | Lagstadgad bok\-Aktuellt skikt\-JE\-110\-Dr \(Cr\) | Lagstadgad bok\-Aktuellt skikt\-JE\-120\-Dr \(Cr\) | Aktuellt skikt \- Summa | - | Återföringsbok\-Anpassat skikt\-JE\-130\-Dr \(Cr\) | IFRS 16-bok\-Anpassat skikt\-JE\-140\-Dr \(Cr\) | IFRS 16-bok\-Anpassat skikt\-JE\-150\-Dr \(Cr\) | IFRS 16-bok\-Anpassat skikt\-JE\-160\-Dr \(Cr\) | IFRS 16-bok\-Anpassat skikt\-JE\-170\-Dr \(Cr\) | Anpassat skikt \+ Aktuellt skikt \- Summa |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Leasingkostnad            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1 000                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Bankavgift                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Momsutgift              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Clearingkonto         | \-1 000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1 000                                           |                                                | \-1 000                                        |                                                |                                                | 0\.00                                   |
| 5          | Leverantörsreskontra         |                                                   | \-1 008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | Tillgång med nyttjanderätt                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Finansiell leasingskyldighet |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22 794                                       | 1 000                                          | \-94\.97                                       |                                                | \-21 888\.87                            |
| 8          | Räntekostnad         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Kontanter                     |                                                   |                                                   | \-1 008\.00                                       | \-1 008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1 008\.00                             |
| 10         | Avskrivningsutgift     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Ackumulerad avskrivning |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
