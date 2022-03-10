---
title: Skapa en journalpost med en mall
description: Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c015bbba6784f511ac51802ea005d2114e703861370e33350cff62b6005d630c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730540"
---
# <a name="create-a-journal-entry-using-template"></a>Skapa en journalpost med en mall

[!include [banner](../../includes/banner.md)]

Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder. I den här proceduren används demonstrationsföretaget USMF.

1. Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalposter > Allmänna journaler**.
2. Klicka på **Nytt** i **Åtgärdsfönstret**. I den här proceduren börjar vi med att skapa och bokföra en journal verifikation, men alla tidigare bokförd bokföringsorder kan sparas som en mall.  
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Klicka på **Rader**.
7. I fältet **Kontotyp**, skriv ett värde.
8. I fältet **Beskrivning** anger du ett värde.
9. Ange ett värde i fältet **Debet**.
10. Klicka på **Ny**.
11. I fältet **Kontotyp**, skriv ett värde.
12. I fältet **Beskrivning** anger du ett värde.
13. Ange ett värde i fältet **Debet**.
14. Klicka på **Ny**.
14. Ange önskade värden i fältet **Konto**.
15. I fältet **Beskrivning** anger du ett värde.
16. Ange ett värde för att balansera verifikationen i fältet **Kredit**.
17. Klicka på **Bokför** i **åtgärdsfönstret**.
18. Klicka på **Funktioner**.
19. Klicka på mallen **Spara verifikation**.
20. I den här proceduren förutsätts typen **Procentmall**. Klicka på OK.
    - Procent: Beloppen i verifikationen konverteras till procentsatsfaktorer, vilket innebär att alla belopp som kan användas när verifikationsmallen har valts.
    - Belopp: De möjligt att beloppen lagras och kommer att användas.  
21. Klicka på **Allmänna journaler**.
22. Klicka på **Ny**.
23. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.
24. Klicka på länken på den valda raden i listan.
25. Klicka på **Rader**.
26. Klicka på **Funktioner**.
27. Klicka på **Välj verifikationsmall**.
28. Sök efter mallen som du skapade tidigare. Klicka på **OK**. Du kan behöva klicka på  **Föregående steg** och sedan välja korrekt mallen, om annan mallar finns.  
29. Ange det belopp som ska användas för verifikationen i fältet **Belopp**. Fältet **Belopp** visas bara om verifikationsmallen är av typen Procent.  
30. Klicka på **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]