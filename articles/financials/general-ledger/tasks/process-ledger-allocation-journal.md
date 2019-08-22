---
title: Bearbeta journal för redovisningsallokering
description: Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 087bd4f203e8762447e823b19076b79296a390d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846377"
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

