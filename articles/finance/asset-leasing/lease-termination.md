---
title: Förslag på uppsägning av leasingavtal
description: I detta ämne beskrivs hur du föreslår ett leasingavtal för uppsägning.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseTerminateLeaseListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6b32f9e8f80827e04269ac8cb6a4fbb5a13af8bc
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881118"
---
# <a name="propose-a-lease-for-termination"></a>Föreslå ett leasingavtal för uppsägning

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Om ett leasingavtal avslutas i förtid kan tillgångsleasingen registrera en journalpost för uppsägning för att skriva av leasingskulden, användanderättigheten (ROU) samt ackumulerad avskrivning, och registrera en vinst eller förlust. Processen för förtida uppsägning avslutar ett leasingavtal och dess associerade leasingböcker. Den säger inte upp enskilda leasingböcker. I detta ämne beskrivs de funktioner som gör att du kan föreslå ett leasingavtal för uppsägning och bearbeta journalposten för leasinguppsägningen.

Om ett leasingavtal inte klassas som ett leasingavtal med uppskjuten leasingavgift samt inte är associerat med en anläggningstillgång, leder tillgångsleasing till följande journalpost för uppsägning.

| Transaktion                           | Debet (Dr.) | Kredit (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. leasingskuld                   | X           |              |
| Dr. Ackumulerad avskrivning          | X           |              |
| Dr. Vinst (förlust) vid leasingändring | X           |              |
| Cr. leasingtillgång                       |             | X            |
| Cr. Vinst (förlust) vid leasingändring |             | X            |

Om leasingboken klassificeras som en bok med för uppskov av leasingavgift skriver posten av saldot för uppskov av leasingavgift före uppsägning till vinst- eller förlustkontot, enligt vad som visas här.

| Transaktion                           | Debet (Dr.) | Kredit (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Uppskov av leasingavgift                     | X           |              |
| Cr. Vinst (förlust) vid leasingändring |             | X            |
| Cr. Uppskov av leasingavgift                     |             | X            |
| Dr. Vinst (förlust) vid leasingändring | X           |              |

Om leasingboken är ansluten till en anläggningstillgång redovisas tillgången med nyttjanderätt i bland anläggningstillgångarna. Denna redovisning omfattar redovisning för tidigare uppsägningar. Tillgångsleasing medför följande journalpost för avskrivning av leasingskulden.

| Transaktion                           | Debet (Dr.) | Kredit (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. leasingskuld                   | X           |              |
| Cr. Vinst (förlust) vid leasingändring |             | X            |

Information om det korrekta sättet att avyttra en tillgång med nyttjanderätt finns i [Avyttra en anläggningstillgång som kassation](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Föreslå ett leasingavtal för uppsägning

1. Gå till det leasingavtal som måste avslutas och välj sedan **Uppsägningsförslag** i åtgärdsfönstret.

    > [!NOTE]
    > Knappen **Uppsägningsförslag** är inte tillgänglig om det finns icke-bokförda journalposter mot någon bok. Innan du kan säga upp leasingavtalet måste du bokföra eller radera journalposter som har skapats mot leasingavtalet.

2. I dialogrutan som visas ställer du in fälten **Giltighetsdatum** och **Bokföringsdatum** för uppsägningsposten i redovisningsjournalen.
3. Välj **Uppsägningsförslag** om du vill föreslå leasingavtalet för uppsägning.
4. Välj **Bokför leasinguppsägning** om du vill att uppsägningen av leasingavtalet ska bokföras automatiskt.
5. På sidan **Leasinguppsägningar** väljer du leasing-ID för det leasingavtal som du föreslagit för uppsägning, om du vill visa uppsägningsraderna. Uppsägningsraderna visar bokförda värden för tillgång med nyttjanderätt, leasingskuld, ackumulerad avskrivning, uppskjuten hyra (om tillämpligt) samt vinst eller förlust som måste redovisas när leasingavtalet avslutas.

Leasingavtalet är nu klart för uppsägning. Värdet i fältet **Uppsägningsstatus** för leasingboken ändras till **Redo för uppsägning**. Du kan nu inte längre bokföra journalposter mot leasingavtalet, eller justera eller försämra det. 

## <a name="process-leases-that-are-ready-for-termination"></a>Bearbeta leasingavtal som är klara för uppsägning

Gör på följande sätt när du vill bearbeta leasingavtal som är klara för uppsägning och bokföra journalposten för uppsägning.

1. På sidan **Uppsägningar av leasingavtal** väljer du det leasingavtal du vill behandla och väljer sedan **Avsluta**.
2. I dialogrutan som visas väljer du **OK**.

Systemet bokför journalposten för uppsägningen. Fältet **Leasingstatus** för leasingboken ställs in på **Uppsagt** och fältet **Status för uppsägningsförslag** ställs in på **Slutfört**.

## <a name="reverse-a-lease-termination"></a>Återföra en leasinguppsägning

Följ det här steget om du vill återföra en journalpost för leasinguppsägning och öppna ett uppsagt leasingavtal.

- På sidan **Uppsägningar av leasingavtal** väljer du det uppsagda leasingavtal du vill återföra och väljer sedan **Återför uppsägning**.

Systemet återför journalposten för uppsägningen. Fältet **Status för leasingavtal** för leasingboken ställs in på **Öppen**. Leasingavtalet visas inte längre på sidan **Uppsägningar av leasingavtal** och kan återigen föreslås för uppsägning.

## <a name="example-of-a-lease-termination"></a>Exempel på uppsägning av ett leasingavtal

I det här exemplet är leasingen associerad med en icke-specialiserad tillgång och överför inte ägarskap av tillgången eller beviljar leasetagaren möjlighet att köpa tillgången.

### <a name="setup"></a>Ställ in

I följande tabeller visas de värden som är inställda på flikarna **Allmänt** och **Betalningsplanrader** för den leasing som används i det här exemplet.

**Fliken Allmänt**

| Fält                      | Värde            |
|----------------------------|------------------|
| Tillgångens verkliga värde    | 600,000          |
| Valuta                   | USD              |
| Direkta utgifter       | 1 000            |
| Marginell låneränta | 7 %               |
| Intervall för sammanslagning       | Årligen         |
| Tillgångens livslängd (månader) | 600              |
| Typ av annuitet               | Vanlig annuitet |
| Startdatum          | 2019-01-01         |

**Fliken Betalningsplanrader**

| Fält             | Värde      |
|-------------------|------------|
| Startdatum        | 2019-01-01   |
| Periodintervall   | Månatlig    |
| Perioder           | 120        |
| Slutdatum          | 2028-12-31 |
| Lönefrekvens | Årligen   |
| Betalningsbelopp    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>Steg för att avsluta leasingavtalet

1. När du har skapat leasingen enligt beskrivningen ovan, gå till leasingboken och bekräfta betalningsplanen. Sedan kan du bokföra den ursprungliga redovisningsjournalposten. Den ursprungliga tillgången med nyttjanderätt uppgår till 71 235,81 USD och leasingskulden bör vara 70 235,81 USD. I det här exemplet klassificerades leasingen som en operationell leasing enligt ASC 842 (Accounting Standards Codification Topic 842).
2. Kör batchjournalprocessen tre gånger för att simulera att tre år förflyter för leasingbetalningarna, räntekostnaderna och avskrivningskostnaderna.
3. När du har kört alla de tre batchjobben går du tillbaka till leasingboken och öppnar tabellerna för skuld- och tillgångstransaktioner för att visa det aktuella bokförda värdet för tillgången med nyttjanderätt samt leasingskulden. Efter tre år ska värdet på skulden vara ungefär -53 893,00 USD och tillgångens värde ungefär 54 593,00 USD.

    När de tre åren har gått är företaget och leasegivaren överens om att avsluta leasingavtalet. Därför måste du nu avsluta leasingavtalet.

4. Gå till det leasingavtal som måste avslutas och välj sedan **Uppsägningsförslag** i åtgärdsfönstret. 
5. I dialogrutan som visas, i fälten **Giltighetsdatum** och **Bokföringsdatum**, anger du **1/1/2021**.
6. Välj **Uppsägningsförslag** om du vill föreslå leasingavtalet för uppsägning.

    Sidan **Uppsadga leasingavtal** visas och visar det leasingavtal som ska avslutas.

7. Om du vill visa uppsägningsraderna väljer du leasing-ID för det leasingavtal som du föreslagit för uppsägning. Uppsägningsraderna visar leasingavtalets bokförda värden. Följande tabell visar vad dessa värden ska vara för det här exemplet. 

    | Fält                                                 | Värde      |
    |-------------------------------------------------------|------------|
    | Bokfört skuldsaldo i transaktionsvaluta | 53 892,89 USD |
    | Tillgång med nyttjanderätt i transaktionsvaluta            | 71 235,81 USD |
    | Ackumulerad avskrivning i transaktionsvaluta      | 16 642,92 USD |
    | Vinst (förlust) i transaktionsvaluta                   | -700,00 USD   |

8. Om du vill bokföra journalposten för uppsägning väljer du leasingavtalet på sidan **Uppsägningar av leasingavtal** och sedan **Avsluta**.
9. I dialogrutan som visas väljer du **OK**.
10. Om du vill visa uppsägningsjournalposten som har skapats och bokförts går du till tillgångens leasingjournal i leasingboken. Följande tabell visar hur denna post bör se ut för detta exempel.

    | Transaktion                           | Debet (Dr.) | Kredit (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. leasingskuld                   | 53,892.89   |              |
    | Dr. Ackumulerad avskrivning          | 16,642.92   |              |
    | Dr. Vinst (förlust) vid leasingändring | 700.00      |              |
    | Cr. leasingtillgång                       |             | 71,235.81    |

11. Om du vill visa nettoeffekterna av uppsägningen, där tillgången med nyttjanderätt och leasingskulden blir 0 (noll), öppnar du transaktionsregistren för skulder och tillgångar.

Leasingstatusen ska nu vara **Avslutad**. Inga ytterligare journalposter kommer att bokföras mot detta leasingavtal om inte uppsägningen återförs.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
