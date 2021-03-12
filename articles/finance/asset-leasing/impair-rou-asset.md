---
title: Skriva ner tillgångar med nyttjanderätt
description: I det här ämnet beskrivs de funktioner som registrerar en nedskrivning och justerar avskrivningsplanen för tillgångar i en operationell leasing enligt Accounting Standards Codification Topic 842 (ASC 842).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 9822a11dbb277726b60ff82843bd26314e968345
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003266"
---
# <a name="impair-right-of-use-assets"></a>Skriva ner tillgångar med nyttjanderätt

[!include [banner](../includes/banner.md)]

Om en ROU-tillgångs (ROU, tillgång med nyttjanderätt) redovisade värde inte kan återbetalas måste du kanske testa om tillgången har skrivits ner. Om du fastställer att till gången har skrivits ner kan Leasing av tillgångar registrera nedskrivningen och justera avskrivningsplanen i enlighet därmed. I det här ämnet beskrivs de funktioner som registrerar nedskrivningen och justerar avskrivningsplanen i en operationell leasing enligt Accounting Standards Codification Topic 842 (ASC 842). Samma metod gäller även leasingar enligt International Financial Reporting Standard 16 (IFRS 16).

Det återstående saldot för ROU-tillgången kommer att amorteras på ett linjärt sätt för det antal perioder som återstår, oavsett om leasingen klassificerades som finansiell leasing enligt IFRS 16 eller operationellt leasing enligt ASC 842.

## <a name="impair-an-rou-asset"></a>Skriva ner en ROU-tillgång

1. Gå till den nedskrivna leasingen och välj **Böcker**.
2. Klicka på **Nedskrivning** i åtgärdsfönstret.
3. I dialogrutan som visas anger du beloppet för tillgångens nedskrivning i fältet **Nedskrivningsbelopp**. Om du vill minska ROU-tillgången anger du ett positivt värde.
4. I fältet **Transaktionsdatum** anger du det datum då nedskrivningsposten ska bokföras.
5. I fältet **Återstående perioder** anger du det återstående antalet månader att amortera.
6. Aktivera parametern **Bokför** om du vill systemet automatiskt ska bokföra utgiftsjournalposten för nedskrivning. Om du låter den här parametern vara inaktiverad skapas posten i systemet, men den bokförs inte. Därefter kan du bokföra posten från sidan **Journaler för leasing av tillgångar**.
7. Ställ in alternativet **Förhandsgranska före bokföring** till **Ja** om du vill visa den föreslagna posten innan den skapas eller bokförs.
8. Ställ in alternativet **Stäng bok** till **Ja** om du vill stänga leasingboken. Du kan inte ångra denna åtgärd. Poster kan inte bokföras mot stängda leasingar, och stängda leasingar kan inte justeras.
9. Välj **OK** för att skapa eller bokföra nedskrivningsposten.
10. Om du vill visa avskrivningsplanen för den nedskrivna tillgången öppnar du avskrivningsplanen för tillgången för den leasingboken. Tillgången avskrivs nu på linjär basis över det antal månader som du har angett i fältet **Återstående perioder**.
11. Om du vill visa journalposten för nedskrivningsutgift väljer du **Journal för leasing av tillgång** i åtgärdsfönstret för den nedskrivna leasingboken. Systemet skapar en post i redovisningsjournalen som debiterar bokföringskontot för nedskrivningsutgiften och krediterar bokföringskontot för leasingtillgången.
12. Om du vill visa det bokförda värdet för ROU-tillgången väljer du **Transaktioner för tillgångar** i leasingbokens åtgärdsfönster.

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
    | Förhandsgranska före bokföring | Nr       |
    | Stäng bok             | Nr       |

6. En journalpost för nedskrivningsutgift har skapats och bokförts. Om du vill visa den går du till tillgångens leasingjournal i leasingboken. Observera att beloppet för nedskrivningen debiterades bokföringskontot för nedskrivningsutgift, och bokföringskontot för ROU-tillgången krediterades.
7. Om du vill visa nettoeffekten av nedskrivningen går du till tabellerna skuld- och tillgångstransaktioner. Observera att nedskrivningsutgifterna har minskat ROU-tillgången, men det bokförda värdet för leasingskulden inte har ändrats.

Nedskrivningen har en annan effekt som du bör tänka på. Eftersom ROU-tillgångsbeloppet nu är mycket mindre än leasingskulden, måste beloppet avskrivas på ett annat sätt än tidigare. Tillgången avskrivs nu på linjärt sätt under de återstående 84 månaderna av leasingen, med början på transaktionsdatumet.
