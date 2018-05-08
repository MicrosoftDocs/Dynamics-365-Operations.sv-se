--- 
title: "Beräkna avskrivning av anläggningstillgången över juridiska personer"
description: "Den här proceduren visar hur du ställer in och kör avskrivningsprocessen för flera juridiska personer."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: sv-se
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Beräkna avskrivning av anläggningstillgången över juridiska personer

[!include [task guide banner](../../includes/task-guide-banner.md)]

Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg. Den här proceduren visar hur du ställer in och kör processen för flera juridiska personer. Den använder rollen Revisor.  

I den här registreringen används demonstrationsföretaget USMF.


Steg (16) Deluppgift: Ställ avskrivningsjournaler som körs mellan företag. 

1. Först måste du konfigurera journalerna som ska användas i avskrivningkörningar mellan företag i respektive juridisk person. Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar. 
2. Expandera avsnittet Förslag på anläggningstillgång. 
3. Skapa en post med journalnamnet som ska användas för varje bokföringsskikt hos den juridiska personen. Om avskrivningsregler inte bokförs i redovisningen, bör inget bokföringsskikt väljas med tillhörande journal. Klicka på Lägg till. 
4. Ange bokföringsskikt eller välj ett värde i bokföringsfältet. 
5. Ange eller välj ett värde i fältet Journal name. 
6. Upprepa journalinställningen på sidan Parametrar för anläggningstillgångar i respektive juridisk person. 

Deluppgift: Beräkna avskrivning.

1. Använd sidan Skapa avskrivningsförslag för att påbörja din avskrivningskörning i juridiska personer. Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag. 
2. Ange bokföringsskikt eller välj ett värde i bokföringsfältet. 
3. Journalnamnet hämtas som standard från parametrar för anläggningstillgångar. Det kan ändras här för den aktuella juridiska personen. 
4. Ange ett datum i fältet Till datum. 
5. Välj de juridiska personerna som ska inkluderas i avskrivningskörningen. Endast juridiska personer med journaler som är inställda för Förslag på anläggningstillgång på sidan Parametrar för anläggningstillgånga visas i listan. 
6. När du har aktiverat det kommer alternativet Bokför journaler automatiskt att bokföra avskrivningsjournalerna när de skapas. När de inte är markerade kommer journalerna att skapas, men inte bokföras, så att du kan granska informationen innan du bokför. Välj Ja i fältet Bokför journaler. 
7. Filtrering av fält inkluderar alla anläggningstillgångar, grupper och böcker för de juridiska personerna som valts för denna avskrivning. 
8. Alternativet Batchbearbetning aktiveras som standard. När detta alternativ är aktiverat körs skapande och bokföring av avskrivningjournal i bakgrunden. 
9. Kicka på Skapa journal. 
10. Du måste visa avskrivningsjournalerna som skapades i respektive juridiska personer. Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.

