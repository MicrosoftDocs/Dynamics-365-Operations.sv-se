---
title: Registrera avskrivning av tillgång med nyttjanderätt (förhandsversion)
description: I det här ämnet beskrivs hur du skapar en journalpost för den amortering som krävs för leasingar som redovisas i en organisations balansräkning.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseAssetSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a766247e5482677429706a324c09cc9be4386c0b
ms.sourcegitcommit: 304a482dfcc31dcb61849f710ae73432324ddef3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/29/2021
ms.locfileid: "7947325"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Registrera avskrivning av tillgång med nyttjanderätt (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


För leasingavtal som redovisas i en organisations balansräkning amorteras den ROU-tillgången (Right-Of-Use) på månatlig basis. I det här ämnet beskrivs hur du skapar en journalpost för amorteringen. Amorteringen debiterar är utgiftsredovisningskontot och krediterar det ackumulerade avskrivningsredovisningskontot, baserat på inställningarna för din bokföringsprofil och leasingtypen. Dessa poster kan skapas för varje leasing, eller så kan de skapas för flera leasingar med hjälp av batchfunktionen för journaler.

## <a name="asset-depreciation-schedule"></a>Tillgångens avskrivningstidsplan

1. Välj en leasing på sidan **Sammanfattning av leasing**. Välj sedan **Böcker \> Avskrivningsplan för tillgången** för att öppna sidan **Avskrivningsplan för tillgången**.

    ROU-tillgångens för journalpost för avskrivningsutgifter baseras på beloppet i kolumnen **Avskrivningsutgift**. Ett exempel på riktlinjer för överensstämmelse med redovisningsstandard finns i [Beräkning av ROU-tillgångens amorteringsutgift för finansiell leasing](#calculation-of-rou-asset-amortization-expense-for-finance-leases) senare i det här ämnet.
    
2. Välj avskrivningsperiod och välj sedan **Skapa journal**. Ett meddelande visas om att journalen som kommer att användas för att registrera avskrivning har skapats.
3. Välj **Journaler \> Journaler för leasing av tillgångar** för att öppna sidan **Journal för leasing av tillgång**, där du kan visa journalposten för avskrivningsutgifter som har skapats.

   Systemet låser vissa ekonomiska fält från att redigeras i syfte att förhindra eventuella avvikelser mellan transaktioner och tidsplaner. Fält som är låsta inkluderar följande: **Kontro**, **Belopp**, **Ekonomiska dimensioner**, **Valuta** och **Transaktionstyp**. Du kan vidare inte lägga till eller ta bort journalpostrader från någon journalpost för tillgångsleasing eftersom detta kan orsaka avvikelser mellan tidsplanerna och transaktionerna.

4. Välj journalposten och välj **Bokför** för att registrera avskrivningsposten i redovisningen.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Beräkning av ROU-tillgångens amorteringsutgift för operationell leasing

Avskrivningskostnaden för en operationell leasing beräknas som skillnaden mellan månadens linjära leasingkostnad och den månatliga räntekostnaden för leasingen, i enlighet med Accounting Standards Codification Topic 842 (ASC 842), som är standard för god redovisningssed i USA (US GAAP, Generally Accepted Accounting Principles). Den linjära leasingkostnaden beräknas som summan av alla leasingbetalningar dividerat med leasingperioden i månader. (Summan av leasingbetalningar inkluderar alla förskottsbetalningar, direkta utgifter, nedmonteringskostnader och leasingincitament.) I följande tabell visas ett exempel på en amorteringskostnad för en operationell leasing.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Exempel på ROU-tillgångens amorteringsutgift för operationell leasing

| Fält                                          | Värde       |
|------------------------------------------------|-------------|
| Betalningsbelopp                                 | 1 000       |
| Lönefrekvens                              | Månatlig     |
| Leasingperiod (månader)                            | 24          |
| Totala leasingbetalningar                           | 24,000      |
| Marginell låneränta                     | 5 %          |
| Typ av annuitet                                   | Annuitet förfaller |
| Intervall för sammanslagning                           | Månatlig     |
| Nuvärde för framtida lägsta leasingbetalningar | 22,888.87   |

Som nämndes tidigare beräknas den linjära leasingkostnaden som summan av alla betalningar dividerat med leasingperioden i månader. Systemet beräknar automatiskt den månatliga räntekostnaden i planen för amortering av skulden. Räntekostnaderna beräknas med hjälp av metoden med effektiva ränta. Systemet använder den linjära leasingkostnaden för att subtrahera räntekostnaden för varje månad. Värdet används för att minska ROU-tillgången.

| Månad | Linjär leasingkostnad | Räntekostnad                        | Beräkning av ROU-tillgångens amorteringsutgift |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24 000 ÷ 24) = 1 000,00 | (22 888,87 – 1 000) × (5 % ÷ 12) = 91,20 | 1 000 – 91,20 = 908,80                        |
| 2     | (24 000 ÷ 24) = 1 000,00 | (21 980,08 – 1 000) × (5 % ÷ 12) = 87,42 | 1 000 – 87,42 = 912,58                        |
| 3     | (24 000 ÷ 24) = 1 000,00 | (21 067,49 – 1 000) × (5 % ÷ 12) = 83,62 | 1 000 – 83,62 = 916,39                        |

> [!NOTE]
> Enligt ASC 842 klassificeras avskrivningen av ROU-tillgången för en operationell leasing som en leasingkostnad i resultaträkningen. För synlighet beskriver tillgångsleasing posten som avskrivningen av ROU-tillgången. Debetposten bör dock tilldelas till ett konto för operationell leasingkostnad och kreditposten ska tilldelas direkt till ROU-tillgången för den operationella leasingen. I leasingparametrarna kan du dock ange att kreditposter ska göras till ett ackumulerat avskrivningskonto för operationella ROU-tillgångar.

Om leasingavtalet är klassificerat som ett rörelseleasing kommer den månatliga avskrivningen efter nedskrivningen att beräknas med hjälp av beräknad linjär avskrivning.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Beräkning av ROU-tillgångens amorteringsutgift för finansiell leasing

För leasingar som har en finansiell klassificering beräknar systemet ROU-tillgångens amortering linjärt. Avskrivningsutgiften kommer därför att vara densamma för varje månad.

I enlighet med International Financial Reporting Standard 16 (IFRS 16) och ASC 842 kommer tillgången att amorteras över antingen leasingperioden eller tillgångens livslängd, beroende på vilket som är mindre. Om däremot parametern **Överföring av ägarskap** har aktiverats för leasingen skrivs leasingen automatiskt av över tillgångens livslängd.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Exempel på ROU-tillgångens amorteringsutgift för finansiell leasing

| Fält                                | Värde                                   |
|--------------------------------------|-----------------------------------------|
| Ingående saldo för tillgång med nyttjanderätt | 22,889.87                               |
| Leasingperiod (månader)                  | 24                                      |
| Tillgångens livslängd (månader)           | 36                                      |
| Månad                                | Amorteringsutgift för tillgång med nyttjanderätt |
| 1                                    | 22 889,87 ÷ 24 = 953,74                 |
| 2                                    | 22 889,87 ÷ 24 = 953,74                 |
| 3                                    | 22 889,87 ÷ 24 = 953,74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
