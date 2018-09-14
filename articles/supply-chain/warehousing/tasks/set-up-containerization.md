--- 
title: "Definiera skapande av behållare"
description: "I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeb7d956560c513c08d5e20dcf20989b49137a52
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-containerization"></a>Definiera skapande av behållare

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning. Automatiskt skapande av behållare skapar behållare och plockarbetet för leveranser när en påfyllnad bearbetas och arbetsrader kan delas i kvantiteter som passar behållarna. Detta hjälper lagerarbetare att plocka artiklarna direkt till den valda behållaren. Jämfört med den manuella förpackningsprocessen automatiseras uppgifter som till exempel att skapa behållare, tilldela artiklar och stänga behållare av systemet. I den här proceduren används USMF-demonstrationsföretaget och utförs av en lagerchef.


## <a name="set-up-a-wave-template"></a>Ställa in en påfyllnadsmall
1. Gå till Lagerstyrning > Inställningar > Påfyllnader > Påfyllnadsmallar.
2. Klicka på Ny.
3. I fältet Påfyllnadsmallnamn, skriv ett värde.
4. Skriv ett värde i fältet Beskrivning av påfyllnadsmall.
5. Ange eller välj ett värde i fältet Plats.
6. Ange eller välj ett värde i fältet Lagerställe.
7. Visa avsnittet Metoder.
    * Fönstret Valda metoder visar metoderna för den valda påfyllnadsmallstypen. Påfyllnadsmallen måste inkludera metoden för skapande av behållare.  
8. Hitta och markera önskad post i listan.
9. I fältet Kod för påfyllnadssteg, skriv ett värde.
    * Ange en Kod för påfyllnadssteg för den tillagda metoden, som kan vara en kod. Det går att lägga till metod mer än en gång och tilldela olika koder för påfyllnadssteg. Om du vill göra detta väljer du Kan upprepas för den här metoden på sidan Metoder för bearbetning av påfyllnad.  
10. Klicka på Spara.
11. Stäng sidan.

## <a name="set-up-a-container-type"></a>Ställ in en behållartyp
1. Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.
    * Du kan definiera dina behållare på sidan Behållartyper. Du kan konfigurera de fysiska dimensionerna på behållare, inklusive taravikt, högsta vikt, högsta volym, längd, bredd, vikt och höjd. I det här exemplet har vi tre olika storlek på boxar.  
2. Klicka på Ny.
3. Ange ett värde i fältet Behållartypkod.
4. Ange ett nummer i fältet Taravikt.
5. Ange ett värde i fältet Högsta vikt.
6. Välj ett nummer i fältet Volym.
7. I fältet Längd, ange ett tal.
8. Ange ett värde i fältet Bredd.
9. Ange ett värde i fältet Höjd.
10. Ange ett värde i fältet Beskrivning.
11. Klicka på Spara.
12. Klicka på Ny.
13. Ange ett värde i fältet Behållartypkod.
14. Ange ett värde i fältet Beskrivning.
15. Ange ett nummer i fältet Taravikt.
16. Ange ett värde i fältet Högsta vikt.
17. Välj ett nummer i fältet Volym.
18. I fältet Längd, ange ett tal.
19. Ange ett värde i fältet Bredd.
20. Ange ett värde i fältet Höjd.
21. Klicka på Spara.
22. Klicka på Ny.
23. Ange ett värde i fältet Behållartypkod.
24. Ange ett värde i fältet Beskrivning.
25. Ange ett nummer i fältet Taravikt.
26. Ange ett värde i fältet Högsta vikt.
27. Välj ett nummer i fältet Volym.
28. I fältet Längd, ange ett tal.
29. Ange ett värde i fältet Bredd.
30. Ange ett värde i fältet Höjd.
31. Klicka på Spara.
32. Stäng sidan.

## <a name="set-up-a-container-group"></a>Ställ in en behållargrupp
1. Gå till Lagerstyrning > Inställningar > Behållare > Behållargrupper.
2. Klicka på Ny.
    * Du kan ställa in logiska grupper av behållartyper. För varje grupp kan du ange sekvens för packning av containrar och procentsatsen av containrarna som ska fyllas. I används storleksdimensioner för artikeln för att avgöra om den passar i en behållare. Den behållare som är närmast artikelns storlek används. Om du har flera behållartyper i en grupp, rekommenderar vi att sekvensen ordnas efter storlek, så att den största, är den första nummer 1 i sekvensen, och den mest minsta behållaren är den sista.    
3. Skriv ett värde i fältet Behållargrupp-ID.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Ny.
6. Markera vald rad i listan.
7. Ange eller välj ett värde i fältet Attributtyp.
8. Klicka på Ny.
9. Markera vald rad i listan.
10. Ange eller välj ett värde i fältet Attributtyp.
11. Klicka på Ny.
12. Markera vald rad i listan.
13. Ange eller välj ett värde i fältet Attributtyp.
14. Klicka på Spara.
15. Stäng sidan.

## <a name="set-up-a-container-build-template"></a>Ställa in en behållarversionsmall
1. Gå till Lagerstyrning > Inställningar > Behållare > Mall för skapande av behållare.
2. Klicka på Ny.
    * Behållareversionmallen baseras på vilket process för skapande av fraktbehållare som utförs. Varje behållareversionmall definierar en process för skapande av fraktbehållare som ska användas i en påfyllnadsmall. Alternativet Redigera fråga låter dig definiera de villkor som den valda mallen ska bearbeta. Till exempel vill du kanske bara att köra skapande av fraktbehållare för specifika kunder, produkter, eller lagerställen och du kan lägga till motsvarande frågeintervall i mallen. Fältet Kod för påfyllnadssteg är hur en behållarversionsmall länkas till steg i en påfyllnadsmall. När en påfyllnad körs, bestämmer den vilka/vilken behållarversionsmall(ar) som används för att initiera skapande av fraktbehållare. Fältet Basfrågetyper bestämmer vad som ska packas och vad filterfrågan ska baseras på.  
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Behållarmall-ID.
5. I fältet Behållargrupp kan du ange eller välja ett värde.
6. I fältet Kod för påfyllnadssteg, skriv ett värde.
7. Markera kryssrutan Tillåt delade plockningar.
8. Klicka på Spara.
9. Klicka på Blandade begränsningar för behållare.
    * Avbrott för blandningslogik låter dig ställa in regler för att packa allokeringsrader i behållare. Om du t.ex. lägger till fältet Artikelnummer, när artiklar tilldelas till behållare, kommer en ny behållare att skapas om det finns ett nytt artikelnummer. Detta kommer att förebygga att arbetare packar allokeringsrader för två olika kunder i samma behållare.  
10. Klicka på Ny.
11. Markera ett alternativ i fältet Tabell.
12. Ange eller välj ett värde i fältet Välj.
13. Klicka på OK.


