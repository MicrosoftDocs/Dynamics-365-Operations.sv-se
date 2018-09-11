--- 
title: Skapa in en kravbrevsserie
description: "Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens."
author: mikefalkner
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-collection-letter-sequence"></a>Skapa in en kravbrevsserie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Kredit och inkasso > Inställningar > Ställ in kravbrevsserier.
2. Klicka på Ny.
3. Ange sekvens-ID för att representera sekvensen i fältet Kravbrevsserie. Detta kan användas, när du ställer in en bokföringsprofil.
4. Ange ett värde i fältet Beskrivning.
    * Betalningsvillkoren är valfri. Om du anger ett värde här, ska kravbrevsavgift fakturan använda dessa betalningsvillkor istället för de betalningsvillkor som lagras med kunden.  
5. Välj kod för det första kravbrevet som du vill skicka i kravbrevskodfältet.
    * Det första kravbrevet skapas med hjälp av förfallodatumet på fakturan, det värde som du anger för respitperioden i fältet och den information som du anger på denna rad.  
6. Ange ett värde i fältet Beskrivning.
    * Valutan för avgiften anpassas till kundens valuta. Denna valutakod kan skilja sig från fakturavalutan.  
7. Klicka på Lägg till om du vill lägga till nästa kravbrev som ska skickas i sekvensen
    * I många fall är det första kravbrevet bara en varning. Du kan lägga till tillägg, om det behövs.  
8. Välj kod för nästa kravbrev som du vill skicka i sekvensen.
9. Skriv ett värde i fältet Beskrivning.
10. Välj intäktskontot som ska användas för tillägg i huvudkontofältet.
11. Ange den avgift som debiteras kravbrev, när den bokförs.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
    * Ange en artikelmomsgrupp, om moms måste beräknas på avgiften.  
13. Klicka på länken på den valda raden i listan.
14. Ange det minsta förfallna saldobeloppet som krävs innan ett kravbrev skickas.
15. Ange antalet respitdagar som tillåts.
    * Detta är antal dagar efter förfallodatumet att ett kravbrev kan genereras. Förfallodatumet som används för beräkning beror på positionen för kravbrevet i kravbrevserien: ⦁ Respitperioden för kravbrev 1 är relaterat till förfallodatumet på fakturan.  ⦁ Respitperioden för kravbrev 2 och högre är relaterade till det datum då det föregående kravbrevet bokfördes eller skrevs ut, beroende på vad som valts i fältet Uppdatera kravbrevskod på sidan Parametrar för kundreskontra.  
16. Klicka på Lägg till om du vill lägga till det sista kravbrevet i sekvensen.
    * Du kan lägga till upp till fem kravbrevskoder för en kravbrevsserie.  
17. Välj kod för nästa kravbrev som du vill skicka i sekvensen.
18. Skriv ett värde i fältet Beskrivning.
19. Ange önskade värden i fältet Huvudkonto.
20. Ange ett nummer i fältet Avgift i valuta.
21. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
22. Klicka på länken på den valda raden i listan.
23. Ange ett värde i fältet Minsta förfallet saldo.
24. Välj ett tal i fältet Dagar.
25. Markera kryssrutan om du vill stoppa ytterligare leveranser till och fakturering av kunden.
    * Om du vill ta bort spärren från kontot väljer du Nej i fältet Spärrad fakturering och leverans på sidan Kunder.  
26. Expandera snabbfliken Anmärkning.
27. Ange den text som ska visas i kravbrevet för den valda kravbrevskoden.
    * Du kan översätta den här texten in på språk med hjälp av översättningsmenyn över anmärkningsasken.  


