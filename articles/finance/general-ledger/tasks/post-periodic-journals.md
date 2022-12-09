---
title: Bokför periodiska journaler
description: Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas.
author: aprilolson
ms.date: 11/21/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc1d9f67a515e3cdc45e173b88982feceb0ebfd
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799397"
---
# <a name="post-periodic-journals"></a>Bokför periodiska journaler

[!include [banner](../../includes/banner.md)]

Periodiska journaler kallas ibland återkommande journaler eftersom beloppet, texten och informationen upprepas varje gång som den periodisk journalen hämtas. När du skapar och bokför en periodisk journal anger du periodintervallet för upprepningen, till exempel dagar eller månader. I den här uppgiftsguiden skapas en periodisk journal med månadsvis upprepningar.

1. Gå till **Navigeringsfönstret > Moduler > Redovisning > Periodiska uppgifter > Periodiska journaler**.
2. Klicka på **Ny**.
3. I fältet **Namn** anger eller väljer du ett värde.
4. Klicka på länken på den valda raden i listan.
5. I fältet **Beskrivning** anger du ett värde. Beskrivningen är namnet på den periodiska journalen när den hämtas senare, så se till att ge den ett relevant namn.
6. Klicka på **Rader** i **åtgärdsfönstret**. En periodisk journal vanligtvis kommer att innehålla flera journalrader. Den här uppgiftguiden lägger bara till en rad.
7. Ange ett datum i fältet **Datum.** Fältet **Datum** innehåller bokföringsdatumet för nästa överföring till den dagliga journalen. För journaler som ska hämtas varje månad rekommenderas du att använda datumet i månaden när de bokförs. Detta är vanligtvis det första eller sista datumet i perioden. Med fältet **Tomt datum** är det möjligt att lämna fältet **Datum** tomt och ge ett datum när journalen hämtas. Fältet uppdateras till nästa återkommande datum då transaktioner hämtas. 
8. Ange önskade värden i fältet **Konto**.
9. Ange eller välj ett värde i fältet **Beskrivning**.
10. Stäng sidan.
11. I fältet **Debit** anger du ett nummer.
12. Ange önskade värden i fältet **Motkonto**.
13. Välj **Månader** i fältet **Enhet**.
14. I fältet **Antal enheter** anger du **1**.
15. Ange ett datum i fältet för **senaste datum**. Om du anger det senaste datumet i den föregående perioden förhindras den återkommande journalen att skapas av misstag i fel startperiod. Senaste datum kommer att uppdateras senare, varje gång den periodiska journalen hämtas. 
16. Klicka på **Spara**.
17. Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalposter > Allmänna journaler**.
18. Klicka på **Ny**.
19. I fältet **Namn** anger eller väljer du ett värde.
20. Hitta och markera önskad post i listan.
21. Klicka på länken på den valda raden i listan.
22. I fältet **Beskrivning** anger du ett värde.
23. Klicka på **Rader** i **åtgärdsfönstret**.
24. Klicka på **Journalkontroll** i **Periodjournal**.
25. Klicka på **Hämta journal**.
26. I fältet **Till-datum**, anger du ett datum. **Till-datumet** fungerar som brytdatum för de periodiska verifikationsraderna. Baserat på återkommandeinställningen kan **senaste datum** och **till-datum** på samma rad inkluderas mer än en gång i den resulterande journalen. **Till-datum** uppdateras automatiskt på grundval av sessiondatumet för den senaste gången den periodiska raden överfördes till en journal. 
27. Ange eller välj ett värde i fältet **Periodisk journal**.
28. Klicka på länken på den valda raden i listan.
29. Klicka på **OK**. Periodjournalen kan nu granskas, godkännas eller bokföras beroende på inställningar och krav.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
