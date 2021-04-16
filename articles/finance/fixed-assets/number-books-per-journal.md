---
title: Antal böcker per journal
description: I det här ämnet beskrivs relationen mellan journaler och tillgångsböcker när du skapar anskaffnings- eller avskrivningsförslag för anläggningstillgångar via ett batchjobb. Du kan definiera det maximala antalet böcker som inkluderas för varje anskaffning och för avskrivning.
author: moaamer
ms.date: 11/19/2020
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
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e948b4353d0216f1e09019a98319e343bd535861
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822043"
---
# <a name="number-of-books-per-journal"></a>Antal böcker per journal

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs relationen mellan journaler och tillgångsböcker när du skapar anskaffnings- eller avskrivningsförslag för anläggningstillgångar via ett batchjobb. Du kan definiera det maximala antalet böcker som inkluderas för varje anskaffning och för avskrivning med hjälp av fälten i avsnittet **Antal böcker per journal** på fliken **Allmänt** på sidan **Parametrar för anläggningstillgångar** (**Anläggningstillgångar \> Konfigurera \> Parametrar för anläggningstillgångar**). Med hjälp av dessa fält kan du fördela antalet tillgångsböcker per anskaffningsjournal och avskrivningsjournal.

För ett anskaffningsförslag är standardvärdet minst 10 000 böcker. För ett avskrivningsförslag är standardvärdet minst 2 000 böcker.

Om det till exempel finns 4 000 anläggningstillgångar och två böcker associeras med varje tillgång, kommer en bok att bokföras på det aktuella skiktet och den andra boken bokförs på skatteskiktet. Om du förvärvar 4 000 anläggningstillgångar via batchbearbetning kommer batchjobbet som skapar en anskaffningsjournal för en anläggningstillgång att innehålla 4 000 tillgångsjournaler.

> [!NOTE]
> Journalen som skapas fortsätter att användas tills batchjobbet är slutfört.
>
> De härledda böckerna inkluderas inte i det maximala antalet böcker per journal.

Du kan använda batchbearbetning för att köra avskrivning för samma uppsättning av förvärvade tillgångar. Ett batchjobb skapar till exempel två avskrivningsjournaler, som var och en består av 2 000 tillgångsböcker. Den första journalen kommer att innehålla böcker som är kopplade till anläggningstillgångar som är numrerade 1 till 2 000. Den andra journalen kommer då att innehålla böcker som är kopplade till anläggningstillgångar som är numrerade 2 001 till 4 000.

I batchbearbetningsjobbet exkluderas stängda böcker. Till exempel, i ett batchjobb för avskrivning, är 10 av de första 2 000 böckerna stängda. I så fall kommer den första journalen innehålla böcker som är kopplade till anläggningstillgångar som är numrerade 1 till 2 011. Den andra journalen kommer då att innehålla böcker som är kopplade till anläggningstillgångar som är numrerade 2 012 till 4 000.

> [!NOTE]
> Om du har anläggningstillgångs-ID med olika avgränsare (till exempel – eller /) och du skapar transaktioner för anläggningstillgångar i batchjobb, måste du köra ett separat batchjobb för varje typ av avgränsare. Systemet kan inte bearbeta olika avgränsare inom samma batchjobb.

Gränsen för antalet böcker tillämpas om det inte finns dubbletter av tillgångs-ID i samma journal. Om tillgångs-ID:t är samma som bok-ID:t, kan antalet böcker per journal överskridas för att behålla tillgångs-ID:t i samma journal.

Det finns till exempel 5 001 anläggningstillgångs-ID:n, tre böcker associeras med varje anläggningstillgångs-ID och varje tillgångsbok bokförs på samma bokföringsskikt. Du kör avskrivningen under tre på varandra följande månader, utan summering.  Avskrivningsjournalen kommer att skapas via ett batchjobb, och i systemet skapas sju journaler med 667 anläggningstillgångs-ID:n och tre böcker för varje anläggningstillgångs-ID. Resultatet blir 2 001 böcker. Därför kommer det att finnas 6 003 journalrader om tre månader för att behålla samma tillgångs-ID:n i samma journal. Systemet kommer också att skapa en journal med 332 anläggningstillgångs-ID:n och tre böcker för varje anläggningstillgångs-ID. Om tre månader kommer det att finnas 2 988 rader.

> [!NOTE] 
> Om parametern **Summera avskrivning** är aktiverad när du skapar ett avskrivningsförslag påverkas inte värdet i fältet **Antal böcker per journal – Avskrivningsförslag**. I det här fallet är antalet böcker per journal 6 000, vilket är den internt definierade gränsen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
