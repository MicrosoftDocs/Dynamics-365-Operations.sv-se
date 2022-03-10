---
title: Skriva ner tillgångar med nyttjanderätt
description: I det här ämnet beskrivs de funktioner som registrerar en nedskrivning och justerar avskrivningsplanen för tillgångar i en operationell leasing enligt Accounting Standards Codification Topic 842 (ASC 842).
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b104cec399a368ada64a73688c42476e6fbd9e52
ms.sourcegitcommit: 304a482dfcc31dcb61849f710ae73432324ddef3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/29/2021
ms.locfileid: "7947350"
---
# <a name="impair-right-of-use-assets"></a>Skriva ner tillgångar med nyttjanderätt

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Om en ROU-tillgångs (ROU, tillgång med nyttjanderätt) redovisade värde inte kan återbetalas måste du kanske testa om tillgången har skrivits ner. Om du fastställer att till gången har skrivits ner kan Leasing av tillgångar registrera nedskrivningen och justera avskrivningsplanen i enlighet därmed. I det här ämnet beskrivs de funktioner som registrerar nedskrivningen och justerar avskrivningsplanen i en operationell leasing enligt Accounting Standards Codification Topic 842 (ASC 842). Samma metod gäller även leasingar enligt International Financial Reporting Standard 16 (IFRS 16).

Det återstående saldot för ROU-tillgången kommer att amorteras på ett linjärt sätt för det antal perioder som återstår, oavsett om leasingen klassificerades som finansiell leasing enligt IFRS 16 eller operationellt leasing enligt ASC 842.

## <a name="impair-an-rou-asset"></a>Skriva ner en ROU-tillgång

1. Gå till den nedskrivna leasingen och välj **Böcker**.
2. Klicka på **Nedskrivning** i åtgärdsfönstret.
3. I dialogrutan som visas anger du beloppet för tillgångens nedskrivning i fältet **Nedskrivningsbelopp**. Om du vill minska ROU-tillgången anger du ett positivt värde.
4. I fältet **Transaktionsdatum** anger du det datum då nedskrivningsposten ska bokföras.
5. I fältet **Återstående perioder** anger du det återstående antalet månader att amortera.
6. Ställ in alternativet **Förhandsgranska** för att visa föreslaget tillgångssaldo och finansiella posten innan den skapas eller bokförs.
7. Ställ in alternativet **Stäng bok** till **Ja** om du vill stänga leasingboken. Du kan ångra den här åtgärden genom att använda status **Öppna leasing igen**. Poster kan inte bokföras mot stängda leasingar, och stängda leasingar kan inte justeras. 
8. Välj **bokföra** för att skapa eller bokföra nedskrivningsposten.

    > [!NOTE]
    > När nedskrivningstransaktionen har bokförts skapas en ny bokversion.

    > Om leasingavtalet är klassificerat som ett rörelseleasing kommer den månatliga avskrivningen efter nedskrivningen att beräknas med hjälp av beräknad linjär avskrivning.

9. Om du vill visa avskrivningsplanen för den nedskrivna tillgången öppnar du avskrivningsplanen för tillgången för den leasingboken. Tillgången avskrivs nu på linjär basis över det antal månader som du har angett i fältet **Återstående perioder**.
10. Om du vill visa journalposten för nedskrivningsutgift väljer du **Journal för leasing av tillgång** i åtgärdsfönstret för den nedskrivna leasingboken. Systemet skapar en post i redovisningsjournalen som debiterar bokföringskontot för nedskrivningsutgiften och krediterar bokföringskontot för leasingtillgången. 
11. Om du vill visa det bokförda värdet för ROU-tillgången väljer du **Transaktioner för tillgångar** i leasingbokens åtgärdsfönster.

## <a name="example-of-rou-asset-impairment"></a>Exempel på nedskrivning av ROU-tillgång

I det här exemplet är leasingen en icke-specialiserad tillgång som inte överför ägarskap eller som beviljar leasetagaren möjligheten att köpa.

### <a name="setup"></a>Ställ in

I följande tabeller visas de värden som är inställda på flikarna **Allmänt** och **Betalningsplanrader** för den leasing som används i det här exemplet.

**Fliken Allmänt**

| Fält                      | Värde            |
|----------------------------|------------------|
| Tillgångens verkliga värde    | 600,000          |
| Marginell låneränta | 7 %               |
| Intervall för sammanslagning       | Årligen         |
| Tillgångens livslängd (månader) | 600              |
| Typ av annuitet               | Vanlig annuitet |
| Startdatum          | 2019-01-01       |

**Fliken Betalningsplanrader**

| Fält             | Värde      |
|-------------------|------------|
| Startdatum        | 2019-01-01   |
| Periodintervall   | Månatlig    |
| Perioder           | 120        |
| Slutdatum          | 2028-12-31 |
| Lönefrekvens | Årligen   |
| Betalningsbelopp    | 10,000     |

### <a name="steps"></a>Steg

1. När du har skapat leasingen enligt beskrivningen ovan, gå till leasingboken och bekräfta betalningsplanen. Sedan kan du bokföra den ursprungliga redovisningsjournalposten. Den ursprungliga ROU-tillgången och leasingskulden bör vara 70 235,81 USD. I det här exemplet klassificerades leasingen som en operationell leasing enligt ASC 842.
2. Kör batchjournalprocessen tre gånger för att simulera att tre år förflyter för leasingbetalningarna, räntekostnaderna och avskrivningskostnaderna.
3. När du har kört alla de tre batchjobben går du tillbaka till leasingboken och öppnar tabellerna för skuld- och tillgångstransaktioner för att visa det aktuella bokförda värdet för ROU-tillgången och leasingskulden. Efter tre år ska värdet på skulden vara ungefär -53 893,00 USD och tillgångens värde ska vara ungefär 53 893,00 USD. 

    Efter tre år gör företaget nedskrivningstest och fastställer att ROU-tillgången har en nedskrivning på 35 000 USD. Du måste nu registrera denna nedskrivning.
    
4. Gå till leasingboken och välj sedan **Nedskrivning** i åtgärdsfönstret.
5. Ange följande information på sidan **Nedskrivningsparameter**.

    | Fält                  | Värde    |
    |------------------------|----------|
    | Nedskrivningsbelopp      | 35,000   |
    | Transaktionsdatum       | 2022-01-01 |
    | Resterande perioder      | 84       |
    | Bokför                   | Ja      |
    | Förhandsgranska före bokföring | Nej       |
    | Stäng bok             | Nej       |

6. En journalpost för nedskrivningsutgift har skapats och bokförts. Om du vill visa den går du till tillgångens leasingjournal i leasingboken. Observera att beloppet för nedskrivningen debiterades bokföringskontot för nedskrivningsutgift, och bokföringskontot för ROU-tillgången krediterades.

7. Om du vill visa nettoeffekten av nedskrivningen går du till tabellerna skuld- och tillgångstransaktioner. Observera att nedskrivningsutgifterna har minskat ROU-tillgången, men det bokförda värdet för leasingskulden inte har ändrats.

Nedskrivningen har en annan effekt som du bör tänka på. Eftersom ROU-tillgångsbeloppet nu är mycket mindre än leasingskulden, måste beloppet avskrivas på ett annat sätt än tidigare. Tillgången avskrivs nu på linjärt sätt under de återstående 84 månaderna av leasingen, med början på transaktionsdatumet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
