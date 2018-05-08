--- 
title: "Konfigurera påfyllnadsbearbetning"
description: "I den här guiden beskrivs hur du ställer in villkoren som avgör vilket arbete som genereras för ett lagerställe när en påfyllnad bearbetas och om påfyllnad bearbetas manuellt eller automatiskt."
author: YuyuScheller
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f7a6db585468c235e07c4a0117a83995ec93f4b0
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="configure-wave-processing"></a>Konfigurera påfyllnadsbearbetning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här guiden beskrivs hur du ställer in villkoren som avgör vilket arbete som genereras för ett lagerställe när en påfyllnad bearbetas och om påfyllnad bearbetas manuellt eller automatiskt. Du anger villkor genom att ställa in påfyllnadsmallar och frågor som matchar en påfyllnad mot frisläppta rader i försäljningsorder, tillverkningsorder eller kanban-ordrar. Påfyllnadsbearbetning används i lagerställen som använder funktionen i modulen Lagerstyrning och inte de som använder funktionen i modulen Lagerhantering. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.

1. Gå till Lagerstyrning > Inställningar > Påfyllnader > Påfyllnadsmallar.
2. Klicka på Ny.
3. I fältet Påfyllnadsmallnamn, skriv ett värde.
    * När du ställer in en påfyllnadsmall, anger du sekvensen i vilken mallar ska matchas för att frisläppa rader på försäljningsorder, tillverkningsorder eller kanban. När en rad frisläppts till lagerställe eller till produktion, används den första påfyllnadsmallen som den uppfyller villkoren för. Vi rekommenderar därför att du sätter mallar med det mest specifika kriteriet längst upp i listan. Ju bredare villkoren är, desto mer rimligt är det att en rad ska uppfylla kriterierna, vilket kan leda till att rader tilldelas fel påfyllnad.  
4. Skriv ett värde i fältet Beskrivning av påfyllnadsmall.
5. Ange eller välj ett värde i fältet Plats.
    * Om du använder USMF kan du välja site 2.  
6. Ange eller välj ett värde i fältet Lagerställe.
    * Om du använder USMF kan du välja lager 24.  
7. Ange fältet Automatisera skapande av påfyllnad till Ja.
    * Välj det här alternativet om du vill skapa en påfyllnad automatiskt när en försäljningsorder, produktionsorder eller kanban frisläpps till lagerstället.  
8. Ange alternativet Bearbeta påfyllnaden vid släpp till lager till Ja. 
    * Välj det här alternativet om du vill bearbeta påfyllnaden automatiskt och skapa arbete när en rad frisläpps till lagerstället.  
9. Ange alternativet Automatisera släpp av påfyllnad till Ja. 
    * Välj det här alternativet om du vill att påfyllnaden ska frisläppas automatiskt. Plockningsarbetet skapas och görs tillgängligt på mobila enheter.  
10. Ange alternativet Automatisera släpp av påfyllnad till Ja. 
    * Rader tilldelas påfyllnader baserat på frågefiltret för påfyllnadsmallen.  
11. Ange alternativet Bearbeta påfyllnad automatiskt vid tröskel till Ja. 
    * Välj det här alternativet om du vill bearbeta påfyllnaden automatiskt när dess värden når trösklarna för vikt, leverans och rader som anges i fältgruppen Påfyllnadströsklar. Detta alternativ är endast tillgängligt om Leverans har valts i fältet Påfyllnadsmalltyp.  
12. Ange alternativet Automatisera frisläppning av lagerpåfyllnadsarbete till Ja. 
    * Välj det här alternativet om du vill skapa efterfrågebaserat återanskaffningsarbete och frisläppa det automatiskt. Du måste lägga till påfyllnadsmetoden i påfyllnadsmallen och skapa en återanskaffningsmall av typen Påfyllnadsefterfrågan.  
13. Visa avsnittet Metoder.
    * Påfyllnadsmallmetoder låter dig kontrollera sekvensen av aktiviteter som varje påfyllnad genomgår, när den har bearbetats. Du kanske till exempel har en metod för lagerpåfyllnad. När du lägger till en metod, anges den automatiskt på rätt plats i sekvensen för steg. Om du har angett alternativet Automatisera frisläppning av lagerpåfyllnadsarbete till Ja, måste du lägga till påfyllningsmetoden här.  
    * Vågattribut fungerar som filter, för att begränsa vilken typ av artiklar som kan använda vågen. Du kan till exempel ange en artikelgrupp.  
14. Klicka på Spara.
15. Stäng sidan.
16. Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.
17. Visa avsnittet Påfyllnadsbearbetning.
18. Ange eller välj ett värde i fältet Batchgrupp för påfyllnadsbearbetning.
19. Ange alternativet Behandla påfyllnader i batch till Ja.
20. Ange ett nummer fältet Vänta på lås (ms).
    * Ange tiden, i millisekunder, som ett allokeringssteg ska vänta på en systemresurs som har låsts av ett annat allokeringssteg. När denna tid överskrids, bearbetas påfyllnaden inte, och ett meddelande visas.  
21. Klicka på Spara.
22. Stäng sidan.
23. Gå till Produktionskontroll > Inställningar > Produktionskontrollparametrar.
24. Markera ett alternativ i fältet Släpp till lagerställe.
    * För försäljnings - och kanbanorder måste lager reserveras om ordern har frisläppts till lagerstället. Annars kan artiklarna eller allokeringsraderna inte bearbetas i en våg. För tillverkningsorder har du även alternativet att välja Tillåt viss reservation. Detta är till exempel praktiskt om du har material som behövs för att starta en produktion, och kan vänta tills ytterligare material är tillgängligt för att avsluta processen. Om du markerar det här alternativet måste du upprepa frisläppningen till lagerprocess när ytterligare material blir tillgängliga.  
25. Stäng sidan.


