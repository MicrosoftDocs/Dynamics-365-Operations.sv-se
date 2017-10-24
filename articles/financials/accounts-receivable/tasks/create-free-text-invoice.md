--- 
title: Skapa en fritextfaktura
description: "Den här uppgifthandboken visar hur du skapar en fritextfaktura."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33324a9b95026600bcc6facb9c22a04fd2e323c8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandboken visar hur du skapar en fritextfaktura. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Kundreskontra > Fakturor > Alla fritextfakturor.
2. Klicka på Ny.
3. Välj ett värde i fältet Kundkonto.
    * Fakturakontot blir som standard samma konto som används för kundkontot.   
    * Redovisningsstatusen börjar med Pågår om fakturan inte har bokförts.   
    * Fakturanumret tilldelas när fakturan bokförs.  
    * Om du använder SEPA-fullmakter, fylls autogiromedgivandet i automatiskt med en fullmakt när du väljer kundkontot.  
4. Ange ett värde i fältet Beskrivning.
5. Ange ett kontonummer utan dimensioner i huvudkontofältet.
    * Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot. Du anger dimensioner senare i den här handboken.  
6. Expandera snabbfliken Radinformation så att du kan lägga till dimensioner i huvudkontot.
7. Klicka på fliken Rad för ekonomisk dimension.
    * Dimensionerna avser endast den valda raden.    
    * Momsgruppen fylls i från kunden. Om kunden inte har en momsgrupp, används momsgruppen från huvudkontot.  
    * Artikelmomsgruppen fylls i från huvudkontot. Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen i redovisningens momsparametrar.    
8. Ange ett tal i fältet Kvantitet.
    * Kvantiteten är valfri.  
9. Ange ett tal i fältet Enhetspris.
    * Enhetspriset är valfritt.  
    * Beloppet beräknas som kvantitet gånger enhetspriset. Du kan dock åsidosätta den beräkningen och ange ett belopp.  
10. Om du vill visa moms som beräknats för din faktura klickar du på Moms.
    * Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken Justering.  
11. Klicka på OK.
12. Klicka på Avgifter om du vill lägga till en avgift i din faktura. 
13. I fältet Kod för avgifter, skriv ett värde.
14. I fältet Avgiftsvärde, ange ett värde.
15. Stäng sidan.
16. Klicka på Summor för att visa sammanfattande fakturadetaljer och summor.
17. Klicka på Stäng.
18. Klicka på Bokför när du vill bokföra fakturan. Du kan avbryta innan du bokför.
    * Om du vill ändra timing på din fakturautskrift: Välj Aktuell om du vill skriva ut fakturor när de uppdateras eller välj Efter om du vill skriva ut när alla fakturor har uppdaterats.  
    * Om du vill ändra hur kundens kreditgräns kontrolleras innan bokföring, ändra kreditgränstypen.  
    * Välj Ja om du vill skriva ut fakturan.  
    * Välj Ja om du vill bokföra fakturan. Du kan skriva ut fakturan utan bokföring.  
19. Klicka på OK.


