--- 
title: "Bearbeta journal för redovisningsallokering"
description: "Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7d299657758b1e1322aef07bfe8c71f7bf00b0ca
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="process-ledger-allocation-journal"></a>Bearbeta journal för redovisningsallokering

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen. Innan du kan skapa en allokeringsjournal måste det finnas minst en aktiv redovisningsallokeringsregel. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Redovisning > Allokeringar > Bearbeta allokeringsbegäran.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Regel.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Ange ett datum i fältet Från och med (datum).
    * Från och med-datumet är mycket viktigt när redovisningen är datakällan för regeln. Detta datum styr vilka redovisningssaldon som ska inkluderas för allokering.     I fältet Noll urspr.belopp väljer du Stoppa. När du gör det stoppas allokeringsprocessen och ett meddelande visa som anger att ett nollbelopp har valts.  
6. Välj Enbart förslag i fältet Förslagsalternativ.
    * Välj Enbart förslag för att granska och eventuellt godkänna resultatet i allokeringsjournalerna innan du bokför allokeringen i redovisningen.  
7. Ange ett datum i fältet Datum för bokföring i huvudbok.
8. Klicka på OK.
9. Gå till Redovisning > Allokeringar > Allokeringsjournaler.
10. Klicka på Rader.
11. Klicka på Bokför.
12. Klicka på Bokför.


