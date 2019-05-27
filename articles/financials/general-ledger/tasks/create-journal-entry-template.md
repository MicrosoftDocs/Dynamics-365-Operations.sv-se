---
title: Skapa en journalpost med en mall
description: Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a749740b62e39202d502a112f947679f85ca085
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562517"
---
# <a name="create-a-journal-entry-using-template"></a>Skapa en journalpost med en mall

[!include [task guide banner](../../includes/task-guide-banner.md)]

Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder. I den här proceduren används demonstrationsföretaget USMF.

1. Redovisning > Journalposter > Allmänna journaler. Klicka på Ny.
    * I den här proceduren börjar vi med att skapa och bokföra en journal verifikation, men alla tidigare bokförd bokföringsorder kan sparas som en mall.  
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Klicka på Rader.
6. Ange ett konto för kontotypen.
7. Ange ett värde i fältet Beskrivning.
8. Ange ett belopp i fältet Debet.
9. Klicka på Ny.
10. Ange ett annat konto för kontotypen.
11. Ange ett värde i fältet Beskrivning.
12. Ange ett belopp i fältet Debet.
13. Klicka på Ny.
14. Ange önskade värden i fältet Konto.
15. Skriv ett värde i fältet Beskrivning.
16. Ange ett belopp i krediteringsfältet för att balansera verifikationen.
17. Klicka på Bokför.
18. Klicka på Funktioner.
19. Klicka på Spara verifikationsmall.
20. I den här proceduren förutsätts det en procentmalltyp. Klicka på OK.
    * • Procent: Beloppen i verifikationen konverteras till procentsatsfaktorer, vilket innebär att alla belopp, används när verifikationsmallen har valts.  • Belopp: De möjligt att beloppen ska lagras och kommer att användas.  
21. Klicka på Allmänna journaler.
22. Klicka på Ny.
23. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
24. Klicka på länken på den valda raden i listan.
25. Klicka på Rader.
26. Klicka på Funktioner.
27. Klicka på Välj verifikationsmall.
28. Sök efter mallen som du skapade tidigare. Klicka på OK.
    * Du kan behöva klicka på föregående steget och sedan välja korrekt mallen, om annan mallar finns.  
29. Ange det belopp som ska användas för verifikationen i beloppsfältet.
    * Beloppsfältet visas bara om verifikationsmallen är av typen Procent.  
30. Klicka på OK.

